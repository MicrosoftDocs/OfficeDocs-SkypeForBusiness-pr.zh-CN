---
title: 在 Skype for Business Server 中向用户应用存档策略
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
ms.assetid: bebd45d1-93c3-4e80-8933-755b699b2209
description: 摘要：了解如何在 Skype for Business Server 中向用户分配存档策略。
ms.openlocfilehash: 1fce0dbd0cc7b0595dcf3cd91baeba9ed364e28a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095486"
---
# <a name="apply-an-archiving-policy-to-users-in-skype-for-business-server"></a><span data-ttu-id="a0bd7-103">在 Skype for Business Server 中向用户应用存档策略</span><span class="sxs-lookup"><span data-stu-id="a0bd7-103">Apply an archiving policy to users in Skype for Business Server</span></span>

<span data-ttu-id="a0bd7-104">**摘要：** 了解如何在 Skype for Business Server 中向用户分配存档策略。</span><span class="sxs-lookup"><span data-stu-id="a0bd7-104">**Summary:** Learn how to assign an archiving policy to users in Skype for Business Server.</span></span>
  
<span data-ttu-id="a0bd7-105">如果为 Skype for Business Server 上用户创建了一个或多个存档用户策略，则可以通过向特定用户或用户组应用相应的策略来实现对特定用户的存档支持。</span><span class="sxs-lookup"><span data-stu-id="a0bd7-105">If you have created one or more user policies for archiving for users homed on Skype for Business Server, you can implement archiving support for specific users by applying the appropriate policies to those users or user groups.</span></span> <span data-ttu-id="a0bd7-106">例如，如果创建支持内部通信存档的策略，可以至少将策略应用于一个用户或用户组以支持该用户的 Skype for Business Server 通信的存档。</span><span class="sxs-lookup"><span data-stu-id="a0bd7-106">For example, if you create a policy to support archiving of internal communications, you can apply it to at least one user or user group to support archiving of the user's Skype for Business Server communications.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a0bd7-107">如果为部署启用了 Microsoft Exchange 集成，Exchange In-Place 保留策略将控制是否对位于 Exchange 上且其邮箱置于"保留"状态In-Place存档。</span><span class="sxs-lookup"><span data-stu-id="a0bd7-107">If you enabled Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="a0bd7-108">有关详细信息，请参阅 [在 Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) 中规划存档和为 Skype for Business Server 配置与 Exchange [存储的集成](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md)。</span><span class="sxs-lookup"><span data-stu-id="a0bd7-108">For details, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span></span> 
  
## <a name="apply-a-user-policy-by-using-the-control-panel"></a><span data-ttu-id="a0bd7-109">使用控制面板应用用户策略</span><span class="sxs-lookup"><span data-stu-id="a0bd7-109">Apply a user policy by using the Control Panel</span></span>

<span data-ttu-id="a0bd7-110">若要使用控制面板应用用户策略：</span><span class="sxs-lookup"><span data-stu-id="a0bd7-110">To apply a user policy by using the Control Panel:</span></span>
  
1. <span data-ttu-id="a0bd7-111">使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="a0bd7-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="a0bd7-112">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="a0bd7-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="a0bd7-113">在左侧导航栏中，单击“用户”，然后搜索要配置的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="a0bd7-113">In the left navigation bar, click **Users**, and then search for the user account that you want to configure.</span></span> 
    
4. <span data-ttu-id="a0bd7-114">在列出搜索结果的表中，单击相应的用户帐户，再单击“编辑”，然后单击“显示详细信息”。</span><span class="sxs-lookup"><span data-stu-id="a0bd7-114">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="a0bd7-115">在 **"编辑 Lync Server 用户"** 中的" **存档策略"** 下，选择要应用存档用户策略。</span><span class="sxs-lookup"><span data-stu-id="a0bd7-115">In **Edit Lync Server User** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a0bd7-116">这些设置 **\<Automatic\>** 将应用默认服务器安装设置。</span><span class="sxs-lookup"><span data-stu-id="a0bd7-116">The **\<Automatic\>** settings apply the default server installation settings.</span></span> <span data-ttu-id="a0bd7-117">服务器将自动应用这些设置。</span><span class="sxs-lookup"><span data-stu-id="a0bd7-117">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="a0bd7-118">单击“提交”。</span><span class="sxs-lookup"><span data-stu-id="a0bd7-118">Click **Commit**.</span></span>
    
## <a name="apply-a-user-policy-by-using-windows-powershell"></a><span data-ttu-id="a0bd7-119">使用策略应用用户Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a0bd7-119">Apply a user policy by using Windows PowerShell</span></span>

<span data-ttu-id="a0bd7-120">您还可以使用 **Grant-CsArchivingPolicy** cmdlet Windows PowerShell用户策略。</span><span class="sxs-lookup"><span data-stu-id="a0bd7-120">You can also apply a user policy by using the Windows PowerShell **Grant-CsArchivingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="a0bd7-121">以下命令向用户 Ken Myer 分配每用户存档策略 RedmondArchivingPolicy。</span><span class="sxs-lookup"><span data-stu-id="a0bd7-121">The following command assigns the per-user archiving policy RedmondArchivingPolicy to the user Ken Myer.</span></span>
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"
```

<span data-ttu-id="a0bd7-122">此命令将每用户存档策略 RedmondArchivingPolicy 分配给在注册器池上拥有帐户的所有用户 atl-cs-001.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="a0bd7-122">This command assigns the per-user archiving policy RedmondArchivingPolicy to all users who have accounts homed on the Registrar pool atl-cs-001.contoso.com.</span></span> <span data-ttu-id="a0bd7-123">有关此命令中使用的 Filter 参数的详细信息，请参阅 [Get-CsUser](/powershell/module/skype/get-csuser?view=skype-ps) cmdlet 文档。</span><span class="sxs-lookup"><span data-stu-id="a0bd7-123">For details about the Filter parameter used in this command, see the [Get-CsUser](/powershell/module/skype/get-csuser?view=skype-ps) cmdlet documentation.</span></span>
  
```PowerShell
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.contoso.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"
```

<span data-ttu-id="a0bd7-124">以下命令删除之前分配给 Ken Myer 的任何每用户存档策略。</span><span class="sxs-lookup"><span data-stu-id="a0bd7-124">The following command removes any per-user archiving policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="a0bd7-125">删除每用户策略后，将自动使用全局策略或本地站点策略（如果存在）管理 Ken Myer。</span><span class="sxs-lookup"><span data-stu-id="a0bd7-125">After the per-user policy is removed, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="a0bd7-126">站点策略优先于全局策略。</span><span class="sxs-lookup"><span data-stu-id="a0bd7-126">A site policy takes precedence over the global policy.</span></span>
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null
```

<span data-ttu-id="a0bd7-127">有关详细信息，请参阅 [Grant-CsArchivingPolicy](/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps) cmdlet 文档。</span><span class="sxs-lookup"><span data-stu-id="a0bd7-127">For details, see the [Grant-CsArchivingPolicy](/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps) cmdlet documentation.</span></span>
