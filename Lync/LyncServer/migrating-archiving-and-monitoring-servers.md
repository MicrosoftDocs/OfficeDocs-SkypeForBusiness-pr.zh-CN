---
title: 迁移存档和监控服务器
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrating Archiving and Monitoring servers
ms:assetid: 77831579-df45-4697-b8c5-207b74a07a40
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205015(v=OCS.15)
ms:contentKeyID: 48184550
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ba32bf2b35a0d2e8b0048ebb9c62aac09cb6eb7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527405"
---
# <a name="migrating-archiving-and-monitoring-servers"></a>迁移存档和监控服务器

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-02_

如果您在 Lync Server 2010 环境中部署了存档服务器和监视服务器，则可以在迁移前端池后在 Lync Server 2013 环境中部署这些服务器。 但是，如果存档和监视功能对您的组织至关重要，那么在迁移之前，应在您的 Lync Server 2013 试点池中添加存档和监控功能，以便在迁移过程中使用该功能。

如果迁移过程中需要存档和监控功能，应注意以下问题：

  - 存档数据和监控数据不会移动到 Lync Server 2013 部署中。 在停用旧环境之前备份的数据将成为 Lync Server 2010 环境中的活动历史记录。

  - Lync Server 2010 版本的存档服务器和监视服务器只能与 Lync Server 2010 前端池关联。 在 Lync Server 2013 中，存档和监控不再是服务器角色，而是集成到 Lync Server 2013 前端池的服务。

  - 在旧版和 Lync Server 2013 部署共存期间，存档服务器和监视服务器的 Lync Server 2010 版本将为驻留在 Lync Server 2010 池中的用户收集数据。 Lync Server 2013 中的存档和监控为驻留在 Lync Server 2013 池上的用户收集数据。
    
    <div>
    

    > [!NOTE]  
    > 在迁移阶段，如果你仍在使用新的 Lync Server 2013 试点池时使用旧版边缘服务器，则存档服务器的 Lync Server 2010 版本将继续为驻留2010在 lync server 中的用户收集数据。2013在 lync server 中的池和存档中，为驻留在 Lync Server 2013 池中的用户收集数据。

    
    </div>

  - 如果将第三方存档和监控解决方案与 Lync Server 2013 中的存档和监控结合使用，请咨询您的供应商，了解何时以及如何将第三方解决方案与 Lync Server 2013 集成。

</div>

<span> </span>

</div>

</div>

</div>

