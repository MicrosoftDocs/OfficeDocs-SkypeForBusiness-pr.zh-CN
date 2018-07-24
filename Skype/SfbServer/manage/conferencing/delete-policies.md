---
title: 删除业务服务器中 Skype 的会议策略
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 497e6ca0-7a49-4f3e-9804-14414cf87b57
description: 摘要： 了解如何删除 Business Server Skype 中的会议策略。
ms.openlocfilehash: 157307fc81bf5e5d0e93bd65b9a513f92b317a68
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "21012621"
---
# <a name="delete-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="3e13c-103">删除业务服务器中 Skype 的会议策略</span><span class="sxs-lookup"><span data-stu-id="3e13c-103">Delete conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="3e13c-104">**摘要：** 了解如何删除 Business Server Skype 中的会议策略。</span><span class="sxs-lookup"><span data-stu-id="3e13c-104">**Summary:** Learn how to delete conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="3e13c-105">可以使用适用于业务 Server Control Panel Skype 或使用 Skype 业务 Server 命令行管理程序中删除会议策略。</span><span class="sxs-lookup"><span data-stu-id="3e13c-105">You can delete conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="3e13c-106">使用适用于业务 Server Control Panel Skype 删除会议策略</span><span class="sxs-lookup"><span data-stu-id="3e13c-106">Delete conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="3e13c-107">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="3e13c-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="3e13c-108">打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="3e13c-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="3e13c-109">在左侧导航栏中，单击“**会议**”，然后单击“**会议策略**”。</span><span class="sxs-lookup"><span data-stu-id="3e13c-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="3e13c-110">在会议策略列表中，单击要删除的站点策略或用户策略，再单击“**编辑**”，然后单击“**删除**”。</span><span class="sxs-lookup"><span data-stu-id="3e13c-110">In the list of conferencing policies, click the site or user policy that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="3e13c-111">使用 Skype 业务 Server 命令行管理程序删除会议策略</span><span class="sxs-lookup"><span data-stu-id="3e13c-111">Delete conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="3e13c-112">若要删除会议策略，请使用 **Remove-CsConferencingPolicy** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3e13c-112">To delete conferencing policies, use the **Remove-CsConferencingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="3e13c-113">以下命令删除 Identity 为 RedmondConferencingPolicy 的会议策略：</span><span class="sxs-lookup"><span data-stu-id="3e13c-113">The following command removes the conferencing policy with the Identity RedmondConferencingPolicy:</span></span>
  
```
Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"
```

<span data-ttu-id="3e13c-114">下一个命令删除允许外部用户记录会议的所有会议策略：</span><span class="sxs-lookup"><span data-stu-id="3e13c-114">The next command deletes any conferencing policies that allow external users to record the conference:</span></span>
  
```
Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy
```

<span data-ttu-id="3e13c-115">有关详细信息，包括完成语法和参数的列表，，请参阅[Remove-csconferencingpolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="3e13c-115">For more information, including complete syntax and a list of parameters, see [Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps).</span></span>
  

