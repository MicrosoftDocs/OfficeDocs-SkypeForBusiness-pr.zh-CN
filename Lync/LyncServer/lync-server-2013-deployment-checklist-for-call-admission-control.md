---
title: Lync Server 2013：呼叫允许控制的部署清单
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for call admission control
ms:assetid: 7e56a169-3e63-44ab-bf28-1fdeb52381c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398631(v=OCS.15)
ms:contentKeyID: 48184621
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 13d9591ad8dfed90373fedc8adfb3a3c3c44eb57
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529139"
---
# <a name="deployment-checklist-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="66c39-102">Lync Server 2013 中呼叫允许控制的部署清单</span><span class="sxs-lookup"><span data-stu-id="66c39-102">Deployment checklist for call admission control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="66c39-103">_**上次修改的主题：** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="66c39-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="66c39-104">若要有效规划呼叫允许控制 (CAC)，则需要考虑以下内容：</span><span class="sxs-lookup"><span data-stu-id="66c39-104">To plan effectively for call admission control (CAC), you need to consider the following:</span></span>

  - <span data-ttu-id="66c39-105">部署 CAC 的先决条件。</span><span class="sxs-lookup"><span data-stu-id="66c39-105">Prerequisites for deploying CAC.</span></span>

  - <span data-ttu-id="66c39-106">CAC 所需的信息以及在部署前必须做出的配置决策。</span><span class="sxs-lookup"><span data-stu-id="66c39-106">Information required for CAC and configuration decisions that you must make in advance of deployment.</span></span>

<div>

## <a name="deployment-prerequisites-for-call-admission-control"></a><span data-ttu-id="66c39-107">呼叫允许控制的部署先决条件</span><span class="sxs-lookup"><span data-stu-id="66c39-107">Deployment Prerequisites for Call Admission Control</span></span>

<span data-ttu-id="66c39-108">在部署呼叫允许控制之前，您必须已部署了 Lync Server 2013 内部服务器，包括前端池或 Standard Edition 服务器。</span><span class="sxs-lookup"><span data-stu-id="66c39-108">Before you deploy call admission control, you must already have deployed your Lync Server 2013 internal servers, including either a Front End pool or a Standard Edition server.</span></span>

</div>

<div>

## <a name="information-requirements-for-call-admission-control"></a><span data-ttu-id="66c39-109">呼叫允许控制的信息要求</span><span class="sxs-lookup"><span data-stu-id="66c39-109">Information Requirements for Call Admission Control</span></span>

<span data-ttu-id="66c39-110">下表汇总了部署呼叫允许控制的必需信息。</span><span class="sxs-lookup"><span data-stu-id="66c39-110">The following table summarizes the required information for deploying call admission control.</span></span>

### <a name="information-requirements-for-call-admission-control-deployment"></a><span data-ttu-id="66c39-111">呼叫允许控制部署的信息要求</span><span class="sxs-lookup"><span data-stu-id="66c39-111">Information Requirements for Call Admission Control Deployment</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="66c39-112">信息</span><span class="sxs-lookup"><span data-stu-id="66c39-112">Information</span></span></th>
<th><span data-ttu-id="66c39-113">所需信息的摘要</span><span class="sxs-lookup"><span data-stu-id="66c39-113">Summary of Information Required</span></span></th>
<th><span data-ttu-id="66c39-114">文档</span><span class="sxs-lookup"><span data-stu-id="66c39-114">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="66c39-115">您的组织所需的 Lync Server 功能</span><span class="sxs-lookup"><span data-stu-id="66c39-115">Lync Server capabilities required by your organization</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="66c39-116">组织支持的功能</span><span class="sxs-lookup"><span data-stu-id="66c39-116">Capabilities to be supported by your organization</span></span></p></li>
<li><p><span data-ttu-id="66c39-117">为各个用户启用的功能</span><span class="sxs-lookup"><span data-stu-id="66c39-117">Capabilities to be enabled for individual users</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="66c39-118"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">在 Lync Server 2013 中定义呼叫允许控制的要求</a></span><span class="sxs-lookup"><span data-stu-id="66c39-118"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Defining your requirements for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66c39-119">要部署的拓扑和组件</span><span class="sxs-lookup"><span data-stu-id="66c39-119">Topologies and components to be deployed</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="66c39-120">CAC 相关组件将作为 Lync Server 2013 的一部分自动安装</span><span class="sxs-lookup"><span data-stu-id="66c39-120">CAC related components are automatically installed as part of Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="66c39-121"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">在 Lync Server 2013 中定义呼叫允许控制的要求</a></span><span class="sxs-lookup"><span data-stu-id="66c39-121"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Defining your requirements for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66c39-122">系统要求</span><span class="sxs-lookup"><span data-stu-id="66c39-122">System requirements</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="66c39-123">硬件要求</span><span class="sxs-lookup"><span data-stu-id="66c39-123">Hardware requirements</span></span></p></li>
<li><p><span data-ttu-id="66c39-124">软件要求</span><span class="sxs-lookup"><span data-stu-id="66c39-124">Software requirements</span></span></p></li>
<li><p><span data-ttu-id="66c39-125">并置要求</span><span class="sxs-lookup"><span data-stu-id="66c39-125">Collocation requirements</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="66c39-126"><a href="lync-server-2013-determining-your-system-requirements.md">确定 Lync Server 2013 的系统要求</a></span><span class="sxs-lookup"><span data-stu-id="66c39-126"><a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66c39-127">基础结构要求</span><span class="sxs-lookup"><span data-stu-id="66c39-127">Infrastructure requirements</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="66c39-128">对 CAC 没有必要的特定基础结构要求</span><span class="sxs-lookup"><span data-stu-id="66c39-128">No specific infrastructure requirements are necessary for CAC</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="66c39-129"><a href="lync-server-2013-infrastructure-requirements-for-call-admission-control.md">Lync Server 2013 中呼叫允许控制的基础结构要求</a></span><span class="sxs-lookup"><span data-stu-id="66c39-129"><a href="lync-server-2013-infrastructure-requirements-for-call-admission-control.md">Infrastructure requirements for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66c39-130">网络接口要求</span><span class="sxs-lookup"><span data-stu-id="66c39-130">Network interface requirements</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="66c39-131">内部和外部接口信息</span><span class="sxs-lookup"><span data-stu-id="66c39-131">Internal and external interface information</span></span></p></li>
<li><p><span data-ttu-id="66c39-132"> (的路由信息，其中包括 <a href="https://go.microsoft.com/fwlink/p/?linkid=203149">https://go.microsoft.com/fwlink/p/?LinkId=203149</a> Microsoft Lync Server 团队的客户响应频道中有关 NextHop 博客的信息) </span><span class="sxs-lookup"><span data-stu-id="66c39-132">Routing information (including information on the NextHop blog at <a href="https://go.microsoft.com/fwlink/p/?linkid=203149">https://go.microsoft.com/fwlink/p/?LinkId=203149</a>, Microsoft Lync Server team’s customer response channel)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="66c39-133"><a href="lync-server-2013-deploying-external-user-access.md">在 Lync Server 2013 中部署外部用户访问</a></span><span class="sxs-lookup"><span data-stu-id="66c39-133"><a href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66c39-134">部署策略</span><span class="sxs-lookup"><span data-stu-id="66c39-134">Deployment strategy</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="66c39-135">部署顺序</span><span class="sxs-lookup"><span data-stu-id="66c39-135">Deployment sequence</span></span></p></li>
<li><p><span data-ttu-id="66c39-136">工作组或域</span><span class="sxs-lookup"><span data-stu-id="66c39-136">Workgroup or domain</span></span></p></li>
<li><p><span data-ttu-id="66c39-137">安全性</span><span class="sxs-lookup"><span data-stu-id="66c39-137">Security</span></span></p></li>
<li><p><span data-ttu-id="66c39-138">监控和审核</span><span class="sxs-lookup"><span data-stu-id="66c39-138">Monitoring and auditing</span></span></p></li>
<li><p><span data-ttu-id="66c39-139">硬件注意事项</span><span class="sxs-lookup"><span data-stu-id="66c39-139">Hardware considerations</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="66c39-140"><a href="lync-server-2013-best-practices-for-call-admission-control.md">Lync Server 2013 中的呼叫允许控制最佳实践</a></span><span class="sxs-lookup"><span data-stu-id="66c39-140"><a href="lync-server-2013-best-practices-for-call-admission-control.md">Best practices for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66c39-141">部署过程</span><span class="sxs-lookup"><span data-stu-id="66c39-141">Deployment process</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="66c39-142">先决条件</span><span class="sxs-lookup"><span data-stu-id="66c39-142">Prerequisites</span></span></p></li>
<li><p><span data-ttu-id="66c39-143">信息要求</span><span class="sxs-lookup"><span data-stu-id="66c39-143">Information requirements</span></span></p></li>
<li><p><span data-ttu-id="66c39-144">过程和步骤</span><span class="sxs-lookup"><span data-stu-id="66c39-144">Process and procedures</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="66c39-145"><a href="lync-server-2013-configure-call-admission-control.md">在 Lync Server 2013 中配置呼叫允许控制</a></span><span class="sxs-lookup"><span data-stu-id="66c39-145"><a href="lync-server-2013-configure-call-admission-control.md">Configure call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

