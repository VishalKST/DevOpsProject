# DevOpsProject
Simple DevOps Project using Terraform in AWS
In this Realtime DevOps project we will be using Terraform and AWS Cloud to set up static website [Personal Portfolio] hosting fully automated in just 3 seconds.

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

![1](https://github.com/VishalKST/DevOpsProject_Terraform/assets/103365187/78a42063-8681-4649-a2a9-30434abfaf95)
![2](https://github.com/VishalKST/DevOpsProject_Terraform/assets/103365187/377ea0b4-21b1-4d32-bcd9-de995bf940ff)
![3](https://github.com/VishalKST/DevOpsProject_Terraform/assets/103365187/155ca55a-3679-4c54-84d7-0672fc519121)
![4](https://github.com/VishalKST/DevOpsProject_Terraform/assets/103365187/e497315e-ef2c-4caf-a623-e58c20b3a437)
![5](https://github.com/VishalKST/DevOpsProject_Terraform/assets/103365187/73e46174-dddc-49aa-82b8-4bfb95acd2da)
![6](https://github.com/VishalKST/DevOpsProject_Terraform/assets/103365187/6a7ba7f0-ea4c-4b54-96f7-111b3ddabc71)

You can find Website link at the end og the Properties tab inside the created bucket.
![7](https://github.com/VishalKST/DevOpsProject_Terraform/assets/103365187/dd3eca2f-3385-4785-a6b3-fc699534ea03)
![8](https://github.com/VishalKST/DevOpsProject_Terraform/assets/103365187/5bc3d104-66f8-42a4-801d-207065bed2a2)
![9](https://github.com/VishalKST/DevOpsProject_Terraform/assets/103365187/e1b31bb6-af66-4395-88d8-1185112c50c8)
