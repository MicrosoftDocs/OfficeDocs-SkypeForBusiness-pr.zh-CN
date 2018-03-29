---
title: 在 Skype for Business Server 2015 中删除现有存档策略
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8b88bed9-2b37-4caf-b119-48688076e06a
description: 摘要： 了解如何删除业务服务器 2015年的 Skype 的存档策略。
ms.openlocfilehash: aeb640cc832bffbded4765e5b6cc931a17365215
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="delete-an-existing-archiving-policy-in-skype-for-business-server-2015"></a><span data-ttu-id="78d31-103">在 Skype for Business Server 2015 中删除现有存档策略</span><span class="sxs-lookup"><span data-stu-id="78d31-103">Delete an existing archiving policy in Skype for Business Server 2015</span></span>

<span data-ttu-id="78d31-104">**摘要：**了解如何删除业务服务器 2015年的 Skype 的存档策略。</span><span class="sxs-lookup"><span data-stu-id="78d31-104">**Summary:** Learn how to delete an archiving policy for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="78d31-105">可以删除用户策略或站点策略，但无法删除全局策略。</span><span class="sxs-lookup"><span data-stu-id="78d31-105">You can delete a user policy or site policy, but not the global policy.</span></span> <span data-ttu-id="78d31-106">如果您删除全局策略，Skype 业务服务器自动将策略重置为默认值。</span><span class="sxs-lookup"><span data-stu-id="78d31-106">If you delete the global policy, Skype for Business Server automatically resets the policy to the default values.</span></span>
  
## <a name="delete-a-policy-by-using-the-control-panel"></a><span data-ttu-id="78d31-107">使用控制面板删除策略</span><span class="sxs-lookup"><span data-stu-id="78d31-107">Delete a policy by using the Control Panel</span></span>

1. <span data-ttu-id="78d31-108">使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="78d31-108">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="78d31-109">打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。</span><span class="sxs-lookup"><span data-stu-id="78d31-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="78d31-110">在左侧导航栏中，单击“**监控和存档**”，然后单击“**存档策略**”。</span><span class="sxs-lookup"><span data-stu-id="78d31-110">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="78d31-111">在存档策略列表中，单击要删除的用户策略或站点策略，再单击“**编辑**”，然后单击“**删除**”。</span><span class="sxs-lookup"><span data-stu-id="78d31-111">In the list of archiving policies, click the user or site policy that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
5. <span data-ttu-id="78d31-112">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="78d31-112">Click **Commit**.</span></span>
    
## <a name="delete-a-policy-by-using-windows-powershell"></a><span data-ttu-id="78d31-113">使用 Windows PowerShell 删除策略</span><span class="sxs-lookup"><span data-stu-id="78d31-113">Delete a policy by using Windows PowerShell</span></span>

<span data-ttu-id="78d31-114">您也可以使用 **Remove-CsArchivingPolicy** cmdlet 删除存档策略。</span><span class="sxs-lookup"><span data-stu-id="78d31-114">You can also delete archiving policies by using the **Remove-CsArchivingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="78d31-p102">例如，以下命令可删除具有 Identity site:Redmond 的策略。删除在站点级别配置的策略后，先前受站点策略管理的用户将自动受到全局存档策略的管理：</span><span class="sxs-lookup"><span data-stu-id="78d31-p102">For example, the following command deletes the policy with the Identity site:Redmond. When a policy configured at the site level is deleted, users previously managed by the site policy will automatically be governed by the global archiving policy instead:</span></span>
  
```
Remove-CsArchivingPolicy -Identity site:Redmond
```

<span data-ttu-id="78d31-117">此命令将删除所有适用于每用户级别的存档策略：</span><span class="sxs-lookup"><span data-stu-id="78d31-117">This command removes all the archiving policies applied to the per-user level:</span></span>
  
```
Get-CsArchivingPolicy -Filter "tag:*" | Remove-CsArchivingPolicy
```

<span data-ttu-id="78d31-118">此命令将删除其中禁用了内部存档的所有存档策略：</span><span class="sxs-lookup"><span data-stu-id="78d31-118">This command removes all the archiving policies where internal archiving has been disabled:</span></span>
  
```
Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False} | Remove-CsArchivingPolicy
```

<span data-ttu-id="78d31-119">有关详细信息，请参阅[删除 CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingpolicy?view=skype-ps) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="78d31-119">For more information, see the help topic for the [Remove-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingpolicy?view=skype-ps) cmdlet.</span></span>