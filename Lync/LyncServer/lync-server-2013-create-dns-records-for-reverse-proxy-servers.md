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
ms.openlocfilehash: 0f85b222688dcefd45030f2c05f7b59ce45ec0ae
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726322"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-dns-records-for-reverse-proxy-servers-in-lync-server-2013"></a>在 Lync Server 2013 中为反向代理服务器创建 DNS 记录

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-03-29_

创建外部 DNS A 记录，指向 Microsoft Internet 安全和加速（ISA） Server 2006 SP1、Forefront 威胁管理网关2010服务器或 Internet 信息服务器应用程序请求路由的公共外部接口，如在[Lync Server 2013 中配置用于 edge 支持的 DNS](lync-server-2013-configure-dns-for-edge-support.md)中所述。 对于每个池、Director （或控制器池）和每个简单的 URL，你都需要针对外部 Web 服务 Fqdn 的 DNS 记录。

客户端解析到反向代理的最低 DNS 记录，必须创建以下记录：

  - 为控制器和控制器池定义已发布的外部 web 服务（例如， **webdirext.contoso.com**）的主机（A）记录

  - 定义托管在任何前端池和标准版服务器角色中的外部 web 服务的已发布外部 web 服务的主机（A）记录（例如， **webext.contoso.com**）

  - 简单 Url 的主机（A）记录（例如， **dialin.contoso.com**和**meet.contoso.com**）

  - Lync 发现外部记录的主机（A）记录，还提供指向所有 Web 应用（包括 Lync Web App、计划程序和移动性（如**lyncdiscover.contoso.com**）的自动发现的指针

  - Office Web Apps 服务器 URL 的主机（A）记录（例如**officewebapp01.contoso.com**）

有关详细信息，请参阅[Lync Server 2013 中的 "DNS 摘要-反向代理](lync-server-2013-dns-summary-reverse-proxy.md)"。

</div>

<span> </span>

</div>

</div>

</div>

