---
title: 迁移多个站点和池
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrating multiple sites and pools
ms:assetid: 3bf677d4-a5af-4f73-8fad-1abf5b668cc1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688025(v=OCS.15)
ms:contentKeyID: 49733615
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7412d0ffb1a5d24c2f30b76b987a16903253bfb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845207"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-multiple-sites-and-pools"></a>迁移多个站点和池

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-08-26_

Lync Server 2013 支持多站点和多池部署。 将多个池从 Office 通信服务器 2007 R2 迁移到 Lync Server 2013 的过程需要考虑下列事项:

1.  部署 Lync Server 2013 试验池后, 你需要定义将被移动到 Lync Server 2013 池的试点用户的子集, 以及用于验证用户功能的方法。

2.  在试验池中部署边缘服务器之后, 你需要验证外部用户是否可以与 Lync Server 2013 池通信。

3.  将 Office 通信服务器 2007 R2 Edge 服务器中的联盟路由转换为试点 Lync Server 2013 Edge 服务器之后, 你需要验证联盟用户是否可以与 Lync Server 2013 池通信。

4.  移动所有用户和非用户联系人对象后, 需要验证 Office 通信服务器 2007 R2 池是否为空。

5.  验证 Office 通信服务器 2007 R2 池是否为空后, 您可以停用该池。
    
    有关如何停用旧版 Office 通信服务器 2007 R2 池和服务器的详细信息, 请参阅第[10 阶段: 停止旧版网站](phase-10-decommission-legacy-site.md)。

</div>

<span> </span>

</div>

</div>

</div>

