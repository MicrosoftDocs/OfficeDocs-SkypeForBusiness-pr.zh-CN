---
title: 删除旧存档和监控服务器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 如果你的旧部署包含存档服务器或监视服务器，迁移到 Skype for business Server 2019 之后，可以从旧环境中删除这些服务器，前提是所有用户都已从任何剩余的旧池删除。 你可以按任意顺序删除存档服务器或监视服务器。 关键要求是所有用户都已从剩余的任何旧版池中删除。
ms.openlocfilehash: 034d2ad284c0247b19e56e4cd8d751a0cf32ee69
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812990"
---
# <a name="remove-legacy-archiving-and-monitoring-servers"></a><span data-ttu-id="78717-105">删除旧存档和监控服务器</span><span class="sxs-lookup"><span data-stu-id="78717-105">Remove legacy Archiving and Monitoring servers</span></span>

<span data-ttu-id="78717-106">如果你的旧部署包含存档服务器或监视服务器，迁移到 Skype for business Server 2019 之后，可以从旧环境中删除这些服务器，前提是所有用户都已从任何剩余的旧池中删除。</span><span class="sxs-lookup"><span data-stu-id="78717-106">If your legacy deployment contained an Archiving Server or a Monitoring Server, after migrating to Skype for Business Server 2019, those servers can be removed from the legacy environment, provided all users have been removed from any remaining legacy pools.</span></span> <span data-ttu-id="78717-107">你可以按任意顺序删除存档服务器或监视服务器。</span><span class="sxs-lookup"><span data-stu-id="78717-107">You can remove the Archiving Server or Monitoring Server in any sequence.</span></span> <span data-ttu-id="78717-108">关键要求是所有用户都已从剩余的任何旧版池中删除。</span><span class="sxs-lookup"><span data-stu-id="78717-108">The key requirement is that all users have been removed from any remaining legacy pools.</span></span>
  
<span data-ttu-id="78717-109">你可以按照第4阶段中概述的过程将用户移动到 Skype for Business Server 2019 [：将测试用户移动到 "试点" 池](phase-4-move-test-users-to-the-pilot-pool.md)。</span><span class="sxs-lookup"><span data-stu-id="78717-109">You can move users to Skype for Business Server 2019 by following the procedures outlined in [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>
  
<span data-ttu-id="78717-110">在确认所有用户都已从任何剩余的池中删除后，decommision 服务器并删除角色。</span><span class="sxs-lookup"><span data-stu-id="78717-110">After you have confirmed that all users have been removed from any remaining pools, decommision the server and remove roles.</span></span> <span data-ttu-id="78717-111">日期已过期，但相关，示例是 "卸载 Microsoft Lync Server 并删除服务器角色"，可在[https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227)此处下载。</span><span class="sxs-lookup"><span data-stu-id="78717-111">A dated, but relevant, example is "Uninstalling Microsoft Lync Server and Removing Server Roles," which can be downloaded at [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227).</span></span>
  

