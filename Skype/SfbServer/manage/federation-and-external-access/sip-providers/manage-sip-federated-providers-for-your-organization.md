---
title: 管理组织的 SIP 联盟提供程序
ms.reviewer: ''
ms:assetid: c78d7e9b-c496-40c6-9249-06ced9cb87f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552455(v=OCS.15)
ms:contentKeyID: 48679566
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 了解如何配置对 SIP 联盟提供程序用户的支持。
ms.openlocfilehash: 8d4c6224a66454f8fb28bb4f991faf6ad672f596
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823562"
---
# <a name="manage-sip-federated-providers-for-your-organization-in-skype-for-business-server"></a><span data-ttu-id="34ecb-103">在 Skype for Business Server 中管理组织的 SIP 联盟提供程序</span><span class="sxs-lookup"><span data-stu-id="34ecb-103">Manage SIP federated providers for your organization in Skype for Business Server</span></span>

<span data-ttu-id="34ecb-104">要配置对 SIP 联盟提供程序用户的支持，需要执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="34ecb-104">To configure support for users of SIP federated providers, you need to do the following:</span></span>

  - <span data-ttu-id="34ecb-105">配置一个或多个外部用户访问策略来支持与 SIP 联盟提供程序联系人进行通信</span><span class="sxs-lookup"><span data-stu-id="34ecb-105">Configure one or more external user access policies to support communicating with SIP federated provider contacts</span></span>

  - <span data-ttu-id="34ecb-106">指定要支持哪些托管提供程序</span><span class="sxs-lookup"><span data-stu-id="34ecb-106">Specify which hosted providers you want to support</span></span>

  - <span data-ttu-id="34ecb-107">指定要支持哪些公共 IM 提供程序</span><span class="sxs-lookup"><span data-stu-id="34ecb-107">Specify which public IM providers you want to support</span></span>

## <a name="create-or-edit-public-sip-federated-providers-in-skype-for-business-server"></a><span data-ttu-id="34ecb-108">在 Skype for Business Server 中创建或编辑公共 SIP 联盟提供程序</span><span class="sxs-lookup"><span data-stu-id="34ecb-108">Create or edit public SIP federated providers in Skype for Business Server</span></span>

<span data-ttu-id="34ecb-109">公共即时消息 (IM) 连接使组织用户可以使用 IM 与公共提供商提供的 IM 服务的用户进行通信。</span><span class="sxs-lookup"><span data-stu-id="34ecb-109">Public instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by public providers.</span></span>

<span data-ttu-id="34ecb-110">Skype for Business Server 具有用于即时消息的公共提供商配置。</span><span class="sxs-lookup"><span data-stu-id="34ecb-110">Skype for Business Server has public provider configurations for instant messaging.</span></span> <span data-ttu-id="34ecb-111">每个公共提供程序均使用提供程序的边缘服务器完全限定域名和默认验证级别“仅允许用户与其联系人列表中使用此提供程序的人员进行通信”进行配置。</span><span class="sxs-lookup"><span data-stu-id="34ecb-111">Each public provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="34ecb-112">作为默认设置，将不启用任何公共提供程序。</span><span class="sxs-lookup"><span data-stu-id="34ecb-112">As a default setting, none of the public providers are enabled.</span></span> <span data-ttu-id="34ecb-113">您应先完成许可协议和设置工作，然后再启用公共提供程序。</span><span class="sxs-lookup"><span data-stu-id="34ecb-113">You should complete license agreement and provisioning work before enabling the public providers.</span></span> <span data-ttu-id="34ecb-114">您可以先启用提供程序，然后再完成许可和设置工作。</span><span class="sxs-lookup"><span data-stu-id="34ecb-114">You can enable the provider before completing the licensing and provisioning work.</span></span> <span data-ttu-id="34ecb-115">在完成首要工作之前，用户将无法与这些提供程序的联系人进行通信。</span><span class="sxs-lookup"><span data-stu-id="34ecb-115">Users will not be able to communicate with contacts on those providers until the pre-requisite work is completed.</span></span> <span data-ttu-id="34ecb-116">有关公共提供商的许可和设置的详细信息，请参阅配置 [策略以控制公共用户加入](../external-access-policies/configure-policies-to-control-public-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="34ecb-116">For details on licensing and provisioning of public providers, see [Configure policies to control public user acces](../external-access-policies/configure-policies-to-control-public-user-access.md).</span></span>

<span data-ttu-id="34ecb-117">使用以下过程可创建或编辑公共提供程序。</span><span class="sxs-lookup"><span data-stu-id="34ecb-117">Use the following procedure to create or edit Public providers.</span></span>


### <a name="to-create-or-edit-public-providers"></a><span data-ttu-id="34ecb-118">创建或编辑公共提供程序</span><span class="sxs-lookup"><span data-stu-id="34ecb-118">To create or edit public providers</span></span>

1.  <span data-ttu-id="34ecb-119">从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或已分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。</span><span class="sxs-lookup"><span data-stu-id="34ecb-119">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="34ecb-120">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="34ecb-120">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="34ecb-121">在左侧导航栏中，单击“联盟和外部访问”，然后单击“SIP 联盟提供程序”。</span><span class="sxs-lookup"><span data-stu-id="34ecb-121">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="34ecb-122">如果您需要创建新的公共提供程序，请单击“新建”，然后单击“公共提供程序”。</span><span class="sxs-lookup"><span data-stu-id="34ecb-122">If you need to create a new Public provider, click **New** and then click **Public provider**.</span></span>

5.  <span data-ttu-id="34ecb-123">如果您需要编辑公共提供程序列表中的条目，请选择一个公共提供程序，单击“编辑”，然后单击“显示详细信息”。</span><span class="sxs-lookup"><span data-stu-id="34ecb-123">If you need to edit an entry from the list of Public providers, select a public provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="34ecb-124">在“编辑 SIP 联盟提供程序”页上，可以键入或编辑以下设置：</span><span class="sxs-lookup"><span data-stu-id="34ecb-124">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="34ecb-125">**允许与此提供程序进行通信**   选择此设置可为此提供程序的用户启用 IM。</span><span class="sxs-lookup"><span data-stu-id="34ecb-125">**Enable communications with this provider**   Selecting this setting enables IM with this provider’s users.</span></span>
    
      - <span data-ttu-id="34ecb-126">**提供程序名称**   必需属性，键入此提供程序的名称，因为 SIP 联盟提供程序的列表中将反映此名称。</span><span class="sxs-lookup"><span data-stu-id="34ecb-126">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="34ecb-127">**访问边缘服务 (FQDN) ：**   必需属性，键入要配置的提供商的访问边缘服务的完全限定域名。</span><span class="sxs-lookup"><span data-stu-id="34ecb-127">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the provider that you are configuring.</span></span> <span data-ttu-id="34ecb-128">此信息作为默认项提供，并且应仅在公共提供商对公共提供商的访问边缘服务的 FQDN 进行更改时进行更改。</span><span class="sxs-lookup"><span data-stu-id="34ecb-128">This information is provided as a default item, and should only be changed if the public provider makes a change to the FQDN of the Access Edge service at the public provider.</span></span>
    
      - <span data-ttu-id="34ecb-129">**默认验证级别**   默认设置“允许用户与其联系人列表中使用此提供程序的人员进行通信”将只允许与您接受的且位于您的联系人列表中的联系人进行通信。</span><span class="sxs-lookup"><span data-stu-id="34ecb-129">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="34ecb-p104">选择“允许用户与使用此提供程序的每个人通信”将去除您必须接收和接受联系人邀请的限制。此设置不会对可从公共提供程序网络与您联系的人员进行限制。</span><span class="sxs-lookup"><span data-stu-id="34ecb-p104">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite. This setting does not limit who can contact you from the public provider’s network.</span></span>

7.  <span data-ttu-id="34ecb-132">配置完这些设置后，请单击“提交”以进行保存，或单击“取消”以放弃更改。</span><span class="sxs-lookup"><span data-stu-id="34ecb-132">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>

## <a name="create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server"></a><span data-ttu-id="34ecb-133">在 Skype for Business Server 中创建或编辑托管 SIP 联盟提供程序</span><span class="sxs-lookup"><span data-stu-id="34ecb-133">Create or edit hosted SIP federated providers in Skype for Business Server</span></span>

<span data-ttu-id="34ecb-134">托管提供商即时消息 (IM) 连接使组织用户可以使用 IM 与托管提供商提供的 IM 服务的用户进行通信。</span><span class="sxs-lookup"><span data-stu-id="34ecb-134">Hosted provider instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by hosted providers.</span></span>

<span data-ttu-id="34ecb-135">使用提供程序的边缘服务器的完全限定域名以及默认验证级别 **仅允许用户与其联系人列表上使用此提供程序的人员进行通信** 来配置每个托管提供程序。</span><span class="sxs-lookup"><span data-stu-id="34ecb-135">Each hosted provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="34ecb-136">使用以下过程可创建或编辑托管提供程序。</span><span class="sxs-lookup"><span data-stu-id="34ecb-136">Use the following procedure to create or edit hosted providers.</span></span>

### <a name="to-create-or-edit-hosted-providers"></a><span data-ttu-id="34ecb-137">创建或编辑托管提供程序</span><span class="sxs-lookup"><span data-stu-id="34ecb-137">To create or edit hosted providers</span></span>

1.  <span data-ttu-id="34ecb-138">从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或已分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。</span><span class="sxs-lookup"><span data-stu-id="34ecb-138">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="34ecb-139">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="34ecb-139">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="34ecb-140">在左侧导航栏中，单击“联盟和外部访问”，然后单击“SIP 联盟提供程序”。</span><span class="sxs-lookup"><span data-stu-id="34ecb-140">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="34ecb-141">如果您需要创建一个新的托管提供程序，请单击“新建”，然后单击“托管提供程序”。</span><span class="sxs-lookup"><span data-stu-id="34ecb-141">If you need to create a new Hosted provider, click **New** and then click **Hosted provider**.</span></span>

5.  <span data-ttu-id="34ecb-142">如果您需要编辑托管提供程序列表上的一个条目，请选择一个托管提供程序，单击“编辑”，然后单击“显示详细信息”。</span><span class="sxs-lookup"><span data-stu-id="34ecb-142">If you need to edit an entry from the list of Hosted providers, select a hosted provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="34ecb-143">在“编辑 SIP 联盟提供程序”页面上，您可以键入或编辑下列设置：</span><span class="sxs-lookup"><span data-stu-id="34ecb-143">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="34ecb-144">**允许与此提供程序进行通信**   选择此设置将允许与此提供程序的用户通信。</span><span class="sxs-lookup"><span data-stu-id="34ecb-144">**Enable communications with this provider**   Selecting this setting enables communications with this provider’s users.</span></span>
    
      - <span data-ttu-id="34ecb-145">**提供程序名称**   必需属性，键入此提供程序的名称，因为 SIP 联盟提供程序的列表中将反映此名称。</span><span class="sxs-lookup"><span data-stu-id="34ecb-145">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="34ecb-146">**访问边缘服务 (FQDN) ：**   必需属性，键入要配置的托管提供商的访问边缘服务的完全限定域名。</span><span class="sxs-lookup"><span data-stu-id="34ecb-146">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the hosted provider that you are configuring.</span></span> <span data-ttu-id="34ecb-147">此信息应由托管提供商提供，并且只有在托管提供商对托管提供商的访问边缘服务的 FQDN 进行更改时才能更改。</span><span class="sxs-lookup"><span data-stu-id="34ecb-147">This information should be provided by the hosted provider, and should only be changed if the hosted provider makes a change to the FQDN of the Access Edge service at the hosted provider.</span></span>
    
      - <span data-ttu-id="34ecb-148">**默认验证级别:**    默认设置“允许用户与其联系人列表上使用此提供程序的人员进行通信”将通信限制在您已接受并位于您的联系人列表中的联系人。</span><span class="sxs-lookup"><span data-stu-id="34ecb-148">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="34ecb-p106">选择“允许用户与所有使用此提供程序的人员通信”可取消您必须收到并接受联系人邀请的限制。此设置不限制可从托管提供程序的网络与您联系的人。</span><span class="sxs-lookup"><span data-stu-id="34ecb-p106">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite. This setting does not limit who can contact you from the hosted provider’s network.</span></span>

7.  <span data-ttu-id="34ecb-151">当您配置完设置后，单击“提交”进行保存，或单击“取消”放弃所做的更改。</span><span class="sxs-lookup"><span data-stu-id="34ecb-151">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>


## <a name="see-also"></a><span data-ttu-id="34ecb-152">另请参阅</span><span class="sxs-lookup"><span data-stu-id="34ecb-152">See Also</span></span>


[<span data-ttu-id="34ecb-153">配置策略以控制公共用户加入</span><span class="sxs-lookup"><span data-stu-id="34ecb-153">Configure policies to control public user acces</span></span>](../external-access-policies/configure-policies-to-control-public-user-access.md)

[<span data-ttu-id="34ecb-154">启用或禁用联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="34ecb-154">Enable or disable federation and public IM connectivity</span></span>](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

