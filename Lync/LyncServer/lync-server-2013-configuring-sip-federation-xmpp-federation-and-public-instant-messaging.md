---
title: 配置 SIP 联盟、XMPP 联盟和公共即时消息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring SIP federation, XMPP federation and public instant messaging
ms:assetid: a6d04f0b-5cb8-4084-a3a2-d501938971f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205134(v=OCS.15)
ms:contentKeyID: 48184998
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f82e154347c0a77dd4367678fefd518b1abf2fc7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837180"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-sip-federation-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="893bd-102">在 Lync Server 2013 中配置 SIP 联盟、XMPP 联盟和公共即时消息</span><span class="sxs-lookup"><span data-stu-id="893bd-102">Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="893bd-103">_**主题上次修改时间:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="893bd-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="893bd-104">联盟、公共即时消息连接和可扩展消息和状态协议 (XMPP) 定义不同的外部用户类-联合用户。</span><span class="sxs-lookup"><span data-stu-id="893bd-104">Federation, public instant messaging connectivity and Extensible Messaging and Presence Protocol (XMPP) define a different class of external users – Federated users.</span></span> <span data-ttu-id="893bd-105">联合 Lync Server 部署或 XMPP 部署的用户有权访问有限的一组服务, 并通过外部部署进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="893bd-105">Users of a federated Lync Server deployment or XMPP deployment have access to a limited set of services and are authenticated by the external deployment.</span></span> <span data-ttu-id="893bd-106">远程用户是 Lync Server 部署的成员, 并且有权访问你的部署提供的所有服务。</span><span class="sxs-lookup"><span data-stu-id="893bd-106">Remote users are members of your Lync Server deployment and have access to all services offered by your deployment.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="893bd-107">AOL 和 Yahoo! 的有效期结束日期为2014年6月</span><span class="sxs-lookup"><span data-stu-id="893bd-107">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="893bd-108">已宣布。</span><span class="sxs-lookup"><span data-stu-id="893bd-108">has been announced.</span></span> <span data-ttu-id="893bd-109">有关详细信息, 请参阅<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公共即时消息连接支持</A>。</span><span class="sxs-lookup"><span data-stu-id="893bd-109">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="893bd-110">公共即时消息连接是一种特殊类型的联盟, 允许 Lync Server 客户端使用 Lync 2013 访问配置的公共即时消息合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="893bd-110">Public instant messaging connectivity is a special type of federation that allows a Lync Server client to access configured public Instant Messaging partners using the Lync 2013.</span></span> <span data-ttu-id="893bd-111">当前公共即时消息连接合作伙伴包括:</span><span class="sxs-lookup"><span data-stu-id="893bd-111">The current public instant messaging connectivity partners are:</span></span>

  - <span></span>  
    <span data-ttu-id="893bd-112">美洲在线</span><span class="sxs-lookup"><span data-stu-id="893bd-112">America Online</span></span>

  - <span></span>  
    <span data-ttu-id="893bd-113">Windows Live</span><span class="sxs-lookup"><span data-stu-id="893bd-113">Windows Live</span></span>

  - <span></span>  
    <span data-ttu-id="893bd-114">Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="893bd-114">Yahoo\!</span></span>

<span data-ttu-id="893bd-115">公共即时消息连接配置允许 Lync 用户通过以下方式访问公共即时消息连接用户:</span><span class="sxs-lookup"><span data-stu-id="893bd-115">A public instant messaging connectivity configuration allows Lync users access to public instant messaging connectivity users by:</span></span>

  - <span data-ttu-id="893bd-116">IM 和状态</span><span class="sxs-lookup"><span data-stu-id="893bd-116">IM and Presence</span></span>

  - <span data-ttu-id="893bd-117">Lync 客户端中的公共即时消息连接联系人的可见性</span><span class="sxs-lookup"><span data-stu-id="893bd-117">Visibility of public instant messaging connectivity contacts in Lync client</span></span>

  - <span data-ttu-id="893bd-118">某人与联系人进行即时消息对话</span><span class="sxs-lookup"><span data-stu-id="893bd-118">Person to person IM conversations with contacts</span></span>

  - <span data-ttu-id="893bd-119">与 Windows Live 用户进行音频和视频通话</span><span class="sxs-lookup"><span data-stu-id="893bd-119">Audio and video calls with Windows Live users</span></span>

<span data-ttu-id="893bd-120">Lync 服务器联合在 Lync Server 部署和其他 Office 通信服务器 2007 R2 或 Lync Server 部署之间定义协议。</span><span class="sxs-lookup"><span data-stu-id="893bd-120">Lync Server federation defines an agreement between your Lync Server deployment and other Office Communications Server 2007 R2 or Lync Server deployments.</span></span> <span data-ttu-id="893bd-121">Lync 服务器联合配置允许 Lync 用户通过以下方式访问联盟用户:</span><span class="sxs-lookup"><span data-stu-id="893bd-121">A Lync Server federated configuration allows Lync users access to federated users by:</span></span>

  - <span data-ttu-id="893bd-122">IM 和状态</span><span class="sxs-lookup"><span data-stu-id="893bd-122">IM and Presence</span></span>

  - <span data-ttu-id="893bd-123">在 Lync 客户端中创建联盟联系人</span><span class="sxs-lookup"><span data-stu-id="893bd-123">Creation of federated contacts in the Lync client</span></span>

<span data-ttu-id="893bd-124">XMPP 联合身份验证基于可扩展消息和状态协议定义外部部署。</span><span class="sxs-lookup"><span data-stu-id="893bd-124">XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol.</span></span> <span data-ttu-id="893bd-125">XMPP 配置允许 Lync 用户通过以下方式访问允许的 XMPP 域用户:</span><span class="sxs-lookup"><span data-stu-id="893bd-125">An XMPP configuration allows Lync users access to allowed XMPP domain users by:</span></span>

  - <span data-ttu-id="893bd-126">IM 和状态-仅限人员</span><span class="sxs-lookup"><span data-stu-id="893bd-126">IM and Presence – person to person only</span></span>

  - <span data-ttu-id="893bd-127">在 Lync 客户端中创建 XMPP 联盟联系人</span><span class="sxs-lookup"><span data-stu-id="893bd-127">Creation of XMPP federated contacts in the Lync client</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="893bd-p106">Microsoft 已测试 Lync Server 2013 的 XMPP 功能，并且支持该功能与 Google Talk 进行即时消息传递联盟。对于任何其他 XMPP 系统，请与第三方供应商联系，以确认它们是否支持与 Lync Server 2013 联盟以及获取任何部署或疑难解答建议。</span><span class="sxs-lookup"><span data-stu-id="893bd-p106">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk. For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>



</div>

<div>

## <a name="edge-server-external-federation-public-instant-messaging-connectivity-and-xmpp-users-deployment-process"></a><span data-ttu-id="893bd-130">边缘服务器外部联合身份验证、公共即时消息连接和 XMPP 用户部署过程</span><span class="sxs-lookup"><span data-stu-id="893bd-130">Edge Server External Federation, Public Instant Messaging Connectivity and XMPP Users Deployment Process</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="893bd-131">阶段</span><span class="sxs-lookup"><span data-stu-id="893bd-131">Phase</span></span></th>
<th><span data-ttu-id="893bd-132">步骤</span><span class="sxs-lookup"><span data-stu-id="893bd-132">Steps</span></span></th>
<th><span data-ttu-id="893bd-133">权限</span><span class="sxs-lookup"><span data-stu-id="893bd-133">Permissions</span></span></th>
<th><span data-ttu-id="893bd-134">文档</span><span class="sxs-lookup"><span data-stu-id="893bd-134">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="893bd-135">确定要添加到现有边缘部署的选项</span><span class="sxs-lookup"><span data-stu-id="893bd-135">Determine the options to add to the existing Edge deployment</span></span></p></td>
<td><p><span data-ttu-id="893bd-136">运行拓扑生成器以编辑边缘服务器设置并创建和发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="893bd-136">Run Topology Builder to edit Edge Server settings and create and publish the topology.</span></span> <span data-ttu-id="893bd-137">现有的边缘拓扑会将中央管理存储中的更改复制到边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="893bd-137">Your existing Edge topology will replicate changes from the Central Management store to the Edge Server.</span></span></p></td>
<td><p><span data-ttu-id="893bd-138">域管理员组和 RTCUniversalServerAdmins 组</span><span class="sxs-lookup"><span data-stu-id="893bd-138">Domain Admins group and RTCUniversalServerAdmins group</span></span></p>



> [!NOTE]
> <span data-ttu-id="893bd-139">你可以使用本地 users 组的成员帐户编辑拓扑, 但发布拓扑需要一个帐户, 该帐户是域管理员组和 RTCUniversalServerAdmins 组的成员</span><span class="sxs-lookup"><span data-stu-id="893bd-139">You can edit a topology using an account that is a member of the local users group, but publishing a topology requires an account that is a member of the Domain Admins group and the RTCUniversalServerAdmins group</span></span>

</td>
<td><p><span data-ttu-id="893bd-140"><a href="lync-server-2013-building-an-edge-and-director-topology.md">在 Lync Server 2013 中构建边缘和控制器拓扑</a></span><span class="sxs-lookup"><span data-stu-id="893bd-140"><a href="lync-server-2013-building-an-edge-and-director-topology.md">Building an edge and Director topology in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="893bd-141">准备安装</span><span class="sxs-lookup"><span data-stu-id="893bd-141">Prepare for setup</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="893bd-142">确保满足系统先决条件。</span><span class="sxs-lookup"><span data-stu-id="893bd-142">Ensure that system prerequisites are met.</span></span></p></li>
<li><p><span data-ttu-id="893bd-143">配置内部和外部 DNS 记录, 以支持公共即时消息连接、Lync 联合身份验证和 XMPP 联合身份验证</span><span class="sxs-lookup"><span data-stu-id="893bd-143">Configure internal and external DNS records, to support public instant messaging connectivity, Lync Federation and XMPP Federation</span></span></p></li>
<li><p><span data-ttu-id="893bd-144">在防火墙上配置端口和协议以支持要部署的联合身份验证类型</span><span class="sxs-lookup"><span data-stu-id="893bd-144">Configure ports and protocols at the firewall to support the types of federation that you are deploying</span></span></p></li>
<li><p><span data-ttu-id="893bd-145">获取并安装公共证书。</span><span class="sxs-lookup"><span data-stu-id="893bd-145">Obtain and install public certificates.</span></span> <span data-ttu-id="893bd-146">获取证书所需的时间取决于证书颁发机构 (CA) 颁发的证书。</span><span class="sxs-lookup"><span data-stu-id="893bd-146">The time required to obtain certificates depends on which certification authority (CA) issues the certificate.</span></span> <span data-ttu-id="893bd-147">此步骤在部署中的这一点是可选的。</span><span class="sxs-lookup"><span data-stu-id="893bd-147">This step is optional at this point in the deployment.</span></span> <span data-ttu-id="893bd-148">如果此时不执行此步骤, 则必须在边缘服务器配置期间执行此操作。</span><span class="sxs-lookup"><span data-stu-id="893bd-148">If you do not perform this step at this point, you must do it during Edge Server configuration.</span></span> <span data-ttu-id="893bd-149">在获取证书之前无法启动 Edge 服务器服务</span><span class="sxs-lookup"><span data-stu-id="893bd-149">The Edge Server service cannot be started until certificates are obtained</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="893bd-150">根据你的组织的需要, 因为这些角色通常会拆分到多个工作组中</span><span class="sxs-lookup"><span data-stu-id="893bd-150">As appropriate to your organization, as these roles are typically split amongst numerous work groups</span></span></p></td>
<td><p><span data-ttu-id="893bd-151"><a href="lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md">在 Lync Server 2013 中规划 SIP、XMPP 联盟和公共即时消息</a></span><span class="sxs-lookup"><span data-stu-id="893bd-151"><a href="lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md">Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="893bd-152">为联盟方案设置边缘服务器</span><span class="sxs-lookup"><span data-stu-id="893bd-152">Set up Edge Servers for Federation Scenarios</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="893bd-153">将导出的拓扑配置文件传输到每台边缘服务器或允许复制完成</span><span class="sxs-lookup"><span data-stu-id="893bd-153">Transport the exported topology configuration file to each Edge Server or allow replication to complete</span></span></p></li>
<li><p><span data-ttu-id="893bd-154">重新运行部署向导以安装联盟的支持组件</span><span class="sxs-lookup"><span data-stu-id="893bd-154">Re-Run the Deployment Wizard to install supporting components for Federation</span></span></p></li>
<li><p><span data-ttu-id="893bd-155">配置边缘服务器</span><span class="sxs-lookup"><span data-stu-id="893bd-155">Configure the Edge Servers</span></span></p></li>
<li><p><span data-ttu-id="893bd-156">为每台边缘服务器请求和安装证书</span><span class="sxs-lookup"><span data-stu-id="893bd-156">Request and install certificates for each Edge Server</span></span></p></li>
<li><p><span data-ttu-id="893bd-157">重新启动 Edge 服务器服务</span><span class="sxs-lookup"><span data-stu-id="893bd-157">Restart the Edge Server services</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="893bd-158">管理员组</span><span class="sxs-lookup"><span data-stu-id="893bd-158">Administrators group</span></span></p></td>
<td><p><span data-ttu-id="893bd-159"><a href="lync-server-2013-setting-up-lync-federation.md">在 Lync Server 2013 中设置 Lync 联盟</a></span><span class="sxs-lookup"><span data-stu-id="893bd-159"><a href="lync-server-2013-setting-up-lync-federation.md">Setting up Lync federation in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="893bd-160"><a href="lync-server-2013-setting-up-public-instant-messaging-connectivity.md">在 Lync Server 2013 中设置公共即时消息连接</a></span><span class="sxs-lookup"><span data-stu-id="893bd-160"><a href="lync-server-2013-setting-up-public-instant-messaging-connectivity.md">Setting up public instant messaging connectivity in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="893bd-161"><a href="lync-server-2013-setting-up-xmpp-federation.md">在 Lync Server 2013 中设置 XMPP 联盟</a></span><span class="sxs-lookup"><span data-stu-id="893bd-161"><a href="lync-server-2013-setting-up-xmpp-federation.md">Setting up XMPP federation in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="893bd-162">配置对外部用户访问的支持。</span><span class="sxs-lookup"><span data-stu-id="893bd-162">Configure support for external user access.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="893bd-163">使用 Lync Server "控制面板" 外部用户访问</span><span class="sxs-lookup"><span data-stu-id="893bd-163">Use the Lync Server Control Panel External User Access</span></span></p></li>
<li><p><span data-ttu-id="893bd-164">配置外部访问策略以启用与联盟用户或公共用户的通信</span><span class="sxs-lookup"><span data-stu-id="893bd-164">Configure External Access Policy to enable Communications with federated users or public users</span></span></p></li>
<li><p><span data-ttu-id="893bd-165">将 SIP 联盟域配置为允许或阻止域</span><span class="sxs-lookup"><span data-stu-id="893bd-165">Configure SIP Federated Domains to Allow or Block domains</span></span></p></li>
<li><p><span data-ttu-id="893bd-166">为公共即时消息连接提供程序启用 SIP 联合提供程序</span><span class="sxs-lookup"><span data-stu-id="893bd-166">Enable SIP Federated Providers for public instant messaging connectivity providers</span></span></p></li>
<li><p><span data-ttu-id="893bd-167">配置每个 XMPP 域的 XMPP 联盟合作伙伴</span><span class="sxs-lookup"><span data-stu-id="893bd-167">Configure XMPP Federated Partners per XMPP domain</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="893bd-168">分配给 CSAdministrator 角色的 RTCUniversalServerAdmins 组或用户帐户</span><span class="sxs-lookup"><span data-stu-id="893bd-168">RTCUniversalServerAdmins group or user account that is assigned to the CSAdministrator role</span></span></p></td>
<td><p><span data-ttu-id="893bd-169"><a href="lync-server-2013-configuring-support-for-external-user-access.md">在 Lync Server 2013 中配置对外部用户访问的支持</a></span><span class="sxs-lookup"><span data-stu-id="893bd-169"><a href="lync-server-2013-configuring-support-for-external-user-access.md">Configuring support for external user access in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="893bd-170"><a href="lync-server-2013-configure-media-encryption-for-public-providers.md">在 Lync Server 2013 中配置公共提供商的媒体加密</a></span><span class="sxs-lookup"><span data-stu-id="893bd-170"><a href="lync-server-2013-configure-media-encryption-for-public-providers.md">Configure media encryption for public providers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="893bd-171">验证 Edge 服务器配置</span><span class="sxs-lookup"><span data-stu-id="893bd-171">Verify your Edge Server configuration</span></span></p></td>
<td><p><span data-ttu-id="893bd-172">验证服务器连接和来自内部服务器的配置数据的复制</span><span class="sxs-lookup"><span data-stu-id="893bd-172">Verify server connectivity and replication of configuration data from internal servers</span></span></p></td>
<td><p><span data-ttu-id="893bd-173">对于复制的验证, RTCUniversalServerAdmins 组或分配给 CSAdministrator roleFor 验证用户连接的用户帐户, 每种类型的联合用户的用户</span><span class="sxs-lookup"><span data-stu-id="893bd-173">For verification of replication, RTCUniversalServerAdmins group or user account that is assigned to the CSAdministrator roleFor verification of user connectivity, a user for each type of Federated user</span></span></p></td>
<td><p><span data-ttu-id="893bd-174"><a href="lync-server-2013-verifying-your-edge-deployment.md">在 Lync Server 2013 中验证边缘部署</a></span><span class="sxs-lookup"><span data-stu-id="893bd-174"><a href="lync-server-2013-verifying-your-edge-deployment.md">Verifying your edge deployment in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="893bd-175"><a href="lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md">Lync Server 2013 中的示例 XMPP 配置 –  与 Google Talk 的 XMPP 联盟</a></span><span class="sxs-lookup"><span data-stu-id="893bd-175"><a href="lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

