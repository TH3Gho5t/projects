<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Host a Website on Amazon S3

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-host-a-website-on-s3)

**Author:** mgardner  
**Email:** cliches_tinfoil.4r@icloud.com

---

![Image](http://learn.nextwork.org/lively_olive_quiet_oriental_melon/uploads/aws-host-a-website-on-s3_5d4474f9)

---

## Introducing Today's Project!

### Project overview

I'm doing this project to learn how to create a bucket in Amazon S3, configure a static website and make objects in the bucket public. 

### Tools and concepts

Services I used were S3 buckets... Key concepts I learnt include ACLs, bucket policy, and static website hosting.

### Time, challenges, and wins

This project took me approximately 2 days working on it in between responsibilities... The most challenging part was understanding the JSON code and what it meant when implementing the bucket policy... It was most rewarding to see the website live from just a html file...

---

## How I Set Up an S3 Bucket

### What I did in this step

In this step, I will create a bucket in Amazon S3 because this is where the files that make up the website will be stored.

### How long it took to create the bucket

Creating an S3 bucket took me less than 30 mins...

### Region selection

The Region I picked for my S3 bucket was east 1 because not only was it the closest but it is the first one Amazon launched. 

### Understanding bucket name uniqueness

S3 bucket names are globally unique! This means no one else has the same name and never will unless the name in question is deleted and no longer in use.

![Image](http://learn.nextwork.org/lively_olive_quiet_oriental_melon/uploads/aws-host-a-website-on-s3_ba6d42ad)

---

## Upload Website Files to S3

### What I did in this step

In this step, I will put the website files inside of my bucket because these files will set up and add images to the website.


### Files I uploaded

I uploaded two files to my S3 bucket - they were index.html and Nextwork_loves_files.zip

### How the files work together

Both files are necessary for this project as the .html file is like the blueprint that tells where everything should go and what things such as font will look like.  And the .zip file is what will give the website images.

![Image](http://learn.nextwork.org/lively_olive_quiet_oriental_melon/uploads/aws-host-a-website-on-s3_a265af88)

---

## Static Website Hosting on S3

### What I did in this step

In this step, I will configure the S3 bucket for static website hosting and visit the public website link.

### Understanding website hosting

Website hosting means making your website public to the internet.

### How I enabled website hosting

To enable website hosting with my S3 bucket I went  to the bucket Properties tab, enable Static website hosting, and set the index document (e.g., index.html).

### Access Control Lists (ACLs)

An ACL is a set of rules that decides who can get access to a resource.  Access Control List

![Image](http://learn.nextwork.org/lively_olive_quiet_oriental_melon/uploads/aws-host-a-website-on-s3_c22c54c0)

---

## Bucket Endpoints

### Understanding bucket endpoint URLs

Once static website is enabled, S3 produces a bucket endpoint URL, which is just like a regular website URL.  It lets people visit your S3 bucket's files like a website.

### What I saw when I tested the endpoint

When I first visited the bucket endpoint URL, I saw an error message, "403 forbidden".  The reason for this error was the website was public but the files in the bucket were still set to private, which made them inacessible.

![Image](http://learn.nextwork.org/lively_olive_quiet_oriental_melon/uploads/aws-host-a-website-on-s3_22ce4daf)

---

## Success!

### What I did in this step

In this step, I will make the objects(files) in the bucket public because that will enable the website to be fully live.

### How I resolved the 403 error

To resolve this 403 Forbidden error, I went back into my bucket settings and changed my object's ACL permissions to make them public, which allow them to be viewable on the public internet, thus resolving the 403 error message.

![Image](http://learn.nextwork.org/lively_olive_quiet_oriental_melon/uploads/aws-host-a-website-on-s3_5d4474f9)

---

## Bucket Policies

### What I did in this extension

In this project extension I'm about to setup a bucket policy to control access to the html file.  I'm doing this so that I can stop people from deleting the html file and I can also test the policy.

### Understanding bucket policies

An alternative to ACLs are bucket policies, which are a bit more advanced since it uses code.  The benefit of using bucket policies is the greater level of control over who can delete, change or upload an object compared to ACLs.  While ACLs are useful for controlling who can see/access an object.

![Image](http://learn.nextwork.org/lively_olive_quiet_oriental_melon/uploads/aws-host-a-website-on-s3_sm2sm2sm)

### What my bucket policy does

My bucket policy blocked everyone from being able to delete the index.html file.   I tested this by taking the necessary steps to delete the index.html file and saw that it failed to delete and that my access was denied.

---

---
