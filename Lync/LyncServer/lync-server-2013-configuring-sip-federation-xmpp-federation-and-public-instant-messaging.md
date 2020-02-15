---
title: 配置 SIP 联盟、XMPP 联盟和公共即时消息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring SIP federation, XMPP federation and public instant messaging
ms:assetid: a6d04f0b-5cb8-4084-a3a2-d501938971f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205134(v=OCS.15)
ms:contentKeyID: 48184998
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d97966d0a5062b133e9802f97ff77934ba29300
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041011"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-sip-federation-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="a18cb-102">在 Lync Server 2013 中配置 SIP 联盟、XMPP 联盟和公共即时消息</span><span class="sxs-lookup"><span data-stu-id="a18cb-102">Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a18cb-103">_**上次修改的主题：** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="a18cb-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="a18cb-104">联盟、公共即时消息连接和可扩展消息传递和状态协议 (XMPP) 定义了一类不同的外部用户 – 联盟用户。</span><span class="sxs-lookup"><span data-stu-id="a18cb-104">Federation, public instant messaging connectivity and Extensible Messaging and Presence Protocol (XMPP) define a different class of external users – Federated users.</span></span> <span data-ttu-id="a18cb-105">联合 Lync Server 部署或 XMPP 部署的用户可以访问有限的一组服务，并通过外部部署进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="a18cb-105">Users of a federated Lync Server deployment or XMPP deployment have access to a limited set of services and are authenticated by the external deployment.</span></span> <span data-ttu-id="a18cb-106">远程用户是 Lync Server 部署的成员，并且具有对部署提供的所有服务的访问权限。</span><span class="sxs-lookup"><span data-stu-id="a18cb-106">Remote users are members of your Lync Server deployment and have access to all services offered by your deployment.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="a18cb-107">AOL 和 Yahoo！的生命周期结束日期为2014年6月</span><span class="sxs-lookup"><span data-stu-id="a18cb-107">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="a18cb-108">已宣布。</span><span class="sxs-lookup"><span data-stu-id="a18cb-108">has been announced.</span></span> <span data-ttu-id="a18cb-109">有关详细信息，请参阅<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的支持公用即时信使连接</A>。</span><span class="sxs-lookup"><span data-stu-id="a18cb-109">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="a18cb-110">公共即时消息连接是一种特殊类型的联盟，允许 Lync Server 客户端使用 Lync 2013 访问已配置的公用即时消息伙伴。</span><span class="sxs-lookup"><span data-stu-id="a18cb-110">Public instant messaging connectivity is a special type of federation that allows a Lync Server client to access configured public Instant Messaging partners using the Lync 2013.</span></span> <span data-ttu-id="a18cb-111">以下是当前公共即时消息连接合作伙伴：</span><span class="sxs-lookup"><span data-stu-id="a18cb-111">The current public instant messaging connectivity partners are:</span></span>

  - <span></span>  
    <span data-ttu-id="a18cb-112">America Online</span><span class="sxs-lookup"><span data-stu-id="a18cb-112">America Online</span></span>

  - <span></span>  
    <span data-ttu-id="a18cb-113">Windows Live</span><span class="sxs-lookup"><span data-stu-id="a18cb-113">Windows Live</span></span>

  - <span></span>  
    <span data-ttu-id="a18cb-114">Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="a18cb-114">Yahoo\!</span></span>

<span data-ttu-id="a18cb-115">利用公共即时消息连接配置，Lync 用户可按以下内容访问公共即时消息连接用户：</span><span class="sxs-lookup"><span data-stu-id="a18cb-115">A public instant messaging connectivity configuration allows Lync users access to public instant messaging connectivity users by:</span></span>

  - <span data-ttu-id="a18cb-116">IM 和状态</span><span class="sxs-lookup"><span data-stu-id="a18cb-116">IM and Presence</span></span>

  - <span data-ttu-id="a18cb-117">Lync 客户端中公共即时消息连接联系人的可见性</span><span class="sxs-lookup"><span data-stu-id="a18cb-117">Visibility of public instant messaging connectivity contacts in Lync client</span></span>

  - <span data-ttu-id="a18cb-118">与联系人的面对面 IM 会话</span><span class="sxs-lookup"><span data-stu-id="a18cb-118">Person to person IM conversations with contacts</span></span>

  - <span data-ttu-id="a18cb-119">与 Windows Live 用户的音频和视频呼叫</span><span class="sxs-lookup"><span data-stu-id="a18cb-119">Audio and video calls with Windows Live users</span></span>

<span data-ttu-id="a18cb-p104">Lync Server 联盟定义 Lync Server 部署与其他 Office Communications Server 2007 R2 或 Lync Server 部署之间的协议。利用 Lync Server 联盟配置，Lync 用户可按以下内容访问联盟用户：</span><span class="sxs-lookup"><span data-stu-id="a18cb-p104">Lync Server federation defines an agreement between your Lync Server deployment and other Office Communications Server 2007 R2 or Lync Server deployments. A Lync Server federated configuration allows Lync users access to federated users by:</span></span>

  - <span data-ttu-id="a18cb-122">IM 和状态</span><span class="sxs-lookup"><span data-stu-id="a18cb-122">IM and Presence</span></span>

  - <span data-ttu-id="a18cb-123">Lync 客户端中联盟联系人的创建</span><span class="sxs-lookup"><span data-stu-id="a18cb-123">Creation of federated contacts in the Lync client</span></span>

<span data-ttu-id="a18cb-p105">XMPP 联盟基于可扩展消息传递和状态协议定义外部部署。利用 XMPP 配置，Lync 用户可按以下内容访问允许的 XMPP 域用户：</span><span class="sxs-lookup"><span data-stu-id="a18cb-p105">XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol. An XMPP configuration allows Lync users access to allowed XMPP domain users by:</span></span>

  - <span data-ttu-id="a18cb-126">IM 和状态 – 仅限于面对面</span><span class="sxs-lookup"><span data-stu-id="a18cb-126">IM and Presence – person to person only</span></span>

  - <span data-ttu-id="a18cb-127">Lync 客户端中 XMPP 联盟联系人的创建</span><span class="sxs-lookup"><span data-stu-id="a18cb-127">Creation of XMPP federated contacts in the Lync client</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="a18cb-128">Microsoft 对 Lync Server 2013 的 XMPP 功能进行了测试，并支持 Microsoft 实现与 Google 谈话的即时消息联盟。</span><span class="sxs-lookup"><span data-stu-id="a18cb-128">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk.</span></span> <span data-ttu-id="a18cb-129">对于任何其他 XMPP 系统，请联系第三方供应商以验证它们是否支持与 Lync Server 2013 联合，以及任何部署或疑难解答建议。</span><span class="sxs-lookup"><span data-stu-id="a18cb-129">For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>



</div>

<div>

## <a name="edge-server-external-federation-public-instant-messaging-connectivity-and-xmpp-users-deployment-process"></a><span data-ttu-id="a18cb-130">边缘服务器外部联盟、公共即时消息连接和 XMPP 用户部署过程</span><span class="sxs-lookup"><span data-stu-id="a18cb-130">Edge Server External Federation, Public Instant Messaging Connectivity and XMPP Users Deployment Process</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a18cb-131">阶段</span><span class="sxs-lookup"><span data-stu-id="a18cb-131">Phase</span></span></th>
<th><span data-ttu-id="a18cb-132">步骤</span><span class="sxs-lookup"><span data-stu-id="a18cb-132">Steps</span></span></th>
<th><span data-ttu-id="a18cb-133">Permissions</span><span class="sxs-lookup"><span data-stu-id="a18cb-133">Permissions</span></span></th>
<th><span data-ttu-id="a18cb-134">文档</span><span class="sxs-lookup"><span data-stu-id="a18cb-134">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a18cb-135">确定要添加到现有边缘部署的选项</span><span class="sxs-lookup"><span data-stu-id="a18cb-135">Determine the options to add to the existing Edge deployment</span></span></p></td>
<td><p><span data-ttu-id="a18cb-136">运行拓扑生成器以编辑边缘服务器设置并创建和发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="a18cb-136">Run Topology Builder to edit Edge Server settings and create and publish the topology.</span></span> <span data-ttu-id="a18cb-137">现有的边缘拓扑会将更改从中央管理存储复制到边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="a18cb-137">Your existing Edge topology will replicate changes from the Central Management store to the Edge Server.</span></span></p></td>
<td><p><span data-ttu-id="a18cb-138">Domain Admins 组和 RTCUniversalServerAdmins 组</span><span class="sxs-lookup"><span data-stu-id="a18cb-138">Domain Admins group and RTCUniversalServerAdmins group</span></span></p>



> [!NOTE]
> <span data-ttu-id="a18cb-139">可以使用属于本地用户组成员的帐户来编辑拓扑，但发布拓扑需要属于 Domain Admins 组和 RTCUniversalServerAdmins 组的成员的帐户。</span><span class="sxs-lookup"><span data-stu-id="a18cb-139">You can edit a topology using an account that is a member of the local users group, but publishing a topology requires an account that is a member of the Domain Admins group and the RTCUniversalServerAdmins group</span></span>

</td>
<td><p><span data-ttu-id="a18cb-140"><a href="lync-server-2013-building-an-edge-and-director-topology.md">在 Lync Server 2013 中构建边缘和控制器拓扑</a></span><span class="sxs-lookup"><span data-stu-id="a18cb-140"><a href="lync-server-2013-building-an-edge-and-director-topology.md">Building an edge and Director topology in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a18cb-141">准备安装</span><span class="sxs-lookup"><span data-stu-id="a18cb-141">Prepare for setup</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="a18cb-142">确保满足系统先决条件。</span><span class="sxs-lookup"><span data-stu-id="a18cb-142">Ensure that system prerequisites are met.</span></span></p></li>
<li><p><span data-ttu-id="a18cb-143">配置内部和外部 DNS 记录以支持公共即时消息连接、Lync 联盟和 XMPP 联盟</span><span class="sxs-lookup"><span data-stu-id="a18cb-143">Configure internal and external DNS records, to support public instant messaging connectivity, Lync Federation and XMPP Federation</span></span></p></li>
<li><p><span data-ttu-id="a18cb-144">在防火墙上配置端口和协议以支持要部署的联盟的类型</span><span class="sxs-lookup"><span data-stu-id="a18cb-144">Configure ports and protocols at the firewall to support the types of federation that you are deploying</span></span></p></li>
<li><p><span data-ttu-id="a18cb-p108">获取和安装公共证书。获取证书所需的时间取决于颁发证书的证书颁发机构 (CA)。此步骤在部署的这一时间点是可选的。如果在此时间点不执行此步骤，则必须在边缘服务器配置过程中执行此步骤。在获取证书前，边缘服务器服务无法启动</span><span class="sxs-lookup"><span data-stu-id="a18cb-p108">Obtain and install public certificates. The time required to obtain certificates depends on which certification authority (CA) issues the certificate. This step is optional at this point in the deployment. If you do not perform this step at this point, you must do it during Edge Server configuration. The Edge Server service cannot be started until certificates are obtained</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="a18cb-150">根据组织的需要，这些角色通常会被分到各种工作组中时</span><span class="sxs-lookup"><span data-stu-id="a18cb-150">As appropriate to your organization, as these roles are typically split amongst numerous work groups</span></span></p></td>
<td><p><span data-ttu-id="a18cb-151"><a href="lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md">在 Lync Server 2013 中规划 SIP、XMPP 联合身份验证和公共即时消息</a></span><span class="sxs-lookup"><span data-stu-id="a18cb-151"><a href="lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md">Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a18cb-152">为联盟方案设置边缘服务器</span><span class="sxs-lookup"><span data-stu-id="a18cb-152">Set up Edge Servers for Federation Scenarios</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="a18cb-153">将导出的拓扑配置文件传输到每台边缘服务器或允许复制完成</span><span class="sxs-lookup"><span data-stu-id="a18cb-153">Transport the exported topology configuration file to each Edge Server or allow replication to complete</span></span></p></li>
<li><p><span data-ttu-id="a18cb-154">重新运行部署向导以安装联盟的支持组件</span><span class="sxs-lookup"><span data-stu-id="a18cb-154">Re-Run the Deployment Wizard to install supporting components for Federation</span></span></p></li>
<li><p><span data-ttu-id="a18cb-155">配置边缘服务器</span><span class="sxs-lookup"><span data-stu-id="a18cb-155">Configure the Edge Servers</span></span></p></li>
<li><p><span data-ttu-id="a18cb-156">为每台边缘服务器请求和安装证书</span><span class="sxs-lookup"><span data-stu-id="a18cb-156">Request and install certificates for each Edge Server</span></span></p></li>
<li><p><span data-ttu-id="a18cb-157">重新启动边缘服务器服务</span><span class="sxs-lookup"><span data-stu-id="a18cb-157">Restart the Edge Server services</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="a18cb-158">Administrators 组</span><span class="sxs-lookup"><span data-stu-id="a18cb-158">Administrators group</span></span></p></td>
<td><p><span data-ttu-id="a18cb-159"><a href="lync-server-2013-setting-up-lync-federation.md">在 Lync Server 2013 中设置 Lync 联合</a></span><span class="sxs-lookup"><span data-stu-id="a18cb-159"><a href="lync-server-2013-setting-up-lync-federation.md">Setting up Lync federation in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="a18cb-160"><a href="lync-server-2013-setting-up-public-instant-messaging-connectivity.md">在 Lync Server 2013 中设置公共即时消息连接</a></span><span class="sxs-lookup"><span data-stu-id="a18cb-160"><a href="lync-server-2013-setting-up-public-instant-messaging-connectivity.md">Setting up public instant messaging connectivity in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="a18cb-161"><a href="lync-server-2013-setting-up-xmpp-federation.md">在 Lync Server 2013 中设置 XMPP 联盟</a></span><span class="sxs-lookup"><span data-stu-id="a18cb-161"><a href="lync-server-2013-setting-up-xmpp-federation.md">Setting up XMPP federation in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a18cb-162">配置对外部用户访问的支持。</span><span class="sxs-lookup"><span data-stu-id="a18cb-162">Configure support for external user access.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="a18cb-163">使用 Lync Server 控制面板外部用户访问</span><span class="sxs-lookup"><span data-stu-id="a18cb-163">Use the Lync Server Control Panel External User Access</span></span></p></li>
<li><p><span data-ttu-id="a18cb-164">配置外部访问策略以实现与联盟用户或公共用户的通信</span><span class="sxs-lookup"><span data-stu-id="a18cb-164">Configure External Access Policy to enable Communications with federated users or public users</span></span></p></li>
<li><p><span data-ttu-id="a18cb-165">配置 SIP 联盟域以允许或阻止域</span><span class="sxs-lookup"><span data-stu-id="a18cb-165">Configure SIP Federated Domains to Allow or Block domains</span></span></p></li>
<li><p><span data-ttu-id="a18cb-166">为公共即时消息连接提供程序启用 SIP 联盟提供程序</span><span class="sxs-lookup"><span data-stu-id="a18cb-166">Enable SIP Federated Providers for public instant messaging connectivity providers</span></span></p></li>
<li><p><span data-ttu-id="a18cb-167">为每个 XMPP 域配置 XMPP 联盟伙伴</span><span class="sxs-lookup"><span data-stu-id="a18cb-167">Configure XMPP Federated Partners per XMPP domain</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="a18cb-168">分配给 CSAdministrator 角色的 RTCUniversalServerAdmins 组或用户帐户</span><span class="sxs-lookup"><span data-stu-id="a18cb-168">RTCUniversalServerAdmins group or user account that is assigned to the CSAdministrator role</span></span></p></td>
<td><p><span data-ttu-id="a18cb-169"><a href="lync-server-2013-configuring-support-for-external-user-access.md">在 Lync Server 2013 中配置对外部用户访问的支持</a></span><span class="sxs-lookup"><span data-stu-id="a18cb-169"><a href="lync-server-2013-configuring-support-for-external-user-access.md">Configuring support for external user access in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="a18cb-170"><a href="lync-server-2013-configure-media-encryption-for-public-providers.md">在 Lync Server 2013 中为公用提供程序配置媒体加密</a></span><span class="sxs-lookup"><span data-stu-id="a18cb-170"><a href="lync-server-2013-configure-media-encryption-for-public-providers.md">Configure media encryption for public providers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a18cb-171">验证边缘服务器配置</span><span class="sxs-lookup"><span data-stu-id="a18cb-171">Verify your Edge Server configuration</span></span></p></td>
<td><p><span data-ttu-id="a18cb-172">验证服务器连接和对内部服务器中的配置数据的复制</span><span class="sxs-lookup"><span data-stu-id="a18cb-172">Verify server connectivity and replication of configuration data from internal servers</span></span></p></td>
<td><p><span data-ttu-id="a18cb-173">对于复制验证，为分配给 CSAdministrator 角色的 RTCUniversalServerAdmins 组或用户帐户。对于用户连接验证，则为每种类型的联盟用户的用户</span><span class="sxs-lookup"><span data-stu-id="a18cb-173">For verification of replication, RTCUniversalServerAdmins group or user account that is assigned to the CSAdministrator roleFor verification of user connectivity, a user for each type of Federated user</span></span></p></td>
<td><p><span data-ttu-id="a18cb-174"><a href="lync-server-2013-verifying-your-edge-deployment.md">在 Lync Server 2013 中验证边缘部署</a></span><span class="sxs-lookup"><span data-stu-id="a18cb-174"><a href="lync-server-2013-verifying-your-edge-deployment.md">Verifying your edge deployment in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="a18cb-175"><a href="lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md">Lync Server 2013 中的示例 XMPP 配置–与 Google 对话的 XMPP 联盟</a></span><span class="sxs-lookup"><span data-stu-id="a18cb-175"><a href="lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

