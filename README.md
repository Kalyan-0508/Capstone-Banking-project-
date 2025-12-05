# Capstone-Banking-project- DAY1
Day 1 Concepts 
--------------------------------------------------
This document contains all Day-1 concepts of the Banking Data Platform project.
1. Storage Account Creation
Storage Account is created to store raw ATM, UPI, and customer data files. It acts as the
landing zone for all uploads. Supports Event Grid triggers to initiate ingestion workflows.
2. Creating Multiple Containers
Containers organize data into ATM, UPI, customer, and transaction folders. Maintains clean
separation of various banking data. Each container is monitored for file uploads through Event
Grid.
3. Event Grid Configuration
Event Grid listens for new blob-created events in the storage account. Automatically notifies
the ingestion function when a file is uploaded. Enables real-time and serverless event-driven
data ingestion.
4. Azure Function App Creation
Function App hosts serverless ingestion logic written in Python. Triggered by Event Grid
whenever new files arrive. Extracts file URL and forwards metadata to queues for processing.
5. Service Bus Namespace Creation
Service Bus Namespace provides enterprise-level messaging for banking workloads. Handles
high-volume ingestion and communication events. Used for sending and receiving processing
messages reliably.
6. Creating Service Bus Queue
Service Bus Queue stores metadata messages like file URLs. Ensures reliable and ordered
delivery of ingestion events. Supports scalable downstream data processing.
7. Creating Storage Queue
Storage Queue offers simple and cost-effective message handling. Stores file metadata
messages for ingestion pipelines. Provides flexibility by supporting alternate queueing
mechanisms.
8. Final Output of Day 1
File uploads now automatically trigger the complete ingestion pipeline. Event Grid activates
the Function App and queues receive metadata.
