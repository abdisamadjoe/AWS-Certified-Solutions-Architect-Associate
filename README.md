# AWS Certified Solutions Architect - Associate (SAA-C03)

## Table of Contents
- [Introduction](#introduction)
- [Target Candidate Description](#target-candidate-description)
- [Exam Content](#exam-content)
  - [Exam Duration](#exam-duration)
  - [Response Types](#response-types)
  - [Unscored Content](#unscored-content)
- [Exam Results](#exam-results)
- [Content Outline](#content-outline)
- [Introduction to S3](#introduction-to-s3)
  - [What is Object Storage (Object-based Storage)?](#what-is-object-storage-object-based-storage)
  - [S3 Object](#s3-object)
  - [S3 Bucket](#s3-bucket)
- [S3 Bucket Overview](#s3-bucket-overview)
- [S3 Bucket Naming Rules](#s3-bucket-naming-rules)
- [S3 Bucket Restrictions and Limitations](#s3-bucket-restrictions-and-limitations)
- [S3 Bucket Types](#s3-bucket-types)
  - [General Purpose Buckets](#general-purpose-buckets)
  - [Directory Buckets](#directory-buckets)
- [S3 Bucket Folders](#s3-bucket-folders)
- [S3 Object Overview](#s3-object-overview)

## Introduction
The AWS Certified Solutions Architect - Associate (SAA-C03) exam is intended for individuals who perform in a solutions architect role. The exam validates a candidate’s ability to use AWS technologies to design solutions based on the AWS Well-Architected Framework.

The exam also validates a candidate’s ability to complete the following tasks:
* Design solutions that incorporate AWS services to meet current business requirements and future projected needs
* Design architectures that are secure, resilient, high-performing, and cost-optimized
* Review existing solutions and determine improvements

## Target Candidate Description
The target candidate should have at least **1 year of hands-on experience** designing cloud solutions that use AWS services. For a detailed list of specific tools and technologies that might be covered on the exam, as well as lists of in-scope and out-of-scope AWS services, refer to the Appendix.

## Exam Content

### Exam Duration
* **Total Time:** 130 minutes
* **Time Allocation:** Approximately 2.1 minutes per question

### Response Types
There are two types of questions on the exam:
* **Multiple choice:** Has one correct response and three incorrect responses (distractors)
* **Multiple response:** Has two or more correct responses out of five or more response options

Select one or more responses that best complete the statement or answer the question. Distractors, or incorrect answers, are response options that a candidate with incomplete knowledge or skill might choose. Distractors are generally plausible responses that match the content area. Unanswered questions are scored as incorrect; there is no penalty for guessing. The exam includes **50 scored questions**.

### Unscored Content
The exam includes **15 unscored questions** that do not affect your score. AWS collects information about candidate performance on these unscored questions to evaluate these questions for future use as scored questions. These unscored questions are not identified on the exam.

## Exam Results
The AWS Certified Solutions Architect - Associate exam is a pass or fail exam. The exam is scored against a minimum standard established by AWS professionals who follow certification industry best practices and guidelines.

* **Score Range:** 100–1,000
* **Minimum Passing Score:** 720

Your score shows how you performed on the exam as a whole and whether or not you passed. Scaled scoring models help equate scores across multiple exam forms that might have slightly different difficulty levels.

Your score report could contain a table of classifications of your performance at each section level. This information provides general feedback about your exam performance. The exam uses a compensatory scoring model, which means that you do not need to achieve a passing score in each section. **You need to pass only the overall exam.**

Each section of the exam has a specific weighting, so some sections have more questions than other sections have. The table contains general information that highlights your strengths and weaknesses. Use caution when interpreting section-level feedback. Candidates who pass the exam will not receive this additional information.

## Content Outline
This exam guide includes weightings, test domains, and task statements for the exam. It is not a comprehensive listing of the content on the exam. However, additional context for each of the task statements is available to help guide your preparation for the exam. 

The following table lists the main content domains and their weightings. The percentage in each domain represents only scored questions.

| Domain | % of Exam |
| :--- | :--- |
| **Domain 1:** Design Secure Architectures | 30% |
| **Domain 2:** Design Resilient Architectures | 26% |
| **Domain 3:** Design High-Performing Architectures | 24% |
| **Domain 4:** Design Cost-Optimized Architectures | 20% |
| **TOTAL** | **100%** |

## Introduction to S3

### What is Object Storage (Object-based Storage)?
Object storage is a data storage architecture that manages data as objects, as opposed to other storage architectures.

* **Unlimited Storage:** S3 provides you with unlimited storage.
* **No Infrastructure Management:** You don't need to think about the underlying infrastructure.
* **S3 Console:** The S3 Console provides an interface for you to upload and access your data.

### S3 Object
Objects contain your data. They are like files. An object may consist of:
* **Key:** This is the name of the object.
* **Value:** The data itself, made up of a sequence of bytes.
* **Version ID:** When versioning is enabled, this represents the version of the object.
* **Metadata:** Additional information attached to the object.

> **NOTE:** You can store an individual object from **0 Bytes to 5 Terabytes** in size.

### S3 Bucket
* Buckets hold objects. Buckets can also have folders which in turn hold objects.
* S3 is a **universal namespace**, so bucket names must be unique (think like having a domain name).

## S3 Bucket Overview

S3 Buckets are infrastructure, and they hold S3 Objects. This section covers:
* **S3 Bucket Naming Rules:** How we have to name our buckets.
* **S3 Bucket Restrictions and Limitations:** What we can and can't do with buckets.
* **S3 Bucket Types:** The two different kinds of buckets, flat (general purpose) and directory.
* **S3 Bucket Folders:** How S3 Buckets have virtual folders for general purpose buckets.
* **Bucket Versioning:** How we can version all objects.
* **Bucket Encryption:** How we can encrypt the contents of a bucket.
* **Static Website Hosting:** How we can let our buckets host websites.

> **Note:** S3 is a globally available service, but when you create a bucket, you specify a region.

## S3 Bucket Naming Rules

S3 Bucket Names are similar to valid URL rules (but with more rules), this is because S3 bucket names are used to form URL links to perform various HTTPS operations.

`https://myexamplebucket.s3.amazonaws.com/photo.jpg`

* **Length:** Bucket names must be 3-63 characters long.
* **Characters:** Only lowercase letters, numbers, dots (`.`), and hyphens (`-`) are allowed.
* **Start and End:** They must begin and end with a letter or number.
* **Adjacent Periods:** No two adjacent periods are allowed.
* **IP Address Format:** Names can't be formatted as IP addresses (e.g., `192.168.5.4`).
* **Restricted Prefixes:** Can't start with `xn--`, `sthree-`, or `sthree-configurator`.
* **Restricted Suffixes:** Can't end with `-s3alias` or `--ol-s3`, reserved for access point alias names.
* **Uniqueness:** Must be unique across all AWS accounts in all AWS Regions within a partition.
* **Exclusivity:** A name can't be reused in the same partition until the original bucket is deleted.
* **Transfer Acceleration:** Buckets used with S3 Transfer Acceleration can't have dots in their names.

> **Note:** No Uppercase, No Underscores, No Spaces in Bucket Names.

## S3 Bucket Restrictions and Limitations

* By default, you can create **100 buckets**.
* You can create a service request to increase the limit to **1,000 buckets**.
* You need to empty a bucket first before you can delete it.
* There is **no max bucket size** and no limit to the number of objects in a bucket.
* Files can be between **0 and 5 TBs**.
* Files larger than **100MB** should use multi-part upload.
* S3 for AWS Outposts has specific limits.
* **Get, Put, List, and Delete** operations are designed for high availability.
* **Create, Delete, or configuration** operations should be run less often.

## S3 Bucket Types

Amazon S3 has two types of buckets:

### General Purpose Buckets
* Organizes data in a flat hierarchy.
* The original S3 bucket type.
* Recommended for most use cases.
* Used with all storage classes except it can't be used with the S3 Express One Zone storage class.
* There aren't prefix limits.
* There is a default limit of 100 general buckets per account.

### Directory Buckets
* Organizes data in a folder hierarchy.
* Only to be used with the S3 Express One Zone storage class.
* Recommended when you need single-digit millisecond performance on PUT and GET.
* There aren't prefix limits for directory buckets.
* Individual directories can scale horizontally.
* There is a default limit of 10 directory buckets per account.

## S3 Bucket Folders

The S3 Console allows you to "create folders". S3 general purpose buckets do not have true folders found in a hierarchical file system.

When you create a folder in the S3 Console, Amazon S3 creates a zero-byte S3 object with a name that ends in a forward slash (e.g., `myfolder/`).

**Example:** `myfolder/myfile.jpg`

* S3 folders are not their own independent identities but just S3 Objects.
* S3 folders don't include metadata or permissions.
* S3 folders don't contain anything; they can't be full or empty.
* S3 folders aren't "moved"; S3 objects containing the same prefix are renamed.

## S3 Object Overview

S3 Objects are resources that represent data and are not infrastructure.

* **Etags:** A way to detect when the contents of an object have changed without downloading the contents.
* **Checksums:** Ensures the integrity of a file being uploaded or downloaded.
* **Object Prefixes:** Simulates file-system folders in a flat hierarchy.
* **Object Metadata:** Attach data alongside the content to describe the contents of the data.
* **Object Tags:** Benefits resource tagging but at the object level.
* **Object Locking:** Makes data files immutable.
* **Object Versioning:** Have multiple versions of a data file.


## Write Once Read Many (WORM)

**Write Once Read Many (WORM)** is a storage compliance feature that makes data immutable. You write the data once, and the file can never be modified or deleted, but you may read it an unlimited number of times.

* **Use Cases:** WORM is useful in healthcare or financial industries, where files need to be audited and remain untampered.
* **Analogy:** An example of WORM is a video game cartridge, where data is written permanently to a ROM (Read-Only Memory).

## S3 Object Lock

S3 Object Lock allows you to prevent the deletion of objects in a bucket. 

* This feature can **only be turned on at the creation of a bucket**.
* Object Lock is for companies that need to prevent objects from being deleted to ensure:
  * Data integrity
  * Regulatory compliance
* S3 Object Lock is **SEC 17a-4, CTCC, and FINRA** regulation compliant.
* You can store objects using a write-once-read-many (WORM) model, just like S3 Glacier.
* You can use it to prevent an object from being deleted or overwritten for:
  * A fixed amount of time
  * Indefinitely

**Object Retention Methods:**
1. **Retention periods:** A fixed period of time during which an object remains locked.
2. **Legal holds:** The object remains locked until you explicitly remove the hold.

> **Note:** S3 buckets with Object Lock enabled cannot be used as destination buckets for server access logs.

> **Note:** Object Locking settings can only be set via the AWS API (e.g., CLI, SDK) and not the AWS Console. This is to avoid misconfiguration by non-technical users accidentally locking objects.

## Amazon S3 Bucket URI

The S3 Bucket URI (Uniform Resource Identifier) is a way to reference the address of an S3 bucket and S3 objects.

**Example:** 
```text
s3://myexamplebucket/photo.jpg
```

You will see this S3 Bucket URI required to be used for specific AWS CLI commands.

**Example:**
```bash
aws s3 cp test.txt s3://mybucket/test2.txt
```

## AWS S3 CLI

There are several command-line interfaces for interacting with S3:

* **`aws s3`**: A high-level way to interact with S3 buckets and objects.
* **`aws s3api`**: A low-level way to interact with S3 buckets and objects.
* **`aws s3control`**: Used for managing S3 access points, S3 Outposts buckets, S3 batch operations, and Storage Lens.
* **`aws s3outposts`**: Used to manage endpoints for S3 Outposts.

## S3 Request Styles

When making requests by using the REST API, there are two styles of requests:
1. **Virtual hosted-style requests:** The bucket name is a subdomain on the host.
2. **Path-style requests:** The bucket name is in the request path.

### Virtual Hosted-Style Request
```http
DELETE /puppy.jpg HTTP/1.1
Host: examplebucket.s3.us-west-2.amazonaws.com
Date: Mon, 11 Apr 2016 12:00:00 GMT
x-amz-date: Mon, 11 Apr 2016 12:00:00 GMT
Authorization: authorization string
```

### Path-Style Request
```http
DELETE /examplebucket/puppy.jpg HTTP/1.1
Host: s3.us-west-2.amazonaws.com
Date: Mon, 11 Apr 2016 12:00:00 GMT
x-amz-date: Mon, 11 Apr 2016 12:00:00 GMT
Authorization: authorization string
```

> **Note:** To force the AWS CLI to use virtual hosted-style requests, you need to globally configure the CLI.

## S3 Storage Classes - Standard

S3 Standard is the default storage class when you upload to S3. It is designed for general-purpose storage for frequently accessed data.

* **High Durability:** 11 9's of durability (99.999999999%)
* **High Availability:** 4 9's of availability (99.99%)
* **Data Redundancy:** Data is stored in 3 or more Availability Zones (AZs)
* **Retrieval Time:** Within milliseconds (low latency)
* **High Throughput:** Optimized for data that is frequently accessed and/or requires real-time access
* **Scalability:** Easily scales to storage size and number of requests
* **Use Cases:** Ideal for a wide range of use cases like content distribution, big data analytics, and mobile and gaming applications, where frequent access is required.

**Pricing:**
* Storage per GB
* Per Request
* No Retrieval fee
* No minimum storage duration charge

## S3 Storage Classes - RRS (Reduced Redundancy Storage)

S3 Reduced Redundancy Storage (RRS) is a legacy storage class designed to store non-critical, reproducible data at lower levels of redundancy than Amazon S3's standard storage.

* RRS was introduced in 2010, and at the time, it was cheaper than Standard storage.
* In 2018, S3 Standard infrastructure changed, and the cost of S3 Standard storage fell well below the cost of RRS.
* RRS currently provides no cost-benefit to customers for the reduced redundancy and has no place in modern storage use-cases.

> **Note:** RRS is no longer cost-effective and is **not recommended for use**. It may still appear in the AWS Console as an option due to legacy customers.

## S3 Storage Classes - Standard-IA (Infrequent Access)

S3 Standard-IA is designed for data that is less frequently accessed but requires rapid access when needed.

* **High Durability:** 11 9's of durability (like S3 Standard)
* **High Availability:** 3 9's of availability (99.9%) - Slower availability compared to S3 Standard
* **Data Redundancy:** Data is stored in 3 or more Availability Zones (AZs)
* **Cost-Effective Storage:** Costs 50% less than Standard, as long as you don't access a file more than once a month!
* **Retrieval Time:** Within milliseconds (low latency)
* **High Throughput:** Optimized for rapid access, although the data is accessed less frequently compared to S3 Standard.
* **Scalability:** Easily scales to storage size and number of requests like S3 Standard
* **Use Cases:** Ideal for data that is accessed less frequently but requires quick access when needed, such as disaster recovery, backups, or long-term data stores.

**Pricing:**
* Storage per GB
* Per Request
* Has a Retrieval fee
* Has a minimum storage duration charge of 30 days

## S3 Storage Classes - Express One Zone

Amazon S3 Express One Zone delivers consistent single-digit millisecond data access for your most frequently accessed data and latency-sensitive applications.

* **Lowest Latency:** The lowest latency cloud object storage class available.
* **Performance:** Data access speeds up to 10x faster than S3 Standard.
* **Request Costs:** Request costs are 50% lower than S3 Standard.
* **Data Redundancy:** Data is stored in a user-selected single Availability Zone (AZ).
* **Bucket Type:** Data is stored in a new bucket type: an Amazon S3 Directory bucket.
  * S3 Directory buckets support a simple real-folder structure.
  * You are only allowed 10 Directory buckets by default per account.
* **Pricing Detail:** Express One Zone applies a flat per-request charge for request sizes up to 512 KB.

## S3 Storage Classes - One-Zone-IA

S3 One-Zone-IA is designed for data that is less frequently accessed and offers additional savings at reduced availability.

* **High Durability:** 11 9's of durability (like S3 Standard and S3 Standard-IA)
* **Lower Availability:** 99.5%. Since it is in a single AZ, it has even lower availability than Standard-IA.
* **Cost-Effective Storage:** Costs 20% less than Standard-IA.
* **Data Redundancy:** Data is stored in one Availability Zone (AZ). There is a risk of data loss in the case of an AZ disaster.
* **Retrieval Time:** Within milliseconds (low latency)
* **Use Cases:** Ideal for secondary backup copies of on-premises data, or for storing data that can be recreated in the event of an AZ failure. It's also suitable for storing infrequently accessed data that is non-mission-critical.

**Pricing:**
* Storage per GB
* Per Request
* Has a Retrieval fee
* Has a minimum storage duration charge of 30 days

## S3 Glacier Storage Classes vs S3 Glacier "Vault"

### S3 Glacier "Vault" (Standalone Service)
* "S3" Glacier is a stand-alone service from S3 that uses **vaults** (instead of buckets) to store data long-term.
* It is the original vault service and features vault control policies.
* Most interactions occur via the AWS CLI.
* Many enterprises are still using S3 Glacier Vault.

### S3 Glacier Storage Classes (Within S3 Buckets)
* S3 Glacier Storage classes offer similar functionality to S3 Glacier but with greater convenience and flexibility, all managed within standard S3 Buckets.
* This is a newer approach with no attachment to the standalone S3 Glacier Vault.

**Under the Hood:**
* **S3 Glacier Instant Retrieval:** A true S3 Storage Class (no Vault required).
* **S3 Glacier Flexible Retrieval:** Uses S3 Glacier Vault underneath.
* **S3 Glacier Deep Archive:** Uses S3 Glacier Vault underneath.

## S3 Storage Classes - Glacier Instant Retrieval

S3 Glacier Instant Retrieval is a storage class designed for rarely accessed data that still needs immediate access in performance-sensitive use cases.

* **High Durability:** 11 9's of durability (like S3 Standard)
* **High Availability:** 3 9's of availability (99.9%) like S3 Standard-IA
* **Cost-Effective Storage:** 68% lower cost than Standard-IA. Ideal for long-lived data that is accessed once per quarter.
* **Retrieval Time:** Within milliseconds (low latency)
* **Use Cases:** Rarely accessed data that needs immediate access (e.g., image hosting, online file-sharing applications, medical imaging and health records, news media assets, and satellite/aerial imaging).

**Pricing:**
* Storage per GB
* Per Request
* Has a Retrieval fee
* Has a minimum storage duration charge of 90 days

> **Note:** Glacier Instant Retrieval is not a separate service and does not require a Vault.



## S3 Storage Classes - Glacier Flexible Retrieval

S3 Glacier Flexible Retrieval (formerly S3 Glacier) combines S3 and Glacier into a single set of APIs. It's considerably faster than Glacier Vault-based storage.

**Retrieval Tiers** (the faster, the more expensive):
* **Expedited Tier:** 1-5 mins. For urgent requests. Limited to 250 MB archive size.
* **Standard Tier:** 3-5 hours. No archive size limit. This is the default option.
* **Bulk Tier:** 5-12 hours. No archive size limit, even petabytes worth of data.

**Pricing & Overhead:**
* You pay per GB retrieved and the number of requests. This is a separate cost from just the cost of storage.
* Archived objects will have an additional **40KB** of data overhead:
  * 32KB for archive index and archive metadata information.
  * 8KB for the name of the object.
* **Best Practice:** You should store fewer and larger files, instead of smaller files. 40KB on thousands of files adds up.

> **Note:** Glacier Flexible Retrieval is not a separate service and does not require a Vault.

## S3 Storage Classes - Glacier Deep Archive

S3 Glacier Deep Archive combines S3 and Glacier into a single set of APIs. It's more cost-effective than S3 Glacier Flexible but has a greater cost of retrieval.

**Retrieval Tiers:**
* **Standard Tier:** 12-48 hours. No archive size limit. This is the default option.
* **Bulk Tier:** 12-48 hours. No archive size limit, even petabytes worth of data.

> **Note:** There is no Expedited tier for Glacier Deep Archive.

**Overhead:**
* Archived objects will have an additional **40KB** of data:
  * 32KB for index and metadata information.
  * 8KB for the name of the object.

> **Note:** Glacier Deep Archive is not a separate service and does not require a Vault.

## S3 Storage Classes - Intelligent-Tiering

S3 Intelligent-Tiering storage class automatically moves objects into different storage tiers to reduce storage costs, but charges a low monthly cost for object monitoring and automation.

**Access Tiers:**
* **Frequent Access tier (automatic):** The default tier. Objects remain in here as long as they are being accessed.
* **Infrequent Access tier (automatic):** If an object is not accessed after 30 days, it is moved here.
* **Archive Instant Access tier (automatic):** If an object is not accessed after 90 days, it is moved here.
* **Archive Access tier (optional):** After activation, if an object is not accessed after 90 days, it is moved here.
* **Deep Archive Access tier (optional):** After activation, if an object is not accessed after 180 days, it is moved here.

> **Note:** S3 Intelligent-Tiering has an additional cost to analyze your objects (monitoring and automation fee).
