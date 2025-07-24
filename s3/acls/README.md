## Create a bucket

```sh
aws s3 mb s3://acls-example-fun-234
```

## Turn off the Block Public Access for ACLs

```sh
aws s3api put-public-access-block \
--bucket acls-example-fun-234 \
--public-access-block-configuration "BlockPublicAcls=false,IgnorePublicAcls=false,BlockPublicPolicy=true,RestrictPublicBuckets=true"
```
 
```sh
aws s3api get-public-access-block --bucket acls-example-fun-234
```

## Change OwnerShip of Bucket

```sh
aws s3api put-bucket-ownership-controls \
--bucket acls-example-fun-234 \
--ownership-controls="Rules=[{ObjectOwnership=BucketOwnerPreferred}]"
```

## Change ACLs to allow a user in another AWS Account

```sh
aws s3api put-bucket-acl \
--bucket acls-example-fun-234 \
--access-control-policy file:///workspace/AWS-Examples-Quan/s3/acls/policy.json
```

## Access S3 from another Account
```sh
touch hello.txt
aws s3 cp hello.txt s3://acls-example-fun-234
aws s3 ls s3://acls-example-fun-234
```

## Clean up

```sh
aws s3 rm s3://acls-example-fun-234/hello.txt
aws s3 rb s3://acls-example-fun-234
```