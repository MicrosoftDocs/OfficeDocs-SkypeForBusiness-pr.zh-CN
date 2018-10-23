---
title: Lync Server 2013 证书基础结构支持
TOCTitle: 证书基础结构支持
ms:assetid: 47aa5c95-eb60-4d4b-81d5-7fdaef1a1145
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425950(v=OCS.15)
ms:contentKeyID: 49312723
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的证书基础结构支持

 

_**上一次修改主题：** 2013-11-07_

Lync Server 2013 需要公钥基础结构 (PKI) 来支持传输层安全性 (TLS) 连接和相互 TLS (MTLS) 连接。默认情况下，将 Lync Server 2013 配置为使用 TLS 进行客户端到服务器的连接。MTLS 用于服务器之间的连接。

Lync Server 2013 的 MTLS 证书必须由受信任的证书颁发机构 (CA) 颁发。Lync Server 支持以下 CA 颁发的证书：

  - 内部 CA 颁发的证书：
    
      - Windows Server 2003 操作系统 CA
    
      - Windows Server 2008 操作系统 CA
    
      - Windows Server 2008 R2 操作系统 CA
    
      - Windows Server 2012 操作系统 CA
    
      - Windows Server 2012 R2 操作系统 CA

  - 公共 CA 颁发的证书

与其他应用程序和服务器（如 Exchange 2013）通信需要使用其他应用程序和产品支持的证书。对于 2013 版本，Lync Server 2013 和其他 Microsoft 服务器产品（包括 Exchange 2013 和 SharePoint Server）都支持使用开放式授权 (OAuth) 协议进行服务器到服务器的身份验证和授权。有关详细信息，请参阅部署文档或操作文档中的[在 Lync Server 2013 中管理服务器到服务器身份验证 (Oauth) 和合作伙伴应用程序](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)。

对于从运行 Windows 7 操作系统、Windows Server 2008 R2 操作系统 和 Microsoft Office Communicator 2007 Phone Edition 的客户端发出的连接，Lync Server 2013 支持（但不需要）使用 SHA-256 加密哈希算法签署的证书。要支持使用 SHA-256 进行外部访问，外部证书必须由公共 CA 使用 SHA-256 颁发。

有关证书要求的详细信息，请参阅规划文档中的 [Lync Server 2013 的证书基础结构要求](lync-server-2013-certificate-infrastructure-requirements.md)。有关使用通配符证书的详细信息，请参阅可支持性文档中的 [Lync Server 2013 中的通配符证书支持](lync-server-2013-wildcard-certificate-support.md)。

