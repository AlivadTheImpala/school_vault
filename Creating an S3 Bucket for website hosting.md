1. In AWS services find and click on s3
2. Click Create Bucket
3. name your bucket (only lowercase)
4. Review settings as you scroll down, leave default values or make changes as needed.
5. "Create bucket"
6. You will be taken to the S3 dashboard and can see your bucket in the list 
7. Click on your buckets name and you will be taken to its dashboard
8. Select properties
9. Scroll down till you see Static Web Hosting and edit
10. Enable "static web hosting"
11. for index document enter "index.html"
12. Save changes 
13. In your buckets dashboard, go to the "objects tab"
14. Click Upload to upload your static web files
15. Drag and drop your files then click upload at the bottom
16. Now in your buckets dashboard click "Permissions"
17. Edit the "Block public access"
18. uncheck "block all public access"
19. click save changes, enter "confirm" in the prompt, then click confirm.
20. Scroll till you see Bucket Policy and edit
21. paste this into the policy and replace "myitbucketyo" with whatever your bucket is called.
```json
{ "Version":"2012-10-17",
"Statement":[{ "Sid":"PublicReadGetObject",
"Effect":"Allow", "Principal": "*",
"Action":["s3:GetObject"], "Resource":["arn:aws:s3:::myitbucketyo/*" ]
} ]
}
```
22. 