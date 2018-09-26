---
title: 配置语音邮件云服务
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 5/9/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 业务服务器驻留在 Skype 中实施的基于云的语音邮件的用户的说明。
ms.openlocfilehash: 9cc990cbaecfea74b269809d9e31588d61eee93c
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027814"
---
# <a name="configure-cloud-voicemail-service"></a><span data-ttu-id="845be-103">配置语音邮件云服务</span><span class="sxs-lookup"><span data-stu-id="845be-103">Configure Cloud Voicemail service</span></span>


[!INCLUDE [disclaimer](../disclaimer.md)]

## <a name="overview"></a><span data-ttu-id="845be-104">概述</span><span class="sxs-lookup"><span data-stu-id="845be-104">Overview</span></span> 
<span data-ttu-id="845be-105">本文介绍如何配置您的业务内部部署用户的 Skype 的 Microsoft 云语音邮件服务。</span><span class="sxs-lookup"><span data-stu-id="845be-105">This article describes how to configure Microsoft Cloud Voicemail service for your Skype for Business on-premises users.</span></span>  

<span data-ttu-id="845be-106">本文假定您已有 Skype 业务服务器部署中支持的拓扑，并且您已满足的先决条件设置混合连接性。</span><span class="sxs-lookup"><span data-stu-id="845be-106">This article assumes that you already have Skype for Business Server deployed in a supported topology, and that you have met the prerequisites for setting up hybrid connectivity.</span></span>

<span data-ttu-id="845be-107">有关好处的详细信息，规划注意事项以及要求实现云语音邮件，请参阅[规划语音邮件云服务](plan-cloud-voicemail.md)。</span><span class="sxs-lookup"><span data-stu-id="845be-107">For more information about the benefits, planning considerations, and requirements for implementing Cloud Voicemail, see [Plan Cloud Voicemail service](plan-cloud-voicemail.md).</span></span>




<span data-ttu-id="845be-108">配置语音邮件云涉及以下任务：</span><span class="sxs-lookup"><span data-stu-id="845be-108">Configuring Cloud Voicemail involves the following tasks:</span></span>

1.  <span data-ttu-id="845be-109">确保您已满足先决条件[规划云语音邮件服务](plan-cloud-voicemail.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="845be-109">Ensure that you have met the prerequisites as described in [Plan Cloud Voicemail service](plan-cloud-voicemail.md).</span></span>

2.  <span data-ttu-id="845be-110">确保您已设置混合连接性[计划混合连接](plan-hybrid-connectivity.md)和[配置混合连接](configure-hybrid-connectivity.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="845be-110">Ensure that you have set up hybrid connectivity as described in [Plan hybrid connectivity](plan-hybrid-connectivity.md) and [Configure hybrid connectivity](configure-hybrid-connectivity.md).</span></span> 

3.  <span data-ttu-id="845be-111">[为边缘服务器上的宿主提供商配置云语音邮件](#configure-cloud-voicemail-as-the-hosting-provider-on-the-edge-server)这篇文章中所述。</span><span class="sxs-lookup"><span data-stu-id="845be-111">[Configure Cloud Voicemail as the hosting provider on the Edge Server](#configure-cloud-voicemail-as-the-hosting-provider-on-the-edge-server) as described in this article.</span></span>

4.  <span data-ttu-id="845be-112">[配置托管语音邮件策略](#configure-a-hosted-voicemail-policy)这篇文章中所述。</span><span class="sxs-lookup"><span data-stu-id="845be-112">[Configure a hosted voicemail policy](#configure-a-hosted-voicemail-policy) as described in this article.</span></span>

5.  <span data-ttu-id="845be-113">本文中所述，[分配托管语音邮件策略](#assign-a-hosted-voicemail-policy)。</span><span class="sxs-lookup"><span data-stu-id="845be-113">[Assign a hosted voicemail policy](#assign-a-hosted-voicemail-policy) as described in this article.</span></span>

6.  <span data-ttu-id="845be-114">本文中所述，[云语音邮件为用户启用](#enable-a-user-for-cloud-voicemail)。</span><span class="sxs-lookup"><span data-stu-id="845be-114">[Enable a user for Cloud Voicemail](#enable-a-user-for-cloud-voicemail) as described in this article.</span></span>


## <a name="configure-cloud-voicemail-as-the-hosting-provider-on-the-edge-server"></a><span data-ttu-id="845be-115">将云语音邮件配置为边缘服务器上的宿主提供商</span><span class="sxs-lookup"><span data-stu-id="845be-115">Configure Cloud Voicemail as the hosting provider on the Edge Server</span></span> 

<span data-ttu-id="845be-116">通过使用带下列参数的 New-cshostingprovider cmdlet 可将云语音邮件配置为边缘服务器上的宿主提供商中：</span><span class="sxs-lookup"><span data-stu-id="845be-116">You configure Cloud Voicemail as the hosting provider on the Edge Server by using the New-CsHostingProvider cmdlet with the following parameters:</span></span>

- <span data-ttu-id="845be-117">**Identity**为正在创建; 的宿主提供商指定唯一的字符串值标识符例如，云语音邮件。</span><span class="sxs-lookup"><span data-stu-id="845be-117">**Identity** specifies a unique string value identifier for the hosting provider that you are creating; for example, Cloud Voicemail.</span></span> 

- <span data-ttu-id="845be-118">\*\*Enabled \*\* 指示您的域与承载服务提供商之间的网络连接是否已启用。</span><span class="sxs-lookup"><span data-stu-id="845be-118">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="845be-119">此参数必须设置为 True。</span><span class="sxs-lookup"><span data-stu-id="845be-119">This parameter must be set to True.</span></span>

- <span data-ttu-id="845be-120">**EnabledSharedAddressSpace**指示是否将共享 SIP 地址空间方案中使用的宿主提供商。</span><span class="sxs-lookup"><span data-stu-id="845be-120">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="845be-121">此参数必须设置为 True。</span><span class="sxs-lookup"><span data-stu-id="845be-121">This parameter must be set to True.</span></span>

- <span data-ttu-id="845be-122">**HostsOCSUsers**指示承载服务提供商是否用于承载 Skype Business Server 帐户。</span><span class="sxs-lookup"><span data-stu-id="845be-122">**HostsOCSUsers** indicates whether the hosting provider is used to host Skype for Business Server accounts.</span></span> <span data-ttu-id="845be-123">此参数必须设置为 False。</span><span class="sxs-lookup"><span data-stu-id="845be-123">This parameter must be set to False.</span></span>

- <span data-ttu-id="845be-124">**ProxyFQDN**指定宿主提供商; 使用的代理服务器的完全限定的域名 (FQDN)例如，proxyserver.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="845be-124">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider; for example, proxyserver.contoso.com.</span></span> <span data-ttu-id="845be-125">有关此信息，请与您宿主提供商联系。</span><span class="sxs-lookup"><span data-stu-id="845be-125">Contact your hosting provider for this information.</span></span> <span data-ttu-id="845be-126">不能修改此值。</span><span class="sxs-lookup"><span data-stu-id="845be-126">This value cannot be modified.</span></span> <span data-ttu-id="845be-127">如果宿主提供商更改其代理服务器，您将需要删除，然后重新创建该提供程序条目。</span><span class="sxs-lookup"><span data-stu-id="845be-127">If the hosting provider changes its proxy server, you will need to delete and then re-create the entry for that provider.</span></span>

- <span data-ttu-id="845be-128">**IsLocal**指示承载服务提供商使用的代理服务器是否包含您 Skype 企业服务器拓扑中。</span><span class="sxs-lookup"><span data-stu-id="845be-128">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Skype for Business Server topology.</span></span> <span data-ttu-id="845be-129">此参数必须设置为 False。</span><span class="sxs-lookup"><span data-stu-id="845be-129">This parameter must be set to False.</span></span>

<span data-ttu-id="845be-130">例如，业务命令行管理程序的 Skype 中, 以下 cmdlet 为宿主提供商配置云语音邮件：</span><span class="sxs-lookup"><span data-stu-id="845be-130">For example, in the Skype for Business Management shell, the following cmdlet configures Cloud Voicemail as the hosting provider:</span></span>


```
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

## <a name="configure-a-hosted-voicemail-policy"></a><span data-ttu-id="845be-131">配置托管语音邮件策略</span><span class="sxs-lookup"><span data-stu-id="845be-131">Configure a hosted voicemail policy</span></span>

<span data-ttu-id="845be-132">若要确保您的组织的语音邮件被路由到云语音邮件服务，您必须为您的组织配置托管语音邮件策略。</span><span class="sxs-lookup"><span data-stu-id="845be-132">To ensure that voicemail for your organization is routed to the Cloud Voicemail service, you must configure a hosted voicemail policy for your organization.</span></span> <span data-ttu-id="845be-133">在许多情况下，只有一个托管语音邮件策略是必需的并可以修改全局策略以满足您的需求。</span><span class="sxs-lookup"><span data-stu-id="845be-133">In many cases, only one hosted voicemail policy is required, and you can modify the global policy to meet all your needs.</span></span> <span data-ttu-id="845be-134">如果您的组织需要多个托管语音邮件策略，您可以通过使用新 cshostedvoicemailpolicy cmdlet 添加策略。</span><span class="sxs-lookup"><span data-stu-id="845be-134">If your organization requires multiple hosted voicemail policies, you can add policies by using the new-cshostedvoicemailpolicy cmdlet.</span></span>

<span data-ttu-id="845be-135">要修改全局策略，请运行以下命令在 Skype 业务服务器命令行管理程序更新您的组织和 TenantID 之后：</span><span class="sxs-lookup"><span data-stu-id="845be-135">To modify the global policy, run the following command in the Skype for Business Server management shell after updating your Organization and TenantID:</span></span>

```
Set-CsHostedVoicemailPolicy -Identity Global -Description "Global Cloud Voicemail Policy" -Destination exap.um.outlook.com -Organization YourDefaultDomain.onmicrosoft.com -TenantID “11111111-1111-1111-1111-111111111111”
```

- <span data-ttu-id="845be-136">**目标**指定承载的语音邮件云服务的完全限定的域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="845be-136">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Cloud Voicemail service.</span></span> <span data-ttu-id="845be-137">此值应设置为**exap.um.outlook.com**。</span><span class="sxs-lookup"><span data-stu-id="845be-137">This value should be set to **exap.um.outlook.com**.</span></span>

- <span data-ttu-id="845be-138">**组织**是分配给您的租户的默认域。</span><span class="sxs-lookup"><span data-stu-id="845be-138">**Organization** is the default domain assigned to your tenant.</span></span> <span data-ttu-id="845be-139">您可以通过租户管理员登录到 office.com 管理中心应用程序的左侧，导航到**安装程序**和，单击**域**检索此信息。</span><span class="sxs-lookup"><span data-stu-id="845be-139">You can retrieve this information by having the tenant admin log in to office.com, click on the Admin Center app, navigate to **Setup** on the left, and click **Domains**.</span></span> <span data-ttu-id="845be-140">例如： mytenant.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="845be-140">For example: mytenant.onmicrosoft.com.</span></span>

    <span data-ttu-id="845be-141">组织名称也是在 Office 365 中的默认域名。</span><span class="sxs-lookup"><span data-stu-id="845be-141">The Organization name is also the Default Domain name in Office 365.</span></span>

- <span data-ttu-id="845be-142">**TenantID**用于标识您在 Office 365 中的租户。</span><span class="sxs-lookup"><span data-stu-id="845be-142">**TenantID** is used to identify your tenant in Office 365.</span></span> <span data-ttu-id="845be-143">有关详细信息，请参阅[查找您的 Office 365 租户 ID](https://support.office.com/en-us/article/find-your-office-365-tenant-id-6891b561-a52d-4ade-9f39-b492285e2c9b)。</span><span class="sxs-lookup"><span data-stu-id="845be-143">For more information, see [Find your Office 365 tenant ID](https://support.office.com/en-us/article/find-your-office-365-tenant-id-6891b561-a52d-4ade-9f39-b492285e2c9b).</span></span>

<span data-ttu-id="845be-144">若要确保已成功创建托管语音邮件策略，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="845be-144">To ensure that a hosted voicemail policy was created successfully, run the following command:</span></span>

```
Get-CsHostedVoicemailPolicy
```

## <a name="assign-a-hosted-voicemail-policy"></a><span data-ttu-id="845be-145">分配托管语音邮件策略</span><span class="sxs-lookup"><span data-stu-id="845be-145">Assign a hosted voicemail policy</span></span>

<span data-ttu-id="845be-146">默认情况下，全局承载语音邮件策略分配给所有用户。</span><span class="sxs-lookup"><span data-stu-id="845be-146">By default, the Global hosted voicemail policy is assigned to all users.</span></span> <span data-ttu-id="845be-147">如果您使用不同的策略，在启用托管语音邮件的用户之前，您必须首先授予用户所需的托管语音邮件策略使用[授予 CSHostedVoicemailPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="845be-147">If you use a different policy, before enabling users for hosted voicemail, you must first grant users the desired hosted voicemail policy by using the [Grant-CSHostedVoicemailPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps) cmdlet.</span></span>

<span data-ttu-id="845be-148">例如，以下命令将非全局托管语音邮件策略分配给用户：</span><span class="sxs-lookup"><span data-stu-id="845be-148">For example, the following command assigns a non-Global hosted voicemail policy to a user:</span></span>


```
Get-CsUser -Identity "User1" | Grant-CsHostedVoicemailPolicy -Identity "Tag:CloudVoiceMailUsers" 
```

## <a name="enable-a-user-for-cloud-voicemail"></a><span data-ttu-id="845be-149">为用户启用云语音邮件</span><span class="sxs-lookup"><span data-stu-id="845be-149">Enable a user for Cloud Voicemail</span></span>

<span data-ttu-id="845be-150">若要启用用户的语音邮件的呼叫路由到云语音邮件，您可以与 HostedVoiceMail 参数中使用[Set-csuser](https://docs.microsoft.com/en-us/powershell/module/skype/set-csuser?view=skype-ps) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="845be-150">To enable a user’s voicemail calls to be routed to Cloud Voicemail, you use the [Set-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/set-csuser?view=skype-ps) cmdlet with the HostedVoiceMail parameter.</span></span> 

<span data-ttu-id="845be-151">例如，以下命令可使云语音邮件的用户帐户：</span><span class="sxs-lookup"><span data-stu-id="845be-151">For example, the following command enables a user account for Cloud Voicemail:</span></span> 

```Set-CsUser -Identity "User1" -HostedVoiceMail $True```

<span data-ttu-id="845be-152">此 cmdlet 会验证云语音邮件策略-全局、 站点或用户级别--适用于此用户。</span><span class="sxs-lookup"><span data-stu-id="845be-152">The cmdlet verifies that a Cloud Voicemail policy--at the global, site, or user level--applies to this user.</span></span> <span data-ttu-id="845be-153">如果没有策略应用，此 cmdlet 将失败。</span><span class="sxs-lookup"><span data-stu-id="845be-153">If no policy applies, the cmdlet fails.</span></span>  

<span data-ttu-id="845be-154">下一个示例禁用云语音邮件的用户帐户：</span><span class="sxs-lookup"><span data-stu-id="845be-154">The next example disables a user account for Cloud Voicemail:</span></span>

```Set-CsUser -Identity "User1" -HostedVoiceMail $False```

<span data-ttu-id="845be-155">Cmdlet 验证的任何托管语音邮件策略-全局、 站点或用户级别--适用于此用户。</span><span class="sxs-lookup"><span data-stu-id="845be-155">The cmdlet verifies that no hosted voicemail policy--at the global, site, or user level--applies to this user.</span></span> <span data-ttu-id="845be-156">如果策略不适用于，cmdlet 将失败。</span><span class="sxs-lookup"><span data-stu-id="845be-156">If a policy does apply, the cmdlet fails.</span></span>

> [!NOTE]
>  <span data-ttu-id="845be-157">用户必须是企业语音启用用于 Microsoft 云语音邮件服务。</span><span class="sxs-lookup"><span data-stu-id="845be-157">Users must be enterprise-voice enabled to use the Microsoft Cloud Voicemail Service.</span></span>