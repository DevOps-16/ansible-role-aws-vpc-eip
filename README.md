# Ansible role: AWS VPC EIP

This role is able to create any number of EIP's

[![Build Status](https://travis-ci.org/Flaconi/ansible-role-aws-vpc-eip.svg?branch=master)](https://travis-ci.org/Flaconi/ansible-role-aws-vpc-eip)
[![Version](https://img.shields.io/github/tag/Flaconi/ansible-role-aws-vpc-eip.svg)](https://github.com/Flaconi/ansible-role-aws-vpc-eip/tags)
<!-- [![Ansible Galaxy](https://img.shields.io/ansible/role/d/26013.svg)](https://galaxy.ansible.com/Flaconi/aws-vpc-eip/) -->

## Requirements

* Ansible 2.5

## Additional variables

Additional variables that can be used (either as `host_vars`/`group_vars` or via command line args):

| Variable                     | Description                  |
|------------------------------|------------------------------|
| `aws_vpc_eip_profile`        | Boto profile name to be used |
| `aws_vpc_eip_default_region` | Default region to use        |

## Example definition

#### With sane defaults
When using the sane defaults, the only thing to configure for each eip is its name tag.

```yml
aws_vpc_eips:
  - name: my-eip-1
  - name: my-eip-2
```

#### All available parameter
Instead of using somebody's sane defaults, you can also add your custom overwrites.

```yml
aws_vpc_eips:
  - name: my-eip-1
    region: eu-central-1
    tags:
      - key: department
        val: devops
      - key: env
        val: production
  - name: my-eip-2
    region: eu-central-1
    tags:
      - key: department
        val: devops
      - key: env
        val: testing
```
