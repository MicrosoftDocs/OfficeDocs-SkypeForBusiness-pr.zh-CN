---
title: 集成本地统一消息的部署过程
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for integrating on-premises Unified Messaging and Lync Server
ms:assetid: 269a4436-f09f-415b-96ab-49a64370a385
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425737(v=OCS.15)
ms:contentKeyID: 48183664
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2f8edade1ed4f0480d776e77eb66816c033a7e3d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213508"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-integrating-on-premises-unified-messaging-and-lync-server-2013"></a><span data-ttu-id="3996e-102">集成本地统一消息和 Lync Server 2013 的部署过程</span><span class="sxs-lookup"><span data-stu-id="3996e-102">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3996e-103">_**上次修改的主题：** 2012-12-17_</span><span class="sxs-lookup"><span data-stu-id="3996e-103">_**Topic Last Modified:** 2012-12-17_</span></span>

<span data-ttu-id="3996e-104">如果要将 Exchange 统一消息（UM）与 Lync Server 2013 集成，则必须执行本主题中所述的任务。</span><span class="sxs-lookup"><span data-stu-id="3996e-104">If you want to integrate Exchange Unified Messaging (UM) with Lync Server 2013, you must perform the tasks described in this topic.</span></span> <span data-ttu-id="3996e-105">此外，请务必查看有关[集成本地统一消息和 Lync Server 2013 指南](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)中所述的规划和部署最佳做法。</span><span class="sxs-lookup"><span data-stu-id="3996e-105">Also be sure that you review the planning and deployment best practices described in [Guidelines for integrating on-premises Unified Messaging and Lync Server 2013](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md).</span></span> <span data-ttu-id="3996e-106">本主题假定您已使用并置中介服务器部署了 Lync Server 2013，并且您已为用户启用 Lync Server 2013，但并不一定已执行了所有部署和配置步骤来启用企业语音，如部署文档中的 "在[Lync Server 2013 中部署企业语音](lync-server-2013-deploying-enterprise-voice.md)" 中所述。</span><span class="sxs-lookup"><span data-stu-id="3996e-106">This topic assumes that you have deployed Lync Server 2013 with a collocated Mediation Server and that you have enabled users for Lync Server 2013, but not necessarily that you have performed all deployment and configuration steps to enable Enterprise Voice, as described in [Deploying Enterprise Voice in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) in the Deployment documentation.</span></span>

<div>

## <a name="unified-messaging-integration-process"></a><span data-ttu-id="3996e-107">统一消息集成过程</span><span class="sxs-lookup"><span data-stu-id="3996e-107">Unified Messaging Integration Process</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="3996e-108">一定要与组织的 Exchange 管理员进行协调以确认您要执行的任务，以帮助确保顺利、成功的集成，这一点非常重要。</span><span class="sxs-lookup"><span data-stu-id="3996e-108">It is important that you coordinate with your organization’s Exchange administrators to confirm the tasks that each of you will perform to help ensure a smooth, successful integration.</span></span>



</div>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3996e-109">阶段</span><span class="sxs-lookup"><span data-stu-id="3996e-109">Phase</span></span></th>
<th><span data-ttu-id="3996e-110">步骤</span><span class="sxs-lookup"><span data-stu-id="3996e-110">Steps</span></span></th>
<th><span data-ttu-id="3996e-111">所需的组和角色</span><span class="sxs-lookup"><span data-stu-id="3996e-111">Required groups and roles</span></span></th>
<th><span data-ttu-id="3996e-112">部署文档</span><span class="sxs-lookup"><span data-stu-id="3996e-112">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3996e-113">部署下列各项之一：</span><span class="sxs-lookup"><span data-stu-id="3996e-113">Deploy one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="3996e-114">Microsoft Exchange Server 2007 Service Pack 1 （SP2）或最新 service pack</span><span class="sxs-lookup"><span data-stu-id="3996e-114">Microsoft Exchange Server 2007 Service Pack 1 (SP2) or latest service pack</span></span></p></li>
<li><p><span data-ttu-id="3996e-115">Microsoft Exchange Server 2010 或最新的 service pack</span><span class="sxs-lookup"><span data-stu-id="3996e-115">Microsoft Exchange Server 2010 or latest service pack</span></span></p></li>
<li><p><span data-ttu-id="3996e-116">Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="3996e-116">Microsoft Exchange Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="3996e-117">如果使用的是 Microsoft Exchange Server 2013，请在与 Lync Server 2013 相同的林或不同林中安装以下 Exchange 服务器角色：</span><span class="sxs-lookup"><span data-stu-id="3996e-117">If you are using Microsoft Exchange Server 2013, install the following Exchange Server roles in either the same forest or a different forest as Lync Server 2013:</span></span></p>
<ul>
<li><p><span data-ttu-id="3996e-118">客户端访问</span><span class="sxs-lookup"><span data-stu-id="3996e-118">Client Access</span></span></p></li>
<li><p><span data-ttu-id="3996e-119">邮箱</span><span class="sxs-lookup"><span data-stu-id="3996e-119">Mailbox</span></span></p></li>
</ul>
<p><span data-ttu-id="3996e-120">如果 Microsoft Exchange Server 2013 和 Exchange 统一消息（UM）安装在不同的林中，则将每个 Exchange 林配置为信任 Lync Server 2013 林。</span><span class="sxs-lookup"><span data-stu-id="3996e-120">If Microsoft Exchange Server 2013 and Exchange Unified Messaging (UM) are installed in different forests, configure each Exchange forest to trust the Lync Server 2013 forest.</span></span></p>
<p><span data-ttu-id="3996e-121">如果使用的是 Exchange 2010，请在与 Lync Server 2013 相同的林中或不同的林中安装以下 Exchange 服务器角色：</span><span class="sxs-lookup"><span data-stu-id="3996e-121">If you are using Exchange 2010, install the following Exchange Server roles in either the same forest or a different forest as Lync Server 2013:</span></span></p>
<ul>
<li><p><span data-ttu-id="3996e-122">统一消息</span><span class="sxs-lookup"><span data-stu-id="3996e-122">Unified Messaging</span></span></p></li>
<li><p><span data-ttu-id="3996e-123">集线器传输</span><span class="sxs-lookup"><span data-stu-id="3996e-123">Hub Transport</span></span></p></li>
<li><p><span data-ttu-id="3996e-124">客户端访问</span><span class="sxs-lookup"><span data-stu-id="3996e-124">Client Access</span></span></p></li>
<li><p><span data-ttu-id="3996e-125">邮箱</span><span class="sxs-lookup"><span data-stu-id="3996e-125">Mailbox</span></span></p></li>
</ul>
<p><span data-ttu-id="3996e-126">如果 Lync Server 2013 和 Exchange 统一消息（UM）安装在不同的林中，则将每个 Exchange 林配置为信任 Lync Server 2013 林。</span><span class="sxs-lookup"><span data-stu-id="3996e-126">If Lync Server 2013 and Exchange Unified Messaging (UM) are installed in different forests, configure each Exchange forest to trust the Lync Server 2013 forest.</span></span></p></td>
<td><p><span data-ttu-id="3996e-127">企业管理员（如果这是组织中的第一个 Exchange Server）</span><span class="sxs-lookup"><span data-stu-id="3996e-127">Enterprise administrators (if this is the first Exchange Server in the organization)</span></span></p>
<p><span data-ttu-id="3996e-128">或者 -</span><span class="sxs-lookup"><span data-stu-id="3996e-128">-OR-</span></span></p>
<p><span data-ttu-id="3996e-129">Exchange 组织管理员（如果这不是组织中的第一个 Exchange Server）</span><span class="sxs-lookup"><span data-stu-id="3996e-129">Exchange Organization administrator (if this is not the first Exchange Server in the organization)</span></span></p></td>
<td><p><span data-ttu-id="3996e-130">请参阅适用于您的 Exchange Server 版本的文档：</span><span class="sxs-lookup"><span data-stu-id="3996e-130">See the appropriate documentation for your version of Exchange Server:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="3996e-131">Exchange Server 2007 中的<a href="https://go.microsoft.com/fwlink/p/?linkid=268694">https://go.microsoft.com/fwlink/p/?LinkId=268694</a>部署文档。</span><span class="sxs-lookup"><span data-stu-id="3996e-131">Exchange Server 2007 deployment documentation at <a href="https://go.microsoft.com/fwlink/p/?linkid=268694">https://go.microsoft.com/fwlink/p/?LinkId=268694</a>.</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="3996e-132">上的<a href="https://go.microsoft.com/fwlink/p/?linkid=268695">https://go.microsoft.com/fwlink/p/?LinkId=268695</a>Exchange Server 2010 或最新的 service pack 部署文档。</span><span class="sxs-lookup"><span data-stu-id="3996e-132">Exchange Server 2010 or latest service pack deployment documentation at <a href="https://go.microsoft.com/fwlink/p/?linkid=268695">https://go.microsoft.com/fwlink/p/?LinkId=268695</a>.</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="3996e-133">Microsoft Exchange Server 2013 规划和部署位置<a href="https://go.microsoft.com/fwlink/p/?linkid=266569">https://go.microsoft.com/fwlink/p/?LinkId=266569</a>。</span><span class="sxs-lookup"><span data-stu-id="3996e-133">Microsoft Exchange Server 2013 Planning and Deployment at <a href="https://go.microsoft.com/fwlink/p/?linkid=266569">https://go.microsoft.com/fwlink/p/?LinkId=266569</a>.</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3996e-134">安装证书。</span><span class="sxs-lookup"><span data-stu-id="3996e-134">Install certificates.</span></span></p></td>
<td><p><span data-ttu-id="3996e-135">从受信任的根证书颁发机构（CA）下载并安装每个 Exchange UM 服务器的证书。</span><span class="sxs-lookup"><span data-stu-id="3996e-135">Download and install certificates for each Exchange UM server from a trusted root certificate authority (CA).</span></span> <span data-ttu-id="3996e-136">在运行 Exchange UM 和 Lync Server 2013 的服务器之间的相互传输级别安全性（MTLS）中，证书是必需的。</span><span class="sxs-lookup"><span data-stu-id="3996e-136">The certificates are required for mutual Transport Level Security (MTLS) between the servers running Exchange UM and Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="3996e-137">管理员</span><span class="sxs-lookup"><span data-stu-id="3996e-137">Administrators</span></span></p></td>
<td><p><span data-ttu-id="3996e-138"><a href="lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md">在运行 Microsoft Exchange Server 统一消息的服务器上配置证书</a></span><span class="sxs-lookup"><span data-stu-id="3996e-138"><a href="lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md">Configure certificates on the server running Microsoft Exchange Server Unified Messaging</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3996e-139">创建和配置新的 Exchange UM SIP 拨号计划。</span><span class="sxs-lookup"><span data-stu-id="3996e-139">Create and configure a new Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="3996e-140">在 Exchange UM 服务器上，根据您的组织的特定部署要求创建 SIP 拨号计划。</span><span class="sxs-lookup"><span data-stu-id="3996e-140">On the Exchange UM server, create a SIP dial plan based on your organization’s specific deployment requirements.</span></span></p></td>
<td><p><span data-ttu-id="3996e-141">Exchange 组织管理员</span><span class="sxs-lookup"><span data-stu-id="3996e-141">Exchange Organization administrator</span></span></p></td>
<td><p><span data-ttu-id="3996e-142">对于 Exchange 2007 SP1 或最新的 service pack &quot;，请参阅如何在<a href="https://go.microsoft.com/fwlink/p/?linkid=268632">https://go.microsoft.com/fwlink/p/?linkId=268632</a>中创建统一消息 SIP&quot; URI 拨号计划。</span><span class="sxs-lookup"><span data-stu-id="3996e-142">For Exchange 2007 SP1 or latest service pack, see &quot;How to Create a Unified Messaging SIP URI Dial Plan&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268632">https://go.microsoft.com/fwlink/p/?linkId=268632</a>.</span></span></p>
<p><span data-ttu-id="3996e-143">有关 Exchange 2010 或最新的 service pack &quot;，请参阅在上&quot; <a href="https://go.microsoft.com/fwlink/p/?linkid=268674">https://go.microsoft.com/fwlink/p/?linkId=268674</a>创建 UM 拨号计划。</span><span class="sxs-lookup"><span data-stu-id="3996e-143">For Exchange 2010 or latest service pack, see &quot;Create a UM Dial Plan&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268674">https://go.microsoft.com/fwlink/p/?linkId=268674</a>.</span></span></p>
<p><span data-ttu-id="3996e-144">对于 Exchange 2013，请参阅中的<a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>统一消息。</span><span class="sxs-lookup"><span data-stu-id="3996e-144">For Exchange 2013, see Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3996e-145">配置 Exchange UM SIP 拨号计划的安全设置。</span><span class="sxs-lookup"><span data-stu-id="3996e-145">Configure security settings for the Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="3996e-146">若要加密企业语音流量，请将 Exchange UM SIP 拨号计划中的安全设置配置为 " <strong>SIP 安全</strong>" 或 "<strong>安全</strong>"。</span><span class="sxs-lookup"><span data-stu-id="3996e-146">To encrypt Enterprise Voice traffic, configure the security settings on the Exchange UM SIP dial plan as <strong>SIP Secured</strong> or <strong>Secured</strong>.</span></span> <span data-ttu-id="3996e-147">如果你已部署或计划在你的环境中部署 Lync Phone Edition 设备，则这是一个非常重要的步骤。</span><span class="sxs-lookup"><span data-stu-id="3996e-147">This is an especially important step if you have deployed or plan to deploy Lync Phone Edition devices in your environment.</span></span> <span data-ttu-id="3996e-148">为了使 Lync Phone Edition 设备在具有 Exchange UM 集成的环境中正常运行，Lync Server 加密设置必须与 Exchange UM 拨号计划安全设置一致。</span><span class="sxs-lookup"><span data-stu-id="3996e-148">For Lync Phone Edition devices to function in an environment with Exchange UM integration, Lync Server encryption settings must align with the Exchange UM dial plan security settings.</span></span> <span data-ttu-id="3996e-149">有关详细信息，请参考部署文档。</span><span class="sxs-lookup"><span data-stu-id="3996e-149">For details, refer to the Deployment documentation.</span></span></p></td>
<td><p><span data-ttu-id="3996e-150">Exchange 组织管理员</span><span class="sxs-lookup"><span data-stu-id="3996e-150">Exchange Organization administrator</span></span></p></td>
<td><p><span data-ttu-id="3996e-151"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">在 Microsoft Exchange 上为 Lync Server 2013 配置统一消息</a></span><span class="sxs-lookup"><span data-stu-id="3996e-151"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configure Unified Messaging on Microsoft Exchange for Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="3996e-152">对于 Exchange 2007 SP1 或最新的 service pack，另请参阅：</span><span class="sxs-lookup"><span data-stu-id="3996e-152">For Exchange 2007 SP1 or latest service pack, see also:</span></span></p>
<p><span data-ttu-id="3996e-153">&quot;如何在的统一消息拨号计划&quot;上配置安全性。 <a href="https://go.microsoft.com/fwlink/p/?linkid=268696">https://go.microsoft.com/fwlink/p/?LinkId=268696</a></span><span class="sxs-lookup"><span data-stu-id="3996e-153">&quot;How to Configure Security on a Unified Messaging Dial Plan&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268696">https://go.microsoft.com/fwlink/p/?LinkId=268696</a>.</span></span></p>
<p><span data-ttu-id="3996e-154">对于 Exchange 2010 或最新的 Service Pack，另请参阅：</span><span class="sxs-lookup"><span data-stu-id="3996e-154">For Exchange 2010 or latest service pack, see also:</span></span></p>
<p><span data-ttu-id="3996e-155">&quot;在 UM 拨号计划&quot; <a href="https://go.microsoft.com/fwlink/p/?linkid=268697">https://go.microsoft.com/fwlink/p/?LinkId=268697</a>中配置 VoIP 安全性。</span><span class="sxs-lookup"><span data-stu-id="3996e-155">&quot;Configure VoIP Security on a UM Dial Plan&quot; <a href="https://go.microsoft.com/fwlink/p/?linkid=268697">https://go.microsoft.com/fwlink/p/?LinkId=268697</a>.</span></span></p>
<p><span data-ttu-id="3996e-156">对于 Exchange 2013，请参阅中的<a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>统一消息。</span><span class="sxs-lookup"><span data-stu-id="3996e-156">For Exchange 2013, see Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3996e-157">将统一消息服务器添加到 Exchange UM SIP 拨号计划。</span><span class="sxs-lookup"><span data-stu-id="3996e-157">Add Unified Messaging servers to the Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="3996e-158">要使新安装的统一消息服务器可以应答和处理传入呼叫，必须将该统一消息服务器添加到 UM 拨号计划中。</span><span class="sxs-lookup"><span data-stu-id="3996e-158">To enable a newly installed Unified Messaging server to answer and process incoming calls, you must add the Unified Messaging server to a UM dial plan.</span></span> <span data-ttu-id="3996e-159">在这种情况下，请将服务器添加到 Exchange UM SIP 拨号计划中。</span><span class="sxs-lookup"><span data-stu-id="3996e-159">In this case, add the server to the Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="3996e-160">管理员</span><span class="sxs-lookup"><span data-stu-id="3996e-160">Administrators</span></span></p>
<p><span data-ttu-id="3996e-161">Exchange Server 管理员</span><span class="sxs-lookup"><span data-stu-id="3996e-161">Exchange Server administrators</span></span></p></td>
<td><p><span data-ttu-id="3996e-162">对于 Exchange 2007 SP1 或最新的 service pack &quot;，请参阅如何将统一消息服务器添加到&quot;拨号<a href="https://go.microsoft.com/fwlink/p/?linkid=268681">https://go.microsoft.com/fwlink/p/?linkId=268681</a>计划。</span><span class="sxs-lookup"><span data-stu-id="3996e-162">For Exchange 2007 SP1 or latest service pack, see &quot;How to Add Unified Messaging Server to a Dial Plan&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268681">https://go.microsoft.com/fwlink/p/?linkId=268681</a>.</span></span></p>
<p><span data-ttu-id="3996e-163">有关 Exchange 2010 或最新的 service pack &quot;，请参阅在上<a href="https://go.microsoft.com/fwlink/p/?linkid=268682">https://go.microsoft.com/fwlink/p/?linkId=268682</a>查看或配置 UM&quot;服务器的属性。</span><span class="sxs-lookup"><span data-stu-id="3996e-163">For Exchange 2010 or latest service pack, see &quot;View or Configure the Properties of a UM Server&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268682">https://go.microsoft.com/fwlink/p/?linkId=268682</a>.</span></span></p>
<p><span data-ttu-id="3996e-164">对于 Exchange 2013，请参阅中的<a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>统一消息。</span><span class="sxs-lookup"><span data-stu-id="3996e-164">For Exchange 2013, see Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3996e-165">配置使用 SIP 地址的邮箱。</span><span class="sxs-lookup"><span data-stu-id="3996e-165">Configure mailboxes with SIP addresses.</span></span></p></td>
<td><p><span data-ttu-id="3996e-166">将 SIP 地址分配给将使用 Exchange UM 功能的企业语音用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="3996e-166">Assign SIP addresses to the mailboxes of Enterprise Voice users who will be using Exchange UM features.</span></span></p></td>
<td><p><span data-ttu-id="3996e-167">Lync Server 2013 管理员</span><span class="sxs-lookup"><span data-stu-id="3996e-167">Lync Server 2013 administrator</span></span></p>
<p><span data-ttu-id="3996e-168">Exchange 收件人管理员</span><span class="sxs-lookup"><span data-stu-id="3996e-168">Exchange Recipient administrator</span></span></p></td>
<td><p><span data-ttu-id="3996e-169">对于 Exchange 2007 SP1 或最新的 service pack &quot;，请参阅如何在&quot; <a href="https://go.microsoft.com/fwlink/p/?linkid=268698">https://go.microsoft.com/fwlink/p/?LinkId=268698</a>中为启用了 UM 的用户添加、删除或修改 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="3996e-169">For Exchange 2007 SP1 or latest service pack, see &quot;How to Add, Remove, or Modify a SIP Address for a UM-Enabled User&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268698">https://go.microsoft.com/fwlink/p/?LinkId=268698</a>.</span></span></p>
<p><span data-ttu-id="3996e-170">对于 Exchange 2010 或最新的 service pack &quot;，请参阅在上<a href="https://go.microsoft.com/fwlink/p/?linkid=268699">https://go.microsoft.com/fwlink/p/?LinkId=268699</a>为启用了 UM 的&quot;用户修改 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="3996e-170">For Exchange 2010 or latest service pack, see &quot;Modify a SIP Address for a UM-Enabled User&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268699">https://go.microsoft.com/fwlink/p/?LinkId=268699</a>.</span></span></p>
<p><span data-ttu-id="3996e-171">对于 Exchange 2013，请参阅中的<a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>统一消息。</span><span class="sxs-lookup"><span data-stu-id="3996e-171">For Exchange 2013, see Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3996e-172">运行 exchucutil.ps1 脚本。</span><span class="sxs-lookup"><span data-stu-id="3996e-172">Run the exchucutil.ps1 script.</span></span></p></td>
<td><p><span data-ttu-id="3996e-173">在运行 Exchange UM 服务的服务器上，打开 Exchange 命令行管理程序并运行 exchucutil.ps1 脚本，该脚本执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="3996e-173">On the server running Exchange UM services, open the Exchange Management Shell and run the exchucutil.ps1 script, which does the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="3996e-174">授予 Lync Server 2013 权限，以读取 Exchange UM Active Directory 域服务对象，尤其是在上一任务中创建的 SIP 拨号计划。</span><span class="sxs-lookup"><span data-stu-id="3996e-174">Grants Lync Server 2013 permission to read Exchange UM Active Directory Domain Services objects, specifically, the SIP dial plans created in the previous task.</span></span></p></li>
<li><p><span data-ttu-id="3996e-175">在 Active Directory 中为每个 Lync Server 2013 Enterprise Edition pool 或 Standard Edition server 创建一个统一消息 IP 网关对象，该对象承载为已启用企业语音的用户。</span><span class="sxs-lookup"><span data-stu-id="3996e-175">Creates a Unified Messaging IP gateway object in Active Directory for each Lync Server 2013 Enterprise Edition pool or Standard Edition server that hosts users who are enabled for Enterprise Voice.</span></span></p></li>
<li><p><span data-ttu-id="3996e-176">为每个网关创建一个 Exchange UM 智能寻线。</span><span class="sxs-lookup"><span data-stu-id="3996e-176">Creates an Exchange UM hunt group for each gateway.</span></span> <span data-ttu-id="3996e-177">该智能寻线的前导标识符将是与相应网关相关联的拨号计划的名称。</span><span class="sxs-lookup"><span data-stu-id="3996e-177">The hunt group pilot identifier will be the name of the dial plan that is associated with the corresponding gateway.</span></span> <span data-ttu-id="3996e-178">如果存在多个拨号计划，则需要进行一对一映射。</span><span class="sxs-lookup"><span data-stu-id="3996e-178">These need to be mapped 1:1 if there is more than one dial plan.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="3996e-179">Exchange 组织管理员</span><span class="sxs-lookup"><span data-stu-id="3996e-179">Exchange Organization administrator</span></span></p>
<p><span data-ttu-id="3996e-180">Exchange 收件人管理员</span><span class="sxs-lookup"><span data-stu-id="3996e-180">Exchange Recipient administrator</span></span></p></td>
<td><p><span data-ttu-id="3996e-181"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">在 Microsoft Exchange 上为 Lync Server 2013 配置统一消息</a></span><span class="sxs-lookup"><span data-stu-id="3996e-181"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configure Unified Messaging on Microsoft Exchange for Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3996e-182">配置 Lync Server 2013 拨号计划。</span><span class="sxs-lookup"><span data-stu-id="3996e-182">Configure Lync Server 2013 dial plans.</span></span></p></td>
<td><p><span data-ttu-id="3996e-183">如果要与 Exchange 2007 SP1 或最新的 service pack 或 Exchange 2010 集成，请使用与 Exchange UM 拨号计划完全限定的域名（FQDN）匹配的名称创建新的企业语音拨号计划。</span><span class="sxs-lookup"><span data-stu-id="3996e-183">If you are integrating with Exchange 2007 SP1 or latest service pack, or Exchange 2010, create a new Enterprise Voice dial plan with a name that matches the Exchange UM dial plan fully qualified domain name (FQDN).</span></span></p>



> [!NOTE]
> <span data-ttu-id="3996e-184">您将需要为每个 UM 拨号计划执行此操作。</span><span class="sxs-lookup"><span data-stu-id="3996e-184">You will need to do this for each UM Dial plan.</span></span>


<p><span data-ttu-id="3996e-185">如果要与 Exchange 2010 SP1 集成，请确保已配置合适的全局/站点级别或池级别的企业语音拨号计划。</span><span class="sxs-lookup"><span data-stu-id="3996e-185">If you are integrating with Exchange 2010 SP1, ensure that suitable global/site-level or pool-level Enterprise Voice dial plans have been configured.</span></span></p>



> [!NOTE]
> <span data-ttu-id="3996e-186">如果要与 Exchange 2010 SP1 集成，则 Lync Server 拨号计划和 Exchange UM SIP 拨号计划名称不需要匹配。</span><span class="sxs-lookup"><span data-stu-id="3996e-186">If you are integrating with Exchange 2010 SP1, the Lync Server dial plan and Exchange UM SIP dial plan names do not need to match.</span></span>

</td>
<td><p><span data-ttu-id="3996e-187">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="3996e-187">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="3996e-188"><a href="lync-server-2013-configuring-dial-plans.md">在 Lync Server 2013 中配置拨号计划</a></span><span class="sxs-lookup"><span data-stu-id="3996e-188"><a href="lync-server-2013-configuring-dial-plans.md">Configuring dial plans in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3996e-189">运行 Exchange UM 集成工具。</span><span class="sxs-lookup"><span data-stu-id="3996e-189">Run the Exchange UM Integration tool.</span></span></p></td>
<td><p><span data-ttu-id="3996e-190">在 Lync Server 2013 上，运行<strong>ocsumutil.exe</strong>，这是：</span><span class="sxs-lookup"><span data-stu-id="3996e-190">On the Lync Server 2013, run <strong>ocsumutil.exe</strong>, which:</span></span></p>
<ul>
<li><p><span data-ttu-id="3996e-191">创建订阅者访问和自动助理联系人对象。</span><span class="sxs-lookup"><span data-stu-id="3996e-191">Creates Subscriber Access and Auto Attendant contact objects.</span></span></p></li>
<li><p><span data-ttu-id="3996e-192">验证是否存在具有与 Exchange UM 拨号计划 FQDN 相匹配的名称的企业语音拨号计划。</span><span class="sxs-lookup"><span data-stu-id="3996e-192">Validates that there is an Enterprise Voice dial plan with a name that matches the Exchange UM dial plan FQDN.</span></span> <span data-ttu-id="3996e-193">如果您运行的是 Exchange 2010 SP1 或更高版本，则拨号计划名称不需要匹配，您可以忽略该工具关于此工具的警告。</span><span class="sxs-lookup"><span data-stu-id="3996e-193">If you are running Exchange 2010 SP1 or later, the dial plan names do not need to match, and you can ignore the tool’s warning about this.</span></span></p></li>
</ul>
<p><span data-ttu-id="3996e-194">此工具的工作方式为：扫描 Active Directory 以获取 Exchange UM 设置，并允许 Lync Server 2013 管理员查看、创建和编辑联系人对象。</span><span class="sxs-lookup"><span data-stu-id="3996e-194">This tool works by scanning the Active Directory for Exchange UM settings and allowing the Lync Server 2013 administrator to view, create, and edit contact objects.</span></span></p></td>
<td><p><span data-ttu-id="3996e-195">RTCUniversalServerAdmins <em>和</em> RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="3996e-195">RTCUniversalServerAdmins <em>and</em> RTCUniversalUserAdmins</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="3996e-196">要成功运行 ocsumutil.exe，用户必须同时属于这两个组。</span><span class="sxs-lookup"><span data-stu-id="3996e-196">To run ocsumutil.exe successfully, the user must belong to both of these groups.</span></span>





> [!NOTE]
> <span data-ttu-id="3996e-197">要创建联系人对象，运行 ocsumutil.exe 的用户必须对存储新联系人对象的 Active Directory 组织单位 (OU) 具有正确的权限。</span><span class="sxs-lookup"><span data-stu-id="3996e-197">To create Contact objects, the user who runs ocsumutil.exe must have the correct permission to the Active Directory organizational unit (OU) where the new contact objects are stored.</span></span> <span data-ttu-id="3996e-198">可以通过运行<STRONG>CsOUPermission</STRONG> cmdlet 来授予此权限。</span><span class="sxs-lookup"><span data-stu-id="3996e-198">This permission can be granted by running the <STRONG>Grant-CsOUPermission</STRONG> cmdlet.</span></span> <span data-ttu-id="3996e-199">有关详细信息，请参阅 Lync Server 命令行管理程序文档。</span><span class="sxs-lookup"><span data-stu-id="3996e-199">For details, see the Lync Server Management Shell documentation.</span></span>

</td>
<td><p><span data-ttu-id="3996e-200"><a href="lync-server-2013-configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server.md">配置 Lync Server 2013 以使用 Microsoft Exchange Server 上的统一消息</a></span><span class="sxs-lookup"><span data-stu-id="3996e-200"><a href="lync-server-2013-configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server.md">Configure Lync Server 2013 to work with Unified Messaging on Microsoft Exchange Server</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3996e-201">如有必要，执行其他企业语音配置步骤。</span><span class="sxs-lookup"><span data-stu-id="3996e-201">If necessary, perform other Enterprise Voice configuration steps.</span></span></p></td>
<td><p><span data-ttu-id="3996e-202">如果尚未配置有关服务器或用户的企业语音设置，请执行下列一项或多项操作：</span><span class="sxs-lookup"><span data-stu-id="3996e-202">If you have not already configured Enterprise Voice settings on your servers or users, do one or more of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="3996e-203">部署和配置</span><span class="sxs-lookup"><span data-stu-id="3996e-203">Deploy and configure</span></span></p>
<p><span data-ttu-id="3996e-204">公共交换电话网络（PSTN）网关和中介服务器</span><span class="sxs-lookup"><span data-stu-id="3996e-204">Public switched telephone network (PSTN) gateways and Mediation Servers</span></span></p></li>
<li><p><span data-ttu-id="3996e-205">定义语音策略、PSTN 用法记录和出站呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="3996e-205">Define voice policies, PSTN usage records, and outbound call routes.</span></span></p></li>
<li><p><span data-ttu-id="3996e-206">为用户启用企业语音。</span><span class="sxs-lookup"><span data-stu-id="3996e-206">Enable users for Enterprise Voice.</span></span></p></li>
<li><p><span data-ttu-id="3996e-207">（可选）为特定用户配置拨号计划。</span><span class="sxs-lookup"><span data-stu-id="3996e-207">Optionally, configure specific users with dial plans.</span></span></p></li>
</ul>
<p><span data-ttu-id="3996e-208">可能还需要其他配置步骤，具体取决于启用的企业语音功能。</span><span class="sxs-lookup"><span data-stu-id="3996e-208">Other configuration steps may be required depending on the Enterprise Voice features that you enable.</span></span></p></td>
<td><p><span data-ttu-id="3996e-209">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="3996e-209">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="3996e-210">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="3996e-210">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="3996e-211">请参阅以下各节中的主题：</span><span class="sxs-lookup"><span data-stu-id="3996e-211">See topics in the following sections:</span></span></p>
<ul>
<li><p><span data-ttu-id="3996e-212"><a href="lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md">在 Lync Server 2013 中配置语音策略、PSTN 用法记录和语音路由</a></span><span class="sxs-lookup"><span data-stu-id="3996e-212"><a href="lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</a></span></span></p></li>
<li><p><span data-ttu-id="3996e-213"><a href="lync-server-2013-deploying-enterprise-voice.md">在 Lync Server 2013 中部署企业语音</a></span><span class="sxs-lookup"><span data-stu-id="3996e-213"><a href="lync-server-2013-deploying-enterprise-voice.md">Deploying Enterprise Voice in Lync Server 2013</a></span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3996e-214">为 Exchange UM 启用企业语音用户。</span><span class="sxs-lookup"><span data-stu-id="3996e-214">Enable Enterprise Voice users for Exchange UM.</span></span></p></td>
<td><p><span data-ttu-id="3996e-215">在 Exchange UM 服务器上，确保已创建统一消息邮箱策略，并且每个用户都有一个唯一的分机号码分配，然后为该用户启用统一消息。</span><span class="sxs-lookup"><span data-stu-id="3996e-215">On the Exchange UM server, ensure that a Unified Messaging mailbox policy has been created and that each user has a unique extension number assignment, and then enable the user for Unified Messaging.</span></span></p></td>
<td><p><span data-ttu-id="3996e-216">Exchange 收件人管理员</span><span class="sxs-lookup"><span data-stu-id="3996e-216">Exchange Recipient administrator</span></span></p></td>
<td><p><span data-ttu-id="3996e-217">对于 Exchange 2007 SP1 或最新的 service pack &quot;，请参阅如何为用户启用统一&quot;消息<a href="https://go.microsoft.com/fwlink/p/?linkid=268700">https://go.microsoft.com/fwlink/p/?LinkId=268700</a>。</span><span class="sxs-lookup"><span data-stu-id="3996e-217">For Exchange 2007 SP1 or latest service pack, see &quot;How to Enable a User for Unified Messaging&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268700">https://go.microsoft.com/fwlink/p/?LinkId=268700</a>.</span></span></p>
<p><span data-ttu-id="3996e-218">对于 Exchange 2010 或最新的 service pack &quot;，请参阅在上<a href="https://go.microsoft.com/fwlink/p/?linkid=268701">https://go.microsoft.com/fwlink/p/?LinkId=268701</a>为&quot;用户启用统一消息。</span><span class="sxs-lookup"><span data-stu-id="3996e-218">For Exchange 2010 or latest service pack, see &quot;Enable a User for Unified Messaging&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268701">https://go.microsoft.com/fwlink/p/?LinkId=268701</a>.</span></span></p>
<p><span data-ttu-id="3996e-219">对于 Exchange 2013，请参阅中的<a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>统一消息。</span><span class="sxs-lookup"><span data-stu-id="3996e-219">For Exchange 2013, see Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

