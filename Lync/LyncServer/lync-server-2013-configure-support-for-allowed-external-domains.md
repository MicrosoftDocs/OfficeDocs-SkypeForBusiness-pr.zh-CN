---
title: Lync Server 2013：配置对允许的外部域的支持
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure support for allowed external domains
ms:assetid: 3ee6e175-986d-4c33-b03a-b9f93083dca6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425908(v=OCS.15)
ms:contentKeyID: 48183943
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8926bd9cdbc64b336b72c62c5171047ae096868
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043294"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-support-for-allowed-external-domains-in-lync-server-2013"></a><span data-ttu-id="1aea6-102">在 Lync Server 2013 中配置对允许的外部域的支持</span><span class="sxs-lookup"><span data-stu-id="1aea6-102">Configure support for allowed external domains in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1aea6-103">_**上次修改的主题：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="1aea6-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="1aea6-p101">如果配置了对联盟伙伴的支持，您可以管理可与组织联盟的特定域。您将一个或多个特定外部域配置为允许的联盟域。要执行此操作，请将每个域添加到允许域列表中。即使组织启用了伙伴发现，但如果域是需要与 1,000 个以上的用户通信或每秒需要发送 20 多条消息的联盟伙伴，也请执行此操作。如果组织未启用伙伴发现，则只有添加到允许域列表的外部域的用户才能与组织内的用户一起参与 IM 会话和会议。如果要将对联盟域的访问限制为运行联盟伙伴的访问边缘服务的特定服务器，可以为允许域列表中的每个域指定运行访问边缘服务的服务器的域名。</span><span class="sxs-lookup"><span data-stu-id="1aea6-p101">If you have configured support for federated partners, you can manage which specific domains can federate with your organization. You configure one or more specific external domains as allowed federated domains. To do this, add each domain to the list of allowed domains. Even if partner discovery is enabled for your organization, do this if the domain is a federated partner that might need to communicate with more than 1,000 of your users or might need to send more than 20 messages per second. If partner discovery is not enabled for your organization, only users of external domains that you add to the allowed domains list can participate in IM and conferencing with users in your organization. If you want to restrict access for a federated domain to a specific server running the Access Edge service of the federated partner, you can specify the domain name of the server running the Access Edge service for each domain in the list of allowed domains.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1aea6-110">此过程描述如何配置对特定域的支持，但是实施对联盟用户的支持还需要组织启用对联盟用户的支持，并配置和应用策略以控制可与联盟用户协作的用户。</span><span class="sxs-lookup"><span data-stu-id="1aea6-110">This procedure describes how to configure support for specific domains, but implementing support for federated users also requires that you enable support for federated users for your organization, and configure and apply policies to control which users can collaborate with federated users.</span></span> <span data-ttu-id="1aea6-111">有关启用对联合用户的支持的详细信息，请参阅<A href="lync-server-2013-enable-or-disable-remote-user-access.md">在 Lync Server 2013 中启用或禁用远程用户访问</A>。</span><span class="sxs-lookup"><span data-stu-id="1aea6-111">For details about enabling support for federated users, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A>.</span></span> <span data-ttu-id="1aea6-112">有关配置用于控制联合的策略的详细信息，请参阅<A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">在 Lync Server 2013 中配置用于控制联合用户访问的策略</A>。</span><span class="sxs-lookup"><span data-stu-id="1aea6-112">For details about configuring policies to control federation, see <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configure policies to control federated user access in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-add-an-external-domain-to-the-list-of-allowed-domains"></a><span data-ttu-id="1aea6-113">将外部域添加到允许域列表中</span><span class="sxs-lookup"><span data-stu-id="1aea6-113">To add an external domain to the list of allowed domains</span></span>

1.  <span data-ttu-id="1aea6-114">从作为 RTCUniversalServerAdmins 组成员的用户帐户（或具有等效的用户权限）或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="1aea6-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1aea6-115">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="1aea6-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1aea6-116">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="1aea6-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1aea6-117">在左侧导航栏中，单击“外部用户访问”\*\*\*\*，然后单击“联盟域”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1aea6-117">In the left navigation bar, click **External User Access**, and then click **Federated Domains**.</span></span>

4.  <span data-ttu-id="1aea6-118">在“联盟域”\*\*\*\* 页上，单击“新建”\*\*\*\*，然后单击“允许的域”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1aea6-118">On the **Federated Domains** page, click **New**, and then click **Allowed domain**.</span></span>

5.  <span data-ttu-id="1aea6-119">在“新建联盟域”\*\*\*\* 中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="1aea6-119">In **New Federated Domains**, do the following:</span></span>
    
      - <span data-ttu-id="1aea6-120">在“域名(或 FQDN)”\*\*\*\* 中，键入联盟伙伴域的名称。</span><span class="sxs-lookup"><span data-stu-id="1aea6-120">In **Domain name (or FQDN)**, type the name of the federated partner domain.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="1aea6-p104">此名称必须是唯一的，并且不能与运行访问边缘服务的服务器的允许域的已有名称相同。该名称的长度不能超过 256 个字符。</span><span class="sxs-lookup"><span data-stu-id="1aea6-p104">This name must be unique and cannot already exist as an allowed domain for this server running the Access Edge service. The name cannot exceed 256 characters in length.</span></span><BR><span data-ttu-id="1aea6-p105">搜索联盟伙伴域名时执行后缀匹配。例如，如果键入 <STRONG>contoso.com</STRONG>，搜索还将返回域 <STRONG>it.contoso.com</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="1aea6-p105">The search on the federated partner domain name performs a suffix match. For example, if you type <STRONG>contoso.com</STRONG>, the search will also return the domain <STRONG>it.contoso.com</STRONG>.</span></span><BR><span data-ttu-id="1aea6-125">无法同时阻止和允许联盟合作伙伴域。</span><span class="sxs-lookup"><span data-stu-id="1aea6-125">A federated partner domain cannot simultaneously be blocked and allowed.</span></span> <span data-ttu-id="1aea6-126">Lync Server 2013 阻止这种情况，因此您不必同步您的列表。</span><span class="sxs-lookup"><span data-stu-id="1aea6-126">Lync Server 2013 prevents this from happening so that you do not have to synch up your lists.</span></span>

        
        </div>
    
      - <span data-ttu-id="1aea6-127">如果要将对此联盟域的访问限制为运行访问边缘服务的特定服务器的用户，请在“访问边缘服务(FQDN)”\*\*\*\* 中键入运行访问边缘服务的联盟域的服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="1aea6-127">If you want to restrict access for this federated domain to users of a specific server running the Access Edge service, in **Access Edge service (FQDN)**, type the FQDN of the federated domain’s server running the Access Edge service.</span></span>
    
      - <span data-ttu-id="1aea6-128">如果要提供其他信息，请在“注释”\*\*\*\* 中键入要与其他系统管理员共享的有关此配置的信息。</span><span class="sxs-lookup"><span data-stu-id="1aea6-128">If you want to provide additional information, in **Comment**, type information that you want to share with other system administrators about this configuration.</span></span>

6.  <span data-ttu-id="1aea6-129">单击“提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1aea6-129">Click **Commit**.</span></span>

7.  <span data-ttu-id="1aea6-130">对要允许的每个联盟伙伴域，重复步骤 4 至 6。</span><span class="sxs-lookup"><span data-stu-id="1aea6-130">Repeat steps 4 through 6 for each federated partner domain that you want to allow.</span></span>

<span data-ttu-id="1aea6-131">若要启用联盟用户的访问，还必须在组织中启用对联盟用户访问的支持。</span><span class="sxs-lookup"><span data-stu-id="1aea6-131">To enable federated user access, you must also enable support for federated user access in your organization.</span></span> <span data-ttu-id="1aea6-132">有关详细信息，请参阅[在 Lync Server 2013 中启用或禁用远程用户访问](lync-server-2013-enable-or-disable-remote-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="1aea6-132">For details, see [Enable or disable remote user access in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span></span>

<span data-ttu-id="1aea6-133">此外，还必须为希望能够与联盟用户协作的用户配置和应用策略。</span><span class="sxs-lookup"><span data-stu-id="1aea6-133">Additionally, you must configure and apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="1aea6-134">有关详细信息，请参阅[在 Lync Server 2013 中配置用于控制联盟用户访问的策略](lync-server-2013-configure-policies-to-control-federated-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="1aea6-134">For details, see [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

