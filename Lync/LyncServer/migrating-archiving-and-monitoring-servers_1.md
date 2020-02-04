---
title: 迁移存档和监控服务器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrating Archiving and Monitoring servers
ms:assetid: 8d879253-ad76-42b7-8386-e44b110239cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688124(v=OCS.15)
ms:contentKeyID: 49733722
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee3abd26386ad26e3b6628d5b9db873bd17373be
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743772"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-archiving-and-monitoring-servers"></a>迁移存档和监控服务器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-02_

如果你在 Office 通信服务器 2007 R2 中部署了存档服务器和监视服务器，你可以在迁移前端池后在 Lync Server 2013 环境中部署这些服务器。 但是，如果存档和监视功能对你的组织至关重要，则应在迁移之前将存档和监视添加到你的试点池，以便在迁移过程中使用该功能。

如果在迁移和共存阶段需要存档和监视功能，请记住以下注意事项：

  - 存档数据和监视数据不会迁移到 Lync Server 2013 部署。 在取消旧版环境之前备份的数据将是 Office 通信服务器 2007 R2 中的活动历史记录。

  - Office 通信服务器 2007 R2 版本的存档服务器和监视服务器只能与 Office 通信服务器 2007 R2 前端池关联。 在 Lync Server 2013 中，存档和监控不再是服务器角色，而是与 Lync Server 2013 前端池集成的服务。

  - 在旧版本和 Lync Server 2013 部署共存期间，Office 通信服务器 2007 R2 版本的存档服务器和监视服务器会为驻留在 Office 通信服务器上的用户收集数据，2007 R2 池。 Lync Server 2013 版本的存档服务器和监视服务器为驻留在 Lync Server 2013 池的用户收集数据。
    
    <div>
    

    > [!NOTE]  
    > 在迁移阶段，当你仍将旧式 Edge 服务器与新的 Lync Server 2013 试验池配合使用时，存档服务器的 Office 通信服务器 2007 R2 版本会继续为驻留在 Office 通信服务器上的用户收集数据。2007R2 池和 Lync Server 2013 版本的存档服务器为驻留在 Lync Server 2013 池的用户收集数据。

    
    </div>

  - 如果你将第三方存档和监视解决方案与存档服务器和监视服务器结合使用，请与你的供应商联系，了解何时以及如何将第三方解决方案与 Lync Server 2013 集成。

</div>

<span> </span>

</div>

</div>

</div>

