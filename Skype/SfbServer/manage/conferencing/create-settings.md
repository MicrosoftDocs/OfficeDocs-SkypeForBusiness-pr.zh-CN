---
title: 在 Skype for Business Server 中创建会议配置设置
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
ms.assetid: 6d8f9ff8-2a04-4175-9bf0-1ec5d78fd015
description: 摘要：了解如何在 Skype for Business Server 中创建会议配置设置。
ms.openlocfilehash: 862ffc56fd14c446a747a490daa0655e410e01d9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119511"
---
# <a name="create-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="e6e63-103">在 Skype for Business Server 中创建会议配置设置</span><span class="sxs-lookup"><span data-stu-id="e6e63-103">Create meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="e6e63-104">**摘要：** 了解如何在 Skype for Business Server 中创建会议配置设置。</span><span class="sxs-lookup"><span data-stu-id="e6e63-104">**Summary:** Learn how to create meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="e6e63-105">可以使用 Skype for Business Server 控制面板或 Skype for Business Server 命令行管理程序创建会议配置设置。</span><span class="sxs-lookup"><span data-stu-id="e6e63-105">You can create meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="create-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="e6e63-106">使用 Skype for Business Server 控制面板创建会议配置设置</span><span class="sxs-lookup"><span data-stu-id="e6e63-106">Create meeting configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="e6e63-107">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="e6e63-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="e6e63-108">打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="e6e63-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="e6e63-109">在左侧导航栏中，单击 **"会议"，** 然后单击"会议 **配置"。**</span><span class="sxs-lookup"><span data-stu-id="e6e63-109">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="e6e63-110">在 **“会议配置”** 页上，单击 **“新建”**，然后执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="e6e63-110">On the **Meeting Configuration** page, click **New**, and then do one of the following:</span></span>
    
    - <span data-ttu-id="e6e63-p101">要创建站点级别的策略，请单击 **“站点配置”**。在 **“选择站点”** 搜索字段中，键入要为其定义与会设置的站点的全部或部分名称。在结果站点列表中，单击所需的站点，然后单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="e6e63-p101">To create a site-level policy, click **Site configuration**. In the **Select a Site** search field, type all or part of the name of the site for which you want to define meeting join settings. In the resulting list of sites, click the site you want, and then click **OK**.</span></span>
    
    - <span data-ttu-id="e6e63-p102">要创建池级别的策略，请单击 **“池配置”**。在 **“选择服务”** 搜索字段中，键入要为其定义与会设置的池服务的全部或部分名称。在结果服务列表中，单击所需的池，然后单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="e6e63-p102">To create a pool-level policy, click **Pool configuration**. In the **Select a Service** search field, type all or part of the name of the pool service for which you want to define meeting join settings. In the resulting list of services, click the pool you want, and then click **OK**.</span></span>
    
5. <span data-ttu-id="e6e63-p103">要路由从公用电话交换网 (PSTN) 通过会议厅拨入的参与者，请清除 **“PSTN 呼叫者绕过会议厅”** 复选框。默认情况下，从 PSTN 拨入的参与者可直接参加会议。</span><span class="sxs-lookup"><span data-stu-id="e6e63-p103">To route participants who dial in from the public switched telephone network (PSTN) through the lobby, clear the **PSTN callers bypass lobby** check box. By default, participants dialing in from the PSTN go directly to the meeting.</span></span>
    
6. <span data-ttu-id="e6e63-119">要配置会议的演示者，请在 **“指定为演示者”** 中执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="e6e63-119">To configure who can be a presenter in the meeting, in **Designate as presenter**, do one of the following:</span></span>
    
   - <span data-ttu-id="e6e63-120">要禁止组织者以外的任何人成为演示者，请单击 **“无”**。</span><span class="sxs-lookup"><span data-stu-id="e6e63-120">To not allow anyone other than the organizer to be a presenter, click **None**.</span></span>
    
   - <span data-ttu-id="e6e63-p104">要只允许组织成员参与者成为演示者，请单击 **“公司”**。这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="e6e63-p104">To allow only participants who are members of your organization to be a presenter, click **Company**. This is the default setting.</span></span>
    
   - <span data-ttu-id="e6e63-123">要允许任何参与者成为演示者，请单击 **“所有人”**。</span><span class="sxs-lookup"><span data-stu-id="e6e63-123">To allow any participants to be a presenter, click **Everyone**.</span></span>
    
7. <span data-ttu-id="e6e63-p105">要让组织者在安排会议时选择会议类型，请清除 **“默认分配的会议类型”** 复选框。默认情况下，会自动分配会议类型。</span><span class="sxs-lookup"><span data-stu-id="e6e63-p105">To have the organizer select a conference type when scheduling a meeting, clear the **Assigned conference type by default** check box. By default, the conference type is automatically assigned.</span></span>
    
8. <span data-ttu-id="e6e63-p106">要阻止自动允许匿名（未经身份验证）用户参加会议，请清除 **“默认允许匿名用户”** 复选框。默认情况下，自动允许匿名用户参加会议。</span><span class="sxs-lookup"><span data-stu-id="e6e63-p106">To prevent anonymous (unauthenticated) users from being automatically admitted, clear the **Admit anonymous users by default** check box. By default, anonymous users are automatically admitted to meetings.</span></span>
    
9. <span data-ttu-id="e6e63-128">若要自定义发送给参与者的会议邀请，请执行下列操作。</span><span class="sxs-lookup"><span data-stu-id="e6e63-128">To customize the meeting invite that is sent out to participants, do the following.</span></span> <span data-ttu-id="e6e63-129">请注意，URL 和自定义页脚文本的最大长度为 1KB。</span><span class="sxs-lookup"><span data-stu-id="e6e63-129">Note that the maximum length for URLs and custom footer text is 1KB.</span></span> <span data-ttu-id="e6e63-130">帮助 **URL** 除外，如果不为自定义项指定值，则它们将不会包含在会议中。</span><span class="sxs-lookup"><span data-stu-id="e6e63-130">Except for **Help URL**, if you do not specify a value for the customizations, they will not be included in the meeting.</span></span> <span data-ttu-id="e6e63-131">如果不包括自定义帮助 URL，Skype for Business 的默认帮助 URL 将显示在邀请中。</span><span class="sxs-lookup"><span data-stu-id="e6e63-131">If you do not include a custom help URL, the default help URL for Skype for Business will be displayed in the invite.</span></span> 
    
   - <span data-ttu-id="e6e63-132">若要自定义会议邀请中出现的徽标，请在"徽标 **URL"** 中输入徽标的位置。</span><span class="sxs-lookup"><span data-stu-id="e6e63-132">To customize the logo that appears in the meeting invite, in **Logo URL**, enter the location of the logo.</span></span> <span data-ttu-id="e6e63-133">徽标必须是大小为 188 x 30 像素的 GIF 或 JPG 图像。</span><span class="sxs-lookup"><span data-stu-id="e6e63-133">The logo must be a GIF or JPG image with a size of 188 by 30 pixels.</span></span> 
    
   - <span data-ttu-id="e6e63-134">若要自定义会议邀请中显示的帮助文本，请在"帮助 **URL"** 中输入帮助文本的位置。</span><span class="sxs-lookup"><span data-stu-id="e6e63-134">To customize the help text that appears in the meeting invite, in **Help URL**, enter the location of the help text.</span></span>
    
   - <span data-ttu-id="e6e63-135">若要自定义会议邀请中显示的法律文本，请在"法律文本 **URL"** 中输入法律文本的位置。</span><span class="sxs-lookup"><span data-stu-id="e6e63-135">To customize the legal text that appears in the meeting invite, in **Legal text URL**, enter the location of the legal text.</span></span>
    
   - <span data-ttu-id="e6e63-136">若要自定义会议邀请中出现的页脚文本，请在"自定义页脚文本" **中** 输入文本。</span><span class="sxs-lookup"><span data-stu-id="e6e63-136">To customize the footer text that appears in the meeting invite, in **Custom footer text**, enter text.</span></span>
    
10. <span data-ttu-id="e6e63-137">单击“提交”。</span><span class="sxs-lookup"><span data-stu-id="e6e63-137">Click **Commit**.</span></span>
    
## <a name="create-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="e6e63-138">使用 Skype for Business Server 命令行管理程序创建会议配置设置</span><span class="sxs-lookup"><span data-stu-id="e6e63-138">Create meeting configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="e6e63-139">若要创建会议配置设置，请使用 **New-CsMeetingConfiguration** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e6e63-139">To create meeting configuration settings, use the **New-CsMeetingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="e6e63-140">以下命令为 Redmond 站点创建一组新的会议配置设置：</span><span class="sxs-lookup"><span data-stu-id="e6e63-140">The following command creates a new set of meeting configuration settings for the Redmond site:</span></span>
  
```PowerShell
New-CsMeetingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="e6e63-141">由于上述 (中未指定必需的 Identity) 参数，因此新的会议配置设置将在其所有属性中都使用默认值。</span><span class="sxs-lookup"><span data-stu-id="e6e63-141">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new meeting configuration settings will use the default values for all its properties.</span></span>
  
<span data-ttu-id="e6e63-142">要创建使用不同属性值的设置，只需包含相应的参数和参数值。</span><span class="sxs-lookup"><span data-stu-id="e6e63-142">To create settings that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="e6e63-143">例如，若要创建默认情况下允许所有人以演示者角色加入会议的会议配置设置集合，请使用类似如下的命令：</span><span class="sxs-lookup"><span data-stu-id="e6e63-143">For example, to create a collection of meeting configuration settings that, by default, admit everyone to a meeting as a presenter use a command like this:</span></span>
  
```PowerShell
New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

<span data-ttu-id="e6e63-144">可以通过包含多个参数来设置多个属性值。</span><span class="sxs-lookup"><span data-stu-id="e6e63-144">Multiple property values can be set by including multiple parameters.</span></span> <span data-ttu-id="e6e63-145">例如，以下命令允许所有人以演示者形式加入会议，并强制 PSTN 用户在会议厅等待，直到正式允许他们参加会议：</span><span class="sxs-lookup"><span data-stu-id="e6e63-145">For example, the following command admits everyone to a meeting as a presenter and also forces PSTN users to wait in the lobby until they are formally admitted to the meeting:</span></span>
  
```PowerShell
New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone" -PSTNUCallersBypassLobby $True
```

<span data-ttu-id="e6e63-146">有关详细信息，包括参数的完整列表，请参阅[New-CsMeetingConfiguration。](/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="e6e63-146">For more information, including a complete list of parameters, see [New-CsMeetingConfiguration](/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps).</span></span>
