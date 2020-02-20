---
title: Lync Server 2013：在位于外围网络外部的观察程序节点上安装证书
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing a certificate on a watcher node located outside the perimeter network
ms:assetid: 825c9c02-1951-4d7a-a25e-a313a85333f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688113(v=OCS.15)
ms:contentKeyID: 49733711
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4704cc5284b6923967e530492edf2a07054a2a19
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150433"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network-of-lync-server-2013"></a>在 Lync Server 2013 外围网络外部的观察程序节点上安装证书

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-22_

在外围网络中运行的 System Center Operations Manager 代理（如 Lync Server Edge 服务器），企业外部（如外部综合事务观察程序节点）或跨 Active Directory 域服务信任边界可能需要配置 System Center Operations Manager 网关服务器。 此服务器角色允许与根管理服务器没有信任关系的代理发出警报。 有关详细信息，请参阅位于[https://go.microsoft.com/fwlink/p/?LinkId=268703](https://go.microsoft.com/fwlink/p/?linkid=268703)的 System Center Operations Manager TechNet Library 中的 "管理 Operations manager 2007 中的网关服务器"。

如果在其中一个位置中部署代理，则还需要请求和配置一个允许观察程序节点向 System Center Operations Manager 发送警报的证书。 为了简化此过程，Operations Manager 团队创建了一系列实用程序，使您能在观察程序节点计算机上请求和安装正确类型的证书。 有关详细信息和下载这些实用程序的详细信息，请参阅中的 "使用证书生成向导获取用于非域加入代理的证书" [https://go.microsoft.com/fwlink/p/?LinkId=267421](https://go.microsoft.com/fwlink/p/?linkid=267421)。中的博客文章。

</div>

<span> </span>

</div>

</div>

</div>

