## Create a bucket

```sh 
aws s3 mb s3://prefixes-bucket-oi
```


## Create a folder
```sh
aws s3api put-object --bucket="prefixes-bucket-oi" --key="hello/"
```

## Create many folders

