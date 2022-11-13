# udacity-aws-machine-learning-engineer-nanodegree-ch3-operationalizing-an-aws-ml-project
udacity-aws-machine-learning-engineer-nanodegree-ch3-operationalizing-an-aws-ml-project

# Initial setup, training and deployment
## Initial Setup
First, find and download your starter files, which are located in the Resources section for this project lesson. The starter file called train_and_deploy-solution.ipynb is a Jupyter notebook that trains and deploys a computer vision model. The starter file called hpo.py is the "entry point" for the train_and_deploy-solution.ipynb notebook. You can upload both of these files to a Sagemaker instance and run them there, using Jupyter or JupyterLab.

Before you run these files, you'll have to create and open a Sagemaker instance. Decide which type of Sagemaker instance you should create for your training and deployment. Consider the cost, computing power, and speed of launching for each instance type. Write a short justification of why you chose the instance type you did. After you launch your Sagemaker instance, take a screenshot of your Sagemaker dashboard's Notebooks > Instances section to show what you've done.

Note: For this project, you should perform all of the Sagemaker steps using Sagemaker itself, not Sagemaker Studio.
Sagemaker Dashboard screenshots

## Justification
I chose an ml.t3.xlarge, because I encountered a memory insufficiency error using ml.t3.medium (to save costs). Per docs https://docs.aws.amazon.com/sagemaker/latest/dg/howitworks-create-ws.html, if more memory is needed, recommend large or xlarge.

![sm-notebook-instance.png](sm-notebook-instance.png)

# Download data to an S3 bucket
The first three cells of the train_and_deploy-solution.ipynb will download data to your AWS workspace. The third cell copies the data to an S3 bucket. You need to set up an S3 bucket that you can copy the data to.

After you set up an S3 bucket, take a screenshot showing that you've set up an S3 bucket. Include this screenshot in your final submission.
## Screenshot of S3 bucket
![s3-bucket.png](s3-bucket.png)

After setting up an S3 bucket, you need to change some cells in the train_and_deploy-solution.ipynb notebook. In particular, the third cell, eighth cell, and sixteenth cell contain references to an S3 bucket called s3://udacitysolution/. You need to find all references to this bucket name and change them so they refer to the name of the S3 bucket that you created.

After changing all of these references, you will be prepared to run the first three cells of your train_and_deploy-solution.ipynb notebook. Run these cells to download training and validation data for the project's ML pipeline.

# Training and Deployment
After downloading your data to S3, you're ready to perform training and deployment. You can accomplish this by running the remaining cells in the train_and_deploy-solution.ipynb notebook. Start by running all of the cells from the fourth to the sixteenth cell. The sixteenth cell is the final cell in the section called "Creating an Estimator." The sixteenth cell will fit an estimator. You will have to wait some time for the estimator to complete the fitting process - it usually takes about 20 minutes for this process to complete. You can check the progress of this process by navigating to the "Training > Training Jobs" section of Sagemaker. While the fitting process is in progress, you will see a job listed here whose status is listed as "InProgress." After it completes, the status should be listed as "Completed."

After the estimator fitting process completes, you can run the remaining cells in the train_and_deploy-solution.ipynb notebook. This will deploy an endpoint to your Sagemaker account. You should navigate to the "Inference > Endpoints" section of Sagemaker so you can see the name of your deployed endpoint. You should make a note of the name of the deployed endpoint, because you will need to use a deployed endpoint later in the project. You should also take a screenshot showing the "Inference > Endpoints" section of SageMaker. This screenshot should show that you've deployed an endpoint. You should submit this screenshot in your final submission.

## Screenshot of deployed endpoint in Inference > Endpoints
![deployed-endpoint.png](deployed-endpoint.png)

Note: Deployed endpoints generate AWS charges. If you need to take a long break from working on your project, you may wish to delete your deployed endpoint, then re-deploy it later, to avoid generating excessive charges.
