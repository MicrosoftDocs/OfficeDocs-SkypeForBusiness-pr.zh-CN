---
title: 在 Skype for Business Server 中创建新的存档策略
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
ms.assetid: 50c39731-ba2f-49c2-a571-6dc373f6aaeb
description: 摘要：了解如何为 Skype for Business Server 创建新的存档策略。
ms.openlocfilehash: fe3a80708d3810a085f1814e6d16ff3cd4c6057c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095416"
---
# <a name="create-a-new-archiving-policy-in-skype-for-business-server"></a><span data-ttu-id="cb0a9-103">在 Skype for Business Server 中创建新的存档策略</span><span class="sxs-lookup"><span data-stu-id="cb0a9-103">Create a new archiving policy in Skype for Business Server</span></span>

<span data-ttu-id="cb0a9-104">**摘要：** 了解如何为 Skype for Business Server 创建新的存档策略。</span><span class="sxs-lookup"><span data-stu-id="cb0a9-104">**Summary:** Learn how to create a new archiving policy for Skype for Business Server.</span></span>
  
<span data-ttu-id="cb0a9-105">可以使用控制面板或 cmdlet 创建新的存档Windows PowerShell策略。</span><span class="sxs-lookup"><span data-stu-id="cb0a9-105">You can create new archiving policies by using the Control Panel or by using Windows PowerShell cmdlets.</span></span>
  
## <a name="create-a-new-archiving-policy-by-using-the-control-panel"></a><span data-ttu-id="cb0a9-106">使用控制面板创建新的存档策略</span><span class="sxs-lookup"><span data-stu-id="cb0a9-106">Create a new archiving policy by using the Control Panel</span></span>

<span data-ttu-id="cb0a9-107">若要使用控制面板创建新的存档策略，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="cb0a9-107">To create a new archiving policy by using the Control Panel:</span></span>
  
1. <span data-ttu-id="cb0a9-108">使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="cb0a9-108">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="cb0a9-109">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="cb0a9-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="cb0a9-110">在左侧导航栏中，单击 **“监控和存档”**，然后单击 **“存档策略”**。</span><span class="sxs-lookup"><span data-stu-id="cb0a9-110">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="cb0a9-111">单击“新建”，然后执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="cb0a9-111">Click **New**, and then do one of the following:</span></span> 
    
   - <span data-ttu-id="cb0a9-112">要创建站点级别的存档策略，请单击"站点策略"，然后在"选择站点"中单击要应用该策略的站点。</span><span class="sxs-lookup"><span data-stu-id="cb0a9-112">To create a site-level archiving policy, click **Site policy**, and then, in **Select a site**, click the site to which the policy is to be applied.</span></span>
    
   - <span data-ttu-id="cb0a9-113">若要创建用户级别的存档策略，请单击“用户策略”。</span><span class="sxs-lookup"><span data-stu-id="cb0a9-113">To create a user-level archiving policy, click **User policy**.</span></span>
    
5. <span data-ttu-id="cb0a9-114">在“新建存档策略”中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="cb0a9-114">In **New Archiving Policy**, do the following:</span></span>
    
   - <span data-ttu-id="cb0a9-115">在“名称”中，指定新策略的名称（例如，externalContoso）。</span><span class="sxs-lookup"><span data-stu-id="cb0a9-115">In **Name**, specify a name for the new policy (for example, externalContoso).</span></span>
    
   - <span data-ttu-id="cb0a9-116">在“说明”中，提供有关该策略内容的详细信息（例如，Contoso 的外部用户存档策略）。</span><span class="sxs-lookup"><span data-stu-id="cb0a9-116">In **Description**, provide details about what the policy is (for example, External user archiving policy for Contoso).</span></span>
    
   - <span data-ttu-id="cb0a9-117">要控制内部用户通信的存档，请选中或清除“存档内部通信”复选框。</span><span class="sxs-lookup"><span data-stu-id="cb0a9-117">To control archiving of communications with internal users, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="cb0a9-118">要控制外部用户通信的存档，请选中或清除“存档外部通信”复选框。</span><span class="sxs-lookup"><span data-stu-id="cb0a9-118">To control archiving of communications with external users, select or clear the **Archive external communications** check box.</span></span>
    
6. <span data-ttu-id="cb0a9-119">单击“提交”。</span><span class="sxs-lookup"><span data-stu-id="cb0a9-119">Click **Commit**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="cb0a9-120">用户策略的设置仅适用于要应用该策略的特定用户和用户组。</span><span class="sxs-lookup"><span data-stu-id="cb0a9-120">The settings of a user policy only apply to the specific users and user groups to which you apply the policy.</span></span> <span data-ttu-id="cb0a9-121">有关详细信息，请参阅 [在 Skype for Business Server 中向用户应用存档策略](apply-a-policy-to-users.md)。</span><span class="sxs-lookup"><span data-stu-id="cb0a9-121">For details, see [Apply an archiving policy to users in Skype for Business Server](apply-a-policy-to-users.md).</span></span> 
  
## <a name="create-a-new-archiving-policy-by-using-windows-powershell"></a><span data-ttu-id="cb0a9-122">使用策略创建新的存档Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cb0a9-122">Create a new archiving policy by using Windows PowerShell</span></span>

<span data-ttu-id="cb0a9-123">您还可以使用 **New-CsArchivingPolicy** cmdlet Windows PowerShell新的存档策略。</span><span class="sxs-lookup"><span data-stu-id="cb0a9-123">You can also create new archiving policies by using the Windows PowerShell **New-CsArchivingPolicy** cmdlet.</span></span> <span data-ttu-id="cb0a9-124">有关详细信息，请参阅 [New-CsArchivingPolicy](/powershell/module/skype/new-csarchivingpolicy?view=skype-ps) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="cb0a9-124">For more information, see the help topic for the [New-CsArchivingPolicy](/powershell/module/skype/new-csarchivingpolicy?view=skype-ps) cmdlet.</span></span>
  
### <a name="to-create-a-new-archiving-policy-at-the-site-level"></a><span data-ttu-id="cb0a9-125">在站点级别创建新的存档策略</span><span class="sxs-lookup"><span data-stu-id="cb0a9-125">To create a new archiving policy at the site level</span></span>

<span data-ttu-id="cb0a9-126">此命令可为 Redmond 站点创建新的存档策略：</span><span class="sxs-lookup"><span data-stu-id="cb0a9-126">This command creates a new archiving policy for the Redmond site:</span></span>
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond"
```

### <a name="to-create-a-new-archiving-policy-at-the-per-user-level"></a><span data-ttu-id="cb0a9-127">在每个用户级别创建新的存档策略</span><span class="sxs-lookup"><span data-stu-id="cb0a9-127">To create a new archiving policy at the per-user level</span></span>

<span data-ttu-id="cb0a9-128">若要在每个用户级别创建新的存档策略，只需在创建策略时指定唯一标识：</span><span class="sxs-lookup"><span data-stu-id="cb0a9-128">To create a new archiving policy at the per-user level, simply specify a unique Identity when creating the policy:</span></span>
  
```PowerShell
New-CsArchivingPolicy -Identity "RedmondArchivingPolicy"
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-internal-communication-sessions"></a><span data-ttu-id="cb0a9-129">创建启用内部通信会话存档的新存档策略</span><span class="sxs-lookup"><span data-stu-id="cb0a9-129">To create a new archiving policy that enables archiving of internal communication sessions</span></span>

<span data-ttu-id="cb0a9-130">由于前面的命令中未指定参数（必需的 Identity 参数之外），因此新策略将对其所有属性使用默认值。</span><span class="sxs-lookup"><span data-stu-id="cb0a9-130">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding commands, the new policies will use the default values for all their properties.</span></span> <span data-ttu-id="cb0a9-131">若要创建使用其他属性值的策略，只需包括适当的参数和参数值。</span><span class="sxs-lookup"><span data-stu-id="cb0a9-131">To create policies that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="cb0a9-132">例如，以下命令可创建允许对内部即时消息会话进行存档的存档策略：</span><span class="sxs-lookup"><span data-stu-id="cb0a9-132">For example, the following command creates an archiving policy that permits archiving of internal instant messaging sessions:</span></span> 
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-both-internal-and-external-communication-sessions"></a><span data-ttu-id="cb0a9-133">创建启用内部和外部通信会话存档的新存档策略</span><span class="sxs-lookup"><span data-stu-id="cb0a9-133">To create a new archiving policy that enables archiving of both internal and external communication sessions</span></span>

<span data-ttu-id="cb0a9-134">可以通过包含多个参数来修改多个属性值。</span><span class="sxs-lookup"><span data-stu-id="cb0a9-134">Multiple property values can be modified by including multiple parameters.</span></span> <span data-ttu-id="cb0a9-135">例如，此命令将新策略配置为同时存档内部和外部即时消息会话：</span><span class="sxs-lookup"><span data-stu-id="cb0a9-135">For example, this command configures the new policy to archive both internal and external instant messaging sessions:</span></span>
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True -ArchiveExternal $True
```