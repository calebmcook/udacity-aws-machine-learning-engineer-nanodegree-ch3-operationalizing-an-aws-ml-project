# udacity-aws-machine-learning-engineer-nanodegree-ch3-operationalizing-an-aws-ml-project
udacity-aws-machine-learning-engineer-nanodegree-ch3-operationalizing-an-aws-ml-project

# Initial setup, training and deployment
## Initial Setup and Justification
I chose an ml.t3.xlarge, because I encountered a memory insufficiency error using ml.t3.medium (to save costs). Per docs https://docs.aws.amazon.com/sagemaker/latest/dg/howitworks-create-ws.html, if more memory is needed, recommend large or xlarge.

![sm-notebook-instance.png](sm-notebook-instance.png)

After you set up an S3 bucket, take a screenshot showing that you've set up an S3 bucket. Include this screenshot in your final submission.
## Screenshot of S3 bucket
![s3-bucket.png](s3-bucket.png)

# Training and Deployment
## Screenshot of deployed endpoint in Inference > Endpoints
![deployed-endpoint.png](deployed-endpoint.png)

# EC2 Training
For EC2 Training I decided to choose something relatively low cost, but with more memory than the base tier - t2.xlarge (4 vCPUs and 16 Gib memory) This is to strike a balance between cost and performance.