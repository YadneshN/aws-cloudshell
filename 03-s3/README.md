# Amazon S3 using AWS CLI

## List Buckets
```bash
aws s3 ls
```

## Create Bucket
```bash
aws s3 mb s3://cloudshell-demo-<unique-id>
```

## Upload Files
```bash
echo "Hello CloudShell" > file.txt
aws s3 cp file.txt s3://cloudshell-demo-<unique-id>/
```

## List Files
```bash
aws s3 ls s3://cloudshell-demo-<unique-id>
```

## Delete Files & Bucket
```bash
aws s3 rm s3://cloudshell-demo-<unique-id> --recursive
aws s3 rb s3://cloudshell-demo-<unique-id>
```
