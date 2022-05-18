# Hello static site from aws s3

Create the bucket, set access policies and put the site resources there:

```bash
aws s3api create-bucket --bucket 2022-my-static-bucket
aws s3api put-bucket-policy --bucket 2022-my-static-bucket --policy file://s3-bucket-policy.json
aws s3 cp . s3://2022-my-static-bucket --recursive
```

[Visit site](https://2022-my-static-bucket.s3.amazonaws.com/index.html)
