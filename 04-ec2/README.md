# Ubuntu EC2 (Free Tier)

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
aws ec2 run-instances --image-id ami-02b8269d5e85954ef --instance-type t3.micro --key-name cloudshell-key --security-groups cloudshell-sg --count 1
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

## Delete Security Group
```bash
aws ec2 delete-security-group --group-name cloudshell-sg
```
