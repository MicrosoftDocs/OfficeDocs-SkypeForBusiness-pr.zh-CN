---
title: 为用户启用联机企业语音和电话系统语音邮件
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 28daebcb-c2dc-4338-b2d1-04345ece9c19
description: 了解如何为 Skype for Business 用户启用电话系统语音服务。
ms.openlocfilehash: f1c59505073a7113407f28b7ebbe3a323724782e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098568"
---
# <a name="enable-users-for-enterprise-voice-online-and-phone-system-voicemail"></a><span data-ttu-id="b1c17-103">为用户启用联机企业语音和电话系统语音邮件</span><span class="sxs-lookup"><span data-stu-id="b1c17-103">Enable users for Enterprise Voice online and Phone System Voicemail</span></span>
 
> [!Important]
> <span data-ttu-id="b1c17-104">Skype for Business Online 将于 2021 年 7 月 31 日停用，此后服务将不再可用。</span><span class="sxs-lookup"><span data-stu-id="b1c17-104">Skype for Business Online will be retired on July 31, 2021 after which the service will no longer be accessible.</span></span>  <span data-ttu-id="b1c17-105">此外，将不再支持本地环境（无论是通过 Skype for Business Server 还是云连接器版本与 Skype for Business Online）之间的 PSTN 连接。</span><span class="sxs-lookup"><span data-stu-id="b1c17-105">In addition, PSTN connectivity between your on-premises environment whether through Skype for Business Server or Cloud Connector Edition and Skype for Business Online will no longer be supported.</span></span>  <span data-ttu-id="b1c17-106">了解如何使用直接路由将本地电话网络连接到[Teams。](/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="b1c17-106">Learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="b1c17-107">了解如何为 Skype for Business 用户启用电话系统语音服务。</span><span class="sxs-lookup"><span data-stu-id="b1c17-107">Learn how to enable Phone System voice services for your Skype for Business users.</span></span>
  
<span data-ttu-id="b1c17-108">使用本地 PSTN 连接部署电话系统的最后一步是为用户启用电话系统和语音邮件。</span><span class="sxs-lookup"><span data-stu-id="b1c17-108">The final step in deploying Phone System with on-premises PSTN connectivity is to enable your users for Phone System and voicemail.</span></span> <span data-ttu-id="b1c17-109">若要启用这些功能，您必须是具有全局管理员角色的用户，并且能够运行远程 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="b1c17-109">To enable these capabilities, you must be a user with the Global Administrator role, and be able to run remote PowerShell.</span></span> <span data-ttu-id="b1c17-110">你需要对尚未启用 Skype for Business Online 的所有用户帐户企业语音本主题中的步骤。</span><span class="sxs-lookup"><span data-stu-id="b1c17-110">You need to follow the steps in this topic for all user accounts that do not already have Enterprise Voice enabled for Skype for Business Online.</span></span>
  
## <a name="enable-phone-system-voice-services"></a><span data-ttu-id="b1c17-111">启用电话系统语音服务</span><span class="sxs-lookup"><span data-stu-id="b1c17-111">Enable Phone System voice services</span></span>

<span data-ttu-id="b1c17-112">若要为用户启用电话系统语音和语音邮件，你需要执行一些初始步骤，例如检查 Skype for Business Online 连接器是否部署在你的服务器上，并启用你的用户托管语音邮件。</span><span class="sxs-lookup"><span data-stu-id="b1c17-112">To enable a user for Phone System Voice and voicemail, you'll need to perform some initial steps, like checking to see if the Skype for Business Online Connector is deployed on your servers and enable your users for hosted voicemail.</span></span>
  
### <a name="to-enable-your-users-for-phone-system-voice-and-voicemail"></a><span data-ttu-id="b1c17-113">为用户启用电话系统语音和语音邮件</span><span class="sxs-lookup"><span data-stu-id="b1c17-113">To enable your users for Phone System voice and voicemail</span></span>

> [!NOTE]
> <span data-ttu-id="b1c17-114">Skype for Business Online Connector 当前是最新的 Teams PowerShell 模块的一部分。</span><span class="sxs-lookup"><span data-stu-id="b1c17-114">Skype for Business Online Connector is currently part of latest Teams PowerShell Module.</span></span>
> <span data-ttu-id="b1c17-115">如果你使用的是最新的 [Teams PowerShell 公共版本](https://www.powershellgallery.com/packages/MicrosoftTeams/)，则无需安装 Skype for Business Online 连接器。</span><span class="sxs-lookup"><span data-stu-id="b1c17-115">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

1. <span data-ttu-id="b1c17-116">开始之前，请检查前端服务器上是否安装了 Teams PowerShell 模块。</span><span class="sxs-lookup"><span data-stu-id="b1c17-116">Before you begin, check that the Teams PowerShell module is installed on your Front End Servers.</span></span> <span data-ttu-id="b1c17-117">如果没有，请按照 Teams PowerShell 模块安装 [中的说明安装](/microsoftteams/teams-powershell-install)。</span><span class="sxs-lookup"><span data-stu-id="b1c17-117">If it's not, please  install using the instructions in [Teams PowerShell Module Installation](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="b1c17-118">以Windows PowerShell开始登录。</span><span class="sxs-lookup"><span data-stu-id="b1c17-118">Start Windows PowerShell as an administrator.</span></span>
    
3. <span data-ttu-id="b1c17-119">键入以下内容并按 Enter：</span><span class="sxs-lookup"><span data-stu-id="b1c17-119">Type the following and press Enter:</span></span>
    
 ```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```

  
4. <span data-ttu-id="b1c17-120">使用 Set-CsUser cmdlet 将 $EnterpriseVoiceEnabled 和 $HostedVoiceMail 属性分配给用户，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b1c17-120">Use the Set-CsUser cmdlet to assign the $EnterpriseVoiceEnabled and $HostedVoiceMail properties to your user as follows:</span></span>
    
   ```powershell
   Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    <span data-ttu-id="b1c17-121">例如：</span><span class="sxs-lookup"><span data-stu-id="b1c17-121">For example:</span></span>
    
   ```powershell
   Set-CsUser -Identity "Bob Kelly" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    > [!NOTE]
    > <span data-ttu-id="b1c17-122">您还可以通过用户的 SIP 地址、用户主体名称 (UPN) 、域名和用户名 (domain\username) 以及 Active Directory ("Bob Kelly") 中的 显示名称 来指定用户。</span><span class="sxs-lookup"><span data-stu-id="b1c17-122">You can also specify a user by their SIP address, User Principal name (UPN), domain name and username (domain\username), and display name in Active Directory ("Bob Kelly").</span></span> 
  
## <a name="update-the-line-uri-and-dial-plan-for-users-enabled-for-phone-system"></a><span data-ttu-id="b1c17-123">更新为电话系统启用的用户的线路 URI 和拨号计划</span><span class="sxs-lookup"><span data-stu-id="b1c17-123">Update the Line URI and dial plan for users enabled for Phone System</span></span>

<span data-ttu-id="b1c17-124">本节介绍如何更新为电话系统启用的用户的线路 URI 和拨号计划。</span><span class="sxs-lookup"><span data-stu-id="b1c17-124">This section describes how to update the Line URI and dial plan for users enabled for Phone System.</span></span> 
  
### <a name="to-update-the-line-uri"></a><span data-ttu-id="b1c17-125">更新线路 URI</span><span class="sxs-lookup"><span data-stu-id="b1c17-125">To update the Line URI</span></span>

1. <span data-ttu-id="b1c17-126">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="b1c17-126">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="b1c17-127">使用"开始"菜单或桌面快捷方式打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="b1c17-127">Use the Start menu or desktop shortcut to open the Skype for Business Server Control Panel.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b1c17-128">还可以打开浏览器窗口，然后输入管理员 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="b1c17-128">You can also open a browser window, and then enter the Administrator URL to open the Skype for Business Server Control Panel.</span></span> 
  
3. <span data-ttu-id="b1c17-129">在左侧导航栏中，单击“用户”。</span><span class="sxs-lookup"><span data-stu-id="b1c17-129">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="b1c17-130">在“搜索用户”框中，键入要启用的用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”。</span><span class="sxs-lookup"><span data-stu-id="b1c17-130">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="b1c17-131">在表中，单击要更改线路 URI 的 Skype for Business 用户帐户。</span><span class="sxs-lookup"><span data-stu-id="b1c17-131">In the table, click the Skype for Business user account that you want to change line URI.</span></span>
    
6. <span data-ttu-id="b1c17-132">单击 **"线路 URI"，** 然后键入唯一的规范化电话号码 (例如 tel：+14255550200) 。</span><span class="sxs-lookup"><span data-stu-id="b1c17-132">Click **Line URI**, and type a unique, normalized phone number (for example, tel:+14255550200).</span></span> <span data-ttu-id="b1c17-133">然后单击"**提交"。**</span><span class="sxs-lookup"><span data-stu-id="b1c17-133">Then click **Commit**.</span></span>
    
## <a name="update-the-dial-plan-using-on-premises-windows-powershell-cmdlets"></a><span data-ttu-id="b1c17-134">使用本地部署 cmdlet 更新Windows PowerShell计划</span><span class="sxs-lookup"><span data-stu-id="b1c17-134">Update the dial plan using on-premises Windows PowerShell cmdlets</span></span>

<span data-ttu-id="b1c17-135">可以使用 Windows PowerShell 和 [Grant-CsDialPlan](/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet 分配每用户拨号计划。</span><span class="sxs-lookup"><span data-stu-id="b1c17-135">You can assign per-user dial plans with Windows PowerShell and the [Grant-CsDialPlan](/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="b1c17-136">可以从 Skype for Business Server 2015 或远程会话运行此 cmdlet Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="b1c17-136">You can run this cmdlet either from the Skype for Business Server 2015 or from a remote session of Windows PowerShell.</span></span>
  
### <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a><span data-ttu-id="b1c17-137">将每用户拨号计划分配给单个用户</span><span class="sxs-lookup"><span data-stu-id="b1c17-137">To assign a per-user dial plan to a single user</span></span>

- <span data-ttu-id="b1c17-138">使用 [Grant-CsDialPlan](/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet 将每用户拨号计划 RedmondDialPlan 分配给用户 Ken Myer：</span><span class="sxs-lookup"><span data-stu-id="b1c17-138">Use the [Grant-CsDialPlan](/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet to assign the per-user dial plan RedmondDialPlan to the user Ken Myer:</span></span>
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"
  ```

### <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a><span data-ttu-id="b1c17-139">将每用户拨号计划分配给多个用户</span><span class="sxs-lookup"><span data-stu-id="b1c17-139">To assign a per-user dial plan to multiple users</span></span>

- <span data-ttu-id="b1c17-140">以下命令将每用户拨号计划 RedmondDialPlan 分配给在 Redmond 市工作的所有用户。</span><span class="sxs-lookup"><span data-stu-id="b1c17-140">The following command assigns the per-user dial plan RedmondDialPlan to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="b1c17-141">有关此命令中使用的 LdapFilter 参数详细信息，请参阅 [Get-CsUser](/powershell/module/skype/get-csuser?view=skype-ps) cmdlet 的文档：</span><span class="sxs-lookup"><span data-stu-id="b1c17-141">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](/powershell/module/skype/get-csuser?view=skype-ps) cmdlet:</span></span>
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"
  ```

> [!NOTE]
> <span data-ttu-id="b1c17-142">您可以为联机用户使用全局或用户拨号计划。</span><span class="sxs-lookup"><span data-stu-id="b1c17-142">You may use either Global or User dial plans for online users.</span></span> <span data-ttu-id="b1c17-143">不能使用站点拨号计划，因为此类计划仅适用于在本地托管并分配到本地站点的用户。</span><span class="sxs-lookup"><span data-stu-id="b1c17-143">Site dial plans cannot be used as these only apply to users who are hosted on premises and are assigned to an on-premises site.</span></span> 
  
### <a name="to-unassign-a-per-user-dial-plan"></a><span data-ttu-id="b1c17-144">取消分配每用户拨号计划</span><span class="sxs-lookup"><span data-stu-id="b1c17-144">To unassign a per-user dial plan</span></span>

- <span data-ttu-id="b1c17-145">使用 [Grant-CsDialPlan](/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet 取消分配之前分配给 Ken Myer 的任何每用户拨号计划。</span><span class="sxs-lookup"><span data-stu-id="b1c17-145">Use the [Grant-CsDialPlan](/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet to unassign any per-user dial plan previously assigned to Ken Myer.</span></span> <span data-ttu-id="b1c17-146">取消分配每用户拨号计划后，将自动使用全局拨号计划或分配给其注册器或 PSTN 网关的服务范围拨号计划管理 Ken Myer。</span><span class="sxs-lookup"><span data-stu-id="b1c17-146">After the per-user dial plan is unassigned, Ken Myer will automatically be managed by using the global dial plan or the service-scope dial plan assigned to his Registrar or PSTN gateway.</span></span> <span data-ttu-id="b1c17-147">服务范围拨号计划优先于全局拨号计划：</span><span class="sxs-lookup"><span data-stu-id="b1c17-147">A service scope dial plan takes precedence over the global dial plan:</span></span>
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null
  ```

## <a name="update-the-voice-routing-policies-using-on-premises-windows-powershell-cmdlets"></a><span data-ttu-id="b1c17-148">使用本地部署 cmdlet 更新Windows PowerShell策略</span><span class="sxs-lookup"><span data-stu-id="b1c17-148">Update the voice routing policies using on-premises Windows PowerShell cmdlets</span></span>

<span data-ttu-id="b1c17-149">本节介绍如何更新为电话系统启用的用户的语音路由策略。</span><span class="sxs-lookup"><span data-stu-id="b1c17-149">This section describes how to update the voice routing policies for users enabled for Phone System.</span></span>
  
<span data-ttu-id="b1c17-150">电话系统用户必须分配有语音路由策略，以便成功路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="b1c17-150">Phone System users must have a Voice Routing Policy assigned to them for calls to route successfully.</span></span> <span data-ttu-id="b1c17-151">这不同于需要为其分配语音策略以允许呼叫成功路由本地商务语音用户。</span><span class="sxs-lookup"><span data-stu-id="b1c17-151">This differs from on-premises business voice users who require a Voice Policy to be assigned to them to allow calls to route successfully.</span></span> <span data-ttu-id="b1c17-152">语音路由策略应包含 PSTN 用法，用于定义电话系统用户的授权呼叫和路由。</span><span class="sxs-lookup"><span data-stu-id="b1c17-152">The Voice Routing Policy should contain PSTN usages that define authorized calls and routes for Phone System users.</span></span> <span data-ttu-id="b1c17-153">可以将这些 PSTN 用法从现有语音策略复制到新的语音路由策略。</span><span class="sxs-lookup"><span data-stu-id="b1c17-153">You can copy these PSTN usages from existing Voice Policies to new Voice Routing Policies.</span></span> <span data-ttu-id="b1c17-154">有关详细信息，请参阅 [New-CsVoiceRoutingPolicy](/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="b1c17-154">For more information, see [New-CsVoiceRoutingPolicy](/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps).</span></span>
  
> [!NOTE]
> <span data-ttu-id="b1c17-155">所有电话系统用户都分配有同一个名为 BusinessVoice 的联机语音策略，该策略定义允许的呼叫功能;例如，允许同时响铃。</span><span class="sxs-lookup"><span data-stu-id="b1c17-155">All Phone System users are assigned the same online Voice Policy named BusinessVoice which defines the calling features allowed; for example, Allow Simultaneous Ring.</span></span> 
  
### <a name="to-assign-a-per-user-voice-routing-policy-to-a-single-user"></a><span data-ttu-id="b1c17-156">将每用户语音路由策略分配给单个用户</span><span class="sxs-lookup"><span data-stu-id="b1c17-156">To assign a per-user voice routing policy to a single user</span></span>

- <span data-ttu-id="b1c17-157">使用 [Grant-CsVoiceRoutingPolicy](/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) cmdlet 将每用户语音路由策略 RedmondVoiceRoutingPolicy 分配给用户 Ken Myer：</span><span class="sxs-lookup"><span data-stu-id="b1c17-157">Use the [Grant-CsVoiceRoutingPolicy](/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) cmdlet to assign the per-user voice routing policy RedmondVoiceRoutingPolicy to the user Ken Myer:</span></span>
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName "RedmondVoiceRoutingPolicy"
  ```

### <a name="to-assign-a-per-user-voice-routing-policy-to-multiple-users"></a><span data-ttu-id="b1c17-158">将每用户语音路由策略分配给多个用户</span><span class="sxs-lookup"><span data-stu-id="b1c17-158">To assign a per-user voice routing policy to multiple users</span></span>

- <span data-ttu-id="b1c17-159">下一个命令将每用户语音路由策略 RedmondVoiceRoutingPolicy 分配给在 Redmond 市工作的所有用户。</span><span class="sxs-lookup"><span data-stu-id="b1c17-159">The next command assigns the per-user voice routing policy RedmondVoiceRoutingPolicy to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="b1c17-160">有关此命令中使用的 LdapFilter 参数详细信息，请参阅 [Get-CsUser](/powershell/module/skype/get-csuser?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="b1c17-160">For more information on the LdapFilter parameter used in this command, see [Get-CsUser](/powershell/module/skype/get-csuser?view=skype-ps).</span></span>
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsVoiceRoutingPolicy -PolicyName "RedmondVoiceRoutingPolicy"
  ```

    > [!NOTE]
    > <span data-ttu-id="b1c17-161">您可以对联机用户使用全局或用户语音路由策略。</span><span class="sxs-lookup"><span data-stu-id="b1c17-161">You may use either Global or User voice routing policies for online users.</span></span> <span data-ttu-id="b1c17-162">不能使用站点语音路由策略，因为这些策略仅适用于在本地托管并分配到本地站点的用户。</span><span class="sxs-lookup"><span data-stu-id="b1c17-162">Site voice routing policies cannot be used as these only apply to users who are hosted on premises and are assigned to an on-premises site.</span></span> 
  
### <a name="to-unassign-a-per-user-voice-routing-policy"></a><span data-ttu-id="b1c17-163">取消分配每用户语音路由策略</span><span class="sxs-lookup"><span data-stu-id="b1c17-163">To unassign a per-user voice routing policy</span></span>

- <span data-ttu-id="b1c17-164">使用Grant-CsVoiceRoutingPolicy取消分配之前分配给 Ken Myer 的任何每用户语音路由策略。</span><span class="sxs-lookup"><span data-stu-id="b1c17-164">Use the Grant-CsVoiceRoutingPolicy to unassign any per-user voice routing policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="b1c17-165">取消分配每用户语音路由策略后，将自动使用全局语音路由策略管理 Ken Myer。</span><span class="sxs-lookup"><span data-stu-id="b1c17-165">After the per-user voice routing policy is unassigned, Ken Myer will automatically be managed by using the global voice routing policy.</span></span>
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

    <span data-ttu-id="b1c17-166">有关详细信息，请参阅 [Grant-CsVoiceRoutingPolicy](/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="b1c17-166">For more information, see [Grant-CsVoiceRoutingPolicy](/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps).</span></span>
