---
title: Lync Server 2013：持久聊天服务器的部署清单
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for Persistent Chat Server
ms:assetid: b1108f8f-88a2-4660-8086-d25ba76f7239
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412851(v=OCS.15)
ms:contentKeyID: 48185155
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6234ca4a8a0e7f6edc2069b7bb42f0bae545713b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049454"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="2281d-102">Lync Server 2013 中持久聊天服务器的部署清单</span><span class="sxs-lookup"><span data-stu-id="2281d-102">Deployment checklist for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2281d-103">_**上次修改的主题：** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="2281d-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="2281d-104">将 Lync Server 2013 与持久聊天服务器的部署要求您按照正确的顺序部署它，并完成所有需要的部署步骤。</span><span class="sxs-lookup"><span data-stu-id="2281d-104">Deployment of Lync Server 2013, Persistent Chat Server requires that you deploy it in the correct sequence and that you complete all required deployment steps.</span></span>

<div>

## <a name="deployment-sequence"></a><span data-ttu-id="2281d-105">部署顺序</span><span class="sxs-lookup"><span data-stu-id="2281d-105">Deployment Sequence</span></span>

<span data-ttu-id="2281d-106">您可以在部署初始拓扑后部署持久聊天服务器，其中包括至少一个 Lync Server 2013、前端池或一个 Lync Server 2013 （Standard Edition server）。</span><span class="sxs-lookup"><span data-stu-id="2281d-106">You can deploy Persistent Chat Server after you deploy your initial topology, including at least one Lync Server 2013, Front End pool or one Lync Server 2013, Standard Edition server.</span></span> <span data-ttu-id="2281d-107">本主题介绍如何通过将持久聊天服务器添加到现有部署来部署持久聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="2281d-107">This topic describes how to deploy Persistent Chat Server by adding it to an existing deployment.</span></span>

</div>

<div>

## <a name="deployment-process"></a><span data-ttu-id="2281d-108">部署过程</span><span class="sxs-lookup"><span data-stu-id="2281d-108">Deployment Process</span></span>

<span data-ttu-id="2281d-109">下表列出了部署持久聊天服务器的基本步骤，并提供了有关更多详细信息的链接。</span><span class="sxs-lookup"><span data-stu-id="2281d-109">The following table lists the basic steps to deploy Persistent Chat Server and provides links for more details.</span></span>

### <a name="persistent-chat-server-deployment-process"></a><span data-ttu-id="2281d-110">持久聊天服务器部署过程</span><span class="sxs-lookup"><span data-stu-id="2281d-110">Persistent Chat Server Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2281d-111">任务</span><span class="sxs-lookup"><span data-stu-id="2281d-111">Task</span></span></th>
<th><span data-ttu-id="2281d-112">步骤</span><span class="sxs-lookup"><span data-stu-id="2281d-112">Steps</span></span></th>
<th><span data-ttu-id="2281d-113">所需角色和组成员身份</span><span class="sxs-lookup"><span data-stu-id="2281d-113">Required roles and group memberships</span></span></th>
<th><span data-ttu-id="2281d-114">相关主题</span><span class="sxs-lookup"><span data-stu-id="2281d-114">Related topics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2281d-115"><strong>安装必备硬件和软件</strong></span><span class="sxs-lookup"><span data-stu-id="2281d-115"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><p><span data-ttu-id="2281d-116">在满足系统要求的硬件上安装以下内容：</span><span class="sxs-lookup"><span data-stu-id="2281d-116">On hardware that meets system requirements, install the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="2281d-117">在持久聊天服务器前端服务器上：</span><span class="sxs-lookup"><span data-stu-id="2281d-117">On the Persistent Chat Server Front End Servers:</span></span></p></li>
</ul>
<ul>
<li><p><span data-ttu-id="2281d-118">满足系统要求的操作系统</span><span class="sxs-lookup"><span data-stu-id="2281d-118">An operating system that meets system requirements</span></span></p></li>
<li><p><span data-ttu-id="2281d-119">运行 Lync Server 2013 的计算机的必备软件</span><span class="sxs-lookup"><span data-stu-id="2281d-119">Software prerequisites for computers running Lync Server 2013</span></span></p></li>
<li><p><span data-ttu-id="2281d-120">将承载持久聊天服务器数据库的服务器上的 SQL Server</span><span class="sxs-lookup"><span data-stu-id="2281d-120">SQL Server on the server that will host Persistent Chat Server database</span></span></p></li>
</ul>
<p><span data-ttu-id="2281d-121">如果需要持久聊天服务器合规性：</span><span class="sxs-lookup"><span data-stu-id="2281d-121">If Persistent Chat Server compliance is required:</span></span></p>
<ul>
<li><p><span data-ttu-id="2281d-122">将承载持久聊天服务器合规性数据库的服务器上的 SQL Server</span><span class="sxs-lookup"><span data-stu-id="2281d-122">SQL Server on the server that will host Persistent Chat Server compliance database</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="2281d-123">属于本地 Administrators 组成员的任何用户。</span><span class="sxs-lookup"><span data-stu-id="2281d-123">Any user who is a member of the local Administrators group.</span></span></p></td>
<td><p><span data-ttu-id="2281d-124">可支持性文档中<a href="lync-server-2013-supported-hardware.md">Lync Server 2013 支持的硬件</a></span><span class="sxs-lookup"><span data-stu-id="2281d-124"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="2281d-125">可支持性文档中的<a href="lync-server-2013-server-software-and-infrastructure-support.md">Lync server 2013 中的服务器软件和基础结构支持</a></span><span class="sxs-lookup"><span data-stu-id="2281d-125"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="2281d-126"><a href="lync-server-2013-determining-your-system-requirements.md">确定 Lync Server 2013 的系统要求</a></span><span class="sxs-lookup"><span data-stu-id="2281d-126"><a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="2281d-127"><a href="lync-server-2013-technical-requirements-for-persistent-chat-server.md">Lync Server 2013 中持久聊天服务器的技术要求</a></span><span class="sxs-lookup"><span data-stu-id="2281d-127"><a href="lync-server-2013-technical-requirements-for-persistent-chat-server.md">Technical requirements for Persistent Chat Server in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2281d-128"><strong>创建适当的内部拓扑以支持持久聊天服务器（也可以选择持久聊天合规性）</strong></span><span class="sxs-lookup"><span data-stu-id="2281d-128"><strong>Create the appropriate internal topology to support Persistent Chat Server (and optionally, Persistent Chat compliance)</strong></span></span></p></td>
<td><p><span data-ttu-id="2281d-129">运行拓扑生成器以将持久聊天服务器池添加到拓扑中：</span><span class="sxs-lookup"><span data-stu-id="2281d-129">Run Topology Builder to add a Persistent Chat Server pool to your topology:</span></span></p>
<ul>
<li><p><span data-ttu-id="2281d-130">将持久聊天服务器组件添加到拓扑</span><span class="sxs-lookup"><span data-stu-id="2281d-130">Add Persistent Chat Server components to the topology</span></span></p></li>
<li><p><span data-ttu-id="2281d-131">为持久聊天服务器存储创建 SQL Server 数据库（以及用于灾难恢复的备份 SQL Server）</span><span class="sxs-lookup"><span data-stu-id="2281d-131">Create a SQL Server database for the Persistent Chat Server store (and a backup SQL Server for disaster recovery)</span></span></p></li>
<li><p><span data-ttu-id="2281d-132">为持久聊天服务器文件定义新的 Lync 文件存储或使用现有的 Lync 文件存储</span><span class="sxs-lookup"><span data-stu-id="2281d-132">Define a new Lync File Store or use an existing Lync File Store for Persistent Chat Server files</span></span></p></li>
<li><p><span data-ttu-id="2281d-133">关联可将请求路由到此持久聊天服务器池的 Lync Server 2013 池</span><span class="sxs-lookup"><span data-stu-id="2281d-133">Associate the Lync Server 2013 pool that can route requests to this Persistent Chat Server pool</span></span></p></li>
</ul>
<p><span data-ttu-id="2281d-134">如果需要持久聊天合规性：</span><span class="sxs-lookup"><span data-stu-id="2281d-134">If Persistent Chat compliance is required:</span></span></p>
<ul>
<li><p><span data-ttu-id="2281d-135">添加持久聊天合规性存储</span><span class="sxs-lookup"><span data-stu-id="2281d-135">Add Persistent Chat Compliance Store</span></span></p></li>
<li><p><span data-ttu-id="2281d-136">单击 "持久聊天服务器池定义" 复选框以启用合规性</span><span class="sxs-lookup"><span data-stu-id="2281d-136">Click the Persistent Chat Server pool definition check box for enabling compliance</span></span></p></li>
<li><p><span data-ttu-id="2281d-137">发布拓扑</span><span class="sxs-lookup"><span data-stu-id="2281d-137">Publish the topology</span></span></p></li>
</ul>
<p><span data-ttu-id="2281d-138">如果在 Standard Edition 上安装持久聊天服务器，则持久聊天服务器池的完全限定域名（FQDN）必须与 Standard Edition server 相匹配，并且 SQL Server 数据库在标准版的 SQL Server Express 实例上并置。Edition 服务器</span><span class="sxs-lookup"><span data-stu-id="2281d-138">If you install Persistent Chat Server on Standard Edition, the fully qualified domain name (FQDN) of the Persistent Chat Server pool must match the Standard Edition server, and the SQL Server databases are collocated on the SQL Server Express instance on the Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="2281d-139">要定义拓扑，需要具有本地 Users 组成员身份的帐户。</span><span class="sxs-lookup"><span data-stu-id="2281d-139">To define a topology, an account that is a member of the local Users group.</span></span></p>
<p><span data-ttu-id="2281d-140">若要发布拓扑，该帐户是 Domain Admins 组和 RTCUniversalServerAdmins 组的成员，并且用户还应具有对持久聊天服务器文件的 Lync 文件存储的完全控制权限（读/写/修改）（以便拓扑生成器可以配置所需的 Dacl）。</span><span class="sxs-lookup"><span data-stu-id="2281d-140">To publish the topology, an account that is a member of the Domain Admins group and RTCUniversalServerAdmins group, and the user should also have full control permissions (read/write/modify) on the Lync File Store for Persistent Chat Server files (so that Topology Builder can configure the required DACLs).</span></span></p></td>
<td><p><span data-ttu-id="2281d-141">在部署文档中<a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">将持久聊天服务器添加到 Lync Server 2013</a>中的部署</span><span class="sxs-lookup"><span data-stu-id="2281d-141"><a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2281d-142"><strong>部署持久聊天服务器</strong></span><span class="sxs-lookup"><span data-stu-id="2281d-142"><strong>Deploy Persistent Chat Server</strong></span></span></p></td>
<td><p><span data-ttu-id="2281d-143">在运行持久聊天服务器的所有计算机上运行 Lync Server 安装程序。</span><span class="sxs-lookup"><span data-stu-id="2281d-143">Run the Lync Server setup on all the computers running Persistent Chat Server.</span></span> <span data-ttu-id="2281d-144">持久聊天服务器安装程序已集成到 Lync Server 2013 部署向导中，其中提供了以下说明：</span><span class="sxs-lookup"><span data-stu-id="2281d-144">The Persistent Chat Server setup is integrated into the Lync Server 2013 Deployment wizard that provides the following instructions:</span></span></p>
<ul>
<li><p><span data-ttu-id="2281d-145">部署本地管理存储</span><span class="sxs-lookup"><span data-stu-id="2281d-145">Deploy local management store</span></span></p></li>
<li><p><span data-ttu-id="2281d-146">安装持久聊天服务器服务</span><span class="sxs-lookup"><span data-stu-id="2281d-146">Install Persistent Chat Server services</span></span></p></li>
<li><p><span data-ttu-id="2281d-147">请求和分配证书</span><span class="sxs-lookup"><span data-stu-id="2281d-147">Request and assign certificates</span></span></p></li>
<li><p><span data-ttu-id="2281d-148">运行并启动服务</span><span class="sxs-lookup"><span data-stu-id="2281d-148">Run and start the services</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="2281d-149">属于本地 Administrators 组成员的任何用户。</span><span class="sxs-lookup"><span data-stu-id="2281d-149">Any user who is a member of the local Administrators group.</span></span></p></td>
<td><p><span data-ttu-id="2281d-150">在部署文档中的<a href="lync-server-2013-deploying-persistent-chat-server.md">Lync server 2013 中部署持久聊天服务器</a></span><span class="sxs-lookup"><span data-stu-id="2281d-150"><a href="lync-server-2013-deploying-persistent-chat-server.md">Deploying Persistent Chat Server in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2281d-151"><strong>创建持久聊天管理员</strong></span><span class="sxs-lookup"><span data-stu-id="2281d-151"><strong>Create a Persistent Chat administrator</strong></span></span></p></td>
<td><p><span data-ttu-id="2281d-152">将用户添加到 CsPersistentChatAdministrator 安全组。</span><span class="sxs-lookup"><span data-stu-id="2281d-152">Add users to the CsPersistentChatAdministrator security group.</span></span></p></td>
<td><p><span data-ttu-id="2281d-153">属于域管理员成员的任何用户。</span><span class="sxs-lookup"><span data-stu-id="2281d-153">Any user who is a member of domain administrators.</span></span></p></td>
<td><p><span data-ttu-id="2281d-154">在部署文档中的<a href="lync-server-2013-adding-a-persistent-chat-administrator.md">Lync Server 2013 中添加持久聊天管理员</a></span><span class="sxs-lookup"><span data-stu-id="2281d-154"><a href="lync-server-2013-adding-a-persistent-chat-administrator.md">Adding a Persistent Chat administrator in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2281d-155"><strong>配置持久聊天服务器</strong></span><span class="sxs-lookup"><span data-stu-id="2281d-155"><strong>Configure Persistent Chat Server</strong></span></span></p></td>
<td><p><span data-ttu-id="2281d-156">配置用户：</span><span class="sxs-lookup"><span data-stu-id="2281d-156">Configure users:</span></span></p>
<ul>
<li><p><span data-ttu-id="2281d-157">必须通过策略启用用户才能访问持久聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="2281d-157">User has to be enabled by policy to access Persistent Chat Server.</span></span> <span data-ttu-id="2281d-158">默认情况下，该策略对所有用户都处于关闭状态，并且可以在全局/站点/池/用户范围进行定义。</span><span class="sxs-lookup"><span data-stu-id="2281d-158">By default, the policy is turned off for all users and can be defined at global/site/pool/user scopes.</span></span></p></li>
<li><p><span data-ttu-id="2281d-159">配置设置</span><span class="sxs-lookup"><span data-stu-id="2281d-159">Configure settings</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="2281d-p104">用户必须是 CsPersistentChatAdministrator 的成员。要更改策略，用户必须至少属于 CsUserAdministrator。</span><span class="sxs-lookup"><span data-stu-id="2281d-p104">User must be a member of CsPersistentChatAdministrator. To change policy, user must be in CsUserAdministrator, at a minimum.</span></span></p></td>
<td><p><span data-ttu-id="2281d-162">在部署文档的<a href="lync-server-2013-configuring-persistent-chat-server.md">Lync server 2013 中配置持久聊天服务器</a></span><span class="sxs-lookup"><span data-stu-id="2281d-162"><a href="lync-server-2013-configuring-persistent-chat-server.md">Configuring Persistent Chat Server in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <span data-ttu-id="2281d-163">您可以部署一个或多个持久聊天服务器池。</span><span class="sxs-lookup"><span data-stu-id="2281d-163">You can deploy one or more Persistent Chat Server pools.</span></span> <span data-ttu-id="2281d-164">我们支持多个持久聊天服务器池的原因是，在给定区域生成的数据需要保留在该区域中的一些法规原因。</span><span class="sxs-lookup"><span data-stu-id="2281d-164">We support multiple Persistent Chat Server pools for regulatory reasons whereby data generated in a given region is required to stay in that region.</span></span> <span data-ttu-id="2281d-165">例如，如果在芝加哥部署一个持久聊天服务器池，而另一个在苏黎世中遵守了适用于瑞士的数据的规章，则用户可以在持久聊天服务器池中连接到聊天室，前提是他们有权访问。</span><span class="sxs-lookup"><span data-stu-id="2281d-165">For example, if you deploy a Persistent Chat Server pool in Chicago, and another in Zurich to comply with regulations for data in Switzerland, users can connect to rooms in both the Persistent Chat Server pools, provided they have access.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

