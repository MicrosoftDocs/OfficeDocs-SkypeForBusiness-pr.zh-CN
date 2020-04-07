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
description: 了解如何启用 Microsoft 手机系统直接路由用户。
ms.openlocfilehash: 10c62d14f283d565765a47e4c07504bc9bffa720
ms.sourcegitcommit: 0fdc60840f45ff5b0a39a8ec4a21138f6cab49c9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/07/2020
ms.locfileid: "43160056"
---
# <a name="enable-users-for-direct-routing-voice-and-voicemail"></a><span data-ttu-id="98c0a-103">为用户启用直接路由、语音和语音邮件</span><span class="sxs-lookup"><span data-stu-id="98c0a-103">Enable users for Direct Routing, voice, and voicemail</span></span>

<span data-ttu-id="98c0a-104">本文介绍如何为用户启用电话系统直接路由。</span><span class="sxs-lookup"><span data-stu-id="98c0a-104">This article describes how to enable users for Phone System Direct Routing.</span></span>  <span data-ttu-id="98c0a-105">这是用于配置直接路由的以下步骤的步骤2：</span><span class="sxs-lookup"><span data-stu-id="98c0a-105">This is step 2 of the following steps for configuring Direct Routing:</span></span>

- <span data-ttu-id="98c0a-106">第 1 步</span><span class="sxs-lookup"><span data-stu-id="98c0a-106">Step 1.</span></span> [<span data-ttu-id="98c0a-107">将 SBC 连接到 Microsoft Phone 系统并验证连接</span><span class="sxs-lookup"><span data-stu-id="98c0a-107">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md) 
- <span data-ttu-id="98c0a-108">**步骤2。为用户启用直接路由、语音和语音邮件**（本文）</span><span class="sxs-lookup"><span data-stu-id="98c0a-108">**Step 2. Enable users for Direct Routing, voice, and voicemail**    (This article)</span></span>
- <span data-ttu-id="98c0a-109">第 3 步</span><span class="sxs-lookup"><span data-stu-id="98c0a-109">Step 3.</span></span> [<span data-ttu-id="98c0a-110">配置语音路由</span><span class="sxs-lookup"><span data-stu-id="98c0a-110">Configure voice routing</span></span>](direct-routing-voice-routing.md)
- <span data-ttu-id="98c0a-111">第 4 步</span><span class="sxs-lookup"><span data-stu-id="98c0a-111">Step 4.</span></span> [<span data-ttu-id="98c0a-112">将数字转换为备用格式</span><span class="sxs-lookup"><span data-stu-id="98c0a-112">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 


<span data-ttu-id="98c0a-113">有关设置直接路由所需的所有步骤的信息，请参阅[配置直接路由](direct-routing-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="98c0a-113">For information on all the steps required for setting up Direct Routing, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

<span data-ttu-id="98c0a-114">准备好为用户启用直接路由时，请按照下列步骤操作：</span><span class="sxs-lookup"><span data-stu-id="98c0a-114">When you are ready to enable users for Direct Routing, follow these steps:</span></span> 

1. <span data-ttu-id="98c0a-115">在 Office 365 中创建用户并分配电话系统许可证。</span><span class="sxs-lookup"><span data-stu-id="98c0a-115">Create a user in Office 365 and assign a phone system license.</span></span> 
2. <span data-ttu-id="98c0a-116">确保用户托管在 Skype for Business Online 中。</span><span class="sxs-lookup"><span data-stu-id="98c0a-116">Ensure that the user is homed in Skype for Business Online.</span></span> 
3. <span data-ttu-id="98c0a-117">配置电话号码并启用企业语音和语音邮件。</span><span class="sxs-lookup"><span data-stu-id="98c0a-117">Configure the phone number and enable enterprise voice and voicemail.</span></span> 
4. <span data-ttu-id="98c0a-118">向用户分配 "仅团队" 模式。</span><span class="sxs-lookup"><span data-stu-id="98c0a-118">Assign Teams Only mode to users.</span></span>

## <a name="create-a-user-in-office-365-and-assign-the-license"></a><span data-ttu-id="98c0a-119">在 Office 365 中创建用户并分配许可证</span><span class="sxs-lookup"><span data-stu-id="98c0a-119">Create a user in Office 365 and assign the license</span></span> 

<span data-ttu-id="98c0a-120">在 Office 365 中创建新用户有两个选项。</span><span class="sxs-lookup"><span data-stu-id="98c0a-120">There are two options for creating a new user in Office 365.</span></span> <span data-ttu-id="98c0a-121">但是，Microsoft 建议你的组织选择一个选项来避免路由问题：</span><span class="sxs-lookup"><span data-stu-id="98c0a-121">However, Microsoft recommends that your organization choose one option to avoid routing issues:</span></span> 

- <span data-ttu-id="98c0a-122">在本地 Active Directory 中创建用户并将用户同步到云。</span><span class="sxs-lookup"><span data-stu-id="98c0a-122">Create the user in on-premises Active Directory and sync the user to the cloud.</span></span> <span data-ttu-id="98c0a-123">请参阅[将本地目录与 Azure Active Directory 集成](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)。</span><span class="sxs-lookup"><span data-stu-id="98c0a-123">See [Integrate your on-premises directories with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>
- <span data-ttu-id="98c0a-124">直接在 Office 365 管理员门户中创建用户。</span><span class="sxs-lookup"><span data-stu-id="98c0a-124">Create the user directly in the Office 365 Administrator Portal.</span></span> <span data-ttu-id="98c0a-125">请参阅[向 Office 365 单独或批量添加用户-管理员帮助](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)。</span><span class="sxs-lookup"><span data-stu-id="98c0a-125">See [Add users individually or in bulk to Office 365 - Admin Help](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span> 

<span data-ttu-id="98c0a-126">如果您的 Skype for Business Online 部署 coexists 使用 Skype for business 2015 或 Lync 2010 或本地2013，则唯一支持的选项是在本地 Active Directory 中创建用户并将用户与云同步（选项1）。</span><span class="sxs-lookup"><span data-stu-id="98c0a-126">If your Skype for Business Online deployment coexists with Skype for Business 2015 or Lync 2010 or 2013 on-premises, the only supported option is to create the user in the on-premises Active Directory and sync the user to the cloud (Option 1).</span></span> 

<span data-ttu-id="98c0a-127">有关许可证要求的信息，请参阅[计划直接路由](direct-routing-plan.md)中的[许可和其他要求](direct-routing-plan.md#licensing-and-other-requirements)。</span><span class="sxs-lookup"><span data-stu-id="98c0a-127">For information about license requirements, see [licensing and other requirements](direct-routing-plan.md#licensing-and-other-requirements) in [Plan Direct Routing](direct-routing-plan.md).</span></span>

## <a name="ensure-that-the-user-is-homed-in-skype-for-business-online"></a><span data-ttu-id="98c0a-128">确保用户托管在 Skype for Business Online 中</span><span class="sxs-lookup"><span data-stu-id="98c0a-128">Ensure that the user is homed in Skype for Business Online</span></span> 

<span data-ttu-id="98c0a-129">直接路由要求用户驻留在 Skype for Business Online 中。</span><span class="sxs-lookup"><span data-stu-id="98c0a-129">Direct Routing requires the user to be homed in Skype for Business Online.</span></span> <span data-ttu-id="98c0a-130">你可以查看 RegistrarPool 参数，该参数需要在 infra.lync.com 域中具有值。</span><span class="sxs-lookup"><span data-stu-id="98c0a-130">You can check by looking at the RegistrarPool parameter, which needs to have a value in the infra.lync.com domain.</span></span>

1. <span data-ttu-id="98c0a-131">连接到远程 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="98c0a-131">Connect to remote PowerShell.</span></span>
2. <span data-ttu-id="98c0a-132">发出命令：</span><span class="sxs-lookup"><span data-stu-id="98c0a-132">Issue the command:</span></span> 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool
    ``` 

## <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a><span data-ttu-id="98c0a-133">配置电话号码并启用企业语音和语音邮件</span><span class="sxs-lookup"><span data-stu-id="98c0a-133">Configure the phone number and enable enterprise voice and voicemail</span></span> 

<span data-ttu-id="98c0a-134">创建用户并分配许可证后，下一步是配置用户的电话号码和语音邮件。</span><span class="sxs-lookup"><span data-stu-id="98c0a-134">After you have created the user and assigned a license, the next step is to configure the user's phone number and voicemail.</span></span> 

<span data-ttu-id="98c0a-135">要为语音邮件添加电话号码和启用，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="98c0a-135">To add the phone number and enable for voicemail:</span></span>
 
1. <span data-ttu-id="98c0a-136">连接到远程 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="98c0a-136">Connect to a remote PowerShell session.</span></span> 
2. <span data-ttu-id="98c0a-137">输入命令：</span><span class="sxs-lookup"><span data-stu-id="98c0a-137">Enter the command:</span></span> 
 
    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<E.164 phone number>
    ```

    <span data-ttu-id="98c0a-138">例如，若要为用户 "Spencer Low" 添加电话号码，请输入以下内容：</span><span class="sxs-lookup"><span data-stu-id="98c0a-138">For example, to add a phone number for user "Spencer Low," enter the following:</span></span> 

    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```

    <span data-ttu-id="98c0a-139">使用的电话号码必须配置为完整的 E-164 个国家/地区代码的电话号码。</span><span class="sxs-lookup"><span data-stu-id="98c0a-139">The phone number used has to be configured as a full E.164 phone number with country code.</span></span> 

      > [!NOTE]
      > <span data-ttu-id="98c0a-140">如果用户的电话号码是在本地管理的，请使用本地 Skype for Business Management Shell 或控制面板配置用户的电话号码。</span><span class="sxs-lookup"><span data-stu-id="98c0a-140">If the user’s phone number is managed on premises, use on-premises Skype for Business Management Shell or Control Panel to configure the user's phone number.</span></span> 


## <a name="configuring-sending-calls-directly-to-voicemail"></a><span data-ttu-id="98c0a-141">配置将呼叫直接发送到语音邮件</span><span class="sxs-lookup"><span data-stu-id="98c0a-141">Configuring sending calls directly to voicemail</span></span>

<span data-ttu-id="98c0a-142">直接路由允许您结束呼叫用户并将其直接发送到用户的语音邮件。</span><span class="sxs-lookup"><span data-stu-id="98c0a-142">Direct Routing allows you to end the call to a user and send it directly to the user's voicemail.</span></span> <span data-ttu-id="98c0a-143">如果您想要将呼叫直接发送到语音邮件，请将不透明 = app：语音邮件附加到请求 URI 标题。</span><span class="sxs-lookup"><span data-stu-id="98c0a-143">If you want to send the call directly to voicemail, attach opaque=app:voicemail to the Request URI header.</span></span> <span data-ttu-id="98c0a-144">例如，"sip： user@yourdomain .com; 不透明 = 应用：语音邮件"。</span><span class="sxs-lookup"><span data-stu-id="98c0a-144">For example, "sip:user@yourdomain.com;opaque=app:voicemail".</span></span> <span data-ttu-id="98c0a-145">在这种情况下，团队用户将不会收到呼叫通知，直接将呼叫连接到用户的语音邮件。</span><span class="sxs-lookup"><span data-stu-id="98c0a-145">In this case, the Teams user will not receive the calling notification, the call will be connected to the voicemail of the user directly.</span></span>

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a><span data-ttu-id="98c0a-146">向用户分配 "仅团队" 模式以确保在 Microsoft 团队中拨打土地</span><span class="sxs-lookup"><span data-stu-id="98c0a-146">Assign Teams Only mode to users to ensure calls land in Microsoft Teams</span></span>

<span data-ttu-id="98c0a-147">直接路由要求用户仅在 "仅工作组" 模式下，以确保传入呼叫位于团队客户的土地。</span><span class="sxs-lookup"><span data-stu-id="98c0a-147">Direct Routing requires that users be in Teams Only mode to ensure incoming calls land in the Teams client.</span></span> <span data-ttu-id="98c0a-148">若要将用户置于 "仅团队" 模式，请为他们分配 TeamsUpgradePolicy 的 "UpgradeToTeams" 实例。</span><span class="sxs-lookup"><span data-stu-id="98c0a-148">To put users in Teams Only mode, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span> <span data-ttu-id="98c0a-149">有关详细信息，请参阅[IT 管理员的升级指南](upgrade-to-teams-on-prem-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="98c0a-149">For more information, see [Upgrade guidance for IT administrators](upgrade-to-teams-on-prem-overview.md).</span></span> <span data-ttu-id="98c0a-150">如果你的组织使用 Skype for business 服务器或 Skype for business Online，请参阅以下文章了解有关 Skype 和团队之间的互操作性的信息：[迁移和与 skype](migration-interop-guidance-for-teams-with-skype.md)for business 之间的互操作性。</span><span class="sxs-lookup"><span data-stu-id="98c0a-150">If your organization uses Skype for Business Server or Skype for Business Online, see the following article for information about interoperability between Skype and Teams: [Migration and interoperability with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="98c0a-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="98c0a-151">See also</span></span>

[<span data-ttu-id="98c0a-152">规划直接路由</span><span class="sxs-lookup"><span data-stu-id="98c0a-152">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="98c0a-153">配置直接路由</span><span class="sxs-lookup"><span data-stu-id="98c0a-153">Configure Direct Routing</span></span>](direct-routing-configure.md)
