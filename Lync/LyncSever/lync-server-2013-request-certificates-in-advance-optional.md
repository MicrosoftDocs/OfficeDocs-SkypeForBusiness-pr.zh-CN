---
title: Lync Server 2013：提前请求证书（可选）
TOCTitle: 提前请求证书（可选）
ms:assetid: 9d6d7de6-ff2a-46da-b1b7-a354c8e383e4
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412733(v=OCS.15)
ms:contentKeyID: 49313749
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 为 Lync Server 2013 提前请求证书（可选）

 

_**上一次修改主题：** 2013-02-21_

运行 Lync Server 2013 的所有内部服务器（包括每台 企业版前端服务器、 Standard Edition Server、 控制器、 边缘服务器和独立的 中介服务器）均需要证书。虽然建议对内部服务器使用内部企业证书颁发机构 (CA)，但您也可以使用公共 CA。有关证书要求和使用公共 CA 的详细信息，请参阅规划文档中的 [Lync Server 2013 中内部服务器的证书要求](lync-server-2013-certificate-requirements-for-internal-servers.md)。

Lync Server 2013 安装程序包括证书向导，可帮助您在部署期间执行请求、分配和安装证书的任务。如果要在安装服务器之前请求证书（例如，为在实际部署服务器时节省时间），可以使用安装了 Lync Server 2013 管理工具的计算机或使用组织中定义的证书请求过程来实现，前提是确保证书可导出并包含所需的全部使用者替代名称。提前请求证书是可选的。如果没有提前请求，则必须在安装每台需要证书的服务器的过程中请求证书。

此部署文档提供了在安装过程中使用证书向导请求证书的过程，如此部署文档的 [在 Lync Server 2013 中为服务器配置证书](lync-server-2013-configure-certificates-for-servers.md)、 [在 Lync Server 2013 中为控制器配置证书](lync-server-2013-configure-certificates-for-the-director.md)和 [在 Lync Server 2013 中安装中介服务器的文件](lync-server-2013-install-the-files-for-mediation-server.md)各节中所述。如果提前请求证书，则必须适当修改上述各节中的证书部署过程，以导入和分配证书，而不是在部署时请求证书。

> [!NOTE]  
> 对于从运行 Windows Vista、 Windows Server 2008、 Windows Server 2008 R2 和 Windows 7 操作系统以及 Lync Phone Edition 的客户端发出的连接， Lync Server 2013 支持使用 SHA-256 证书。要支持使用 SHA-256 进行外部访问，外部证书必须由公共 CA 使用 SHA-256 颁发。


