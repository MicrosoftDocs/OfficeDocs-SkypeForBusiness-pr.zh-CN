---
title: 将用户从内部部署移动到团队
ms.author: crowe
author: CarolynRowe
manager: serdars--
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: 摘要： 了解如何迁移用户设置并将用户移动到团队。
ms.openlocfilehash: 78f0c49fa2179b4a0aa95a993476c21fb679f489
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2018
ms.locfileid: "26293563"
---
# <a name="move-users-from-on-premises-to-teams"></a><span data-ttu-id="a1759-103">将用户从内部部署移动到团队</span><span class="sxs-lookup"><span data-stu-id="a1759-103">Move users from on-premises to Teams</span></span>

<span data-ttu-id="a1759-104">与业务服务器 2019年的 Skype，可以将内部部署用户迁移到团队这篇文章中所述。</span><span class="sxs-lookup"><span data-stu-id="a1759-104">With Skype for Business Server 2019, you can migrate your on-premises users to Teams as described in this article.</span></span>

<span data-ttu-id="a1759-105">请注意，之后将您的用户移动到团队：</span><span class="sxs-lookup"><span data-stu-id="a1759-105">Be aware that after moving your users to Teams:</span></span> 
 
- <span data-ttu-id="a1759-106">他们的会议都将迁移到 Skype online 业务和联系人都将迁移到团队。</span><span class="sxs-lookup"><span data-stu-id="a1759-106">Their meetings are migrated to Skype for Business Online, and their contacts are migrated to Teams.</span></span> 
- <span data-ttu-id="a1759-107">他们可以加入 Skype 会议通过业务富客户端 （用户不会提示登录每次） 的 Skype 或 Skype 会议应用程序 （需要一次性下载和登录）。</span><span class="sxs-lookup"><span data-stu-id="a1759-107">They can join Skype meetings through the Skype for Business rich client (users are not prompted for sign-in each time) or through the Skype Meetings App (requires a one-time download and sign-in).</span></span> <span data-ttu-id="a1759-108">当用户单击团队中的业务会议链接 Skype 时，将在相应的应用程序中启动会议。</span><span class="sxs-lookup"><span data-stu-id="a1759-108">When a user clicks on a Skype for Business meeting link within Teams, the meeting will launch in the appropriate app.</span></span>

- <span data-ttu-id="a1759-109">移动，在您的用户将能够加入现有 Skype 业务会议使用本机应用程序。</span><span class="sxs-lookup"><span data-stu-id="a1759-109">On Mobile, your users will be able to join existing Skype for Business meetings using the native app only.</span></span>

> [!NOTE]
> <span data-ttu-id="a1759-110">将用户移动到 TeamsOnly 模式后，用户在 Skype 驻留业务 online 中。</span><span class="sxs-lookup"><span data-stu-id="a1759-110">After a user is moved to TeamsOnly mode, the user is homed in Skype for Business Online.</span></span>

## <a name="prerequisites-for-moving-on-premises-users-to-teams"></a><span data-ttu-id="a1759-111">将内部部署用户移动到团队的先决条件</span><span class="sxs-lookup"><span data-stu-id="a1759-111">Prerequisites for moving on-premises users to Teams</span></span> 

<span data-ttu-id="a1759-112">本节介绍用于将内部部署用户移到团队系统必备组件。</span><span class="sxs-lookup"><span data-stu-id="a1759-112">This section describes the prerequisites for moving your on-premises users to Teams.</span></span> <span data-ttu-id="a1759-113">您必须：</span><span class="sxs-lookup"><span data-stu-id="a1759-113">You must:</span></span>
- <span data-ttu-id="a1759-114">[设置混合连接性](#set-up-hybrid-connectivity)（如果您尚未这样)</span><span class="sxs-lookup"><span data-stu-id="a1759-114">[Set up hybrid connectivity](#set-up-hybrid-connectivity) (if you have not already done so)</span></span>
- <span data-ttu-id="a1759-115">[通知用户的移动到团队](#notify-your-users-of-the-move-to-teams)（可选）</span><span class="sxs-lookup"><span data-stu-id="a1759-115">[Notify your users of the move to Teams](#notify-your-users-of-the-move-to-teams) (optional)</span></span>
- [<span data-ttu-id="a1759-116">确保您的用户具有有效的许可证</span><span class="sxs-lookup"><span data-stu-id="a1759-116">Ensure that your users have a valid license</span></span>](#make-sure-your-users-have-a-valid-license)
- [<span data-ttu-id="a1759-117">注意的语音配置要求</span><span class="sxs-lookup"><span data-stu-id="a1759-117">Be aware of voice configuration requirements</span></span>](#voice-configuration-requirements)
- <span data-ttu-id="a1759-118">[分配团队升级策略](#assign-a-teams-upgrade-policy)（可选）</span><span class="sxs-lookup"><span data-stu-id="a1759-118">[Assign a Teams Upgrade policy](#assign-a-teams-upgrade-policy) (optional)</span></span>

## <a name="set-up-hybrid-connectivity"></a><span data-ttu-id="a1759-119">设置混合连接性</span><span class="sxs-lookup"><span data-stu-id="a1759-119">Set up hybrid connectivity</span></span>
<span data-ttu-id="a1759-120">如果您未迁移用户之前，必须确保您已配置您的业务服务器内部部署环境的 Skype 和 Skype 业务 online 之间的混合连接性。</span><span class="sxs-lookup"><span data-stu-id="a1759-120">Before you migrate your users, if you have not already done so, you must ensure that you have configured hybrid connectivity between your Skype for Business Server on-premises environment and Skype for Business Online.</span></span> <span data-ttu-id="a1759-121">混合连接需要 Active Directory 同步、 配置联合身份验证，等等。</span><span class="sxs-lookup"><span data-stu-id="a1759-121">Hybrid connectivity requires Active Directory synchronization, configuring federation, and so on.</span></span> <span data-ttu-id="a1759-122">有关详细信息，请参阅[规划混合连接性](plan-hybrid-connectivity.md)和[配置混合连接性](configure-hybrid-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="a1759-122">For more information, see [Plan hybrid connectivity](plan-hybrid-connectivity.md) and [Configure hybrid connectivity](configure-hybrid-connectivity.md).</span></span>

## <a name="notify-your-users-of-the-move-to-teams"></a><span data-ttu-id="a1759-123">通知用户的移动到团队</span><span class="sxs-lookup"><span data-stu-id="a1759-123">Notify your users of the move to Teams</span></span> 
<span data-ttu-id="a1759-124">这是一个可选步骤，但您应考虑的一个。</span><span class="sxs-lookup"><span data-stu-id="a1759-124">This is an optional step, but one that you should consider.</span></span> <span data-ttu-id="a1759-125">通知用户的待处理的团队升级，您可以使用本地 TeamsUpgradePolicy 和 TeamsUpgradeConfiguration cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a1759-125">To notify users of the pending Teams upgrade, you can use the on-premises TeamsUpgradePolicy and TeamsUpgradeConfiguration cmdlets.</span></span> <span data-ttu-id="a1759-126">您还可以在后台之前升级 （仅 Win32 客户端） 配置的团队的无提示自动下载。</span><span class="sxs-lookup"><span data-stu-id="a1759-126">You can also configure silent auto-download of Teams in the background prior to upgrade (Win32 clients only).</span></span> 

<span data-ttu-id="a1759-127">例如，通知用户，他们正在升级到团队，使用内部部署 TeamsUpgradePolicy cmdlet-NotifySbUser 参数。</span><span class="sxs-lookup"><span data-stu-id="a1759-127">For example, to notify users that they are being upgraded to Teams, use the on-premises TeamsUpgradePolicy cmdlet with the -NotifySbUser parameter.</span></span> <span data-ttu-id="a1759-128">您可以在全局、 站点、 池或用户级别设置策略。</span><span class="sxs-lookup"><span data-stu-id="a1759-128">You can set the policy on a global, site, pool, or user level.</span></span> <span data-ttu-id="a1759-129">以下命令创建并授予用户级别策略：</span><span class="sxs-lookup"><span data-stu-id="a1759-129">The following command creates and grants a user-level policy:</span></span>
 
```
New-CsTeamsUpgradePolicy -Identity UpgradeNotice -NotifySfbUser $true 
Grant-CsTeamsUpgradePolicy -Identity user01 -PolicyName “UpgradeNotice”
```

<span data-ttu-id="a1759-130">您可以通过使用 Get-csTeamsUpgradePolicy cmdlet 来检查此策略。</span><span class="sxs-lookup"><span data-stu-id="a1759-130">You can check this policy by using the Get-csTeamsUpgradePolicy cmdlet.</span></span>

<span data-ttu-id="a1759-131">您的用户将看到即将移动到团队的通知。</span><span class="sxs-lookup"><span data-stu-id="a1759-131">Your users will see a notification of the impending move to Teams.</span></span> <span data-ttu-id="a1759-132">该通知出现在 Win32、 Mac、 Mobile 以及 Web 客户端 （使用正确的版本中）。</span><span class="sxs-lookup"><span data-stu-id="a1759-132">The notification occurs on Win32, Mac, Mobile, and Web Clients (with the right version).</span></span>

<span data-ttu-id="a1759-133">您可以指定与 DownloadTeams 参数一起使用的本地 TeamsUpgradeConfiguration cmdlet 正在升级的用户自动下载团队 （对于 Win32 客户端）。</span><span class="sxs-lookup"><span data-stu-id="a1759-133">You can specify automatic download of Teams (for Win32 clients) for users being upgraded by using the on-premises TeamsUpgradeConfiguration cmdlet with the DownloadTeams parameter.</span></span> <span data-ttu-id="a1759-134">租户级别设置此策略，而且可应用于全局、 站点和池级。</span><span class="sxs-lookup"><span data-stu-id="a1759-134">You set this policy at the tenant level, and it can be applied on a global, site, and pool level.</span></span> <span data-ttu-id="a1759-135">例如，以下命令在网站级别设置的策略：</span><span class="sxs-lookup"><span data-stu-id="a1759-135">For example, the following command sets the policy at the site level:</span></span>

```
New-CsTeamsUpgradeConfiguration -Identity “site:redmond1” 
```

<span data-ttu-id="a1759-136">默认情况下 DownloadTeams 的值为 true 时，但您还必须设置为 True 可为给定的用户启用团队 NotifySfbUser。</span><span class="sxs-lookup"><span data-stu-id="a1759-136">By default, the value of DownloadTeams is True, but you must also set NotifySfbUser to True to enable Teams for a given user.</span></span> 

## <a name="make-sure-your-users-have-a-valid-license"></a><span data-ttu-id="a1759-137">请确保您的用户具有有效的许可证</span><span class="sxs-lookup"><span data-stu-id="a1759-137">Make sure your users have a valid license</span></span>  
<span data-ttu-id="a1759-138">在迁移之前的本地用户必须有有效的许可证，，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a1759-138">Before migration, the on-premises user must be given a valid license, as follows:</span></span>

-   <span data-ttu-id="a1759-139">用户必须拥有团队许可证。</span><span class="sxs-lookup"><span data-stu-id="a1759-139">User must have a Teams license.</span></span>
-   <span data-ttu-id="a1759-140">如果对用户配置为使用内部部署企业语音，它们必须具有联机语音许可证，移动时。</span><span class="sxs-lookup"><span data-stu-id="a1759-140">If the user is configured to use on-premises Enterprise Voice, they must have an online voice license when moving.</span></span> 
-   <span data-ttu-id="a1759-141">如果用户的本地电话拨入式会议配置，它们必须具有许可证的电话系统 (云 PBX)。</span><span class="sxs-lookup"><span data-stu-id="a1759-141">If the user is configured for on-premises dial-in conferencing, they must have a license for Phone System (Cloud PBX).</span></span>

## <a name="voice-configuration-requirements"></a><span data-ttu-id="a1759-142">语音配置要求</span><span class="sxs-lookup"><span data-stu-id="a1759-142">Voice configuration requirements</span></span>

<span data-ttu-id="a1759-143">如果您在本地用户具有内部部署语音，您有两个选项：</span><span class="sxs-lookup"><span data-stu-id="a1759-143">If your on-premises users have on-premises voice, you have two options:</span></span>

-  <span data-ttu-id="a1759-144">**将具有电话功能的用户迁移。**</span><span class="sxs-lookup"><span data-stu-id="a1759-144">**Migrate users with telephony capabilities.**</span></span> <span data-ttu-id="a1759-145">用户可以发起和接收呼叫使用团队客户端。</span><span class="sxs-lookup"><span data-stu-id="a1759-145">Users can make and receive calls using the Teams client.</span></span>  <span data-ttu-id="a1759-146">您可以选择 Microsoft 调用规划或直接路由连接到团队的电话服务。</span><span class="sxs-lookup"><span data-stu-id="a1759-146">You can choose either Microsoft Calling Plan or Direct Routing to connect the telephony services to Teams.</span></span>  

    -  <span data-ttu-id="a1759-147">规划 Microsoft 调用提供了一云语音解决方案。</span><span class="sxs-lookup"><span data-stu-id="a1759-147">Microsoft Calling Plan provides an all-in-the-cloud voice solution.</span></span> <span data-ttu-id="a1759-148">有关 Microsoft 调用规划的详细信息，请参阅 （即将推出的链接）。</span><span class="sxs-lookup"><span data-stu-id="a1759-148">For more information about Microsoft Calling Plan, see (link coming soon).</span></span> 
    -  <span data-ttu-id="a1759-149">直接路由允许您使用几乎任何 PSTN 中继，并且您可以配置客户拥有电话设备和 Microsoft 电话系统之间的互操作性。</span><span class="sxs-lookup"><span data-stu-id="a1759-149">Direct Routing lets you use virtually any PSTN trunk,  and you can configure interoperability between customer-owned telephony equipment and Microsoft Phone System.</span></span>  <span data-ttu-id="a1759-150">有关详细信息，请参阅[规划直接路由](https://docs.microsoft.com/en-us/MicrosoftTeams/direct-routing-plan)和[配置直接路由](https://docs.microsoft.com/en-us/MicrosoftTeams/direct-routing-configure)。</span><span class="sxs-lookup"><span data-stu-id="a1759-150">For more information, see [Plan Direct Routing](https://docs.microsoft.com/en-us/MicrosoftTeams/direct-routing-plan) and [Configure Direct Routing](https://docs.microsoft.com/en-us/MicrosoftTeams/direct-routing-configure).</span></span>

-  <span data-ttu-id="a1759-151">**迁移用户不带电话功能。**</span><span class="sxs-lookup"><span data-stu-id="a1759-151">**Migrate users without telephony capabilities.**</span></span> <span data-ttu-id="a1759-152">如果将用户迁移而不保留电话功能，请确保用户在云中有相应的许可证。</span><span class="sxs-lookup"><span data-stu-id="a1759-152">If you migrate users without preserving  telephony capabilities, make sure users have appropriate licenses in the cloud.</span></span> 

## <a name="assign-a-teams-upgrade-policy"></a><span data-ttu-id="a1759-153">分配团队升级策略</span><span class="sxs-lookup"><span data-stu-id="a1759-153">Assign a Teams Upgrade policy</span></span>  
<span data-ttu-id="a1759-154">在线工具可用于管理如用户策略控制的传入邮件和呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="a1759-154">You can use online tools to manage user policies, such as to control routing of incoming messages and calls.</span></span> <span data-ttu-id="a1759-155">有关详细信息，请参阅 （即将推出的链接）。</span><span class="sxs-lookup"><span data-stu-id="a1759-155">For more information, see (link coming soon).</span></span>

## <a name="move-on-premises-users-to-teams"></a><span data-ttu-id="a1759-156">将内部部署用户移至团队</span><span class="sxs-lookup"><span data-stu-id="a1759-156">Move on-premises users to Teams</span></span>

<span data-ttu-id="a1759-157">使用 PowerShell cmdlet 或使用 Skype 业务 Server 2019 控制面板，则可以移到团队内部部署用户。</span><span class="sxs-lookup"><span data-stu-id="a1759-157">You can move your on-premises users to Teams by using PowerShell cmdlets or by using the Skype for Business Server 2019 Control Panel.</span></span>

### <a name="move-users-by-using-powershell"></a><span data-ttu-id="a1759-158">使用 PowerShell 移动用户</span><span class="sxs-lookup"><span data-stu-id="a1759-158">Move users by using PowerShell</span></span>
<span data-ttu-id="a1759-159">使用 PowerShell 将用户移动到团队中，您将使用 moveToTeams 参数，如下所示使用 Move-csuser cmdlet:</span><span class="sxs-lookup"><span data-stu-id="a1759-159">To move your users to Teams by using PowerShell, you’ll use the Move-CsUser cmdlet with the moveToTeams parameter as follows:</span></span>

```
Move-CsUser -Identity user0 -Target sipfed.online.lync.com -moveToTeams -credentials $cred. 
```

<span data-ttu-id="a1759-160">($cred = 获取凭据。</span><span class="sxs-lookup"><span data-stu-id="a1759-160">($cred = get-Credentials.</span></span> <span data-ttu-id="a1759-161">您必须提供 Office 365 管理员凭据。）</span><span class="sxs-lookup"><span data-stu-id="a1759-161">You must provide Office 365 admin credentials.)</span></span>

> [!NOTE]
> <span data-ttu-id="a1759-162">此命令将 TeamsInteropPolicy 设置为团队，并将 TeamsUpgradePolicy 设置为 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="a1759-162">This command sets the TeamsInteropPolicy to Teams and sets the TeamsUpgradePolicy to TeamsOnly mode.</span></span> 
 
<span data-ttu-id="a1759-163">向工作组移动成功后，业务客户端的用户的 Skype 将显示以下消息：</span><span class="sxs-lookup"><span data-stu-id="a1759-163">After the move to Teams is successful, the user’s Skype for Business client will display the following message:</span></span> 

![成功迁移到团队消息](../media/teams-upgrade-complete-message.png)

<span data-ttu-id="a1759-165">请注意，Skype for Business 将不再除以加入会议的用户。</span><span class="sxs-lookup"><span data-stu-id="a1759-165">Note that Skype for Business will no longer be available to the user except to join a meeting.</span></span> 

<span data-ttu-id="a1759-166">在极少数情况下，将用户移动到团队时，您可能想要重写电话拨入式会议和云语音功能。</span><span class="sxs-lookup"><span data-stu-id="a1759-166">In rare cases, when moving your users to Teams, you might want to override dial-in conferencing and cloud voice functionality.</span></span> <span data-ttu-id="a1759-167">可以使用 Move-csuser 命令具有以下参数执行此操作：</span><span class="sxs-lookup"><span data-stu-id="a1759-167">You can do this by using the following parameters with the Move-CsUser command:</span></span>
- <span data-ttu-id="a1759-168">**BypassAudioConferencingCheck:** 如果用户具有启用内部部署的电话拨入式会议，用户还必须在迁移之前分配 Office 365 中的 AudioConf 许可证。</span><span class="sxs-lookup"><span data-stu-id="a1759-168">**BypassAudioConferencingCheck:** If a user has dial-in conferencing enabled for on-premises, the user must also have an AudioConf license assigned in Office 365 before migrating.</span></span> <span data-ttu-id="a1759-169">一旦迁移到云中，将在云中的音频会议设置的用户。</span><span class="sxs-lookup"><span data-stu-id="a1759-169">Once migrated to the cloud, the user will be provisioned for audio conferencing in the cloud.</span></span> <span data-ttu-id="a1759-170">如果由于某种原因，您想要将用户移动到云，但不是使用的音频会议功能，您可以通过指定此参数覆盖它。</span><span class="sxs-lookup"><span data-stu-id="a1759-170">If, for some reason, you want to move a user to the cloud, but not use the audio conferencing functionality, you can override it by specifying this parameter.</span></span>
- <span data-ttu-id="a1759-171">**ByPassEnterpriseVoice:** 如果用户具有启用内部部署企业语音，用户必须在迁移之前分配 Office 365 中的企业语音许可证。</span><span class="sxs-lookup"><span data-stu-id="a1759-171">**ByPassEnterpriseVoice:** If a user has Enterprise Voice enabled for on-premises, the user must have an Enterprise Voice license assigned in Office 365 before migrating.</span></span> <span data-ttu-id="a1759-172">迁移到云中之后, 将云中的语音设置的用户。</span><span class="sxs-lookup"><span data-stu-id="a1759-172">After migration to the cloud, the user will be provisioned for voice in the cloud.</span></span> <span data-ttu-id="a1759-173">如果由于某种原因，您想要将用户移动到云，但不是使用云语音功能，您可以通过指定此参数覆盖云语音。</span><span class="sxs-lookup"><span data-stu-id="a1759-173">If, for some reason, you want to move a user to the cloud but not use cloud voice functionality, you can override cloud voice by specifying this parameter.</span></span>
 
### <a name="move-users-by-using-the-skype-for-business-server-control-panel"></a><span data-ttu-id="a1759-174">使用 Skype 业务 Server 控制面板移动用户</span><span class="sxs-lookup"><span data-stu-id="a1759-174">Move users by using the Skype for Business Server Control Panel</span></span> 

<span data-ttu-id="a1759-175">若要将用户移至团队使用 Skype 业务控制面板：</span><span class="sxs-lookup"><span data-stu-id="a1759-175">To move users to Teams by using the Skype for Business Control Panel:</span></span>

1. <span data-ttu-id="a1759-176">打开业务 Control Panel Skype 和登录到 Office 365 帐户。</span><span class="sxs-lookup"><span data-stu-id="a1759-176">Open the Skype for Business Control Panel and sign in to your Office 365 account.</span></span>

2. <span data-ttu-id="a1759-177">在左侧导航窗格中，选择**用户**，然后选择要迁移用户。</span><span class="sxs-lookup"><span data-stu-id="a1759-177">Select **Users** in the left navigation, and select the users to migrate.</span></span> 
     
3. <span data-ttu-id="a1759-178">在**操作**菜单中，选择**移动到团队的所选的用户**。</span><span class="sxs-lookup"><span data-stu-id="a1759-178">On the **Action** menu, choose **Move selected users to Teams**.</span></span> 

    ![单击下一步以确认迁移](../media/migration-confirmation.png)
    
4. <span data-ttu-id="a1759-180">单击**下一步**以确认您的迁移。</span><span class="sxs-lookup"><span data-stu-id="a1759-180">Click **Next** to confirm your migration.</span></span> 

<span data-ttu-id="a1759-181">用户移动到团队后，您将看到类似如下的确认：</span><span class="sxs-lookup"><span data-stu-id="a1759-181">After the user is moved to Teams, you will see  confirmations like the following:</span></span>

<span data-ttu-id="a1759-182">![移动用户确认](../media/move-user-confirmation.png)
</span><span class="sxs-lookup"><span data-stu-id="a1759-182">![Move users confirmation](../media/move-user-confirmation.png)
</span></span><br/><br/>
<span data-ttu-id="a1759-183">![邮件已移动用户](../media/users-moved-successfully.png)</span><span class="sxs-lookup"><span data-stu-id="a1759-183">![Message that users have been moved](../media/users-moved-successfully.png)</span></span>

<span data-ttu-id="a1759-184">如果移动不成功，您将看到以下消息：</span><span class="sxs-lookup"><span data-stu-id="a1759-184">If the move was not successful, you will see a message like the following:</span></span>

![邮件的用户无法移动](../media/users-not-moved.png)
