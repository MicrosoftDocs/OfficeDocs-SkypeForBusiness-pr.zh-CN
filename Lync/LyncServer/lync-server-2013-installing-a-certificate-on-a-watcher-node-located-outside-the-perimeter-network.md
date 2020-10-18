---
title: Lync Server 2013：在位于外围网络外部的观察程序节点上安装证书
description: Lync Server 2013：在位于外围网络外部的观察程序节点上安装证书。
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
ms.openlocfilehash: 66f40886e9784b5bd4182a60b955745b5daf2034
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574028"
---
# <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network-of-lync-server-2013"></a>在 Lync Server 2013 外围网络外部的观察程序节点上安装证书

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-22_

在外围网络中运行的 System Center Operations Manager 代理 (如 Lync Server Edge Server) 、企业外 (（例如外部综合事务观察程序节点) 或跨 Active Directory 域服务信任边界）的情况下，可能需要配置 System Center Operations Manager 网关服务器。 此服务器角色允许与根管理服务器没有信任关系的代理发出警报。 有关详细信息，请参阅位于的 System Center Operations Manager TechNet Library 中的 "管理 Operations Manager 2007 中的网关服务器" [https://go.microsoft.com/fwlink/p/?LinkId=268703](https://go.microsoft.com/fwlink/p/?linkid=268703) 。

如果在其中一个位置中部署代理，则还需要请求和配置一个允许观察程序节点向 System Center Operations Manager 发送警报的证书。 为了简化此过程，Operations Manager 团队创建了一系列实用程序，使您能在观察程序节点计算机上请求和安装正确类型的证书。 有关详细信息和下载这些实用程序的详细信息，请参阅中的 "使用证书生成向导获取用于非域加入代理的证书"。中的博客文章 [https://go.microsoft.com/fwlink/p/?LinkId=267421](https://go.microsoft.com/fwlink/p/?linkid=267421) 。

</div>

<span> </span>

</div>

</div>

</div>

