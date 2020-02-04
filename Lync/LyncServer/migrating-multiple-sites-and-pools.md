---
title: 迁移多个站点和池
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrating multiple sites and pools
ms:assetid: a6d726d2-564d-4b39-a97c-5656a673292a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205165(v=OCS.15)
ms:contentKeyID: 48185079
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b2f01303c7fe137253d8e993edb05e9562d963ff
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765250"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-multiple-sites-and-pools"></a>迁移多个站点和池

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-09-17_

Lync Server 2013 支持多站点和多池部署。 将多个池从 Lync Server 2010 迁移到 Lync Server 2013 的过程需要考虑下列事项：

1.  部署 Lync Server 2013 试验池后，你需要定义将被移动到 Lync Server 2013 池的试点用户的子集，以及用于验证用户功能的方法。 例如，将用户移动到试验池后，请验证用户的会议策略是否已迁移到 Lync Server 2013。

2.  在试验池中部署边缘服务器之后，你需要验证外部用户是否可以与 Lync Server 2013 池通信。

3.  将 Lync Server 2010 Edge 服务器中的联盟路由转换为试点 Lync Server 2013 Edge 服务器之后，你需要验证联盟用户是否可以与 Lync Server 2013 池通信。

4.  移动所有用户和非用户联系人对象后，需要验证 Lync Server 2010 池是否为空。

5.  验证 Lync Server 2010 池是否为空后，您可以停用该池。
    
    有关如何停用旧版 Lync Server 2010 池和服务器的详细信息，请参阅[第8阶段：解除旧版池](phase-8-decommission-legacy-pools.md)。

</div>

<span> </span>

</div>

</div>

</div>

