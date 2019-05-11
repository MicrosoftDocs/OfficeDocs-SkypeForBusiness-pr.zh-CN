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
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 了解如何管理和配置您可以与，联盟的 SIP 域
ms.openlocfilehash: aa793c5380c4baaa18876bfa2e2891a8260670dd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33903171"
---
# <a name="manage-sip-federated-domains-for-your-organization-in-skype-for-business-server"></a><span data-ttu-id="1b24d-103">管理您的组织中 Skype 业务服务器的 SIP 联盟域</span><span class="sxs-lookup"><span data-stu-id="1b24d-103">Manage SIP federated domains for your organization in Skype for Business Server</span></span>


<span data-ttu-id="1b24d-104">若要管理和配置可与其进行联盟的 SIP 域，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="1b24d-104">To manage and configure SIP domains that you can federate with, you can do the following:</span></span>

  - <span data-ttu-id="1b24d-105">创建或编辑 SIP 联盟伙伴域的允许的域列表。</span><span class="sxs-lookup"><span data-stu-id="1b24d-105">Create or edit an allowed domain list of SIP federated partner domains.</span></span>

  - <span data-ttu-id="1b24d-106">创建或编辑 SIP 联盟域的阻止的域列表。</span><span class="sxs-lookup"><span data-stu-id="1b24d-106">Create or edit a blocked domain list of SIP federated domains.</span></span>

## <a name="configure-support-for-allowed-external-domains-in-skype-for-business-server"></a><span data-ttu-id="1b24d-107">在 Skype for Business Server 配置为允许的外部域的支持</span><span class="sxs-lookup"><span data-stu-id="1b24d-107">Configure support for allowed external domains in Skype for Business Server</span></span>

<span data-ttu-id="1b24d-108">如果已配置联盟伙伴的支持，您可以管理的特定域可以与组织联盟。</span><span class="sxs-lookup"><span data-stu-id="1b24d-108">If you have configured support for federated partners, you can manage which specific domains can federate with your organization.</span></span> <span data-ttu-id="1b24d-109">您将一个或多个特定的外部域配置为允许的联盟域。</span><span class="sxs-lookup"><span data-stu-id="1b24d-109">You configure one or more specific external domains as allowed federated domains.</span></span> <span data-ttu-id="1b24d-110">若要执行此操作，请将每个域添加到允许域列表。</span><span class="sxs-lookup"><span data-stu-id="1b24d-110">To do this, add each domain to the list of allowed domains.</span></span> <span data-ttu-id="1b24d-111">即使您的组织启用合作伙伴搜索之后，如果这样做域为联盟的伙伴，可能需要与多个 1,000 个用户进行通信，或者可能需要发送多个是每秒 20 条消息。</span><span class="sxs-lookup"><span data-stu-id="1b24d-111">Even if partner discovery is enabled for your organization, do this if the domain is a federated partner that might need to communicate with more than 1,000 of your users or might need to send more than 20 messages per second.</span></span> <span data-ttu-id="1b24d-112">如果未为组织启用合作伙伴发现，只有您将添加到允许的域列表的外部域的用户可以参与 IM 和会议与您的组织中的用户。</span><span class="sxs-lookup"><span data-stu-id="1b24d-112">If partner discovery is not enabled for your organization, only users of external domains that you add to the allowed domains list can participate in IM and conferencing with users in your organization.</span></span> <span data-ttu-id="1b24d-113">如果您想要限制到特定服务器上运行的访问边缘服务的联盟伙伴的联盟域的访问，您可以指定运行访问边缘服务的每个域的允许域列表中的服务器的域名。</span><span class="sxs-lookup"><span data-stu-id="1b24d-113">If you want to restrict access for a federated domain to a specific server running the Access Edge service of the federated partner, you can specify the domain name of the server running the Access Edge service for each domain in the list of allowed domains.</span></span>

> [!NOTE]  
> <span data-ttu-id="1b24d-114">此过程介绍如何配置为特定域的支持，但还实现联盟用户的支持要求您为组织启用联盟用户的支持和配置，并将策略应用于哪些用户可以的控制与联盟用户进行协作。</span><span class="sxs-lookup"><span data-stu-id="1b24d-114">This procedure describes how to configure support for specific domains, but implementing support for federated users also requires that you enable support for federated users for your organization, and configure and apply policies to control which users can collaborate with federated users.</span></span> <span data-ttu-id="1b24d-115">有关启用联盟用户的支持的详细信息，请参阅[启用或禁用远程用户访问](../access-edge/enable-or-disable-remote-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="1b24d-115">For details about enabling support for federated users, see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span> <span data-ttu-id="1b24d-116">有关配置策略以控制联盟的详细信息，请参阅[配置策略以控制联盟用户访问](../external-access-policies/configure-policies-to-control-federated-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="1b24d-116">For details about configuring policies to control federation, see [Configure policies to control federated user access](../external-access-policies/configure-policies-to-control-federated-user-access.md).</span></span>

### <a name="to-add-an-external-domain-to-the-list-of-allowed-domains"></a><span data-ttu-id="1b24d-117">将外部域添加到允许域列表</span><span class="sxs-lookup"><span data-stu-id="1b24d-117">To add an external domain to the list of allowed domains</span></span>

1.  <span data-ttu-id="1b24d-118">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="1b24d-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
2.  <span data-ttu-id="1b24d-119">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="1b24d-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3.  <span data-ttu-id="1b24d-120">在左侧的导航栏中，单击**外部用户访问**，然后单击**联盟域**。</span><span class="sxs-lookup"><span data-stu-id="1b24d-120">In the left navigation bar, click **External User Access**, and then click **Federated Domains**.</span></span>
4.  <span data-ttu-id="1b24d-121">在**联盟域**页上，单击**新建**，然后单击**允许的域**。</span><span class="sxs-lookup"><span data-stu-id="1b24d-121">On the **Federated Domains** page, click **New**, and then click **Allowed domain**.</span></span>
5.  <span data-ttu-id="1b24d-122">在**新建联盟域**中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="1b24d-122">In **New Federated Domains**, do the following:</span></span>
    
      - <span data-ttu-id="1b24d-123">在**域名 （或 FQDN）**，键入的联盟的伙伴域名。</span><span class="sxs-lookup"><span data-stu-id="1b24d-123">In **Domain name (or FQDN)**, type the name of the federated partner domain.</span></span>       

        > [!NOTE]  
        > <span data-ttu-id="1b24d-124">此名称必须是唯一的并且不能为此服务器的运行访问边缘服务不允许域已存在。</span><span class="sxs-lookup"><span data-stu-id="1b24d-124">This name must be unique and cannot already exist as an allowed domain for this server running the Access Edge service.</span></span> <span data-ttu-id="1b24d-125">该名称不得超过 256 个字符的长度。</span><span class="sxs-lookup"><span data-stu-id="1b24d-125">The name cannot exceed 256 characters in length.</span></span><BR><br><span data-ttu-id="1b24d-126">联盟的伙伴域名上的搜索执行后缀匹配。</span><span class="sxs-lookup"><span data-stu-id="1b24d-126">The search on the federated partner domain name performs a suffix match.</span></span> <span data-ttu-id="1b24d-127">例如，如果键入**contoso.com**，则搜索也将返回域**it.contoso.com**。</span><span class="sxs-lookup"><span data-stu-id="1b24d-127">For example, if you type **contoso.com**, the search will also return the domain **it.contoso.com**.</span></span><BR><br><span data-ttu-id="1b24d-128">不能同时阻止并且允许联盟的伙伴域。</span><span class="sxs-lookup"><span data-stu-id="1b24d-128">A federated partner domain cannot simultaneously be blocked and allowed.</span></span> <span data-ttu-id="1b24d-129">Skype 业务服务器阻止此发生，以便您无需同步您的列表。</span><span class="sxs-lookup"><span data-stu-id="1b24d-129">Skype for Business Server prevents this from happening so that you do not have to sync up your lists.</span></span>
    
      - <span data-ttu-id="1b24d-130">如果要将此联合域的访问限制的特定服务器中**访问边缘服务 (FQDN)**，运行访问边缘服务，用户键入运行访问边缘服务的联盟的域服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="1b24d-130">If you want to restrict access for this federated domain to users of a specific server running the Access Edge service, in **Access Edge service (FQDN)**, type the FQDN of the federated domain’s server running the Access Edge service.</span></span>    
      - <span data-ttu-id="1b24d-131">如果您想要提供其他信息，在**注释**键入要与有关此配置其他系统管理员共享的信息。</span><span class="sxs-lookup"><span data-stu-id="1b24d-131">If you want to provide additional information, in **Comment**, type information that you want to share with other system administrators about this configuration.</span></span>

6.  <span data-ttu-id="1b24d-132">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="1b24d-132">Click **Commit**.</span></span>
7.  <span data-ttu-id="1b24d-133">对于您要允许每个联盟的伙伴域，重复步骤 4 至 6。</span><span class="sxs-lookup"><span data-stu-id="1b24d-133">Repeat steps 4 through 6 for each federated partner domain that you want to allow.</span></span>

<span data-ttu-id="1b24d-134">若要启用联盟的用户访问，您还必须在组织中启用对联盟的用户访问的支持。</span><span class="sxs-lookup"><span data-stu-id="1b24d-134">To enable federated user access, you must also enable support for federated user access in your organization.</span></span> <span data-ttu-id="1b24d-135">有关详细信息，请参阅[启用或禁用远程用户访问](../access-edge/enable-or-disable-remote-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="1b24d-135">For details, see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span>

<span data-ttu-id="1b24d-136">此外，您必须配置并将策略应用于您希望能够与联盟用户进行协作的用户。</span><span class="sxs-lookup"><span data-stu-id="1b24d-136">Additionally, you must configure and apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="1b24d-137">有关详细信息，请参阅[配置策略以控制联盟用户访问](../external-access-policies/configure-policies-to-control-federated-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="1b24d-137">For details, see [Configure policies to control federated user access](../external-access-policies/configure-policies-to-control-federated-user-access.md).</span></span>

## <a name="configure-support-for-blocked-external-domains-in-skype-for-business-server"></a><span data-ttu-id="1b24d-138">在 Skype for Business Server 中配置对阻止的外部域的支持</span><span class="sxs-lookup"><span data-stu-id="1b24d-138">Configure support for blocked external domains in Skype for Business Server</span></span> 

<span data-ttu-id="1b24d-139">如果已配置联盟伙伴的支持，您可以管理哪些域将阻止与您的组织建立联盟。</span><span class="sxs-lookup"><span data-stu-id="1b24d-139">If you have configured support for federated partners, you can manage which domains will be blocked from federating with your organization.</span></span> <span data-ttu-id="1b24d-140">阻止的域列表将充当阻止列表 （将不允许的显式条目的列表），并且如果您已启用此选项将应用在联盟的域发现。</span><span class="sxs-lookup"><span data-stu-id="1b24d-140">The list of blocked domains will act as a block list (listing of explicit entries that are not to be allowed) and will apply in federated domain discovery, if you have this option enabled.</span></span> <span data-ttu-id="1b24d-141">有关详细信息，请参阅[启用或禁用联盟伙伴的发现](../access-edge/enable-or-disable-discovery-of-federation-partners.md)。</span><span class="sxs-lookup"><span data-stu-id="1b24d-141">For details, see [Enable or disable discovery of federation partners](../access-edge/enable-or-disable-discovery-of-federation-partners.md).</span></span>

<span data-ttu-id="1b24d-142">阻止从连接到组织的一个或多个外部域。</span><span class="sxs-lookup"><span data-stu-id="1b24d-142">Block one or more external domains from connecting to your organization.</span></span> <span data-ttu-id="1b24d-143">若要执行此操作，请将域添加到阻止的域列表。</span><span class="sxs-lookup"><span data-stu-id="1b24d-143">To do this, add the domain to the list of blocked domains.</span></span>


### <a name="to-add-an-external-domain-to-the-list-of-blocked-domains"></a><span data-ttu-id="1b24d-144">将外部域添加到阻止的域列表</span><span class="sxs-lookup"><span data-stu-id="1b24d-144">To add an external domain to the list of blocked domains</span></span>

1.  <span data-ttu-id="1b24d-145">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="1b24d-145">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
2.  <span data-ttu-id="1b24d-146">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="1b24d-146">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3.  <span data-ttu-id="1b24d-147">在左侧的导航栏中，单击**外部用户访问**。</span><span class="sxs-lookup"><span data-stu-id="1b24d-147">In the left navigation bar, click **External User Access**.</span></span>
4.  <span data-ttu-id="1b24d-148">单击**联盟域**，单击**新建**，然后单击**被阻止的域**。</span><span class="sxs-lookup"><span data-stu-id="1b24d-148">Click **Federated Domains**, click **New**, and then click **Blocked domain**.</span></span>
5.  <span data-ttu-id="1b24d-149">在**新建联盟域**中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="1b24d-149">In **New Federated Domains**, do the following:</span></span>
    
      - <span data-ttu-id="1b24d-150">在**域名 （或 FQDN）** 中，键入您想要阻止的联盟的伙伴域的名称。</span><span class="sxs-lookup"><span data-stu-id="1b24d-150">In **Domain name (or FQDN)**, type the name of the federated partner domain that you want to block.</span></span>

        > [!NOTE]  
        > <span data-ttu-id="1b24d-151">该名称不得超过 256 个字符的长度。</span><span class="sxs-lookup"><span data-stu-id="1b24d-151">The name cannot exceed 256 characters in length.</span></span><BR><br><span data-ttu-id="1b24d-152">联盟的伙伴域名上的搜索执行后缀匹配。</span><span class="sxs-lookup"><span data-stu-id="1b24d-152">The search on the federated partner domain name performs a suffix match.</span></span> <span data-ttu-id="1b24d-153">例如，如果键入**contoso.com**，则搜索也将返回域**it.contoso.com**。</span><span class="sxs-lookup"><span data-stu-id="1b24d-153">For example, if you type **contoso.com**, the search will also return the domain **it.contoso.com**.</span></span><BR><br><span data-ttu-id="1b24d-154">不能同时阻止并且允许联盟的伙伴域。</span><span class="sxs-lookup"><span data-stu-id="1b24d-154">A federated partner domain cannot simultaneously be blocked and allowed.</span></span> <span data-ttu-id="1b24d-155">Skype 业务服务器阻止此发生，以便您无需同步您的列表。</span><span class="sxs-lookup"><span data-stu-id="1b24d-155">Skype for Business Server prevents this from happening so that you do not have to sync up your lists.</span></span>
   
      - <span data-ttu-id="1b24d-156">（可选）在**注释**中，键入要与有关此配置其他系统管理员共享的信息。</span><span class="sxs-lookup"><span data-stu-id="1b24d-156">(Optional) In **Comment**, type information that you want to share with other system administrators about this configuration.</span></span>

6.  <span data-ttu-id="1b24d-157">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="1b24d-157">Click **Commit**.</span></span>
7.  <span data-ttu-id="1b24d-158">对每个要阻止的联盟伙伴重复步骤 4 至 6。</span><span class="sxs-lookup"><span data-stu-id="1b24d-158">Repeat steps 4 through 6 for each federated partner that you want to block.</span></span>

<span data-ttu-id="1b24d-159">若要启用联盟的用户访问，您还必须在组织中启用对联盟的用户访问的支持。</span><span class="sxs-lookup"><span data-stu-id="1b24d-159">To enable federated user access, you must also enable support for federated user access in your organization.</span></span> <span data-ttu-id="1b24d-160">有关详细信息，请参阅[启用或禁用远程用户访问](../access-edge/enable-or-disable-remote-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="1b24d-160">For details, see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span>

<span data-ttu-id="1b24d-161">此外，您必须配置并将策略应用于您希望能够与联盟用户进行协作的用户。</span><span class="sxs-lookup"><span data-stu-id="1b24d-161">Additionally, you must configure and apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="1b24d-162">有关详细信息，请参阅[配置策略以控制联盟用户访问](../external-access-policies/configure-policies-to-control-federated-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="1b24d-162">For details, see [Configure policies to control federated user access](../external-access-policies/configure-policies-to-control-federated-user-access.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="1b24d-163">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1b24d-163">See Also</span></span>

[<span data-ttu-id="1b24d-164">配置策略以控制联盟用户访问</span><span class="sxs-lookup"><span data-stu-id="1b24d-164">Configure policies to control federated user access</span></span>](../external-access-policies/configure-policies-to-control-federated-user-access.md)  

[<span data-ttu-id="1b24d-165">启用或禁用联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="1b24d-165">Enable or disable federation and public IM connectivity</span></span>](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

[<span data-ttu-id="1b24d-166">启用或禁用联盟伙伴发现</span><span class="sxs-lookup"><span data-stu-id="1b24d-166">Enable or disable discovery of federation partners</span></span>](../access-edge/enable-or-disable-discovery-of-federation-partners.md)
  

