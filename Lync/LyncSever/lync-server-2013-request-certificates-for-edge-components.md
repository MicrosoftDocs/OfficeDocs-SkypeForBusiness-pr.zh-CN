---
title: Lync Server 2013：请求边缘组件的证书
TOCTitle: 请求边缘组件的证书
ms:assetid: 8c72b877-febc-428f-89dc-389e7a7ac849
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398708(v=OCS.15)
ms:contentKeyID: 49313538
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中请求边缘组件的证书

 

_**上一次修改主题：** 2013-11-07_

支持外部用户访问所需的证书包括公共证书颁发机构 (CA) 颁发的证书和内部企业 CA 颁发的证书：

  - 边缘服务器和反向代理的外部接口所需的证书必须由公共 CA 颁发。

  - 内部接口所需的证书可以由公共 CA 或内部企业 CA 颁发。建议使用内部 Windows Server 2008 CA、Windows Server 2008 R2 CA、Windows Server 2012 CA 或 Windows Server 2012 R2 CA 创建这些证书以节省使用公共证书的费用。

> [!IMPORTANT]
> 处理证书请求可能需要花费一些时间（特别是向公共 CA 提交的请求），因此应提前请求 边缘服务器的证书，以确保开始部署 边缘服务器组件时证书可用。有关 边缘服务器的证书要求的摘要，请参阅 <a href="lync-server-2013-certificate-requirements-for-external-user-access.md">Lync Server 2013 中外部用户访问的证书要求</a>。


虽然可以选择将公共 CA 用于内部边缘证书，但是我们建议您将内部企业 CA 用于其他证书，以将证书的成本降到最低。有关 边缘服务器的证书要求摘要，请参阅 [Lync Server 2013 中外部用户访问的证书要求](lync-server-2013-certificate-requirements-for-external-user-access.md)。

> [!NOTE]  
> 安装 边缘服务器时，安装程序还包括协助请求、分配和安装证书的任务的证书向导，如 <a href="lync-server-2013-set-up-edge-certificates.md">为 Lync Server 2013 设置边缘证书</a>一节所述。如果要在安装 边缘服务器之前请求证书（例如为了在实际部署 边缘服务器组件期间节省时间），则可以使用内部服务器执行此操作，前提是确保证书可导出且包含全部所需的使用者替代名称。本文档不提供使用内部服务器请求证书的过程。



## 从公共 CA 请求证书

边缘服务器部署需要一个 边缘服务器外部接口的公共证书，以用于 访问边缘服务、 Web 会议边缘服务和 A/V 身份验证服务。此证书必须具有可导出的私钥才能确保 A/V 身份验证服务在池中的所有 边缘服务器上使用同一密钥。用于 Microsoft Internet Security and Acceleration (ISA) 服务器 2006 或 Microsoft Forefront Threat Management Gateway 2010 的反向代理也需要公共证书。

## 从内部企业 CA 请求证书

内部边缘接口所需的证书可由公共证书颁发机构 (CA) 或内部 CA 颁发。使用内部企业 CA 可以帮助最大限度地降低证书成本。如果组织部署了内部 CA，则应由内部 CA 颁发内部边缘的证书。对内部证书使用内部企业 CA 可降低证书成本。

有关边缘组件的证书要求摘要，请参阅 [Lync Server 2013 中外部用户访问的证书要求](lync-server-2013-certificate-requirements-for-external-user-access.md)。有关使用公共 CA 获取证书的详细信息，请参阅 [在 Lync Server 2013 中请求边缘组件的证书](lync-server-2013-request-certificates-for-edge-components.md)。有关请求、安装和分配证书的详细信息，请参阅 [为 Lync Server 2013 设置边缘证书](lync-server-2013-set-up-edge-certificates.md)。

