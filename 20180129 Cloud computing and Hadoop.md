# Cloud Computing

# Server
collection of resources. 

Racks:

[  Top of rack ]
[              ]
[              ]
[              ]
[              ]
[    run VMs   ]
[Shared storage]

Racks in sites (availability zone) - 1 data warehouse

Singapore has 3 availability zone (1a, 1b, 1c) = 1 region (ap - Southeast - 1)

# fundamental services
1. Elastic Computing Cloud [EC2]
renting VMs (usu linux)
build using amazon machine image [AMI]

2. AMI >> (immutable infrastructure) 

base os, pre req, application (layered in an auto mated way) AMI is patched: automated layering

From AMI launch an instance
differs:
- price (spot price - like market exchange / spot )
- performance

3. Elastic Block Storage (EBS) - resilient hard drive:
- performance (SSD, magnetic)
- type 

Instance : EC2 + EBS

type: t2.micro (general instance, shared VM, free)

4. Simple storage service (S3)
static assets
https://s3.amazonaws.com/ (Bucket) / object name blah blah
metadata + payload]

5. CloudFront
Differrent country, every one has Point of Presence (POP)

6. Elastic Load Balancer (ELB)
green blue deployment

# Generating keys and logging in with keys

1. Open puttygen
2. import, .pem
3. Save private key . ppk
4. Open putty
5. configure etc
6. In putty:
Host name (Public IP address)
SSH>> Auth >> open key

# connecting to ec2 using putty and puttygen

Q1 login as ec2-user in terminal
Q2 $ sudo yum update -y