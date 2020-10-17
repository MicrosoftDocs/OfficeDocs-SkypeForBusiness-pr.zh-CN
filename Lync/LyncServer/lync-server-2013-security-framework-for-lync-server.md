---
title: Lync Server 2013： Lync Server 的安全框架
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Security framework for Lync Server 2013
ms:assetid: 01131e28-b38e-40d9-8524-06725b9c6608
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481316(v=OCS.15)
ms:contentKeyID: 59893866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f84b7eaf3476624479d1ecb7c7bb564a4eae8ad9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510439"
---
# <a name="security-framework-for-lync-server-2013"></a>Lync Server 2013 的安全框架

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-11-08_

本节概述了构成 Microsoft Lync Server 2013 安全框架的基本元素。 了解这些元素协同工作的方式对于做出有关保护您的特定 Lync Server 2013 部署的明智决定至关重要。

这些要素如下所示：

  - Active Directory 域服务 (AD DS) 为用户帐户和网络资源提供一个受信任的后端存储库。

  - Role-Based 访问控制 (RBAC) 使您能够在保持高标准安全性的同时委派管理任务。

  - 公钥基础结构 (PKI) 使用受信任的证书颁发机构 (CAs 颁发的证书) 对服务器进行身份验证，并确保数据完整性。

  - 传输层安全性 (TLS)、HTTPS over SSL (HTTPS) 和相互 TLS (MTLS) 可实现终结点身份验证和 IM 加密。点对点音频、视频和应用程序共享流使用安全实时传输协议 (SRTP) 进行加密。

  - 用于用户身份验证的行业标准协议，如果可能。

  - Windows PowerShell 提供默认启用的安全功能，这样用户便无法轻松或在不知情的情况下运行脚本。

这些基本安全元素协同工作以定义受信任的用户、服务器、连接和操作，以帮助确保 Lync Server 2013 的安全基础。

<div>

## <a name="in-this-section"></a>本部分内容

本节中的主题介绍每个基本元素如何工作以增强 Lync Server 基础结构的安全性。

  - [Lync Server 2013 的 Active Directory 域服务](lync-server-2013-active-directory-domain-services-for-lync-server.md)

  - [Lync Server 2013 的基于角色的访问控制 (RBAC) ](lync-server-2013-role-based-access-control-rbac.md)

  - [Lync Server 2013 的公钥基础结构](lync-server-2013-public-key-infrastructure.md)

  - [Lync Server 2013 的 TLS 和 MTLS](lync-server-2013-tls-and-mtls.md)

  - [Lync Server 2013 加密](lync-server-2013-encryption.md)

  - [Lync Server 2013 的用户和客户端身份验证](lync-server-2013-user-and-client-authentication.md)

  - [Windows PowerShell 和 Lync Server 2013 管理工具](lync-server-2013-windows-powershell-and-lync-server-management-tools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

