---
title: Lync Server 2013：为反向代理服务器创建 DNS 记录
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create DNS records for reverse proxy servers
ms:assetid: b3513339-e49b-4665-80f1-b5a1c81a0e2e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429719(v=OCS.15)
ms:contentKeyID: 48185181
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 79c583f5c25ea58f0d1a2ea32246db8eec8f7740
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205638"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-dns-records-for-reverse-proxy-servers-in-lync-server-2013"></a>在 Lync Server 2013 中为反向代理服务器创建 DNS 记录

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-03-29_

创建外部 DNS A 记录，该记录指向 Microsoft Internet 安全和加速（ISA） Server 2006 SP1、Forefront 威胁管理网关2010服务器或 Internet Information Server 应用程序请求路由的公共外部接口，如在[Lync Server 2013 中配置 DNS 以实现边缘支持](lync-server-2013-configure-dns-for-edge-support.md)中所述。 对于每个池、控制器（或控制器池）和每个简单 URL，您都需要针对外部 Web 服务 Fqdn 的 DNS 记录。

反向代理的客户端解析的最少 DNS 记录，必须创建以下记录：

  - 为控制器和控制器池定义已发布的外部 web 服务的主机（A）记录（例如， **webdirext.contoso.com**）

  - 为托管在任何前端池和 Standard Edition 服务器角色上的外部 web 服务定义已发布的外部 web 服务的主机（A）记录（例如， **webext.contoso.com**）

  - 简单 URL 的主机 (A) 记录（例如，**dialin.contoso.com** 和 **meet.contoso.com**）

  - Lync 发现外部记录的主机（A）记录，还提供了指向所有 Web 应用的自动发现的指针，包括 Lync Web App、计划程序和移动（例如， **lyncdiscover.contoso.com**）

  - Office Web Apps Server URL 的主机（A）记录（例如**officewebapp01.contoso.com**）

有关详细信息，请参阅[Lync Server 2013 中的 DNS 摘要-反向代理](lync-server-2013-dns-summary-reverse-proxy.md)。

</div>

<span> </span>

</div>

</div>

</div>

