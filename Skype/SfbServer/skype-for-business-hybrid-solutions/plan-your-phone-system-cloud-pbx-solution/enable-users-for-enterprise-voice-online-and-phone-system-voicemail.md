---
title: 在 Office 365 语音邮件中为用户启用企业语音在线和电话系统
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
description: 了解如何为你的 Skype for Business 用户启用 Office 365 语音服务中的电话系统。
ms.openlocfilehash: ae1443fa0f0725b6cbbe722703f24af02139c12d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050194"
---
# <a name="enable-users-for-enterprise-voice-online-and-phone-system-in-office-365-voicemail"></a><span data-ttu-id="32b68-103">在 Office 365 语音邮件中为用户启用企业语音在线和电话系统</span><span class="sxs-lookup"><span data-stu-id="32b68-103">Enable users for Enterprise Voice online and Phone System in Office 365 Voicemail</span></span>
 
<span data-ttu-id="32b68-104">了解如何为你的 Skype for Business 用户启用 Office 365 语音服务中的电话系统。</span><span class="sxs-lookup"><span data-stu-id="32b68-104">Learn how to enable Phone System in Office 365 voice services for your Skype for Business users.</span></span>
  
<span data-ttu-id="32b68-105">在使用本地 PSTN 连接的 Office 365 中部署电话系统的最后一步是为用户启用 Office 365 和语音邮件中的电话系统。</span><span class="sxs-lookup"><span data-stu-id="32b68-105">The final step in deploying Phone System in Office 365 with on-premises PSTN connectivity is to enable your users for Phone System in Office 365 and voicemail.</span></span> <span data-ttu-id="32b68-106">若要启用这些功能，您必须是具有 Office 365 全局管理员角色的用户，并且能够运行远程 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="32b68-106">To enable these capabilities, you must be a user with the Office 365 Global Administrator role, and be able to run remote PowerShell.</span></span> <span data-ttu-id="32b68-107">对于尚未为 Skype for business Online 启用企业语音的所有用户帐户，您需要按照本主题中的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="32b68-107">You need to follow the steps in this topic for all user accounts that do not already have Enterprise Voice enabled for Skype for Business Online.</span></span>
  
## <a name="enable-phone-system-in-office-365-voice-services"></a><span data-ttu-id="32b68-108">启用 Office 365 语音服务中的电话系统</span><span class="sxs-lookup"><span data-stu-id="32b68-108">Enable Phone System in Office 365 voice services</span></span>

<span data-ttu-id="32b68-109">若要为用户启用 Office 365 语音和语音邮件中的电话系统，需要执行一些初始步骤，如检查是否在服务器上部署了 Skype for Business Online 连接器并为用户启用托管语音邮件。</span><span class="sxs-lookup"><span data-stu-id="32b68-109">To enable a user for Phone System in Office 365 Voice and voicemail, you'll need to perform some initial steps, like checking to see if the Skype for Business Online Connector is deployed on your servers and enable your users for hosted voicemail.</span></span>
  
### <a name="to-enable-your-users-for-phone-system-in-office-365-voice-and-voicemail"></a><span data-ttu-id="32b68-110">为用户启用 Office 365 语音和语音邮件中的电话系统</span><span class="sxs-lookup"><span data-stu-id="32b68-110">To enable your users for Phone System in Office 365 voice and voicemail</span></span>

1. <span data-ttu-id="32b68-111">在开始之前，请检查是否在前端服务器上部署了 Skype for Business Online 连接器（Windows PowerShell 模块）。</span><span class="sxs-lookup"><span data-stu-id="32b68-111">Before you begin, check that the Skype for Business Online Connector (Windows PowerShell module) is deployed on your Front End Servers.</span></span> <span data-ttu-id="32b68-112">如果不是，则可以从[下载中心](https://www.microsoft.com/download/details.aspx?id=39366)下载它。</span><span class="sxs-lookup"><span data-stu-id="32b68-112">If it's not, you can download it from [the download center](https://www.microsoft.com/download/details.aspx?id=39366).</span></span> <span data-ttu-id="32b68-113">您可以在[为计算机配置 Skype for Business Online 管理](https://technet.microsoft.com/library/dn362839%28v=ocs.15%29.aspx)中找到有关使用此模块的详细信息。</span><span class="sxs-lookup"><span data-stu-id="32b68-113">You can find more information about using this module at [Configuring your computer for Skype for Business Online management](https://technet.microsoft.com/library/dn362839%28v=ocs.15%29.aspx).</span></span>
    
2. <span data-ttu-id="32b68-114">以管理员身份启动 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="32b68-114">Start Windows PowerShell as an administrator.</span></span>
    
3. <span data-ttu-id="32b68-115">键入以下命令，然后按 Enter：</span><span class="sxs-lookup"><span data-stu-id="32b68-115">Type the following and press Enter:</span></span>
    
   ```powershell
   Import-Module skypeonlineconnector
   ```

4. <span data-ttu-id="32b68-116">键入以下命令，然后按 Enter：</span><span class="sxs-lookup"><span data-stu-id="32b68-116">Type the following and press Enter:</span></span>
    
   ```powershell
   $cred = Get-Credential
   ```

    <span data-ttu-id="32b68-117">按 Enter 后，您应该会看到 "Windows PowerShell 凭据" 对话框。</span><span class="sxs-lookup"><span data-stu-id="32b68-117">After you press Enter, you should see the Windows PowerShell Credential dialog box.</span></span>
    
5. <span data-ttu-id="32b68-118">键入租户管理员用户名和密码，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="32b68-118">Type your tenant admin username and password, and click **OK**.</span></span>
    
6. <span data-ttu-id="32b68-119">在 PowerShell 窗口中，键入以下命令，然后按 Enter：</span><span class="sxs-lookup"><span data-stu-id="32b68-119">In the PowerShell window, type the following and press Enter:</span></span>
    
   ```powershell
   $Session = New-CsOnlineSession -Credential $cred -Verbose
   ```

7. <span data-ttu-id="32b68-120">通过键入以下 cmdlet 导入会话：</span><span class="sxs-lookup"><span data-stu-id="32b68-120">Import the session by typing the following cmdlet:</span></span>
    
   ```powershell
   Import-PSSession $Session -AllowClobber
   ```

    <span data-ttu-id="32b68-121">在 Skype for business 服务器上运行 PowerShell 时，在打开 PowerShell 时，本地 Skype for Business cmdlet 已加载。</span><span class="sxs-lookup"><span data-stu-id="32b68-121">When running PowerShell on a Skype for Business Server, the local Skype for Business cmdlets are already loaded when you open PowerShell.</span></span> <span data-ttu-id="32b68-122">您必须指定-AllowClobber 参数，以允许联机 cmdlet 覆盖具有相同名称的本地 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="32b68-122">You must specify the -AllowClobber parameter to allow the online cmdlets to overwrite the on-premises cmdlets with the same name.</span></span>
    
8. <span data-ttu-id="32b68-123">使用 Get-csuser cmdlet 将 $EnterpriseVoiceEnabled 和 $HostedVoiceMail 属性分配给用户，如下所示：</span><span class="sxs-lookup"><span data-stu-id="32b68-123">Use the Set-CsUser cmdlet to assign the $EnterpriseVoiceEnabled and $HostedVoiceMail properties to your user as follows:</span></span>
    
   ```powershell
   Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    <span data-ttu-id="32b68-124">例如：</span><span class="sxs-lookup"><span data-stu-id="32b68-124">For example:</span></span>
    
   ```powershell
   Set-CsUser -Identity "Bob Kelly" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    > [!NOTE]
    > <span data-ttu-id="32b68-125">您还可以通过其 SIP 地址、用户主体名称（UPN）、域名和用户名（域 \ 用户名）以及 Active Directory 中的显示名称（"Bob 凯利"）来指定用户。</span><span class="sxs-lookup"><span data-stu-id="32b68-125">You can also specify a user by their SIP address, User Principal name (UPN), domain name and username (domain\username), and display name in Active Directory ("Bob Kelly").</span></span> 
  
## <a name="update-the-line-uri-and-dial-plan-for-users-enabled-for-phone-system-in-office-365"></a><span data-ttu-id="32b68-126">为 Office 365 中启用了电话系统的用户更新线路 URI 和拨号计划</span><span class="sxs-lookup"><span data-stu-id="32b68-126">Update the Line URI and dial plan for users enabled for Phone System in Office 365</span></span>

<span data-ttu-id="32b68-127">本节介绍如何为在 Office 365 中启用电话系统的用户更新线路 URI 和拨号计划。</span><span class="sxs-lookup"><span data-stu-id="32b68-127">This section describes how to update the Line URI and dial plan for users enabled for Phone System in Office 365.</span></span> 
  
### <a name="to-update-the-line-uri"></a><span data-ttu-id="32b68-128">更新线路 URI</span><span class="sxs-lookup"><span data-stu-id="32b68-128">To update the Line URI</span></span>

1. <span data-ttu-id="32b68-129">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="32b68-129">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="32b68-130">使用 "开始" 菜单或桌面快捷方式打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="32b68-130">Use the Start menu or desktop shortcut to open the Skype for Business Server Control Panel.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="32b68-131">您还可以打开浏览器窗口，然后输入管理员 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="32b68-131">You can also open a browser window, and then enter the Administrator URL to open the Skype for Business Server Control Panel.</span></span> 
  
3. <span data-ttu-id="32b68-132">在左侧导航栏中，单击“用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="32b68-132">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="32b68-133">在“搜索用户”\*\*\*\* 框中，键入要启用的用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="32b68-133">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="32b68-134">在表中，单击要更改行 URI 的 Skype for Business 用户帐户。</span><span class="sxs-lookup"><span data-stu-id="32b68-134">In the table, click the Skype for Business user account that you want to change line URI.</span></span>
    
6. <span data-ttu-id="32b68-135">单击 "**线路 URI**"，然后键入唯一的规范化电话号码（例如，电话： + 14255550200）。</span><span class="sxs-lookup"><span data-stu-id="32b68-135">Click **Line URI**, and type a unique, normalized phone number (for example, tel:+14255550200).</span></span> <span data-ttu-id="32b68-136">然后单击 "**提交**"。</span><span class="sxs-lookup"><span data-stu-id="32b68-136">Then click **Commit**.</span></span>
    
## <a name="update-the-dial-plan-using-on-premises-windows-powershell-cmdlets"></a><span data-ttu-id="32b68-137">使用本地 Windows PowerShell cmdlet 更新拨号计划</span><span class="sxs-lookup"><span data-stu-id="32b68-137">Update the dial plan using on-premises Windows PowerShell cmdlets</span></span>

<span data-ttu-id="32b68-138">您可以使用 Windows PowerShell 和[grant-csdialplan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet 分配每用户拨号计划。</span><span class="sxs-lookup"><span data-stu-id="32b68-138">You can assign per-user dial plans with Windows PowerShell and the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="32b68-139">您可以从 Skype for Business Server 2015 或从 Windows PowerShell 的远程会话中运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="32b68-139">You can run this cmdlet either from the Skype for Business Server 2015 or from a remote session of Windows PowerShell.</span></span>
  
### <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a><span data-ttu-id="32b68-140">为单个用户分配每用户拨号计划</span><span class="sxs-lookup"><span data-stu-id="32b68-140">To assign a per-user dial plan to a single user</span></span>

- <span data-ttu-id="32b68-141">使用[grant-csdialplan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet 可将每用户拨号计划 RedmondDialPlan 分配给用户 Ken Myer：</span><span class="sxs-lookup"><span data-stu-id="32b68-141">Use the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet to assign the per-user dial plan RedmondDialPlan to the user Ken Myer:</span></span>
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"
  ```

### <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a><span data-ttu-id="32b68-142">将每用户拨号计划分配给多个用户</span><span class="sxs-lookup"><span data-stu-id="32b68-142">To assign a per-user dial plan to multiple users</span></span>

- <span data-ttu-id="32b68-143">以下命令将每用户拨号计划 RedmondDialPlan 分配给在 Redmond 市工作的所有用户。</span><span class="sxs-lookup"><span data-stu-id="32b68-143">The following command assigns the per-user dial plan RedmondDialPlan to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="32b68-144">有关此命令中使用的 LdapFilter 参数的详细信息，请参阅[get-csuser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet 的文档：</span><span class="sxs-lookup"><span data-stu-id="32b68-144">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet:</span></span>
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"
  ```

> [!NOTE]
> <span data-ttu-id="32b68-145">您可以为联机用户使用全局或用户拨号计划。</span><span class="sxs-lookup"><span data-stu-id="32b68-145">You may use either Global or User dial plans for online users.</span></span> <span data-ttu-id="32b68-146">无法使用网站拨号计划，因为这些计划仅适用于在本地托管并且分配到本地网站的用户。</span><span class="sxs-lookup"><span data-stu-id="32b68-146">Site dial plans cannot be used as these only apply to users who are hosted on premises and are assigned to an on-premises site.</span></span> 
  
### <a name="to-unassign-a-per-user-dial-plan"></a><span data-ttu-id="32b68-147">取消分配每用户拨号计划</span><span class="sxs-lookup"><span data-stu-id="32b68-147">To unassign a per-user dial plan</span></span>

- <span data-ttu-id="32b68-148">使用[grant-csdialplan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet 可以取消分配之前分配给 Ken Myer 的任何每用户拨号计划。</span><span class="sxs-lookup"><span data-stu-id="32b68-148">Use the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet to unassign any per-user dial plan previously assigned to Ken Myer.</span></span> <span data-ttu-id="32b68-149">未分配每用户拨号计划后，将使用分配给他/她的注册机构或 PSTN 网关的全局拨号计划或服务范围拨号计划自动管理 Ken Myer。</span><span class="sxs-lookup"><span data-stu-id="32b68-149">After the per-user dial plan is unassigned, Ken Myer will automatically be managed by using the global dial plan or the service-scope dial plan assigned to his Registrar or PSTN gateway.</span></span> <span data-ttu-id="32b68-150">服务范围拨号计划优先于全局拨号计划：</span><span class="sxs-lookup"><span data-stu-id="32b68-150">A service scope dial plan takes precedence over the global dial plan:</span></span>
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null
  ```

## <a name="update-the-voice-routing-policies-using-on-premises-windows-powershell-cmdlets"></a><span data-ttu-id="32b68-151">使用本地 Windows PowerShell cmdlet 更新语音路由策略</span><span class="sxs-lookup"><span data-stu-id="32b68-151">Update the voice routing policies using on-premises Windows PowerShell cmdlets</span></span>

<span data-ttu-id="32b68-152">本节介绍如何更新为 Office 365 中的电话系统启用的用户的语音路由策略。</span><span class="sxs-lookup"><span data-stu-id="32b68-152">This section describes how to update the voice routing policies for users enabled for Phone System in Office 365.</span></span>
  
<span data-ttu-id="32b68-153">Office 365 中的电话系统用户必须为其分配一个语音路由策略，以便呼叫能够成功路由。</span><span class="sxs-lookup"><span data-stu-id="32b68-153">Phone System in Office 365 users must have a Voice Routing Policy assigned to them for calls to route successfully.</span></span> <span data-ttu-id="32b68-154">这与需要向其分配语音策略以允许呼叫成功路由的本地业务语音用户不同。</span><span class="sxs-lookup"><span data-stu-id="32b68-154">This differs from on-premises business voice users who require a Voice Policy to be assigned to them to allow calls to route successfully.</span></span> <span data-ttu-id="32b68-155">语音路由策略应包含 PSTN 用法，用于定义适用于 Office 365 用户的电话系统的授权呼叫和路由。</span><span class="sxs-lookup"><span data-stu-id="32b68-155">The Voice Routing Policy should contain PSTN usages that define authorized calls and routes for Phone System in Office 365 users.</span></span> <span data-ttu-id="32b68-156">您可以将这些 PSTN 用法从现有语音策略复制到新的语音路由策略。</span><span class="sxs-lookup"><span data-stu-id="32b68-156">You can copy these PSTN usages from existing Voice Policies to new Voice Routing Policies.</span></span> <span data-ttu-id="32b68-157">有关详细信息，请参阅[grant-csvoiceroutingpolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="32b68-157">For more information, see [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps).</span></span>
  
> [!NOTE]
> <span data-ttu-id="32b68-158">Office 365 用户中的所有电话系统均被分配了名为 BusinessVoice 的相同联机语音策略，用于定义允许的呼叫功能;例如，允许同时响铃。</span><span class="sxs-lookup"><span data-stu-id="32b68-158">All Phone System in Office 365 users are assigned the same online Voice Policy named BusinessVoice which defines the calling features allowed; for example, Allow Simultaneous Ring.</span></span> 
  
### <a name="to-assign-a-per-user-voice-routing-policy-to-a-single-user"></a><span data-ttu-id="32b68-159">向单个用户分配每用户语音路由策略</span><span class="sxs-lookup"><span data-stu-id="32b68-159">To assign a per-user voice routing policy to a single user</span></span>

- <span data-ttu-id="32b68-160">使用[grant-csvoiceroutingpolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) cmdlet 可将每用户语音路由策略 RedmondVoiceRoutingPolicy 分配给用户 Ken Myer：</span><span class="sxs-lookup"><span data-stu-id="32b68-160">Use the [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) cmdlet to assign the per-user voice routing policy RedmondVoiceRoutingPolicy to the user Ken Myer:</span></span>
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName "RedmondVoiceRoutingPolicy"
  ```

### <a name="to-assign-a-per-user-voice-routing-policy-to-multiple-users"></a><span data-ttu-id="32b68-161">为多个用户分配每用户语音路由策略</span><span class="sxs-lookup"><span data-stu-id="32b68-161">To assign a per-user voice routing policy to multiple users</span></span>

- <span data-ttu-id="32b68-162">下一个命令向在 Redmond 市工作的所有用户分配每用户语音路由策略 RedmondVoiceRoutingPolicy。</span><span class="sxs-lookup"><span data-stu-id="32b68-162">The next command assigns the per-user voice routing policy RedmondVoiceRoutingPolicy to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="32b68-163">有关此命令中使用的 LdapFilter 参数的详细信息，请参阅[get-csuser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="32b68-163">For more information on the LdapFilter parameter used in this command, see [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).</span></span>
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsVoiceRoutingPolicy -PolicyName "RedmondVoiceRoutingPolicy"
  ```

    > [!NOTE]
    > <span data-ttu-id="32b68-164">您可以对联机用户使用全局或用户语音路由策略。</span><span class="sxs-lookup"><span data-stu-id="32b68-164">You may use either Global or User voice routing policies for online users.</span></span> <span data-ttu-id="32b68-165">无法使用站点语音路由策略，因为这些策略仅适用于在本地托管并且分配到本地站点的用户。</span><span class="sxs-lookup"><span data-stu-id="32b68-165">Site voice routing policies cannot be used as these only apply to users who are hosted on premises and are assigned to an on-premises site.</span></span> 
  
### <a name="to-unassign-a-per-user-voice-routing-policy"></a><span data-ttu-id="32b68-166">取消分配每用户语音路由策略</span><span class="sxs-lookup"><span data-stu-id="32b68-166">To unassign a per-user voice routing policy</span></span>

- <span data-ttu-id="32b68-167">使用 Grant-csvoiceroutingpolicy 可取消分配之前分配给 Ken Myer 的任何每用户语音路由策略。</span><span class="sxs-lookup"><span data-stu-id="32b68-167">Use the Grant-CsVoiceRoutingPolicy to unassign any per-user voice routing policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="32b68-168">在未分配每用户语音路由策略之后，将自动使用全局语音路由策略管理 Ken Myer。</span><span class="sxs-lookup"><span data-stu-id="32b68-168">After the per-user voice routing policy is unassigned, Ken Myer will automatically be managed by using the global voice routing policy.</span></span>
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

    <span data-ttu-id="32b68-169">有关详细信息，请参阅[grant-csvoiceroutingpolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="32b68-169">For more information, see [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps).</span></span>
    

