---
title: Lync Server 2013：存档的部署清单
description: Lync Server 2013：存档的部署清单。
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
ms.openlocfilehash: 0e9fb3085950aa1e8a750d36a0aeb8592bc18113
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557708"
---
# <a name="deployment-checklist-for-archiving-in-lync-server-2013"></a><span data-ttu-id="14f47-103">Lync Server 2013 中存档的部署清单</span><span class="sxs-lookup"><span data-stu-id="14f47-103">Deployment checklist for Archiving in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="14f47-104">_**上次修改的主题：** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="14f47-104">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="14f47-105">存档将自动安装在 Lync Server 2013 部署中的每台前端服务器上，但您仍需要对其进行设置，然后才能使用它。</span><span class="sxs-lookup"><span data-stu-id="14f47-105">Archiving is automatically installed on each Front End Server in your Lync Server 2013 deployment, but you still need to set it up before you can use it.</span></span> <span data-ttu-id="14f47-106">本节中总结了设置存档所需的步骤，这些步骤构成了存档的部署。</span><span class="sxs-lookup"><span data-stu-id="14f47-106">The steps required to set it up, as summarized in this section, constitute the deployment of Archiving.</span></span>

<div>

## <a name="deployment-sequence"></a><span data-ttu-id="14f47-107">部署顺序</span><span class="sxs-lookup"><span data-stu-id="14f47-107">Deployment Sequence</span></span>

<span data-ttu-id="14f47-108">设置存档的方式取决于您所选的存储选项：</span><span class="sxs-lookup"><span data-stu-id="14f47-108">How you set up Archiving depends on which storage option you choose:</span></span>

  - <span data-ttu-id="14f47-109">如果对部署中的所有用户使用 Microsoft Exchange 集成，则无需为用户配置 Lync Server 2013 存档策略。</span><span class="sxs-lookup"><span data-stu-id="14f47-109">If you use Microsoft Exchange integration for all users in your deployment, you don’t need to configure Lync Server 2013 Archiving policies for your users.</span></span> <span data-ttu-id="14f47-110">相反，请将 Exchange In-Place 保留策略配置为支持驻留在 Exchange 2013 上的用户的存档，并将其邮箱置于 In-Place 保留状态。</span><span class="sxs-lookup"><span data-stu-id="14f47-110">Instead, configure your Exchange In-Place Hold policies to support archiving for users homed on Exchange 2013, with their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="14f47-111">有关配置这些策略的详细信息，请参阅 Exchange 2013 产品文档。</span><span class="sxs-lookup"><span data-stu-id="14f47-111">For details about configuring these policies, see the Exchange 2013 product documentation.</span></span>

  - <span data-ttu-id="14f47-112">如果您不在部署中对所有用户使用 Microsoft Exchange 集成，则需要将 Lync Server 存档数据库添加 (SQL Server 数据库) 到拓扑，然后发布该数据库，并为用户配置策略和设置，然后才能存档这些用户的数据。</span><span class="sxs-lookup"><span data-stu-id="14f47-112">If you do not use Microsoft Exchange integration for all users in your deployment, you need to add Lync Server Archiving databases (SQL Server databases) to your topology and then publish it, as well as configure policies and settings for your users, before you can archive data for those users.</span></span> <span data-ttu-id="14f47-113">可以在部署初始拓扑的同时部署存档数据库，或在部署了至少一个前端池或 Standard Edition 服务器之后部署存档数据库。</span><span class="sxs-lookup"><span data-stu-id="14f47-113">You can deploy Archiving databases at the same time that you deploy your initial topology or after you have deployed at least one Front End pool or Standard Edition server.</span></span> <span data-ttu-id="14f47-114">本文档介绍如何通过将存档数据库添加到现有部署中来部署这些数据库。</span><span class="sxs-lookup"><span data-stu-id="14f47-114">This document describes how to deploy Archiving databases by adding them to an existing deployment.</span></span>

<span data-ttu-id="14f47-p104">如果在一个前端池或 Standard Edition 服务器中启用存档，则应为部署中的所有其他前端池和 Standard Edition 服务器启用存档。这是因为需要存档通信内容的用户可能会受邀参加其他池中承载的组 IM 对话或会议。如果承载对话或会议的池上没有启用存档，则无法存档完整会话。在这些情况下，仍可以为启用了存档的 IM 的用户进行存档，但不能为会议内容文件以及会议加入或离开事件存档。</span><span class="sxs-lookup"><span data-stu-id="14f47-p104">If you enable archiving in one Front End pool or Standard Edition server, you should enable it for all other Front End pools and Standard Edition servers in your deployment. This is because users whose communications are required to be archived can be invited to a group IM conversation or meetings hosted on a different pool. If archiving is not enabled on the pool where the conversation or meeting is hosted, the complete session may not be archived. In these cases, IMs with archiving-enabled users still can be archived, but not for conferencing content files, and conference join or leave events.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="14f47-119">如果出于合规性原因，存档在您的组织中至关重要，请务必部署存档、在适当的级别配置策略和其他选项，并为所有适当的用户启用该策略，然后再为这些用户启用 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="14f47-119">If archiving is critical in your organization for compliance reasons, be sure to deploy Archiving, configure policies and other options at the appropriate level, and enable it for all appropriate users, before you enable those users for Lync Server 2013.</span></span>



</div>

</div>

<div>

## <a name="archiving-deployment-process"></a><span data-ttu-id="14f47-120">存档部署过程</span><span class="sxs-lookup"><span data-stu-id="14f47-120">Archiving Deployment Process</span></span>

<span data-ttu-id="14f47-121">下表提供在现有拓扑中部署存档所需步骤的概述。</span><span class="sxs-lookup"><span data-stu-id="14f47-121">The following table provides an overview of the steps required to deploy archiving in an existing topology.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="14f47-122">阶段</span><span class="sxs-lookup"><span data-stu-id="14f47-122">Phase</span></span></th>
<th><span data-ttu-id="14f47-123">步骤</span><span class="sxs-lookup"><span data-stu-id="14f47-123">Steps</span></span></th>
<th><span data-ttu-id="14f47-124">角色和组成员身份</span><span class="sxs-lookup"><span data-stu-id="14f47-124">Roles and group memberships</span></span></th>
<th><span data-ttu-id="14f47-125">文档</span><span class="sxs-lookup"><span data-stu-id="14f47-125">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="14f47-126"><strong>安装必备软硬件</strong></span><span class="sxs-lookup"><span data-stu-id="14f47-126"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="14f47-127">若要使用 Microsoft Exchange 集成 (使用 Exchange 2013 存档) 的部分或所有用户的存储，需要一个现有的 Exchange 2013 部署。</span><span class="sxs-lookup"><span data-stu-id="14f47-127">To use Microsoft Exchange integration (using Exchange 2013 for archiving storage for some or all users), you need an existing Exchange 2013 deployment.</span></span></p></li>
<li><p><span data-ttu-id="14f47-128">若要使用单独的存档数据库（使用 SQL Server 数据库）为部分或所有用户进行存档存储，需要将存储存档数据的服务器上的 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="14f47-128">To use separate Archiving databases (using SQL Server databases) for archiving storage for some or all users, SQL Server on the server that will store archiving data.</span></span></p></li>
</ul>
<div>

> [!NOTE]  
> <span data-ttu-id="14f47-p105">存档在企业池的前端服务器和 Standard Edition 服务器上运行。除了需要安装这些服务器外，没有额外的软硬件要求。</span><span class="sxs-lookup"><span data-stu-id="14f47-p105">Archiving runs on Front End Servers of an Enterprise pool and Standard Edition servers. It has no additional hardware or software requirements beyond what is required to install those servers.</span></span>


</div></td>
<td><p><span data-ttu-id="14f47-131">属于本地 Administrators 组成员的域用户。</span><span class="sxs-lookup"><span data-stu-id="14f47-131">Domain user who is a member of the local administrators group.</span></span></p></td>
<td><p><span data-ttu-id="14f47-132">可支持性文档中的<a href="lync-server-2013-supported-hardware.md">Lync Server 2013 支持的硬件</a>。</span><span class="sxs-lookup"><span data-stu-id="14f47-132"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability documentation.</span></span></p>
<p><span data-ttu-id="14f47-133">可支持性文档中的<a href="lync-server-2013-server-software-and-infrastructure-support.md">Lync server 2013 中的服务器软件和基础结构支持</a>。</span><span class="sxs-lookup"><span data-stu-id="14f47-133"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability documentation.</span></span></p>
<p><span data-ttu-id="14f47-134">在规划文档中的<a href="lync-server-2013-technical-requirements-for-archiving.md">Lync Server 2013 中存档的技术要求</a>。</span><span class="sxs-lookup"><span data-stu-id="14f47-134"><a href="lync-server-2013-technical-requirements-for-archiving.md">Technical requirements for Archiving in Lync Server 2013</a> in the Planning documentation.</span></span></p>
<p><span data-ttu-id="14f47-135">部署文档中的在<a href="lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md">Lync Server 2013 中设置用于存档的系统和基础结构</a>。</span><span class="sxs-lookup"><span data-stu-id="14f47-135"><a href="lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md">Setting up systems and infrastructure for Archiving in Lync Server 2013</a> in the Deployment documentation.</span></span></p>
<p><span data-ttu-id="14f47-136">可支持性文档中的<a href="lync-server-2013-exchange-and-sharepoint-integration-support.md">Lync server 2013 中的 Exchange Server 和 SharePoint 集成支持</a>。</span><span class="sxs-lookup"><span data-stu-id="14f47-136"><a href="lync-server-2013-exchange-and-sharepoint-integration-support.md">Exchange Server and SharePoint integration support in Lync Server 2013</a> in the Supportability documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14f47-137"><strong>创建适当的内部拓扑，以支持仅当不为部署中的所有用户使用 Microsoft Exchange 集成时 (存档) </strong></span><span class="sxs-lookup"><span data-stu-id="14f47-137"><strong>Create the appropriate internal topology to support archiving (only if not using Microsoft Exchange integration for all users in your deployment)</strong></span></span></p></td>
<td><p><span data-ttu-id="14f47-138">运行拓扑生成器以将 Lync Server 2013 存档数据库 (SQL Server 数据库) 到拓扑，然后发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="14f47-138">Run Topology Builder to add Lync Server 2013 Archiving databases (SQL Server databases) to the topology, and then publish the topology.</span></span></p></td>
<td><p><span data-ttu-id="14f47-139">要定义拓扑以包含存档数据库，需具有作为本地用户组的成员的帐户。</span><span class="sxs-lookup"><span data-stu-id="14f47-139">To define a topology to incorporate Archiving databases, an account that is a member of the local users group.</span></span></p>
<p><span data-ttu-id="14f47-140">若要发布拓扑，该帐户是 domain admins 组和 RTCUniversalServerAdmins 组的成员，并且具有对用于 Lync Server 2013 文件 (存储的文件共享上的完全控制权限 (读/写/修改) ，以便拓扑生成器可以配置所需的 Dacl) 。</span><span class="sxs-lookup"><span data-stu-id="14f47-140">To publish the topology, an account that is a member of the domain admins group and RTCUniversalServerAdmins group, and that has full control permissions (read/write/modify) on the file share to be used for the Lync Server 2013 file store (so that Topology Builder can configure the required DACLs).</span></span></p></td>
<td><p><span data-ttu-id="14f47-141">在部署文档中<a href="lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md">将存档数据库添加到现有 Lync Server 2013 部署</a>中。</span><span class="sxs-lookup"><span data-stu-id="14f47-141"><a href="lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md">Adding Archiving databases to an existing Lync Server 2013 Deployment</a> in the Deployment documentation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14f47-142"><strong>仅在使用 Microsoft Exchange 集成时配置服务器到服务器身份验证 () </strong></span><span class="sxs-lookup"><span data-stu-id="14f47-142"><strong>Configure server-to-server authentication (only if using Microsoft Exchange integration)</strong></span></span></p></td>
<td><p><span data-ttu-id="14f47-143">将服务器配置为在 Lync Server 2013 与 Exchange 2013 之间启用身份验证。</span><span class="sxs-lookup"><span data-stu-id="14f47-143">Configure servers to enable authentication between Lync Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="14f47-144">我们建议在启用存档之前，运行 <strong>CsExchangeStorageConnectivity testuser_sipUri – Folder 转储程序</strong> 以验证 Exchange 存档存储连接。</span><span class="sxs-lookup"><span data-stu-id="14f47-144">We recommend running <strong>Test-CsExchangeStorageConnectivity testuser_sipUri –Folder Dumpster</strong> to validate Exchange Archiving storage connectivity before enabling archiving.</span></span></p></td>
<td><p><span data-ttu-id="14f47-145">具有用于管理服务器上的证书的相应权限的帐户。</span><span class="sxs-lookup"><span data-stu-id="14f47-145">An account with the appropriate permissions for managing certificates on the servers.</span></span></p></td>
<td><p><span data-ttu-id="14f47-146">在部署文档或操作文档中<a href="lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md">管理 Lync server 2013 中的服务器到服务器身份验证 (OAuth) 和合作伙伴应用程序</a>。</span><span class="sxs-lookup"><span data-stu-id="14f47-146"><a href="lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md">Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013</a> in the Deployment documentation or the Operations documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14f47-147"><strong>配置存档策略和配置</strong></span><span class="sxs-lookup"><span data-stu-id="14f47-147"><strong>Configure archiving policies and configurations</strong></span></span></p></td>
<td><p><span data-ttu-id="14f47-148">配置存档，包括是否使用 Microsoft Exchange 集成、全局策略和任何站点和用户策略 (不将 Microsoft Exchange 集成用于所有数据存储) ，以及特定的存档选项（如关键模式和数据导出和清除）。</span><span class="sxs-lookup"><span data-stu-id="14f47-148">Configure archiving, including whether to use Microsoft Exchange integration, the global policy and any site and user policies (when not using Microsoft Exchange integration for all data storage), and specific archiving options, such as critical mode and data export and purging.</span></span></p>
<p><span data-ttu-id="14f47-149">如果使用 Microsoft Exchange 集成，请根据需要配置 Exchange In-Place 保留策略。</span><span class="sxs-lookup"><span data-stu-id="14f47-149">If using Microsoft Exchange integration, configure Exchange In-Place Hold policies as appropriate.</span></span></p></td>
<td><p><span data-ttu-id="14f47-150">RTCUniversalServerAdmins 组（仅限于 Windows PowerShell）或向 CSArchivingAdministrator 或 CSAdministrator 角色分配用户。</span><span class="sxs-lookup"><span data-stu-id="14f47-150">RTCUniversalServerAdmins group (Windows PowerShell only) or assign users to the CSArchivingAdministrator or CSAdministrator role.</span></span></p></td>
<td><p><span data-ttu-id="14f47-151">在部署文档中<a href="lync-server-2013-configuring-support-for-archiving.md">配置对 Lync Server 2013 存档的支持</a>。</span><span class="sxs-lookup"><span data-stu-id="14f47-151"><a href="lync-server-2013-configuring-support-for-archiving.md">Configuring support for Archiving in Lync Server 2013</a> in the Deployment documentation.</span></span></p>
<p><span data-ttu-id="14f47-152">如果使用 Microsoft Exchange 集成) ，则为 Exchange 产品文档 (。</span><span class="sxs-lookup"><span data-stu-id="14f47-152">Exchange product documentation (if using Microsoft Exchange integration).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="deploying-lync-server-and-microsoft-exchange-in-different-forests"></a><span data-ttu-id="14f47-153">在不同林中部署 Lync Server 和 Microsoft Exchange</span><span class="sxs-lookup"><span data-stu-id="14f47-153">Deploying Lync Server and Microsoft Exchange in Different Forests</span></span>

<span data-ttu-id="14f47-154">如果 Microsoft Exchange Server 未部署在与 Lync Server 相同的林中，则必须确保将以下 Exchange Active Directory 属性同步到部署 Lync Server 的林：</span><span class="sxs-lookup"><span data-stu-id="14f47-154">If Microsoft Exchange Server is not deployed in the same forest as Lync Server, you must make sure that the following Exchange Active Directory attributes are synchronized to the forest where Lync Server is deployed:</span></span>

1.  <span data-ttu-id="14f47-155">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="14f47-155">msExchUserHoldPolicies</span></span>

2.  <span data-ttu-id="14f47-156">proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="14f47-156">proxyAddresses</span></span>

<span data-ttu-id="14f47-p107">这是一个多值属性。在同步此属性时，需要合并各个值（而不是将其替换）以确保现有值不会丢失。</span><span class="sxs-lookup"><span data-stu-id="14f47-p107">This is a multi-value attribute. When synchronizing this attribute, you need to merge the values, not replace them to ensure the existing values are not lost.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

