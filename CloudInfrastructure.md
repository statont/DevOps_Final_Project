# **Cloud Infrastructure**
- uname -a
    - verifies the instance is working properly
- df -h
    - shows file systems and available space
- sudo yum install *{httpd}* (web server)
    - installs web server
- sudo systemctl start *{httpd}*
    - starts service
    - use public ip or dns address to navigate to webpage
- sudo poweroff
    - use when finished to avoid unnecessary charges
### S3 Storage
**Place in bucket Policy:**
```
{
    "Version": "2012-10-17",
    "Statement": [
    {
      "Effect": "Allow",
      "Principal": "*",
      "Action": [
        "s3:GetObject"
      ],
      "Resource": "arn:aws:s3:::YOUR_BUCKET_NAME/*"
    }
  ]

}
```
### IAM (Users)
- add user
### Security Groups
- edit inbound rules
- edit outbound rules