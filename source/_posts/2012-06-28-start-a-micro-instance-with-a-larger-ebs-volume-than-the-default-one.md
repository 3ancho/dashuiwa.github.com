--- 
layout: post
title: Start a micro instance with a larger EBS volume than the default one
tags: 
---
Start a micro instance with a larger EBS volume than the default one.

ec2-run-instances -k KEY -n 1 -t t1.micro --block-device-mapping /dev/sda1=:10
ami-0ce41865 -r us-east-1d

