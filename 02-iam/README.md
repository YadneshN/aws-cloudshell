# IAM using AWS CLI

## List Users
```bash
aws iam list-users
```

## Create User
```bash
aws iam create-user --user-name cloudshell-demo-user
```

## List Policies
```bash
aws iam list-policies --scope AWS
```

## Attach Policies
```bash
aws iam attach-user-policy --user-name cloudshell-demo-user --policy-arn arn:aws:iam::aws:policy/AmazonS3FullAccess
aws iam attach-user-policy --user-name cloudshell-demo-user --policy-arn arn:aws:iam::aws:policy/AmazonEC2FullAccess
```

## List Attached Policies
```bash
aws iam list-attached-user-policies --user-name cloudshell-demo-user
```

## Cleanup
```bash
aws iam detach-user-policy --user-name cloudshell-demo-user --policy-arn arn:aws:iam::aws:policy/AmazonS3FullAccess
aws iam detach-user-policy --user-name cloudshell-demo-user --policy-arn arn:aws:iam::aws:policy/AmazonEC2FullAccess
aws iam delete-user --user-name cloudshell-demo-user
```
