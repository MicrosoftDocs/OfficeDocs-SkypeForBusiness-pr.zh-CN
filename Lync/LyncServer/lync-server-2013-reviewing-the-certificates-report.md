---
title: 在 Lync Server 2013 中查看证书报告
TOCTitle: 在 Lync Server 2013 中查看证书报告
ms:assetid: 549cfc9b-3cc5-4483-a93c-fc0738c7f622
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg558651(v=OCS.15)
ms:contentKeyID: 52061025
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中查看证书报告

 

_**上一次修改主题：** 2013-02-21_

证书报告提供了推荐的 Lync Server 2013 部署中所需的全部证书。规划工具负责处理输入的使用者名称和使用者替代名称。未经编辑的默认文本可能会给负责请求和颁发证书的团队带来挑战。证书信息还包含通常可以从何处颁发证书的信息。如果基础结构中没有内部公钥基础结构 (PKI)，则可以通过公共证书提供商请求所有证书。该报告中的“扩展密钥用法 (EKU)”和“分配给”字段非常有助于理解每个证书应有的用途和应处的位置。

![证书管理报告](images/Gg558651.63a29335-d9e4-41ae-97ec-3c9d9fd30d8a(OCS.15).jpg "证书管理报告")

仔细阅读并确保了解部署中每个证书的用法和用途。如果对证书用途有疑问，请确定是何种服务器或服务在与何种对象通信。Lync Server 2013 中证书的两个主要用途是：

  - 相互传输层安全性 (MTLS) – 参与通信的每台计算机均需向另一台计算机出示证明其身份的证书，这称为服务器身份验证。所有计算机相互信任彼此的身份后，通信才会开始。

  - 加密 – 加密（安全套接字层 (SSL) 和传输层安全性 (TLS)）是帮助保护通信安全、确保隐私以及创建受信任通信与协作系统的重要途径。

## 另请参阅

#### 其他资源

[在 Lync Server 2013 中查看管理员报告](lync-server-2013-reviewing-the-administrator-reports.md)

