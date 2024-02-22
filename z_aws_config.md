### Create EC2 instance
```
chmod 400 "{name}.pem"

ssh -i "{name}.pem" ubuntu@{chave}.compute-1.amazonaws.com
```

### Structure Bucket S3
The files inside the bucket follow this path pattern: `<bucket>/folder/subfolder/file.csv`

Maximum size file is `5Gbytes`

Object tag's: up to `10 key/value pairs`