---
title: Lync Server 2013：分支站点恢复解决方案
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch-site resiliency solutions
ms:assetid: 1700f99b-709c-4e47-88eb-c0a5490e26e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398234(v=OCS.15)
ms:contentKeyID: 48183517
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a72d07e1ccdae6c433de92057e6e9414fff20153
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150881"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-solutions-in-lync-server-2013"></a><span data-ttu-id="a8001-102">Lync Server 2013 中的分支站点恢复解决方案</span><span class="sxs-lookup"><span data-stu-id="a8001-102">Branch-site resiliency solutions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a8001-103">_**上次修改的主题：** 2014-12-10_</span><span class="sxs-lookup"><span data-stu-id="a8001-103">_**Topic Last Modified:** 2014-12-10_</span></span>

<span data-ttu-id="a8001-104">为组织提供分支站点复原的好处显而易见。</span><span class="sxs-lookup"><span data-stu-id="a8001-104">There are obvious advantages to providing branch-site resiliency to your organization.</span></span> <span data-ttu-id="a8001-105">具体来说，如果您失去了与中央站点的连接，分支站点用户将继续拥有企业语音服务和语音邮件（如果配置了语音邮件重新路由设置，请参阅[Lync Server 2013 的分支站点恢复要求](lync-server-2013-branch-site-resiliency-requirements.md)）。</span><span class="sxs-lookup"><span data-stu-id="a8001-105">Specifically, if you lose the connection to the central site, branch site users will continue to have Enterprise Voice service and voice mail (if you configure voice mail rerouting settings; for details, see [Branch-site resiliency requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md)).</span></span> <span data-ttu-id="a8001-106">但是，对于用户少于 25 名的站点，复原解决方案可能无法为投资带来相应的回报。</span><span class="sxs-lookup"><span data-stu-id="a8001-106">However, for sites with fewer than 25 users, a resiliency solution may not provide a sufficient return on investment.</span></span>

<span data-ttu-id="a8001-p102">如果决定提供分支站点复原，有三个选项可供使用。使用下表帮助确定最适合贵组织的选项。</span><span class="sxs-lookup"><span data-stu-id="a8001-p102">If you decide to provide branch-site resiliency, you have three options. The following table can help you determine the best option for your organization.</span></span>

<div>



<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a8001-109">如果...</span><span class="sxs-lookup"><span data-stu-id="a8001-109">If you…</span></span></th>
<th><span data-ttu-id="a8001-110">建议使用...</span><span class="sxs-lookup"><span data-stu-id="a8001-110">We recommend that you use a…</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a8001-111">分支站点承载 25 到 1000 位用户，并且投资回报不支持完整部署，或本地管理支持不可用</span><span class="sxs-lookup"><span data-stu-id="a8001-111">Host between 25 and 1000 users at your branch site, and if the return on investment does not support a full deployment or where local administrative support is unavailable</span></span></p></td>
<td><p><span data-ttu-id="a8001-112">Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="a8001-112">Survivable Branch Appliance</span></span></p>
<p><span data-ttu-id="a8001-113">Survivable 分支设备是行业标准刀片服务器，其中包含在 Windows Server 2008 R2 上运行的 Lync Server 注册台和中介服务器。</span><span class="sxs-lookup"><span data-stu-id="a8001-113">The Survivable Branch Appliance is an industry-standard blade server with a Lync Server Registrar and Mediation Server running on Windows Server 2008 R2.</span></span> <span data-ttu-id="a8001-114">Survivable 分支设备还包含一个公共交换电话网络（PSTN）网关。</span><span class="sxs-lookup"><span data-stu-id="a8001-114">The Survivable Branch Appliance also contains a public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="a8001-115">合格第三方设备（由 Microsoft 合作伙伴在 Survivable Branch Appliance (SBA) 资格鉴定/认证计划中开发）在 WAN 发生故障时可以提供连续的 PSTN 连接，但不能提供可恢复的状态和会议，因为这些功能依赖于中央站点的前端服务器。</span><span class="sxs-lookup"><span data-stu-id="a8001-115">Qualified third-party devices (developed by Microsoft partners in the Survivable Branch Appliance (SBA) qualification/certification program) provide a continuous PSTN connection in the event of WAN failure, but this approach does not provide resilient presence and conferencing because these features depend on Front End Servers at the central site.</span></span></p>
<p><span data-ttu-id="a8001-116">有关 Survivable 分支设备的详细信息， &quot;请参阅本主题&quot;后面的 Survivable 分支设备详细信息。</span><span class="sxs-lookup"><span data-stu-id="a8001-116">For details about Survivable Branch Appliances, see &quot;Survivable Branch Appliance Details,&quot; later in this topic.</span></span></p>
<p><span data-ttu-id="a8001-117"><strong>注意：</strong>如果您决定还要将 SIP 中继与您的 Survivable 分支设备一起使用，请联系您的 Survivable 分支设备供应商，了解最适合您的组织的服务提供商。</span><span class="sxs-lookup"><span data-stu-id="a8001-117"><strong>Note:</strong> If you decide to also use a SIP trunk with your Survivable Branch Appliance, contact your Survivable Branch Appliance vendor to learn about which service provider is best for your organization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a8001-118">在分支站点上的1000和2000用户之间的主机，缺少一个强健的 WAN 连接，并且已培训的 Lync Server 管理员可用</span><span class="sxs-lookup"><span data-stu-id="a8001-118">Host between 1000 and 2000 users at your branch site, lack a resilient WAN connection, and have trained Lync Server administrators available</span></span></p></td>
<td><p><span data-ttu-id="a8001-119">Survivable 分支服务器或两个 Survivable 分支装置。</span><span class="sxs-lookup"><span data-stu-id="a8001-119">Survivable Branch Server or two Survivable Branch Appliances.</span></span></p>
<p><span data-ttu-id="a8001-120">Survivable 分支服务器是一个 Windows Server 会议指定的硬件要求，其中安装了 Lync Server 注册器和中介服务器软件。</span><span class="sxs-lookup"><span data-stu-id="a8001-120">The Survivable Branch Server is a Windows Server meeting specified hardware requirements that has Lync Server Registrar and Mediation Server software installed on it.</span></span> <span data-ttu-id="a8001-121">它必须连接到 PSTN 网关或电话服务提供商的 SIP 中继。</span><span class="sxs-lookup"><span data-stu-id="a8001-121">It must connect to either a PSTN gateway or a SIP trunk to a telephone service provider.</span></span></p>
<p><span data-ttu-id="a8001-122">有关 Survivable 分支服务器的详细信息， &quot;请参阅本主题&quot;后面的 Survivable 分支服务器详细信息。</span><span class="sxs-lookup"><span data-stu-id="a8001-122">For details about Survivable Branch Servers, see &quot;Survivable Branch Server Details,&quot; later in this topic.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a8001-123">如果你除了支持最高5000个用户的语音功能之外还需要状态和会议功能，并且已培训的 Lync Server 管理员可用</span><span class="sxs-lookup"><span data-stu-id="a8001-123">If you require presence and conferencing features in addition to voice features for up to 5000 users, and have trained Lync Server administrators available</span></span></p></td>
<td><p><span data-ttu-id="a8001-124">将 Standard Edition Server 部署为中央站点，而非分支站点。</span><span class="sxs-lookup"><span data-stu-id="a8001-124">Deploy as a central site with a Standard Edition server rather than as a branch site.</span></span></p>
<p><span data-ttu-id="a8001-125">在出现 WAN 故障时，完全规模的 Lync Server 部署可提供连续的 PSTN 连接和弹性状态和会议。</span><span class="sxs-lookup"><span data-stu-id="a8001-125">A full-scale Lync Server deployment provides a continuous PSTN connection and resilient presence and conferencing in the event of WAN failure.</span></span></p>
<p><span data-ttu-id="a8001-126">有关准备此解决方案的详细信息，请参阅<a href="lync-server-2013-planning-for-your-organization.md">组织规划 Lync server 2013</a>、<a href="lync-server-2013-determining-your-system-requirements.md">确定 lync server 2013 的系统要求</a>、<a href="lync-server-2013-determining-your-infrastructure-requirements.md">确定 lync server 2013 的基础结构要求</a>以及规划文档的其他相关部分。</span><span class="sxs-lookup"><span data-stu-id="a8001-126">For details about preparing for this solution, see <a href="lync-server-2013-planning-for-your-organization.md">Organization planning for Lync Server 2013</a>, <a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a>, <a href="lync-server-2013-determining-your-infrastructure-requirements.md">Determining your infrastructure requirements for Lync Server 2013</a>, and other relevant sections of the Planning documentation.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="resiliency-topologies"></a><span data-ttu-id="a8001-127">复原拓扑</span><span class="sxs-lookup"><span data-stu-id="a8001-127">Resiliency Topologies</span></span>

<span data-ttu-id="a8001-128">下图显示了推荐的分支站点复原拓扑。</span><span class="sxs-lookup"><span data-stu-id="a8001-128">The following figure shows the recommended topologies for branch-site resiliency.</span></span>

<span data-ttu-id="a8001-129">**分支站点复原选项**</span><span class="sxs-lookup"><span data-stu-id="a8001-129">**Branch site resiliency options**</span></span>

<span data-ttu-id="a8001-130">![语音分支复原选项](images/Gg398234.47eecd19-08ae-4d82-acbe-61f0de760306(OCS.15).jpg "语音分支复原选项")</span><span class="sxs-lookup"><span data-stu-id="a8001-130">![Voice Branch Resiliency Options](images/Gg398234.47eecd19-08ae-4d82-acbe-61f0de760306(OCS.15).jpg "Voice Branch Resiliency Options")</span></span>

</div>

<div>

## <a name="survivable-branch-appliance-details"></a><span data-ttu-id="a8001-131">Survivable Branch Appliance 详细信息</span><span class="sxs-lookup"><span data-stu-id="a8001-131">Survivable Branch Appliance Details</span></span>

<span data-ttu-id="a8001-132">Lync Server Survivable 分支设备包括以下组件：</span><span class="sxs-lookup"><span data-stu-id="a8001-132">The Lync Server Survivable Branch Appliance includes the following components:</span></span>

  - <span data-ttu-id="a8001-133">注册器，用于用户身份验证、注册和呼叫路由</span><span class="sxs-lookup"><span data-stu-id="a8001-133">A Registrar for user authentication, registration and call routing</span></span>

  - <span data-ttu-id="a8001-134">中介服务器，用于处理注册器和 PSTN 网关之间的信号</span><span class="sxs-lookup"><span data-stu-id="a8001-134">A Mediation Server for handling signaling between the Registrar and a PSTN gateway</span></span>

  - <span data-ttu-id="a8001-135">PSTN 网关，用于在 WAN 中断时，将呼叫作为回退传输路由到 PSTN</span><span class="sxs-lookup"><span data-stu-id="a8001-135">A PSTN gateway for routing calls to the PSTN as a fallback transport in the event of a WAN outage</span></span>

  - <span data-ttu-id="a8001-136">SQL Server Express，用于本地用户数据存储</span><span class="sxs-lookup"><span data-stu-id="a8001-136">SQL Server Express for local user data storage</span></span>

<span data-ttu-id="a8001-137">Survivable 分支设备还包括 PSTN 中继、模拟端口和以太网适配器。</span><span class="sxs-lookup"><span data-stu-id="a8001-137">The Survivable Branch Appliance also includes PSTN trunks, analog ports, and an Ethernet adapter.</span></span>

<span data-ttu-id="a8001-138">如果到中央站点的分支站点的 WAN 连接不可用，则内部分支用户将继续使用 Survivable 分支设备注册器进行注册，并通过使用 Survivable 分支设备连接获取不间断语音服务。PSTN。</span><span class="sxs-lookup"><span data-stu-id="a8001-138">If the branch site’s WAN connection to a central site becomes unavailable, internal branch users continue to be registered with the Survivable Branch Appliance Registrar and obtain uninterrupted voice service by using the Survivable Branch Appliance connection to the PSTN.</span></span> <span data-ttu-id="a8001-139">从主机或其他远程位置进行连接的分支站点用户，可在连接到分支站点的 WAN 链路不可用时，在中央站点上的注册服务器中注册。</span><span class="sxs-lookup"><span data-stu-id="a8001-139">Branch site users who connect from home or other remote locations will be able to register with a Registrar server at a central site if the WAN link to the branch site is unavailable.</span></span> <span data-ttu-id="a8001-140">这些用户将具有完整的统一通信功能，一个例外是分支站点的入站呼叫将转到语音邮件。</span><span class="sxs-lookup"><span data-stu-id="a8001-140">These users will have full unified communications functionality, with the one exception that inbound calls to the branch site will go to voice mail.</span></span> <span data-ttu-id="a8001-141">WAN 连接可用时，将为分支站点用户恢复完整功能。</span><span class="sxs-lookup"><span data-stu-id="a8001-141">When the WAN connection becomes available, full functionality should be restored to branch site users.</span></span> <span data-ttu-id="a8001-142">无论是故障转移到 Survivable 分支设备还是服务还原，都不需要 IT 管理员。</span><span class="sxs-lookup"><span data-stu-id="a8001-142">Neither the failover to the Survivable Branch Appliance nor the restoration of service requires the presence of an IT administrator.</span></span>

<span data-ttu-id="a8001-143">Lync Server 最高支持分支站点上的两个 Survivable 分支装置。</span><span class="sxs-lookup"><span data-stu-id="a8001-143">Lync Server supports up to two Survivable Branch Appliance at a branch site.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a8001-144">驻留在 Lync Server Survivable 分支设备上的用户无法创建新的聊天室或查看现有聊天室的会议室卡片。</span><span class="sxs-lookup"><span data-stu-id="a8001-144">Users who are homed on a Lync Server Survivable Branch Appliance are unable to create new Chat Rooms or view the Room Card for existing rooms.</span></span>



</div>

<div>

## <a name="survivable-branch-appliance-deployment-overview"></a><span data-ttu-id="a8001-145">Survivable Branch Appliance 部署概述</span><span class="sxs-lookup"><span data-stu-id="a8001-145">Survivable Branch Appliance Deployment Overview</span></span>

<span data-ttu-id="a8001-146">Survivable 分支设备由与 Microsoft 合作的原始设备制造商生产，并由增值零售商代表它们部署。</span><span class="sxs-lookup"><span data-stu-id="a8001-146">The Survivable Branch Appliance is manufactured by original equipment manufacturers in partnership with Microsoft and deployed on their behalf by value-added retailers.</span></span> <span data-ttu-id="a8001-147">只有在中央站点部署了 Lync Server，与分支站点的 WAN 连接已就位，并为其启用了企业语音的分支站点用户，才应进行此部署。</span><span class="sxs-lookup"><span data-stu-id="a8001-147">This deployment should occur only after Lync Server has been deployed at the central site, a WAN connection to the branch site is in place, and branch site users are enabled for Enterprise Voice.</span></span>

<span data-ttu-id="a8001-148">有关这些阶段的详细信息，请参阅部署文档中的[使用 Lync Server 2013 部署 Survivable 分支装置或服务器](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md)。</span><span class="sxs-lookup"><span data-stu-id="a8001-148">For details about these phases, see [Deploying a Survivable Branch Appliance or Server with Lync Server 2013](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md) in the Deployment documentation.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a8001-149">阶段</span><span class="sxs-lookup"><span data-stu-id="a8001-149">Phase</span></span></th>
<th><span data-ttu-id="a8001-150">步骤</span><span class="sxs-lookup"><span data-stu-id="a8001-150">Steps</span></span></th>
<th><span data-ttu-id="a8001-151">用户权限</span><span class="sxs-lookup"><span data-stu-id="a8001-151">User Rights</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a8001-152">为 Survivable 分支设备设置 Active Directory 域服务</span><span class="sxs-lookup"><span data-stu-id="a8001-152">Set up Active Directory Domain Services for the Survivable Branch Appliance</span></span></p></td>
<td><p><span data-ttu-id="a8001-153"><strong>在中央站点：</strong></span><span class="sxs-lookup"><span data-stu-id="a8001-153"><strong>At the central site:</strong></span></span></p>
<ol>
<li><p><span data-ttu-id="a8001-154">为将在分支站点安装和激活 Survivable 分支设备的技术人员创建域用户帐户（或企业标识）。</span><span class="sxs-lookup"><span data-stu-id="a8001-154">Create a domain user account (or enterprise identity) for the technician who will install and activate the Survivable Branch Appliance at the branch site.</span></span></p></li>
<li><p><span data-ttu-id="a8001-155">为 Active Directory 域服务中的 Survivable 分支设备创建计算机帐户（包含适用的完全限定域名（FQDN））。</span><span class="sxs-lookup"><span data-stu-id="a8001-155">Create a computer account (with the applicable fully qualified domain name (FQDN)) for Survivable Branch Appliance in Active Directory Domain Services.</span></span></p></li>
<li><p><span data-ttu-id="a8001-156">在拓扑生成器中，创建并发布 Survivable 分支设备。</span><span class="sxs-lookup"><span data-stu-id="a8001-156">In Topology Builder, create and publish the Survivable Branch Appliance.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="a8001-157">技术人员用户帐户必须是 RTCUniversalSBATechnicians 的成员。</span><span class="sxs-lookup"><span data-stu-id="a8001-157">The technician user account must be a member of RTCUniversalSBATechnicians.</span></span> <span data-ttu-id="a8001-158">Survivable 分支设备必须属于 RTCSBAUniversalServices 组，这是在使用拓扑生成器时自动发生的。</span><span class="sxs-lookup"><span data-stu-id="a8001-158">The Survivable Branch Appliance must belong to the RTCSBAUniversalServices group, which happens automatically when you use Topology Builder.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a8001-159">安装并激活 Survivable 分支设备。</span><span class="sxs-lookup"><span data-stu-id="a8001-159">Install, and activate the Survivable Branch Appliance.</span></span></p></td>
<td><p><span data-ttu-id="a8001-160"><strong>在分支站点：</strong></span><span class="sxs-lookup"><span data-stu-id="a8001-160"><strong>At the branch site:</strong></span></span></p>
<ol>
<li><p><span data-ttu-id="a8001-161">将 Survivable 分支设备连接到以太网端口和 PSTN 端口。</span><span class="sxs-lookup"><span data-stu-id="a8001-161">Connect the Survivable Branch Appliance to an Ethernet port and PSTN port.</span></span></p></li>
<li><p><span data-ttu-id="a8001-162">启动 Survivable 分支设备。</span><span class="sxs-lookup"><span data-stu-id="a8001-162">Start the Survivable Branch Appliance.</span></span></p></li>
<li><p><span data-ttu-id="a8001-163">使用为在中心站点上的 Survivable 分支设备创建的域用户帐户将 Survivable 分支设备加入域。</span><span class="sxs-lookup"><span data-stu-id="a8001-163">Join the Survivable Branch Appliance to the domain, using the domain user account created for the Survivable Branch Appliance at the central site.</span></span> <span data-ttu-id="a8001-164">设置 FQDN 和 IP 地址以匹配在计算机帐户中创建的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="a8001-164">Set the FQDN and IP address to match the FQDN created in the computer account.</span></span></p></li>
<li><p><span data-ttu-id="a8001-165">使用 OEM 用户界面配置 Survivable 分支设备。</span><span class="sxs-lookup"><span data-stu-id="a8001-165">Configure the Survivable Branch Appliance using the OEM user interface.</span></span></p></li>
<li><p><span data-ttu-id="a8001-166">测试 PSTN 连接。</span><span class="sxs-lookup"><span data-stu-id="a8001-166">Test PSTN connectivity.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="a8001-167">技术人员用户帐户必须是 RTCUniversalSBATechnicians 的成员。</span><span class="sxs-lookup"><span data-stu-id="a8001-167">The technician user account must be a member of RTCUniversalSBATechnicians.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="survivable-branch-server-details"></a><span data-ttu-id="a8001-168">Survivable Branch Server 详细信息</span><span class="sxs-lookup"><span data-stu-id="a8001-168">Survivable Branch Server Details</span></span>

<span data-ttu-id="a8001-169">在拓扑生成器中，创建分支站点，将 Survivable 分支服务器添加到该站点，然后在要安装该角色的计算机上运行 Lync Server 部署向导。</span><span class="sxs-lookup"><span data-stu-id="a8001-169">In Topology Builder create the branch site, add the Survivable Branch Server to that site, and then run the Lync Server Deployment Wizard on the computer where you want to install the role.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a8001-170">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a8001-170">See Also</span></span>


[<span data-ttu-id="a8001-171">部署 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a8001-171">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

