Onprem-to-Analytics AWS Pipeline Blog

** Abstract - 
This is a blog about the Onprem-to-Analytics AWS Pipeline, a serverless data processing and analytics pipeline that allows organizations to migrate their on-premises servers to AWS and gain insights into their application's performance. The blog is based on a simple AWS pipeline that includes the following components:

Server ("Onprem Server")
Elastic Load Balancer (ELB)
API Gateway
Lambda
S3
Glue Crawlers
Athena
Analytics (Business Intelligence)


<img width="530" alt="image" src="https://github.com/jithupaulose/DiagramStudy/blob/b8a73c504a98604c5071d216783b08ea196a8632/simple_aws_data_pipeline.png">



Data Engineering – Use Case – Read the file from S3 and Load it in RDS.
Problem Statement -  An organization received source systems data to an input landing. The requirement is to load the data to a relational database system so that BI reports can be developed. The average number of records in the file is 10000.
Solution:  Looking at the problem statement and file size, we are going to develop an event driven architecture to load the data. The solution steps.
# Data Engineering – Use Case – Read the file from S3 and Load it in RDS.

** Abstract -  
An organization received source systems data to an input landing. The requirement is to load the data to a relational database system so that BI reports can be developed. The average number of records in the file is 10000.

** Solution - 
Looking at the problem statement and file size, we are going to develop an event driven architecture to load the data. The solution steps.
1.	The input files are placed in S3 bucket.
2.	An event is triggered, which in turn 
3.	The lambda function extracts the file details from event context and load the data in RDS.
We are going to follow below solution architecture to solve this problem.


<img width="591" alt="image" src="https://user-images.githubusercontent.com/24868114/222958135-a2e4c7b6-ed1e-498d-b3eb-7b743e56e45e.png">

Let’s start’s the e2e action on this.
Step -1: Create a bucket called aws-data-engineering-lab-001 for our data engineering project.

<img width="530" alt="image" src="https://user-images.githubusercontent.com/24868114/222958176-91156817-8661-4702-a471-dce032da94d4.png">

Step -2: Create a folder called input where we will store the input files.

<img width="499" alt="image" src="https://user-images.githubusercontent.com/24868114/222958199-beaca93f-7886-4a51-9619-02b3a5d4957a.png">

Step -3:  For this demo, we created a demo file which is having 2 fields ( roll_no, name). The sample record of the file is 

<img width="182" alt="image" src="https://user-images.githubusercontent.com/24868114/222958215-a8d266c1-22b9-421b-a2e7-a7c4bdf684f3.png">
