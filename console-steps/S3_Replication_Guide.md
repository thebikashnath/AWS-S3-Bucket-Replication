# Step-by-Step AWS Console Guide: S3 Replication

This guide details the manual process for configuring S3 Replication between two buckets within the AWS Management Console.

## Prerequisites

* An active **AWS Account**.
* **Permissions** to create S3 buckets, enable versioning, and create IAM roles/policies.

## Step 1: Create the S3 Buckets

1.  Log into the **AWS Management Console** and navigate to the **S3 Service**.
2.  Click **Create bucket**.
3.  **Bucket 1 (Source):**
    * **Bucket Name:** Choose a unique, descriptive name (e.g., `source-data-bucket-prod`).
    * **Region:** Select your primary region.
    * Click **Create bucket**.
4.  **Bucket 2 (Destination):**
    * Repeat the process.
    * **Bucket Name:** Choose a unique name (e.g., `destination-data-bucket-dr`).
    * **Region:** Select your desired region (usually different from the Source for **Cross-Region Replication**).
    * Click **Create bucket**.

## Step 2: Enable Bucket Versioning (Crucial Step)

Versioning must be enabled on both buckets before replication can be configured.

1.  Go to the list of **Buckets**.
2.  Click on **Bucket 1 (Source)**, then go to the **Properties** tab.
3.  Find **Bucket Versioning** and click **Edit**.
4.  Select **Enable** and click **Save changes**.
5.  Repeat this exact process for **Bucket 2 (Destination)**.

## Step 3: Create the Replication Rule

1.  Go back to the **Source Bucket** (Bucket 1).
2.  Navigate to the **Management** tab.
3.  Under the Replication rules section, click **Create replication rule**.
4.  **Replication rule name:** Give it a clear name (e.g., `crr-rule-to-dr-bucket`).
5.  **Source:** Choose **Apply to all objects in the bucket**.
6.  **Destination:**
    * Select **Choose a bucket in this account**.
    * Click **Browse S3** and select your **Bucket 2 (Destination)**.
7.  **IAM Role:**
    * Select **Create new role**. AWS will automatically generate a role with the necessary permissions (`s3:ReplicateObject`, etc.).
8.  Leave other settings (Encryption, Storage Class) as default for a basic setup.
9.  Click **Save** and then **Submit** to activate the rule.

## Step 4: Test Replication

1.  Go to the **Source Bucket**.
2.  Go to the **Objects** tab and click **Upload**.
3.  Upload any test file.
4.  Wait a short period (typically seconds to minutes).
5.  Go to the **Destination Bucket**. The file should now appear in the **Objects** tab, confirming successful replication!
