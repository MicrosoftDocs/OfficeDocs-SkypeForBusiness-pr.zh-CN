---
title: 删除 Skype for Business Server 中的会议策略
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 497e6ca0-7a49-4f3e-9804-14414cf87b57
description: 摘要：了解如何在 Skype for Business Server 中删除会议策略。
ms.openlocfilehash: eedb0b3676f0cc046e6096dca2cb1ec5ced5d6ec
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828192"
---
# <a name="delete-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="626aa-103">删除 Skype for Business Server 中的会议策略</span><span class="sxs-lookup"><span data-stu-id="626aa-103">Delete conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="626aa-104">**摘要：** 了解如何删除 Skype for Business Server 中的会议策略。</span><span class="sxs-lookup"><span data-stu-id="626aa-104">**Summary:** Learn how to delete conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="626aa-105">可以使用 Skype for Business Server 控制面板或 Skype for Business Server 命令行管理程序删除会议策略。</span><span class="sxs-lookup"><span data-stu-id="626aa-105">You can delete conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="626aa-106">使用 Skype for Business Server 控制面板删除会议策略</span><span class="sxs-lookup"><span data-stu-id="626aa-106">Delete conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="626aa-107">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="626aa-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="626aa-108">打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="626aa-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="626aa-109">在左侧导航栏中，单击 **"会议"，** 然后单击 **"会议策略"。**</span><span class="sxs-lookup"><span data-stu-id="626aa-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="626aa-110">在会议策略列表中，单击要删除的站点或用户策略，单击"编辑"，然后单击"删除 **"。**</span><span class="sxs-lookup"><span data-stu-id="626aa-110">In the list of conferencing policies, click the site or user policy that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="626aa-111">使用 Skype for Business Server 命令行管理程序删除会议策略</span><span class="sxs-lookup"><span data-stu-id="626aa-111">Delete conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="626aa-112">若要删除会议策略，请使用 **Remove-CsConferencingPolicy** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="626aa-112">To delete conferencing policies, use the **Remove-CsConferencingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="626aa-113">以下命令删除 Identity 为 RedmondConferencingPolicy 的会议策略：</span><span class="sxs-lookup"><span data-stu-id="626aa-113">The following command removes the conferencing policy with the Identity RedmondConferencingPolicy:</span></span>
  
```PowerShell
Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"
```

<span data-ttu-id="626aa-114">下一个命令将删除允许外部用户录制会议的任何会议策略：</span><span class="sxs-lookup"><span data-stu-id="626aa-114">The next command deletes any conferencing policies that allow external users to record the conference:</span></span>
  
```PowerShell
Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy
```

<span data-ttu-id="626aa-115">有关详细信息，包括完整语法和参数列表，请参阅 [Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="626aa-115">For more information, including complete syntax and a list of parameters, see [Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps).</span></span>
  

