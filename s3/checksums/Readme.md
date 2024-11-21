## Create a new s3 bucket

```md 
aws s3 mb s3://checksums-examples-oi
```

## Create a file that we will checksum on

```
echo "Hello Mars" > myfile.txt

```

## Get the checksum of a file for md5

``` md
md5sum myfile.txt
#  8ed2d86f12620cdba4c976ff6651637f  myfile.txt
```
## Upload a file to s3 bucket

```
aws s3 cp myfile.txt s3://checksums-examples-oi
aws s3api head-object --bucket checksums-examples-oi --key myfile.txt
```

## Lets upload a file with a different kind of checksum

```sh
sudo apt install rhash -y
rhash --crc32 --simple myfile.txt
```

```sh
aws s3api put-object \
--bucket checksums-examples-oi \
--key myfilesha1.txt \
--body myfile.txt \
--checksum-algorithm="SHA1"

```