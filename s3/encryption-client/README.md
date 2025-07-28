## Create a bucket

```sh
aws s3 mb s3://encrytion-client-fun-bucket-345
```

## Run our our SDK ruby script

```sh
bundle exec ruby encrypt.rb
```

## Cleanup

```sh
aws s3 rm s3://encrytion-client-fun-bucket-345/hello.txt 
aws s3 rb s3://encrytion-client-fun-bucket-345
```

