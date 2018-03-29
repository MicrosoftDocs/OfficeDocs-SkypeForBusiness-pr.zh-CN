---
title: 在 Skype for Business Server 2015 中向用户应用存档策略
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bebd45d1-93c3-4e80-8933-755b699b2209
description: 摘要： 了解如何为业务服务器 2015年到 Skype 的用户分配的存档策略。
ms.openlocfilehash: fc9811aa57a1ba397dedce325f03ea2d77e4413b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="apply-an-archiving-policy-to-users-in-skype-for-business-server-2015"></a><span data-ttu-id="9ca1e-103">在 Skype for Business Server 2015 中向用户应用存档策略</span><span class="sxs-lookup"><span data-stu-id="9ca1e-103">Apply an archiving policy to users in Skype for Business Server 2015</span></span>

<span data-ttu-id="9ca1e-104">**摘要：**了解如何为业务服务器 2015年到 Skype 的用户分配的存档策略。</span><span class="sxs-lookup"><span data-stu-id="9ca1e-104">**Summary:** Learn how to assign an archiving policy to users in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="9ca1e-105">如果您已创建了一个或多个存档的用户的用户策略的业务服务器 2015年驻留在 Skype 上，可以实现通过将合适的策略应用到这些用户或用户组对特定用户存档支持。</span><span class="sxs-lookup"><span data-stu-id="9ca1e-105">If you have created one or more user policies for archiving for users homed on Skype for Business Server 2015, you can implement archiving support for specific users by applying the appropriate policies to those users or user groups.</span></span> <span data-ttu-id="9ca1e-106">例如，如果您创建的策略来支持内部通信存档，可以将其应用到至少一个用户或用户组，以支持用户的 Skype 业务服务器 2015年通信存档。</span><span class="sxs-lookup"><span data-stu-id="9ca1e-106">For example, if you create a policy to support archiving of internal communications, you can apply it to at least one user or user group to support archiving of the user's Skype for Business Server 2015 communications.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9ca1e-107">如果您启用 Microsoft Exchange 集成您的部署 Exchange 的就地保存策略控制是否驻留在 Exchange 的用户启用存档和保留在原位上放有自己的邮箱。</span><span class="sxs-lookup"><span data-stu-id="9ca1e-107">If you enabled Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="9ca1e-108">有关详细信息，请参阅[规划业务服务器 2015年的 Skype 在归档](../../plan-your-deployment/archiving/archiving.md)和[具有的业务服务器 2015 Skype 的 Exchange 存储配置集成](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md)。</span><span class="sxs-lookup"><span data-stu-id="9ca1e-108">For details, see [Plan for archiving in Skype for Business Server 2015](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype for Business Server 2015](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span></span> 
  
## <a name="apply-a-user-policy-by-using-the-control-panel"></a><span data-ttu-id="9ca1e-109">使用控制面板应用用户策略</span><span class="sxs-lookup"><span data-stu-id="9ca1e-109">Apply a user policy by using the Control Panel</span></span>

<span data-ttu-id="9ca1e-110">使用控制面板应用用户策略：</span><span class="sxs-lookup"><span data-stu-id="9ca1e-110">To apply a user policy by using the Control Panel:</span></span>
  
1. <span data-ttu-id="9ca1e-111">使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="9ca1e-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="9ca1e-112">打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。</span><span class="sxs-lookup"><span data-stu-id="9ca1e-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="9ca1e-113">在左侧导航栏中，单击“**用户**”，然后搜索要配置的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="9ca1e-113">In the left navigation bar, click **Users**, and then search for the user account that you want to configure.</span></span> 
    
4. <span data-ttu-id="9ca1e-114">在列出搜索结果的表中，单击相应的用户帐户，再单击“**编辑**”，然后单击“**显示详细信息**”。</span><span class="sxs-lookup"><span data-stu-id="9ca1e-114">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="9ca1e-115">在**编辑 Lync 服务器用户****存档策略**下，选择您要应用的存档用户策略。</span><span class="sxs-lookup"><span data-stu-id="9ca1e-115">In **Edit Lync Server User** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9ca1e-116">**\<自动\>**设置应用默认服务器安装设置。</span><span class="sxs-lookup"><span data-stu-id="9ca1e-116">The **\<Automatic\>** settings apply the default server installation settings.</span></span> <span data-ttu-id="9ca1e-117">服务器将自动应用这些设置。</span><span class="sxs-lookup"><span data-stu-id="9ca1e-117">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="9ca1e-118">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="9ca1e-118">Click **Commit**.</span></span>
    
## <a name="apply-a-user-policy-by-using-windows-powershell"></a><span data-ttu-id="9ca1e-119">通过使用 Windows PowerShell 应用用户策略</span><span class="sxs-lookup"><span data-stu-id="9ca1e-119">Apply a user policy by using Windows PowerShell</span></span>

<span data-ttu-id="9ca1e-120">您还可以通过使用 Windows PowerShell**授予 CsArchivingPolicy** cmdlet 应用用户策略。</span><span class="sxs-lookup"><span data-stu-id="9ca1e-120">You can also apply a user policy by using the Windows PowerShell **Grant-CsArchivingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="9ca1e-121">以下命令向用户 Ken Myer 分配每用户存档策略 RedmondArchivingPolicy。</span><span class="sxs-lookup"><span data-stu-id="9ca1e-121">The following command assigns the per-user archiving policy RedmondArchivingPolicy to the user Ken Myer.</span></span>
  
```
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"
```

<span data-ttu-id="9ca1e-122">此命令将每个用户存档策略 RedmondArchivingPolicy 对所有用户谁具有帐户穴上注册池 atl-cs-001.contoso.com。在此命令中使用该筛选器参数的详细信息，请参阅[获取 CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet 文档。</span><span class="sxs-lookup"><span data-stu-id="9ca1e-122">This command assigns the per-user archiving policy RedmondArchivingPolicy to all users who have accounts homed on the Registrar pool atl-cs-001.contoso.com. For details about the Filter parameter used in this command, see the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet documentation.</span></span>
  
```
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.contoso.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"

```

<span data-ttu-id="9ca1e-p104">以下命令可删除之前已分配给 Ken Myer 的所有每用户存档策略。在删除每用户策略后，将自动使用全局策略或本地站点策略（如果有）管理 Ken Myer。站点策略优先于全局策略。</span><span class="sxs-lookup"><span data-stu-id="9ca1e-p104">The following command removes any per-user archiving policy previously assigned to Ken Myer. After the per-user policy is removed, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
  
```
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null
```

<span data-ttu-id="9ca1e-126">有关详细信息，请参阅[授予 CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps) cmdlet 文档。</span><span class="sxs-lookup"><span data-stu-id="9ca1e-126">For details, see the [Grant-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps) cmdlet documentation.</span></span>
  

