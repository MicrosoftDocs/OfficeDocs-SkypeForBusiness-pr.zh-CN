---
title: 在 Skype for Business 服务器中创建新的存档策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50c39731-ba2f-49c2-a571-6dc373f6aaeb
description: 摘要：了解如何为 Skype for Business 服务器创建新的存档策略。
ms.openlocfilehash: 8542c31050cf4ca9383c22b39c83b28309d3ea32
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992729"
---
# <a name="create-a-new-archiving-policy-in-skype-for-business-server"></a><span data-ttu-id="c762f-103">在 Skype for Business 服务器中创建新的存档策略</span><span class="sxs-lookup"><span data-stu-id="c762f-103">Create a new archiving policy in Skype for Business Server</span></span>

<span data-ttu-id="c762f-104">**摘要：** 了解如何为 Skype for Business 服务器创建新的存档策略。</span><span class="sxs-lookup"><span data-stu-id="c762f-104">**Summary:** Learn how to create a new archiving policy for Skype for Business Server.</span></span>
  
<span data-ttu-id="c762f-105">您可以使用控制面板或 Windows PowerShell cmdlet 创建新的存档策略。</span><span class="sxs-lookup"><span data-stu-id="c762f-105">You can create new archiving policies by using the Control Panel or by using Windows PowerShell cmdlets.</span></span>
  
## <a name="create-a-new-archiving-policy-by-using-the-control-panel"></a><span data-ttu-id="c762f-106">使用控制面板创建新的存档策略</span><span class="sxs-lookup"><span data-stu-id="c762f-106">Create a new archiving policy by using the Control Panel</span></span>

<span data-ttu-id="c762f-107">要使用控制面板创建新的存档策略：</span><span class="sxs-lookup"><span data-stu-id="c762f-107">To create a new archiving policy by using the Control Panel:</span></span>
  
1. <span data-ttu-id="c762f-108">使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="c762f-108">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="c762f-109">打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="c762f-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="c762f-110">在左侧导航栏中，单击“监控和存档”\*\*\*\*，然后单击“存档策略”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c762f-110">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="c762f-111">单击“**新建**”，然后执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="c762f-111">Click **New**, and then do one of the following:</span></span> 
    
   - <span data-ttu-id="c762f-112">若要创建站点级别的存档策略，请单击“**站点策略**”，然后在“**选择站点**”中，单击要应用该策略的站点。</span><span class="sxs-lookup"><span data-stu-id="c762f-112">To create a site-level archiving policy, click **Site policy**, and then, in **Select a site**, click the site to which the policy is to be applied.</span></span>
    
   - <span data-ttu-id="c762f-113">若要创建用户级别的存档策略，请单击“**用户策略**”。</span><span class="sxs-lookup"><span data-stu-id="c762f-113">To create a user-level archiving policy, click **User policy**.</span></span>
    
5. <span data-ttu-id="c762f-114">在“**新建存档策略**”中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="c762f-114">In **New Archiving Policy**, do the following:</span></span>
    
   - <span data-ttu-id="c762f-115">在“**名称**”中，指定新策略的名称（例如，externalContoso）。</span><span class="sxs-lookup"><span data-stu-id="c762f-115">In **Name**, specify a name for the new policy (for example, externalContoso).</span></span>
    
   - <span data-ttu-id="c762f-116">在“**说明**”中，提供有关该策略内容的详细信息（例如，Contoso 的外部用户存档策略）。</span><span class="sxs-lookup"><span data-stu-id="c762f-116">In **Description**, provide details about what the policy is (for example, External user archiving policy for Contoso).</span></span>
    
   - <span data-ttu-id="c762f-117">要控制内部用户通信的存档，请选中或清除“**存档内部通信**”复选框。</span><span class="sxs-lookup"><span data-stu-id="c762f-117">To control archiving of communications with internal users, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="c762f-118">要控制外部用户通信的存档，请选中或清除“**存档外部通信**”复选框。</span><span class="sxs-lookup"><span data-stu-id="c762f-118">To control archiving of communications with external users, select or clear the **Archive external communications** check box.</span></span>
    
6. <span data-ttu-id="c762f-119">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="c762f-119">Click **Commit**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="c762f-120">用户策略的设置仅适用于要应用该策略的特定用户和用户组。</span><span class="sxs-lookup"><span data-stu-id="c762f-120">The settings of a user policy only apply to the specific users and user groups to which you apply the policy.</span></span> <span data-ttu-id="c762f-121">有关详细信息，请参阅[将存档策略应用于 Skype for Business 服务器中的用户](apply-a-policy-to-users.md)。</span><span class="sxs-lookup"><span data-stu-id="c762f-121">For details, see [Apply an archiving policy to users in Skype for Business Server](apply-a-policy-to-users.md).</span></span> 
  
## <a name="create-a-new-archiving-policy-by-using-windows-powershell"></a><span data-ttu-id="c762f-122">使用 Windows PowerShell 创建新的存档策略</span><span class="sxs-lookup"><span data-stu-id="c762f-122">Create a new archiving policy by using Windows PowerShell</span></span>

<span data-ttu-id="c762f-123">也可以使用 Windows PowerShell **New-CsArchivingPolicy** cmdlet 创建新的存档策略。</span><span class="sxs-lookup"><span data-stu-id="c762f-123">You can also create new archiving policies by using the Windows PowerShell **New-CsArchivingPolicy** cmdlet.</span></span> <span data-ttu-id="c762f-124">有关详细信息，请参阅[CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csarchivingpolicy?view=skype-ps) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="c762f-124">For more information, see the help topic for the [New-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csarchivingpolicy?view=skype-ps) cmdlet.</span></span>
  
### <a name="to-create-a-new-archiving-policy-at-the-site-level"></a><span data-ttu-id="c762f-125">要在站点级别创建新的存档策略</span><span class="sxs-lookup"><span data-stu-id="c762f-125">To create a new archiving policy at the site level</span></span>

<span data-ttu-id="c762f-126">此命令可为 Redmond 站点创建新的存档策略：</span><span class="sxs-lookup"><span data-stu-id="c762f-126">This command creates a new archiving policy for the Redmond site:</span></span>
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond"
```

### <a name="to-create-a-new-archiving-policy-at-the-per-user-level"></a><span data-ttu-id="c762f-127">要在每用户级别创建新的存档策略</span><span class="sxs-lookup"><span data-stu-id="c762f-127">To create a new archiving policy at the per-user level</span></span>

<span data-ttu-id="c762f-128">若要在每用户级别创建新的存档策略，只需在创建策略时指定唯一标识即可：</span><span class="sxs-lookup"><span data-stu-id="c762f-128">To create a new archiving policy at the per-user level, simply specify a unique Identity when creating the policy:</span></span>
  
```PowerShell
New-CsArchivingPolicy -Identity "RedmondArchivingPolicy"
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-internal-communication-sessions"></a><span data-ttu-id="c762f-129">要创建允许对内部通信会话进行存档的新存档策略</span><span class="sxs-lookup"><span data-stu-id="c762f-129">To create a new archiving policy that enables archiving of internal communication sessions</span></span>

<span data-ttu-id="c762f-130">由于前面的命令中未指定参数（必需的 Identity 参数之外），因此新策略将对其所有属性使用默认值。</span><span class="sxs-lookup"><span data-stu-id="c762f-130">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding commands, the new policies will use the default values for all their properties.</span></span> <span data-ttu-id="c762f-131">若要创建使用其他属性值的策略，只需包括适当的参数和参数值。</span><span class="sxs-lookup"><span data-stu-id="c762f-131">To create policies that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="c762f-132">例如，以下命令将创建允许存档内部即时消息会话的存档策略：</span><span class="sxs-lookup"><span data-stu-id="c762f-132">For example, the following command creates an archiving policy that permits archiving of internal instant messaging sessions:</span></span> 
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-both-internal-and-external-communication-sessions"></a><span data-ttu-id="c762f-133">要创建允许对内部和外部通信会话进行存档的新存档策略</span><span class="sxs-lookup"><span data-stu-id="c762f-133">To create a new archiving policy that enables archiving of both internal and external communication sessions</span></span>

<span data-ttu-id="c762f-p104">可通过包含多个参数来修改多个属性值。例如，此命令将配置新策略以便对内部和外部即时消息会话进行存档：</span><span class="sxs-lookup"><span data-stu-id="c762f-p104">Multiple property values can be modified by including multiple parameters. For example, this command configures the new policy to archive both internal and external instant messaging sessions:</span></span>
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True -ArchiveExternal $True
```
