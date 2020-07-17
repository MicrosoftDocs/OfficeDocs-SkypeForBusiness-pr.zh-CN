---
title: 删除旧存档和监控服务器
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove legacy Archiving and Monitoring servers
ms:assetid: befa586b-615c-496e-996e-395a6e36a826
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205221(v=OCS.15)
ms:contentKeyID: 48185278
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d77292fe478fa95deec50df84a78907af4290e3
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757103"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-legacy-archiving-and-monitoring-servers"></a><span data-ttu-id="917e9-102">删除旧存档和监控服务器</span><span class="sxs-lookup"><span data-stu-id="917e9-102">Remove legacy Archiving and Monitoring servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="917e9-103">_**上次修改的主题：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="917e9-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="917e9-104">如果您的旧部署包含存档服务器或监视服务器，则在迁移到 Lync Server 2013 之后，可以从旧环境中删除这些服务器，前提是所有用户都已从任何剩余的旧池中删除。</span><span class="sxs-lookup"><span data-stu-id="917e9-104">If your legacy deployment contained an Archiving Server or a Monitoring Server, after migrating to Lync Server 2013, those servers can be removed from the legacy environment provided all users have been removed from any remaining legacy pools.</span></span> <span data-ttu-id="917e9-105">可以任意顺序删除存档服务器或监控服务器。</span><span class="sxs-lookup"><span data-stu-id="917e9-105">You can remove the Archiving Server or Monitoring Server in any sequence.</span></span> <span data-ttu-id="917e9-106">关键要求是所有用户均已从其余任何旧池中删除。</span><span class="sxs-lookup"><span data-stu-id="917e9-106">The key requirement is that all users have been removed from any remaining legacy pools.</span></span>

<span data-ttu-id="917e9-107">您可以按照[第4阶段：将测试用户移动到试点池](phase-4-move-test-users-to-the-pilot-pool.md)中所述的过程，将用户从 lync server 2010 移动到 Lync server 2013。</span><span class="sxs-lookup"><span data-stu-id="917e9-107">You can move users from Lync Server 2010 to Lync Server 2013 by following the procedures outlined in [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>

<span data-ttu-id="917e9-108">确认所有用户都已从任何剩余的池中删除后，请按照 "卸载 Microsoft Lync Server 2010 和删除服务器角色" 中的过程操作，该过程可在中下载 [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkid=246227) 。</span><span class="sxs-lookup"><span data-stu-id="917e9-108">After you have confirmed that all users have been removed from any remaining pools, follow the procedure in "Uninstalling Microsoft Lync Server 2010 and Removing Server Roles," which can be downloaded at [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkid=246227).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

