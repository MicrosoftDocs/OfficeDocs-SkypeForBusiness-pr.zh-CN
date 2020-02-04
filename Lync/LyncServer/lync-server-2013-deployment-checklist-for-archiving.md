---
title: Lync Server 2013：存档的部署清单
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for Archiving
ms:assetid: 7479734d-be01-40d9-ad82-320a09d19d04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205009(v=OCS.15)
ms:contentKeyID: 48184516
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e55e2471a71c985861c35c4ec2e07582dbfa0f23
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740752"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-archiving-in-lync-server-2013"></a><span data-ttu-id="95292-102">Lync Server 2013 中存档的部署清单</span><span class="sxs-lookup"><span data-stu-id="95292-102">Deployment checklist for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="95292-103">_**主题上次修改时间：** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="95292-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="95292-104">存档将自动安装在 Lync Server 2013 部署中的每台前端服务器上，但您仍需要对其进行设置，然后才能使用它。</span><span class="sxs-lookup"><span data-stu-id="95292-104">Archiving is automatically installed on each Front End Server in your Lync Server 2013 deployment, but you still need to set it up before you can use it.</span></span> <span data-ttu-id="95292-105">对其进行设置的步骤（如本部分所述）组成了存档的部署。</span><span class="sxs-lookup"><span data-stu-id="95292-105">The steps required to set it up, as summarized in this section, constitute the deployment of Archiving.</span></span>

<div>

## <a name="deployment-sequence"></a><span data-ttu-id="95292-106">部署序列</span><span class="sxs-lookup"><span data-stu-id="95292-106">Deployment Sequence</span></span>

<span data-ttu-id="95292-107">设置存档的方式取决于您选择的存储选项：</span><span class="sxs-lookup"><span data-stu-id="95292-107">How you set up Archiving depends on which storage option you choose:</span></span>

  - <span data-ttu-id="95292-108">如果你对部署中的所有用户使用 Microsoft Exchange 集成，则无需为你的用户配置 Lync Server 2013 存档策略。</span><span class="sxs-lookup"><span data-stu-id="95292-108">If you use Microsoft Exchange integration for all users in your deployment, you don’t need to configure Lync Server 2013 Archiving policies for your users.</span></span> <span data-ttu-id="95292-109">相反，配置 Exchange 就地保留策略以支持驻留在 Exchange 2013 上的用户的存档，并将其邮箱置于就地保留。</span><span class="sxs-lookup"><span data-stu-id="95292-109">Instead, configure your Exchange In-Place Hold policies to support archiving for users homed on Exchange 2013, with their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="95292-110">有关配置这些策略的详细信息，请参阅 Exchange 2013 产品文档。</span><span class="sxs-lookup"><span data-stu-id="95292-110">For details about configuring these policies, see the Exchange 2013 product documentation.</span></span>

  - <span data-ttu-id="95292-111">如果你不为部署中的所有用户使用 Microsoft Exchange 集成，你需要将 Lync Server 存档数据库（SQL Server 数据库）添加到你的拓扑，然后将其发布，并为你的用户配置策略和设置，然后才能为这些用户存档数据。</span><span class="sxs-lookup"><span data-stu-id="95292-111">If you do not use Microsoft Exchange integration for all users in your deployment, you need to add Lync Server Archiving databases (SQL Server databases) to your topology and then publish it, as well as configure policies and settings for your users, before you can archive data for those users.</span></span> <span data-ttu-id="95292-112">在部署初始拓扑时或在部署了至少一个前端池或标准版服务器之后，你可以部署存档数据库。</span><span class="sxs-lookup"><span data-stu-id="95292-112">You can deploy Archiving databases at the same time that you deploy your initial topology or after you have deployed at least one Front End pool or Standard Edition server.</span></span> <span data-ttu-id="95292-113">本文档介绍如何通过将存档数据库添加到现有部署来部署存档数据库。</span><span class="sxs-lookup"><span data-stu-id="95292-113">This document describes how to deploy Archiving databases by adding them to an existing deployment.</span></span>

<span data-ttu-id="95292-114">如果在一个前端池或标准版服务器中启用存档，则应为部署中的所有其他前端池和标准版服务器启用它。</span><span class="sxs-lookup"><span data-stu-id="95292-114">If you enable archiving in one Front End pool or Standard Edition server, you should enable it for all other Front End pools and Standard Edition servers in your deployment.</span></span> <span data-ttu-id="95292-115">这是因为需要存档通信内容的用户可能会受邀参加其他池中承载的组 IM 对话或会议。</span><span class="sxs-lookup"><span data-stu-id="95292-115">This is because users whose communications are required to be archived can be invited to a group IM conversation or meetings hosted on a different pool.</span></span> <span data-ttu-id="95292-116">如果承载对话或会议的池上没有启用存档，则无法存档完整会话。</span><span class="sxs-lookup"><span data-stu-id="95292-116">If archiving is not enabled on the pool where the conversation or meeting is hosted, the complete session may not be archived.</span></span> <span data-ttu-id="95292-117">在这些情况下，仍可以为启用了存档的 IM 的用户进行存档，但不能为会议内容文件以及会议加入或离开事件存档。</span><span class="sxs-lookup"><span data-stu-id="95292-117">In these cases, IMs with archiving-enabled users still can be archived, but not for conferencing content files, and conference join or leave events.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="95292-118">如果出于合规性原因，存档在你的组织中非常重要，请确保部署存档、在相应级别配置策略和其他选项，并为所有适用的用户启用它，然后再为 Lync Server 2013 启用这些用户。</span><span class="sxs-lookup"><span data-stu-id="95292-118">If archiving is critical in your organization for compliance reasons, be sure to deploy Archiving, configure policies and other options at the appropriate level, and enable it for all appropriate users, before you enable those users for Lync Server 2013.</span></span>



</div>

</div>

<div>

## <a name="archiving-deployment-process"></a><span data-ttu-id="95292-119">存档部署过程</span><span class="sxs-lookup"><span data-stu-id="95292-119">Archiving Deployment Process</span></span>

<span data-ttu-id="95292-120">下表提供在现有拓扑中部署存档所需步骤的概述。</span><span class="sxs-lookup"><span data-stu-id="95292-120">The following table provides an overview of the steps required to deploy archiving in an existing topology.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="95292-121">阶段</span><span class="sxs-lookup"><span data-stu-id="95292-121">Phase</span></span></th>
<th><span data-ttu-id="95292-122">步骤</span><span class="sxs-lookup"><span data-stu-id="95292-122">Steps</span></span></th>
<th><span data-ttu-id="95292-123">角色和组成员身份</span><span class="sxs-lookup"><span data-stu-id="95292-123">Roles and group memberships</span></span></th>
<th><span data-ttu-id="95292-124">文档</span><span class="sxs-lookup"><span data-stu-id="95292-124">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="95292-125"><strong>安装必备硬件和软件</strong></span><span class="sxs-lookup"><span data-stu-id="95292-125"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="95292-126">若要使用 Microsoft Exchange 集成（使用 Exchange 2013 存档某些或所有用户的存储），您需要一个现有的 Exchange 2013 部署。</span><span class="sxs-lookup"><span data-stu-id="95292-126">To use Microsoft Exchange integration (using Exchange 2013 for archiving storage for some or all users), you need an existing Exchange 2013 deployment.</span></span></p></li>
<li><p><span data-ttu-id="95292-127">若要使用单独的存档数据库（使用 SQL Server 数据库）来存档某些或所有用户的存储，将存储存档数据的服务器上的 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="95292-127">To use separate Archiving databases (using SQL Server databases) for archiving storage for some or all users, SQL Server on the server that will store archiving data.</span></span></p></li>
</ul>
<div>

> [!NOTE]  
> <span data-ttu-id="95292-128">存档在企业版池和标准版服务器的前端服务器上运行。</span><span class="sxs-lookup"><span data-stu-id="95292-128">Archiving runs on Front End Servers of an Enterprise pool and Standard Edition servers.</span></span> <span data-ttu-id="95292-129">除了需要安装这些服务器外，没有额外的软硬件要求。</span><span class="sxs-lookup"><span data-stu-id="95292-129">It has no additional hardware or software requirements beyond what is required to install those servers.</span></span>


</div></td>
<td><p><span data-ttu-id="95292-130">属于本地 Administrators 组成员的域用户。</span><span class="sxs-lookup"><span data-stu-id="95292-130">Domain user who is a member of the local administrators group.</span></span></p></td>
<td><p><span data-ttu-id="95292-131">可支持文档中的<a href="lync-server-2013-supported-hardware.md">Lync Server 2013 支持的硬件</a>。</span><span class="sxs-lookup"><span data-stu-id="95292-131"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability documentation.</span></span></p>
<p><span data-ttu-id="95292-132">支持文档中的<a href="lync-server-2013-server-software-and-infrastructure-support.md">Lync server 2013 中的服务器软件和基础结构支持</a>。</span><span class="sxs-lookup"><span data-stu-id="95292-132"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability documentation.</span></span></p>
<p><span data-ttu-id="95292-133">规划文档中<a href="lync-server-2013-technical-requirements-for-archiving.md">Lync Server 2013 中存档的技术要求</a>。</span><span class="sxs-lookup"><span data-stu-id="95292-133"><a href="lync-server-2013-technical-requirements-for-archiving.md">Technical requirements for Archiving in Lync Server 2013</a> in the Planning documentation.</span></span></p>
<p><span data-ttu-id="95292-134">在部署文档中，<a href="lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md">在 Lync Server 2013 中设置用于存档的系统和基础结构</a>。</span><span class="sxs-lookup"><span data-stu-id="95292-134"><a href="lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md">Setting up systems and infrastructure for Archiving in Lync Server 2013</a> in the Deployment documentation.</span></span></p>
<p><span data-ttu-id="95292-135">支持文档中的<a href="lync-server-2013-exchange-and-sharepoint-integration-support.md">Lync server 2013 中的 Exchange Server 和 SharePoint 集成支持</a>。</span><span class="sxs-lookup"><span data-stu-id="95292-135"><a href="lync-server-2013-exchange-and-sharepoint-integration-support.md">Exchange Server and SharePoint integration support in Lync Server 2013</a> in the Supportability documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95292-136"><strong>创建适当的内部拓扑以支持存档（仅在未对部署中的所有用户使用 Microsoft Exchange 集成时）</strong></span><span class="sxs-lookup"><span data-stu-id="95292-136"><strong>Create the appropriate internal topology to support archiving (only if not using Microsoft Exchange integration for all users in your deployment)</strong></span></span></p></td>
<td><p><span data-ttu-id="95292-137">运行拓扑生成器以将 Lync Server 2013 存档数据库（SQL Server 数据库）添加到拓扑，然后发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="95292-137">Run Topology Builder to add Lync Server 2013 Archiving databases (SQL Server databases) to the topology, and then publish the topology.</span></span></p></td>
<td><p><span data-ttu-id="95292-138">定义用于合并存档数据库的拓扑，该帐户是本地用户组的成员。</span><span class="sxs-lookup"><span data-stu-id="95292-138">To define a topology to incorporate Archiving databases, an account that is a member of the local users group.</span></span></p>
<p><span data-ttu-id="95292-139">若要发布拓扑，是域管理员组和 RTCUniversalServerAdmins 组的成员的帐户，并且具有对 Lync Server 2013 文件存储使用的文件共享的完全控制权限（读/写/修改），以便拓扑生成器可以配置所需的 Dacl。</span><span class="sxs-lookup"><span data-stu-id="95292-139">To publish the topology, an account that is a member of the domain admins group and RTCUniversalServerAdmins group, and that has full control permissions (read/write/modify) on the file share to be used for the Lync Server 2013 file store (so that Topology Builder can configure the required DACLs).</span></span></p></td>
<td><p><span data-ttu-id="95292-140">在部署文档中<a href="lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md">将存档数据库添加到现有 Lync Server 2013 部署</a>。</span><span class="sxs-lookup"><span data-stu-id="95292-140"><a href="lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md">Adding Archiving databases to an existing Lync Server 2013 Deployment</a> in the Deployment documentation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95292-141"><strong>配置服务器到服务器身份验证（仅当使用 Microsoft Exchange 集成时）</strong></span><span class="sxs-lookup"><span data-stu-id="95292-141"><strong>Configure server-to-server authentication (only if using Microsoft Exchange integration)</strong></span></span></p></td>
<td><p><span data-ttu-id="95292-142">将服务器配置为在 Lync Server 2013 和 Exchange 2013 之间启用身份验证。</span><span class="sxs-lookup"><span data-stu-id="95292-142">Configure servers to enable authentication between Lync Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="95292-143">我们建议在启用存档之前，运行<strong>CsExchangeStorageConnectivity testuser_sipUri-文件夹 Dumpster</strong>验证 Exchange 存档存储连接。</span><span class="sxs-lookup"><span data-stu-id="95292-143">We recommend running <strong>Test-CsExchangeStorageConnectivity testuser_sipUri –Folder Dumpster</strong> to validate Exchange Archiving storage connectivity before enabling archiving.</span></span></p></td>
<td><p><span data-ttu-id="95292-144">具有用于管理服务器上的证书的相应权限的帐户。</span><span class="sxs-lookup"><span data-stu-id="95292-144">An account with the appropriate permissions for managing certificates on the servers.</span></span></p></td>
<td><p><span data-ttu-id="95292-145">在部署文档或操作文档中<a href="lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md">管理 Lync server 2013 中的服务器到服务器身份验证（OAuth）和合作伙伴应用程序</a>。</span><span class="sxs-lookup"><span data-stu-id="95292-145"><a href="lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md">Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013</a> in the Deployment documentation or the Operations documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95292-146"><strong>配置存档策略和配置</strong></span><span class="sxs-lookup"><span data-stu-id="95292-146"><strong>Configure archiving policies and configurations</strong></span></span></p></td>
<td><p><span data-ttu-id="95292-147">配置存档，包括是否使用 Microsoft Exchange 集成、全局策略和任何网站和用户策略（不使用 Microsoft Exchange 集成进行所有数据存储）和特定的存档选项（如关键模式和数据）导出和清除。</span><span class="sxs-lookup"><span data-stu-id="95292-147">Configure archiving, including whether to use Microsoft Exchange integration, the global policy and any site and user policies (when not using Microsoft Exchange integration for all data storage), and specific archiving options, such as critical mode and data export and purging.</span></span></p>
<p><span data-ttu-id="95292-148">如果使用 Microsoft Exchange 集成，请根据需要配置 Exchange 就地保留策略。</span><span class="sxs-lookup"><span data-stu-id="95292-148">If using Microsoft Exchange integration, configure Exchange In-Place Hold policies as appropriate.</span></span></p></td>
<td><p><span data-ttu-id="95292-149">RTCUniversalServerAdmins 组（仅限于 Windows PowerShell）或向 CSArchivingAdministrator 或 CSAdministrator 角色分配用户。</span><span class="sxs-lookup"><span data-stu-id="95292-149">RTCUniversalServerAdmins group (Windows PowerShell only) or assign users to the CSArchivingAdministrator or CSAdministrator role.</span></span></p></td>
<td><p><span data-ttu-id="95292-150">在部署文档中<a href="lync-server-2013-configuring-support-for-archiving.md">配置 Lync Server 2013 中的存档支持</a>。</span><span class="sxs-lookup"><span data-stu-id="95292-150"><a href="lync-server-2013-configuring-support-for-archiving.md">Configuring support for Archiving in Lync Server 2013</a> in the Deployment documentation.</span></span></p>
<p><span data-ttu-id="95292-151">Exchange 产品文档（如果使用的是 Microsoft Exchange 集成）。</span><span class="sxs-lookup"><span data-stu-id="95292-151">Exchange product documentation (if using Microsoft Exchange integration).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="deploying-lync-server-and-microsoft-exchange-in-different-forests"></a><span data-ttu-id="95292-152">在不同的林中部署 Lync Server 和 Microsoft Exchange</span><span class="sxs-lookup"><span data-stu-id="95292-152">Deploying Lync Server and Microsoft Exchange in Different Forests</span></span>

<span data-ttu-id="95292-153">如果 Microsoft Exchange Server 未在 Lync Server 所在的林中部署，则必须确保以下 Exchange Active Directory 属性已同步到部署 Lync Server 的林：</span><span class="sxs-lookup"><span data-stu-id="95292-153">If Microsoft Exchange Server is not deployed in the same forest as Lync Server, you must make sure that the following Exchange Active Directory attributes are synchronized to the forest where Lync Server is deployed:</span></span>

1.  <span data-ttu-id="95292-154">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="95292-154">msExchUserHoldPolicies</span></span>

2.  <span data-ttu-id="95292-155">proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="95292-155">proxyAddresses</span></span>

<span data-ttu-id="95292-p107">这是一个多值属性。在同步此属性时，需要合并各个值（而不是将其替换）以确保现有值不会丢失。</span><span class="sxs-lookup"><span data-stu-id="95292-p107">This is a multi-value attribute. When synchronizing this attribute, you need to merge the values, not replace them to ensure the existing values are not lost.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

