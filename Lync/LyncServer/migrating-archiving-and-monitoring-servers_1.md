---
title: 迁移存档和监控服务器
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrating Archiving and Monitoring servers
ms:assetid: 8d879253-ad76-42b7-8386-e44b110239cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688124(v=OCS.15)
ms:contentKeyID: 49733722
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 95646d47ae7b045a193cfec49ea06ad75466853f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527399"
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

如果在 Office 通信服务器 2007 R2 中部署了存档服务器和监视服务器，则可以在迁移前端池后在 Lync Server 2013 环境中部署这些服务器。 不过，如果存档和监控功能对您的组织至关重要，则应在迁移之前在试点池中添加存档和监控，以便迁移过程中可使用这些功能。

如果在迁移和共存阶段需要存档和监控功能，应注意以下问题：

  - 存档数据和监控数据不会移动到 Lync Server 2013 部署中。 在您解除旧环境之前备份的数据将是 Office 通信服务器 2007 R2 中的活动历史记录。

  - Office 通信服务器 2007 R2 版本的存档服务器和监视服务器只能与 Office 通信服务器 2007 R2 前端池相关联。 在 Lync Server 2013 中，存档和监控不再是服务器角色，而是集成到 Lync Server 2013 前端池的服务。

  - 在旧版和 Lync Server 2013 部署共存期间，存档服务器和监视服务器的 Office 通信服务器 2007 R2 版本将为驻留在 Office 通信服务器上的用户收集数据，以 2007 R2 池。 Lync Server 2013 版本的存档服务器和监视服务器为驻留在 Lync Server 2013 池上的用户收集数据。
    
    <div>
    

    > [!NOTE]  
    > 在迁移阶段，如果您仍在使用新的 Lync Server 2013 试点池，则存档服务器的 Office 通信服务器 2007 R2 版本将继续为驻留在 Office 通信服务器上的用户收集数据。 2007 R2 池，而 Lync Server 2013 版本的存档服务器可为驻留在 Lync Server 2013 池中的用户收集数据。

    
    </div>

  - 如果将第三方存档和监控解决方案与存档服务器和监视服务器结合使用，请与供应商联系，了解何时以及如何使用 Lync Server 2013 集成第三方解决方案。

</div>

<span> </span>

</div>

</div>

</div>

