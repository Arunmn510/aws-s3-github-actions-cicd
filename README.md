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

3️⃣ Add GitHub Secrets
In your GitHub repo:

Settings → Secrets → Actions → New repository secret

Add these:

AWS_ACCESS_KEY_ID

AWS_SECRET_ACCESS_KEY

AWS_REGION (e.g., us-east-1)

S3_BUCKET (your bucket name)

4️⃣ How it Works
Any push to main branch triggers the workflow

GitHub Actions syncs the website/ folder to your S3 bucket

5️⃣ View Your Website
Go to the bucket's Static Website Hosting endpoint

Example: http://my-cicd-site-bucket.s3-website-us-east-1.amazonaws.com


✅ How to Set Up

1️⃣ Create Your Repo

git init aws-s3-github-actions-cicd

cd aws-s3-github-actions-cicd

2️⃣ Add Files
Add website/ with your HTML/CSS

Add .github/workflows/deploy.yml

Add README.md

3️⃣ Push to GitHub

1 git add .
2 git commit -m "Initial commit"
3 git branch -M main
4 git remote add origin <YOUR-GITHUB-REPO-URL>
5 git push -u origin main

4️⃣ Add Secrets on GitHub

GitHub → Your Repo → Settings → Secrets → Actions

Add:
AWS_ACCESS_KEY_ID

AWS_SECRET_ACCESS_KEY

AWS_REGION

S3_BUCKET

✅ Result
✅ Every push to main → your website auto-deploys to S3 🚀

5. website preview

<img width="2880" height="1800" alt="Screenshot (80)" src="https://github.com/user-attachments/assets/29954708-d3b9-4c6c-ac9d-72869a5f1a20" />
