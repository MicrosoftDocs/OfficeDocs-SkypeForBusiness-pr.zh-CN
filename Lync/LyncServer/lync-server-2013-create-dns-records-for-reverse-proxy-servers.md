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

# <a name="create-dns-records-for-reverse-proxy-servers-in-lync-server-2013"></a><span data-ttu-id="4e258-102">在 Lync Server 2013 中为反向代理服务器创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="4e258-102">Create DNS records for reverse proxy servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4e258-103">_**主题上次修改时间：** 2013-03-29_</span><span class="sxs-lookup"><span data-stu-id="4e258-103">_**Topic Last Modified:** 2013-03-29_</span></span>

<span data-ttu-id="4e258-104">创建外部 DNS A 记录，指向 Microsoft Internet 安全和加速（ISA） Server 2006 SP1、Forefront 威胁管理网关2010服务器或 Internet 信息服务器应用程序请求路由的公共外部接口，如在[Lync Server 2013 中配置用于 edge 支持的 DNS](lync-server-2013-configure-dns-for-edge-support.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="4e258-104">Create external DNS A records that point to the public external interface of your Microsoft Internet Security and Acceleration (ISA) Server 2006 SP1, Forefront Threat Management Gateway 2010 Server or Internet Information Server Application Request Routing, as described in [Configure DNS for edge support in Lync Server 2013](lync-server-2013-configure-dns-for-edge-support.md).</span></span> <span data-ttu-id="4e258-105">对于每个池、Director （或控制器池）和每个简单的 URL，你都需要针对外部 Web 服务 Fqdn 的 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="4e258-105">You need DNS records for the external Web Service FQDNs for each pool, the Director (or Director pool), and each simple URL.</span></span>

<span data-ttu-id="4e258-106">客户端解析到反向代理的最低 DNS 记录，必须创建以下记录：</span><span class="sxs-lookup"><span data-stu-id="4e258-106">The minimum DNS records for client resolution to the reverse proxy, the following records must be created:</span></span>

  - <span data-ttu-id="4e258-107">为控制器和控制器池定义已发布的外部 web 服务（例如， **webdirext.contoso.com**）的主机（A）记录</span><span class="sxs-lookup"><span data-stu-id="4e258-107">Host (A) record(s) that define the published external web services for Directors and Director pools (for example, **webdirext.contoso.com**)</span></span>

  - <span data-ttu-id="4e258-108">定义托管在任何前端池和标准版服务器角色中的外部 web 服务的已发布外部 web 服务的主机（A）记录（例如， **webext.contoso.com**）</span><span class="sxs-lookup"><span data-stu-id="4e258-108">Host (A) record(s) that define the published external web services for external web services hosted on the any Front End pools and Standard Edition server roles (for example, **webext.contoso.com**)</span></span>

  - <span data-ttu-id="4e258-109">简单 Url 的主机（A）记录（例如， **dialin.contoso.com**和**meet.contoso.com**）</span><span class="sxs-lookup"><span data-stu-id="4e258-109">Host (A) records for the Simple URLs (for example, **dialin.contoso.com** and **meet.contoso.com**)</span></span>

  - <span data-ttu-id="4e258-110">Lync 发现外部记录的主机（A）记录，还提供指向所有 Web 应用（包括 Lync Web App、计划程序和移动性（如**lyncdiscover.contoso.com**）的自动发现的指针</span><span class="sxs-lookup"><span data-stu-id="4e258-110">Host (A) record for the Lync Discover External record, and also provides pointer to AutoDiscover for all Web apps, including the Lync Web App, scheduler and Mobility (for example, **lyncdiscover.contoso.com**)</span></span>

  - <span data-ttu-id="4e258-111">Office Web Apps 服务器 URL 的主机（A）记录（例如**officewebapp01.contoso.com**）</span><span class="sxs-lookup"><span data-stu-id="4e258-111">Host (A) records for the Office Web Apps Server URL (for example **officewebapp01.contoso.com**)</span></span>

<span data-ttu-id="4e258-112">有关详细信息，请参阅[Lync Server 2013 中的 "DNS 摘要-反向代理](lync-server-2013-dns-summary-reverse-proxy.md)"。</span><span class="sxs-lookup"><span data-stu-id="4e258-112">For details, see [DNS summary - Reverse proxy in Lync Server 2013](lync-server-2013-dns-summary-reverse-proxy.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

