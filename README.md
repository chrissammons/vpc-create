### Create an AWS VPC

This Python script creates a two or three availability-zone VPC in the AWS region of choice.

**Requirements:**

* Tested w/ python version 2.7 / boto version 2.38
* Valid AWS API keys
* The netaddr library: https://pythonhosted.org/netaddr

**Usage:**

```
build-vpc.py
```

**Arguments:**

1. Number of availability-zones (AZs) [ 2 or 3 ]
2. Region [ Any valid AWS region ]
3. KeyId [ AWS key.id ]
4. SecretId [ AWS secret_key.id ]
5. VPC CIDR size [ /25, /24, /23, /22 ]
6. Owner (for tagging) [ eng, cloudops, etc ]
7. Env (for tagging) [ dev, stage, prod, etc ]

**Output:**

Using the VPC CIDR: 10.64.0.0/23 in 3 AZs

```
./build-vpc.py
vpc-id:  vpc-d94d63bc      name:  eng-dev-vpc-uw2
sub-id:  subnet-fade8f8d   size:  10.64.0.0/27    zone:  us-west-2a
sub-id:  subnet-989caffd   size:  10.64.0.32/27   zone:  us-west-2b
sub-id:  subnet-9b6c04c2   size:  10.64.0.64/27   zone:  us-west-2c
sub-id:  subnet-e5de8f92   size:  10.64.0.128/25  zone:  us-west-2a
sub-id:  subnet-9b9caffe   size:  10.64.1.0/25    zone:  us-west-2b
sub-id:  subnet-9d6c04c4   size:  10.64.1.128/25  zone:  us-west-2c
```

**To Do:**

- [ ] Expand subnet options.
