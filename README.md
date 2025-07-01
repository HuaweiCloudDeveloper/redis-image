<h1 align="center">Redis Database</h1>
<p align="center">
    <strong>English</strong> | <a href="README_ZH.md">简体中文</a>
</p>

## Table of Contents

- [Repository Introduction](#repository-introduction)
- [Prerequisites](#prerequisites)
- [Image Description](#image-description)
- [Get Help](#get-help)
- [How to Contribute](#how-to-contribute)

## Repository Introduction

[Redis](https://github.com/redis/redis/) is a high-performance in-memory key-value database that supports multiple data structures (strings, hashes, lists, etc.) and is used in scenarios requiring fast data reading and writing. This product is based on the arm architecture Huawei Cloud EulerOS 2.0 64-bit system and provides an out-of-the-box Redis database.

## Why choose Redis?

Redis is a popular choice for developers worldwide due to its combination of speed, flexibility, and rich feature set. Here's why people choose Redis for:

- **Performance:** Because Redis keeps data primarily in memory and uses efficient data structures, it achieves extremely low latency (often sub-millisecond) for both read and write operations. This makes it ideal for applications demanding real-time responsiveness.
- **Flexibility:** Redis isn't just a key-value store, it provides native support for a wide range of data structures and capabilities listed in [What is Redis?](#what-is-redis)
- **Extensibility:** Redis is not limited to the built-in data structures, it has a [modules API](https://redis.io/docs/latest/develop/reference/modules/) that makes it possible to extend Redis functionality and rapidly implement new Redis commands
- **Simplicity:** Redis has a simple, text-based protocol and [well-documented command set](https://redis.io/docs/latest/commands/)
- **Ubiquity:** Redis is battle tested in production workloads at a massive scale. There is a good chance you indirectly interact with Redis several times daily
- **Versatility**: Redis is the de facto standard for use cases such as:
    - **Caching:** quickly access frequently used data without needing to query your primary database
    - **Session management:** read and write user session data without hurting user experience or slowing down every API call
    - **Querying, sorting, and analytics:** perform deduplication, full text search, and secondary indexing on in-memory data as fast as possible
    - **Messaging and interservice communication:** job queues, message brokering, pub/sub, and streams for communicating between services
    - **Vector operations:** Long-term and short-term LLM memory, RAG content retrieval, semantic caching, semantic routing, and vector similarity search

The open-source image product [**Redis Database**](https://marketplace.huaweicloud.com/contents/61248ad4-be4d-4078-a918-ad59ef63a52f#productid=OFFI1111824746859552768) provided by this project has Redis version 6.2.7 and its related runtime environment pre-installed and also offers deployment templates. Refer to the usage guide and start your efficient "out-of-the-box" experience now!

> **System requirements are as follows:**
> - CPU: 2 vCPUs or higher
> - RAM: 4GB or more
> - Disk: At least 40GB

## Prerequisites
[Register a Huawei account and activate Huawei Cloud](https://support.huaweicloud.com/usermanual-account/account_id_001.html)

## Image Description

| Image Specification                                                                               | Feature Description | Remarks |
|---------------------------------------------------------------------------------------------------| --- | --- |
| [Redis-6.2.7-kunpeng](https://github.com/HuaweiCloudDeveloper/redis-image/tree/Redis-6.2.7-kunpeng) | Installed and deployed based on Kunpeng servers + Huawei Cloud EulerOS 2.0 64-bit |  |

## Get Help
- For more questions, you can contact us via [issues](https://github.com/HuaweiCloudDeveloper/redis-image/issues) or the service support of the specified product in the Huawei Cloud Marketplace.
- For other open-source images, refer to [open-source-image-repos](https://github.com/HuaweiCloudDeveloper/open-source-image-repos).

## How to Contribute
- Fork this repository and submit a merge request.
- Update README.md synchronously based on your open-source image information.