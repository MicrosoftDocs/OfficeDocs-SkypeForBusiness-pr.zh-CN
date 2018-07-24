---
title: 向 Skype 中的用户的存档策略应用于业务服务器
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bebd45d1-93c3-4e80-8933-755b699b2209
description: 摘要： 了解如何为业务服务器在 Skype 中向用户分配存档策略。
ms.openlocfilehash: bc54c25a710e4e1cca44fb7311a47101f31ef7df
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20985614"
---
# <a name="apply-an-archiving-policy-to-users-in-skype-for-business-server"></a><span data-ttu-id="73798-103">向 Skype 中的用户的存档策略应用于业务服务器</span><span class="sxs-lookup"><span data-stu-id="73798-103">Apply an archiving policy to users in Skype for Business Server</span></span>

<span data-ttu-id="73798-104">**摘要：** 了解如何为业务服务器在 Skype 中向用户分配存档策略。</span><span class="sxs-lookup"><span data-stu-id="73798-104">**Summary:** Learn how to assign an archiving policy to users in Skype for Business Server.</span></span>
  
<span data-ttu-id="73798-105">如果您已创建了一个或多个用户策略的用户的存档业务服务器驻留在 Skype，您可以通过将适当的策略应用于这些用户或用户组来实现特定用户的存档支持。</span><span class="sxs-lookup"><span data-stu-id="73798-105">If you have created one or more user policies for archiving for users homed on Skype for Business Server, you can implement archiving support for specific users by applying the appropriate policies to those users or user groups.</span></span> <span data-ttu-id="73798-106">例如，如果您创建策略，以支持的内部通信存档，可将其应用于至少一个用户或用户组，以支持存档的用户的 Skype 的业务服务器通信。</span><span class="sxs-lookup"><span data-stu-id="73798-106">For example, if you create a policy to support archiving of internal communications, you can apply it to at least one user or user group to support archiving of the user's Skype for Business Server communications.</span></span>
  
> [!NOTE]
> <span data-ttu-id="73798-107">如果您为您的部署，Exchange 就地保留策略控件上启用 Microsoft Exchange 集成，是否驻留在 Exchange 上的用户启用存档，并且具有其邮箱置于就地保留。</span><span class="sxs-lookup"><span data-stu-id="73798-107">If you enabled Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="73798-108">有关详细信息，请参阅[规划存档中的业务服务器 Skype](../../plan-your-deployment/archiving/archiving.md)和[配置与业务服务器 Skype 的 Exchange 存储的集成](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md)。</span><span class="sxs-lookup"><span data-stu-id="73798-108">For details, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span></span> 
  
## <a name="apply-a-user-policy-by-using-the-control-panel"></a><span data-ttu-id="73798-109">使用控制面板应用用户策略</span><span class="sxs-lookup"><span data-stu-id="73798-109">Apply a user policy by using the Control Panel</span></span>

<span data-ttu-id="73798-110">使用控制面板应用用户策略：</span><span class="sxs-lookup"><span data-stu-id="73798-110">To apply a user policy by using the Control Panel:</span></span>
  
1. <span data-ttu-id="73798-111">使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="73798-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="73798-112">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="73798-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="73798-113">在左侧导航栏中，单击“**用户**”，然后搜索要配置的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="73798-113">In the left navigation bar, click **Users**, and then search for the user account that you want to configure.</span></span> 
    
4. <span data-ttu-id="73798-114">在列出搜索结果的表中，单击相应的用户帐户，再单击“**编辑**”，然后单击“**显示详细信息**”。</span><span class="sxs-lookup"><span data-stu-id="73798-114">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="73798-115">在**编辑 Lync Server 用户****存档策略**下，选择要应用的存档用户策略。</span><span class="sxs-lookup"><span data-stu-id="73798-115">In **Edit Lync Server User** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="73798-116">**\<自动\>** 设置应用默认服务器安装设置。</span><span class="sxs-lookup"><span data-stu-id="73798-116">The **\<Automatic\>** settings apply the default server installation settings.</span></span> <span data-ttu-id="73798-117">服务器将自动应用这些设置。</span><span class="sxs-lookup"><span data-stu-id="73798-117">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="73798-118">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="73798-118">Click **Commit**.</span></span>
    
## <a name="apply-a-user-policy-by-using-windows-powershell"></a><span data-ttu-id="73798-119">使用 Windows PowerShell 将用户策略应用</span><span class="sxs-lookup"><span data-stu-id="73798-119">Apply a user policy by using Windows PowerShell</span></span>

<span data-ttu-id="73798-120">您还可以使用 Windows PowerShell **Grant-csarchivingpolicy** cmdlet 应用的用户策略。</span><span class="sxs-lookup"><span data-stu-id="73798-120">You can also apply a user policy by using the Windows PowerShell **Grant-CsArchivingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="73798-121">以下命令向用户 Ken Myer 分配每用户存档策略 RedmondArchivingPolicy。</span><span class="sxs-lookup"><span data-stu-id="73798-121">The following command assigns the per-user archiving policy RedmondArchivingPolicy to the user Ken Myer.</span></span>
  
```
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"
```

<span data-ttu-id="73798-122">此命令向帐户驻留在注册器池 atl-cs-001.contoso.com 的所有用户分配每用户存档策略 RedmondArchivingPolicy。</span><span class="sxs-lookup"><span data-stu-id="73798-122">This command assigns the per-user archiving policy RedmondArchivingPolicy to all users who have accounts homed on the Registrar pool atl-cs-001.contoso.com.</span></span> <span data-ttu-id="73798-123">有关此命令中同时使用 Filter 参数的详细信息，请参阅[Get-csuser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet 文档。</span><span class="sxs-lookup"><span data-stu-id="73798-123">For details about the Filter parameter used in this command, see the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet documentation.</span></span>
  
```
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.contoso.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"
```

<span data-ttu-id="73798-p105">以下命令可删除之前已分配给 Ken Myer 的所有每用户存档策略。在删除每用户策略后，将自动使用全局策略或本地站点策略（如果有）管理 Ken Myer。站点策略优先于全局策略。</span><span class="sxs-lookup"><span data-stu-id="73798-p105">The following command removes any per-user archiving policy previously assigned to Ken Myer. After the per-user policy is removed, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
  
```
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null
```

<span data-ttu-id="73798-127">有关详细信息，请参阅[Grant-csarchivingpolicy](https://docs.microsoft.com/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps) cmdlet 文档。</span><span class="sxs-lookup"><span data-stu-id="73798-127">For details, see the [Grant-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps) cmdlet documentation.</span></span>
  

