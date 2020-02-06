---
title: 管理组织的 SIP 联盟域
ms.reviewer: ''
ms:assetid: abc48829-e5cf-4651-bc38-899192f5c3bc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552454(v=OCS.15)
ms:contentKeyID: 48679565
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
description: 了解如何管理和配置可与联合的 SIP 域，
ms.openlocfilehash: af014c6c24d3655612846e97cfa7ff5c7b9c816b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818233"
---
# <a name="manage-sip-federated-domains-for-your-organization-in-skype-for-business-server"></a><span data-ttu-id="40b79-103">在 Skype for Business Server 中管理组织的 SIP 联盟域</span><span class="sxs-lookup"><span data-stu-id="40b79-103">Manage SIP federated domains for your organization in Skype for Business Server</span></span>


<span data-ttu-id="40b79-104">若要管理和配置可以与联盟的 SIP 域，可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="40b79-104">To manage and configure SIP domains that you can federate with, you can do the following:</span></span>

  - <span data-ttu-id="40b79-105">创建或编辑 SIP 联盟伙伴域的允许域列表。</span><span class="sxs-lookup"><span data-stu-id="40b79-105">Create or edit an allowed domain list of SIP federated partner domains.</span></span>

  - <span data-ttu-id="40b79-106">创建或编辑 SIP 联盟域的阻止域列表。</span><span class="sxs-lookup"><span data-stu-id="40b79-106">Create or edit a blocked domain list of SIP federated domains.</span></span>

## <a name="configure-support-for-allowed-external-domains-in-skype-for-business-server"></a><span data-ttu-id="40b79-107">在 Skype for Business 服务器中配置对允许的外部域的支持</span><span class="sxs-lookup"><span data-stu-id="40b79-107">Configure support for allowed external domains in Skype for Business Server</span></span>

<span data-ttu-id="40b79-108">如果您已为联盟伙伴配置支持，则可以管理哪些特定域可以与您的组织联盟。</span><span class="sxs-lookup"><span data-stu-id="40b79-108">If you have configured support for federated partners, you can manage which specific domains can federate with your organization.</span></span> <span data-ttu-id="40b79-109">将一个或多个特定外部域配置为 "允许的联盟域"。</span><span class="sxs-lookup"><span data-stu-id="40b79-109">You configure one or more specific external domains as allowed federated domains.</span></span> <span data-ttu-id="40b79-110">若要执行此操作，请将每个域添加到允许的域列表中。</span><span class="sxs-lookup"><span data-stu-id="40b79-110">To do this, add each domain to the list of allowed domains.</span></span> <span data-ttu-id="40b79-111">即使为你的组织启用了合作伙伴发现，如果域是联盟伙伴，并且可能需要与超过1000的用户通信，或者可能需要每秒发送20个以上的消息，请执行此操作。</span><span class="sxs-lookup"><span data-stu-id="40b79-111">Even if partner discovery is enabled for your organization, do this if the domain is a federated partner that might need to communicate with more than 1,000 of your users or might need to send more than 20 messages per second.</span></span> <span data-ttu-id="40b79-112">如果你的组织未启用合作伙伴发现，则只有你添加到 "允许的域" 列表中的外部域用户才可以与你的组织中的用户参与 IM 和会议。</span><span class="sxs-lookup"><span data-stu-id="40b79-112">If partner discovery is not enabled for your organization, only users of external domains that you add to the allowed domains list can participate in IM and conferencing with users in your organization.</span></span> <span data-ttu-id="40b79-113">如果你想要将联盟域的访问权限限制为运行联盟伙伴的访问边缘服务的特定服务器，你可以为允许的域列表中的每个域指定运行 "访问边缘" 服务的服务器的域名。</span><span class="sxs-lookup"><span data-stu-id="40b79-113">If you want to restrict access for a federated domain to a specific server running the Access Edge service of the federated partner, you can specify the domain name of the server running the Access Edge service for each domain in the list of allowed domains.</span></span>

> [!NOTE]  
> <span data-ttu-id="40b79-114">此过程介绍如何为特定域配置支持，但实现对联合用户的支持还要求你为组织启用联合用户支持，以及配置和应用策略以控制哪些用户可以协作处理联盟用户。</span><span class="sxs-lookup"><span data-stu-id="40b79-114">This procedure describes how to configure support for specific domains, but implementing support for federated users also requires that you enable support for federated users for your organization, and configure and apply policies to control which users can collaborate with federated users.</span></span> <span data-ttu-id="40b79-115">有关为联盟用户启用支持的详细信息，请参阅[启用或禁用远程用户访问](../access-edge/enable-or-disable-remote-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="40b79-115">For details about enabling support for federated users, see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span> <span data-ttu-id="40b79-116">有关配置控制联盟的策略的详细信息，请参阅[配置控制联盟用户访问的策略](../external-access-policies/configure-policies-to-control-federated-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="40b79-116">For details about configuring policies to control federation, see [Configure policies to control federated user access](../external-access-policies/configure-policies-to-control-federated-user-access.md).</span></span>

### <a name="to-add-an-external-domain-to-the-list-of-allowed-domains"></a><span data-ttu-id="40b79-117">将外部域添加到允许的域列表</span><span class="sxs-lookup"><span data-stu-id="40b79-117">To add an external domain to the list of allowed domains</span></span>

1.  <span data-ttu-id="40b79-118">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="40b79-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
2.  <span data-ttu-id="40b79-119">打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="40b79-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3.  <span data-ttu-id="40b79-120">在左侧导航栏中，单击 "**外部用户访问**"，然后单击 "**联盟域**"。</span><span class="sxs-lookup"><span data-stu-id="40b79-120">In the left navigation bar, click **External User Access**, and then click **Federated Domains**.</span></span>
4.  <span data-ttu-id="40b79-121">在 "**联盟域**" 页面上，单击 "**新建**"，然后单击 "**允许的域**"。</span><span class="sxs-lookup"><span data-stu-id="40b79-121">On the **Federated Domains** page, click **New**, and then click **Allowed domain**.</span></span>
5.  <span data-ttu-id="40b79-122">在**新的联盟域**中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="40b79-122">In **New Federated Domains**, do the following:</span></span>
    
      - <span data-ttu-id="40b79-123">在 "**域名（或 FQDN）**" 中，键入联盟伙伴域的名称。</span><span class="sxs-lookup"><span data-stu-id="40b79-123">In **Domain name (or FQDN)**, type the name of the federated partner domain.</span></span>       

        > [!NOTE]  
        > <span data-ttu-id="40b79-124">此名称必须是唯一的，并且不能作为运行 Access Edge 服务的此服务器的允许域存在。</span><span class="sxs-lookup"><span data-stu-id="40b79-124">This name must be unique and cannot already exist as an allowed domain for this server running the Access Edge service.</span></span> <span data-ttu-id="40b79-125">名称长度不能超过256个字符。</span><span class="sxs-lookup"><span data-stu-id="40b79-125">The name cannot exceed 256 characters in length.</span></span><BR><br><span data-ttu-id="40b79-126">"联盟伙伴" 域名上的搜索执行后缀匹配。</span><span class="sxs-lookup"><span data-stu-id="40b79-126">The search on the federated partner domain name performs a suffix match.</span></span> <span data-ttu-id="40b79-127">例如，如果您键入 " **contoso.com**"，搜索也将返回域**it.contoso.com**。</span><span class="sxs-lookup"><span data-stu-id="40b79-127">For example, if you type **contoso.com**, the search will also return the domain **it.contoso.com**.</span></span><BR><br><span data-ttu-id="40b79-128">联盟伙伴域不能同时被阻止和允许。</span><span class="sxs-lookup"><span data-stu-id="40b79-128">A federated partner domain cannot simultaneously be blocked and allowed.</span></span> <span data-ttu-id="40b79-129">Skype for Business 服务器阻止这种情况，因此您不必同步您的列表。</span><span class="sxs-lookup"><span data-stu-id="40b79-129">Skype for Business Server prevents this from happening so that you do not have to sync up your lists.</span></span>
    
      - <span data-ttu-id="40b79-130">如果要将此联盟域的访问权限限制为运行 Access Edge 服务的特定服务器的用户，请在 "**访问边缘服务（FQDN）**" 中，键入运行 access Edge 服务的联盟域服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="40b79-130">If you want to restrict access for this federated domain to users of a specific server running the Access Edge service, in **Access Edge service (FQDN)**, type the FQDN of the federated domain’s server running the Access Edge service.</span></span>    
      - <span data-ttu-id="40b79-131">如果要提供其他信息，请在 "**评论**" 中键入要与其他系统管理员共享的有关此配置的信息。</span><span class="sxs-lookup"><span data-stu-id="40b79-131">If you want to provide additional information, in **Comment**, type information that you want to share with other system administrators about this configuration.</span></span>

6.  <span data-ttu-id="40b79-132">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="40b79-132">Click **Commit**.</span></span>
7.  <span data-ttu-id="40b79-133">对要允许的每个联盟伙伴域重复步骤4到步骤6。</span><span class="sxs-lookup"><span data-stu-id="40b79-133">Repeat steps 4 through 6 for each federated partner domain that you want to allow.</span></span>

<span data-ttu-id="40b79-134">若要启用联盟用户访问，还必须启用组织中的联合用户访问支持。</span><span class="sxs-lookup"><span data-stu-id="40b79-134">To enable federated user access, you must also enable support for federated user access in your organization.</span></span> <span data-ttu-id="40b79-135">有关详细信息，请参阅[启用或禁用远程用户访问](../access-edge/enable-or-disable-remote-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="40b79-135">For details, see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span>

<span data-ttu-id="40b79-136">此外，你必须配置策略并将其应用到你希望能够与联盟用户协作的用户。</span><span class="sxs-lookup"><span data-stu-id="40b79-136">Additionally, you must configure and apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="40b79-137">有关详细信息，请参阅[配置用于控制联盟用户访问的策略](../external-access-policies/configure-policies-to-control-federated-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="40b79-137">For details, see [Configure policies to control federated user access](../external-access-policies/configure-policies-to-control-federated-user-access.md).</span></span>

## <a name="configure-support-for-blocked-external-domains-in-skype-for-business-server"></a><span data-ttu-id="40b79-138">在 Skype for Business 服务器中配置对阻止的外部域的支持</span><span class="sxs-lookup"><span data-stu-id="40b79-138">Configure support for blocked external domains in Skype for Business Server</span></span> 

<span data-ttu-id="40b79-139">如果你已为联盟伙伴配置支持，你可以管理阻止哪些域与你的组织进行联盟。</span><span class="sxs-lookup"><span data-stu-id="40b79-139">If you have configured support for federated partners, you can manage which domains will be blocked from federating with your organization.</span></span> <span data-ttu-id="40b79-140">被阻止域的列表将充当阻止列表（列出不允许的显式条目），并且将在联合域发现中应用（如果已启用此选项）。</span><span class="sxs-lookup"><span data-stu-id="40b79-140">The list of blocked domains will act as a block list (listing of explicit entries that are not to be allowed) and will apply in federated domain discovery, if you have this option enabled.</span></span> <span data-ttu-id="40b79-141">有关详细信息，请参阅[启用或禁用联合身份验证合作伙伴的发现](../access-edge/enable-or-disable-discovery-of-federation-partners.md)。</span><span class="sxs-lookup"><span data-stu-id="40b79-141">For details, see [Enable or disable discovery of federation partners](../access-edge/enable-or-disable-discovery-of-federation-partners.md).</span></span>

<span data-ttu-id="40b79-142">阻止一个或多个外部域连接到你的组织。</span><span class="sxs-lookup"><span data-stu-id="40b79-142">Block one or more external domains from connecting to your organization.</span></span> <span data-ttu-id="40b79-143">若要执行此操作，请将该域添加到阻止域的列表中。</span><span class="sxs-lookup"><span data-stu-id="40b79-143">To do this, add the domain to the list of blocked domains.</span></span>


### <a name="to-add-an-external-domain-to-the-list-of-blocked-domains"></a><span data-ttu-id="40b79-144">将外部域添加到阻止域的列表</span><span class="sxs-lookup"><span data-stu-id="40b79-144">To add an external domain to the list of blocked domains</span></span>

1.  <span data-ttu-id="40b79-145">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="40b79-145">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
2.  <span data-ttu-id="40b79-146">打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="40b79-146">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3.  <span data-ttu-id="40b79-147">在左侧导航栏中，单击 "**外部用户访问**"。</span><span class="sxs-lookup"><span data-stu-id="40b79-147">In the left navigation bar, click **External User Access**.</span></span>
4.  <span data-ttu-id="40b79-148">单击 "**联盟域**"，单击 "**新建**"，然后单击 "**阻止的域**"。</span><span class="sxs-lookup"><span data-stu-id="40b79-148">Click **Federated Domains**, click **New**, and then click **Blocked domain**.</span></span>
5.  <span data-ttu-id="40b79-149">在**新的联盟域**中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="40b79-149">In **New Federated Domains**, do the following:</span></span>
    
      - <span data-ttu-id="40b79-150">在 "**域名（或 FQDN）**" 中，键入要阻止的联盟伙伴域的名称。</span><span class="sxs-lookup"><span data-stu-id="40b79-150">In **Domain name (or FQDN)**, type the name of the federated partner domain that you want to block.</span></span>

        > [!NOTE]  
        > <span data-ttu-id="40b79-151">名称长度不能超过256个字符。</span><span class="sxs-lookup"><span data-stu-id="40b79-151">The name cannot exceed 256 characters in length.</span></span><BR><br><span data-ttu-id="40b79-152">"联盟伙伴" 域名上的搜索执行后缀匹配。</span><span class="sxs-lookup"><span data-stu-id="40b79-152">The search on the federated partner domain name performs a suffix match.</span></span> <span data-ttu-id="40b79-153">例如，如果您键入 " **contoso.com**"，搜索也将返回域**it.contoso.com**。</span><span class="sxs-lookup"><span data-stu-id="40b79-153">For example, if you type **contoso.com**, the search will also return the domain **it.contoso.com**.</span></span><BR><br><span data-ttu-id="40b79-154">联盟伙伴域不能同时被阻止和允许。</span><span class="sxs-lookup"><span data-stu-id="40b79-154">A federated partner domain cannot simultaneously be blocked and allowed.</span></span> <span data-ttu-id="40b79-155">Skype for Business 服务器阻止这种情况，因此您不必同步您的列表。</span><span class="sxs-lookup"><span data-stu-id="40b79-155">Skype for Business Server prevents this from happening so that you do not have to sync up your lists.</span></span>
   
      - <span data-ttu-id="40b79-156">可选在 "**批注**" 中，键入要与其他系统管理员共享的有关此配置的信息。</span><span class="sxs-lookup"><span data-stu-id="40b79-156">(Optional) In **Comment**, type information that you want to share with other system administrators about this configuration.</span></span>

6.  <span data-ttu-id="40b79-157">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="40b79-157">Click **Commit**.</span></span>
7.  <span data-ttu-id="40b79-158">对要阻止的每个联盟伙伴重复步骤4到步骤6。</span><span class="sxs-lookup"><span data-stu-id="40b79-158">Repeat steps 4 through 6 for each federated partner that you want to block.</span></span>

<span data-ttu-id="40b79-159">若要启用联盟用户访问，还必须启用组织中的联合用户访问支持。</span><span class="sxs-lookup"><span data-stu-id="40b79-159">To enable federated user access, you must also enable support for federated user access in your organization.</span></span> <span data-ttu-id="40b79-160">有关详细信息，请参阅[启用或禁用远程用户访问](../access-edge/enable-or-disable-remote-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="40b79-160">For details, see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span>

<span data-ttu-id="40b79-161">此外，你必须配置策略并将其应用到你希望能够与联盟用户协作的用户。</span><span class="sxs-lookup"><span data-stu-id="40b79-161">Additionally, you must configure and apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="40b79-162">有关详细信息，请参阅[配置用于控制联盟用户访问的策略](../external-access-policies/configure-policies-to-control-federated-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="40b79-162">For details, see [Configure policies to control federated user access](../external-access-policies/configure-policies-to-control-federated-user-access.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="40b79-163">另请参阅</span><span class="sxs-lookup"><span data-stu-id="40b79-163">See Also</span></span>

[<span data-ttu-id="40b79-164">配置策略以控制联盟用户访问</span><span class="sxs-lookup"><span data-stu-id="40b79-164">Configure policies to control federated user access</span></span>](../external-access-policies/configure-policies-to-control-federated-user-access.md)  

[<span data-ttu-id="40b79-165">启用或禁用联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="40b79-165">Enable or disable federation and public IM connectivity</span></span>](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

[<span data-ttu-id="40b79-166">启用或禁用联盟伙伴发现</span><span class="sxs-lookup"><span data-stu-id="40b79-166">Enable or disable discovery of federation partners</span></span>](../access-edge/enable-or-disable-discovery-of-federation-partners.md)
  

