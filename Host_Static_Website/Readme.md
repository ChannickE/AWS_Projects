
Project #1: Host a website on AWS

This project will guide you through setting up a personal website using Amazon S3 and connecting it with a custom domain through Amazon Route 53.

Step #1: Design Your Website

Design your own personal website. Personally, I created a portfolio website for myself.

Step #2: Set Up Amazon S3 Bucket

Amazon S3 is the service that would hold the content of your website.
S3 is the perfect solution for hosting static website.
Go to the AWS Management Console and open the Amazon S3 console.
Click "Create bucket" and enter a unique name for your bucket.
In the "Properties" section, enable "Static website hosting."
Upload your website files to the bucket.
Set the bucket permissions to allow public access.

Step #3: Purchase a Custom Domain through Amazon Route 53

Open the Amazon Route 53 console.
Choose "Domain registration" and then "Register domain."
Follow the prompts to purchase your custom domain.
In the "Route 53 hosted zones," create a new record set.
Enter your S3 bucket's endpoint as the alias target.

![AWS Project 1](https://github.com/ChannickE/AWS_Projects/assets/148730724/f012badb-fbfa-47d5-a839-01dc3833837e)
