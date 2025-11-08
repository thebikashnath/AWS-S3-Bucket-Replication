# AWS S3 Bucket Replication Policy Setup 

This repository provides the complete, step-by-step instructions to configure **Amazon S3 Replication** between two buckets using the AWS Management Console.

This setup ensures high data durability by automatically copying objects from a **Source** bucket to a **Destination** bucket, which is essential for backups, disaster recovery, and meeting compliance requirements.

## Project Goal

The guide covers the entire manual process:
1.  Creating two S3 Buckets (Source and Destination).
2.  Enabling **Versioning** on both buckets (a mandatory step for replication).
3.  Creating the necessary **IAM Role** to grant S3 permissions for data transfer.
4.  Configuring and activating the **Replication Rule** on the Source bucket.

## 🎥 Video Tutorial

Watch the full, hands-on tutorial to see this configuration in action:
[Create Two S3 Buckets & Setup Replication Policy | AWS S3 Bucket Replication](https://youtu.be/CH-u14IZ5xE)

## Getting Started

To follow along, you only need an active AWS account. Proceed to the detailed guide:
➡️ [S3 Replication Guide](console-steps/S3_Replication_Guide.md)
