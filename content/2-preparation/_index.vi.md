---
title : "Prerequisites"
date: "2024-01-01" 
weight : 2
chapter : false
pre : " <b> 2. </b> "
---


#### 2.1. Verify IAM Permissions
Before starting, ensure your IAM user has the required permissions.

**Required Permissions:**
- `ReadOnlyAccess` (AWS Managed Policy)
- `AWSCloudShellFullAccess`
- `cloudformation:CreateStack`
- `cloudformation:DeleteStack`

**Optional for Cross-Account Operations:**
- `iam:SetSecurityTokenServicePreferences`

#### 2.2. Create IAM Policy (If Needed)
If you need to create a custom policy, use this JSON:

```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": [
                "cloudformation:CreateStack",
                "cloudformation:DeleteStack",
                "cloudshell:*"
            ],
            "Resource": "*"
        }
    ]
}
```
#### 2.3. Launch AWS CloudShell
- Log into your AWS Console
- Navigate to CloudShell service (search for "CloudShell" in the services menu)
- Launch CloudShell in your preferred region
- Wait for the environment to initialize
{{%expand "AWS CloudShell" %}}![console](/images/3/1.png){{% /expand%}}

#### 2.4. Install Service Screener v2
Run the following commands in CloudShell:
```bash
# Navigate to temporary directory
cd /tmp

# Create and activate Python virtual environment
python3 -m venv screener-env
source screener-env/bin/activate

# Upgrade pip
python3 -m pip install --upgrade pip

# Clean up any existing installation
rm -rf service-screener-v2

# Clone the repository
git clone https://github.com/aws-samples/service-screener-v2.git

# Navigate to the project directory
cd service-screener-v2

# Install dependencies
pip install -r requirements.txt

# Prepare Lambda runtime dependencies
python3 unzip_botocore_lambda_runtime.py

# Create alias for easy execution
alias screener='python3 $(pwd)/main.py'
```
{{%expand "Install Service Screener V2" %}}![Install Service Screener V2](/images/3/2.png){{% /expand%}}

---
