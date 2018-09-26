---
title: 删除旧存档和监控服务器
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 如果旧部署包含存档服务器或监控服务器，在迁移到 Skype for Business Server 2019 后，这些服务器可以删除从旧环境中，前提是已从其余任何旧池中删除所有用户。 您可以按任何顺序中删除存档服务器或监控服务器。 关键要求是确认已从其余任何旧池中删除所有用户。
ms.openlocfilehash: 4de6d9db5538864646f978e9fc33a79b39d4c2a4
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028612"
---
# <a name="remove-legacy-archiving-and-monitoring-servers"></a><span data-ttu-id="ba348-105">删除旧存档和监控服务器</span><span class="sxs-lookup"><span data-stu-id="ba348-105">Remove legacy Archiving and Monitoring servers</span></span>

<span data-ttu-id="ba348-106">如果旧部署包含存档服务器或监控服务器，在迁移到 Skype for Business Server 2019 后，可以从旧环境中删除这些服务器，、 提供已从其余任何旧池中删除所有用户。</span><span class="sxs-lookup"><span data-stu-id="ba348-106">If your legacy deployment contained an Archiving Server or a Monitoring Server, after migrating to Skype for Business Server 2019, those servers can be removed from the legacy environment, provided all users have been removed from any remaining legacy pools.</span></span> <span data-ttu-id="ba348-107">您可以按任何顺序中删除存档服务器或监控服务器。</span><span class="sxs-lookup"><span data-stu-id="ba348-107">You can remove the Archiving Server or Monitoring Server in any sequence.</span></span> <span data-ttu-id="ba348-108">关键要求是确认已从其余任何旧池中删除所有用户。</span><span class="sxs-lookup"><span data-stu-id="ba348-108">The key requirement is that all users have been removed from any remaining legacy pools.</span></span>
  
<span data-ttu-id="ba348-109">您可以将用户移至 Skype 的业务服务器 2019年中概述的过程[第 4 阶段： 将测试用户移至试点池](phase-4-move-test-users-to-the-pilot-pool.md)。</span><span class="sxs-lookup"><span data-stu-id="ba348-109">You can move users to Skype for Business Server 2019 by following the procedures outlined in [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>
  
<span data-ttu-id="ba348-110">后已确认所有用户均已从其余的任何池中，decommision 服务器和删除角色。</span><span class="sxs-lookup"><span data-stu-id="ba348-110">After you have confirmed that all users have been removed from any remaining pools, decommision the server and remove roles.</span></span> <span data-ttu-id="ba348-111">一个日期，但相关，例如，"卸载 Microsoft Lync Server 和删除服务器角色，"可在下载[https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227)。</span><span class="sxs-lookup"><span data-stu-id="ba348-111">A dated, but relevant, example is "Uninstalling Microsoft Lync Server and Removing Server Roles," which can be downloaded at [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227).</span></span>
  

