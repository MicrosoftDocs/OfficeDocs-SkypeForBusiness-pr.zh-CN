---
title: Lync Server 2013： SQL Server 数据和日志文件的放置
description: Lync Server 2013： SQL Server 数据和日志文件的放置。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SQL Server data and log file placement
ms:assetid: 67aa525b-8aa3-474f-827e-8e1d4697f30f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398479(v=OCS.15)
ms:contentKeyID: 48184395
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a127254fec41a734136df9b63fc6cc8929745df7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558278"
---
# <a name="sql-server-data-and-log-file-placement-for-lync-server-2013"></a>Lync Server 2013 的 SQL Server 数据和日志文件放置

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-21_

在为 Lync Server 2013 前端池规划和部署 Microsoft SQL Server 2012 或 Microsoft SQL Server 2008 R2 SP1 的过程中，重要的考虑因素是将数据和日志文件放置在物理硬盘上以提高性能。 建议的磁盘配置是使用6个心轴来实现 1 + 0 RAID 集。 将由前端池和相关服务器角色和 (服务使用的所有数据库和日志文件（即，存档和监控服务器、Lync Server 响应组服务、Lync Server 呼叫寄存服务) 使用 Lync server 部署向导）中的所有数据库和日志文件都放在使用 Lync Server 部署向导的 RAID 驱动器集上时，将导致配置已测试为获得最佳性能。 下表详细介绍了这些数据库文件以及它们负责的内容。

<div>


> [!NOTE]  
> 如果您的策略和 SQL Server 配置需要更专用的安装，则可以使用 Lync Server 命令行管理程序将数据库和日志文件安装到任何预定义的位置。 有关更多详细信息，请参阅 <A href="lync-server-2013-database-installation-using-lync-server-management-shell.md">使用 Lync Server 命令行管理程序在 Lync server 2013 中安装数据库</A> 。



</div>

### <a name="data-and-log-files-for-central-management-store"></a>中央管理存储的数据和日志文件

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>中央管理存储数据库文件</th>
<th>用于数据文件或日志</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Xds</p></td>
<td><p>中央管理存储的事务日志文件</p></td>
</tr>
<tr class="even">
<td><p>Xds</p></td>
<td><p>维护由拓扑生成器定义和发布的当前 Lync Server 2013 拓扑的配置</p></td>
</tr>
<tr class="odd">
<td><p>.Lis</p></td>
<td><p>位置信息服务数据文件</p></td>
</tr>
<tr class="even">
<td><p>.Lis</p></td>
<td><p>位置信息服务数据文件的事务日志</p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-user-conferencing-and-address-book"></a>用户、会议和通讯簿的数据和日志文件

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>核心 Lync Server 2013 数据库文件</th>
<th>用于数据文件或日志</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Rtc</p></td>
<td><p>持久性用户数据 (例如，访问控制列表 (Acl) 、联系人、安排的会议) </p></td>
</tr>
<tr class="even">
<td><p>Rtc</p></td>
<td><p>Rtc 数据的事务日志</p></td>
</tr>
<tr class="odd">
<td><p>Rtcdyn</p></td>
<td><p>维护瞬时用户数据 (状态运行时数据) </p></td>
</tr>
<tr class="even">
<td><p>Rtcdyn</p></td>
<td><p>Rtcdyn 数据的事务日志</p></td>
</tr>
<tr class="odd">
<td><p>Rtcab</p></td>
<td><p>实时通信 (RTC) 通讯簿数据库是存储通讯簿服务信息的 SQL Server 存储库</p></td>
</tr>
<tr class="even">
<td><p>Rtcab</p></td>
<td><p>通讯簿服务的事务日志</p></td>
</tr>
<tr class="odd">
<td><p>Rtclocal</p></td>
<td><p>承载会议目录</p></td>
</tr>
<tr class="even">
<td><p>Rtcxds</p></td>
<td><p>维护用户数据的备份</p></td>
</tr>
<tr class="odd">
<td><p>Rtcxds</p></td>
<td><p>Rtcxds 数据的事务日志</p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-call-park-and-response-group"></a>呼叫寄存和响应组的数据和日志文件

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>应用程序数据库</th>
<th>用于数据文件或日志</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Cpsdyn</p></td>
<td><p>呼叫寄存应用程序的动态信息数据库</p></td>
</tr>
<tr class="even">
<td><p>Cpsdyn</p></td>
<td><p>呼叫寄存应用程序数据文件的事务日志</p></td>
</tr>
<tr class="odd">
<td><p>Rgsconfig</p></td>
<td><p>用于配置服务的 Lync Server 响应组服务数据文件</p></td>
</tr>
<tr class="even">
<td><p>Rgsconfig</p></td>
<td><p>响应组应用程序配置的事务日志文件</p></td>
</tr>
<tr class="odd">
<td><p>Rgsdyn</p></td>
<td><p>运行时操作的响应组服务数据文件</p></td>
</tr>
<tr class="even">
<td><p>Rgsdyn</p></td>
<td><p>响应组服务运行时数据文件的事务日志</p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-archiving-and-monitoring-server"></a>存档和监控服务器的数据和日志文件

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>存档和监控数据库文件</th>
<th>用于数据文件或日志</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>LcsCdr</p></td>
<td><p>监视服务器 (CDR) 流程的呼叫详细信息记录的数据存储</p></td>
</tr>
<tr class="even">
<td><p>LcsCdr</p></td>
<td><p>呼叫详细信息记录 (CDR) 数据的事务日志</p></td>
</tr>
<tr class="odd">
<td><p>QoEMetrics</p></td>
<td><p>从监视服务器存储的经验数据文件的质量</p></td>
</tr>
<tr class="even">
<td><p>QoEMetrics</p></td>
<td><p>监控数据的事务日志</p></td>
</tr>
<tr class="odd">
<td><p>Lcslog</p></td>
<td><p>存档服务器上的即时消息和会议数据的保留数据文件</p></td>
</tr>
<tr class="even">
<td><p>Lcslog</p></td>
<td><p>为数据存档的事务日志</p></td>
</tr>
</tbody>
</table>


本主题引用了磁盘和 RAID 集的相关内容。请注意，SQL Server 资源配置中提及的磁盘表示单个硬件设备。硬盘驱动器包括两个分区，一个分区保存日志文件，另一个分区保存数据文件，这与有两个磁盘，每个磁盘专用于存储日志或数据文件的情况不同。

谈到 RAID 集，不同的供应商提供了几种不同的 RAID 技术。 并且，随着存储区域网络 (SAN) 的扩展，专用于单个系统的 RAID 集越来越少。 在使用 Lync Server 2013 配置 SQL Server 性能时，应咨询你的 RAID 或 SAN 供应商，以确定您的磁盘布局的最佳配置。

另请注意，创建的磁盘驱动器的性能可能各不相同，一些磁盘驱动器的性能优于其他磁盘驱动器。 由于转速、硬件缓存大小以及其他因素，即使是同一制造商的驱动器的性能也会有所不同。

</div>

<span> </span>

</div>

</div>

</div>

