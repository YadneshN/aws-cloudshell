# Amazon EC2 (Free Tier)

## Find Amazon Linux 2 AMI
```bash
aws ec2 describe-images --owners amazon --filters "Name=name,Values=amzn2-ami-hvm-*-x86_64-gp2" --query "Images[*].[ImageId,CreationDate]" --output table
```

## Create Key Pair
```bash
aws ec2 create-key-pair --key-name cloudshell-key --query 'KeyMaterial' --output text > cloudshell-key.pem
chmod 400 cloudshell-key.pem
```

## Create Security Group
```bash
aws ec2 create-security-group --group-name cloudshell-sg --description "CloudShell demo SG"
aws ec2 authorize-security-group-ingress --group-name cloudshell-sg --protocol tcp --port 22 --cidr 0.0.0.0/0
```

## Launch Instance
```bash
aws ec2 run-instances --image-id ami-xxxxxxxx --instance-type t2.micro --key-name cloudshell-key --security-groups cloudshell-sg --count 1
```

## List Instances
```bash
aws ec2 describe-instances --query 'Reservations[*].Instances[*].[InstanceId,State.Name,InstanceType]' --output table
```

## Stop / Start / Terminate
```bash
aws ec2 stop-instances --instance-ids i-xxxxxxxx
aws ec2 start-instances --instance-ids i-xxxxxxxx
aws ec2 terminate-instances --instance-ids i-xxxxxxxx
```
