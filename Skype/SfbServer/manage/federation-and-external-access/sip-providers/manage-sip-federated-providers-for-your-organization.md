---
title: 管理组织的 SIP 联盟提供程序
ms.reviewer: ''
ms:assetid: c78d7e9b-c496-40c6-9249-06ced9cb87f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552455(v=OCS.15)
ms:contentKeyID: 48679566
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 了解如何为用户的 SIP 联盟提供程序配置支持。
ms.openlocfilehash: 1259ae9d2dfd7d829caaa6dba714f0876b5500c4
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899671"
---
# <a name="manage-sip-federated-providers-for-your-organization-in-skype-for-business-server"></a><span data-ttu-id="bfe60-103">管理您的组织中 Skype 业务服务器的 SIP 联盟提供程序</span><span class="sxs-lookup"><span data-stu-id="bfe60-103">Manage SIP federated providers for your organization in Skype for Business Server</span></span>

<span data-ttu-id="bfe60-104">要配置用户的 SIP 联盟提供商支持，您需要执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="bfe60-104">To configure support for users of SIP federated providers, you need to do the following:</span></span>

  - <span data-ttu-id="bfe60-105">配置一个或多个外部用户访问策略以支持与 SIP 联盟提供程序联系人</span><span class="sxs-lookup"><span data-stu-id="bfe60-105">Configure one or more external user access policies to support communicating with SIP federated provider contacts</span></span>

  - <span data-ttu-id="bfe60-106">指定要支持哪些托管提供程序</span><span class="sxs-lookup"><span data-stu-id="bfe60-106">Specify which hosted providers you want to support</span></span>

  - <span data-ttu-id="bfe60-107">指定要支持哪些公共 IM 提供程序</span><span class="sxs-lookup"><span data-stu-id="bfe60-107">Specify which public IM providers you want to support</span></span>

## <a name="create-or-edit-public-sip-federated-providers-in-skype-for-business-server"></a><span data-ttu-id="bfe60-108">创建或编辑公共 SIP 联盟提供商 Skype 中的业务服务器</span><span class="sxs-lookup"><span data-stu-id="bfe60-108">Create or edit public SIP federated providers in Skype for Business Server</span></span>

<span data-ttu-id="bfe60-109">公共即时消息 (IM) 连接，您的组织中的用户，可以使用 IM 与 IM 服务提供的公共提供商的用户进行通信。</span><span class="sxs-lookup"><span data-stu-id="bfe60-109">Public instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by public providers.</span></span>

<span data-ttu-id="bfe60-110">Skype 业务服务器都有公共提供商配置即时消息。</span><span class="sxs-lookup"><span data-stu-id="bfe60-110">Skype for Business Server has public provider configurations for instant messaging.</span></span> <span data-ttu-id="bfe60-111">每个公共提供程序配置提供程序的边缘服务器的完全限定名称，与默认的验证级别**允许用户仅与使用此提供程序其联系人列表上的人进行通信**。</span><span class="sxs-lookup"><span data-stu-id="bfe60-111">Each public provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="bfe60-112">设置默认情况下，启用无公共提供商。</span><span class="sxs-lookup"><span data-stu-id="bfe60-112">As a default setting, none of the public providers are enabled.</span></span> <span data-ttu-id="bfe60-113">您应完成许可协议和资源调配前启用公共提供商的工作。</span><span class="sxs-lookup"><span data-stu-id="bfe60-113">You should complete license agreement and provisioning work before enabling the public providers.</span></span> <span data-ttu-id="bfe60-114">在完成的许可和资源调配工作之前，您可以启用提供程序。</span><span class="sxs-lookup"><span data-stu-id="bfe60-114">You can enable the provider before completing the licensing and provisioning work.</span></span> <span data-ttu-id="bfe60-115">用户不能与联系人进行通信在这些提供程序直到完成的系统必备的工时。</span><span class="sxs-lookup"><span data-stu-id="bfe60-115">Users will not be able to communicate with contacts on those providers until the pre-requisite work is completed.</span></span> <span data-ttu-id="bfe60-116">有关许可和公共提供商的设置的详细信息，请参阅[配置策略以控制公共用户访问](../external-access-policies/configure-policies-to-control-public-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="bfe60-116">For details on licensing and provisioning of public providers, see [Configure policies to control public user acces](../external-access-policies/configure-policies-to-control-public-user-access.md).</span></span>

<span data-ttu-id="bfe60-117">使用以下过程创建或编辑公共提供商。</span><span class="sxs-lookup"><span data-stu-id="bfe60-117">Use the following procedure to create or edit Public providers.</span></span>


### <a name="to-create-or-edit-public-providers"></a><span data-ttu-id="bfe60-118">创建或编辑公共提供商</span><span class="sxs-lookup"><span data-stu-id="bfe60-118">To create or edit public providers</span></span>

1.  <span data-ttu-id="bfe60-119">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="bfe60-119">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="bfe60-120">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="bfe60-120">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="bfe60-121">在左侧的导航栏中，单击**联盟和外部访问**，然后单击**SIP 联盟提供程序**。</span><span class="sxs-lookup"><span data-stu-id="bfe60-121">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="bfe60-122">如果您需要创建新的公共提供程序，请单击**新建**，然后单击**公共提供商**。</span><span class="sxs-lookup"><span data-stu-id="bfe60-122">If you need to create a new Public provider, click **New** and then click **Public provider**.</span></span>

5.  <span data-ttu-id="bfe60-123">如果您需要编辑公共提供商的列表的一个条目，请您可以选择一个公共提供程序，单击**编辑**，然后单击**显示详细信息**。</span><span class="sxs-lookup"><span data-stu-id="bfe60-123">If you need to edit an entry from the list of Public providers, select a public provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="bfe60-124">在**编辑 SIP 联盟提供程序**页上，您可以键入或编辑以下设置：</span><span class="sxs-lookup"><span data-stu-id="bfe60-124">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="bfe60-125">**启用与此提供程序通信**   选择此设置允许与此提供程序的用户的 IM。</span><span class="sxs-lookup"><span data-stu-id="bfe60-125">**Enable communications with this provider**   Selecting this setting enables IM with this provider’s users.</span></span>
    
      - <span data-ttu-id="bfe60-126">**提供程序名称：**   必需的属性，类型为其提供程序的名称将反映在 SIP 联盟提供商的列表。</span><span class="sxs-lookup"><span data-stu-id="bfe60-126">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="bfe60-127">**访问边缘服务 (FQDN):**   必需的属性，键入您要配置的提供程序的访问边缘服务的完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="bfe60-127">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the provider that you are configuring.</span></span> <span data-ttu-id="bfe60-128">此信息作为默认项，提供，且如果公共提供商访问边缘服务公共提供商的 fqdn 进行了更改只应被更改。</span><span class="sxs-lookup"><span data-stu-id="bfe60-128">This information is provided as a default item, and should only be changed if the public provider makes a change to the FQDN of the Access Edge service at the public provider.</span></span>
    
      - <span data-ttu-id="bfe60-129">**默认验证级别：**   默认设置，**允许用户与使用此提供程序其联系人列表上的人进行通信**将限制到的已接受和联系人列表中联系人通信。</span><span class="sxs-lookup"><span data-stu-id="bfe60-129">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="bfe60-130">选择**允许用户与任何人使用此提供程序通信**中删除的限制，您必须已收到并接受联系人邀请。</span><span class="sxs-lookup"><span data-stu-id="bfe60-130">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite.</span></span> <span data-ttu-id="bfe60-131">此设置不会限制谁可以与您联系从公共提供商网络。</span><span class="sxs-lookup"><span data-stu-id="bfe60-131">This setting does not limit who can contact you from the public provider’s network.</span></span>

7.  <span data-ttu-id="bfe60-132">当您完成配置设置，单击**提交**保存，，或单击**取消**以放弃更改。</span><span class="sxs-lookup"><span data-stu-id="bfe60-132">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>

## <a name="create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server"></a><span data-ttu-id="bfe60-133">创建或编辑业务服务器承载 Skype 中的 SIP 联盟提供程序</span><span class="sxs-lookup"><span data-stu-id="bfe60-133">Create or edit hosted SIP federated providers in Skype for Business Server</span></span>

<span data-ttu-id="bfe60-134">托管提供程序即时消息 (IM) 连接，用户在组织中可以使用 IM 与托管提供程序提供的 IM 服务的用户进行通信。</span><span class="sxs-lookup"><span data-stu-id="bfe60-134">Hosted provider instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by hosted providers.</span></span>

<span data-ttu-id="bfe60-135">每个托管的提供程序配置提供程序的边缘服务器的完全限定名称，与默认的验证级别**允许用户仅与使用此提供程序其联系人列表上的人进行通信**。</span><span class="sxs-lookup"><span data-stu-id="bfe60-135">Each hosted provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="bfe60-136">使用以下过程可创建或编辑托管提供程序。</span><span class="sxs-lookup"><span data-stu-id="bfe60-136">Use the following procedure to create or edit hosted providers.</span></span>

### <a name="to-create-or-edit-hosted-providers"></a><span data-ttu-id="bfe60-137">要创建或编辑托管提供程序</span><span class="sxs-lookup"><span data-stu-id="bfe60-137">To create or edit hosted providers</span></span>

1.  <span data-ttu-id="bfe60-138">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="bfe60-138">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="bfe60-139">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="bfe60-139">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="bfe60-140">在左侧的导航栏中，单击**联盟和外部访问**，然后单击**SIP 联盟提供程序**。</span><span class="sxs-lookup"><span data-stu-id="bfe60-140">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="bfe60-141">如果您需要创建新的托管提供程序，请单击**新建**，然后单击**托管提供程序**。</span><span class="sxs-lookup"><span data-stu-id="bfe60-141">If you need to create a new Hosted provider, click **New** and then click **Hosted provider**.</span></span>

5.  <span data-ttu-id="bfe60-142">如果您需要编辑托管提供程序的列表的一个条目，请选择一个托管提供程序，单击**编辑**，然后单击**显示详细信息**。</span><span class="sxs-lookup"><span data-stu-id="bfe60-142">If you need to edit an entry from the list of Hosted providers, select a hosted provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="bfe60-143">在**编辑 SIP 联盟提供程序**页上，您可以键入或编辑以下设置：</span><span class="sxs-lookup"><span data-stu-id="bfe60-143">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="bfe60-144">**启用与此提供程序通信**   选择此设置允许与此提供程序的用户的通信。</span><span class="sxs-lookup"><span data-stu-id="bfe60-144">**Enable communications with this provider**   Selecting this setting enables communications with this provider’s users.</span></span>
    
      - <span data-ttu-id="bfe60-145">**提供程序名称：**   必需的属性，类型为其提供程序的名称将反映在 SIP 联盟提供商的列表。</span><span class="sxs-lookup"><span data-stu-id="bfe60-145">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="bfe60-146">**访问边缘服务 (FQDN):**   必需的属性，键入您要配置的托管提供程序的访问边缘服务的完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="bfe60-146">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the hosted provider that you are configuring.</span></span> <span data-ttu-id="bfe60-147">此信息应由托管提供程序提供，且如果宿主提供程序托管提供商访问边缘服务的 fqdn 进行了更改只应被更改。</span><span class="sxs-lookup"><span data-stu-id="bfe60-147">This information should be provided by the hosted provider, and should only be changed if the hosted provider makes a change to the FQDN of the Access Edge service at the hosted provider.</span></span>
    
      - <span data-ttu-id="bfe60-148">**默认验证级别：**   默认设置，**允许用户与使用此提供程序其联系人列表上的人进行通信**将限制到的已接受和联系人列表中联系人通信。</span><span class="sxs-lookup"><span data-stu-id="bfe60-148">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="bfe60-149">选择**允许用户与任何人使用此提供程序通信**中删除的限制，您必须已收到并接受联系人邀请。</span><span class="sxs-lookup"><span data-stu-id="bfe60-149">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite.</span></span> <span data-ttu-id="bfe60-150">此设置不会限制谁可以与您联系从托管提供程序的网络。</span><span class="sxs-lookup"><span data-stu-id="bfe60-150">This setting does not limit who can contact you from the hosted provider’s network.</span></span>

7.  <span data-ttu-id="bfe60-151">当您完成配置设置，单击**提交**保存，，或单击**取消**以放弃更改。</span><span class="sxs-lookup"><span data-stu-id="bfe60-151">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>


## <a name="see-also"></a><span data-ttu-id="bfe60-152">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bfe60-152">See Also</span></span>


[<span data-ttu-id="bfe60-153">配置策略以控制公共用户访问</span><span class="sxs-lookup"><span data-stu-id="bfe60-153">Configure policies to control public user acces</span></span>](../external-access-policies/configure-policies-to-control-public-user-access.md)

[<span data-ttu-id="bfe60-154">启用或禁用联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="bfe60-154">Enable or disable federation and public IM connectivity</span></span>](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

