# 📊 WordFreq – Scalable Text Processing System on AWS

> ⚡ A production-ready, auto-scaling text analytics platform using AWS services to process large-scale file uploads and extract top word frequencies.

---

## 🌐 Overview

**WordFreq** is a cloud-native, event-driven system that processes user-uploaded text files to compute the top 10 most frequent words. It uses Amazon S3 for file storage, SQS for task queuing, EC2 for scalable compute, and DynamoDB for result persistence. The system is designed for real-world production environments with observability, scalability, and fault tolerance.

---

## 🪄 Key Features

- 🔁 **Serverless Ingestion via S3**  
  Seamless user upload triggers processing without manual intervention.

- 📬 **Queue-Driven Architecture**  
  SQS queues decouple processing jobs and results, enabling fault tolerance and modular scaling.

- 📈 **Auto Scaling Based on Load**  
  EC2 worker fleet scales dynamically in/out based on message volume in job queue (CloudWatch-based).

- ⚙️ **Stateless, Distributed Workers**  
  Worker nodes are stateless Go services designed for high availability and parallel file processing.

- 🧠 **Top 10 Word Frequency Analysis**  
  Efficient algorithm to identify most common words across text files, storing structured output in DynamoDB.

- 🗂️ **Result Persistence**  
  All processed results are persisted with job IDs, word counts, and timestamps for future retrieval and monitoring.

- 📊 **Performance Benchmarked**  
  Load tested across multiple instance types with metrics collected for performance tuning.

- 🔒 **IAM-Secured Architecture**  
  Fine-grained access control via IAM roles scoped to specific AWS services only.

- 🧪 **Replay-Friendly Design**  
  Jobs remain in queue until explicitly completed, ensuring no lost processing on worker failure.

---

## 💡 Use Cases

- MVP for real-time data ingestion pipelines  
- Benchmarking EC2 instance performance and auto-scaling policies  
- Cloud engineering demo for queue-first, stateless distributed architectures  

---

## 🏗️ AWS Services Utilized

| Service         | Description                                                  |
|-----------------|--------------------------------------------------------------|
| **Amazon S3**    | Storage for uploaded and processed files                    |
| **Amazon SQS**   | Messaging queue for job distribution and status signaling   |
| **Amazon EC2**   | Hosts worker nodes (written in Go)                          |
| **Auto Scaling** | Dynamically provisions compute based on workload            |
| **CloudWatch**   | Monitors queue size, triggers scaling policies              |
| **DynamoDB**     | Stores top 10 word frequencies per job                      |
| **IAM**          | Role-based access management for AWS service interactions   |
