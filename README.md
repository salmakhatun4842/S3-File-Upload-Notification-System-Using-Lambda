# S3-File-Upload-Notification-System-Using-Lambda


📌 Project Overview The S3 File Upload Notification System is an event driven AWS solution that automatically sends email notifications whenever a file is uploaded to an Amazon S3 bucket. This project demonstrates serverless architecture using AWS managed services with minimal operational overhead.

🛠️ AWS Services Used Amazon S3 AWS Lambda Amazon SNS Amazon CloudWatch AWS IAM 🏗️ Architecture Flow Summary User uploads a file to Amazon S3 S3 detects object creation event S3 triggers AWS Lambda Lambda extracts file metadata SNS sends email notification CloudWatch logs execution

🚀 Step by Step Implementation 🪣 Step 1. Create an S3 Bucket Open AWS Management Console Go to Amazon S3 Click Create bucket Enter a unique bucket name Choose a region Keep default settings Create the bucket Purpose This bucket stores files uploaded by users.

📢 Step 2. Create an SNS Topic Open Amazon SNS Click Create topic Type - Standard Topic name is S3-Notification-System Create topic Purpose SNS sends email notifications when a file is uploaded.

📧 Step 3. Subscribe Email to SNS Topic Open the SNS topic Click Create subscription Protocol - Email Endpoint - Your email address Create subscription Confirm the subscription from your email Purpose Registers email recipients for notifications.

🔐 Step 4. Create an IAM Role for Lambda Go to IAM Create role Trusted entity. AWS service Use case. Lambda Attach policies AmazonS3ReadOnlyAccess AmazonSNSFullAccess CloudWatchLogsFullAccess Create role Purpose Allows Lambda to read S3 events, publish SNS messages, and write logs.

⚡ Step 5. Create a Lambda Function Open AWS Lambda Click Create function Author from scratch Function name - s3-notification-lambda Runtime - Python 3.x Role - Use existing role Select the IAM role created earlier

🧠 Step 6. Add Lambda Function Code

🔁 Step 7. Configure S3 Event Trigger Open the S3 bucket Go to the Properties tab Scroll down to Event notifications Click Create event notification Event name. file-upload-event Event type. All object create events Destination. Lambda function Select your Lambda function Save changes Purpose This configuration automatically triggers the Lambda function whenever a new file is uploaded to the S3 bucket.

🧪 Step 8. Test the System Open the S3 bucket Upload any file, for example test.txt The upload automatically triggers Lambda Lambda publishes a message to SNS An email notification is sent to the subscribed email address Expected Result You should receive an email containing the bucket name and uploaded file name.

📊 Step 9. Verify CloudWatch Logs Open Amazon CloudWatch Go to Log groups Select the log group for your Lambda function Review logs to confirm successful execution Purpose CloudWatch logs confirm that Lambda executed successfully and help with debugging if errors occur.

🎯 Learning Outcomes Learned event driven architecture using AWS services Implemented serverless automation with AWS Lambda Integrated Amazon S3, Lambda, SNS, and CloudWatch using event triggers Gained hands on experience with AWS monitoring and logging
