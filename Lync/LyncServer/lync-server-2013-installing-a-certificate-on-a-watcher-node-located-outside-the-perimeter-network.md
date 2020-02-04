---
title: Lync Server 2013：在外围网络外部的观察程序节点上安装证书
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
ms.openlocfilehash: 10cd31639445fab6138ea77cb40a03d727ecce12
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726172"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network-of-lync-server-2013"></a>在 Lync Server 2013 外围网络外部的观察程序节点上安装证书

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-22_

在外围网络（如 Lync 服务器 Edge 服务器）中运行的 System Center Operations Manager 代理（如外部合成事务观察程序节点）或在 Active Directory 域服务信任边界内运行的 System Center Operations Manager 代理可能需要配置 System Center Operations Manager 网关服务器。 此服务器角色允许与根管理服务器不具有信任关系的代理引发警报。 有关详细信息，请参阅 System Center Operations Manager TechNet 库中的 "管理 Operations Manager 2007 中的网[http://go.microsoft.com/fwlink/p/?LinkId=268703](http://go.microsoft.com/fwlink/p/?linkid=268703)关服务器"。

如果在其中一个位置中部署代理，你还需要请求和配置一个允许观察程序节点向 System Center Operations Manager 发送警报的证书。 为简化此过程，Operations Manager 团队已创建一组实用工具，可让你在观察程序节点计算机上请求和安装正确的证书类型。 有关详细信息，以及要下载这些实用程序，请参阅中的 "通过证书生成向导为非域加入的代理获取证书" 中[http://go.microsoft.com/fwlink/p/?LinkId=267421](http://go.microsoft.com/fwlink/p/?linkid=267421)的 "博客文章"。

</div>

<span> </span>

</div>

</div>

</div>

