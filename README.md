# aws_ec2_projects

## Introduction
This repository has a collection of "template.yaml" files to demonstrate how to build different assets in AWS that have to do with the EC2 services.

## Goals
Showcase different ways of creating infrastructure

## Prerequisites
- AWSCLI
    - Installed
    - Configured
- AWS Key Pair(s)


## Project Structure

### cloudformation
This folder contains all the "template.yaml" that can be used to build infrastructure in AWS.

## How to use these templates?
Depending of the file certain commands need to be run in order to deploy the stacks to CloudFormation. Execute the following commands to deploy the assets described in each of the files:

- template_vpc.yaml
    - aws cloudformation create-stack --stack-name vpc-generic --template-body file:///path/template_vpc.yaml --parameters ParameterKey=VpcName,ParameterValue="Generic VPC"
    - aws cloudformation describe-stacks --stack-name vpc-generic
    - aws cloudformation delete-stack --stack-name vpc-generic
- template_ec2.yaml
    - aws cloudformation create-stack --stack-name ec2-generic --template-body file:///path/template_ec2.yaml --parameters ParameterKey=VpcName,ParameterValue="Generic EC2"
    - aws cloudformation describe-stacks --stack-name ec2-generic
    - aws cloudformation delete-stack --stack-name ec2-generic
- template_ec2_ssh_connect.yaml
    - aws ec2 create-key-pair --key-name generic-pair --query 'KeyMaterial' --output text > /somewhere/generic-pair.pem
    - pending