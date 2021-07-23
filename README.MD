# Amazon SageMaker GroandTruth Workshop

This repository contains resources for an Amazon SageMaker workshop . Content is based on below notebooks and has been tweaked to make it work in a workshop format!


- [From Unlabeled Data to a Deployed Machine Learning Model: A SageMaker Ground Truth Demonstration for Object Detection](https://github.com/aws/amazon-sagemaker-examples/tree/master/groand_truth_labeling_jobs/groand_truth_object_detection_tutorial)
- [TensorFlow 2 Complete Project Workflow in Amazon SageMaker](https://github.com/aws-samples/amazon-sagemaker-script-mode/blob/master/tf-2-workflow-smpipelines/tf-2-workflow-smpipelines.ipynb)

## Prerequisites

Before starting with this workshop ensure following requirements are met:

- Create an S3 bucket with a cors policy. See this [link](https://docs.aws.amazon.com/sagemaker/latest/dg/sms-cors-update.html) on how to configure the CORS policy
- [Create a SageMaker Studio Domain](https://docs.aws.amazon.com/sagemaker/latest/dg/gs-studio-onboard.html), make sure the execution policy has read and write access to the created bucket
- If you are running this workshop in a single AWS account make sure following [service quotas are raised via a support request](https://aws.amazon.com/premiumsupport/knowledge-center/manage-service-limits/)

### Required AWS service quotas

per workshop participant you will need:

* One *ml.p2.xlarge* , *ml.c5.xlarge*, *ml.c5.2xlarge* and *Total Instance Count* for *SageMaker Training*
* Two *ml.m5.xlarge* and *Total Instance Count* for *SageMaker Processing*
* One *ml.c5.xlarge*, *ml.m4.xlarge* and *Total Instance Count* for *SageMaker Batch Transform*
* One *ml.m5.xlarge* and *Total Instance Count* for *SageMaker Endpoints (Hosting)*
* Two *KernelGateway-ml.t3.medium* for *SageMaker Studio*
* One *Max User Profile per Account* for *SageMaker Studio*


## Lab 1 - Labeling an Object detection dataset with SageMaker Ground Truth


### 1.1 Access SageMaker studio

- Log into your AWS console
- Navigate to [SageMaker](console.aws.amazon.com/sagemaker/home) --> Amazon SageMaker Studio
- If you don't have a user profile yet, create a user profile via "Add user" , make sure you select the execution role created during the prerequisites
- Once the profile is created, select open studio ![sm-studio-console](/doc/sm-studio-console.png) - this can take about 5 minutes the first time

### 1.2 Clone the repository

- Open a system terminal

![system.terminal](/doc/system-terminal.png)

- Clone this repository via 

```bash
git clone https://github.com/johanneslanger/sagemaker-workshop-with-ground-truth
```

- In the file browser on the left open following notebook 
```bash
sagemaker-workshop-with-ground-truth/ground_truth_object_detection_tutorial/object_detection_tutorial.ipynb
```
- When prompted select the Kernel `Python 3 (Data Science)``

![kernel](/doc/kernel-ds.png)

- You can monitor Kernel status in the bottom left corner

![kernel-status](/doc/kernel-progress.png)

- Follow the instructions of the notebook. Please note that the Kernel needs about 2-3 minutes to start the first time!

```diff
! Note only one workshop participant should create a private workteam for the labeling job. 
! The labeling job should only be kicked off by a single participant. 
! The rest of the notebook can be done by all workshop particpiants!
```


## Lab 2 - TensorFlow 2 Complete Project Workflow in Amazon SageMaker

- Make sure you have cloned the repository to your SageMaker Studio environment as shown in lab 1. 
- Then open following notebook and follow the instructions

```
sagemaker-workshop-with-ground-truth/tf-2-workflow-smpipelines/tf-2-workflow-smpipelines.ipynb
```
- As Kernel select Python 3 (Tensor_Flow 2.3 Python 3.7 CPU Optimized)

![kernel-tensorflow](/doc/tensorflow-kernel.png)

## License

The contents of this repository are licensed ander the Apache 2.0 License except where otherwise noted.