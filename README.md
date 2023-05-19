# vaik-website
This project to create the static website (http://vaik-bucket.s3-website-ap-southeast-2.amazonaws.com)

In order to create the static website using the S3 bucket, you have to follow the below steps.

1.Create an S3 Bucket:

You have to the AWS Management Console and navigate to the S3. Then click on Create bucket and provide a unique name for your bucket. After that choose the region for your bucket. Finally leave the default settings as they are and click on Create bucket.

2.Enable the static website hosting

In the bucket, Goto properties and edit the static website hosting. Enable the static website hostings and add the file name of the index file. then save the changes.

3. Remove the block public access and add the bucket policy to access the website publickly.

In permissions, Edit the block public access and clear all ticks. Edit the bucket policy and add below policy and change the bucket arn accoridng to your bucket name arn. 

{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "PublicReadGetObject",
            "Effect": "Allow",
            "Principal": "*",
            "Action": [
                "s3:GetObject"
            ],
            "Resource": [
                "arn:aws:s3:::Bucket-Name/*"
            ]
        }
    ]
}

4. Finally upload your index file inside your bucket and check your static website.
