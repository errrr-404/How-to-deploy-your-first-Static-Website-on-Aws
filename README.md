# How-to-deploy-your-first-Static-Website-on-Aws
This repository provides you the steps on how to deploy a static website built with (index.html, css and js) in aws using free tier for learning. I have broken down the simple steps, what to click and why you should click them.

# STEP 1. 
You definitely need an AWS account, then create IAM user for admin role, assign AdministratorAccess and PowerUserAccess persmission to it or the group you categorised the user to. Logout of the root user account and sign in to the admin account you just created or have already to carry out labs and activities as it is the proper routine.

# Step 2. 
You need to have built the static website already with any IDE of your choice, keeping it simple with just html, css and js.

# Step 3.
In your aws admin account, search for s3 to create a new bucket for your file upload. 
<img width="924" height="341" alt="image" src="https://github.com/user-attachments/assets/4837a005-9731-4221-91ed-04b1f3fce5c6" />

i. Leave as General Purpose
ii. For **Bucket Namespace** select Account Regional namespace ( Why ? Your bucket name gets to be unique within your own AWS account and specific region,  AWS achieves this by reserving a dedicated space for you by quietly sticking your account details onto the end of the name. For example, if you name a bucket my-app-logs, AWS generates it as:
my-app-logs-{your-account-id}-{region}-an.  The **Benefit** is No one else can steal your bucket names. You can use the exact same clean name patterns (logs, backups, etc.) across multiple projects and accounts without ever seeing a "Bucket Name Already Exists" error, and its the best option for New projects, infrastructure automation. With this little explanation you can decide your option now.
iii. Type in your bucket name prefix using hyphen inbetween (-) 

<img width="886" height="317" alt="image" src="https://github.com/user-attachments/assets/aa76eea5-f175-42ba-921a-03a49daf901f" />

iv. Leave the defualt **ACL Disabled** for Object Ownership
v. Also, do not touch the **Block Public Access Settings** leave it ticked

<img width="810" height="103" alt="image" src="https://github.com/user-attachments/assets/3a9056b9-1029-4dcf-9708-357d3ad44608" />

vi. Enable Bucket Versioning (Why? : The benefit includes **Accidental deletion Protection** because aws helps you make a copy of it down already, Second benefit is **Overwriting Protection,** if incase you upload a new file with the exact name as the existing file, AWS dosen't replace the old file, it gives the new file it own unique identity. Thirdly its support **Easy Roll back.** By the way, there's a little cost applied for every protection or feauture aws applies. For this Lab, its okay to enable bucket version, you might like to make changes later on.

<img width="880" height="354" alt="image" src="https://github.com/user-attachments/assets/938c392c-a331-4a58-8345-a76d92e805ed" />

i. For the **Default Encryption** leave as, Server-side encryption with Amazon S3 managed keys (SSE-S3). (Why? cause it cost free and easy to use, AWS handles everything in the background. It generates, manages, and rotates the security keys for you. The other options are paid, but gives you more management authority to see everything going on, but since this is a simple lab and not an enterprise platform, you're good to go with option one. 
ii. Enable bucket key
iii. In **Advance Settings (Object lock)** leave it as **disabled** (Why? It will break your workflow, since you are building a static website, you are going to want to update your index.html, fix typos, change CSS designs, or tweak your JavaScript files later. If you enable Object Lock, AWS will completely block you from overwriting or updating your website files. Who it's actually for: It is built for healthcare companies, banks, and government agencies who are legally required to store official records (like tax documents or medical history) for 5 to 10 years without any risk of tampering or accidental deletion.
iv Now, Click the **create bucket** button

# Step 4
Aws cli connection

putting files in bucket and using cloud front link to view publicly






