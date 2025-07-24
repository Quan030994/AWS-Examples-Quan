# Create Website 1

## Create a bucket

```sh
aws s3 mb s3://cors-fun-ab-9988
```

## Change Block public access

```sh
aws s3api put-public-access-block \
--bucket cors-fun-ab-9988 \
--public-access-block-configuration "BlockPublicAcls=true,IgnorePublicAcls=true,BlockPublicPolicy=false,RestrictPublicBuckets=false"
```

## Create a Bucket Policy

```sh
aws s3api put-bucket-policy --bucket cors-fun-ab-9988 --policy file://bucket-policy.json
```

## Turn on static website hosting

```sh
aws s3api put-bucket-website --bucket cors-fun-ab-9988 --website-configuration file://website.json
```

## Upload our index.html file and include a resource that would be cross-origin

```sh
aws s3 cp index.html s3://cors-fun-ab-9988
```
## View the website and see if the index.html is there.

```
http://cors-fun-ab-9988.s3-website-ap-southeast-1.amazonaws.com
```

# Create Website 2

## Create a bucket

```sh
aws s3 mb s3://cors-fun2-ab-9988
```

## Change Block public access

```sh
aws s3api put-public-access-block \
--bucket cors-fun2-ab-9988 \
--public-access-block-configuration "BlockPublicAcls=true,IgnorePublicAcls=true,BlockPublicPolicy=false,RestrictPublicBuckets=false"
```

## Create a Bucket Policy

```sh
aws s3api put-bucket-policy --bucket cors-fun2-ab-9988 --policy file://bucket-policy2.json
```

## Turn on static website hosting

```sh
aws s3api put-bucket-website --bucket cors-fun2-ab-9988 --website-configuration file://website.json
```

## Upload our javascript file

```sh
aws s3 cp hello.js s3://cors-fun2-ab-9988
```
## Create API Gateway with mock response and then test the endpoint.

```
curl -X POST -H "Content-Type: application/json" https://01p854hrz9.execute-api.ap-southeast-1.amazonaws.com/prod/hello
```

##

```sh
aws s3api put-bucket-cors --bucket cors-fun-ab-9988 --cors-configuration file://cors.json
```

