---
title: 在 Skype for Business 服务器中分配会议策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f384d19b-0950-4ec6-9d93-2c5958b83e71
description: '摘要: 了解如何在 Skype for Business Server 中分配会议策略。'
ms.openlocfilehash: acd74262b51000a3f4af5668fb3c9271a8c0978d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34289025"
---
# <a name="assign-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="c7a44-103">在 Skype for Business 服务器中分配会议策略</span><span class="sxs-lookup"><span data-stu-id="c7a44-103">Assign conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="c7a44-104">**摘要:** 了解如何在 Skype for Business Server 中分配会议策略。</span><span class="sxs-lookup"><span data-stu-id="c7a44-104">**Summary:** Learn how to assign conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="c7a44-105">你可以使用 Skype for Business Server Management Shell 和**CsConferencingPolicy** cmdlet 将会议策略分配给用户。</span><span class="sxs-lookup"><span data-stu-id="c7a44-105">You can assign conferencing policies to users by using Skype for Business Server Management Shell and the **Grant-CsConferencingPolicy** cmdlet.</span></span>
  
## <a name="assign-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="c7a44-106">使用 Skype for Business Server 命令行管理程序分配会议策略</span><span class="sxs-lookup"><span data-stu-id="c7a44-106">Assign conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="c7a44-107">在下面的示例中，将策略 SalesConferencingPolicy 分配给 Identity 为 "Ken Myer" 的用户：</span><span class="sxs-lookup"><span data-stu-id="c7a44-107">In the following example, the policy SalesConferencingPolicy is assigned to the user with the Identity "Ken Myer":</span></span>
  
```
Grant-CsConferencingPolicy -identity "Ken Myer" -PolicyName SalesConferencingPolicy
```

<span data-ttu-id="c7a44-p101">在下一个示例中，将会议策略 FinanceConferencingPolicy 分配给 Finance 组织单位中拥有帐户的所有用户。若要将相同策略分配给指定组织单位 (OU) 中的所有用户，应使用 Get-CsUser cmdlet 来检索该 OU 中的所有帐户。在检索完用户帐户后，将该信息通过管道传递到 Grant-CsConferencingPolicy cmdlet，后者会将 FinanceConferencingPolicy 策略分配给集合中的每个用户：</span><span class="sxs-lookup"><span data-stu-id="c7a44-p101">In the next example, the conferencing policy FinanceConferencingPolicy is assigned to all the users who have accounts in the Finance organizational unit. To assign the same policy to all the users in a given organizational unit (OU), the Get-CsUser cmdlet is used to retrieve all the accounts in that OU. After the user accounts have been retrieved, that information is then piped to the Grant-CsConferencingPolicy cmdlet, which assigns the FinanceConferencingPolicy policy to each user in the collection:</span></span>
  
```
Get-CsUser -OU "ou=Finance,dc=litwareinc,dc=com" | Grant-CsConferencingPolicy -PolicyName FinanceConferencingPolicy
```

<span data-ttu-id="c7a44-111">有关详细信息, 包括完整语法和参数列表, 请参阅[Grant-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="c7a44-111">For more information, including complete syntax and a list of parameters, see [Grant-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps).</span></span>
  

