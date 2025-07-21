## Create a new s3 bucket
'''md
aws s3 mb s3://checksums-example-bucket-9094
'''

## Create a new file that we will checksum on

'''
echo "Hello World!!!" > myfile.txt
'''

## Get a checksum of a file for md5

'''md
md5sum myfile.txt

'''
## e9ff62a6b64718b317b858edeed42928  myfile.txt

## Upload our file and look at its etags

'''
aws s3 cp myfile.txt s3://checksums-example-bucket-9094
aws s3api head-object --bucket checksums-example-bucket-9094 --key myfile.txt
'''

## Upload a file with a different kind of checksum

'''sh
sudo apt install rhash -y
rhash --crc32 myfile.txt
'''

'''sh
aws s3api put-object \
--bucket="" \
--key="myfilecrc32.txt" \
--body="myfile.txt" \
--checksum-algorithm="CRC32" \
--checksum-crc32=""
'''