---
title: 迁移多个站点和池
description: 迁移多个站点和池。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrating multiple sites and pools
ms:assetid: a6d726d2-564d-4b39-a97c-5656a673292a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205165(v=OCS.15)
ms:contentKeyID: 48185079
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7efaa6f038286ff9138e631f23da88bb445e20f1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543248"
---
# <a name="migrating-multiple-sites-and-pools"></a>迁移多个站点和池

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-17_

Lync Server 2013 支持多站点部署和多池部署。 将多个池从 Lync Server 2010 迁移到 Lync Server 2013 的过程需要以下注意事项：

1.  部署 Lync Server 2013 引导池之后，需要定义将移动到 Lync Server 2013 池的试点用户的子集，以及用于验证用户功能的方法。 例如，在将用户移动到引导池之后，请验证用户的会议策略是否已移动到 Lync Server 2013。

2.  在引导池中部署边缘服务器之后，需要验证外部用户是否可以与 Lync Server 2013 池通信。

3.  将来自 Lync Server 2010 边缘服务器的联盟路由转换为试点 Lync Server 2013 边缘服务器后，需要验证联合用户是否可以与 Lync Server 2013 池通信。

4.  移动所有用户和非用户联系人对象之后，需要验证 Lync Server 2010 池是否为空。

5.  在验证 Lync Server 2010 池是否为空之后，您可以停用该池。
    
    有关如何停用旧版 Lync Server 2010 池和服务器的详细信息，请参阅 [第8阶段：停止旧版池](phase-8-decommission-legacy-pools.md)。

</div>

<span> </span>

</div>

</div>

</div>

