## Create a Bucket

aws s3 mb s3://metadata-example-oi


echo "Hello Mars!" > hello.txt

## Upload file with metadata

aws s3api put-object --bucket metadata-example-oi --key hello.txt --body hello.txt --metadata Planet=Mars


## Get metadata through head object
aws s3api head-object --bucket metadata-example-oi --key hello.txt
