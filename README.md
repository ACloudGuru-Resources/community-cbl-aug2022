# Cloud Builder Live - August 2022

![Cloud Builder Live Thumbnail](/images/thumbnail.jpg)

In this session, David will deploy a container-based microservice to AWS using the Elastic Kubernetes Service (EKS). David will walk through cluster deployment, node group deployment, pod deployment, and ultimately exposing a service that can be accessed.

Watch it Live - [Cloud Builder Live - August 2022](https://www.youtube.com/watch?v=Pcj1RCB9ny8)  

## Warning

**It is important to note that you could incur substantial AWS charges if you do not delete the resources configured in this episode.** At the end of the episode I will cover the delete process in detail, but if you have followed along with the demo, you can run the following command:

```
eksctl delete cluster --name cbl-cluster --region us-east-2
```

I recommend that anytime you are using your own account to test out AWS services that you setup a billing alarm.  You can follow the video below for more information on how to set this up.

[How to set up an AWS billing and budget alarm - ACG](https://www.youtube.com/watch?v=2XilJFirnWY)

## Prerequisites

To follow along with this demo, you will need two things: an AWS account and the AWS CLI.  You can get instructions on how to get these setup at the following links:

* [Create an AWS Account](https://aws.amazon.com/premiumsupport/knowledge-center/create-and-activate-aws-account/)
* [Install the AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html)

## Tools to Install

During the episode, I'll be walking you through some tools we will be using to deploy, monitor, and configure Kubernetes (k8s) via the Elastic Kubernetes Service (EKS).  I've listed them below along with the purpose for including them:

| Tool | Installation Instructions | Use |
|-----|-----|-----|
| **eksctl** | [Install eksctl](https://docs.aws.amazon.com/eks/latest/userguide/eksctl.html) | This command line tool greatly simplifies the creating and management of k8s clusters and node groups on AWS with EKS. *This tool requires the AWS CLI.*  |
| **kubectl** | [Install kubectl](https://docs.aws.amazon.com/eks/latest/userguide/install-kubectl.html) | The official k8s command line tool for interacting with the cluster API's. *This tool requires a proper config file referencing the cluster you will be working on.* |
| **k9s** | [Install k9s](https://k9scli.io/topics/install/) | Terminal based tool for the monitoring and management of a k8s cluster. *This tool requires kubectl to be installed.*<br><br>[Video Overview of k9s](https://www.youtube.com/watch?v=jovHiTobzKQ)|

## What We Will Deploy

This episode will use a sample container-based HTTP API (built on Node.js and Express).  The microservice exposes COVID-19 data collected from *Our World in Data*.  For more information around the API or the data, you can check out the link below:

[COVID Data API](https://github.com/davidtucker/covid-data-api-demo)