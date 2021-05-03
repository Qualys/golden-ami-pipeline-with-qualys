# AWS Golden AMI Pipeline with Qualys (Supports both Windows and Linux/Unix EC2 instances)

Allows for current and future AWS and Qualys customers to implement the AWS Golden AMI Pipeline reference architecture utilizing the Qualys Scanner Appliance to scan for and report on the vulnerabilities and configuration compliance on golden image builds in the image creation process.
It uses the AWS Cloud Formation Template to assess Vulnerabilities in the EC2 instance (Windows & Linux/Unix) using Qualys scanner appliance and embeds Qualys Cloud Agent into the golden AMI. EC2 instances can be then, provisioned from these Golden AMIs and will get scanned by Qualys Cloud Agent continuously. 

## License
***THIS SCRIPT IS PROVIDED TO YOU "AS IS." TO THE EXTENT PERMITTED BY LAW, QUALYS HEREBY DISCLAIMS ALL WARRANTIES AND LIABILITY FOR THE PROVISION OR USE OF THIS SCRIPT. IN NO EVENT SHALL THESE SCRIPTS BE DEEMED TO BE CLOUD SERVICES AS PROVIDED BY QUALYS***

## Description
You can use this Cloudformation template for AWS Golden AMi Pipleine with Qualys, supports (Windows and Linux/Unix).



## Pre-Requisites:
1. All the pre-requisites mentioned in the existing PDF document should remain unchanged.

## Assumptions:
All Assumptions mentioned in the existing PDF should remain unchanged.

## Scan Workflow Pre-requisites:
Qualys Scan Flow Prerequisites
1. Create Qualys EC2 Connector
2. Create a AWS Key pair for authenticated scans on linux/Windows.
3. Define Qualys Vulnerability Scan Option Profile
4. Deploy Virtual Scanner in VPC or into a peered VPC
5. Define parent tag ID
6. Define a Policy Compliance Option Profile


## Steps:
### A] Before creating cloud formation stack using the AWS golden AMI pipeline template, ensure you note down the following information, either on clipboard, notepad or any other text editor tool.

1. EC2 Connector Id: This is connector Id of EC2 connector available in Qualys Asset View. EC2 connector creation can be done using the EC2 connector creation CF or script.
2. EC2 Connector Name: Name of the EC2 connector in Qualys Asset view.
3. VM Option Id: Id of the option profile that will be used for scanning Ec2 instance.
4. SSH Key Pair name: the AWS key pair name created for authenticating EC2 instances.
5. Parent Tag Id: Tag Id of Qualys Asset tag created in Asset view.
6. Scanner name: A general name for Qualys Scanner Appliance. For this, you need to create a Scanner Appliance in Qualys and note down its Personalization code.
7. Agent Location for DebianRPM/Windows installers: The s3 url where Qualys cloud agent installers are uploaded.
8. Activation ID & Customer Id: The agent Activation Id and customer Id retrieved from Qualys Portal.

### B] Deploy the Cloud formation template:
1. Login to AWS Console, then navigate to CloudFormation. click 'Create stack' > With new resources (standard).
2. Within Specify template, select 'Upload a template file'. Upload teh AWS Golden AMI pipeline Cloud fornation template file provided by Qualys on github. Once, file is uploaded, click 'Next'.
3. Provide the input values for parameters as in Step A. Click Next.
4. on Last page, check 'I acknowledge that AWS CloudFormation might create IAm resources' check box and click 'Create stack' to initiate deployment process.

 






