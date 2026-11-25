# Project 3: Static Website Hosting Using Amazon S3

 Project Overview

This project demonstrates how to host a static website using Amazon Simple Storage Service (Amazon S3).

The website was created using HTML and CSS, uploaded to an S3 bucket, and configured for static website hosting. Public read access was configured using an S3 bucket policy, allowing visitors to access the website through its S3 website endpoint.

 AWS Services Used

  Amazon S3
  AWS Management Console

  Technologies Used

  HTML
  CSS
  Amazon S3 Static Website Hosting
  JSON Bucket Policy

  Project Implementation

  1. Created an S3 Bucket
  Created a new general-purpose S3 bucket.
  Selected the Europe (Stockholm) region (`eu-north-1`).

  3. Created the Website
 Created an `index.html` file using HTML and CSS.
 Designed a simple cloud portfolio webpage.

   4. Uploaded Website Files
   Uploaded `index.html` to the S3 bucket.

  5. Enabled Static Website Hosting
   Enabled static website hosting in the bucket properties.
   Configured `index.html` as the index document.

  6. Configured Public Access
  Updated the bucket's Block Public Access settings.
  Added a bucket policy granting public read access (`s3:GetObject`) to website objects.

  7. Tested the Website
  Opened the S3 website endpoint in a browser.
  Successfully verified that the website was accessible.



 Screenshots
 S3 bucket created
 HTML file uploaded
 Static website hosting enabled
 S3 bucket policy
 Working S3 static website

 What I Learned

  How to create and configure an Amazon S3 bucket.
  How to upload website files to S3.
  How to enable static website hosting.
  How to configure public read access using an S3 bucket policy.
  How to access and test a website using an S3 website endpoint.

## Cleanup

AWS resources were created for hands-on learning and practice. The S3 bucket and associated configuration can be deleted after the project demonstration to avoid unnecessary charges.
