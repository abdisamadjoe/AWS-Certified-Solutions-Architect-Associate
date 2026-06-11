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


## S3 Storage Classes Comparison

| Feature | Express One-Zone | Standard | Intelligent Tiering | Standard IA | One-Zone IA | Glacier Instant | Glacier Flexible | Glacier Deep Archive |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **Durability** | 11 9's | 11 9's | 11 9's | 11 9's | 11 9's | 11 9's | 11 9's | 11 9's |
| **Availability** | 99.95% | 99.99% | 99.9% | 99.9% | 99.5% | 99.9% | N/A | N/A |
| **Availability SLA** | 99.9% | 99.99% | 99% | 99% | 99% | 99%? | N/A | N/A |
| **AZs** | 1 | >3 | >3 | >3 | 1 | >3 | >3 | >3 |
| **Min cap. charge per obj** | N/A | N/A | N/A | 128kb | 128kb | - | 40kb | 40kb |
| **Min stor. duration charge** | N/A | N/A | 30 days | 30 days | 30 days | 90 days | 90 days | 180 days |
| **Retrieval fee** | N/A | N/A | N/A | Per GB | Per GB | Per GB | Per GB | Per GB |
| **First byte latency** | single-digit ms | ms | ms | ms | ms | ms | mins to hrs | hours |


## S3 Security Overview

* **Bucket Policies:** Define permissions for an entire S3 bucket using a JSON-based access policy language.
* **Access Control Lists (ACLs):** Provide a legacy method to manage access permissions on individual objects and buckets.
* **AWS PrivateLink for Amazon S3:** Enables private network access to S3, bypassing the public internet for enhanced security.
* **Cross-Origin Resource Sharing (CORS):** Allows restricted resources on a web page from another domain to be requested.
* **Amazon S3 Block Public Access:** Offers settings to easily block public access to all your S3 resources.
* **IAM Access Analyzer for S3:** Analyzes resource policies to help identify and mitigate potential access risks.
* **Internetwork Traffic Privacy:** Ensures data privacy by encrypting data moving between AWS services and the Internet.
* **Object Ownership:** Manages data ownership between AWS accounts when objects are uploaded to S3 buckets.
* **Access Points:** Simplifies managing data access at scale for shared datasets in S3.
* **Access Grants:** Provides access to S3 data via directory services (e.g., Active Directory).
* **Versioning:** Preserves, retrieves, and restores every version of every object stored in an S3 bucket.
* **MFA Delete:** Adds an additional layer of security by requiring MFA for the deletion of S3 objects.
* **Object Tags:** Provides a way to categorize storage by assigning key-value pairs to S3 objects.
* **In-Transit Encryption:** Protects data by encrypting it as it travels to and from S3 over the internet.
* **Server-Side Encryption:** Automatically encrypts data when writing it to S3 and decrypts it when downloading.
* **Client-Side Encryption:** Encrypts data client-side before uploading to S3 and decrypts it after downloading.
* **Compliance Validation for Amazon S3:** Ensures S3 services meet compliance requirements like HIPAA, GDPR, etc.
* **Infrastructure Security:** Protects the underlying infrastructure of the S3 service, ensuring data integrity and availability.

## Amazon S3 Block Public Access

Block Public Access is a safety feature that is enabled by default to block all public access to an S3 bucket.

> **Important:** Unrestricted access to S3 buckets is the **#1 security misconfiguration**.

**There are four options to configure:**
* **New Access Control Lists (ACLs):** Blocks new ACLs from being created.
* **Any Access Control Lists:** Blocks all existing and new ACLs.
* **New Bucket Policies or Access Points:** Blocks new bucket policies or access points from granting public access.
* **Any Bucket Policies or Access Points:** Blocks all existing and new bucket policies or access points from granting public access.

> **Note:** Access points can have their own independent Block Public Access setting.


## Amazon S3 - Access Control Lists (ACLs)

ACLs grant basic read/write permissions to other AWS accounts. 

**Key Limitations of ACLs:**
* You can grant permissions **only to other AWS accounts**.
* You **cannot** grant permissions to users in your own account.
* You **cannot** grant conditional permissions.
* You **cannot** explicitly deny permissions.

S3 ACLs have been traditionally used to allow other AWS accounts to upload objects to a bucket.

> **Note:** Access Control Lists (ACLs) are a **legacy feature** of S3. There are much more robust and recommended ways to provide cross-account access via **Bucket Policies** and **Access Points**.


Amazon S3 - Bocket Policies

S3 Bucket Policy is a resource-based policy to grant an s3 bucket and bucket
objects to other Principles eg. AWS Accounts, Users, AWS services



S3 Bucket Policies vs IAM Policies

S3 Bucket policies have overlapping functionality as an IAM policy that grant access to S3.
S3 Bucket Policies provide convenience over IAM policies granting S3 access.


S3 Bucket Policy

Provides access to a specific bucket and its objects

You can specific multiple principal to grant access

Bucket Policies can be 20 KB in size

Block Public Access is turned on by default and
will DENY all anonymous access even if the
bucket policy grant its unless the feature is
turned off.


IAM Policy

Provides access to many AWS services
Can provide permissions for multiple buckets in one policy

The principal by default is the entity the IAM
policy is attached to

IAM policy sizes are limited based on the principal:
. Users 2 KB
. Groups 5 KB
. Roles 10 KB


Amazon S3 - Access Grants

Amazon S3 Access Grants lets you map identities in a directory service
(IAM Identify center, Active Directory, Okta) to access datasets in s3.


IAM Access Analyzer for S3

Access Analyzer for S3 will alert you when your S3 buckets are exposed to the Internet or other AWS Accounts.


In order to use Access Analyzer for S3 you need to first create an analyzer in IAM Access Analyzer at the account level.


## Internetwork Traffic Privacy

Internetwork traffic privacy is about keeping data private as it travels across different networks.

### AWS PrivateLink (VPC Interface Endpoints)
Allows you to connect an Elastic Network Interface (ENI) directly to other AWS services (e.g., S3, EC2, Lambda). It can also connect to select third-party services via the AWS Marketplace.
* **Cross-Account:** Yes, AWS PrivateLink can go cross-account.
* **Permissions:** Has fine-grained permissions via VPC endpoint policies.
* **Cost:** There is a charge for using AWS PrivateLink.

### VPC Gateway Endpoint
Allows you to connect a VPC directly to S3 (or DynamoDB), staying private within the internal AWS network.
* **Cross-Account:** No, VPC Gateway Endpoints cannot go cross-account.
* **Permissions:** Does not have fine-grained permissions.
* **Cost:** There is **no charge** to use VPC Gateway Endpoints.

## Cross-Origin Resource Sharing (CORS)

Cross-Origin Resource Sharing (CORS) is an HTTP-header based mechanism that allows a server to indicate any other origins (domain, scheme, or port) than its own from which a browser should permit loading of resources.

Access is controlled via HTTP headers:

**Request Headers:**
* `Origin`
* `Access-Control-Request-Method`
* `Access-Control-Request-Headers`

**Response Headers:**
* `Access-Control-Allow-Origin`
* `Access-Control-Allow-Credentials`
* `Access-Control-Expose-Headers`
* `Access-Control-Max-Age`
* `Access-Control-Allow-Methods`

> **Note:** CORS restricts which websites may access data to be loaded onto its page.

## S3 Encryption Overview

### Encryption In Transit
Data is encrypted by the sender and then decrypted by the receiver.

### Encryption At-Rest
* **Client-Side Encryption (CSE):** Data is encrypted by the client and then sent to the server. The client has the key; the server will serve the encrypted file since it does not have the key to decrypt when data is requested.
* **Server-Side Encryption (SSE):** Data is encrypted by the server. The server has the key to decrypt when data is requested.

## S3 - Encryption In Transit

Encryption In-Transit ensures that data remains confidential and cannot be intercepted or viewed by unauthorized parties while moving between locations. 

**Common Algorithms:** TLS, SSL

### Transport Layer Security (TLS)
An encryption protocol for data integrity between two or more communicating computer applications.
* TLS 1.0 and 1.1 are **deprecated**.
* **TLS 1.2 and TLS 1.3** are the current best practices.

### Secure Sockets Layer (SSL)
An older encryption protocol for data integrity between communicating applications.
* SSL 1.0, 2.0, and 3.0 are all **deprecated**.

## S3 - Server-Side Encryption

Server-Side Encryption (SSE) is **always-on** for all new S3 objects.

* **SSE-S3:** Amazon S3 manages the keys. Encrypts using the AES-GCM (256-bit) algorithm.
* **SSE-KMS:** Uses AWS Key Management Service (KMS). You manage the keys.
* **SSE-C:** Customer-provided keys. You manage the keys entirely.
* **DSSE-KMS:** Dual-layer server-side encryption. Encrypts the object twice for enhanced security.

> **Note:** Server-side encryption only encrypts the **contents** of an object, not its metadata.


## S3 Bucket Key

When you use SSE-KMS, an individual data key is used for every object request. In this case, S3 has to call AWS KMS every time a request is made. KMS charges based on the number of requests, so this cost can add up quickly.

**S3 Bucket Key** lets you generate a short-lived bucket-level key from AWS KMS that is temporarily stored in S3.
* **Cost Reduction:** Reduces KMS request costs by up to 99%.
* **Performance:** Decreases request traffic and improves overall performance.

**Key Details:**
* A unique bucket-level key is generated for each requester.
* You can enable the Bucket Key at the **bucket level** to apply it to all new objects.
* You can enable the Bucket Key at the **object level** for only specific objects.
* S3 Bucket Key can be enabled for both **SSE-S3** and **SSE-KMS**.

## S3 - Client-Side Encryption

Client-Side Encryption is when you encrypt your own files before uploading them to S3. This provides a guarantee that AWS, and no third-party, can decrypt your data, as you retain full control of the encryption keys.

## S3 - Data Consistency

**What is data consistency?**
It refers to data being kept in two different places and whether the data exactly matches or does not match across those locations.

* **Strongly Consistent:** Every time you request data (query), you can expect consistent data to be returned within a specific time (e.g., 1 second). You will never be returned old data, but you may have to wait at least 2 seconds for the query to return.
* **Eventually Consistent:** When you request data, you may get back inconsistent data within a short window (e.g., 2 seconds). The system gives you whatever data is currently in the database (which could be new or old), but if you wait a little bit longer, it will generally be up to date.

> **Important Note:** Amazon S3 offers **strong consistency** for all read, write, and delete operations. Prior to January 2020, S3 did not have strong consistency for all S3 operations.

## S3 - Object Replication

Object Replication helps you achieve the following:
* Replicate objects while retaining metadata.
* Replicate objects into different storage classes.
* Maintain object copies under different ownership.
* Keep objects stored over multiple AWS Regions.
* Replicate objects within 15 minutes.
* Sync buckets, replicate existing objects, and replicate previously failed or replicated objects.
* Replicate objects and fail over to a bucket in another AWS Region.

**Replication Options in S3:**
* **Cross-Region Replication (CRR):** Live-replication across different regions.
* **Same-Region Replication (SRR):** Live-replication within the same region.
* **Bi-Directional Replication:** Live-replication in both directions between two buckets.
* **S3 Batch Replication:** On-demand replication for existing objects.

## S3 Versioning

S3 Versioning allows you to store multiple versions of S3 objects. With versioning, you can recover more easily from unintended user actions and application failures, such as accidental deletion or overwrite.

**Key Features:**
* Stores all versions of an object in S3 at the same object key address.
* By default, S3 Versioning is **disabled** on buckets, and you must explicitly enable it.
* Once enabled, it **cannot be disabled**, only suspended on the bucket.
* Fully integrates with S3 Lifecycle rules.
* **MFA Delete** feature provides extra protection against the permanent deletion of your data.

**Bucket States:**
Buckets can be in one of three states:
1. **Unversioned** (default)
2. **Versioned**
3. **Versioning Suspended**

## Introduction to S3 Lifecycle

S3 Lifecycle allows you to automate the storage class changes, archival, or deletion of objects.
* Can be used together with versioning.
* Can be applied to both current and previous (noncurrent) versions.

**There are two types of Actions:**
1. **Transition Actions:** Changing the storage class of an object.
2. **Expiration Actions:** Deleting an object after a certain period.

**Lifecycle Rule Actions:**
* Move current versions of objects between storage classes.
* Move noncurrent versions of objects between storage classes.
* Expire current versions of objects.
* Permanently delete noncurrent versions of objects.
* Delete expired object delete markers or incomplete multipart uploads.

## Introduction to S3 Transfer Acceleration

S3 Transfer Acceleration is a bucket-level feature that provides fast and secure transfer of files over long distances between your end users and an S3 bucket. It utilizes CloudFront's distributed Edge Locations to quickly enter the Amazon Global Network.

**Requirements and Constraints:**
* Only supported on **virtual-hosted style requests**.
* Buckets **cannot contain periods** and must be DNS compliant.
* It can take up to **20 minutes** after enabling for Transfer Acceleration to take effect.

## S3 - Presigned URLs

S3 Presigned URLs provide temporary access to upload or download object data via a URL. 

* Presigned URLs are commonly used to provide temporary access to private objects without requiring AWS credentials.
* You can use the **AWS CLI** or **AWS SDK** to generate a Presigned URL.
