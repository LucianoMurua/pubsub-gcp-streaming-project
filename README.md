# pubsub-gcp-streaming-project
Demo project using Pub/Sub and Dataflow on Google Cloud Platform

# step by step

1) bigquery_create_table.sql: This script runs directly in BigQuery to create the target table.
2) irctc_mock_data_to_pubsub.py: Python function named "generate_mock_data" defines a dictionary with random messages. Next, "publish_to_pubsub" function publishes data to Pub/Sub.
3) transform_udf.py: 
