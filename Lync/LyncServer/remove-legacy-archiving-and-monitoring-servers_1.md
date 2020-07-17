---
title: 删除旧存档和监控服务器
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove legacy Archiving and Monitoring servers
ms:assetid: bca6b419-d5bc-4a46-af42-1dd51b99a26b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205215(v=OCS.15)
ms:contentKeyID: 48185261
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b4f149db04be75cec961478f4382b3e7a333e0a
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757093"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-legacy-archiving-and-monitoring-servers"></a><span data-ttu-id="fcb7c-102">删除旧存档和监控服务器</span><span class="sxs-lookup"><span data-stu-id="fcb7c-102">Remove legacy Archiving and Monitoring servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fcb7c-103">_**上次修改的主题：** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="fcb7c-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="fcb7c-104">如果 Office 通信服务器 2007 R2 部署包含存档服务器或监视服务器，则在迁移到 Lync Server 2013 之后，如果所有用户已从任何剩余的 Office 通信服务器 2007 R2 池中删除，则可以从旧环境中删除这些服务器。</span><span class="sxs-lookup"><span data-stu-id="fcb7c-104">If your Office Communications Server 2007 R2 deployment contained an Archiving Server or a Monitoring Server, after migrating to Lync Server 2013, those servers can be removed from the legacy environment provided all users have been removed from any remaining Office Communications Server 2007 R2 pools.</span></span> <span data-ttu-id="fcb7c-105">可以任意顺序删除存档服务器或监控服务器。</span><span class="sxs-lookup"><span data-stu-id="fcb7c-105">You can remove the Archiving Server or Monitoring Server in any sequence.</span></span> <span data-ttu-id="fcb7c-106">关键要求是所有用户都已从任何剩余的 Office 通信服务器 2007 R2 池中删除。</span><span class="sxs-lookup"><span data-stu-id="fcb7c-106">The key requirement is that all users have been removed from any remaining Office Communications Server 2007 R2 pools.</span></span>

<span data-ttu-id="fcb7c-107">您可以按照[第6阶段：将用户移动到试点池](phase-6-move-users-to-the-pilot-pool.md)中所述的过程，将用户从 Office 通信服务器 2007 R2 移动到 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="fcb7c-107">You can move users from Office Communications Server 2007 R2 to Lync Server 2013 by following the procedures outlined in [Phase 6: Move users to the pilot pool](phase-6-move-users-to-the-pilot-pool.md).</span></span>

<span data-ttu-id="fcb7c-108">确认所有用户都已从任何剩余的池中删除后，请按照中 "删除服务器和服务器角色" 中的过程操作 [https://go.microsoft.com/fwlink/p/?linkId=205887](https://go.microsoft.com/fwlink/p/?linkid=205887) 。</span><span class="sxs-lookup"><span data-stu-id="fcb7c-108">After you have confirmed that all users have been removed from any remaining pools, follow the procedure in "Removing Servers and Server Roles" at [https://go.microsoft.com/fwlink/p/?linkId=205887](https://go.microsoft.com/fwlink/p/?linkid=205887).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

