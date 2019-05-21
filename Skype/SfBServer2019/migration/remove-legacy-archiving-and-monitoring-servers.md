---
title: 删除旧存档和监控服务器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 如果你的旧部署包含存档服务器或监视服务器, 迁移到 Skype for business Server 2019 之后, 可以从旧环境中删除这些服务器, 前提是所有用户都已从任何剩余的旧池删除。 你可以按任意顺序删除存档服务器或监视服务器。 关键要求是所有用户都已从剩余的任何旧版池中删除。
ms.openlocfilehash: 918e04bb42853f0203ae8a2a56db5e640985af99
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34301123"
---
# <a name="remove-legacy-archiving-and-monitoring-servers"></a><span data-ttu-id="4159e-105">删除旧存档和监控服务器</span><span class="sxs-lookup"><span data-stu-id="4159e-105">Remove legacy Archiving and Monitoring servers</span></span>

<span data-ttu-id="4159e-106">如果你的旧部署包含存档服务器或监视服务器, 迁移到 Skype for business Server 2019 之后, 可以从旧环境中删除这些服务器, 前提是所有用户都已从任何剩余的旧池中删除。</span><span class="sxs-lookup"><span data-stu-id="4159e-106">If your legacy deployment contained an Archiving Server or a Monitoring Server, after migrating to Skype for Business Server 2019, those servers can be removed from the legacy environment, provided all users have been removed from any remaining legacy pools.</span></span> <span data-ttu-id="4159e-107">你可以按任意顺序删除存档服务器或监视服务器。</span><span class="sxs-lookup"><span data-stu-id="4159e-107">You can remove the Archiving Server or Monitoring Server in any sequence.</span></span> <span data-ttu-id="4159e-108">关键要求是所有用户都已从剩余的任何旧版池中删除。</span><span class="sxs-lookup"><span data-stu-id="4159e-108">The key requirement is that all users have been removed from any remaining legacy pools.</span></span>
  
<span data-ttu-id="4159e-109">你可以按照第4阶段中概述的过程将用户移动到 Skype for Business Server 2019 [: 将测试用户移动到 "试点" 池](phase-4-move-test-users-to-the-pilot-pool.md)。</span><span class="sxs-lookup"><span data-stu-id="4159e-109">You can move users to Skype for Business Server 2019 by following the procedures outlined in [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>
  
<span data-ttu-id="4159e-110">在确认所有用户都已从任何剩余的池中删除后, decommision 服务器并删除角色。</span><span class="sxs-lookup"><span data-stu-id="4159e-110">After you have confirmed that all users have been removed from any remaining pools, decommision the server and remove roles.</span></span> <span data-ttu-id="4159e-111">日期已过期, 但相关, 示例是 "卸载 Microsoft Lync Server 并删除服务器角色", 可在[https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227)此处下载。</span><span class="sxs-lookup"><span data-stu-id="4159e-111">A dated, but relevant, example is "Uninstalling Microsoft Lync Server and Removing Server Roles," which can be downloaded at [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227).</span></span>
  

