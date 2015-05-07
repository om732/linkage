Linkage
====

## Overview
ELBとEC2インスタンスを紐付けるスクリプト
紐付ける条件はタグによって判断する

## Description
ELBとEC2インスタンスに設定されているState、Role、Envタグを元にELBとEC2インスタンスを紐付けます

### Tag setting example
- EC2
    - Env
        - dev
    - Role
        - node
    - State
        - running
- ELB
    - Env
        - dev
    - Role
        - node
    - State
        - running


## Requirement
- python 2.7~
- boto3

## Install
```
$ git clone https://github.com/om732/linkage.git
```

## Setup

~/.aws/credentials

```
[default]
aws_access_key_id = YOUR_ACCESS_KEY
aws_secret_access_key = YOUR_SECRET_KEY
region = ap-northeast-1
```

## Usage
### options
```
-a --aws_access_key KEY           (default: ~/.aws/credentials or ~/.boto or /etc/boto.cfg)
-s --aws_secret_key KEY           (default: ~/.aws/credentials or ~/.boto or /etc/boto.cfg)
-r --region REGION_NAME           (default: all region)
-c --credentials CREDENTIALS_FILE (default: ~/.aws/credentials or ~/.boto or /etc/boto.cfg)
-p --profile PROFILE_NAME         (default: default)
-n --name ROLE_NAME               (default: None, requirement)
-e --env  ENV_NAME                (default: None, requirement)
-v --verbose                      (default: False)
   --dry-run                      (default: false)
```

### run
run to dev

```
% linkage -n node -e dev
```

check

```
% linkage -n node -e dev --dry-run
```

verbose

```
% linkage -n node -e dev -v
```

## Licence

[MIT](https://github.com/tcnksm/tool/blob/master/LICENCE)

## Author

[og732](https://github.com/om732)
