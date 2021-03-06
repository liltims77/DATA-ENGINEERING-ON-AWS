#Data pipeline on AWS

Introduction

This is a project that involves building a platform and pipeline on AWS for Data Engineering.

CONTENTS
- [The Data Set](#the-data-set)
- [Used Tools](#used-tools)
- [Pipelines](#pipelines)
- [Stream Processing](#stream-processing)
- [Storing Data Stream](#storing-data-stream)
- [Processing Data Stream](#processing-data-stream)
- [Batch Processing](#batch-processing)
- [Visualizations](#visualizations)


# The Data Set
- an e-commerce data set from kaggle was used for this project because it is nice to work with.
- the main goal is to build a platform and pipelines with the data set 

# Used Tools
- kinesis, S3 storage, DynamoDB, kinesis firehose,  Redshift Data warehouse, power BI, Aws Glue.

# Pipelines
- Data ingestion (API, Lambda,Kinesis)
- Stream To Raw S3 Storage
- Visualization API For DynamoDB
- Stream to Redshift
- Batch processing pipeline

# Stream Processing
Firstly lambda function was created for kinesis and also API gateway using resource and methods, configure the API gateway to Lambda function.

# Storing Data Stream
for storing data stream  Kinesis data stream called API DATA was created, IAM was already generated by Lambda.
Data from kinesis was used to trigger lambda function for DynamoDB.
Lambda writes customer data (customer + invoices), (invoices + stockcode).


# Processing Data Stream
S3 bucket and IAM was created for S3, Lambda function was also created to write kinesis to S3.
Kinesis firehose delivery stream connects to kinesis data streams.
Firehouse writes data into intermediate S3 buckets.
Kinesis firehose copies data into Redshift table.

# Batch Processing
Aws glue was used for batch processing to create a job that writes from S3 to redshift
Glue crawlers was used to creat glue catalog for S3 and redshift

# Test
Postman was used for testing

# Visualizations
Data reset in DynamoDB table invoices.
Client request items for invoiceNo
Lambda triggered by API, queries DynamoDB with InvoiceNO.
PowerBI was also used to visualize the data

# Conclusion
A data set (CSV format) was downloaded from kaggle
a platform was designed for it.
designed a pipeline for it
AWS basics was used (logging, API python)
pipeline was built.  
postman was used for testing
power BI was used to visualized our data.

