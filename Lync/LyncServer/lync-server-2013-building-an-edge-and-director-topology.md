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
ms.openlocfilehash: 9f8a86d4f80b7fb4fc9990911908ef0c8a317c98
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741782"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="building-an-edge-and-director-topology-in-lync-server-2013"></a>在 Lync Server 2013 中构建边缘和控制器拓扑

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-09-08_

构建拓扑涉及以下规划和部署任务：

  - **规划**   你需要为你的组织定义合适的拓扑，并确定部署该拓扑所需的组件。 这些是规划流程中的标准步骤。 Lync Server 2013 提供的 Microsoft Lync Server 2013、计划工具使你能够轻松地开始规划过程，以及如何在你的要求和计划完成后轻松进行更改。

  - **部署**   使用拓扑生成器定义的拓扑对于部署任何 Lync server 2013 服务器非常重要。 如果你未通过在计划工作中使用拓扑生成器来完成定义和发布拓扑，则必须先完成它并发布拓扑，然后再部署你的 Edge 服务器。

只有在部署了至少一个内部池后才能部署 Edge 服务器组件，并且必须安装拓扑生成器才能部署内部池。 本节不介绍拓扑生成器的安装，因为它是内部池安装过程的一部分。

有关这些工具的详细信息，请参阅[Lync Server 2013 中的外部用户访问的部署清单](lync-server-2013-deployment-checklist-for-external-user-access.md)。

<div>


> [!NOTE]  
> 如果你以前使用拓扑生成器定义完整拓扑（包括边缘拓扑），则可以跳过<A href="lync-server-2013-define-your-edge-topology.md">在 Lync server 2013 中定义 edge 拓扑</A>并在此部分中的<A href="lync-server-2013-publish-your-topology.md">Lync server 2013 任务中发布你的拓扑</A>，但你需要完成<A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">导出 Lync Server 2013 拓扑并将其复制到外部媒体以进行边缘安装</A>任务。



</div>

<div>

## <a name="in-this-section"></a>本节内容

  - [在 Lync Server 2013 中定义边缘拓扑](lync-server-2013-define-your-edge-topology.md)

  - [针对 Lync Server 2013 在拓扑中定义可选控制器拓扑](lync-server-2013-define-optional-director-topologies-in-your-topology.md)

  - [在 Lync Server 2013 中发布拓扑](lync-server-2013-publish-your-topology.md)

  - [导出 Lync Server 2013 拓扑并将其复制到外部媒体以用于边缘安装](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

