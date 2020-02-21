---
title: Lync Server 2013：用于 IP 电话的拓扑
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topologies for IP phones
ms:assetid: 26ebffcf-43ff-4e70-847d-0fbc90e94e57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425740(v=OCS.15)
ms:contentKeyID: 48183662
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 36afef4fe357e79f1d6c9579273262b265d2c0ad
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193565"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="topologies-for-ip-phones-in-lync-server-2013"></a>Lync Server 2013 中的 IP 电话拓扑

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-06-21_

本节概述连接过程，并介绍 IP 电话在内部和外部网络中的连接方式之间的差异。

<div>


> [!NOTE]  
> Lync Server 为以下 IP 电话提供支持： Aastra 6721ip 公共区域电话、Aastra 6725ip 办公桌电话、HP 4110 IP 电话（公用区域电话）、HP 4120 IP 电话（桌面电话）、Polycom CX600 IP 桌面电话、Polycom CX700 IP 桌面电话、Polycom CX500 IP公共区域电话和 Polycom CX3000 IP 会议电话。 在这些电话中，除 Polycom CX700 之外的所有其他电话都可以运行 Lync Phone Edition。



</div>

下图介绍在企业环境下设备连接涉及的所有组件。

**内部拓扑**

![3d88893e-df57-46e3-855a-a1d24589030a](images/Gg425740.3d88893e-df57-46e3-855a-a1d24589030a(OCS.15).jpg "3d88893e-df57-46e3-855a-a1d24589030a")

<div>


> [!NOTE]  
> 上图采用逻辑表示形式，而非物理概述。 例如，Active Directory 域服务（AD DS）很少与任何 Lync Server 组件位于同一台计算机上。 用户存储可以位于后端服务器上，也可以位于存档服务器和监控服务器上。 Lync Server 命令行管理程序、web 服务器和更新服务都是前端服务器角色的一部分。



</div>

下图概述设备位于企业网络外部时涉及的组件。

**外部拓扑**

![8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3](images/Gg425740.8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3(OCS.15).jpg "8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3")

<div>


> [!NOTE]  
> 设备更新 Web 服务提供外部和内部网站，但此处仅显示外部网站。<BR>如果要启用外部访问，则必须在 DNS 中发布注册器的位置和组织设备更新 Web 服务的 URL。此外，还必须部署和正确配置边缘服务器，以允许从设备到企业环境的往返外部通信。上图省略了该内容，因为边缘部署并非特定于设备连接。



</div>

</div>

<span> </span>

</div>

</div>

</div>

