## Install AWS CLI:

```bash
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"

unzip awscliv2.zip

sudo ./aws/install
```


```bash
aws --version

aws-cli/2.36.29 Python/3.14.6 Linux/6.8.0-138-generic exe/x86_64.ubuntu.24
```


### Method A: Configure AWS CLI (Recommended) 

The terminal will prompt you to enter the following information one by one:
- AWS Access Key ID: Paste your downloaded Access Key ID.
- AWS Secret Access Key: Paste your downloaded Secret Access Key.
- Default region name: Enter your primary AWS region (e.g., `us-east-1` or `eu-west-1`).
- Default output format: Enter your preferred format (e.g., `json`, `yaml`, or `text`).


_Configure:_
```bash
aws configure


AWS Access Key ID [None]: 
AWS Secret Access Key [None]: 
Default region name [None]: us-east-1
Default output format [None]: json
```


```bash
aws configure list

NAME       : VALUE                    : TYPE             : LOCATION
profile    : <not set>                : None             : None
access_key : ****************STGL     : shared-credentials-file :
secret_key : ****************0HNo     : shared-credentials-file :
region     : us-east-1                : config-file      : ~/.aws/config
```


_Verify:_
```bash
aws iam list-users

aws iam list-groups

aws s3 ls

aws ec2 describe-availability-zones
```



_Or, Configure Custom profile:_
```bash
aws configure --profile aws_dev

```


```bash 
aws sts get-caller-identity --profile aws_dev
```





### Method B: Setting Environment Variables (Temporary Setup)

If you only need the credentials for a single terminal session, you can `export` them directly into your environment:

```bash
## Linux / macOS: 
export AWS_ACCESS_KEY_ID=your_access_key_id
export AWS_SECRET_ACCESS_KEY=your_secret_access_key
export AWS_DEFAULT_REGION=us-east-1
```



```bash
aws configure list
```









---
---



## Install `eksctl` CLI:



### For Unix:

```bash
ARCH=amd64
PLATFORM=$(uname -s)_$ARCH
echo $PLATFORM


curl -sLO "https://github.com/eksctl-io/eksctl/releases/latest/download/eksctl_$PLATFORM.tar.gz"

# (Optional) Verify checksum
curl -sL "https://github.com/eksctl-io/eksctl/releases/latest/download/eksctl_checksums.txt" | grep $PLATFORM | sha256sum --check

tar -xzf eksctl_$PLATFORM.tar.gz -C /tmp

sudo mv /tmp/eksctl /usr/local/bin
```



```bash 
eksctl version

0.230.0
```


```bash
eksctl -h
```




### Shell Completion:

_To enable bash completion, run the following, or put it in `~/.bashrc` or `~/.profile`:_
```bash
. <(eksctl completion bash)
```




---
---




## Install `kubectl` CLI:


```bash
-- Kubernetes 1.36:
curl -O https://s3.us-west-2.amazonaws.com/amazon-eks/1.36.2/2026-07-05/bin/linux/amd64/kubectl


-- Kubernetes 1.35:
curl -O https://s3.us-west-2.amazonaws.com/amazon-eks/1.35.6/2026-07-05/bin/linux/amd64/kubectl


-- Kubernetes 1.34:
curl -O https://s3.us-west-2.amazonaws.com/amazon-eks/1.34.9/2026-07-05/bin/linux/amd64/kubectl


chmod +x ./kubectl

sudo mv ./kubectl /usr/local/bin
```


```bash
kubectl version --client
```







---
---

### Ref:
- [github.com/eksctl-io](https://github.com/eksctl-io/eksctl/releases/)
- [Installation eksctl](https://docs.aws.amazon.com/eks/latest/eksctl/installation.html)
- [Installation kubectl](https://docs.aws.amazon.com/eks/latest/userguide/install-kubectl.html)

