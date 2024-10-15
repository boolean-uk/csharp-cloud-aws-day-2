# AWS Cloud Setup

EC2 Setup & VPC Configuration

### EC2 Instance Setup
1. **Launched EC2 Instance:**
   - Created an EC2 instance with Ubuntu Server as image
   - This instance used pre-configured security group with SSH and HTTP ports open.
   - Downloaded a key pair for SSH access.

2. **Connected to EC2:**
   - SSH’d into the instance using the terminal and the downloaded key.
   - Installed required dependencies for my backend (e.g., .NET SDK, nginx).

3. **Deployed Backend:**
   - Transferred backend files using `scp`.
   - Unzipped the files and started the app with `dotnet exercise.wwwapi.dll`.

### VPC & API Gateway Setup
1. **Created VPC:**
   - Created a VPC with CIDR block `10.0.0.0/16`.
   - Set up subnets across different availability zones.

2. **Security group**
   - Created a security group for the VPC with inbound rules for HTTP and SSH.
   - Also opened ports for the backend and the database (i.e port 5432 and 5000)

3. **Configured Route Table & Gateway:**
   - Added an Internet Gateway to the VPC and set up the route tables for public subnets.

4. **Created API Gateway:**
   - Configured a REST API on API Gateway that forwards HTTP requests to my EC2 backend.