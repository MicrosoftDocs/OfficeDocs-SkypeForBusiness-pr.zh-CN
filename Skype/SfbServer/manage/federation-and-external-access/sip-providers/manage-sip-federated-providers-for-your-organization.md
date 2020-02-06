---
title: 管理组织的 SIP 联盟提供程序
ms.reviewer: ''
ms:assetid: c78d7e9b-c496-40c6-9249-06ced9cb87f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552455(v=OCS.15)
ms:contentKeyID: 48679566
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 了解如何为 SIP 联合提供商的用户配置支持。
ms.openlocfilehash: 42845bfd39c65e60765ee8d3fd2f1e3a58a08aae
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818363"
---
# <a name="manage-sip-federated-providers-for-your-organization-in-skype-for-business-server"></a><span data-ttu-id="f84fa-103">在 Skype for Business Server 中管理你的组织的 SIP 联合提供商</span><span class="sxs-lookup"><span data-stu-id="f84fa-103">Manage SIP federated providers for your organization in Skype for Business Server</span></span>

<span data-ttu-id="f84fa-104">若要为 SIP 联合提供商的用户配置支持，你需要执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f84fa-104">To configure support for users of SIP federated providers, you need to do the following:</span></span>

  - <span data-ttu-id="f84fa-105">配置一个或多个外部用户访问策略以支持与 SIP 联合提供者联系人通信</span><span class="sxs-lookup"><span data-stu-id="f84fa-105">Configure one or more external user access policies to support communicating with SIP federated provider contacts</span></span>

  - <span data-ttu-id="f84fa-106">指定要支持的托管提供商</span><span class="sxs-lookup"><span data-stu-id="f84fa-106">Specify which hosted providers you want to support</span></span>

  - <span data-ttu-id="f84fa-107">指定要支持的公共 IM 提供商</span><span class="sxs-lookup"><span data-stu-id="f84fa-107">Specify which public IM providers you want to support</span></span>

## <a name="create-or-edit-public-sip-federated-providers-in-skype-for-business-server"></a><span data-ttu-id="f84fa-108">在 Skype for Business 服务器中创建或编辑公共 SIP 联合提供商</span><span class="sxs-lookup"><span data-stu-id="f84fa-108">Create or edit public SIP federated providers in Skype for Business Server</span></span>

<span data-ttu-id="f84fa-109">公共即时消息（IM）连接使组织中的用户能够使用 IM 与由公共提供商提供的 IM 服务的用户进行通信。</span><span class="sxs-lookup"><span data-stu-id="f84fa-109">Public instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by public providers.</span></span>

<span data-ttu-id="f84fa-110">Skype for business 服务器具有用于即时消息的公共提供商配置。</span><span class="sxs-lookup"><span data-stu-id="f84fa-110">Skype for Business Server has public provider configurations for instant messaging.</span></span> <span data-ttu-id="f84fa-111">每个公共提供程序均使用提供程序的边缘服务器完全限定的域名进行配置，默认验证级别**允许用户仅与其 "联系人" 列表中使用此提供商的人员进行通信**。</span><span class="sxs-lookup"><span data-stu-id="f84fa-111">Each public provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="f84fa-112">默认设置是未启用任何公共提供程序。</span><span class="sxs-lookup"><span data-stu-id="f84fa-112">As a default setting, none of the public providers are enabled.</span></span> <span data-ttu-id="f84fa-113">在启用公共提供程序之前，应完成许可证协议和预配工作。</span><span class="sxs-lookup"><span data-stu-id="f84fa-113">You should complete license agreement and provisioning work before enabling the public providers.</span></span> <span data-ttu-id="f84fa-114">你可以先启用提供程序，然后再完成授权和预配工作。</span><span class="sxs-lookup"><span data-stu-id="f84fa-114">You can enable the provider before completing the licensing and provisioning work.</span></span> <span data-ttu-id="f84fa-115">在完成先决条件工作之前，用户将无法与这些提供商上的联系人进行通信。</span><span class="sxs-lookup"><span data-stu-id="f84fa-115">Users will not be able to communicate with contacts on those providers until the pre-requisite work is completed.</span></span> <span data-ttu-id="f84fa-116">有关授权和设置公共提供程序的详细信息，请参阅[配置控制公共用户](../external-access-policies/configure-policies-to-control-public-user-access.md)访问的策略。</span><span class="sxs-lookup"><span data-stu-id="f84fa-116">For details on licensing and provisioning of public providers, see [Configure policies to control public user acces](../external-access-policies/configure-policies-to-control-public-user-access.md).</span></span>

<span data-ttu-id="f84fa-117">使用以下过程创建或编辑公共提供程序。</span><span class="sxs-lookup"><span data-stu-id="f84fa-117">Use the following procedure to create or edit Public providers.</span></span>


### <a name="to-create-or-edit-public-providers"></a><span data-ttu-id="f84fa-118">创建或编辑公共提供程序</span><span class="sxs-lookup"><span data-stu-id="f84fa-118">To create or edit public providers</span></span>

1.  <span data-ttu-id="f84fa-119">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="f84fa-119">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f84fa-120">打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="f84fa-120">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="f84fa-121">在左侧导航栏中，单击 "**联盟和外部访问**"，然后单击 " **SIP 联合提供商**"。</span><span class="sxs-lookup"><span data-stu-id="f84fa-121">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="f84fa-122">如果需要创建新的公共提供商，请单击 "**新建**"，然后单击 "**公共提供商**"。</span><span class="sxs-lookup"><span data-stu-id="f84fa-122">If you need to create a new Public provider, click **New** and then click **Public provider**.</span></span>

5.  <span data-ttu-id="f84fa-123">如果需要从公共提供商列表中编辑条目，请选择公共提供商，单击 "**编辑**"，然后单击 "**显示详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="f84fa-123">If you need to edit an entry from the list of Public providers, select a public provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="f84fa-124">在 "**编辑 SIP 联合提供商**" 页面上，您可以键入或编辑以下设置：</span><span class="sxs-lookup"><span data-stu-id="f84fa-124">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="f84fa-125">**启用与此提供商**   的通信选择此设置将启用与此提供商的用户的即时消息。</span><span class="sxs-lookup"><span data-stu-id="f84fa-125">**Enable communications with this provider**   Selecting this setting enables IM with this provider’s users.</span></span>
    
      - <span data-ttu-id="f84fa-126">**提供程序名称：**   "必需" 属性键入提供程序的名称，因为它将反映在 SIP 联合提供程序的列表中。</span><span class="sxs-lookup"><span data-stu-id="f84fa-126">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="f84fa-127">**Access edge 服务（FQDN）：**   一个必需的属性，键入要配置的提供程序的访问边缘服务的完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="f84fa-127">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the provider that you are configuring.</span></span> <span data-ttu-id="f84fa-128">此信息以默认项的形式提供，仅当公共提供程序对公共提供程序的访问边缘服务的 FQDN 进行更改时，才应更改此信息。</span><span class="sxs-lookup"><span data-stu-id="f84fa-128">This information is provided as a default item, and should only be changed if the public provider makes a change to the FQDN of the Access Edge service at the public provider.</span></span>
    
      - <span data-ttu-id="f84fa-129">**默认验证级别：**   默认设置，**允许用户与使用此提供商的联系人列表中的人员进行通信**，将对您已接受的联系人和您的联系人列表中的联系人进行通信。</span><span class="sxs-lookup"><span data-stu-id="f84fa-129">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="f84fa-130">选择 "**允许用户通过此提供商与所有人通信**"，将删除您必须收到并接受的联系人邀请的限制。</span><span class="sxs-lookup"><span data-stu-id="f84fa-130">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite.</span></span> <span data-ttu-id="f84fa-131">此设置不会限制可以通过公共提供商的网络与您联系的人员。</span><span class="sxs-lookup"><span data-stu-id="f84fa-131">This setting does not limit who can contact you from the public provider’s network.</span></span>

7.  <span data-ttu-id="f84fa-132">配置设置完成后，单击 "**提交**" 以保存，或单击 "**取消**" 放弃更改。</span><span class="sxs-lookup"><span data-stu-id="f84fa-132">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>

## <a name="create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server"></a><span data-ttu-id="f84fa-133">在 Skype for Business 服务器中创建或编辑托管 SIP 联合提供商</span><span class="sxs-lookup"><span data-stu-id="f84fa-133">Create or edit hosted SIP federated providers in Skype for Business Server</span></span>

<span data-ttu-id="f84fa-134">托管提供商即时消息（IM）连接使组织中的用户能够使用 IM 与托管提供商提供的 IM 服务的用户进行通信。</span><span class="sxs-lookup"><span data-stu-id="f84fa-134">Hosted provider instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by hosted providers.</span></span>

<span data-ttu-id="f84fa-135">每个托管提供程序均使用提供程序的边缘服务器完全限定的域名进行配置，默认验证级别**允许用户仅与其 "联系人" 列表中使用此提供程序的人员进行通信**。</span><span class="sxs-lookup"><span data-stu-id="f84fa-135">Each hosted provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="f84fa-136">使用以下过程创建或编辑托管提供程序。</span><span class="sxs-lookup"><span data-stu-id="f84fa-136">Use the following procedure to create or edit hosted providers.</span></span>

### <a name="to-create-or-edit-hosted-providers"></a><span data-ttu-id="f84fa-137">创建或编辑托管提供商</span><span class="sxs-lookup"><span data-stu-id="f84fa-137">To create or edit hosted providers</span></span>

1.  <span data-ttu-id="f84fa-138">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="f84fa-138">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f84fa-139">打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="f84fa-139">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="f84fa-140">在左侧导航栏中，单击 "**联盟和外部访问**"，然后单击 " **SIP 联合提供商**"。</span><span class="sxs-lookup"><span data-stu-id="f84fa-140">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="f84fa-141">如果需要创建新的托管提供商，请单击 "**新建**"，然后单击 "**托管提供商**"。</span><span class="sxs-lookup"><span data-stu-id="f84fa-141">If you need to create a new Hosted provider, click **New** and then click **Hosted provider**.</span></span>

5.  <span data-ttu-id="f84fa-142">如果需要从托管提供商列表中编辑条目，请选择托管提供商，单击 "**编辑**"，然后单击 "**显示详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="f84fa-142">If you need to edit an entry from the list of Hosted providers, select a hosted provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="f84fa-143">在 "**编辑 SIP 联合提供商**" 页面上，您可以键入或编辑以下设置：</span><span class="sxs-lookup"><span data-stu-id="f84fa-143">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="f84fa-144">**启用与此提供商**   的通信选择此设置可启用与此提供商的用户的通信。</span><span class="sxs-lookup"><span data-stu-id="f84fa-144">**Enable communications with this provider**   Selecting this setting enables communications with this provider’s users.</span></span>
    
      - <span data-ttu-id="f84fa-145">**提供程序名称：**   "必需" 属性键入提供程序的名称，因为它将反映在 SIP 联合提供程序的列表中。</span><span class="sxs-lookup"><span data-stu-id="f84fa-145">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="f84fa-146">**Access edge 服务（FQDN）：**   一个必需的属性，键入你要配置的托管提供程序的访问边缘服务的完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="f84fa-146">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the hosted provider that you are configuring.</span></span> <span data-ttu-id="f84fa-147">此信息应由托管提供程序提供，并且仅当托管提供程序对托管提供程序的访问边缘服务的 FQDN 进行更改时，才应更改此信息。</span><span class="sxs-lookup"><span data-stu-id="f84fa-147">This information should be provided by the hosted provider, and should only be changed if the hosted provider makes a change to the FQDN of the Access Edge service at the hosted provider.</span></span>
    
      - <span data-ttu-id="f84fa-148">**默认验证级别：**   默认设置，**允许用户与使用此提供商的联系人列表中的人员进行通信**，将对您已接受的联系人和您的联系人列表中的联系人进行通信。</span><span class="sxs-lookup"><span data-stu-id="f84fa-148">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="f84fa-149">选择 "**允许用户通过此提供商与所有人通信**"，将删除您必须收到并接受的联系人邀请的限制。</span><span class="sxs-lookup"><span data-stu-id="f84fa-149">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite.</span></span> <span data-ttu-id="f84fa-150">此设置不限制可以通过托管提供商的网络与您联系的人员。</span><span class="sxs-lookup"><span data-stu-id="f84fa-150">This setting does not limit who can contact you from the hosted provider’s network.</span></span>

7.  <span data-ttu-id="f84fa-151">配置设置完成后，单击 "**提交**" 以保存，或单击 "**取消**" 放弃更改。</span><span class="sxs-lookup"><span data-stu-id="f84fa-151">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>


## <a name="see-also"></a><span data-ttu-id="f84fa-152">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f84fa-152">See Also</span></span>


[<span data-ttu-id="f84fa-153">配置控制公共用户访问的策略</span><span class="sxs-lookup"><span data-stu-id="f84fa-153">Configure policies to control public user acces</span></span>](../external-access-policies/configure-policies-to-control-public-user-access.md)

[<span data-ttu-id="f84fa-154">启用或禁用联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="f84fa-154">Enable or disable federation and public IM connectivity</span></span>](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

