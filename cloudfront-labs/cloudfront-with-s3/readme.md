# ☁️ 🪣 Setting Up AWS CloudFront with an S3 Bucket Origin
A quick tutorial on how to use CloudFront with an S3 bucket as the origin

## 🧰 Technology Used
AWS Cloudfront
AWS S3

## 🚀 Steps 
  1. Create an S3 bucket and block all access to it
  2. Add index.html file and a couple jpg files to the S3 bucket
  3. Confirm S3 bucket is private
     - Click the Object URL from the index.html file. Confirm that access is blocked.
     - Open the URL from the console to confirm that the photo is not loading.
     - Go to the permissions tab of the S3 bucket and confirm that the bucket policy is empty.
  4. Go to the CloudFront console and create a CloudFront distribution
     - Name your distribution
     - Select origin type (Amazon S3)
     - Select origin as the S3 bucket just created
     - Allow CloudFront to access your bucket
     - Keep the Origin Path empty since the files are located in the root
     - Select "Do not enable security protections"
     - Review and create
  5. Wait for the CloudFront distribution to fully deploy
  6. In the S3 console, confirm the S3 bucket policy has been modified for CloudFront to get objects from your S3 bucket
  7. In the CloudFront distribution just created, copy the distribution domain name and paste into browser with the path `/index.html`
  8. Confirm the webpage loads showing the photo
  9. Clean up
     - Disable the CloudFront distribution (This may take a while)
     - After disabling, then delete
    
## 🧠 What I Learned
- Cloudfront is a CDN (Content Delivery Network)
- CloudFront caches content all around the world in edge locations
- You can choose the edge locations you want based on your needs
- CloudFront has several origins you can use
- You can use cache invalidation to force a full or partial cache refresh
- You can use CloudFront Geo Location to restrict access to your distribution based on country
