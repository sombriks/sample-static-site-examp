# Static site from aws s3

Static sites on amazon s3 are dead simple.

## Before begin

See this article in order to
[configure aws cli](https://sombriks.com.br/#/blog/0032-introduction-to-aws-cli.md).

## Amazon s3 setup

```bash
# Create the bucket
aws s3api create-bucket --bucket 2022-my-static-bucket

# set access policies
aws s3api put-bucket-policy --bucket 2022-my-static-bucket --policy file://s3-bucket-policy.json

# put the site resources there
aws s3 cp ./site s3://2022-my-static-bucket --recursive

# enable website mode
aws s3 website s3://2022-my-static-bucket/ --index-document index.html
```

[Visit site](http://2022-my-static-bucket.s3-website-us-east-1.amazonaws.com/)

## Cloudfront setup

At first, it was not working. But a simple email to amazon support enabled my
account to use cloudfront

Set up a https and dns name for that site.
