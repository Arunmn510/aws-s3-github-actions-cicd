# aws-s3-github-actions-cicd

# AWS S3 Static Website with GitHub Actions CI/CD

This project demonstrates how to automatically deploy a static website to AWS S3 using GitHub Actions.

## 🚀 Features
- Static website (HTML/CSS)
- Automated CI/CD deployment via GitHub Actions
- AWS S3 for static site hosting

---

## 🗺️ Steps to Use

### 1️⃣ Create an S3 Bucket
- Go to AWS S3 Console
- Click "Create bucket"
- Give it a unique name (e.g., `my-cicd-site-bucket`)
- Uncheck "Block all public access"
- Enable Static Website Hosting
- Set `index.html` as index document

---

### 2️⃣ Configure Bucket Policy

Allow public read access. Example policy:

json
{
  "Version": "2012-10-17",
  "Statement": [{
    "Sid": "PublicReadGetObject",
    "Effect": "Allow",
    "Principal": "*",
    "Action": "s3:GetObject",
    "Resource": "arn:aws:s3:::YOUR_BUCKET_NAME/*"
  }]
}
