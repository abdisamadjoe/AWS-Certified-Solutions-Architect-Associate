# AWS Certified Solutions Architect - Associate (SAA-C03)

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

> **NOTE:** You can store an individual object from **0 Bytes to 5 Terabytes** in size.

## S3 Bucket
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
