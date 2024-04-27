# DevOpsProject
Simple DevOps Project using Terraform in AWS
In this Realtime DevOps project we will be using Terraform and AWS Cloud to set up static website hosting fully automated in just 3 seconds.

1. **Prerequisites:**
   - Have an AWS account.
   - Install Terraform.
     ```
     terraform --version
     ```

2. **Setup:**
   - Create a folder for the project.
     ```
     mkdir my_S3_static_website
     cd my_S3_static_website
     code .  # Open in VS Code
     ```

3. **Provider Configuration:**
   - Create a `providers.tf` file to define AWS as the provider.
     ```
     provider "aws" {
       region = "your_region"
     }
     ```
   - Initialize Terraform with the AWS provider.
     ```
     terraform init
     ```

4. **Bucket Creation:**
   - Define variables in a `variables.tf` file (e.g., bucket name).
     ```
     variable "bucket_name" {
       default = "your_bucket_name"
     }
     ```
   - Create an S3 bucket using Terraform in `main.tf`.
     ```hcl
     resource "aws_s3_bucket" "my_bucket" {
       bucket = var.bucket_name
       acl    = "private"
     }
     ```
   - Apply changes:
     ```
     terraform apply -auto-approve
     ```

5. **Static Website Hosting:**
   - Enable static website hosting for the S3 bucket.
   - Upload website files (index.html, error.html, images) to the bucket.
   - Ensure proper ACL settings for public access if needed.

6. **Testing and Optional Configuration:**
   - Test the accessibility of the website.
   - Optionally, connect a domain name to the S3 website.
   - Check the configuration, make adjustments if necessary.

7. **Output Configuration (Optional):**
   - Create an `outputs.tf` file to define any desired outputs (e.g., website endpoint).

8. **Final Testing and Cleanup:**
   - Test the website functionality again.
   - Optionally, upload the code to GitHub for sharing.
   - Destroy resources if necessary for cleanup.
     ```
     terraform destroy -auto-approve
     ```

OUTPUT

