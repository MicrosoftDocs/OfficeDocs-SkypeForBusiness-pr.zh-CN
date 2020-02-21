---
title: Lync Server 2013：构建边缘和控制器拓扑
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Building an edge and Director topology
ms:assetid: 11e5759e-d69f-4c39-8994-f467c279c558
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398202(v=OCS.15)
ms:contentKeyID: 48183451
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be41eb547589c74b070a55325efcfd05e33f4588
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196525"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="building-an-edge-and-director-topology-in-lync-server-2013"></a><span data-ttu-id="ee30d-102">在 Lync Server 2013 中构建边缘和控制器拓扑</span><span class="sxs-lookup"><span data-stu-id="ee30d-102">Building an edge and Director topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ee30d-103">_**上次修改的主题：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="ee30d-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="ee30d-104">构建拓扑涉及以下规划和部署任务：</span><span class="sxs-lookup"><span data-stu-id="ee30d-104">Building the topology involves the following planning and deployment tasks:</span></span>

  - <span data-ttu-id="ee30d-105">**规划**   您需要为您的组织定义适当的拓扑，并确定部署它所需的组件。</span><span class="sxs-lookup"><span data-stu-id="ee30d-105">**Planning**   You need to define an appropriate topology for your organization and identify the components required to deploy it.</span></span> <span data-ttu-id="ee30d-106">这些是规划过程中的标准步骤。</span><span class="sxs-lookup"><span data-stu-id="ee30d-106">These are standard steps in the planning process.</span></span> <span data-ttu-id="ee30d-107">使用 Lync Server 2013 提供的 Microsoft Lync Server 2013 和规划工具，可以轻松地开始规划过程，也可以在要求和计划最终完成时轻松做出更改。</span><span class="sxs-lookup"><span data-stu-id="ee30d-107">The Microsoft Lync Server 2013, Planning Tool provided with Lync Server 2013 makes it easy to start the planning process, as well as including the ability to easily make changes as your requirements and plans are finalized.</span></span>

  - <span data-ttu-id="ee30d-108">**部署**   使用拓扑生成器定义的拓扑对部署任何 Lync server 2013 服务器至关重要。</span><span class="sxs-lookup"><span data-stu-id="ee30d-108">**Deployment**   The topology that you define using Topology Builder is essential to the deployment of any Lync Server 2013 server.</span></span> <span data-ttu-id="ee30d-109">如果您未在规划工作过程中使用拓扑生成器来定义和发布拓扑，则必须先完成它并发布拓扑，然后再部署边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="ee30d-109">If you do not finish defining and publishing your topology by using Topology Builder as part of your planning efforts, you must complete it and publish the topology before you deploy your Edge Servers.</span></span>

<span data-ttu-id="ee30d-110">只有在部署了至少一个内部池之后，才能部署边缘服务器组件，并且必须安装拓扑生成器才能部署内部池。</span><span class="sxs-lookup"><span data-stu-id="ee30d-110">You cannot deploy Edge Server components until you have deployed at least one internal pool, and you must install Topology Builder to deploy an internal pool.</span></span> <span data-ttu-id="ee30d-111">本节不包含拓扑生成器安装，因为这是内部池的安装过程的一部分。</span><span class="sxs-lookup"><span data-stu-id="ee30d-111">This section does not cover installation of Topology Builder because that is part of the installation process for the internal pool.</span></span>

<span data-ttu-id="ee30d-112">有关这些工具的详细信息，请参阅[Lync Server 2013 中的外部用户访问的部署清单](lync-server-2013-deployment-checklist-for-external-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="ee30d-112">For details about these tools, see [Deployment checklist for external user access in Lync Server 2013](lync-server-2013-deployment-checklist-for-external-user-access.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ee30d-113">如果您以前使用拓扑生成器定义了完整的拓扑，包括边缘拓扑，则可以跳过在<A href="lync-server-2013-define-your-edge-topology.md">Lync server 2013 中定义边缘拓扑</A>并在此部分中的<A href="lync-server-2013-publish-your-topology.md">lync server 2013 任务中发布拓扑</A>，但您确实需要完成<A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">导出 Lync Server 2013 拓扑并将其复制到外部媒体以进行边缘安装</A>任务。</span><span class="sxs-lookup"><span data-stu-id="ee30d-113">If you previously used Topology Builder to define a complete topology, including the edge topology, you do can skip the <A href="lync-server-2013-define-your-edge-topology.md">Define your edge topology in Lync Server 2013</A> and <A href="lync-server-2013-publish-your-topology.md">Publish your topology in Lync Server 2013</A> tasks in this section, but you do need to complete the <A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">Export your Lync Server 2013 topology and copy it to external media for edge installation</A> task.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ee30d-114">本部分内容</span><span class="sxs-lookup"><span data-stu-id="ee30d-114">In This Section</span></span>

  - [<span data-ttu-id="ee30d-115">在 Lync Server 2013 中定义边缘拓扑</span><span class="sxs-lookup"><span data-stu-id="ee30d-115">Define your edge topology in Lync Server 2013</span></span>](lync-server-2013-define-your-edge-topology.md)

  - [<span data-ttu-id="ee30d-116">在拓扑中为 Lync Server 2013 定义可选控制器拓扑</span><span class="sxs-lookup"><span data-stu-id="ee30d-116">Define optional Director topologies in your topology for Lync Server 2013</span></span>](lync-server-2013-define-optional-director-topologies-in-your-topology.md)

  - [<span data-ttu-id="ee30d-117">在 Lync Server 2013 中发布拓扑</span><span class="sxs-lookup"><span data-stu-id="ee30d-117">Publish your topology in Lync Server 2013</span></span>](lync-server-2013-publish-your-topology.md)

  - [<span data-ttu-id="ee30d-118">导出 Lync Server 2013 拓扑并将其复制到外部媒体以进行边缘安装</span><span class="sxs-lookup"><span data-stu-id="ee30d-118">Export your Lync Server 2013 topology and copy it to external media for edge installation</span></span>](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

