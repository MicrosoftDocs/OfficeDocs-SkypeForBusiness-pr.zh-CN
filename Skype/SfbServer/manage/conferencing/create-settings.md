---
title: 创建会议配置设置中 Skype 业务服务器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6d8f9ff8-2a04-4175-9bf0-1ec5d78fd015
description: 摘要： 了解如何创建会议配置设置中 Skype 业务服务器。
ms.openlocfilehash: c154661e5e8b974e4a475c935b40749776e0499c
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30890400"
---
# <a name="create-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="94d55-103">创建会议配置设置中 Skype 业务服务器</span><span class="sxs-lookup"><span data-stu-id="94d55-103">Create meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="94d55-104">**摘要：** 了解如何创建会议配置设置中 Skype 业务服务器。</span><span class="sxs-lookup"><span data-stu-id="94d55-104">**Summary:** Learn how to create meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="94d55-105">您可以创建会议配置设置，使用的业务 Server Control Panel Skype 或使用 Skype 业务 Server Management Shell。</span><span class="sxs-lookup"><span data-stu-id="94d55-105">You can create meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="create-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="94d55-106">创建使用适用于业务 Server Control Panel Skype 会议配置设置</span><span class="sxs-lookup"><span data-stu-id="94d55-106">Create meeting configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="94d55-107">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="94d55-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="94d55-108">打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="94d55-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="94d55-109">在左侧导航栏中，单击“**会议**”，然后单击“**会议配置**”。</span><span class="sxs-lookup"><span data-stu-id="94d55-109">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="94d55-110">在“**会议配置**”页上，单击“**新建**”，然后执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="94d55-110">On the **Meeting Configuration** page, click **New**, and then do one of the following:</span></span>
    
    - <span data-ttu-id="94d55-p101">若要创建站点级别的策略，请单击“**站点配置**”。在“**选择站点**”搜索字段中，键入要为其定义与会设置的站点的全部或部分名称。在结果站点列表中，单击所需的站点，然后单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="94d55-p101">To create a site-level policy, click **Site configuration**. In the **Select a Site** search field, type all or part of the name of the site for which you want to define meeting join settings. In the resulting list of sites, click the site you want, and then click **OK**.</span></span>
    
    - <span data-ttu-id="94d55-p102">若要创建池级别的策略，请单击“**池配置**”。在“**选择服务**”搜索字段中，键入要为其定义与会设置的池服务的全部或部分名称。在结果服务列表中，单击所需的池，然后单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="94d55-p102">To create a pool-level policy, click **Pool configuration**. In the **Select a Service** search field, type all or part of the name of the pool service for which you want to define meeting join settings. In the resulting list of services, click the pool you want, and then click **OK**.</span></span>
    
5. <span data-ttu-id="94d55-p103">若要路由从公用电话交换网 (PSTN) 通过会议厅拨入的参与者，请清除“**PSTN 呼叫者绕过休息室**”复选框。默认情况下，从 PSTN 拨入的参与者可直接参加会议。</span><span class="sxs-lookup"><span data-stu-id="94d55-p103">To route participants who dial in from the public switched telephone network (PSTN) through the lobby, clear the **PSTN callers bypass lobby** check box. By default, participants dialing in from the PSTN go directly to the meeting.</span></span>
    
6. <span data-ttu-id="94d55-119">若要配置会议的演示者，请在“**指定为演示者**”中执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="94d55-119">To configure who can be a presenter in the meeting, in **Designate as presenter**, do one of the following:</span></span>
    
   - <span data-ttu-id="94d55-120">若要禁止组织者以外的任何人成为演示者，请单击“**无**”。</span><span class="sxs-lookup"><span data-stu-id="94d55-120">To not allow anyone other than the organizer to be a presenter, click **None**.</span></span>
    
   - <span data-ttu-id="94d55-p104">若要只允许属于组织成员的参与者成为演示者，请单击“**公司**”。这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="94d55-p104">To allow only participants who are members of your organization to be a presenter, click **Company**. This is the default setting.</span></span>
    
   - <span data-ttu-id="94d55-123">若要允许任何参与者成为演示者，请单击“**所有人**”。</span><span class="sxs-lookup"><span data-stu-id="94d55-123">To allow any participants to be a presenter, click **Everyone**.</span></span>
    
7. <span data-ttu-id="94d55-p105">若要让组织者在安排会议时选择会议类型，请清除“**默认分配的会议类型**”复选框。默认情况下，会自动分配会议类型。</span><span class="sxs-lookup"><span data-stu-id="94d55-p105">To have the organizer select a conference type when scheduling a meeting, clear the **Assigned conference type by default** check box. By default, the conference type is automatically assigned.</span></span>
    
8. <span data-ttu-id="94d55-p106">若要阻止自动允许匿名（未经身份验证）用户参加会议，请清除“**默认允许匿名用户**”复选框。默认情况下，自动允许匿名用户参加会议。</span><span class="sxs-lookup"><span data-stu-id="94d55-p106">To prevent anonymous (unauthenticated) users from being automatically admitted, clear the **Admit anonymous users by default** check box. By default, anonymous users are automatically admitted to meetings.</span></span>
    
9. <span data-ttu-id="94d55-128">若要自定义发送给参与者的会议邀请，请执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="94d55-128">To customize the meeting invite that is sent out to participants, do the following.</span></span> <span data-ttu-id="94d55-129">请注意，URL 和自定义页脚文本的最大长度为 1KB。</span><span class="sxs-lookup"><span data-stu-id="94d55-129">Note that the maximum length for URLs and custom footer text is 1KB.</span></span> <span data-ttu-id="94d55-130">除了“**帮助 URL**”外，如果不指定自定义的值，则它们不会包括在会议中。</span><span class="sxs-lookup"><span data-stu-id="94d55-130">Except for **Help URL**, if you do not specify a value for the customizations, they will not be included in the meeting.</span></span> <span data-ttu-id="94d55-131">如果不包括自定义帮助 URL，for Business 的 Skype 的默认帮助 URL 将显示在邀请。</span><span class="sxs-lookup"><span data-stu-id="94d55-131">If you do not include a custom help URL, the default help URL for Skype for Business will be displayed in the invite.</span></span> 
    
   - <span data-ttu-id="94d55-p108">若要自定义会议邀请中显示的徽标，请在“**徽标 URL**”中输入徽标的位置。徽标必须是大小为 188 x 30 像素的 GIF 或 JPG 图像。</span><span class="sxs-lookup"><span data-stu-id="94d55-p108">To customize the logo that appears in the meeting invite, in **Logo URL**, enter the location of the logo. The logo must be a GIF or JPG image with a size of 188 by 30 pixels.</span></span> 
    
   - <span data-ttu-id="94d55-134">若要自定义会议邀请中显示的帮助文本，请在“**帮助 URL**”中输入帮助文本的位置。</span><span class="sxs-lookup"><span data-stu-id="94d55-134">To customize the help text that appears in the meeting invite, in **Help URL**, enter the location of the help text.</span></span>
    
   - <span data-ttu-id="94d55-135">若要自定义会议邀请中显示的法律文本，请在“**法律文本 URL**”中输入法律文本的位置。</span><span class="sxs-lookup"><span data-stu-id="94d55-135">To customize the legal text that appears in the meeting invite, in **Legal text URL**, enter the location of the legal text.</span></span>
    
   - <span data-ttu-id="94d55-136">若要自定义会议邀请中显示的页脚文本，请在“**自定义页脚文本**”中输入文本。</span><span class="sxs-lookup"><span data-stu-id="94d55-136">To customize the footer text that appears in the meeting invite, in **Custom footer text**, enter text.</span></span>
    
10. <span data-ttu-id="94d55-137">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="94d55-137">Click **Commit**.</span></span>
    
## <a name="create-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="94d55-138">创建使用适用于业务 Server 命令行管理程序 Skype 会议配置设置</span><span class="sxs-lookup"><span data-stu-id="94d55-138">Create meeting configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="94d55-139">若要创建会议配置设置，请使用 **New-CsMeetingConfiguration** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="94d55-139">To create meeting configuration settings, use the **New-CsMeetingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="94d55-140">以下命令为 Redmond 站点创建一组新的会议配置设置：</span><span class="sxs-lookup"><span data-stu-id="94d55-140">The following command creates a new set of meeting configuration settings for the Redmond site:</span></span>
  
```
New-CsMeetingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="94d55-141">由于在上述命令中未指定参数（不包括必需的 Identity 参数），新的会议配置设置的所有属性将使用默认值。</span><span class="sxs-lookup"><span data-stu-id="94d55-141">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new meeting configuration settings will use the default values for all its properties.</span></span>
  
<span data-ttu-id="94d55-p109">要创建使用不同属性值的设置，只需包含相应的参数和参数值。例如，要创建在默认情况下允许所有人以演示者身份加入会议的会议配置设置集合，请使用如下命令：</span><span class="sxs-lookup"><span data-stu-id="94d55-p109">To create settings that use different property values, simply include the appropriate parameter and parameter value. For example, to create a collection of meeting configuration settings that, by default, admit everyone to a meeting as a presenter use a command like this:</span></span>
  
```
New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

<span data-ttu-id="94d55-p110">可以通过包含多个参数来设置多个属性值。例如，以下命令允许所有人以演示者身份加入会议，同时强制 PSTN 用户在会议厅等待，直至他们被正式允许加入会议：</span><span class="sxs-lookup"><span data-stu-id="94d55-p110">Multiple property values can be set by including multiple parameters. For example, the following command admits everyone to a meeting as a presenter and also forces PSTN users to wait in the lobby until they are formally admitted to the meeting:</span></span>
  
```
New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone" -PSTNUCallersBypassLobby $True
```

<span data-ttu-id="94d55-146">有关详细信息，包括完成参数的列表，请参阅[New-csmeetingconfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="94d55-146">For more information, including a complete list of parameters, see [New-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps).</span></span>
  

