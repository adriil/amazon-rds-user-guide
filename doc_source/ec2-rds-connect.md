# Connecting an EC2 instance and an RDS database automatically<a name="ec2-rds-connect"></a>

You can use the RDS console to simplify setting up a connection between an EC2 instance and an RDS database\. The RDS database can be a DB instance or a Multi\-AZ DB cluster\.

![\[Automatically connect an RDS database with an EC2 instance\]](http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/images/auto-connect-rds-ec2.png)

## Overview of automatic connectivity with an EC2 instance<a name="ec2-rds-connect-overview"></a>

When you set up a connection between an EC2 instance and an RDS database automatically, RDS configures the VPC security group for your EC2 instance and for your RDS database\.

The following are requirements for connecting an EC2 instance with an RDS database:
+ The EC2 instance must exist in the same VPC as the RDS database\.

  If no EC2 instances exist in the same VPC, the console provides a link to create one\.
+ The user who is setting up connectivity must have permissions to perform the following EC2 operations:
  + `ec2:AuthorizeSecurityGroupEgress` 
  + `ec2:AuthorizeSecurityGroupIngress` 
  + `ec2:CreateSecurityGroup` 
  + `ec2:DescribeInstances` 
  + `ec2:DescribeNetworkInterfaces` 
  + `ec2:DescribeSecurityGroups` 
  + `ec2:ModifyNetworkInterfaceAttribute` 
  + `ec2:RevokeSecurityGroupEgress` 

If the DB instance and EC2 instance are in different Availability Zones, there is the possibility of cross Availability Zone costs\.

When you set up a connection to an EC2 instance, RDS takes an action based on the current configuration of the security groups associated with the RDS database and EC2 instance, as described in the following table\.


****  

| Current RDS security group configuration | Current EC2 security group configuration | RDS action | 
| --- | --- | --- | 
|  There are one or more security groups associated with the RDS database with a name that matches the pattern `rds-ec2-n` \(where `n` is a number\)\. A security group that matches the pattern hasn't been modified\. This security group has only one inbound rule with the VPC security group of the EC2 instance as the source\.  |  There are one or more security groups associated with the EC2 instance with a name that matches the pattern `rds-ec2-n` \(where `n` is a number\)\. A security group that matches the pattern hasn't been modified\. This security group has only one outbound rule with the VPC security group of the RDS database as the source\.  |  RDS takes no action\. A connection was already configured automatically between the EC2 instance and RDS database\. Because a connection already exists between the EC2 instance and the RDS database, the security groups aren't modified\.  | 
|  Either of the following conditions apply: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/ec2-rds-connect.html)  |  Either of the following conditions apply: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/ec2-rds-connect.html)  |  [RDS action: create new security groups](#rds-action-create-new-security-groups)  | 
|  There are one or more security groups associated with the RDS database with a name that matches the pattern `rds-ec2-n`\. A security group that matches the pattern hasn't been modified\. This security group has only one inbound rule with the VPC security group of the EC2 instance as the source\.  |  There are one or more security groups associated with the EC2 instance with a name that matches the pattern `ec2-rds-n`\. However, none of these security groups can be used for the connection with the RDS database\. A security group can't be used if it doesn't have one outbound rule with the VPC security group of the RDS database as the source\. A security group also can't be used if it has been modified\.  |  [RDS action: create new security groups](#rds-action-create-new-security-groups)  | 
|  There are one or more security groups associated with the RDS database with a name that matches the pattern `rds-ec2-n`\. A security group that matches the pattern hasn't been modified\. This security group has only one inbound rule with the VPC security group of the EC2 instance as the source\.  |  A valid EC2 security group for the connection exists, but it is not associated with the EC2 instance\. This security group has a name that matches the pattern `rds-ec2-n`\. It hasn't been modified\. It has only one outbound rule with the VPC security group of the RDS database as the source\.  |  [RDS action: associate EC2 security group](#rds-action-associate-ec2-security-group)  | 
|  Either of the following conditions apply: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/ec2-rds-connect.html)  |  There are one or more security groups associated with the EC2 instance with a name that matches the pattern `rds-ec2-n`\. A security group that matches the pattern hasn't been modified\. This security group has only one outbound rule with the VPC security group of the RDS database as the source\.  |  [RDS action: create new security groups](#rds-action-create-new-security-groups)  | 

**RDS action: create new security groups**  
RDS takes the following actions:
+ Creates a new security group that matches the pattern `rds-ec2-n`\. This security group has an inbound rule with the VPC security group of the EC2 instance as the source\. This security group is associated with the RDS database and allows the EC2 instance to access the RDS database\.
+ Creates a new security group that matches the pattern `ec2-rds-n`\. This security group has an outbound rule with the VPC security group of the RDS database as the source\. This security group is associated with the EC2 instance and allows the EC2 instance to send traffic to the RDS database\.

**RDS action: associate EC2 security group**  
RDS associates the valid, existing EC2 security group with the EC2 instance\. This security group allows the EC2 instance to send traffic to the RDS database\.

## Connecting an EC2 instance and an RDS database automatically<a name="ec2-rds-connect-connecting"></a>

Before setting up a connection between an EC2 instance and an RDS database, make sure you meet the requirements described in [Overview of automatic connectivity with an EC2 instance](#ec2-rds-connect-overview)\.

If you change these security groups after you configure connectivity, the changes might affect the connection between the EC2 instance and the RDS database\.

**Note**  
You can only set up a connection between an EC2 instance and an RDS database automatically by using the AWS Management Console\. You can't set up a connection automatically with the AWS CLI or RDS API\.

**To connect an EC2 instance and an RDS database automatically**

1. Sign in to the AWS Management Console and open the Amazon RDS console at [https://console\.aws\.amazon\.com/rds/](https://console.aws.amazon.com/rds/)\.

1. In the navigation pane, choose **Databases**, and then choose the RDS database\.

1. For **Actions**, choose **Set up EC2 connection**\.

   The **Set up EC2 connection** page appears\.  
![\[Set up EC2 connection page\]](http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/images/auto-connect-rds-ec2-set-up.png)

1. On the **Set up EC2 connection** page, choose the EC2 instance\.

   If no EC2 instances exist in the same VPC, choose **Create EC2 instance** to create one\. In this case, make sure the new EC2 instance is in the same VPC as the RDS database\.

1. Choose **Continue**\.

   The **Review and confirm** page appears\.  
![\[EC2 connection review and confirmation page\]](http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/images/auto-connect-rds-ec2-confirm.png)

1. On the **Review and confirm** page, review the changes that RDS will make to set up connectivity with the EC2 instance\.

   If the changes are correct, choose **Set up connection**\.

   If the changes aren't correct, choose **Previous** or **Cancel**\.