---
title: 在 Skype for Business Server 2015 中删除会议策略
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 497e6ca0-7a49-4f3e-9804-14414cf87b57
description: 摘要： 了解如何删除业务服务器 2015 Skype 会议策略。
ms.openlocfilehash: 783e2ef4c1bc0732fd93949427cea21c5ca165ea
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="delete-conferencing-policies-in-skype-for-business-server-2015"></a><span data-ttu-id="24c25-103">在 Skype for Business Server 2015 中删除会议策略</span><span class="sxs-lookup"><span data-stu-id="24c25-103">Delete conferencing policies in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="24c25-104">**摘要：**了解如何删除业务服务器 2015 Skype 会议策略。</span><span class="sxs-lookup"><span data-stu-id="24c25-104">**Summary:** Learn how to delete conferencing policies in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="24c25-105">通过 Skype 业务服务器控件面板或通过 Skype 业务服务器管理外壳，您可以删除会议策略。</span><span class="sxs-lookup"><span data-stu-id="24c25-105">You can delete conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="24c25-106">通过 Skype 业务服务器控件面板中删除会议策略</span><span class="sxs-lookup"><span data-stu-id="24c25-106">Delete conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="24c25-107">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="24c25-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="24c25-108">打开 Skype 业务服务器的控制面板。</span><span class="sxs-lookup"><span data-stu-id="24c25-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="24c25-109">在左侧导航栏中，单击“**会议**”，然后单击“**会议策略**”。</span><span class="sxs-lookup"><span data-stu-id="24c25-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="24c25-110">在会议策略列表中，单击要删除的站点策略或用户策略，再单击“**编辑**”，然后单击“**删除**”。</span><span class="sxs-lookup"><span data-stu-id="24c25-110">In the list of conferencing policies, click the site or user policy that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="24c25-111">通过 Skype 业务服务器管理外壳程序删除会议策略</span><span class="sxs-lookup"><span data-stu-id="24c25-111">Delete conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="24c25-112">若要删除会议策略，请使用 **Remove-CsConferencingPolicy** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="24c25-112">To delete conferencing policies, use the **Remove-CsConferencingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="24c25-113">以下命令删除 Identity 为 RedmondConferencingPolicy 的会议策略：</span><span class="sxs-lookup"><span data-stu-id="24c25-113">The following command removes the conferencing policy with the Identity RedmondConferencingPolicy:</span></span>
  
```
Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"
```

<span data-ttu-id="24c25-114">下一个命令删除允许外部用户记录会议的所有会议策略：</span><span class="sxs-lookup"><span data-stu-id="24c25-114">The next command deletes any conferencing policies that allow external users to record the conference:</span></span>
  
```
Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy
```

<span data-ttu-id="24c25-115">包括完整语法和参数的列表的详细信息，请参阅[删除 CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="24c25-115">For more information, including complete syntax and a list of parameters, see [Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps).</span></span>
  

