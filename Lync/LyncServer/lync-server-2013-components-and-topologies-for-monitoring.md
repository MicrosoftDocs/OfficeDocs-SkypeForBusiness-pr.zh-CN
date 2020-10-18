---
title: Lync Server 2013：用于监控的组件和拓扑
description: Lync Server 2013：用于监控的组件和拓扑。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for monitoring
ms:assetid: c1bb36b0-1fb8-4d8e-9cc9-9bef740fe3c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412952(v=OCS.15)
ms:contentKeyID: 48185313
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8767a7eb16ca85e9606838606a6e86ee1296fc0e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576838"
---
# <a name="components-and-topologies-for-monitoring-in-lync-server-2013"></a>Lync Server 2013 中用于监控的组件和拓扑

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-05_

由于统一数据收集代理会在每台前端服务器上自动安装和激活，因此无需将服务器配置为监视服务器;每个前端服务器都已用作监控服务器。 但是，您需要安装和配置一个数据库，使其充当您的监控数据的后端数据存储区。 Microsoft Lync Server 2013 可将以下任何数据库用作用于监控的后端存储：

  - Microsoft SQL Server 2008 R2 Enterprise Edition

  - Microsoft SQL Server 2008 R2 Standard Edition

  - Microsoft SQL Server 2012 Enterprise Edition

  - Microsoft SQL Server 2012 Standard Edition

请注意，您必须使用这些数据库的64位版本;32位版本的 SQL Server 不能用作监视的后端存储。 同样，Lync Server 2013 不支持 SQL Server 2008 或 SQL Server 2012 的速成版。 有关 Lync Server 2013 的数据库要求的详细信息，请参阅 Lync server 2013 可支持性指南中的 " [Lync server 2013 中的数据库软件支持](lync-server-2013-database-software-support.md) " 主题。

请注意，必须先安装并配置 SQL Server，然后才能部署和配置监控。 但是，您只需部署 SQL Server 本身;您无需事先设置监控数据库。 相反，在发布 Lync Server 拓扑时，将自动为您创建这些数据库。

监视数据可以与其他类型的数据共享 SQL Server 实例。 通常情况下，呼叫详细信息记录数据库 (LcsCdr) 和体验质量数据库 (QoEMetrics) 共享相同的 SQL 实例;此外，两个监视数据库与存档数据库位于同一 SQL 实例中也很常见 (LcsLog) 。 关于 SQL Server 实例的唯一真正要求是，SQL Server 的任何一个实例仅限于以下内容：

  - Lync Server 2013 后端数据库的一个实例。  (一般规则是，不建议将监视数据库并置在与后端数据库相同的 SQL 实例中，甚至在同一台计算机上。 虽然从技术上讲，您还可以使用后端数据库所需的磁盘空间来运行监控数据库的风险。 ) 

  - 呼叫详细信息记录数据库的一个实例。

  - "体验质量" 数据库的一个实例。

  - 存档数据库的一个实例。

换言之，不能在同一 SQL Server 实例中有两个 LcsCdr 数据库实例。 如果需要 LcsCdr 数据库的多个实例，则需要配置多个 SQL Server 实例。

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中部署监控](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

