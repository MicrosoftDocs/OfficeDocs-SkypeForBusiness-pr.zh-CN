---
title: 为用户启用直接路由
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 了解如何启用用户 Microsoft Phone 系统直接路由。
ms.openlocfilehash: 972bd8d5e01a050a67978560b8de272439fda40d
ms.sourcegitcommit: 6f7b91f573e2a034f8c5474be2c5cb2971f4b5ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "50421307"
---
# <a name="enable-users-for-direct-routing-voice-and-voicemail"></a><span data-ttu-id="a32d9-103">为用户启用直接路由、语音和语音邮件</span><span class="sxs-lookup"><span data-stu-id="a32d9-103">Enable users for Direct Routing, voice, and voicemail</span></span>

<span data-ttu-id="a32d9-104">本文介绍如何为用户启用电话系统直接路由。</span><span class="sxs-lookup"><span data-stu-id="a32d9-104">This article describes how to enable users for Phone System Direct Routing.</span></span>  <span data-ttu-id="a32d9-105">这是配置直接路由的以下步骤的步骤 2：</span><span class="sxs-lookup"><span data-stu-id="a32d9-105">This is step 2 of the following steps for configuring Direct Routing:</span></span>

- <span data-ttu-id="a32d9-106">第 1 步</span><span class="sxs-lookup"><span data-stu-id="a32d9-106">Step 1.</span></span> [<span data-ttu-id="a32d9-107">将 SBC 与 Microsoft Phone System 连接并验证连接</span><span class="sxs-lookup"><span data-stu-id="a32d9-107">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md) 
- <span data-ttu-id="a32d9-108">**步骤 2.为用户启用直接路由、语音和语音邮件**   (本文) </span><span class="sxs-lookup"><span data-stu-id="a32d9-108">**Step 2. Enable users for Direct Routing, voice, and voicemail**   (this article)</span></span>
- <span data-ttu-id="a32d9-109">第 3 步</span><span class="sxs-lookup"><span data-stu-id="a32d9-109">Step 3.</span></span> [<span data-ttu-id="a32d9-110">配置语音路由</span><span class="sxs-lookup"><span data-stu-id="a32d9-110">Configure voice routing</span></span>](direct-routing-voice-routing.md)
- <span data-ttu-id="a32d9-111">第 4 步</span><span class="sxs-lookup"><span data-stu-id="a32d9-111">Step 4.</span></span> [<span data-ttu-id="a32d9-112">将数字转换为备用格式</span><span class="sxs-lookup"><span data-stu-id="a32d9-112">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 


<span data-ttu-id="a32d9-113">有关设置直接路由所需的所有步骤的信息，请参阅"配置[直接路由"。](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="a32d9-113">For information on all the steps required for setting up Direct Routing, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

<span data-ttu-id="a32d9-114">准备好为用户启用直接路由时，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="a32d9-114">When you are ready to enable users for Direct Routing, follow these steps:</span></span> 

1. <span data-ttu-id="a32d9-115">在 Microsoft 365 或 Office 365 中创建用户并分配电话系统许可证。</span><span class="sxs-lookup"><span data-stu-id="a32d9-115">Create a user in Microsoft 365 or Office 365 and assign a Phone System license.</span></span> 
2. <span data-ttu-id="a32d9-116">确保用户位于 Skype for Business Online 中。</span><span class="sxs-lookup"><span data-stu-id="a32d9-116">Ensure that the user is homed in Skype for Business Online.</span></span> 
3. <span data-ttu-id="a32d9-117">配置电话号码并启用企业语音和语音邮件。</span><span class="sxs-lookup"><span data-stu-id="a32d9-117">Configure the phone number and enable enterprise voice and voicemail.</span></span> 
4. <span data-ttu-id="a32d9-118">向用户分配"仅 Teams"模式。</span><span class="sxs-lookup"><span data-stu-id="a32d9-118">Assign Teams Only mode to users.</span></span>

## <a name="create-a-user-and-assign-the-license"></a><span data-ttu-id="a32d9-119">创建用户并分配许可证</span><span class="sxs-lookup"><span data-stu-id="a32d9-119">Create a user and assign the license</span></span> 

<span data-ttu-id="a32d9-120">有两个选项用于在 Microsoft 365 或 Office 365 中创建新用户。</span><span class="sxs-lookup"><span data-stu-id="a32d9-120">There are two options for creating a new user in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="a32d9-121">但是，Microsoft 建议组织选择一个选项以避免路由问题：</span><span class="sxs-lookup"><span data-stu-id="a32d9-121">However, Microsoft recommends that your organization choose one option to avoid routing issues:</span></span> 

- <span data-ttu-id="a32d9-122">在本地 Active Directory 中创建用户，将该用户同步到云。</span><span class="sxs-lookup"><span data-stu-id="a32d9-122">Create the user in on-premises Active Directory and sync the user to the cloud.</span></span> <span data-ttu-id="a32d9-123">请参阅["将本地目录与 Azure Active Directory 集成"。](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)</span><span class="sxs-lookup"><span data-stu-id="a32d9-123">See [Integrate your on-premises directories with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>
- <span data-ttu-id="a32d9-124">直接在 Microsoft 365 管理中心创建用户。</span><span class="sxs-lookup"><span data-stu-id="a32d9-124">Create the user directly in the Microsoft 365 admin center.</span></span> <span data-ttu-id="a32d9-125">请参阅["将用户单独或批量添加到 Microsoft 365 或 Office 365 - 管理员帮助"。](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)</span><span class="sxs-lookup"><span data-stu-id="a32d9-125">See [Add users individually or in bulk to Microsoft 365 or Office 365 - Admin Help](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span> 

<span data-ttu-id="a32d9-126">如果 Skype for Business Online 部署与本地 Skype for Business 2015 或 Lync 2010 或 2013 共存，则唯一支持的选项是在本地 Active Directory 创建用户，将用户同步到云 (选项 1) 。</span><span class="sxs-lookup"><span data-stu-id="a32d9-126">If your Skype for Business Online deployment coexists with Skype for Business 2015 or Lync 2010 or 2013 on-premises, the only supported option is to create the user in the on-premises Active Directory and sync the user to the cloud (Option 1).</span></span> 

<span data-ttu-id="a32d9-127">有关许可证要求的信息，请参阅 [计划直接路由中的](direct-routing-plan.md#licensing-and-other-requirements) 许可 [和其他要求](direct-routing-plan.md)。</span><span class="sxs-lookup"><span data-stu-id="a32d9-127">For information about license requirements, see [licensing and other requirements](direct-routing-plan.md#licensing-and-other-requirements) in [Plan Direct Routing](direct-routing-plan.md).</span></span>

## <a name="ensure-that-the-user-is-homed-online-and-phone-number-is-not-being-synced-from-on-premises-applicable-for-skype-for-business-server-enterprise-voice-enabled-users-being-migrated-to-teams-direct-routing"></a><span data-ttu-id="a32d9-128">确保用户是在线家庭用户且电话号码未从本地 (同步，而该本地 (适用于启用了 Skype for Business Server 企业语音 且正在迁移到 Teams Direct Routing) </span><span class="sxs-lookup"><span data-stu-id="a32d9-128">Ensure that the user is homed online and phone number is not being synced from on-premises (applicable for Skype for Business Server Enterprise Voice enabled users being migrated to Teams Direct Routing)</span></span>

<span data-ttu-id="a32d9-129">直接路由要求用户联机进行家庭管理。</span><span class="sxs-lookup"><span data-stu-id="a32d9-129">Direct Routing requires the user to be homed online.</span></span> <span data-ttu-id="a32d9-130">可以通过查看 RegistrarPool 参数来检查，该参数需要在 infra.lync.com 中。</span><span class="sxs-lookup"><span data-stu-id="a32d9-130">You can check by looking at the RegistrarPool parameter, which needs to have a value in the infra.lync.com domain.</span></span> <span data-ttu-id="a32d9-131">OnPremLineUriManuallySet 参数也应设置为 True。</span><span class="sxs-lookup"><span data-stu-id="a32d9-131">OnPremLineUriManuallySet parameter should also to be set to True.</span></span> <span data-ttu-id="a32d9-132">这是通过使用 Skype for Business Online PowerShell 配置电话号码并启用企业语音和语音邮件实现的。</span><span class="sxs-lookup"><span data-stu-id="a32d9-132">This is achieved by configuring the phone number and enable enterprise voice and voicemail using Skype for Business Online PowerShell.</span></span>

1. <span data-ttu-id="a32d9-133">连接 Skype for Business Online PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="a32d9-133">Connect a Skype for Business Online PowerShell session.</span></span>

2. <span data-ttu-id="a32d9-134">发出命令：</span><span class="sxs-lookup"><span data-stu-id="a32d9-134">Issue the command:</span></span> 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri
    ``` 
    <span data-ttu-id="a32d9-135">如果 OnPremLineUriManuallySet 设置为 False 且 LineUri 填充了 <E.164 电话号码>，请在使用 Skype for Business Online PowerShell 配置电话号码之前，使用本地 Skype for Business 命令行管理程序清理参数。</span><span class="sxs-lookup"><span data-stu-id="a32d9-135">In case OnPremLineUriManuallySet is set to False and LineUri is populated with a <E.164 phone number>, please clean the parameters using on-premises Skype for Business Management Shell, before configuring the phone number using Skype for Business Online PowerShell.</span></span> 

1. <span data-ttu-id="a32d9-136">从 Skype for Business 命令行管理程序发出以下命令：</span><span class="sxs-lookup"><span data-stu-id="a32d9-136">From Skype for Business Management Shell issue the command:</span></span> 

   ```PowerShell
   Set-CsUser -Identity "<User name>" -LineUri $null -EnterpriseVoiceEnabled $False -HostedVoiceMail $False
    ``` 
   <span data-ttu-id="a32d9-137">将更改同步到 Office 365 后，预期输出 `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` 为：</span><span class="sxs-lookup"><span data-stu-id="a32d9-137">After the changes have synced to Office 365 the expected output of `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` would be:</span></span>

   ```console
   RegistrarPool                        : pool.infra.lync.com
   OnPremLineURIManuallySet             : True
   OnPremLineURI                        : 
   LineURI                              : 
   ```

## <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a><span data-ttu-id="a32d9-138">配置电话号码并启用企业语音和语音邮件</span><span class="sxs-lookup"><span data-stu-id="a32d9-138">Configure the phone number and enable enterprise voice and voicemail</span></span> 

<span data-ttu-id="a32d9-139">创建用户并分配许可证后，下一步是配置用户的电话号码和语音邮件。</span><span class="sxs-lookup"><span data-stu-id="a32d9-139">After you have created the user and assigned a license, the next step is to configure the user's phone number and voicemail.</span></span> 

<span data-ttu-id="a32d9-140">添加电话号码并启用语音邮件：</span><span class="sxs-lookup"><span data-stu-id="a32d9-140">To add the phone number and enable for voicemail:</span></span>
 
1. <span data-ttu-id="a32d9-141">连接 Skype for Business Online PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="a32d9-141">Connect a Skype for Business Online PowerShell session.</span></span> 

2. <span data-ttu-id="a32d9-142">发出命令：</span><span class="sxs-lookup"><span data-stu-id="a32d9-142">Issue the command:</span></span> 
 
    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<phone number>
    ```
    
    <span data-ttu-id="a32d9-143">例如，若要为用户"Spencer Low"添加电话号码，请输入以下代码：</span><span class="sxs-lookup"><span data-stu-id="a32d9-143">For example, to add a phone number for user "Spencer Low," enter the following:</span></span> 

    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```
    <span data-ttu-id="a32d9-144">如果用户"Spencer Low"和"Stacy Quinn"共享同一个具有唯一扩展名的基号，请输入以下代码</span><span class="sxs-lookup"><span data-stu-id="a32d9-144">If the users "Spencer Low" and "Stacy Quinn" share the same base number with unique extensions, enter the following</span></span>
    
    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388701;ext=1001 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    Set-CsUser -Identity "stacy.quinn@contoso.com" -OnPremLineURI tel:+14255388701;ext=1002 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```

    <span data-ttu-id="a32d9-145">建议但不要求将使用的电话号码配置为完整的 E.164 电话号码以及国家/地区代码。</span><span class="sxs-lookup"><span data-stu-id="a32d9-145">It's recommended, but not required, that the phone number used is configured as a full E.164 phone number with country code.</span></span> <span data-ttu-id="a32d9-146">支持使用分机号配置电话号码，当针对基本号码的查找返回多个结果时，将用来查找用户。</span><span class="sxs-lookup"><span data-stu-id="a32d9-146">It is supported to configure phone numbers with extensions which will be used to lookup users when the lookup against the base number returns more than one result.</span></span> <span data-ttu-id="a32d9-147">这允许公司使用相同的基本号码和唯一分机号配置电话号码。</span><span class="sxs-lookup"><span data-stu-id="a32d9-147">This allows companies to configure phone numbers with the same base number and unique extensions.</span></span> <span data-ttu-id="a32d9-148">若要成功查找，邀请必须包含完整的扩展号，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a32d9-148">For lookup to be successful, the invite must include the full number with extension as follows:</span></span>
    ```PowerShell
    To: <sip:+14255388701;ext=1001@sbc1.adatum.biz
    ```
    
    > [!NOTE]
    > <span data-ttu-id="a32d9-149">如果用户的电话号码在本地管理，请使用本地 Skype for Business 命令行管理程序或控制面板来配置用户的电话号码。</span><span class="sxs-lookup"><span data-stu-id="a32d9-149">If the user’s phone number is managed on premises, use on-premises Skype for Business Management Shell or Control Panel to configure the user's phone number.</span></span> 


## <a name="configuring-sending-calls-directly-to-voicemail"></a><span data-ttu-id="a32d9-150">配置将呼叫直接发送到语音邮件</span><span class="sxs-lookup"><span data-stu-id="a32d9-150">Configuring sending calls directly to voicemail</span></span>

<span data-ttu-id="a32d9-151">直接路由允许你结束对用户的呼叫，并将其直接发送到用户的语音邮件。</span><span class="sxs-lookup"><span data-stu-id="a32d9-151">Direct Routing allows you to end the call to a user and send it directly to the user's voicemail.</span></span> <span data-ttu-id="a32d9-152">如果要将呼叫直接发送到语音邮件，请将 opaque=app：voicemail 附加到请求 URI 标头。</span><span class="sxs-lookup"><span data-stu-id="a32d9-152">If you want to send the call directly to voicemail, attach opaque=app:voicemail to the Request URI header.</span></span> <span data-ttu-id="a32d9-153">例如，"sip：user@yourdomain.com;opaque=app：voicemail"。</span><span class="sxs-lookup"><span data-stu-id="a32d9-153">For example, "sip:user@yourdomain.com;opaque=app:voicemail".</span></span> <span data-ttu-id="a32d9-154">在这种情况下，Teams 用户不会收到呼叫通知，呼叫将直接连接到用户的语音邮件。</span><span class="sxs-lookup"><span data-stu-id="a32d9-154">In this case, the Teams user will not receive the calling notification, the call will be connected to the voicemail of the user directly.</span></span>

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a><span data-ttu-id="a32d9-155">向用户分配"仅 Teams"模式以确保呼叫进入 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a32d9-155">Assign Teams Only mode to users to ensure calls land in Microsoft Teams</span></span>

<span data-ttu-id="a32d9-156">直接路由要求用户进入"仅 Teams"模式，以确保传入呼叫进入 Teams 客户端。</span><span class="sxs-lookup"><span data-stu-id="a32d9-156">Direct Routing requires that users be in Teams Only mode to ensure incoming calls land in the Teams client.</span></span> <span data-ttu-id="a32d9-157">若要将用户置于"仅 Teams"模式，请为其分配 TeamsUpgradePolicy 的"UpgradeToTeams"实例。</span><span class="sxs-lookup"><span data-stu-id="a32d9-157">To put users in Teams Only mode, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span> <span data-ttu-id="a32d9-158">有关详细信息，请参阅适用于 [IT 管理员的升级策略](upgrade-to-teams-on-prem-implement.md)。</span><span class="sxs-lookup"><span data-stu-id="a32d9-158">For more information, see [Upgrade strategies for IT administrators](upgrade-to-teams-on-prem-implement.md).</span></span> <span data-ttu-id="a32d9-159">如果你的组织使用 Skype for Business Server 或 Skype for Business Online，请参阅以下文章，了解 Skype 和 Teams 之间的互操作性：迁移和与 [Skype for Business 的互操作性](migration-interop-guidance-for-teams-with-skype.md)。</span><span class="sxs-lookup"><span data-stu-id="a32d9-159">If your organization uses Skype for Business Server or Skype for Business Online, see the following article for information about interoperability between Skype and Teams: [Migration and interoperability with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a32d9-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a32d9-160">See also</span></span>

[<span data-ttu-id="a32d9-161">规划直接路由</span><span class="sxs-lookup"><span data-stu-id="a32d9-161">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="a32d9-162">配置直接路由</span><span class="sxs-lookup"><span data-stu-id="a32d9-162">Configure Direct Routing</span></span>](direct-routing-configure.md)
