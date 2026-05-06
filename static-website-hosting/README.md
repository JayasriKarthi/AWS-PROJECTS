<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Host a Website on Amazon S3

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-host-a-website-on-s3)

**Author:** Jayasri Selvi  
**Email:** jayasriselvi23@gmail.com

---

![Image](http://learn.nextwork.org/confident_vermilion_curious_karearea/uploads/aws-host-a-website-on-s3_5d4474f9)

---

## Introducing Today's Project!

### Project overview

In this project, I am demonstrating the hosting of the website on  amazon s3 (amazon simple storage services)  .

### Tools and concepts

Services I used were amaxon s3 and ACL and bucket policy and hosting static website  Key concepts I learnt include how to store the file and folder in s3 bucket and how to host it on the s3 

### Time, challenges, and wins

This project took me approximately one hour The most challenging part was  resolve the troubleshooting error .

---

## How I Set Up an S3 Bucket

### What I did in this step

In this step, I am opening  amazon s3 and going  to create storage space for my website files 

### How long it took to create the bucket

Creating an S3 bucket took me just 2 minutes

### Region selection

The Region I picked for my S3 bucket was mumbai because it is the  region which is near to my current location .

### Understanding bucket name uniqueness

S3 bucket names are globally unique! This means no one can access unless the user delete the bucket

![Image](http://learn.nextwork.org/confident_vermilion_curious_karearea/uploads/aws-host-a-website-on-s3_ba6d42ad)

---

## Upload Website Files to S3

### What I did in this step

In this step, I will download the html file and zip file of images  and upload both files into s3 bucket .

### Files I uploaded

I uploaded two files to my S3 bucket - they were index. html and the another folder is nextwork everyone love ..

### How the files work together

Both files are necessary for this project as it has images and html page.

![Image](http://learn.nextwork.org/confident_vermilion_curious_karearea/uploads/aws-host-a-website-on-s3_a265af88)

---

## Static Website Hosting on S3

### What I did in this step

In this step, I will configure the s3 bucket for hosting static website 

### Understanding website hosting

Website hosting means making the website visible or accessible to any  people through the internet  in the world

### How I enabled website hosting

To enable website hosting with my S3 bucket, I need to click the enable in static website hosting.

### Access Control Lists (ACLs)

An ACL = a set of rules that decides who can get access to a resource. Enabling ACLs in this S3 setup lets you control who can access and do things with the objects (i.e. website files) you upload into your bucket. With ACLs, different AWS accounts can own and control different files in your bucket.



![Image](http://learn.nextwork.org/confident_vermilion_curious_karearea/uploads/aws-host-a-website-on-s3_c22c54c0)

---

## Bucket Endpoints

### Understanding bucket endpoint URLs

Once static website is enabled, S3 produces a bucket endpoint URL, which can be accessible anywhere but the content in the bucket cannot be accessible because it is private.

### What I saw when I tested the endpoint

When I first visited the bucket endpoint URL, I saw  the error message . The reason for this error was the content in the website is private.

![Image](http://learn.nextwork.org/confident_vermilion_curious_karearea/uploads/aws-host-a-website-on-s3_22ce4daf)

---

## Success!

### What I did in this step

In this step, I will make sure the public can see the website live on the internet .

### How I resolved the 403 error

To resolve this 403 Forbidden error, I have checked all whether the file   names are correct . all the files are uploaded .

![Image](http://learn.nextwork.org/confident_vermilion_curious_karearea/uploads/aws-host-a-website-on-s3_5d4474f9)

---

## Bucket Policies

### What I did in this extension

### Understanding bucket policies

### What my bucket policy does

---

---
