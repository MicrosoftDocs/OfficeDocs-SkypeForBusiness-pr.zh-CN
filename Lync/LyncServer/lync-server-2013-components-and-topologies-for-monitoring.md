---
title: Lync Server 2013：用于监控的组件和拓扑
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
ms.openlocfilehash: 76e857d0c80793f61b8e60686cc9455d27bb9f95
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742592"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-monitoring-in-lync-server-2013"></a>Lync Server 2013 中用于监控的组件和拓扑

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-09-05_

由于统一数据收集代理会在每个前端服务器上自动安装和激活，因此无需将服务器配置为监视服务器;每个前端服务器都已充当监视服务器。 但是，你将需要安装和配置数据库以用作你的监视数据的后端数据存储。 Microsoft Lync Server 2013 可以将以下任意数据库用作监视的后端存储：

  - Microsoft SQL Server 2008 R2 企业版

  - Microsoft SQL Server 2008 R2 标准版

  - Microsoft SQL Server 2012 企业版

  - Microsoft SQL Server 2012 标准版

请注意，您必须使用这些数据库的64位版本;32位版本的 SQL Server 无法用作监视的后端存储。 同样，Lync Server 2013 不支持 SQL Server 2008 或 SQL Server 2012 的速成版。 有关 Lync Server 2013 的数据库要求的详细信息，请参阅 Lync server 2013 支持指南中的 " [Lync server 2013 中的数据库软件支持](lync-server-2013-database-software-support.md)" 主题。

请记住，必须先安装并配置 SQL Server，然后再部署和配置监控。 但是，你只需部署 SQL Server 本身;您无需提前设置监视数据库。 因此，当你发布 Lync Server 拓扑时，将自动为你创建这些数据库。

监控数据可以与其他类型的数据共享 SQL Server 实例。通常，呼叫详细信息记录数据库 (LcsCdr) 和体验质量数据库 (QoEMetrics) 共享相同的 SQL 实例；这两个监控数据库与存档数据库 (LcsLog) 位于相同的 SQL 实例中也是很常见的。对 SQL Server 实例的唯一真正要求是，SQL Server 的任何一个实例仅限于以下各项：

  - Lync Server 2013 后端数据库的一个实例。 （作为一般规则，建议不要将监视数据库 collocated 在同一 SQL 实例中，甚至可以在同一台计算机上，而不是后端数据库。 尽管技术上可以使用后端数据库所需的磁盘空间来运行监视数据库的风险。）

  - 呼叫详细信息记录数据库的一个实例。

  - 体验质量数据库的一个实例。

  - 存档数据库的一个实例。

换句话说，在 SQL Server 的同一实例中，不能有两个 LcsCdr 数据库实例。 如果需要 LcsCdr 数据库的多个实例，则需要配置多个 SQL Server 实例。

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中部署监视](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

