# Data Streaming Project in GCP
This demo project uses Pub/Sub and Dataflow to stream data in real-time to BigQuery.

## Architecture
![pubsub_gcp_diagram drawio](https://github.com/user-attachments/assets/b1bd5ef9-1fbb-44e3-8c4a-75a77482a246)

## Technology used

### Programming Language
- Python
- SQL

### Google Cloud Platform
- Cloud Shell
- Pub/Sub
- Dataflow
- BigQuery

## How it works

The order of execution of the scripts found in the repository and a brief description of each one is explained step by step below.
First, clone this repository using Cloud Shell with the following command: git clone https://github.com/LucianoMurua/pubsub-gcp-streaming-project. Then, follow the next steps:

1) bigquery_create_table.sql: This script runs directly in BigQuery to create the target table.
2) irctc_mock_data_to_pubsub.py: Python function named "generate_mock_data" defines a dictionary with random messages. Next, "publish_to_pubsub" function publishes data to Pub/Sub.
3) transform_udf.py: In this script the cleaning and validation of the data is carried out.

## How it looks

### Cloud Shell
irctc_mock_data_to_pubsub.py script (publisher) runs in Cloud Shell:
![image](https://github.com/user-attachments/assets/733e8db3-9d89-48a0-864d-d1faf7be688e)

### Pub/Sub
Messages generated in previous step are published to a Pub/Sub topic named irctc-data, and then pull the mentioned messages from irctc-data-sub subscription:
![image](https://github.com/user-attachments/assets/b7150765-4ecc-4dbd-bc9d-391ae5a80d92)

### Cloud Storage
Transformation script that uses Dataflow in next step:
![image](https://github.com/user-attachments/assets/86813fc3-8b5c-4139-b610-a6222dba13a2)


### Dataflow
An overview of the irctc-pubsub-to-bigquery-dev job. This was created from the Dataflow template named "Pub/Sub to BigQuery with Python UDFs"
![image](https://github.com/user-attachments/assets/3765aa93-83cf-49d0-af19-691a94087ee1)

#### BigQuery


