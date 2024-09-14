# AWS-Employee-Profile-Application-Project

This project is a web application that allows employees of XYZ Company to input their information, including uploading photos, and view their profiles. The application uses various AWS services to manage employee data, store images, and provide a scalable and secure solution.

## Project Overview

### Application Features:
- **New Employee Input**: Allows new employees to enter their information and upload a profile photo.
- **Existing Employee Information Retrieval**: Employees can retrieve their profile information using their employee ID.

### Architecture:

The project utilizes the following AWS components:

- **Public Subnet**: For the Load Balancer.
- **Private Subnet**: For EC2 instances and RDS.
- **Application Load Balancer (ALB)**: Distributes incoming traffic across EC2 instances.
- **EC2**: Hosts the application.
- **RDS (MySQL)**: Stores employee data.
- **DynamoDB**: Stores image metadata.
- **S3 Bucket**: Stores employee images and hosts the static web page.

### Technical Architecture:

1. **Frontend**:
   - A static website hosted on S3 with pages for:
     - Main Page
     - About Us
     - Employee Information (Input form for employee details)

2. **Backend**:
   - Employee data is stored in an RDS MySQL database.
   - Images uploaded by employees are stored in an S3 bucket, and metadata is stored in DynamoDB.

### AWS Setup:

1. **VPC Setup**:
   - 1 Public Subnet and 2 Private Subnets.
   - Create a bastion host in the public subnet to access the EC2 instances in private subnets.
   
2. **Security**:
   - Setup Security Groups and Network ACLs for VPC and instances.

3. **Storage**:
   - Create S3 buckets for image storage and static website hosting.

4. **Database**:
   - Launch RDS MySQL instance and create the employee table.
   - Create a DynamoDB table to store image metadata.

5. **Auto-Scaling**:
   - Setup Auto Scaling Group (ASG) for EC2 instances.

### Application Logic:

1. **User Input**:
   - Name
   - Location
   - Technology
   - Salary

   Data is then inserted into the RDS MySQL database.

2. **Employee Retrieval**:
   - Employee ID is used to fetch and display employee information.

### Steps to Deploy:

1. **Create VPC and Subnets**.
2. **Launch Bastion Host and EC2 Instances**.
3. **Create and Configure Security Groups and Firewalls**.
4. **Create S3 Bucket** for image storage and static website hosting.
5. **Setup RDS MySQL Instance** and create the `employee` table.
6. **Create DynamoDB Table** for image metadata.
7. **Set up Auto Scaling Group and Load Balancer.
8. **Test the Application** by uploading employee details and photos.

## Requirements

- AWS account with access to EC2, RDS, S3, DynamoDB, Application Load Balancer.

## Author

This project was created as part of the AWS Foundation case study.
