# Streaming project in GCP
This demo project uses Pub/Sub and Dataflow to stream data in real-time to BigQuery.

## Diagram
![pubsub_gcp_diagram drawio](https://github.com/user-attachments/assets/b1bd5ef9-1fbb-44e3-8c4a-75a77482a246)


## How it works

The order of execution of the scripts found in the repository and a brief description of each one is explained step by step below.
First, clone this repository using Cloud Shell with the following command: git clone https://github.com/LucianoMurua/pubsub-gcp-streaming-project. Then, follow the next steps:

1) bigquery_create_table.sql: This script runs directly in BigQuery to create the target table.
2) irctc_mock_data_to_pubsub.py: Python function named "generate_mock_data" defines a dictionary with random messages. Next, "publish_to_pubsub" function publishes data to Pub/Sub.
3) transform_udf.py: In this script the cleaning and validation of the data is carried out.
