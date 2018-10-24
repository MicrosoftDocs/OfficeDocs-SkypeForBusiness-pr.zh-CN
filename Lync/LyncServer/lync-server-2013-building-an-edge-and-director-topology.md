---
title: Lync Server 2013：构建边缘和控制器拓扑
TOCTitle: 构建边缘和控制器拓扑
ms:assetid: 11e5759e-d69f-4c39-8994-f467c279c558
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398202(v=OCS.15)
ms:contentKeyID: 49312049
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中构建边缘和控制器拓扑

 

_**上一次修改主题：** 2012-09-08_

构建拓扑涉及以下规划和部署任务：

  - **规划** 需要为您的组织定义相应的拓扑并标识部署该拓扑所需的组件。这些是规划过程中的标准步骤。使用 Microsoft Lync Server 2013（随 Lync Server 2013 提供的 规划工具），您可以轻松地开始规划过程，包括在最终确定要求和计划后能够轻松地进行更改。

  - **部署** 使用 拓扑生成器定义的拓扑对任何 Lync Server 2013 服务器的部署都是必不可少的。如果在规划过程中未使用 拓扑生成器完成拓扑的定义和发布，则您必须在部署边缘服务器之前完成此操作并发布拓扑。

至少部署一个内部池后才能部署边缘服务器组件，而且必须安装 拓扑生成器后才能部署内部池。本节不涉及 拓扑生成器的安装，因为那属于内部池的安装过程。

有关这些工具的详细信息，请参阅[Lync Server 2013 中外部用户访问的部署清单](lync-server-2013-deployment-checklist-for-external-user-access.md)。

> [!NOTE]  
> 如果以前已使用 拓扑生成器定义完整的拓扑（包括边缘拓扑），则可以跳过本节中的 <a href="lync-server-2013-define-your-edge-topology.md">在 Lync Server 2013 中定义边缘拓扑</a>和 <a href="lync-server-2013-publish-your-topology.md">在 Lync Server 2013 中发布拓扑</a>任务，但需要完成 <a href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">导出 Lync Server 2013 拓扑并将其复制到外部媒体以用于边缘安装</a>任务。



## 本部分内容

  - [在 Lync Server 2013 中定义边缘拓扑](lync-server-2013-define-your-edge-topology.md)

  - [针对 Lync Server 2013 在拓扑中定义可选控制器拓扑](lync-server-2013-define-optional-director-topologies-in-your-topology.md)

  - [在 Lync Server 2013 中发布拓扑](lync-server-2013-publish-your-topology.md)

  - [导出 Lync Server 2013 拓扑并将其复制到外部媒体以用于边缘安装](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)

