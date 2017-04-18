# Problem: Why curl to S3 is not working from my EC2 instance even my instance has correctly set IAM role?

Your best friend in such a situation is awscli.
Install awscli via apt or pip

```
pip install awscli
```
try to access your S3 object
```
aws s3 ls <your_bucket/your_folder/>
```

If your IAM role and S3 permissions are set correctly you should get folder contents.

But when you try with curl it does not work:

```
curl https://<amazon_s3_object_url>
```

Now the reason why AWS CLI works and curl does not is that ***curl has not way to access credentials in IAM role***. 
What IAM role does is that it periodically propagates AWS api keys to instance.

Thus instance will get access key and secret key through IAM role.

All AWS SDK libraries has credential helper which is able to access these credentials.

There is a way to see actual credential keys. If you have IAM role attached to instance you can get credentials keys from [AWS metadata URL](http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-instance-metadata.html):
```
curl http://169.254.169.254/latest/meta-data/iam/security-credentials/role-name	
```


# Solution

1. Use AWS libraries to access your content from EC2 instance (AWS CLI, boto3, nodejs etc.)
2. Build a simple parser of credentials from metadata URL
