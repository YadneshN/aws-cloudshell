# CloudShell Overview
AWS CloudShell is a browser-based command-line environment for interacting with your AWS account, providing pre-configured tools (AWS CLI, Python, etc.) and 1GB of persistent storage per region, eliminating local setup for quick management, scripting, and exploration of AWS resources directly from your browser. It uses your existing console credentials for secure access and is ideal for running commands, uploading/downloading files, and running scripts without installing software. 


## Key Features
- Browser-Based: Accessible from any web browser, no local installation needed.
- Pre-installed Tools: Comes with AWS CLI, Git, Python, Node.js, SAM CLI, and more.
- Pre-Authenticated: Uses your AWS console credentials and IAM permissions automatically.
- Persistent Storage: 1GB of storage in your home directory per region for scripts and files.
- Multi-Tab/Split View: Open multiple shells or split the view for complex tasks.
- File Upload/Download: Easily transfer files to/from your CloudShell environment.
- Free to Use: Included at no extra cost for basic usage. 

## Commands

```bash
pwd
whoami
aws --version
echo $AWS_REGION
aws sts get-caller-identity
aws configure list
```

## Key Learnings
- No credential setup needed
- Uses IAM role from AWS Console
- Region-specific environment
