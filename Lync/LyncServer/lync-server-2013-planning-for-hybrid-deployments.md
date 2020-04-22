---
title: Lync Server 2013：规划混合部署
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for hybrid deployments
ms:assetid: f8b3d240-bc2e-42c9-acf8-d532d641a14c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205403(v=OCS.15)
ms:contentKeyID: 48185910
ms.date: 05/25/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54888a96d33dc3d9195256483f41719031847744
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780321"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-lync-server-2013-hybrid-deployments"></a><span data-ttu-id="2050f-102">规划 Lync Server 2013 混合部署</span><span class="sxs-lookup"><span data-stu-id="2050f-102">Planning for Lync Server 2013 hybrid deployments</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2050f-103">_**上次修改的主题：** 2016-05-25_</span><span class="sxs-lookup"><span data-stu-id="2050f-103">_**Topic Last Modified:** 2016-05-25_</span></span>

<span data-ttu-id="2050f-104">在规划混合部署时，应考虑对用户和网络基础结构的以下要求。</span><span class="sxs-lookup"><span data-stu-id="2050f-104">You should consider the following requirements for users and your network infrastructure while planning for a hybrid deployment.</span></span>

<div>

## <a name="infrastructure-requirements"></a><span data-ttu-id="2050f-105">基础结构要求</span><span class="sxs-lookup"><span data-stu-id="2050f-105">Infrastructure Requirements</span></span>

<span data-ttu-id="2050f-106">您必须在您的环境中配置以下各项才能实现和部署混合部署。</span><span class="sxs-lookup"><span data-stu-id="2050f-106">You must have the following configured in your environment in order to implement and deploy a hybrid deployment.</span></span>

  - <span data-ttu-id="2050f-107">启用了 Skype for Business Online 的 Microsoft Office 365 组织。</span><span class="sxs-lookup"><span data-stu-id="2050f-107">A Microsoft Office 365 organization with Skype for Business Online enabled.</span></span> <span data-ttu-id="2050f-108">请注意，您只能将一个租户用于与本地部署的混合配置。</span><span class="sxs-lookup"><span data-stu-id="2050f-108">Note that you can use only a single tenant for a hybrid configuration with your on-premises deployment.</span></span>

  - <span data-ttu-id="2050f-109">在受支持的拓扑中部署的 Skype for Business Server 或 Lync Server 的单一本地部署（基础架构）。</span><span class="sxs-lookup"><span data-stu-id="2050f-109">A single on-premises deployment (infrastructure) of Skype for Business Server or Lync Server that is deployed in a supported topology.</span></span> <span data-ttu-id="2050f-110">请参阅拓扑要求。</span><span class="sxs-lookup"><span data-stu-id="2050f-110">See Topology Requirements.</span></span>
    
    <span data-ttu-id="2050f-111">有关为混合配置 Lync Server 2013 或 Lync Server 2010 部署的信息，请参阅[配置 Lync server 2013 混合部署](lync-server-2013-configuring-hybrid-deployments.md)。</span><span class="sxs-lookup"><span data-stu-id="2050f-111">For information about configuring your Lync Server 2013 or Lync Server 2010 deployment for hybrid, see [Configuring Lync Server 2013 hybrid deployments](lync-server-2013-configuring-hybrid-deployments.md).</span></span>

  - <span data-ttu-id="2050f-112">Skype for Business Server 2015 管理工具。</span><span class="sxs-lookup"><span data-stu-id="2050f-112">Skype for Business Server 2015 administrative tools.</span></span> <span data-ttu-id="2050f-113">如果您使用的是 Lync Server 2013 或 Lync Server 2010，则可以使用 Lync Server 2013 管理工具。</span><span class="sxs-lookup"><span data-stu-id="2050f-113">If you are using Lync Server 2013 or Lync Server 2010, you can use the Lync Server 2013 administrative tools.</span></span>

  - <span data-ttu-id="2050f-114">若要支持 Office 365 单一登录，以便用户可以使用与在本地登录 Office 时相同的登录凭据来登录 Office，您可以使用 Azure Active Directory （AAD）连接的密码同步功能。</span><span class="sxs-lookup"><span data-stu-id="2050f-114">To support Single Sign-on with Office 365 so that users can use the same login credentials for signing in to Office as they do on-premises, you can use the password sync features of Azure Active Directory (AAD) Connect.</span></span> <span data-ttu-id="2050f-115">您还可以将 Active Directory 联合身份验证服务（AD FS）用于 Office 365 的单一登录。</span><span class="sxs-lookup"><span data-stu-id="2050f-115">You can also use Active Directory Federation Services (AD FS) for single sign-on with Office 365.</span></span>
    
    <span data-ttu-id="2050f-116">有关详细信息，请参阅[将您的本地标识与 Azure Active Directory 集成](https://go.microsoft.com/fwlink/p/?linkid=619754)。</span><span class="sxs-lookup"><span data-stu-id="2050f-116">For more information, see [Integrating your on-premises identities with Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=619754).</span></span>

  - <span data-ttu-id="2050f-117">用于保持本地和联机 Active Directory 对象同步的单个目录同步解决方案。</span><span class="sxs-lookup"><span data-stu-id="2050f-117">A single directory synchronization solution to keep your on-premises and online Active Directory objects synchronized.</span></span> <span data-ttu-id="2050f-118">有关目录同步的详细信息，请参阅[目录集成工具](https://go.microsoft.com/fwlink/p/?linkid=530320)。</span><span class="sxs-lookup"><span data-stu-id="2050f-118">For details about Directory Synchronization, see [Directory Integration Tools](https://go.microsoft.com/fwlink/p/?linkid=530320).</span></span>

</div>

<div>

## <a name="lync-client-support"></a><span data-ttu-id="2050f-119">Lync 客户端支持</span><span class="sxs-lookup"><span data-stu-id="2050f-119">Lync Client Support</span></span>

<span data-ttu-id="2050f-120">Lync 客户端支持的功能以及本地和联机环境中提供的功能存在一些差异。</span><span class="sxs-lookup"><span data-stu-id="2050f-120">There are some differences in the features supported in Lync clients, as well as the features available in on-premises and online environments.</span></span> <span data-ttu-id="2050f-121">在决定要在组织中的哪些位置的位置之前，您可以查看不同的 Lync Server 配置的客户端支持。</span><span class="sxs-lookup"><span data-stu-id="2050f-121">Before you decide where you want to home users in your organization, you can view the client support for the various configurations of Lync Server.</span></span> <span data-ttu-id="2050f-122">Lync 混合部署中的 Skype for Business Online 支持以下客户端：</span><span class="sxs-lookup"><span data-stu-id="2050f-122">The following clients are supported with Skype for Business Online in a Lync hybrid deployment:</span></span>

  - <span data-ttu-id="2050f-123">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="2050f-123">Lync 2010</span></span>

  - <span data-ttu-id="2050f-124">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="2050f-124">Lync 2013</span></span>

  - <span data-ttu-id="2050f-125">Lync Windows 应用商店应用</span><span class="sxs-lookup"><span data-stu-id="2050f-125">Lync Windows Store app</span></span>

  - <span data-ttu-id="2050f-126">Lync Web App</span><span class="sxs-lookup"><span data-stu-id="2050f-126">Lync Web App</span></span>

  - <span data-ttu-id="2050f-127">Lync Mobile</span><span class="sxs-lookup"><span data-stu-id="2050f-127">Lync Mobile</span></span>

  - <span data-ttu-id="2050f-128">Lync for Mac 2011</span><span class="sxs-lookup"><span data-stu-id="2050f-128">Lync for Mac 2011</span></span>

  - <span data-ttu-id="2050f-129">Lync 会议室系统</span><span class="sxs-lookup"><span data-stu-id="2050f-129">Lync Room System</span></span>

  - <span data-ttu-id="2050f-130">Lync Basic 2013</span><span class="sxs-lookup"><span data-stu-id="2050f-130">Lync Basic 2013</span></span>

<span data-ttu-id="2050f-131">有关客户端支持的详细信息，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="2050f-131">For details about client support, see the following topics:</span></span>

  - [<span data-ttu-id="2050f-132">Lync Online 客户端</span><span class="sxs-lookup"><span data-stu-id="2050f-132">Clients for Lync Online</span></span>](https://go.microsoft.com/fwlink/?linkid=281902)

  - [<span data-ttu-id="2050f-133">Lync Server 2013 的客户端比较表</span><span class="sxs-lookup"><span data-stu-id="2050f-133">Client comparison tables for Lync Server 2013</span></span>](lync-server-2013-desktop-client-comparison-tables.md)

  - [<span data-ttu-id="2050f-134">Lync Server 2013 的移动客户端比较表</span><span class="sxs-lookup"><span data-stu-id="2050f-134">Mobile client comparison tables for Lync Server 2013</span></span>](lync-server-2013-mobile-client-comparison-tables.md)

</div>

<span id="BKMK_Topology"></span>

<div>

## <a name="topology-requirements"></a><span data-ttu-id="2050f-135">拓扑要求</span><span class="sxs-lookup"><span data-stu-id="2050f-135">Topology Requirements</span></span>

<span data-ttu-id="2050f-136">若要配置与 Skype for Business Online 的混合部署，您需要具有以下受支持的拓扑之一：</span><span class="sxs-lookup"><span data-stu-id="2050f-136">To configure your deployment for hybrid with Skype for Business Online, you need to have one of the following supported topologies:</span></span>

  - <span data-ttu-id="2050f-137">一个 Skype for business Server 2015 部署，其中包含运行 Skype for Business Server 2015 的所有服务器。</span><span class="sxs-lookup"><span data-stu-id="2050f-137">A Skype for Business Server 2015 deployment with all servers running Skype for Business Server 2015.</span></span>

  - <span data-ttu-id="2050f-138">Lync Server 2013 部署，其中包含运行 Lync Server 2013 的所有服务器。</span><span class="sxs-lookup"><span data-stu-id="2050f-138">A Lync Server 2013 deployment with all servers running Lync Server 2013.</span></span>

  - <span data-ttu-id="2050f-139">Lync Server 2010 部署，其中包含运行 Lync Server 2010 的所有服务器以及最新的累积更新。</span><span class="sxs-lookup"><span data-stu-id="2050f-139">A Lync Server 2010 deployment with all servers running Lync Server 2010 with the latest cumulative updates.</span></span>
    
      - <span data-ttu-id="2050f-140">联合边缘服务器和联合边缘服务器中的下一个跃点服务器必须使用最新的累积更新运行 Lync Server 2010。</span><span class="sxs-lookup"><span data-stu-id="2050f-140">The federation Edge Server and next hop server from the federation Edge Server must be running Lync Server 2010 with the latest cumulative updates.</span></span>
    
      - <span data-ttu-id="2050f-141">Skype for Business Server 2015 或 Lync Server 2013 管理工具必须至少安装在一台服务器或管理工作站上。</span><span class="sxs-lookup"><span data-stu-id="2050f-141">The Skype for Business Server 2015 or Lync Server 2013 Administrative Tools must be installed on at least one server or management workstation.</span></span>

  - <span data-ttu-id="2050f-142">混合 Lync Server 2013 和 Skype for Business Server 2015 部署，其中至少有一个运行 Skype for Business Server 2015 的站点中具有以下服务器角色：</span><span class="sxs-lookup"><span data-stu-id="2050f-142">A mixed Lync Server 2013 and Skype for Business Server 2015 deployment with the following server roles in at least one site running Skype for Business Server 2015:</span></span>
    
      - <span data-ttu-id="2050f-143">至少一个企业版池或 Standard Edition server</span><span class="sxs-lookup"><span data-stu-id="2050f-143">At least one Enterprise Pool or Standard Edition server</span></span>
    
      - <span data-ttu-id="2050f-144">与 SIP 联盟关联的控制器池（如果存在）</span><span class="sxs-lookup"><span data-stu-id="2050f-144">The Director Pool associated with SIP federation, if it exists</span></span>
    
      - <span data-ttu-id="2050f-145">与 SIP 联盟关联的边缘池</span><span class="sxs-lookup"><span data-stu-id="2050f-145">The Edge Pool associated with SIP federation</span></span>

  - <span data-ttu-id="2050f-146">混合 Lync Server 2010 和 Skype for Business Server 2015 部署，其中至少有一个运行 Skype for Business Server 2015 的站点中具有以下服务器角色：</span><span class="sxs-lookup"><span data-stu-id="2050f-146">A mixed Lync Server 2010 and Skype for Business Server 2015 deployment with the following servers roles in at least one site running Skype for Business Server 2015:</span></span>
    
      - <span data-ttu-id="2050f-147">至少一个企业版池或 Standard Edition server</span><span class="sxs-lookup"><span data-stu-id="2050f-147">At least one Enterprise Pool or Standard Edition server</span></span>
    
      - <span data-ttu-id="2050f-148">与 SIP 联盟关联的控制器池（如果存在）</span><span class="sxs-lookup"><span data-stu-id="2050f-148">The Director Pool associated with SIP federation, if it exists</span></span>
    
      - <span data-ttu-id="2050f-149">与站点的 SIP 联盟关联的边缘池</span><span class="sxs-lookup"><span data-stu-id="2050f-149">The Edge Pool associated with SIP federation for the Site</span></span>

  - <span data-ttu-id="2050f-150">在至少一个运行 Lync Server 2013 的站点中具有以下服务器角色的混合 Lync Server 2010 和 Lync Server 2013 部署：</span><span class="sxs-lookup"><span data-stu-id="2050f-150">A mixed Lync Server 2010 and Lync Server 2013 deployment with the following server roles in at least one site running Lync Server 2013:</span></span>
    
      - <span data-ttu-id="2050f-151">站点中至少有一个企业版池或 Standard Edition server</span><span class="sxs-lookup"><span data-stu-id="2050f-151">At least one Enterprise Pool or Standard Edition server in the site</span></span>
    
      - <span data-ttu-id="2050f-152">与 SIP 联盟关联的控制器池（如果它存在于网站中）</span><span class="sxs-lookup"><span data-stu-id="2050f-152">The Director Pool associated with SIP federation, if it exists in the site</span></span>
    
      - <span data-ttu-id="2050f-153">与站点的 SIP 联盟关联的边缘池</span><span class="sxs-lookup"><span data-stu-id="2050f-153">The Edge Pool associated with SIP federation for the site</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2050f-154">所有用户管理（包括用户在本地和 UNRESOLVED_TOKEN_VAL 之间移动（skypeforbusiness））都需要使用管理工具的最新安装版本来完成。</span><span class="sxs-lookup"><span data-stu-id="2050f-154">All user management, including user moves between on-premises and UNRESOLVED_TOKEN_VAL(skypeforbusiness) Online, needs to be done using the latest installed version of the administrative tools.</span></span> <span data-ttu-id="2050f-155">管理工具必须安装在具有对现有本地部署和 Internet 的连接访问权限的单独服务器上。</span><span class="sxs-lookup"><span data-stu-id="2050f-155">The administrative tools must be installed on a separate server that has connect access to the existing on-premises deployment and to the Internet.</span></span> <span data-ttu-id="2050f-156">将用户从本地部署移动到 UNRESOLVED_TOKEN_VAL （skype16_online）的<A href="https://docs.microsoft.com/powershell/module/skype/Move-CsUser">get-csuser</A> cmdlet 必须从连接到本地部署的管理工具运行。</span><span class="sxs-lookup"><span data-stu-id="2050f-156">The <A href="https://docs.microsoft.com/powershell/module/skype/Move-CsUser">Move-CsUser</A> cmdlet to move users from your on-premises deployment to UNRESOLVED_TOKEN_VAL(skype16_online) must be run from the administrative tools connected to your on-premises deployment.</span></span>



</div>

<span data-ttu-id="2050f-157">有关支持的拓扑的详细信息，请参阅[Lync server 2013 支持的拓扑](lync-server-2013-supported-topologies.md)和[适用于企业混合部署的 Lync Server 2013 参考拓扑](https://go.microsoft.com/fwlink/p/?linkid=398709)。</span><span class="sxs-lookup"><span data-stu-id="2050f-157">For more information about supported topologies, see [Supported topologies in Lync Server 2013](lync-server-2013-supported-topologies.md), and [Lync Server 2013 Reference Topologies for Enterprise Hybrid Deployments](https://go.microsoft.com/fwlink/p/?linkid=398709).</span></span>

<span data-ttu-id="2050f-158">有关混合部署和将 PowerShell 连接到 Lync Online 的故障排除信息，请参阅[Lync Online： Lync PowerShell 和混合故障排除](https://go.microsoft.com/fwlink/p/?linkid=306718)。</span><span class="sxs-lookup"><span data-stu-id="2050f-158">For troubleshooting information about hybrid deployments and connecting PowerShell to Lync Online, see [Lync Online: Lync PowerShell and Hybrid Troubleshooting](https://go.microsoft.com/fwlink/p/?linkid=306718).</span></span>

</div>

<div>

## <a name="requirements-for-federation-allowedblocked-lists"></a><span data-ttu-id="2050f-159">联合身份验证允许/阻止列表的要求</span><span class="sxs-lookup"><span data-stu-id="2050f-159">Requirements for Federation Allowed/Blocked Lists</span></span>

<span data-ttu-id="2050f-160">"允许的域" 列表包括已配置合作伙伴边缘完全限定域名（FQDN）的域。</span><span class="sxs-lookup"><span data-stu-id="2050f-160">The Allowed domains list includes domains that have a partner Edge fully qualified domain name (FQDN) configured.</span></span> <span data-ttu-id="2050f-161">这有时称为 "允许的*合作伙伴服务器*" 或 "*直接联盟伙伴*"。</span><span class="sxs-lookup"><span data-stu-id="2050f-161">These are sometimes referred to as *allowed partner servers* or *direct federation partners*.</span></span> <span data-ttu-id="2050f-162">您应熟悉开放联合身份验证和已关闭联盟之间的区别（分别称为 "*合作伙伴发现*" 和 "*允许的合作伙伴域列表*"），在本地部署中。</span><span class="sxs-lookup"><span data-stu-id="2050f-162">You should be familiar with the difference between Open Federation and Closed Federation, referred to as *partner discovery* and *allowed partner domain list*, respectively, in on-premises deployments.</span></span>

<span data-ttu-id="2050f-163">若要成功配置混合部署，必须满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="2050f-163">The following requirements must be met to successfully configure a hybrid deployment:</span></span>

  - <span data-ttu-id="2050f-164">为本地部署和 Office 365 组织配置的域匹配必须相同。</span><span class="sxs-lookup"><span data-stu-id="2050f-164">Domain matching must be configured the same for your on-premises deployment and your Office 365 organization.</span></span> <span data-ttu-id="2050f-165">如果在本地部署上启用了合作伙伴发现，则必须为您的联机租户配置开放联盟。</span><span class="sxs-lookup"><span data-stu-id="2050f-165">If partner discovery is enabled on the on-premises deployment, then open federation must be configured for your online tenant.</span></span> <span data-ttu-id="2050f-166">如果未启用合作伙伴发现，则必须为您的联机租户配置关闭的联合身份验证。</span><span class="sxs-lookup"><span data-stu-id="2050f-166">If partner discovery is not enabled, then closed federation must be configured for your online tenant.</span></span>

  - <span data-ttu-id="2050f-167">本地部署中的阻止域列表必须与您的联机租户的阻止域列表完全匹配。</span><span class="sxs-lookup"><span data-stu-id="2050f-167">The Blocked domains list in the on-premises deployment must exactly match the Blocked domains list for your online tenant.</span></span>

  - <span data-ttu-id="2050f-168">本地部署中的允许域列表必须与您的联机租户的允许域列表完全匹配。</span><span class="sxs-lookup"><span data-stu-id="2050f-168">The Allowed domains list in the on-premises deployment must exactly match the Allowed domains list for your online tenant.</span></span>

  - <span data-ttu-id="2050f-169">必须为使用 Lync Online 控制面板配置的联机租户的外部通信启用联合。</span><span class="sxs-lookup"><span data-stu-id="2050f-169">Federation must be enabled for the external communications for the online tenant, which is configured by using the Lync Online Control Panel.</span></span>

</div>

<div>

## <a name="dns-settings"></a><span data-ttu-id="2050f-170">DNS 设置</span><span class="sxs-lookup"><span data-stu-id="2050f-170">DNS Settings</span></span>

<span data-ttu-id="2050f-171">在为混合部署创建 DNS 记录时，所有 Lync 外部 DNS 记录都应指向内部部署基础结构。</span><span class="sxs-lookup"><span data-stu-id="2050f-171">When creating DNS records for hybrid deployments, all Lync external DNS records should point to the on-premises infrastructure.</span></span> <span data-ttu-id="2050f-172">有关所需 DNS 记录的详细信息，请参阅[Lync Server 2013 的域名系统（DNS）要求](lync-server-2013-domain-name-system-dns-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2050f-172">For details on required DNS records, please refer to [Domain Name System (DNS) requirements for Lync Server 2013](lync-server-2013-domain-name-system-dns-requirements.md).</span></span>

<span data-ttu-id="2050f-173">此外，还需要确保下表中所述的 DNS 解析在本地部署中运行：</span><span class="sxs-lookup"><span data-stu-id="2050f-173">Additionally you need to ensure that the DNS resolution described in the following table works in your on-premises deployment:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2050f-174">DNS 记录</span><span class="sxs-lookup"><span data-stu-id="2050f-174">DNS record</span></span></p></td>
<td><p><span data-ttu-id="2050f-175">可解析者</span><span class="sxs-lookup"><span data-stu-id="2050f-175">Resolvable by</span></span></p></td>
<td><p><span data-ttu-id="2050f-176">DNS 要求</span><span class="sxs-lookup"><span data-stu-id="2050f-176">DNS requirement</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2050f-177">_Sipfederationtls _tcp 的 DNS SRV 记录。&lt;sipdomain.com&gt;用于所有受支持的 SIP 域解析为访问边缘外部 IP （s）</span><span class="sxs-lookup"><span data-stu-id="2050f-177">DNS SRV record for _sipfederationtls._tcp.&lt;sipdomain.com&gt; for all supported SIP domains resolving to Access Edge external IP(s)</span></span></p></td>
<td><p><span data-ttu-id="2050f-178">边缘服务器</span><span class="sxs-lookup"><span data-stu-id="2050f-178">Edge server(s)</span></span></p></td>
<td><p><span data-ttu-id="2050f-179">在混合配置中启用联合通信。</span><span class="sxs-lookup"><span data-stu-id="2050f-179">Enable federated communication in a hybrid configuration.</span></span> <span data-ttu-id="2050f-180">边缘服务器需要知道为在本地和联机之间拆分的 SIP 域路由联盟流量的位置。</span><span class="sxs-lookup"><span data-stu-id="2050f-180">The Edge Server needs to know where to route federated traffic for the SIP domain that is split between on premises and online.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2050f-181">用于边缘 Web 会议服务 FQDN 的 DNS A 记录，例如，webcon.contoso.com 解析为 Web 会议边缘外部 IP （s）</span><span class="sxs-lookup"><span data-stu-id="2050f-181">DNS A record(s) for Edge Web Conferencing Service FQDN, e.g. webcon.contoso.com resolving to Web Conferencing Edge external IP(s)</span></span></p></td>
<td><p><span data-ttu-id="2050f-182">连接到用户计算机的内部公司网络</span><span class="sxs-lookup"><span data-stu-id="2050f-182">Internal corporate network connected users’ computers</span></span></p></td>
<td><p><span data-ttu-id="2050f-183">使联机用户能够在本地托管会议中显示或查看内容。</span><span class="sxs-lookup"><span data-stu-id="2050f-183">Enable online users to present or view content in on-premises hosted meetings.</span></span> <span data-ttu-id="2050f-184">内容包括 PowerPoint 文件、白板、投票和共享便笺。</span><span class="sxs-lookup"><span data-stu-id="2050f-184">Content includes PowerPoint files, whiteboards, polls, and shared notes.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="2050f-185">根据组织中配置 DNS 的方式，您可能需要将这些记录添加到相应 SIP 域的内部托管 DNS 区域中，以提供对这些记录的内部 DNS 解析。</span><span class="sxs-lookup"><span data-stu-id="2050f-185">Depending on how DNS is configured in your organization, you may need to add these records to the internal hosted DNS zone for the corresponding SIP domain(s) to provide internal DNS resolution to these records.</span></span>

</div>

<div>

## <a name="firewall-considerations"></a><span data-ttu-id="2050f-186">防火墙注意事项</span><span class="sxs-lookup"><span data-stu-id="2050f-186">Firewall Considerations</span></span>

<span data-ttu-id="2050f-p113">您的网络上的计算机必须能够执行标准 Internet DNS 查找。如果这些计算机可以连接标准 Internet 站点，表明您的网络符合此要求。</span><span class="sxs-lookup"><span data-stu-id="2050f-p113">Computers on your network must be able to perform standard Internet DNS lookups. If these computers can reach standard Internet sites, your network meets this requirement.</span></span>

<span data-ttu-id="2050f-189">根据 Microsoft Online Services 数据中心的位置，您还必须将网络防火墙设备配置为根据通配符域名（例如，所有来自\*outlook.com 的流量）接受连接。</span><span class="sxs-lookup"><span data-stu-id="2050f-189">Depending on the location of your Microsoft Online Services data center, you must also configure your network firewall devices to accept connections based on wildcard domain names (for example, all traffic from \*.outlook.com).</span></span> <span data-ttu-id="2050f-190">如果组织的防火墙不支持通配符名称配置，则必须手动确定要允许和指定端口的 IP 地址范围。</span><span class="sxs-lookup"><span data-stu-id="2050f-190">If your organization’s firewalls do not support wildcard name configurations, you will have to manually determine the IP address ranges that you would like to allow and the specified ports.</span></span>

<span data-ttu-id="2050f-191">请参阅帮助主题 " [Office 365 url 和 IP 地址范围](https://go.microsoft.com/fwlink/p/?linkid=252942)"。</span><span class="sxs-lookup"><span data-stu-id="2050f-191">Refer to the Help topic [Office 365 URLs and IP address ranges](https://go.microsoft.com/fwlink/p/?linkid=252942).</span></span>

</div>

<span id="b"></span>

<div>

## <a name="port-and-protocol-requirements"></a><span data-ttu-id="2050f-192">端口和协议要求</span><span class="sxs-lookup"><span data-stu-id="2050f-192">Port and Protocol Requirements</span></span>

<span data-ttu-id="2050f-193">除了内部 Lync Server 2013 通信的端口要求之外，还必须配置以下端口。</span><span class="sxs-lookup"><span data-stu-id="2050f-193">In addition to the port requirements for internal Lync Server 2013 communication, you must also configure the following ports.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2050f-194">协议/端口</span><span class="sxs-lookup"><span data-stu-id="2050f-194">Protocol / Port</span></span></th>
<th><span data-ttu-id="2050f-195">应用程序</span><span class="sxs-lookup"><span data-stu-id="2050f-195">Applications</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2050f-196">TCP 443</span><span class="sxs-lookup"><span data-stu-id="2050f-196">TCP 443</span></span></p></td>
<td><p><span data-ttu-id="2050f-197">对入站方向开放</span><span class="sxs-lookup"><span data-stu-id="2050f-197">Open inbound</span></span></p>
<ul>
<li><p><span data-ttu-id="2050f-198">Active Directory 联合身份验证服务（联合服务器角色）</span><span class="sxs-lookup"><span data-stu-id="2050f-198">Active Directory Federation Services (federation server role)</span></span></p>
<p><span data-ttu-id="2050f-199">有关详细信息，请参阅<a href="https://go.microsoft.com/fwlink/p/?linkid=281899">了解 AD FS 角色服务</a>。</span><span class="sxs-lookup"><span data-stu-id="2050f-199">For more information, see <a href="https://go.microsoft.com/fwlink/p/?linkid=281899">Understanding AD FS Role Services</a>.</span></span></p></li>
<li><p><span data-ttu-id="2050f-200">Active Directory 联合身份验证服务（代理服务器角色）</span><span class="sxs-lookup"><span data-stu-id="2050f-200">Active Directory Federation Services (proxy server role)</span></span></p></li>
<li><p><span data-ttu-id="2050f-201">Microsoft Online Services 门户</span><span class="sxs-lookup"><span data-stu-id="2050f-201">Microsoft Online Services Portal</span></span></p></li>
<li><p><span data-ttu-id="2050f-202">我的公司门户</span><span class="sxs-lookup"><span data-stu-id="2050f-202">My Company Portal</span></span></p></li>
<li><p><span data-ttu-id="2050f-203">Outlook Web App</span><span class="sxs-lookup"><span data-stu-id="2050f-203">Outlook Web App</span></span></p></li>
<li><p><span data-ttu-id="2050f-204">Lync 客户端（从内部部署 Lync Server 与 Lync Online 的通信）</span><span class="sxs-lookup"><span data-stu-id="2050f-204">Lync client (communication to Lync Online from on-premises Lync Server)</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2050f-205">TCP 80 和 443</span><span class="sxs-lookup"><span data-stu-id="2050f-205">TCP 80 and 443</span></span></p></td>
<td><p><span data-ttu-id="2050f-206">对入站方向开放</span><span class="sxs-lookup"><span data-stu-id="2050f-206">Open inbound</span></span></p>
<ul>
<li><p><span data-ttu-id="2050f-207">Microsoft Online Services 目录同步工具</span><span class="sxs-lookup"><span data-stu-id="2050f-207">Microsoft Online Services Directory Synchronization Tool</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2050f-208">TCP 5061</span><span class="sxs-lookup"><span data-stu-id="2050f-208">TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="2050f-209">在边缘服务器上打开入站/出站</span><span class="sxs-lookup"><span data-stu-id="2050f-209">Open inbound/outbound on the Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2050f-210">PSOM/TLS 443</span><span class="sxs-lookup"><span data-stu-id="2050f-210">PSOM/TLS 443</span></span></p></td>
<td><p><span data-ttu-id="2050f-211">为数据共享会话打开入站/出站</span><span class="sxs-lookup"><span data-stu-id="2050f-211">Open inbound/outbound for data sharing sessions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2050f-212">STUN/TCP 443</span><span class="sxs-lookup"><span data-stu-id="2050f-212">STUN/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="2050f-213">为音频、视频、应用程序共享会话打开入站/出站</span><span class="sxs-lookup"><span data-stu-id="2050f-213">Open inbound/outbound for audio, video, application sharing sessions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2050f-214">STUN/UDP 3478</span><span class="sxs-lookup"><span data-stu-id="2050f-214">STUN/UDP 3478</span></span></p></td>
<td><p><span data-ttu-id="2050f-215">为音频和视频会话打开入站/出站</span><span class="sxs-lookup"><span data-stu-id="2050f-215">Open inbound/outbound for audio and video sessions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2050f-216">RTP/TCP 50000-59999</span><span class="sxs-lookup"><span data-stu-id="2050f-216">RTP/TCP 50000-59999</span></span></p></td>
<td><p><span data-ttu-id="2050f-217">为音频和视频会话打开出站</span><span class="sxs-lookup"><span data-stu-id="2050f-217">Open outbound for audio and video sessions</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-accounts-and-data"></a><span data-ttu-id="2050f-218">用户帐户和数据</span><span class="sxs-lookup"><span data-stu-id="2050f-218">User Accounts and Data</span></span>

<span data-ttu-id="2050f-219">在 Lync Server 2013 混合部署中，您要在家中使用的任何用户都必须先在本地部署中创建，以便在 Active Directory 域服务中创建用户帐户。</span><span class="sxs-lookup"><span data-stu-id="2050f-219">In a Lync Server 2013 hybrid deployment, any user that you want to home in Lync Online must first be created in the on-premises deployment, so that the user account is created in Active Directory Domain Services.</span></span> <span data-ttu-id="2050f-220">然后，您可以将用户移动到 Skype for Business Online，这将移动用户的联系人列表。</span><span class="sxs-lookup"><span data-stu-id="2050f-220">You can then move the user to Skype for Business Online, which will move the user’s contact list.</span></span>

<span data-ttu-id="2050f-221">当您在 Lync 本地部署和使用 AD FS 和 Dirsync Online 部署之间同步用户帐户时，您需要在内部部署和联机 Lync 部署之间同步组织中所有 Lync 用户的 AD 帐户，即使用户未移动到 Lync Online 也是如此。</span><span class="sxs-lookup"><span data-stu-id="2050f-221">When you synchronize user accounts between your Lync on-premises and Lync Online deployments with AD FS and Dirsync, you need to synchronize the AD accounts for all Lync users in your organization between your on-premises and online Lync deployments, even if users are not moved to Lync Online.</span></span> <span data-ttu-id="2050f-222">如果不同步所有用户，组织中的内部部署用户和联机用户之间的通信可能无法按预期工作。</span><span class="sxs-lookup"><span data-stu-id="2050f-222">If you do not synchronize all users, communication between on-premises and online users in your organization may not work as expected.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2050f-223">如果用户是使用适用于 Office 365 的联机门户创建的，则该用户帐户将不会与本地 Active Directory 同步，并且该用户将不会存在于本地 Active Directory 中。</span><span class="sxs-lookup"><span data-stu-id="2050f-223">If the user is created by using the online portal for Office 365, the user account will not be synchronized with on-premises Active Directory, and the user will not exist in the on-premises Active Directory.</span></span> <span data-ttu-id="2050f-224">如果你已在 Lync Online 中创建用户，并且想要使用本地 Lync Server 配置混合，请参阅<A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Lync Server 2013 中的将用户从 Lync Online 移动到 lync 本地</A>。</span><span class="sxs-lookup"><span data-stu-id="2050f-224">If you have already created users in Lync Online, and want to configure hybrid with an on-premises Lync Server, see <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Moving users from Lync Online to Lync on-premises in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="2050f-225">在规划混合部署时，还应考虑以下与用户相关的问题。</span><span class="sxs-lookup"><span data-stu-id="2050f-225">You should also consider the following user-related issues when planning for a hybrid deployment.</span></span>

  - <span data-ttu-id="2050f-226">**用户联系人**   Lync Online 用户的联系人限制为250。</span><span class="sxs-lookup"><span data-stu-id="2050f-226">**User contacts**   The limit for contacts for Lync Online users is 250.</span></span> <span data-ttu-id="2050f-227">当帐户移动到 Lync Online 时，该号码之外的所有联系人都将从用户的联系人列表中删除。</span><span class="sxs-lookup"><span data-stu-id="2050f-227">Any contacts beyond that number will be removed from the user’s contact list when the account is moved to Lync Online.</span></span>

  - <span data-ttu-id="2050f-228">**即时消息和状态**   用户联系人列表、组和访问控制列表（acl）随用户帐户一起迁移。</span><span class="sxs-lookup"><span data-stu-id="2050f-228">**Instant Messaging and Presence**   User contact lists, groups, and access control lists (ACLs) are migrated with the user account.</span></span>

  - <span data-ttu-id="2050f-229">**会议数据、会议内容和计划会议**   此内容不会随用户帐户一起迁移。</span><span class="sxs-lookup"><span data-stu-id="2050f-229">**Conferencing data, meeting content, and scheduled meetings**   This content is not migrated with the user account.</span></span> <span data-ttu-id="2050f-230">用户必须在其帐户迁移到 Lync Online 之后重新安排会议。</span><span class="sxs-lookup"><span data-stu-id="2050f-230">Users must reschedule meetings after their accounts are migrated to Lync Online.</span></span>

</div>

<div>

## <a name="user-policies-and-features"></a><span data-ttu-id="2050f-231">用户策略和功能</span><span class="sxs-lookup"><span data-stu-id="2050f-231">User Policies and Features</span></span>

  - <span data-ttu-id="2050f-232">在 Lync Server 2013 混合环境中，可以对本地或联机的即时消息、语音和会议启用用户，但不能同时启用两者。</span><span class="sxs-lookup"><span data-stu-id="2050f-232">In a Lync Server 2013 hybrid environment, users can be enabled for Instant Messaging, voice, and meetings either on-premises or online, but not both simultaneously.</span></span>

  - <span data-ttu-id="2050f-233">**Lync 客户端**   在移动到 Lync Online 时，某些用户可能需要新的客户端版本。</span><span class="sxs-lookup"><span data-stu-id="2050f-233">**Lync Client**    Some users may require a new client version when they are moved to Lync Online.</span></span> <span data-ttu-id="2050f-234">对于 Office 通信服务器 2007 R2，在迁移到 Lync Online 之前，必须将用户移动到 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="2050f-234">For Office Communications Server 2007 R2, users must be moved to a Lync Server 2013 pool prior to migration to Lync Online.</span></span>
    
    <span data-ttu-id="2050f-235">有关客户端支持的详细信息，请参阅[适用于 Lync Online 的客户端](https://go.microsoft.com/fwlink/p/?linkid=281902)和[支持的 lync 客户端和网络端口配置](https://go.microsoft.com/fwlink/p/?linkid=281901)。</span><span class="sxs-lookup"><span data-stu-id="2050f-235">For more information about client support, see [Clients for Lync Online](https://go.microsoft.com/fwlink/p/?linkid=281902) and [Supported Lync clients and network port configurations](https://go.microsoft.com/fwlink/p/?linkid=281901).</span></span>

  - <span data-ttu-id="2050f-236">**本地策略和配置（非用户）**   联机和本地策略需要单独的配置。</span><span class="sxs-lookup"><span data-stu-id="2050f-236">**On-premises policies and configuration (non-user)**   Online and on-premises policies require separate configuration.</span></span> <span data-ttu-id="2050f-237">无法设置同适用于二者的全局策略。</span><span class="sxs-lookup"><span data-stu-id="2050f-237">You cannot set global policies that apply to both.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

