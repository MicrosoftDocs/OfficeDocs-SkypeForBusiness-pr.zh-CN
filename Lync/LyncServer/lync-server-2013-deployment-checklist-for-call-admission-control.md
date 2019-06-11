---
title: Lync Server 2013：呼叫允许控制的部署清单
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment checklist for call admission control
ms:assetid: 7e56a169-3e63-44ab-bf28-1fdeb52381c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398631(v=OCS.15)
ms:contentKeyID: 48184621
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3dd425d53a282cc24fed8ad2f8be9acc5bf42209
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830503"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="9b222-102">Lync Server 2013 中呼叫允许控制的部署清单</span><span class="sxs-lookup"><span data-stu-id="9b222-102">Deployment checklist for call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9b222-103">_**主题上次修改时间:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="9b222-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="9b222-104">要有效规划呼叫许可控制 (CAC), 需要考虑以下事项:</span><span class="sxs-lookup"><span data-stu-id="9b222-104">To plan effectively for call admission control (CAC), you need to consider the following:</span></span>

  - <span data-ttu-id="9b222-105">部署 CAC 的先决条件。</span><span class="sxs-lookup"><span data-stu-id="9b222-105">Prerequisites for deploying CAC.</span></span>

  - <span data-ttu-id="9b222-106">在部署之前必须进行的 CAC 和配置决策所需的信息。</span><span class="sxs-lookup"><span data-stu-id="9b222-106">Information required for CAC and configuration decisions that you must make in advance of deployment.</span></span>

<div>

## <a name="deployment-prerequisites-for-call-admission-control"></a><span data-ttu-id="9b222-107">呼叫许可控制的部署先决条件</span><span class="sxs-lookup"><span data-stu-id="9b222-107">Deployment Prerequisites for Call Admission Control</span></span>

<span data-ttu-id="9b222-108">在部署 "呼叫许可控制" 之前, 您必须已部署了 Lync Server 2013 内部服务器, 包括 "前端" 池或标准版服务器。</span><span class="sxs-lookup"><span data-stu-id="9b222-108">Before you deploy call admission control, you must already have deployed your Lync Server 2013 internal servers, including either a Front End pool or a Standard Edition server.</span></span>

</div>

<div>

## <a name="information-requirements-for-call-admission-control"></a><span data-ttu-id="9b222-109">呼叫许可控制的信息要求</span><span class="sxs-lookup"><span data-stu-id="9b222-109">Information Requirements for Call Admission Control</span></span>

<span data-ttu-id="9b222-110">下表总结了部署 "呼叫许可控制" 所需的信息。</span><span class="sxs-lookup"><span data-stu-id="9b222-110">The following table summarizes the required information for deploying call admission control.</span></span>

### <a name="information-requirements-for-call-admission-control-deployment"></a><span data-ttu-id="9b222-111">呼叫许可控制部署的信息要求</span><span class="sxs-lookup"><span data-stu-id="9b222-111">Information Requirements for Call Admission Control Deployment</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9b222-112">信息</span><span class="sxs-lookup"><span data-stu-id="9b222-112">Information</span></span></th>
<th><span data-ttu-id="9b222-113">所需信息摘要</span><span class="sxs-lookup"><span data-stu-id="9b222-113">Summary of Information Required</span></span></th>
<th><span data-ttu-id="9b222-114">文档</span><span class="sxs-lookup"><span data-stu-id="9b222-114">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9b222-115">您的组织所需的 Lync 服务器功能</span><span class="sxs-lookup"><span data-stu-id="9b222-115">Lync Server capabilities required by your organization</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="9b222-116">您的组织支持的功能</span><span class="sxs-lookup"><span data-stu-id="9b222-116">Capabilities to be supported by your organization</span></span></p></li>
<li><p><span data-ttu-id="9b222-117">为单个用户启用的功能</span><span class="sxs-lookup"><span data-stu-id="9b222-117">Capabilities to be enabled for individual users</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="9b222-118"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">在 Lync Server 2013 中定义呼叫允许控制要求</a></span><span class="sxs-lookup"><span data-stu-id="9b222-118"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Defining your requirements for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b222-119">要部署的拓扑和组件</span><span class="sxs-lookup"><span data-stu-id="9b222-119">Topologies and components to be deployed</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="9b222-120">CAC 相关组件将作为 Lync Server 2013 的一部分自动安装</span><span class="sxs-lookup"><span data-stu-id="9b222-120">CAC related components are automatically installed as part of Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="9b222-121"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">在 Lync Server 2013 中定义呼叫允许控制要求</a></span><span class="sxs-lookup"><span data-stu-id="9b222-121"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Defining your requirements for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b222-122">系统要求</span><span class="sxs-lookup"><span data-stu-id="9b222-122">System requirements</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="9b222-123">硬件要求</span><span class="sxs-lookup"><span data-stu-id="9b222-123">Hardware requirements</span></span></p></li>
<li><p><span data-ttu-id="9b222-124">软件要求</span><span class="sxs-lookup"><span data-stu-id="9b222-124">Software requirements</span></span></p></li>
<li><p><span data-ttu-id="9b222-125">Collocation 要求</span><span class="sxs-lookup"><span data-stu-id="9b222-125">Collocation requirements</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="9b222-126"><a href="lync-server-2013-determining-your-system-requirements.md">确定 Lync Server 2013 的系统要求</a></span><span class="sxs-lookup"><span data-stu-id="9b222-126"><a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b222-127">基础结构要求</span><span class="sxs-lookup"><span data-stu-id="9b222-127">Infrastructure requirements</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="9b222-128">CAC 不需要特定的基础结构要求</span><span class="sxs-lookup"><span data-stu-id="9b222-128">No specific infrastructure requirements are necessary for CAC</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="9b222-129"><a href="lync-server-2013-infrastructure-requirements-for-call-admission-control.md">Lync Server 2013 中呼叫允许控制的基础结构要求</a></span><span class="sxs-lookup"><span data-stu-id="9b222-129"><a href="lync-server-2013-infrastructure-requirements-for-call-admission-control.md">Infrastructure requirements for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b222-130">网络接口要求</span><span class="sxs-lookup"><span data-stu-id="9b222-130">Network interface requirements</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="9b222-131">内部和外部接口信息</span><span class="sxs-lookup"><span data-stu-id="9b222-131">Internal and external interface information</span></span></p></li>
<li><p><span data-ttu-id="9b222-132">路由信息 (包括有关在 Microsoft Lync 服务器团队<a href="http://go.microsoft.com/fwlink/p/?linkid=203149">http://go.microsoft.com/fwlink/p/?LinkId=203149</a>的客户响应频道上的 NextHop 博客的信息)</span><span class="sxs-lookup"><span data-stu-id="9b222-132">Routing information (including information on the NextHop blog at <a href="http://go.microsoft.com/fwlink/p/?linkid=203149">http://go.microsoft.com/fwlink/p/?LinkId=203149</a>, Microsoft Lync Server team’s customer response channel)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="9b222-133"><a href="lync-server-2013-deploying-external-user-access.md">在 Lync Server 2013 中部署外部用户访问</a></span><span class="sxs-lookup"><span data-stu-id="9b222-133"><a href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b222-134">部署策略</span><span class="sxs-lookup"><span data-stu-id="9b222-134">Deployment strategy</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="9b222-135">部署序列</span><span class="sxs-lookup"><span data-stu-id="9b222-135">Deployment sequence</span></span></p></li>
<li><p><span data-ttu-id="9b222-136">工作组或域</span><span class="sxs-lookup"><span data-stu-id="9b222-136">Workgroup or domain</span></span></p></li>
<li><p><span data-ttu-id="9b222-137">安全性</span><span class="sxs-lookup"><span data-stu-id="9b222-137">Security</span></span></p></li>
<li><p><span data-ttu-id="9b222-138">监视和审核</span><span class="sxs-lookup"><span data-stu-id="9b222-138">Monitoring and auditing</span></span></p></li>
<li><p><span data-ttu-id="9b222-139">硬件注意事项</span><span class="sxs-lookup"><span data-stu-id="9b222-139">Hardware considerations</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="9b222-140"><a href="lync-server-2013-best-practices-for-call-admission-control.md">Lync Server 2013 中呼叫允许控制的最佳做法</a></span><span class="sxs-lookup"><span data-stu-id="9b222-140"><a href="lync-server-2013-best-practices-for-call-admission-control.md">Best practices for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b222-141">部署过程</span><span class="sxs-lookup"><span data-stu-id="9b222-141">Deployment process</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="9b222-142">先决条件</span><span class="sxs-lookup"><span data-stu-id="9b222-142">Prerequisites</span></span></p></li>
<li><p><span data-ttu-id="9b222-143">信息要求</span><span class="sxs-lookup"><span data-stu-id="9b222-143">Information requirements</span></span></p></li>
<li><p><span data-ttu-id="9b222-144">流程和过程</span><span class="sxs-lookup"><span data-stu-id="9b222-144">Process and procedures</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="9b222-145"><a href="lync-server-2013-configure-call-admission-control.md">在 Lync Server 2013 中配置呼叫许可控制</a></span><span class="sxs-lookup"><span data-stu-id="9b222-145"><a href="lync-server-2013-configure-call-admission-control.md">Configure call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

