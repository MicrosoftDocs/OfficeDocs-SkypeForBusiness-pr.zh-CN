---
title: 为本地用户配置云语音邮件服务
ms.reviewer: ''
ms.author: dstrome
author: dstrome
manager: serdars
ms.date: 2/11/2019
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 为托管在 Skype for Business Server 上的用户实施基于云的语音邮件的说明。
ms.openlocfilehash: a9c308189a5dc70c85382f638f30f52c0ac69bdb
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118981"
---
# <a name="configure-cloud-voicemail-service-for-on-premises-users"></a><span data-ttu-id="bfce3-103">为本地用户配置云语音邮件服务</span><span class="sxs-lookup"><span data-stu-id="bfce3-103">Configure Cloud Voicemail service for on-premises users</span></span>

## <a name="overview"></a><span data-ttu-id="bfce3-104">概述</span><span class="sxs-lookup"><span data-stu-id="bfce3-104">Overview</span></span> 
<span data-ttu-id="bfce3-105">本文介绍如何为 Skype for Business 本地用户配置 Microsoft 云语音邮件服务。</span><span class="sxs-lookup"><span data-stu-id="bfce3-105">This article describes how to configure Microsoft Cloud Voicemail service for your Skype for Business on-premises users.</span></span>  

<span data-ttu-id="bfce3-106">本文假定你已在支持的拓扑中部署了 Skype for Business Server，并且你已满足设置混合连接的先决条件。</span><span class="sxs-lookup"><span data-stu-id="bfce3-106">This article assumes that you already have Skype for Business Server deployed in a supported topology, and that you have met the prerequisites for setting up hybrid connectivity.</span></span>

<span data-ttu-id="bfce3-107">有关实施云语音邮件的好处、规划注意事项和要求详细信息，请参阅规划 [云语音邮件服务](plan-cloud-voicemail.md)。</span><span class="sxs-lookup"><span data-stu-id="bfce3-107">For more information about the benefits, planning considerations, and requirements for implementing Cloud Voicemail, see [Plan Cloud Voicemail service](plan-cloud-voicemail.md).</span></span>




<span data-ttu-id="bfce3-108">配置云语音邮件涉及以下任务：</span><span class="sxs-lookup"><span data-stu-id="bfce3-108">Configuring Cloud Voicemail involves the following tasks:</span></span>

1.  <span data-ttu-id="bfce3-109">确保你已满足 Plan Cloud Voicemail [service](plan-cloud-voicemail.md)中所述的先决条件。</span><span class="sxs-lookup"><span data-stu-id="bfce3-109">Ensure that you have met the prerequisites as described in [Plan Cloud Voicemail service](plan-cloud-voicemail.md).</span></span>

2.  <span data-ttu-id="bfce3-110">确保已设置混合连接，如规划混合连接和[](plan-hybrid-connectivity.md)[配置混合连接中所述](configure-hybrid-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="bfce3-110">Ensure that you have set up hybrid connectivity as described in [Plan hybrid connectivity](plan-hybrid-connectivity.md) and [Configure hybrid connectivity](configure-hybrid-connectivity.md).</span></span> 

3.  <span data-ttu-id="bfce3-111">[将云语音邮件配置为](#configure-cloud-voicemail-as-the-hosting-provider) 前端服务器的托管提供商，如本文所述。</span><span class="sxs-lookup"><span data-stu-id="bfce3-111">[Configure Cloud Voicemail as the hosting provider on the Front End Server](#configure-cloud-voicemail-as-the-hosting-provider) as described in this article.</span></span>

4.  <span data-ttu-id="bfce3-112">[配置托管语音邮件策略](#configure-a-hosted-voicemail-policy) ，如本文所述。</span><span class="sxs-lookup"><span data-stu-id="bfce3-112">[Configure a hosted voicemail policy](#configure-a-hosted-voicemail-policy) as described in this article.</span></span>

5.  <span data-ttu-id="bfce3-113">[分配托管语音邮件策略](#assign-a-hosted-voicemail-policy) ，如本文所述。</span><span class="sxs-lookup"><span data-stu-id="bfce3-113">[Assign a hosted voicemail policy](#assign-a-hosted-voicemail-policy) as described in this article.</span></span>

6.  <span data-ttu-id="bfce3-114">[为用户启用云语音邮件](#enable-a-user-for-cloud-voicemail) ，如本文所述。</span><span class="sxs-lookup"><span data-stu-id="bfce3-114">[Enable a user for Cloud Voicemail](#enable-a-user-for-cloud-voicemail) as described in this article.</span></span>


## <a name="configure-cloud-voicemail-as-the-hosting-provider"></a><span data-ttu-id="bfce3-115">将云语音邮件配置为托管提供商</span><span class="sxs-lookup"><span data-stu-id="bfce3-115">Configure Cloud Voicemail as the hosting provider</span></span> 

<span data-ttu-id="bfce3-116">通过具有以下参数的 New-CsHostingProvider cmdlet，可以将云语音邮件配置为前端服务器的托管提供商：</span><span class="sxs-lookup"><span data-stu-id="bfce3-116">You configure Cloud Voicemail as the hosting provider on a Front End Server by using the New-CsHostingProvider cmdlet with the following parameters:</span></span>

- <span data-ttu-id="bfce3-117">**Identity** 指定要创建的宿主提供商的唯一字符串值标识符;例如，云语音邮件。</span><span class="sxs-lookup"><span data-stu-id="bfce3-117">**Identity** specifies a unique string value identifier for the hosting provider that you are creating; for example, Cloud Voicemail.</span></span> 

- <span data-ttu-id="bfce3-118">**Enabled** 指示您的域与承载服务提供商之间的网络连接是否已启用。</span><span class="sxs-lookup"><span data-stu-id="bfce3-118">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="bfce3-119">此参数必须设置为 True。</span><span class="sxs-lookup"><span data-stu-id="bfce3-119">This parameter must be set to True.</span></span>

- <span data-ttu-id="bfce3-120">**EnabledSharedAddressSpace** 指示是否要在共享 SIP 地址空间方案中使用承载服务提供商。</span><span class="sxs-lookup"><span data-stu-id="bfce3-120">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="bfce3-121">此参数必须设置为 True。</span><span class="sxs-lookup"><span data-stu-id="bfce3-121">This parameter must be set to True.</span></span>

- <span data-ttu-id="bfce3-122">**HostsOCSUsers** 指示宿主提供商是否用于托管 Skype for Business Server 帐户。</span><span class="sxs-lookup"><span data-stu-id="bfce3-122">**HostsOCSUsers** indicates whether the hosting provider is used to host Skype for Business Server accounts.</span></span> <span data-ttu-id="bfce3-123">此参数必须设置为 False。</span><span class="sxs-lookup"><span data-stu-id="bfce3-123">This parameter must be set to False.</span></span>

- <span data-ttu-id="bfce3-124">**ProxyFQDN** 指定托管 (使用的) 的完全限定域名和 FQDN 名称;例如，proxyserver.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="bfce3-124">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider; for example, proxyserver.contoso.com.</span></span> <span data-ttu-id="bfce3-125">有关此信息，请与承载服务提供商联系。</span><span class="sxs-lookup"><span data-stu-id="bfce3-125">Contact your hosting provider for this information.</span></span> <span data-ttu-id="bfce3-126">不能修改此值。</span><span class="sxs-lookup"><span data-stu-id="bfce3-126">This value cannot be modified.</span></span> <span data-ttu-id="bfce3-127">如果宿主提供商更改其代理服务器，则需要删除该条目，然后重新创建该提供商的条目。</span><span class="sxs-lookup"><span data-stu-id="bfce3-127">If the hosting provider changes its proxy server, you will need to delete and then re-create the entry for that provider.</span></span>

- <span data-ttu-id="bfce3-128">**IsLocal** 指示宿主提供商使用的代理服务器是否包含在 Skype for Business Server 拓扑中。</span><span class="sxs-lookup"><span data-stu-id="bfce3-128">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Skype for Business Server topology.</span></span> <span data-ttu-id="bfce3-129">此参数必须设置为 False。</span><span class="sxs-lookup"><span data-stu-id="bfce3-129">This parameter must be set to False.</span></span>

<span data-ttu-id="bfce3-130">例如，在 Skype for Business 命令行管理程序中，以下 cmdlet 将云语音邮件配置为托管提供商：</span><span class="sxs-lookup"><span data-stu-id="bfce3-130">For example, in the Skype for Business Management shell, the following cmdlet configures Cloud Voicemail as the hosting provider:</span></span>


```PowerShell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

## <a name="configure-a-hosted-voicemail-policy"></a><span data-ttu-id="bfce3-131">配置托管语音邮件策略</span><span class="sxs-lookup"><span data-stu-id="bfce3-131">Configure a hosted voicemail policy</span></span>

<span data-ttu-id="bfce3-132">若要确保组织的语音邮件路由到云语音邮件服务，必须为组织配置托管语音邮件策略。</span><span class="sxs-lookup"><span data-stu-id="bfce3-132">To ensure that voicemail for your organization is routed to the Cloud Voicemail service, you must configure a hosted voicemail policy for your organization.</span></span> <span data-ttu-id="bfce3-133">在许多情况下，只需要一个托管语音邮件策略，您可以修改全局策略来满足所有需求。</span><span class="sxs-lookup"><span data-stu-id="bfce3-133">In many cases, only one hosted voicemail policy is required, and you can modify the global policy to meet all your needs.</span></span> <span data-ttu-id="bfce3-134">如果组织需要多个托管语音邮件策略，可以使用 new-cshostedvoicemailpolicy cmdlet 添加策略。</span><span class="sxs-lookup"><span data-stu-id="bfce3-134">If your organization requires multiple hosted voicemail policies, you can add policies by using the new-cshostedvoicemailpolicy cmdlet.</span></span>

<span data-ttu-id="bfce3-135">若要修改全局策略，在更新组织和 TenantID 后，在 Skype for Business Server 命令行管理程序中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="bfce3-135">To modify the global policy, run the following command in the Skype for Business Server management shell after updating your Organization and TenantID:</span></span>

```PowerShell
Set-CsHostedVoicemailPolicy -Identity Global -Description "Global Cloud Voicemail Policy" -Destination exap.um.outlook.com -Organization YourDefaultDomain.onmicrosoft.com
```

- <span data-ttu-id="bfce3-136">**Destination** 指定托管云语音邮件 (FQDN) 的完全限定域名。</span><span class="sxs-lookup"><span data-stu-id="bfce3-136">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Cloud Voicemail service.</span></span> <span data-ttu-id="bfce3-137">此值应设置为 **exap.um.outlook.com**。</span><span class="sxs-lookup"><span data-stu-id="bfce3-137">This value should be set to **exap.um.outlook.com**.</span></span>

- <span data-ttu-id="bfce3-138">**组织** 是分配给租户的默认域。</span><span class="sxs-lookup"><span data-stu-id="bfce3-138">**Organization** is the default domain assigned to your tenant.</span></span> <span data-ttu-id="bfce3-139">可以通过让租户管理员登录帐户来检索此信息 office.com 单击管理中心应用，导航到左侧的"设置"，然后单击"域 **"。**</span><span class="sxs-lookup"><span data-stu-id="bfce3-139">You can retrieve this information by having the tenant admin log in to office.com, click on the Admin Center app, navigate to **Setup** on the left, and click **Domains**.</span></span> <span data-ttu-id="bfce3-140">例如：mytenant.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="bfce3-140">For example: mytenant.onmicrosoft.com.</span></span>

    <span data-ttu-id="bfce3-141">组织名称也是 Microsoft 365 或 Office 365 中的默认域名。</span><span class="sxs-lookup"><span data-stu-id="bfce3-141">The Organization name is also the Default Domain name in Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="bfce3-142">若要确保已成功创建托管语音邮件策略，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="bfce3-142">To ensure that a hosted voicemail policy was created successfully, run the following command:</span></span>

```PowerShell
Get-CsHostedVoicemailPolicy
```

## <a name="assign-a-hosted-voicemail-policy"></a><span data-ttu-id="bfce3-143">分配托管语音邮件策略</span><span class="sxs-lookup"><span data-stu-id="bfce3-143">Assign a hosted voicemail policy</span></span>

<span data-ttu-id="bfce3-144">默认情况下，全局托管语音邮件策略分配给所有用户。</span><span class="sxs-lookup"><span data-stu-id="bfce3-144">By default, the Global hosted voicemail policy is assigned to all users.</span></span> <span data-ttu-id="bfce3-145">如果您使用其他策略，则必须先使用 [Grant-CSHostedVoicemailPolicy](/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps) cmdlet 向用户授予所需的托管语音邮件策略，然后才能为用户启用托管语音邮件。</span><span class="sxs-lookup"><span data-stu-id="bfce3-145">If you use a different policy, before enabling users for hosted voicemail, you must first grant users the desired hosted voicemail policy by using the [Grant-CSHostedVoicemailPolicy](/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps) cmdlet.</span></span>

<span data-ttu-id="bfce3-146">例如，以下命令将非全局托管语音邮件策略分配给用户：</span><span class="sxs-lookup"><span data-stu-id="bfce3-146">For example, the following command assigns a non-Global hosted voicemail policy to a user:</span></span>


```PowerShell
Get-CsUser -Identity "User1" | Grant-CsHostedVoicemailPolicy -PolicyName "Tag:CloudVoiceMailUsers" 
```

## <a name="enable-a-user-for-cloud-voicemail"></a><span data-ttu-id="bfce3-147">为用户启用云语音邮件</span><span class="sxs-lookup"><span data-stu-id="bfce3-147">Enable a user for Cloud Voicemail</span></span>

<span data-ttu-id="bfce3-148">若要使用户的语音邮件呼叫可以路由到云语音邮件，请使用 [Set-CsUser](/powershell/module/skype/set-csuser?view=skype-ps) cmdlet 和 HostedVoiceMail 参数。</span><span class="sxs-lookup"><span data-stu-id="bfce3-148">To enable a user’s voicemail calls to be routed to Cloud Voicemail, you use the [Set-CsUser](/powershell/module/skype/set-csuser?view=skype-ps) cmdlet with the HostedVoiceMail parameter.</span></span> 

<span data-ttu-id="bfce3-149">例如，以下命令为用户帐户启用云语音邮件：</span><span class="sxs-lookup"><span data-stu-id="bfce3-149">For example, the following command enables a user account for Cloud Voicemail:</span></span> 

```powershell
Set-CsUser -Identity "User1" -HostedVoiceMail $True
```

<span data-ttu-id="bfce3-150">此 cmdlet 验证云语音邮件策略（全局、站点或用户级别）是否适用于此用户。</span><span class="sxs-lookup"><span data-stu-id="bfce3-150">The cmdlet verifies that a Cloud Voicemail policy--at the global, site, or user level--applies to this user.</span></span> <span data-ttu-id="bfce3-151">如果没有适用的策略，该 cmdlet 将失败。</span><span class="sxs-lookup"><span data-stu-id="bfce3-151">If no policy applies, the cmdlet fails.</span></span>  

<span data-ttu-id="bfce3-152">下一个示例禁用云语音邮件的用户帐户：</span><span class="sxs-lookup"><span data-stu-id="bfce3-152">The next example disables a user account for Cloud Voicemail:</span></span>

```powershell
Set-CsUser -Identity "User1" -HostedVoiceMail $False
```

<span data-ttu-id="bfce3-153">此 cmdlet 验证在全局、站点或用户级别托管语音邮件策略是否适用于此用户。</span><span class="sxs-lookup"><span data-stu-id="bfce3-153">The cmdlet verifies that no hosted voicemail policy--at the global, site, or user level--applies to this user.</span></span> <span data-ttu-id="bfce3-154">如果有适用的策略，该 cmdlet 将失败。</span><span class="sxs-lookup"><span data-stu-id="bfce3-154">If a policy does apply, the cmdlet fails.</span></span>

> [!NOTE]
>  <span data-ttu-id="bfce3-155">用户必须启用企业语音，以便使用 Microsoft 云语音邮件服务。</span><span class="sxs-lookup"><span data-stu-id="bfce3-155">Users must be enterprise-voice enabled to use the Microsoft Cloud Voicemail Service.</span></span>