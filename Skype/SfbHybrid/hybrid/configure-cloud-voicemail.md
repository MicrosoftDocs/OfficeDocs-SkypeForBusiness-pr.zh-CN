---
title: 为本地用户配置云语音邮件服务
ms.reviewer: ''
ms.author: dstrome
author: dstrome
manager: serdars
ms.date: 2/11/2019
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 有关为驻留在 Skype for business Server 上的用户实施基于云的语音邮件的说明。
ms.openlocfilehash: 754d69a9b76497f8776667b6ac97498a151c7e4e
ms.sourcegitcommit: bcac0d94f6eb7132fc17b0ace62e7028f77b0ee6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2020
ms.locfileid: "41230352"
---
# <a name="configure-cloud-voicemail-service-for-on-premises-users"></a><span data-ttu-id="16227-103">为本地用户配置云语音邮件服务</span><span class="sxs-lookup"><span data-stu-id="16227-103">Configure Cloud Voicemail service for on-premises users</span></span>

## <a name="overview"></a><span data-ttu-id="16227-104">概述</span><span class="sxs-lookup"><span data-stu-id="16227-104">Overview</span></span> 
<span data-ttu-id="16227-105">本文介绍如何为您的 Skype for business 本地用户配置 Microsoft 云语音邮件服务。</span><span class="sxs-lookup"><span data-stu-id="16227-105">This article describes how to configure Microsoft Cloud Voicemail service for your Skype for Business on-premises users.</span></span>  

<span data-ttu-id="16227-106">本文假定您已在受支持的拓扑中部署了 Skype for Business 服务器，并且您已满足设置混合连接的先决条件。</span><span class="sxs-lookup"><span data-stu-id="16227-106">This article assumes that you already have Skype for Business Server deployed in a supported topology, and that you have met the prerequisites for setting up hybrid connectivity.</span></span>

<span data-ttu-id="16227-107">有关实施云语音邮件的优势、规划注意事项和要求的详细信息，请参阅[Plan 云语音邮件服务](plan-cloud-voicemail.md)。</span><span class="sxs-lookup"><span data-stu-id="16227-107">For more information about the benefits, planning considerations, and requirements for implementing Cloud Voicemail, see [Plan Cloud Voicemail service](plan-cloud-voicemail.md).</span></span>




<span data-ttu-id="16227-108">配置云语音邮件涉及以下任务：</span><span class="sxs-lookup"><span data-stu-id="16227-108">Configuring Cloud Voicemail involves the following tasks:</span></span>

1.  <span data-ttu-id="16227-109">确保您符合[Plan 云语音邮件服务](plan-cloud-voicemail.md)中所述的先决条件。</span><span class="sxs-lookup"><span data-stu-id="16227-109">Ensure that you have met the prerequisites as described in [Plan Cloud Voicemail service](plan-cloud-voicemail.md).</span></span>

2.  <span data-ttu-id="16227-110">确保已按照[规划混合连接](plan-hybrid-connectivity.md)和[配置混合连接](configure-hybrid-connectivity.md)中所述设置了混合连接。</span><span class="sxs-lookup"><span data-stu-id="16227-110">Ensure that you have set up hybrid connectivity as described in [Plan hybrid connectivity](plan-hybrid-connectivity.md) and [Configure hybrid connectivity](configure-hybrid-connectivity.md).</span></span> 

3.  <span data-ttu-id="16227-111">[将云语音邮件配置为边缘服务器上的承载提供程序](#configure-cloud-voicemail-as-the-hosting-provider)，如本文中所述。</span><span class="sxs-lookup"><span data-stu-id="16227-111">[Configure Cloud Voicemail as the hosting provider on the Edge Server](#configure-cloud-voicemail-as-the-hosting-provider) as described in this article.</span></span>

4.  <span data-ttu-id="16227-112">[配置托管的语音邮件策略](#configure-a-hosted-voicemail-policy)，如本文中所述。</span><span class="sxs-lookup"><span data-stu-id="16227-112">[Configure a hosted voicemail policy](#configure-a-hosted-voicemail-policy) as described in this article.</span></span>

5.  <span data-ttu-id="16227-113">按照本文所述，[分配一个托管的语音邮件策略](#assign-a-hosted-voicemail-policy)。</span><span class="sxs-lookup"><span data-stu-id="16227-113">[Assign a hosted voicemail policy](#assign-a-hosted-voicemail-policy) as described in this article.</span></span>

6.  <span data-ttu-id="16227-114">为[用户启用云语音邮件](#enable-a-user-for-cloud-voicemail)，如本文中所述。</span><span class="sxs-lookup"><span data-stu-id="16227-114">[Enable a user for Cloud Voicemail](#enable-a-user-for-cloud-voicemail) as described in this article.</span></span>


## <a name="configure-cloud-voicemail-as-the-hosting-provider"></a><span data-ttu-id="16227-115">将云语音邮件配置为承载提供程序</span><span class="sxs-lookup"><span data-stu-id="16227-115">Configure Cloud Voicemail as the hosting provider</span></span> 

<span data-ttu-id="16227-116">您可以使用 CsHostingProvider cmdlet 和以下参数将云语音邮件配置为前端服务器上的托管提供程序：</span><span class="sxs-lookup"><span data-stu-id="16227-116">You configure Cloud Voicemail as the hosting provider on a Front End Server by using the New-CsHostingProvider cmdlet with the following parameters:</span></span>

- <span data-ttu-id="16227-117">**Identity**为您要创建的托管提供程序指定一个唯一的字符串值标识符;例如，云语音邮件。</span><span class="sxs-lookup"><span data-stu-id="16227-117">**Identity** specifies a unique string value identifier for the hosting provider that you are creating; for example, Cloud Voicemail.</span></span> 

- <span data-ttu-id="16227-118">**Enabled** 指示您的域与承载服务提供商之间的网络连接是否已启用。</span><span class="sxs-lookup"><span data-stu-id="16227-118">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="16227-119">此参数必须设置为 True。</span><span class="sxs-lookup"><span data-stu-id="16227-119">This parameter must be set to True.</span></span>

- <span data-ttu-id="16227-120">**EnabledSharedAddressSpace** 指示是否要在共享 SIP 地址空间方案中使用承载服务提供商。</span><span class="sxs-lookup"><span data-stu-id="16227-120">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="16227-121">此参数必须设置为 True。</span><span class="sxs-lookup"><span data-stu-id="16227-121">This parameter must be set to True.</span></span>

- <span data-ttu-id="16227-122">**HostsOCSUsers**指示是否使用托管提供程序来承载 Skype For business Server 帐户。</span><span class="sxs-lookup"><span data-stu-id="16227-122">**HostsOCSUsers** indicates whether the hosting provider is used to host Skype for Business Server accounts.</span></span> <span data-ttu-id="16227-123">此参数必须设置为 False。</span><span class="sxs-lookup"><span data-stu-id="16227-123">This parameter must be set to False.</span></span>

- <span data-ttu-id="16227-124">**ProxyFQDN**指定承载提供程序所使用的代理服务器的完全限定域名（FQDN）;例如，proxyserver.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="16227-124">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider; for example, proxyserver.contoso.com.</span></span> <span data-ttu-id="16227-125">有关此信息，请与承载服务提供商联系。</span><span class="sxs-lookup"><span data-stu-id="16227-125">Contact your hosting provider for this information.</span></span> <span data-ttu-id="16227-126">不能修改此值。</span><span class="sxs-lookup"><span data-stu-id="16227-126">This value cannot be modified.</span></span> <span data-ttu-id="16227-127">如果托管提供程序更改其代理服务器，则需要删除并重新创建该提供程序的条目。</span><span class="sxs-lookup"><span data-stu-id="16227-127">If the hosting provider changes its proxy server, you will need to delete and then re-create the entry for that provider.</span></span>

- <span data-ttu-id="16227-128">**IsLocal**指示托管提供程序使用的代理服务器是否包含在您的 Skype For business server 拓扑中。</span><span class="sxs-lookup"><span data-stu-id="16227-128">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Skype for Business Server topology.</span></span> <span data-ttu-id="16227-129">此参数必须设置为 False。</span><span class="sxs-lookup"><span data-stu-id="16227-129">This parameter must be set to False.</span></span>

<span data-ttu-id="16227-130">例如，在 Skype for Business 命令行管理程序中，以下 cmdlet 将云语音邮件配置为承载提供程序：</span><span class="sxs-lookup"><span data-stu-id="16227-130">For example, in the Skype for Business Management shell, the following cmdlet configures Cloud Voicemail as the hosting provider:</span></span>


```PowerShell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

## <a name="configure-a-hosted-voicemail-policy"></a><span data-ttu-id="16227-131">配置托管的语音邮件策略</span><span class="sxs-lookup"><span data-stu-id="16227-131">Configure a hosted voicemail policy</span></span>

<span data-ttu-id="16227-132">为了确保将组织的语音邮件路由到云语音邮件服务，您必须为您的组织配置托管的语音邮件策略。</span><span class="sxs-lookup"><span data-stu-id="16227-132">To ensure that voicemail for your organization is routed to the Cloud Voicemail service, you must configure a hosted voicemail policy for your organization.</span></span> <span data-ttu-id="16227-133">在许多情况下，只需要一个托管的语音邮件策略，您可以修改全局策略以满足您的所有需求。</span><span class="sxs-lookup"><span data-stu-id="16227-133">In many cases, only one hosted voicemail policy is required, and you can modify the global policy to meet all your needs.</span></span> <span data-ttu-id="16227-134">如果您的组织需要多个托管的语音邮件策略，则可以使用 cshostedvoicemailpolicy cmdlet 添加策略。</span><span class="sxs-lookup"><span data-stu-id="16227-134">If your organization requires multiple hosted voicemail policies, you can add policies by using the new-cshostedvoicemailpolicy cmdlet.</span></span>

<span data-ttu-id="16227-135">若要修改全局策略，请在更新组织和 TenantID 之后在 Skype for Business Server 命令行管理程序中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="16227-135">To modify the global policy, run the following command in the Skype for Business Server management shell after updating your Organization and TenantID:</span></span>

```PowerShell
Set-CsHostedVoicemailPolicy -Identity Global -Description "Global Cloud Voicemail Policy" -Destination exap.um.outlook.com -Organization YourDefaultDomain.onmicrosoft.com -Tenant “11111111-1111-1111-1111-111111111111”
```

- <span data-ttu-id="16227-136">**Destination**指定托管云语音邮件服务的完全限定域名（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="16227-136">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Cloud Voicemail service.</span></span> <span data-ttu-id="16227-137">此值应设置为**exap.um.outlook.com**。</span><span class="sxs-lookup"><span data-stu-id="16227-137">This value should be set to **exap.um.outlook.com**.</span></span>

- <span data-ttu-id="16227-138">"**组织**" 是分配给租户的默认域。</span><span class="sxs-lookup"><span data-stu-id="16227-138">**Organization** is the default domain assigned to your tenant.</span></span> <span data-ttu-id="16227-139">您可以通过让租户管理员登录到 office.com，单击 "管理中心" 应用程序，导航到左侧的 "**安装**"，然后单击 "**域**" 来检索此信息。</span><span class="sxs-lookup"><span data-stu-id="16227-139">You can retrieve this information by having the tenant admin log in to office.com, click on the Admin Center app, navigate to **Setup** on the left, and click **Domains**.</span></span> <span data-ttu-id="16227-140">例如： mytenant.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="16227-140">For example: mytenant.onmicrosoft.com.</span></span>

    <span data-ttu-id="16227-141">组织名称也是 Office 365 中的默认域名。</span><span class="sxs-lookup"><span data-stu-id="16227-141">The Organization name is also the Default Domain name in Office 365.</span></span>

- <span data-ttu-id="16227-142">**租户**用于在 Office 365 中标识你的租户。</span><span class="sxs-lookup"><span data-stu-id="16227-142">**Tenant** is used to identify your tenant in Office 365.</span></span> <span data-ttu-id="16227-143">有关详细信息，请参阅[查找 Office 365 租户 ID](https://support.office.com/en-us/article/find-your-office-365-tenant-id-6891b561-a52d-4ade-9f39-b492285e2c9b)。</span><span class="sxs-lookup"><span data-stu-id="16227-143">For more information, see [Find your Office 365 tenant ID](https://support.office.com/en-us/article/find-your-office-365-tenant-id-6891b561-a52d-4ade-9f39-b492285e2c9b).</span></span>

<span data-ttu-id="16227-144">若要确保已成功创建托管的语音邮件策略，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="16227-144">To ensure that a hosted voicemail policy was created successfully, run the following command:</span></span>

```PowerShell
Get-CsHostedVoicemailPolicy
```

## <a name="assign-a-hosted-voicemail-policy"></a><span data-ttu-id="16227-145">分配托管语音邮件策略</span><span class="sxs-lookup"><span data-stu-id="16227-145">Assign a hosted voicemail policy</span></span>

<span data-ttu-id="16227-146">默认情况下，将全局托管的语音邮件策略分配给所有用户。</span><span class="sxs-lookup"><span data-stu-id="16227-146">By default, the Global hosted voicemail policy is assigned to all users.</span></span> <span data-ttu-id="16227-147">如果使用其他策略，则在为用户启用托管语音邮件之前，必须首先使用[CSHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps) cmdlet 向用户授予所需的托管语音邮件策略。</span><span class="sxs-lookup"><span data-stu-id="16227-147">If you use a different policy, before enabling users for hosted voicemail, you must first grant users the desired hosted voicemail policy by using the [Grant-CSHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps) cmdlet.</span></span>

<span data-ttu-id="16227-148">例如，以下命令可向用户分配非全局托管的语音邮件策略：</span><span class="sxs-lookup"><span data-stu-id="16227-148">For example, the following command assigns a non-Global hosted voicemail policy to a user:</span></span>


```PowerShell
Get-CsUser -Identity "User1" | Grant-CsHostedVoicemailPolicy -Identity "Tag:CloudVoiceMailUsers" 
```

## <a name="enable-a-user-for-cloud-voicemail"></a><span data-ttu-id="16227-149">为用户启用云语音邮件</span><span class="sxs-lookup"><span data-stu-id="16227-149">Enable a user for Cloud Voicemail</span></span>

<span data-ttu-id="16227-150">若要使用户的语音邮件呼叫能够路由到云语音邮件，请使用[get-csuser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) Cmdlet 和 HostedVoiceMail 参数。</span><span class="sxs-lookup"><span data-stu-id="16227-150">To enable a user’s voicemail calls to be routed to Cloud Voicemail, you use the [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) cmdlet with the HostedVoiceMail parameter.</span></span> 

<span data-ttu-id="16227-151">例如，以下命令将为云语音邮件启用用户帐户：</span><span class="sxs-lookup"><span data-stu-id="16227-151">For example, the following command enables a user account for Cloud Voicemail:</span></span> 

```Set-CsUser -Identity "User1" -HostedVoiceMail $True```

<span data-ttu-id="16227-152">Cmdlet 验证云语音邮件策略--在全局、站点或用户级别--适用于此用户。</span><span class="sxs-lookup"><span data-stu-id="16227-152">The cmdlet verifies that a Cloud Voicemail policy--at the global, site, or user level--applies to this user.</span></span> <span data-ttu-id="16227-153">如果没有适用的策略，该 cmdlet 将失败。</span><span class="sxs-lookup"><span data-stu-id="16227-153">If no policy applies, the cmdlet fails.</span></span>  

<span data-ttu-id="16227-154">下一个示例为云语音邮件禁用用户帐户：</span><span class="sxs-lookup"><span data-stu-id="16227-154">The next example disables a user account for Cloud Voicemail:</span></span>

```Set-CsUser -Identity "User1" -HostedVoiceMail $False```

<span data-ttu-id="16227-155">此 cmdlet 在全局、站点或用户级别验证没有托管的语音邮件策略--适用于此用户。</span><span class="sxs-lookup"><span data-stu-id="16227-155">The cmdlet verifies that no hosted voicemail policy--at the global, site, or user level--applies to this user.</span></span> <span data-ttu-id="16227-156">如果有适用的策略，该 cmdlet 将失败。</span><span class="sxs-lookup"><span data-stu-id="16227-156">If a policy does apply, the cmdlet fails.</span></span>

> [!NOTE]
>  <span data-ttu-id="16227-157">用户必须是已启用企业语音的用户才能使用 Microsoft 云语音邮件服务。</span><span class="sxs-lookup"><span data-stu-id="16227-157">Users must be enterprise-voice enabled to use the Microsoft Cloud Voicemail Service.</span></span>
