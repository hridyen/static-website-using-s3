# 🌐 Static Website Hosted on AWS S3

This project is a static, multi-page website hosted on **Amazon S3**, featuring:

- Multiple HTML pages (`index.html`, `elements.html`, `generic.html`, `landing.html`)
- CSS, JavaScript, and font files inside the `assets/` folder
- Images stored in the `images/` folder


---

## 🚀 How It's Hosted (S3 Steps)

### 1️⃣ Create an S3 Bucket
- Go to AWS S3 console and create a new bucket.
- Uncheck **"Block all public access"** and acknowledge warning.

### 2️⃣ Upload Website Files
- Upload all files and folders (`*.html`, `assets/`, `images/`).
- Preserve the folder structure.

### 3️⃣ Make Files Public
You can either:
- Use **"Make public"** action for all files, OR
- Add the following **bucket policy**:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadGetObject",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::your-bucket-name/*"
    }
  ]
}
