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

## License

The contents of this repository are licensed ander the Apache 2.0 License except where otherwise noted.