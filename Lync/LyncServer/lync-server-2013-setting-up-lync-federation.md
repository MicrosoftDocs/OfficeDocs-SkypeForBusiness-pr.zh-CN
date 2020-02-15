---
title: Lync Server 2013：设置 Lync federation
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Lync federation
ms:assetid: 374ddc43-26f9-499d-be68-a5158adfa49c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204800(v=OCS.15)
ms:contentKeyID: 48183822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1972155fa48cd8bc96ee0ec4602bd4b08b2a7b17
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007721"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-lync-federation-in-lync-server-2013"></a><span data-ttu-id="f6bf1-102">在 Lync Server 2013 中设置 Lync 联合</span><span class="sxs-lookup"><span data-stu-id="f6bf1-102">Setting up Lync federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f6bf1-103">_**上次修改的主题：** 2014-03-27_</span><span class="sxs-lookup"><span data-stu-id="f6bf1-103">_**Topic Last Modified:** 2014-03-27_</span></span>

<span data-ttu-id="f6bf1-104">如果您已经部署了一台或多台边缘服务器，那么添加联盟方案功能就非常简单。</span><span class="sxs-lookup"><span data-stu-id="f6bf1-104">If you have already deployed you Edge server or servers, adding the federated scenarios features is straight forward.</span></span> <span data-ttu-id="f6bf1-105">如果尚未设置边缘服务器，则必须先设置边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="f6bf1-105">If you have not set up Edge Servers, you must do that first.</span></span> <span data-ttu-id="f6bf1-106">有关详细信息，请参阅部署文档中的规划文档和在[Lync server 2013 中部署外部用户访问](lync-server-2013-deploying-external-user-access.md)中的 "[在 lync Server 2013 中规划外部用户访问](lync-server-2013-planning-for-external-user-access.md)"。</span><span class="sxs-lookup"><span data-stu-id="f6bf1-106">For details, see: [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in the Planning documentation and [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f6bf1-p102">如果打算设置 XMPP 联盟、Lync 联盟或公共即时消息连接的任意组合，则可以并行部署它们，也可以一次部署一个。如果通过拓扑生成器和 Lync Server 命令行管理程序配置选项，则应在为一个、两个或全部三个联盟类型配置选项后在边缘服务器上运行部署向导，这样您可以减少需要执行的步骤数目。</span><span class="sxs-lookup"><span data-stu-id="f6bf1-p102">If you intend to setup any combination of XMPP federation, Lync Federation, or public instant messaging connectivity, you can deploy them concurrently or one at a time. If you configure the options through the Topology Builder and the Lync Server Management shell, then run the Deployment Wizard at the Edge server after configuring the options for one, two or all three federation types, you can reduce the number of steps required.</span></span>



</div>

<div>

## <a name="setting-up-lync-federation-in-topology-builder-and-the-deployment-wizard"></a><span data-ttu-id="f6bf1-109">在拓扑生成器和部署向导中设置 Lync 联盟</span><span class="sxs-lookup"><span data-stu-id="f6bf1-109">Setting Up Lync Federation in Topology Builder and the Deployment Wizard</span></span>

1.  <span data-ttu-id="f6bf1-p103">在前端服务器上，打开拓扑生成器。展开“边缘池”，然后右键单击您的边缘服务器或边缘服务器池。选择“编辑属性”。</span><span class="sxs-lookup"><span data-stu-id="f6bf1-p103">On a Front End server, open Topology Builder. Expand Edge pools, then right click your Edge server or Edge server pool. Select Edit properties.</span></span>

2.  <span data-ttu-id="f6bf1-p104">在“编辑属性”中的“常规”下，选择“为此边缘池启用联盟(端口 5061)”。单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="f6bf1-p104">In Edit Properties under General, select Enable federation for this Edge pool (Port 5061). Click OK.</span></span>

3.  <span data-ttu-id="f6bf1-p105">单击“操作”，选择“拓扑”，再选择“发布”。当“发布拓扑”中出现提示时，单击“下一步”。完成发布后，单击“完成”。</span><span class="sxs-lookup"><span data-stu-id="f6bf1-p105">Click Action, select Topology, select Publish. When prompted on Publish the topology, click Next. When the Publish is finished, click Finish.</span></span>

4.  <span data-ttu-id="f6bf1-p106">在边缘服务器上，打开 Lync Server 部署向导。单击“安装或更新 Lync Server 系统”，然后单击“安装或删除 Lync Server 组件”。单击“再次运行”。</span><span class="sxs-lookup"><span data-stu-id="f6bf1-p106">On the Edge server, open the Lync Server Deployment wizard. Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components. Click Run Again.</span></span>

5.  <span data-ttu-id="f6bf1-p107">在“设置 Lync Server 组件”中，单击“下一步”。摘要屏幕将显示已执行的操作。部署完成后，单击“查看日志”可查看可用日志文件。单击“完成”以完成部署。</span><span class="sxs-lookup"><span data-stu-id="f6bf1-p107">At Setup Lync Server components, click Next. The summary screen will show actions as they are executed. Once the deployment is done, click View Log to view available log files. Click Finish to complete the deployment.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f6bf1-p108">您可以选择此选项，但只能为联盟对外发布组织中的一个边缘池或边缘服务器。联盟用户（包括公共即时消息 (IM) 用户）的所有访问都将通过相同的边缘池或单台边缘服务器。例如，如果部署中有一个边缘池或单台边缘服务器部署在纽约，另一个部署在伦敦，并对纽约的边缘池或单台边缘服务器启用联盟支持，则联盟用户的信号流量将通过纽约的边缘池或单台边缘服务器。这同样适用于伦敦用户的通信，尽管伦敦内部用户呼叫伦敦联盟用户时将使用伦敦的池或边缘服务器路由 A/V 流量。</span><span class="sxs-lookup"><span data-stu-id="f6bf1-p108">You can select this option, but only one Edge pool or Edge Server in your organization can be published externally for federation. All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server. For example, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server. This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

    
    </div>

</div>

<div>

## <a name="configuring-federation-with-partners"></a><span data-ttu-id="f6bf1-129">对合作伙伴配置联盟</span><span class="sxs-lookup"><span data-stu-id="f6bf1-129">Configuring Federation with Partners</span></span>

1.  <span data-ttu-id="f6bf1-130">若要设置与另一台 Microsoft Lync Server 2013、Lync Server 2010、Office 通信服务器 2007 R2 或 Office Communicator 2007 的成功联合，请选择下表中的联合身份验证类型并定义 DNS SRV 记录、DNS 主机（A 或 AAAA）。IPv6）和配置适用于联合类型的策略：</span><span class="sxs-lookup"><span data-stu-id="f6bf1-130">To setup a successful federation with another Microsoft Lync Server 2013, Lync Server 2010, Office Communications Server 2007 R2, or Office Communicator 2007, select the type of federation from the following table and define DNS SRV records, DNS host (A or AAAA for IPv6) and configure policies applicable to the type of federation:</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="f6bf1-131">联盟类型</span><span class="sxs-lookup"><span data-stu-id="f6bf1-131">Federation type</span></span></th>
    <th><span data-ttu-id="f6bf1-132">DNS 记录</span><span class="sxs-lookup"><span data-stu-id="f6bf1-132">DNS Records</span></span></th>
    <th><span data-ttu-id="f6bf1-133">策略定义</span><span class="sxs-lookup"><span data-stu-id="f6bf1-133">Policy Definition</span></span></th>
    <th><span data-ttu-id="f6bf1-134">备注</span><span class="sxs-lookup"><span data-stu-id="f6bf1-134">Notes</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="f6bf1-135">已发现的伙伴域</span><span class="sxs-lookup"><span data-stu-id="f6bf1-135">Discovered Partner Domain</span></span></p></td>
    <td><p><span data-ttu-id="f6bf1-136">配置 _sipfederationtls _tcp 格式的 SRV 记录。&lt;外部域名&gt;，其中 SRV 记录的端口值为 TCP 5061，并且<strong>提供此服务的主机</strong>定义为 sip。</span><span class="sxs-lookup"><span data-stu-id="f6bf1-136">Configure SRV record of the format _sipfederationtls._tcp.&lt;external domain name&gt;Where the port value for the SRV record is TCP 5061 and the <strong>Host offering this service</strong> is defined as sip.</span></span> <span data-ttu-id="f6bf1-137">&lt;外部域名&gt; –访问边缘服务的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="f6bf1-137">&lt;external domain name&gt; – the FQDN of your Access Edge service.</span></span> <span data-ttu-id="f6bf1-138">有关创建 SRV 记录的详细信息，请参阅<a href="lync-server-2013-configure-dns-for-edge-support.md">CONFIGURE DNS for edge 支持在 Lync Server 2013 中</a></span><span class="sxs-lookup"><span data-stu-id="f6bf1-138">See <a href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</a> for details on creating the SRV record</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="f6bf1-139"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">在 Lync Server 2013 中启用或禁用联盟和公共 IM 连接</a></span><span class="sxs-lookup"><span data-stu-id="f6bf1-139"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="f6bf1-140"><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">在 Lync Server 2013 中启用或禁用联盟伙伴发现</a></span><span class="sxs-lookup"><span data-stu-id="f6bf1-140"><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Enable or disable discovery of federation partners in Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="f6bf1-p110">以前版本将此联盟类型称为<strong>开放增强联盟</strong>。创建 SRV 记录对于此联盟类型是必需的，并且将允许其他合作伙伴发现您的联盟。</span><span class="sxs-lookup"><span data-stu-id="f6bf1-p110">Previous versions referred to this type of federation as <strong>Open Enhanced Federation</strong>. The creation of the SRV record is required for this type of federation and is to allow other partners to discover your federation.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="f6bf1-143">所允许的伙伴域</span><span class="sxs-lookup"><span data-stu-id="f6bf1-143">Allowed Partner Domain</span></span></p></td>
    <td><p><span data-ttu-id="f6bf1-144">配置 _sipfederationtls _tcp 格式的 SRV 记录。&lt;外部域名&gt;，其中 SRV 记录的端口值为 TCP 5061，并且<strong>提供此服务的主机</strong>定义为 sip。</span><span class="sxs-lookup"><span data-stu-id="f6bf1-144">Configure SRV record of the format _sipfederationtls._tcp.&lt;external domain name&gt;Where the port value for the SRV record is TCP 5061 and the <strong>Host offering this service</strong> is defined as sip.</span></span> <span data-ttu-id="f6bf1-145">&lt;外部域名&gt; –访问边缘服务的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="f6bf1-145">&lt;external domain name&gt; – the FQDN of your Access Edge service.</span></span> <span data-ttu-id="f6bf1-146">有关创建 SRV 记录的详细信息，请参阅<a href="lync-server-2013-configure-dns-for-edge-support.md">CONFIGURE DNS for edge 支持在 Lync Server 2013 中</a></span><span class="sxs-lookup"><span data-stu-id="f6bf1-146">See <a href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</a> for details on creating the SRV record</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="f6bf1-147"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">在 Lync Server 2013 中启用或禁用联盟和公共 IM 连接</a></span><span class="sxs-lookup"><span data-stu-id="f6bf1-147"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="f6bf1-148">以前版本的联合称为 "<strong>增强联盟</strong>"。</span><span class="sxs-lookup"><span data-stu-id="f6bf1-148">Previous versions referred to this type of federation as <strong>Enhanced Federation</strong>.</span></span> <span data-ttu-id="f6bf1-149">创建 SRV 记录对于此联盟类型是可选的，并且将允许其他合作伙伴发现您的联盟。</span><span class="sxs-lookup"><span data-stu-id="f6bf1-149">The creation of the SRV record is optional for this type of federation and is to allow other partners to discover your federation.</span></span> <span data-ttu-id="f6bf1-150">当然，这之后将是<strong>开放增强联盟</strong>或者<strong>已发现的伙伴域</strong></span><span class="sxs-lookup"><span data-stu-id="f6bf1-150">Of course, this is then an <strong>Open Enhanced Federation</strong>, or <strong>Discovered Partner Domain</strong></span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="f6bf1-151">允许的伙伴服务器</span><span class="sxs-lookup"><span data-stu-id="f6bf1-151">Allowed Partner Server</span></span></p></td>
    <td><p><span data-ttu-id="f6bf1-152">在策略中将 SIP 域名和合作伙伴边缘服务器 FQDN 配置为联合合作伙伴</span><span class="sxs-lookup"><span data-stu-id="f6bf1-152">Configure the SIP domain name and the partner Edge Server FQDN as a federation partner in Policies</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="f6bf1-153"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">在 Lync Server 2013 中启用或禁用联盟和公共 IM 连接</a></span><span class="sxs-lookup"><span data-stu-id="f6bf1-153"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="f6bf1-154"><a href="lync-server-2013-configure-support-for-allowed-external-domains.md">在 Lync Server 2013 中配置对允许的外部域的支持</a></span><span class="sxs-lookup"><span data-stu-id="f6bf1-154"><a href="lync-server-2013-configure-support-for-allowed-external-domains.md">Configure support for allowed external domains in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="f6bf1-155"><a href="lync-server-2013-configure-support-for-blocked-external-domains.md">在 Lync Server 2013 中配置对阻止的外部域的支持</a></span><span class="sxs-lookup"><span data-stu-id="f6bf1-155"><a href="lync-server-2013-configure-support-for-blocked-external-domains.md">Configure support for blocked external domains in Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="f6bf1-p113">此联盟类型定义为一对一关系并且不允许发现其他联盟伙伴。每个联盟伙伴是显式配置的。在以前版本中，这称为<strong>直接联盟</strong></span><span class="sxs-lookup"><span data-stu-id="f6bf1-p113">This federation type is the definition of a one to one relationship and does not allow for discovery of other federation partners. Each federation partner is configured explicitly. In previous versions, this was known as <strong>Direct Federation</strong></span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="f6bf1-159">宿主提供程序和公共 IM 提供程序</span><span class="sxs-lookup"><span data-stu-id="f6bf1-159">Hosting Provider and Public IM Provider</span></span></p></td>
    <td><p><span data-ttu-id="f6bf1-160">没有为此联盟类型定义特定 DNS 要求</span><span class="sxs-lookup"><span data-stu-id="f6bf1-160">No specific DNS requirements are defined for this type of federation</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="f6bf1-161"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">在 Lync Server 2013 中启用或禁用联盟和公共 IM 连接</a></span><span class="sxs-lookup"><span data-stu-id="f6bf1-161"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="f6bf1-162"><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">在 Lync Server 2013 中创建或编辑公共 SIP 联合提供程序</a></span><span class="sxs-lookup"><span data-stu-id="f6bf1-162"><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Create or edit public SIP federated providers in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="f6bf1-163"><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">创建或编辑托管的 SIP 联合提供商 Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f6bf1-163"><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Create or edit hosted SIP federated providers Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="f6bf1-164">此联盟类型定义您要为用户配置的服务和宿主提供程序。</span><span class="sxs-lookup"><span data-stu-id="f6bf1-164">This federation type defines services and hosting providers that you want to configure for your users.</span></span> <span data-ttu-id="f6bf1-165">典型用法包括配置 Windows Live Messenger、Yahoo!</span><span class="sxs-lookup"><span data-stu-id="f6bf1-165">Typical uses include configuration for public IM providers like Windows Live Messenger, Yahoo!</span></span> <span data-ttu-id="f6bf1-166">和 AOL 以及 Lync Online 和 Office 365 等托管提供程序</span><span class="sxs-lookup"><span data-stu-id="f6bf1-166">and AOL, as well as hosting providers such as Lync Online and Office 365</span></span></p>
    <div>

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="f6bf1-167">从2012年9月1日起，Microsoft Lync 公共 IM 连接用户订阅许可证（"PIC USL"）不再可用于购买新的或更新的协议。</span><span class="sxs-lookup"><span data-stu-id="f6bf1-167">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="f6bf1-168">拥有主动许可证的客户将能够继续与 Yahoo！联合联合</span><span class="sxs-lookup"><span data-stu-id="f6bf1-168">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="f6bf1-169">信使，直到服务关闭日期。</span><span class="sxs-lookup"><span data-stu-id="f6bf1-169">Messenger until the service shut down date.</span></span> <span data-ttu-id="f6bf1-170">AOL 和 Yahoo！的生命周期结束日期为2014年6月</span><span class="sxs-lookup"><span data-stu-id="f6bf1-170">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="f6bf1-171">已宣布。</span><span class="sxs-lookup"><span data-stu-id="f6bf1-171">has been announced.</span></span> <span data-ttu-id="f6bf1-172">有关详细信息，请参阅<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的支持公用即时信使连接</A>。</span><span class="sxs-lookup"><span data-stu-id="f6bf1-172">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="f6bf1-173">PIC USL 是 Lync Server 或 Office 通信服务器与 Yahoo！联合所需的每个用户每月订阅许可证。</span><span class="sxs-lookup"><span data-stu-id="f6bf1-173">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="f6bf1-174">Messenger.</span><span class="sxs-lookup"><span data-stu-id="f6bf1-174">Messenger.</span></span> <span data-ttu-id="f6bf1-175">Microsoft 提供此服务的能力因 Yahoo！中的支持而受到了支持，其下凸的底层协议。</span><span class="sxs-lookup"><span data-stu-id="f6bf1-175">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="f6bf1-176">Lync 是前所未有的强大工具，用于跨组织和世界各地的个人进行连接。</span><span class="sxs-lookup"><span data-stu-id="f6bf1-176">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="f6bf1-177">与 Windows Live Messenger 的联盟不需要除 Lync Standard CAL 之外的其他用户/设备许可证。</span><span class="sxs-lookup"><span data-stu-id="f6bf1-177">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="f6bf1-178">Skype 联合身份验证将添加到此列表中，使 Lync 用户可以使用即时消息和语音访问成百上千人。</span><span class="sxs-lookup"><span data-stu-id="f6bf1-178">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>


    </div></td>
    </tr>
    </tbody>
    </table>


2.  <span data-ttu-id="f6bf1-179">定义和配置任何必需的 DNS 主机（IPv6 的 A 或 AAAA）和 DNS SRV 记录</span><span class="sxs-lookup"><span data-stu-id="f6bf1-179">Define and configure any required DNS host (A or AAAA for IPv6) and DNS SRV records</span></span>

3.  <span data-ttu-id="f6bf1-180">使用 Lync Server 控制面板或使用 Lync Server 命令行管理程序和相应的 cmdlet 定义和配置任何策略。</span><span class="sxs-lookup"><span data-stu-id="f6bf1-180">Define and configure any policies using the Lync Server Control Panel or by using the Lync Server Management Shell and the appropriate cmdlets.</span></span> <span data-ttu-id="f6bf1-181">有关 Lync Server 命令行管理程序 cmdlet 的详细信息，请参阅[Lync server 2013 中的联合身份验证和外部访问 cmdlet](https://docs.microsoft.com/powershell/module/skype/)</span><span class="sxs-lookup"><span data-stu-id="f6bf1-181">For details on the Lync Server Management Shell cmdlets, see [Federation and external access cmdlets in Lync Server 2013](https://docs.microsoft.com/powershell/module/skype/)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f6bf1-182">Lync 会议室系统（LRS）不显示由联合 Lync 合作伙伴中的组织者发送的会议的 "加入" 按钮。</span><span class="sxs-lookup"><span data-stu-id="f6bf1-182">Lync Room System (LRS) does not show join button for meetings sent by organizers in federated Lync partners.</span></span> <span data-ttu-id="f6bf1-183">若要在 LRS 上显示会议加入链接，发送组织必须使用以下 cmdlet 启用 TNEF：</span><span class="sxs-lookup"><span data-stu-id="f6bf1-183">For a meeting join link to appear on LRS, the sending organization must enable TNEF by using the following cmdlet:</span></span><BR><BR><CODE>New-RemoteDomain -DomainName Contoso.com -Name Contoso</CODE><BR><CODE>Set-RemoteDomain -Identity Contoso -TNEFEnabled $true</CODE><BR><span data-ttu-id="f6bf1-184">请注意，这不是 LRS 特定的。</span><span class="sxs-lookup"><span data-stu-id="f6bf1-184">Note that this is not LRS specific.</span></span> <span data-ttu-id="f6bf1-185">在这种情况下，outlook 和 Lync 也不会显示联接链接，因为 MAPI 属性不会传输，但在 Outlook 中，用户可以打开会议邀请并单击会议 URL。</span><span class="sxs-lookup"><span data-stu-id="f6bf1-185">Outlook and Lync would also not show Join links in this case as MAPI properties are not transported, but in the Outlook case, the user can open up the meeting invite and click on the meeting URL.</span></span> <span data-ttu-id="f6bf1-186">如果将 TNEFEnabled 设置为 true，则 Exchange 2013 不会去除 MAPI 属性（包括 OnlineMeetingExternalLink），并且将在提醒上显示 "加入" 按钮。</span><span class="sxs-lookup"><span data-stu-id="f6bf1-186">When TNEFEnabled is set to true Exchange 2013 does not strip MAPI properties including OnlineMeetingExternalLink and the Join button will be shown on the reminder.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f6bf1-187">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f6bf1-187">See Also</span></span>


[<span data-ttu-id="f6bf1-188">在 Lync Server 2013 中规划 SIP、XMPP 联合身份验证和公共即时消息</span><span class="sxs-lookup"><span data-stu-id="f6bf1-188">Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md)  
[<span data-ttu-id="f6bf1-189">管理对 Lync Server 2013 的联盟和外部访问</span><span class="sxs-lookup"><span data-stu-id="f6bf1-189">Managing federation and external access to Lync Server 2013</span></span>](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

