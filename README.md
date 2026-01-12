# AWS Static Website Hosting (S3 + CloudFront)

This project demonstrates how to host a static website on AWS using **Amazon S3** and **Amazon CloudFront** without purchasing a custom domain.

---

## 🧰 Technologies Used
- Amazon S3 (Static Website Hosting)
- Amazon CloudFront (CDN)
- HTML

---

## 🏗️ Architecture
User → CloudFront → S3 Bucket

---

## 📁 Project Structure


---

## ⚙️ Setup Steps

### 1️⃣ Create S3 Bucket
- Create an S3 bucket
- Disable **Block all public access**
- Enable **Static website hosting**
- Set index document to `index.html`

---

### 2️⃣ Upload Website Files
- Upload `index.html` to the S3 bucket

---

### 3️⃣ Configure Bucket Policy
```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::YOUR_BUCKET_NAME/*"
    }
  ]
}


4️⃣ Create CloudFront Distribution

- Origin: S3 bucket
- Viewer protocol policy: Redirect HTTP to HTTPS
- Default root object: index.html

5️⃣ Access Website

Use CloudFront distribution URL:
http://snehaingole.com.s3-website-us-east-1.amazonaws.com/

✅ Output

The website loads securely via HTTPS using CloudFront CDN.

🎯 Key Learnings

- Static website hosting with S3
- CDN caching with CloudFront
- Default root object configuration
- Cache invalidation

📌 Author

Sneha Ingole