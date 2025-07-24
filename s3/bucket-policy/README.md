## Create a bucket

```sh
aws s3 mb s3://bucket-policy-example-fun-234
```

## Create a Bucket Policy to allow a user in another AWS Account to access

```sh
aws s3api put-bucket-policy --bucket bucket-policy-example-fun-234 --policy file://policy.json
```

## Access S3 from another Account
```sh
touch hello.txt
aws s3 cp hello.txt s3://bucket-policy-example-fun-234
aws s3 ls s3://bucket-policy-example-fun-234
```

## Clean up

```sh
aws s3 rm s3://bucket-policy-example-fun-234/hello.txt
aws s3 rb s3://bucket-policy-example-fun-234
```