---
title: 为业务服务器分配中 Skype 的会议策略
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f384d19b-0950-4ec6-9d93-2c5958b83e71
description: 摘要： 了解如何为业务服务器分配中 Skype 的会议策略。
ms.openlocfilehash: 44e29842fd11d600aa5a692e98b5ddbb72149ade
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32222868"
---
# <a name="assign-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="cd8b8-103">为业务服务器分配中 Skype 的会议策略</span><span class="sxs-lookup"><span data-stu-id="cd8b8-103">Assign conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="cd8b8-104">**摘要：** 了解如何为业务服务器分配中 Skype 的会议策略。</span><span class="sxs-lookup"><span data-stu-id="cd8b8-104">**Summary:** Learn how to assign conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="cd8b8-105">使用 Skype 的业务 Server 命令行管理程序和**Grant-csconferencingpolicy** cmdlet，可以向用户分配会议策略。</span><span class="sxs-lookup"><span data-stu-id="cd8b8-105">You can assign conferencing policies to users by using Skype for Business Server Management Shell and the **Grant-CsConferencingPolicy** cmdlet.</span></span>
  
## <a name="assign-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="cd8b8-106">使用 Skype 业务 Server 命令行管理程序分配会议策略</span><span class="sxs-lookup"><span data-stu-id="cd8b8-106">Assign conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="cd8b8-107">在下面的示例中，将策略 SalesConferencingPolicy 分配给 Identity 为 "Ken Myer" 的用户：</span><span class="sxs-lookup"><span data-stu-id="cd8b8-107">In the following example, the policy SalesConferencingPolicy is assigned to the user with the Identity "Ken Myer":</span></span>
  
```
Grant-CsConferencingPolicy -identity "Ken Myer" -PolicyName SalesConferencingPolicy
```

<span data-ttu-id="cd8b8-p101">在下一个示例中，将会议策略 FinanceConferencingPolicy 分配给 Finance 组织单位中拥有帐户的所有用户。若要将相同策略分配给指定组织单位 (OU) 中的所有用户，应使用 Get-CsUser cmdlet 来检索该 OU 中的所有帐户。在检索完用户帐户后，将该信息通过管道传递到 Grant-CsConferencingPolicy cmdlet，后者会将 FinanceConferencingPolicy 策略分配给集合中的每个用户：</span><span class="sxs-lookup"><span data-stu-id="cd8b8-p101">In the next example, the conferencing policy FinanceConferencingPolicy is assigned to all the users who have accounts in the Finance organizational unit. To assign the same policy to all the users in a given organizational unit (OU), the Get-CsUser cmdlet is used to retrieve all the accounts in that OU. After the user accounts have been retrieved, that information is then piped to the Grant-CsConferencingPolicy cmdlet, which assigns the FinanceConferencingPolicy policy to each user in the collection:</span></span>
  
```
Get-CsUser -OU "ou=Finance,dc=litwareinc,dc=com" | Grant-CsConferencingPolicy -PolicyName FinanceConferencingPolicy
```

<span data-ttu-id="cd8b8-111">有关详细信息，包括完成语法和参数的列表，，请参阅[Grant-csconferencingpolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="cd8b8-111">For more information, including complete syntax and a list of parameters, see [Grant-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps).</span></span>
  

