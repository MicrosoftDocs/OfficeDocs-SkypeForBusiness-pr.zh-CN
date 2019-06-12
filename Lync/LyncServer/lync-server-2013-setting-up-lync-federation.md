---
title: Lync Server 2013：设置 Lync 联盟
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up Lync federation
ms:assetid: 374ddc43-26f9-499d-be68-a5158adfa49c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204800(v=OCS.15)
ms:contentKeyID: 48183822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe6dc0a2aeb39c86db54d21a2c4be5ff6c5be599
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845893"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-lync-federation-in-lync-server-2013"></a><span data-ttu-id="7a804-102">在 Lync Server 2013 中设置 Lync 联盟</span><span class="sxs-lookup"><span data-stu-id="7a804-102">Setting up Lync federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7a804-103">_**主题上次修改时间:** 2014-03-27_</span><span class="sxs-lookup"><span data-stu-id="7a804-103">_**Topic Last Modified:** 2014-03-27_</span></span>

<span data-ttu-id="7a804-104">如果你已部署了 Edge 服务器或服务器, 则添加联合方案功能是直接的。</span><span class="sxs-lookup"><span data-stu-id="7a804-104">If you have already deployed you Edge server or servers, adding the federated scenarios features is straight forward.</span></span> <span data-ttu-id="7a804-105">如果尚未设置边缘服务器, 则必须首先执行此操作。</span><span class="sxs-lookup"><span data-stu-id="7a804-105">If you have not set up Edge Servers, you must do that first.</span></span> <span data-ttu-id="7a804-106">有关详细信息, 请参阅: 在[Lync server 2013 中规划外部用户访问](lync-server-2013-planning-for-external-user-access.md)在部署文档中的 "lync server 2013" 中的 "规划文档" 和 "[部署外部用户访问](lync-server-2013-deploying-external-user-access.md)"。</span><span class="sxs-lookup"><span data-stu-id="7a804-106">For details, see: [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in the Planning documentation and [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7a804-107">如果想要设置 XMPP 联盟、Lync 联合身份验证或公共即时消息连接的任意组合, 可以同时部署它们或一次一个。</span><span class="sxs-lookup"><span data-stu-id="7a804-107">If you intend to setup any combination of XMPP federation, Lync Federation, or public instant messaging connectivity, you can deploy them concurrently or one at a time.</span></span> <span data-ttu-id="7a804-108">如果通过拓扑生成器和 Lync Server Management shell 配置选项, 则在配置了一种、两种或三种联合身份的选项后, 在 Edge 服务器上运行部署向导, 可以减少所需的步骤数。</span><span class="sxs-lookup"><span data-stu-id="7a804-108">If you configure the options through the Topology Builder and the Lync Server Management shell, then run the Deployment Wizard at the Edge server after configuring the options for one, two or all three federation types, you can reduce the number of steps required.</span></span>



</div>

<div>

## <a name="setting-up-lync-federation-in-topology-builder-and-the-deployment-wizard"></a><span data-ttu-id="7a804-109">在拓扑生成器和部署向导中设置 Lync Federation</span><span class="sxs-lookup"><span data-stu-id="7a804-109">Setting Up Lync Federation in Topology Builder and the Deployment Wizard</span></span>

1.  <span data-ttu-id="7a804-110">在前端服务器上, 打开拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="7a804-110">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="7a804-111">展开 "边缘池", 然后右键单击 "边缘服务器" 或 "边缘服务器" 池。</span><span class="sxs-lookup"><span data-stu-id="7a804-111">Expand Edge pools, then right click your Edge server or Edge server pool.</span></span> <span data-ttu-id="7a804-112">选择 "编辑属性"。</span><span class="sxs-lookup"><span data-stu-id="7a804-112">Select Edit properties.</span></span>

2.  <span data-ttu-id="7a804-113">在 "常规" 下的 "编辑属性" 下, 选择 "为此边缘池启用联盟 (端口 5061)"。</span><span class="sxs-lookup"><span data-stu-id="7a804-113">In Edit Properties under General, select Enable federation for this Edge pool (Port 5061).</span></span> <span data-ttu-id="7a804-114">单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="7a804-114">Click OK.</span></span>

3.  <span data-ttu-id="7a804-115">单击 "操作", 选择 "拓扑", 选择 "发布"。</span><span class="sxs-lookup"><span data-stu-id="7a804-115">Click Action, select Topology, select Publish.</span></span> <span data-ttu-id="7a804-116">当系统提示发布拓扑时, 单击 "下一步"。</span><span class="sxs-lookup"><span data-stu-id="7a804-116">When prompted on Publish the topology, click Next.</span></span> <span data-ttu-id="7a804-117">发布完成后, 单击 "完成"。</span><span class="sxs-lookup"><span data-stu-id="7a804-117">When the Publish is finished, click Finish.</span></span>

4.  <span data-ttu-id="7a804-118">在边缘服务器上, 打开 "Lync Server 部署向导"。</span><span class="sxs-lookup"><span data-stu-id="7a804-118">On the Edge server, open the Lync Server Deployment wizard.</span></span> <span data-ttu-id="7a804-119">单击 "安装或更新 Lync 服务器系统", 然后单击 "设置" 或 "删除 Lync Server 组件"。</span><span class="sxs-lookup"><span data-stu-id="7a804-119">Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components.</span></span> <span data-ttu-id="7a804-120">再次单击 "运行"。</span><span class="sxs-lookup"><span data-stu-id="7a804-120">Click Run Again.</span></span>

5.  <span data-ttu-id="7a804-121">在 "安装 Lync 服务器组件" 中, 单击 "下一步"。</span><span class="sxs-lookup"><span data-stu-id="7a804-121">At Setup Lync Server components, click Next.</span></span> <span data-ttu-id="7a804-122">"摘要" 屏幕将显示执行时的操作。</span><span class="sxs-lookup"><span data-stu-id="7a804-122">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="7a804-123">部署完成后, 单击 "查看日志" 以查看可用的日志文件。</span><span class="sxs-lookup"><span data-stu-id="7a804-123">Once the deployment is done, click View Log to view available log files.</span></span> <span data-ttu-id="7a804-124">单击 "完成" 以完成部署。</span><span class="sxs-lookup"><span data-stu-id="7a804-124">Click Finish to complete the deployment.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="7a804-125">你可以选择此选项, 但你的组织中只能为联盟发布一个 Edge 池或边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="7a804-125">You can select this option, but only one Edge pool or Edge Server in your organization can be published externally for federation.</span></span> <span data-ttu-id="7a804-126">联盟用户 (包括公共即时消息 (IM) 用户) 的所有访问权限, 请访问同一 Edge 池或单个边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="7a804-126">All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server.</span></span> <span data-ttu-id="7a804-127">例如, 如果你的部署包括在纽约部署的 Edge 池或单层服务器, 并且在伦敦部署了一个, 并且你在纽约的 Edge 池或单边服务器上启用了联合身份验证支持, 则联盟用户的信号流量将通过纽约边缘池或单边服务器。</span><span class="sxs-lookup"><span data-stu-id="7a804-127">For example, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server.</span></span> <span data-ttu-id="7a804-128">这同样适用于 London 用户的通信，尽管 London 内部用户呼叫 London 联盟用户时将使用 London 池或边缘服务器路由 A/V 流量。</span><span class="sxs-lookup"><span data-stu-id="7a804-128">This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

    
    </div>

</div>

<div>

## <a name="configuring-federation-with-partners"></a><span data-ttu-id="7a804-129">与合作伙伴配置联盟</span><span class="sxs-lookup"><span data-stu-id="7a804-129">Configuring Federation with Partners</span></span>

1.  <span data-ttu-id="7a804-130">若要与另一个 Microsoft Lync Server 2013、Lync Server 2010、Office 通信服务器 2007 R2 或 Office Communicator 2007 设置成功的联盟, 请从下表中选择联盟的类型并定义 DNS SRV 记录、DNS 主机 (A 或 AAAA)IPv6) 和配置适用于联盟类型的策略:</span><span class="sxs-lookup"><span data-stu-id="7a804-130">To setup a successful federation with another Microsoft Lync Server 2013, Lync Server 2010, Office Communications Server 2007 R2, or Office Communicator 2007, select the type of federation from the following table and define DNS SRV records, DNS host (A or AAAA for IPv6) and configure policies applicable to the type of federation:</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="7a804-131">联合身份验证类型</span><span class="sxs-lookup"><span data-stu-id="7a804-131">Federation type</span></span></th>
    <th><span data-ttu-id="7a804-132">DNS 记录</span><span class="sxs-lookup"><span data-stu-id="7a804-132">DNS Records</span></span></th>
    <th><span data-ttu-id="7a804-133">策略定义</span><span class="sxs-lookup"><span data-stu-id="7a804-133">Policy Definition</span></span></th>
    <th><span data-ttu-id="7a804-134">注释</span><span class="sxs-lookup"><span data-stu-id="7a804-134">Notes</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="7a804-135">已发现合作伙伴域</span><span class="sxs-lookup"><span data-stu-id="7a804-135">Discovered Partner Domain</span></span></p></td>
    <td><p><span data-ttu-id="7a804-136">配置 _sipfederationtls 格式的 SRV 记录。 _tcp。&lt;外部域名&gt;, SRV 记录的端口值为 TCP 5061, 并且<strong>提供此服务的主机</strong>定义为 sip。</span><span class="sxs-lookup"><span data-stu-id="7a804-136">Configure SRV record of the format _sipfederationtls._tcp.&lt;external domain name&gt;Where the port value for the SRV record is TCP 5061 and the <strong>Host offering this service</strong> is defined as sip.</span></span> <span data-ttu-id="7a804-137">&lt;外部域名&gt; -您的访问边缘服务的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="7a804-137">&lt;external domain name&gt; – the FQDN of your Access Edge service.</span></span> <span data-ttu-id="7a804-138">有关创建 SRV 记录的详细信息, 请参阅<a href="lync-server-2013-configure-dns-for-edge-support.md">在 Lync Server 2013 中配置 edge 支持的 DNS</a></span><span class="sxs-lookup"><span data-stu-id="7a804-138">See <a href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</a> for details on creating the SRV record</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="7a804-139"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">在 Lync Server 2013 中启用或禁用联盟和公共 IM 连接</a></span><span class="sxs-lookup"><span data-stu-id="7a804-139"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="7a804-140"><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">在 Lync Server 2013 中启用或禁用联盟伙伴发现</a></span><span class="sxs-lookup"><span data-stu-id="7a804-140"><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Enable or disable discovery of federation partners in Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="7a804-141">以前的版本称为 "<strong>增强联盟</strong>" 这种类型的联合。</span><span class="sxs-lookup"><span data-stu-id="7a804-141">Previous versions referred to this type of federation as <strong>Open Enhanced Federation</strong>.</span></span> <span data-ttu-id="7a804-142">这种类型的联盟需要创建 SRV 记录, 这是为了允许其他合作伙伴发现你的联盟。</span><span class="sxs-lookup"><span data-stu-id="7a804-142">The creation of the SRV record is required for this type of federation and is to allow other partners to discover your federation.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="7a804-143">允许的伙伴域</span><span class="sxs-lookup"><span data-stu-id="7a804-143">Allowed Partner Domain</span></span></p></td>
    <td><p><span data-ttu-id="7a804-144">配置 _sipfederationtls 格式的 SRV 记录。 _tcp。&lt;外部域名&gt;, SRV 记录的端口值为 TCP 5061, 并且<strong>提供此服务的主机</strong>定义为 sip。</span><span class="sxs-lookup"><span data-stu-id="7a804-144">Configure SRV record of the format _sipfederationtls._tcp.&lt;external domain name&gt;Where the port value for the SRV record is TCP 5061 and the <strong>Host offering this service</strong> is defined as sip.</span></span> <span data-ttu-id="7a804-145">&lt;外部域名&gt; -您的访问边缘服务的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="7a804-145">&lt;external domain name&gt; – the FQDN of your Access Edge service.</span></span> <span data-ttu-id="7a804-146">有关创建 SRV 记录的详细信息, 请参阅<a href="lync-server-2013-configure-dns-for-edge-support.md">在 Lync Server 2013 中配置 edge 支持的 DNS</a></span><span class="sxs-lookup"><span data-stu-id="7a804-146">See <a href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</a> for details on creating the SRV record</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="7a804-147"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">在 Lync Server 2013 中启用或禁用联盟和公共 IM 连接</a></span><span class="sxs-lookup"><span data-stu-id="7a804-147"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="7a804-148">以前版本将此类型的联合称为<strong>增强联盟</strong>。</span><span class="sxs-lookup"><span data-stu-id="7a804-148">Previous versions referred to this type of federation as <strong>Enhanced Federation</strong>.</span></span> <span data-ttu-id="7a804-149">SRV 记录的创建对于这种类型的联盟是可选的, 并且允许其他合作伙伴发现你的联盟。</span><span class="sxs-lookup"><span data-stu-id="7a804-149">The creation of the SRV record is optional for this type of federation and is to allow other partners to discover your federation.</span></span> <span data-ttu-id="7a804-150">当然, 这是一个打开的<strong>增强联盟</strong>, 或者是已<strong>发现的合作伙伴域</strong></span><span class="sxs-lookup"><span data-stu-id="7a804-150">Of course, this is then an <strong>Open Enhanced Federation</strong>, or <strong>Discovered Partner Domain</strong></span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="7a804-151">允许的合作伙伴服务器</span><span class="sxs-lookup"><span data-stu-id="7a804-151">Allowed Partner Server</span></span></p></td>
    <td><p><span data-ttu-id="7a804-152">在策略中将 SIP 域名和合作伙伴边缘服务器 FQDN 配置为联盟伙伴</span><span class="sxs-lookup"><span data-stu-id="7a804-152">Configure the SIP domain name and the partner Edge Server FQDN as a federation partner in Policies</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="7a804-153"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">在 Lync Server 2013 中启用或禁用联盟和公共 IM 连接</a></span><span class="sxs-lookup"><span data-stu-id="7a804-153"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="7a804-154"><a href="lync-server-2013-configure-support-for-allowed-external-domains.md">在 Lync Server 2013 中配置对允许的外部域的支持</a></span><span class="sxs-lookup"><span data-stu-id="7a804-154"><a href="lync-server-2013-configure-support-for-allowed-external-domains.md">Configure support for allowed external domains in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="7a804-155"><a href="lync-server-2013-configure-support-for-blocked-external-domains.md">在 Lync Server 2013 中配置对阻止的外部域的支持</a></span><span class="sxs-lookup"><span data-stu-id="7a804-155"><a href="lync-server-2013-configure-support-for-blocked-external-domains.md">Configure support for blocked external domains in Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="7a804-156">此联合类型是一对一关系的定义, 不允许发现其他联合合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="7a804-156">This federation type is the definition of a one to one relationship and does not allow for discovery of other federation partners.</span></span> <span data-ttu-id="7a804-157">每个联盟伙伴都是明确配置的。</span><span class="sxs-lookup"><span data-stu-id="7a804-157">Each federation partner is configured explicitly.</span></span> <span data-ttu-id="7a804-158">在以前的版本中, 这称为<strong>直接联盟</strong></span><span class="sxs-lookup"><span data-stu-id="7a804-158">In previous versions, this was known as <strong>Direct Federation</strong></span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="7a804-159">托管提供商和公共 IM 提供商</span><span class="sxs-lookup"><span data-stu-id="7a804-159">Hosting Provider and Public IM Provider</span></span></p></td>
    <td><p><span data-ttu-id="7a804-160">没有为此类型的联合定义特定的 DNS 要求</span><span class="sxs-lookup"><span data-stu-id="7a804-160">No specific DNS requirements are defined for this type of federation</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="7a804-161"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">在 Lync Server 2013 中启用或禁用联盟和公共 IM 连接</a></span><span class="sxs-lookup"><span data-stu-id="7a804-161"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="7a804-162"><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">在 Lync Server 2013 中创建或编辑公共 SIP 联盟提供程序</a></span><span class="sxs-lookup"><span data-stu-id="7a804-162"><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Create or edit public SIP federated providers in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="7a804-163"><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">在 Lync Server 2013 中创建或编辑托管的 SIP 联盟提供程序</a></span><span class="sxs-lookup"><span data-stu-id="7a804-163"><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Create or edit hosted SIP federated providers Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="7a804-164">此联合类型定义你希望为你的用户配置的服务和托管提供程序。</span><span class="sxs-lookup"><span data-stu-id="7a804-164">This federation type defines services and hosting providers that you want to configure for your users.</span></span> <span data-ttu-id="7a804-165">典型用法包括公共 IM 提供商 (如 Windows Live Messenger) 的配置 Yahoo!</span><span class="sxs-lookup"><span data-stu-id="7a804-165">Typical uses include configuration for public IM providers like Windows Live Messenger, Yahoo!</span></span> <span data-ttu-id="7a804-166">和 AOL 以及托管提供商 (如 Lync Online 和 Office 365)</span><span class="sxs-lookup"><span data-stu-id="7a804-166">and AOL, as well as hosting providers such as Lync Online and Office 365</span></span></p>
    <div>

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="7a804-167">从2012年9月1日起, Microsoft Lync 公共 IM 连接用户订阅许可证 ("PIC USL") 不再可用于购买新的或续订协议。</span><span class="sxs-lookup"><span data-stu-id="7a804-167">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="7a804-168">具有活动许可证的客户将能够继续与 Yahoo! 进行联盟</span><span class="sxs-lookup"><span data-stu-id="7a804-168">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="7a804-169">Messenger, 直到服务关闭日期。</span><span class="sxs-lookup"><span data-stu-id="7a804-169">Messenger until the service shut down date.</span></span> <span data-ttu-id="7a804-170">AOL 和 Yahoo! 的有效期结束日期为2014年6月</span><span class="sxs-lookup"><span data-stu-id="7a804-170">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="7a804-171">已宣布。</span><span class="sxs-lookup"><span data-stu-id="7a804-171">has been announced.</span></span> <span data-ttu-id="7a804-172">有关详细信息, 请参阅<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公共即时消息连接支持</A>。</span><span class="sxs-lookup"><span data-stu-id="7a804-172">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="7a804-173">PIC USL 是 Lync Server 或 Office 通信服务器与 Yahoo! 联合所需的每个每个用户每月订阅许可证。</span><span class="sxs-lookup"><span data-stu-id="7a804-173">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="7a804-174">Messenger.</span><span class="sxs-lookup"><span data-stu-id="7a804-174">Messenger.</span></span> <span data-ttu-id="7a804-175">Microsoft 提供此服务的能力已作为对 Yahoo! 的支持, 它的底层协议被向下缠绕。</span><span class="sxs-lookup"><span data-stu-id="7a804-175">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="7a804-176">Lync 比以往更多, 是一种强大的工具, 用于跨组织和全球各地的人员进行连接。</span><span class="sxs-lookup"><span data-stu-id="7a804-176">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="7a804-177">与 Windows Live Messenger 的联盟不需要除 Lync 标准 CAL 之外的其他用户/设备许可证。</span><span class="sxs-lookup"><span data-stu-id="7a804-177">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="7a804-178">Skype 联盟将添加到此列表, 使 Lync 用户可以通过 IM 和语音与成百上千人联系。</span><span class="sxs-lookup"><span data-stu-id="7a804-178">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>


    </div></td>
    </tr>
    </tbody>
    </table>


2.  <span data-ttu-id="7a804-179">定义和配置任何所需的 DNS 主机 (A 或 AAAA for IPv6) 和 DNS SRV 记录</span><span class="sxs-lookup"><span data-stu-id="7a804-179">Define and configure any required DNS host (A or AAAA for IPv6) and DNS SRV records</span></span>

3.  <span data-ttu-id="7a804-180">使用 Lync Server 控制面板或使用 Lync Server 命令行管理程序和相应的 cmdlet 定义和配置任何策略。</span><span class="sxs-lookup"><span data-stu-id="7a804-180">Define and configure any policies using the Lync Server Control Panel or by using the Lync Server Management Shell and the appropriate cmdlets.</span></span> <span data-ttu-id="7a804-181">有关 Lync Server Management Shell cmdlet 的详细信息, 请参阅[Lync server 2013 中的联盟和外部访问 cmdlet](https://docs.microsoft.com/powershell/module/skype/)</span><span class="sxs-lookup"><span data-stu-id="7a804-181">For details on the Lync Server Management Shell cmdlets, see [Federation and external access cmdlets in Lync Server 2013](https://docs.microsoft.com/powershell/module/skype/)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7a804-182">Lync 会议室系统 (LRS) 不显示由联盟 Lync 合作伙伴中的组织者发送的会议的 "联接" 按钮。</span><span class="sxs-lookup"><span data-stu-id="7a804-182">Lync Room System (LRS) does not show join button for meetings sent by organizers in federated Lync partners.</span></span> <span data-ttu-id="7a804-183">若要在 LRS 上显示会议加入链接, 发送组织必须使用以下 cmdlet 启用 TNEF:</span><span class="sxs-lookup"><span data-stu-id="7a804-183">For a meeting join link to appear on LRS, the sending organization must enable TNEF by using the following cmdlet:</span></span><BR><BR><CODE>New-RemoteDomain -DomainName Contoso.com -Name Contoso</CODE><BR><CODE>Set-RemoteDomain -Identity Contoso -TNEFEnabled $true</CODE><BR><span data-ttu-id="7a804-184">请注意, 这不是 LRS 的特定功能。</span><span class="sxs-lookup"><span data-stu-id="7a804-184">Note that this is not LRS specific.</span></span> <span data-ttu-id="7a804-185">在这种情况下, outlook 和 Lync 也不会显示联接链接, 因为 MAPI 属性未传输, 但在 Outlook 情况下, 用户可以打开会议邀请, 然后单击会议 URL。</span><span class="sxs-lookup"><span data-stu-id="7a804-185">Outlook and Lync would also not show Join links in this case as MAPI properties are not transported, but in the Outlook case, the user can open up the meeting invite and click on the meeting URL.</span></span> <span data-ttu-id="7a804-186">当 TNEFEnabled 设置为 true 时, Exchange 2013 不会去除 MAPI 属性 (包括 OnlineMeetingExternalLink), 并且将在提醒中显示 "加入" 按钮。</span><span class="sxs-lookup"><span data-stu-id="7a804-186">When TNEFEnabled is set to true Exchange 2013 does not strip MAPI properties including OnlineMeetingExternalLink and the Join button will be shown on the reminder.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7a804-187">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7a804-187">See Also</span></span>


[<span data-ttu-id="7a804-188">在 Lync Server 2013 中规划 SIP、XMPP 联盟和公共即时消息</span><span class="sxs-lookup"><span data-stu-id="7a804-188">Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md)  
[<span data-ttu-id="7a804-189">管理对 Lync Server 2013 的联盟和外部访问</span><span class="sxs-lookup"><span data-stu-id="7a804-189">Managing federation and external access to Lync Server 2013</span></span>](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

