---
title: 适用于 A/V 会议的 Lync Server 2013 部署清单
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for A/V conferencing
ms:assetid: 6d47426f-6559-407b-9ac1-2453f0b7a2a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619183(v=OCS.15)
ms:contentKeyID: 49733684
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 736719475d77f67932b350e1684b4af26ca2fbd6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740782"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-av-conferencing-in-lync-server-2013"></a><span data-ttu-id="e3807-102">Lync Server 2013 中的 A/V 会议的部署清单</span><span class="sxs-lookup"><span data-stu-id="e3807-102">Deployment checklist for A/V conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3807-103">_**主题上次修改时间：** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="e3807-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="e3807-104">与其他 Lync Server 2013 组件的部署一样，部署 A/V 会议需要使用拓扑生成器创建和发布合并会议的拓扑。</span><span class="sxs-lookup"><span data-stu-id="e3807-104">As with deployment of your other Lync Server 2013 components, deployment of A/V conferencing requires that you use Topology Builder to create and publish a topology that incorporates conferencing.</span></span>

<div>

## <a name="deployment-sequence"></a><span data-ttu-id="e3807-105">部署序列</span><span class="sxs-lookup"><span data-stu-id="e3807-105">Deployment Sequence</span></span>

<span data-ttu-id="e3807-106">在部署初始拓扑时，或者在部署了至少一个前端池或标准版服务器之后，你可以部署会议。</span><span class="sxs-lookup"><span data-stu-id="e3807-106">You can deploy conferencing at the same time that you deploy your initial topology or after you have deployed at least one Front End pool or Standard Edition server.</span></span>

</div>

<div>

## <a name="conferencing-deployment-process"></a><span data-ttu-id="e3807-107">会议部署过程</span><span class="sxs-lookup"><span data-stu-id="e3807-107">Conferencing Deployment Process</span></span>

<span data-ttu-id="e3807-108">下表概述了将会议部署到现有拓扑中所需的步骤。</span><span class="sxs-lookup"><span data-stu-id="e3807-108">The following table provides an overview of the steps required to deploy conferencing into an existing topology.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e3807-109">阶段</span><span class="sxs-lookup"><span data-stu-id="e3807-109">Phase</span></span></th>
<th><span data-ttu-id="e3807-110">步骤</span><span class="sxs-lookup"><span data-stu-id="e3807-110">Steps</span></span></th>
<th><span data-ttu-id="e3807-111">角色和组成员身份</span><span class="sxs-lookup"><span data-stu-id="e3807-111">Roles and group memberships</span></span></th>
<th><span data-ttu-id="e3807-112">文档</span><span class="sxs-lookup"><span data-stu-id="e3807-112">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e3807-113"><strong>安装必备硬件和软件</strong></span><span class="sxs-lookup"><span data-stu-id="e3807-113"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><p><span data-ttu-id="e3807-114">会议在前端池和标准版服务器的前端服务器上运行。</span><span class="sxs-lookup"><span data-stu-id="e3807-114">Conferencing runs on Front End Servers of a Front End pool and Standard Edition servers.</span></span> <span data-ttu-id="e3807-115">除了需要安装这些服务器外，没有额外的软硬件要求。</span><span class="sxs-lookup"><span data-stu-id="e3807-115">It has no additional hardware or software requirements beyond what is required to install those servers.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="e3807-116">Lync Server 2013 使用 Office Web Apps 和 Office Web Apps 服务器处理 PowerPoint 演示文稿的共享和呈现。</span><span class="sxs-lookup"><span data-stu-id="e3807-116">Lync Server 2013 uses Office Web Apps and the Office Web Apps Server to handle sharing and rendering of PowerPoint presentations.</span></span> <span data-ttu-id="e3807-117">有关安装和配置 Office Web Apps 服务器的详细信息，请参阅<A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">配置与 Office web Apps server 和 Lync server 2013 的集成</A>。</span><span class="sxs-lookup"><span data-stu-id="e3807-117">For details about installing and configuring the Office Web Apps Server, see <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Configuring integration with Office Web Apps Server and Lync Server 2013</A>.</span></span>


</div></td>
<td><p><span data-ttu-id="e3807-118">属于本地 Administrators 组成员的域用户</span><span class="sxs-lookup"><span data-stu-id="e3807-118">Domain user who is a member of the local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="e3807-119">可支持文档中的<a href="lync-server-2013-supported-hardware.md">Lync Server 2013 支持的硬件</a></span><span class="sxs-lookup"><span data-stu-id="e3807-119"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="e3807-120">支持文档中的<a href="lync-server-2013-server-software-and-infrastructure-support.md">Lync server 2013 中的服务器软件和基础结构支持</a></span><span class="sxs-lookup"><span data-stu-id="e3807-120"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="e3807-121">在规划文档中<a href="lync-server-2013-determining-your-system-requirements.md">确定 Lync Server 2013 的系统要求</a>。</span><span class="sxs-lookup"><span data-stu-id="e3807-121"><a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a> in the Planning documentation.</span></span></p>
<p><span data-ttu-id="e3807-122">规划文档中<a href="lync-server-2013-technical-requirements-for-archiving.md">Lync Server 2013 中存档的技术要求</a>。</span><span class="sxs-lookup"><span data-stu-id="e3807-122"><a href="lync-server-2013-technical-requirements-for-archiving.md">Technical requirements for Archiving in Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3807-123"><strong>创建相应的内部拓扑以支持会议</strong></span><span class="sxs-lookup"><span data-stu-id="e3807-123"><strong>Create the appropriate internal topology to support conferencing</strong></span></span></p></td>
<td><p><span data-ttu-id="e3807-124">运行拓扑生成器以将会议添加到拓扑，然后发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="e3807-124">Run Topology Builder to add conferencing to the topology, and then publish the topology.</span></span></p></td>
<td><p><span data-ttu-id="e3807-125">若要定义拓扑，需具有本地 Users 组成员的帐户</span><span class="sxs-lookup"><span data-stu-id="e3807-125">To define a topology, an account that is a member of the local Users group</span></span></p>
<p><span data-ttu-id="e3807-126">若要发布拓扑，是域管理员组和 RTCUniversalServerAdmins 组的成员的帐户，并且具有对 Lync Server 2013 文件存储使用的文件共享的完全控制权限（读/写/修改），以便拓扑生成器可以配置所需的 Dacl。</span><span class="sxs-lookup"><span data-stu-id="e3807-126">To publish the topology, an account that is a member of the Domain Admins group and RTCUniversalServerAdmins group, and that has full control permissions (read/write/modify) on the file share to be used for the Lync Server 2013 file store (so that Topology Builder can configure the required DACLs)</span></span></p></td>
<td><p><span data-ttu-id="e3807-127">在部署文档中，在<a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Lync Server 2013 的拓扑生成器中定义和配置拓扑</a>。</span><span class="sxs-lookup"><span data-stu-id="e3807-127"><a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Define and configure a topology in Topology Builder for Lync Server 2013</a> in the Deployment documentation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3807-128"><strong>配置会议策略和支持</strong></span><span class="sxs-lookup"><span data-stu-id="e3807-128"><strong>Configure conferencing policies and support</strong></span></span></p></td>
<td><p><span data-ttu-id="e3807-129">使用 Lync Server 2013 控制面板或 Lync Server Management Shell 配置会议设置。</span><span class="sxs-lookup"><span data-stu-id="e3807-129">Use the Lync Server 2013 Control Panel or Lync Server Management Shell to configure conferencing settings.</span></span></p></td>
<td><p><span data-ttu-id="e3807-130">RTCUniversalServerAdmins 组（仅限 Windows PowerShell）或将用户分配到 [] 或 CSAdministrator 角色</span><span class="sxs-lookup"><span data-stu-id="e3807-130">RTCUniversalServerAdmins group (Windows PowerShell only) or assign users to the [] or CSAdministrator role</span></span></p></td>
<td><p><span data-ttu-id="e3807-131"><a href="lync-server-2013-conferencing-policies.md">Lync Server 2013 中的会议策略</a>在操作文档中。</span><span class="sxs-lookup"><span data-stu-id="e3807-131"><a href="lync-server-2013-conferencing-policies.md">Conferencing policies in Lync Server 2013</a> in the Operations documentation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e3807-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e3807-132">See Also</span></span>


[<span data-ttu-id="e3807-133">Lync Server 2013 中的会议概述</span><span class="sxs-lookup"><span data-stu-id="e3807-133">Overview of conferencing in Lync Server 2013</span></span>](lync-server-2013-overview-of-conferencing.md)  
[<span data-ttu-id="e3807-134">在 Lync Server 2013 中定义会议要求</span><span class="sxs-lookup"><span data-stu-id="e3807-134">Defining your requirements for conferencing in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

