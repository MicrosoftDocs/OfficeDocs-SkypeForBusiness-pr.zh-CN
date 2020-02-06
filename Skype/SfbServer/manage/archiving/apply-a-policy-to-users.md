---
title: 将存档策略应用于 Skype for Business 服务器中的用户
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: bebd45d1-93c3-4e80-8933-755b699b2209
description: 摘要：了解如何为 Skype for Business Server 中的用户分配存档策略。
ms.openlocfilehash: 7be62aaf5b2b70108cb67a36559b242377d26117
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819004"
---
# <a name="apply-an-archiving-policy-to-users-in-skype-for-business-server"></a><span data-ttu-id="5ab0e-103">将存档策略应用于 Skype for Business 服务器中的用户</span><span class="sxs-lookup"><span data-stu-id="5ab0e-103">Apply an archiving policy to users in Skype for Business Server</span></span>

<span data-ttu-id="5ab0e-104">**摘要：** 了解如何为 Skype for Business Server 中的用户分配存档策略。</span><span class="sxs-lookup"><span data-stu-id="5ab0e-104">**Summary:** Learn how to assign an archiving policy to users in Skype for Business Server.</span></span>
  
<span data-ttu-id="5ab0e-105">如果已为驻留在 Skype for business Server 上的用户创建了一个或多个用户策略，则可以通过向这些用户或用户组应用相应的策略来实现对特定用户的存档支持。</span><span class="sxs-lookup"><span data-stu-id="5ab0e-105">If you have created one or more user policies for archiving for users homed on Skype for Business Server, you can implement archiving support for specific users by applying the appropriate policies to those users or user groups.</span></span> <span data-ttu-id="5ab0e-106">例如，如果创建了支持内部通信存档的策略，则可以将其应用到至少一个用户或用户组以支持用户的 Skype for Business 服务器通信的存档。</span><span class="sxs-lookup"><span data-stu-id="5ab0e-106">For example, if you create a policy to support archiving of internal communications, you can apply it to at least one user or user group to support archiving of the user's Skype for Business Server communications.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5ab0e-107">如果为你的部署启用了 Microsoft Exchange 集成，则 Exchange 就地保留策略控制是否为托管在 Exchange 上的用户启用存档，并将其邮箱置于原地保留。</span><span class="sxs-lookup"><span data-stu-id="5ab0e-107">If you enabled Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="5ab0e-108">有关详细信息，请参阅[在 skype for Business 服务器中规划存档](../../plan-your-deployment/archiving/archiving.md)和[配置与 Skype for Business 服务器的 Exchange 存储的集成](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md)。</span><span class="sxs-lookup"><span data-stu-id="5ab0e-108">For details, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span></span> 
  
## <a name="apply-a-user-policy-by-using-the-control-panel"></a><span data-ttu-id="5ab0e-109">使用控制面板应用用户策略</span><span class="sxs-lookup"><span data-stu-id="5ab0e-109">Apply a user policy by using the Control Panel</span></span>

<span data-ttu-id="5ab0e-110">使用控制面板应用用户策略：</span><span class="sxs-lookup"><span data-stu-id="5ab0e-110">To apply a user policy by using the Control Panel:</span></span>
  
1. <span data-ttu-id="5ab0e-111">使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="5ab0e-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="5ab0e-112">打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="5ab0e-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="5ab0e-113">在左侧导航栏中，单击“**用户**”，然后搜索要配置的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="5ab0e-113">In the left navigation bar, click **Users**, and then search for the user account that you want to configure.</span></span> 
    
4. <span data-ttu-id="5ab0e-114">在列出搜索结果的表中，单击相应的用户帐户，再单击“**编辑**”，然后单击“**显示详细信息**”。</span><span class="sxs-lookup"><span data-stu-id="5ab0e-114">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="5ab0e-115">在 "在**存档策略**中**编辑 Lync 服务器用户**" 下，选择要应用的存档用户策略。</span><span class="sxs-lookup"><span data-stu-id="5ab0e-115">In **Edit Lync Server User** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5ab0e-116">" \*\* \<自动\> \*\*设置" 应用默认服务器安装设置。</span><span class="sxs-lookup"><span data-stu-id="5ab0e-116">The **\<Automatic\>** settings apply the default server installation settings.</span></span> <span data-ttu-id="5ab0e-117">服务器将自动应用这些设置。</span><span class="sxs-lookup"><span data-stu-id="5ab0e-117">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="5ab0e-118">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="5ab0e-118">Click **Commit**.</span></span>
    
## <a name="apply-a-user-policy-by-using-windows-powershell"></a><span data-ttu-id="5ab0e-119">使用 Windows PowerShell 应用用户策略</span><span class="sxs-lookup"><span data-stu-id="5ab0e-119">Apply a user policy by using Windows PowerShell</span></span>

<span data-ttu-id="5ab0e-120">你还可以使用 Windows PowerShell**授权 CsArchivingPolicy** cmdlet 应用用户策略。</span><span class="sxs-lookup"><span data-stu-id="5ab0e-120">You can also apply a user policy by using the Windows PowerShell **Grant-CsArchivingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="5ab0e-121">以下命令向用户 Ken Myer 分配每用户存档策略 RedmondArchivingPolicy。</span><span class="sxs-lookup"><span data-stu-id="5ab0e-121">The following command assigns the per-user archiving policy RedmondArchivingPolicy to the user Ken Myer.</span></span>
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"
```

<span data-ttu-id="5ab0e-122">此命令向帐户驻留在注册器池 atl-cs-001.contoso.com 的所有用户分配每用户存档策略 RedmondArchivingPolicy。</span><span class="sxs-lookup"><span data-stu-id="5ab0e-122">This command assigns the per-user archiving policy RedmondArchivingPolicy to all users who have accounts homed on the Registrar pool atl-cs-001.contoso.com.</span></span> <span data-ttu-id="5ab0e-123">有关此命令中使用的筛选器参数的详细信息，请参阅[move-csuser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet 文档。</span><span class="sxs-lookup"><span data-stu-id="5ab0e-123">For details about the Filter parameter used in this command, see the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet documentation.</span></span>
  
```PowerShell
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.contoso.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"
```

<span data-ttu-id="5ab0e-p105">以下命令可删除之前已分配给 Ken Myer 的所有每用户存档策略。在删除每用户策略后，将自动使用全局策略或本地站点策略（如果有）管理 Ken Myer。站点策略优先于全局策略。</span><span class="sxs-lookup"><span data-stu-id="5ab0e-p105">The following command removes any per-user archiving policy previously assigned to Ken Myer. After the per-user policy is removed, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null
```

<span data-ttu-id="5ab0e-127">有关详细信息，请参阅[CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps) cmdlet 文档。</span><span class="sxs-lookup"><span data-stu-id="5ab0e-127">For details, see the [Grant-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps) cmdlet documentation.</span></span>
  

