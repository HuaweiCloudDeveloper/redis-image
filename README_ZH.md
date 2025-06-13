 <h1 align="center">Redis数据库</h1>
  <p align="center">
    <a href="README.md"><strong>English</strong></a> | <strong>简体中文</strong>
  </p>


## 目录

- [仓库简介](#项目介绍)
- [前置条件](#前置条件)
- [镜像说明](#镜像说明)
- [获取帮助](#获取帮助)
- [如何贡献](#如何贡献)

## 项目介绍

[Redis](https://github.com/redis/redis/) 是一款高性能的‌内存键值数据库‌，支持多种数据结构（字符串、哈希、列表等），用于快速数据读写场景。本商品基于arm架构的Huawei Cloud EulerOS 2.0 64bit系统，提供开箱即用的‌Redis‌数据库。

## 为什么选择Redis

由于速度，灵活性和丰富功能集的结合，Redis是全球开发人员的流行选择。这就是为什么人们选择Redis的原因：

- **性能：** 因为REDIS主要将数据保留在内存中并使用有效的数据结构，因此它可以为读取和写操作实现极低的延迟（通常为子毫秒）。这使其非常适合需要实时响应能力的应用程序。
- **灵活性：**  Redis不仅是一家钥匙值商店，还为Redis中列出的广泛数据结构和功能提供了本机支持？
- **可扩展性：**  REDIS不限于内置数据结构，它具有一个模块API，可以扩展REDIS功能并迅速实现新的REDIS命令
- **简单性：** Redis具有简单的，基于文本的协议和有据可查的命令集
- **普遍存在：** Redis在生产工作量中进行了大规模测试。您很可能每天间接与Redis互动几次
- **多功能性：** Redis是用例的事实上的标准，例如：
    - **缓存：** 快速访问常用数据，无需查询主数据库
    - **会话管理：** 读写用户会话数据而不会损害用户体验或减慢每个API调用
    - **查询，分类和分析：** 执行重复数据删除，全文搜索以及在内存数据上尽快在内存数据上进行辅助索引
    - **消息传递和服务间通信：** 用于服务之间通信的作业队列、消息代理、发布/订阅和流
    - **向量操作：** 长期和短期LLM内存、RAG内容检索、语义缓存、语义路由和向量相似性搜索

本项目提供的开源镜像商品 [**Redis数据库**](https://marketplace.huaweicloud.com/hidden/contents/61248ad4-be4d-4078-a918-ad59ef63a52f#productid=OFFI1111824746859552768) 已预先安装6.2.7版本的Redis及其相关运行环境，并提供部署模板。快来参照使用指南，轻松开启“开箱即用”的高效体验吧。


> **系统要求如下：**
> - CPU: 2vCPUs 或更高
> - RAM: 4GB 或更大
> - Disk: 至少 40GB

## 前置条件
[注册华为账号并开通华为云](https://support.huaweicloud.com/usermanual-account/account_id_001.html)

## 镜像说明

| 镜像规格                                                                                            | 特性说明 | 备注 |
|-------------------------------------------------------------------------------------------------| --- | --- |
| [Redis6.2.7-arm-v1](https://github.com/HuaweiCloudDeveloper/redis-image/tree/Redis6.2.7-arm-v1) | 基于鲲鹏服务器 + Huawei Cloud EulerOS 2.0 64bit 安装部署 |  |

## 获取帮助
- 更多问题可通过 [issue](https://github.com/HuaweiCloudDeveloper/redis-image/issues) 或 华为云云商店指定商品的服务支持 与我们取得联系
- 其他开源镜像可看 [open-source-image-repos](https://github.com/HuaweiCloudDeveloper/open-source-image-repos)

## 如何贡献
- Fork 此存储库并提交合并请求
- 基于您的开源镜像信息同步更新 README.md