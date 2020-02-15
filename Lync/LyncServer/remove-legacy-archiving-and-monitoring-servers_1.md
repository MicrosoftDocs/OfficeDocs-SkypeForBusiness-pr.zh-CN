---
title: 删除旧的存档和监控服务器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove legacy Archiving and Monitoring servers
ms:assetid: bca6b419-d5bc-4a46-af42-1dd51b99a26b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205215(v=OCS.15)
ms:contentKeyID: 48185261
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 331a6f24cd2cc176679f628bc54460a6c3c7a718
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008898"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-legacy-archiving-and-monitoring-servers"></a><span data-ttu-id="05fa7-102">删除旧的存档和监控服务器</span><span class="sxs-lookup"><span data-stu-id="05fa7-102">Remove legacy Archiving and Monitoring servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05fa7-103">_**上次修改的主题：** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="05fa7-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="05fa7-104">如果 Office 通信服务器 2007 R2 部署包含存档服务器或监视服务器，则在迁移到 Lync Server 2013 之后，可以从旧环境中删除这些服务器，前提是所有用户都已从任何剩余的Office 通信服务器 2007 R2 池。</span><span class="sxs-lookup"><span data-stu-id="05fa7-104">If your Office Communications Server 2007 R2 deployment contained an Archiving Server or a Monitoring Server, after migrating to Lync Server 2013, those servers can be removed from the legacy environment provided all users have been removed from any remaining Office Communications Server 2007 R2 pools.</span></span> <span data-ttu-id="05fa7-105">可以任意顺序删除存档服务器或监控服务器。</span><span class="sxs-lookup"><span data-stu-id="05fa7-105">You can remove the Archiving Server or Monitoring Server in any sequence.</span></span> <span data-ttu-id="05fa7-106">关键要求是所有用户都已从任何剩余的 Office 通信服务器 2007 R2 池中删除。</span><span class="sxs-lookup"><span data-stu-id="05fa7-106">The key requirement is that all users have been removed from any remaining Office Communications Server 2007 R2 pools.</span></span>

<span data-ttu-id="05fa7-107">您可以按照[第6阶段：将用户移动到试点池](phase-6-move-users-to-the-pilot-pool.md)中所述的过程，将用户从 Office 通信服务器 2007 R2 移动到 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="05fa7-107">You can move users from Office Communications Server 2007 R2 to Lync Server 2013 by following the procedures outlined in [Phase 6: Move users to the pilot pool](phase-6-move-users-to-the-pilot-pool.md).</span></span>

<span data-ttu-id="05fa7-108">确认所有用户都已从任何剩余的池中删除后，请按照中 "删除服务器和服务器角色" 中的过程[http://go.microsoft.com/fwlink/p/?linkId=205887](http://go.microsoft.com/fwlink/p/?linkid=205887)操作。</span><span class="sxs-lookup"><span data-stu-id="05fa7-108">After you have confirmed that all users have been removed from any remaining pools, follow the procedure in "Removing Servers and Server Roles" at [http://go.microsoft.com/fwlink/p/?linkId=205887](http://go.microsoft.com/fwlink/p/?linkid=205887).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

