## Create a bucket

aws s3 mb s3://metadata-example-fun123

## Create a file

echo "Hello Mars!!!" > hello.txt

## Upload the file to S3 bucket with metadata

aws s3api put-object --bucket metadata-example-fun123 --key hello.txt --body hello.txt --metadata Planet=Mars

## Get metadata through head object

aws s3api head-object --bucket metadata-example-fun123 --key hello.txt

## Cleanup

aws s3 rm s3://metadata-example-fun123/hello.txt
aws s3 rb s3://metadata-example-fun123