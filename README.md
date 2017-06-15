# Private Drop

<p>Python script and Ansible playbooks used to watch for changes in a directory. When there are changes the files will be backed up to an S3 bucket.</p>

### Requirements
* Python 2.7
* Ansible 2.3
* Watchdog
* A Private Key PEM file with access to an S3 bucket
* AWS Access Key ID
* AWS Secret Access Key

### How To Install
<p>In the root of the directory you wish to keep backed up, run the following:</p>

`git clone https://github.com/mcred/private-drop ./.ansible/`

### How To Set Up
<p>Ansible assumes that your host has CLI access to AWS configured. This script will help set that up, but you will need two files: the PEM file that was used to create the EC2 host and a configuration file that contains the following:</p>

```
export AWS_ACCESS_KEY_ID='INSERT YOUR ACCESS KEY'
export AWS_SECRET_ACCESS_KEY='INSERT YOUR SECRET KEY'
export EC2_REGION='INSERT YOUR REGION'
```

### How To Use
<p>Copy your configuration files into place:</p>

```
cp ~/.ssh/YOURKEYFILE.pem ./ansible/inventory/ansible-s3.pem
cp ~/.ssh/YOURAWSKEYS ./ansible/inventory/aws_keys
```
<p>Once your configuration is in place, simply run `cd .ansible/ && ./privatebox ../`</p>
