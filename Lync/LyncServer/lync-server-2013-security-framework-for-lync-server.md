---
title: Lync Server 2013 的安全框架
TOCTitle: Lync Server 2013 的安全框架
ms:assetid: 01131e28-b38e-40d9-8524-06725b9c6608
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn481316(v=OCS.15)
ms:contentKeyID: 59682852
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 的安全框架

 

_**上一次修改主题：** 2013-11-08_

此部分概述构成 Microsoft Lync Server 2013 安全框架的基本要素。了解各要素协同工作的方式对于做出有关保护特定 Lync Server 2013 部署的明智决定至关重要。

这些要素如下所示：

  - Active Directory 域服务 (AD DS) 为用户帐户和网络资源提供单个受信任的后端存储库。

  - 通过基于角色的访问控制 (RBAC)，您能够在保持高标准安全性的同时委派管理任务。

  - 公钥基础结构 (PKI) 使用受信任的证书颁发机构 (CA) 颁发的证书来对服务器进行身份验证，并确保数据完整性。

  - 传输层安全性 (TLS)、HTTPS over SSL (HTTPS) 和相互 TLS (MTLS) 可实现终结点身份验证和 IM 加密。点对点音频、视频和应用程序共享流使用安全实时传输协议 (SRTP) 进行加密。

  - 用于用户身份验证的行业标准协议，如果可能。

  - Windows PowerShell 提供默认启用的安全功能，这样用户便无法轻松或在不知情的情况下运行脚本。

这些基本安全要素共同定义受信任用户、服务器、连接和操作，从而帮助确保建立安全的 Lync Server 2013 基础。

## 本部分内容

本节中的主题介绍以上每个基本要素如何协同工作以增强 Lync Server 基础结构的安全性。

  - [Lync Server 2013 的 Active Directory 域服务](lync-server-2013-active-directory-domain-services-for-lync-server.md)

  - [Lync Server 2013 的基于角色的访问控制 (RBAC)](lync-server-2013-role-based-access-control-rbac.md)

  - [Lync Server 2013 的公钥基础结构](lync-server-2013-public-key-infrastructure.md)

  - [Lync Server 2013 的 TLS 和 MTLS](lync-server-2013-tls-and-mtls.md)

  - [Lync Server 2013 加密](lync-server-2013-encryption.md)

  - [Lync Server 2013 的用户和客户端身份验证](lync-server-2013-user-and-client-authentication.md)

  - [Windows PowerShell 和 Lync Server 2013 管理工具](lync-server-2013-windows-powershell-and-lync-server-management-tools.md)

