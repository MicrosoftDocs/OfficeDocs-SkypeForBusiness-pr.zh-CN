---
title: 迁移多个站点和池
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrating multiple sites and pools
ms:assetid: 3bf677d4-a5af-4f73-8fad-1abf5b668cc1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688025(v=OCS.15)
ms:contentKeyID: 49733615
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6efbad7107109096a5f17d82912353e6f8a1a14a
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756491"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrating-multiple-sites-and-pools"></a>迁移多个站点和池

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-08-26_

Lync Server 2013 支持多站点部署和多池部署。 将多个池从 Office 通信服务器 2007 R2 迁移到 Lync Server 2013 的过程需要以下注意事项：

1.  部署 Lync Server 2013 引导池之后，需要定义将移动到 Lync Server 2013 池的试点用户的子集，以及用于验证用户功能的方法。

2.  在引导池中部署边缘服务器之后，需要验证外部用户是否可以与 Lync Server 2013 池通信。

3.  将来自 Office 通信服务器 2007 R2 边缘服务器的联盟路由转换为试点 Lync Server 2013 边缘服务器后，需要验证联合用户是否可以与 Lync Server 2013 池通信。

4.  移动所有用户和非用户联系人对象之后，需要验证 Office 通信服务器 2007 R2 池是否为空。

5.  验证 Office 通信服务器 2007 R2 池是否为空之后，您可以停用池。
    
    有关如何停用旧版 Office 通信服务器 2007 R2 池和服务器的详细信息，请参阅[阶段10：停止旧版网站](phase-10-decommission-legacy-site.md)。

</div>

<span> </span>

</div>

</div>

</div>

