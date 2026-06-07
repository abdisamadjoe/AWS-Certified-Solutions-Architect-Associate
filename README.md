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

## S3 Object
Objects contain your data. They are like files. An object may consist of:
* **Key:** This is the name of the object.
* **Value:** The data itself, made up of a sequence of bytes.
* **Version ID:** When versioning is enabled, this represents the version of the object.
* **Metadata:** Additional information attached to the object.

> **NOTE:** You can store an individual object from **0 Bytes to 5 Terabytes** in size.

## S3 Bucket
* Buckets hold objects. Buckets can also have folders which in turn hold objects.
* S3 is a **universal namespace**, so bucket names must be unique (think like having a domain name).
