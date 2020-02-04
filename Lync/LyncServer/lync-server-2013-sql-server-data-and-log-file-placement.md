---
title: Lync Server 2013：SQL Server 数据和日志文件放置
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
ms.openlocfilehash: 197141ea62307631eab206fce5403d25b4d89583
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764438"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sql-server-data-and-log-file-placement-for-lync-server-2013"></a>Lync Server 2013 的 SQL Server 数据和日志文件放置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-02-21_

在为 Lync Server 2013 前端池规划和部署 Microsoft SQL Server 2012 或 Microsoft SQL Server 2008 R2 SP1 的过程中，重要的考虑因素是将数据和日志文件放置在物理硬盘上以提高性能。 推荐的磁盘配置是使用6个心轴实现 1 + 0 RAID 集。 将前端池和关联的服务器角色和服务（即，存档和监视服务器、Lync Server 响应组服务、Lync Server 呼叫驻留服务）使用的所有数据库和日志文件放在使用 Lync Server 的 RAID 驱动器集上部署向导将导致配置已测试为获得良好性能。 下表详细介绍了数据库文件及其所负责的内容。

<div>


> [!NOTE]  
> 如果你的策略和 SQL Server 配置需要更多专用安装，则可以使用 Lync Server 命令行管理程序将数据库和日志文件安装到任何预定义的位置。 有关详细信息，请参阅<A href="lync-server-2013-database-installation-using-lync-server-management-shell.md">在 Lync server 2013 中使用 Lync Server Management Shell 的数据库安装</A>。



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
<th>数据文件或日志用途</th>
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
<th>数据文件或日志用途</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Rtc</p></td>
<td><p>永久性用户数据（例如访问控制列表（Acl）、联系人、计划的会议）</p></td>
</tr>
<tr class="even">
<td><p>Rtc</p></td>
<td><p>Rtc 数据的事务日志</p></td>
</tr>
<tr class="odd">
<td><p>Rtcdyn</p></td>
<td><p>维护瞬时用户数据（状态显示运行时数据）</p></td>
</tr>
<tr class="even">
<td><p>Rtcdyn</p></td>
<td><p>Rtcdyn 数据的事务日志</p></td>
</tr>
<tr class="odd">
<td><p>Rtcab</p></td>
<td><p>实时通信（RTC）通讯簿数据库是存储通讯簿服务信息的 SQL Server 存储库</p></td>
</tr>
<tr class="even">
<td><p>Rtcab</p></td>
<td><p>通讯簿服务的事务日志</p></td>
</tr>
<tr class="odd">
<td><p>Rtclocal</p></td>
<td><p>托管会议目录</p></td>
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


### <a name="data-and-log-files-for-call-park-and-response-group"></a>通话寄存和响应组的数据和日志文件

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>应用程序数据库</th>
<th>数据文件或日志用途</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Cpsdyn</p></td>
<td><p>用于呼叫驻留应用程序的动态信息数据库</p></td>
</tr>
<tr class="even">
<td><p>Cpsdyn</p></td>
<td><p>呼叫驻留应用程序数据文件的事务日志</p></td>
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


### <a name="data-and-log-files-for-archiving-and-monitoring-server"></a>用于存档和监视服务器的数据和日志文件

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>存档和监视数据库文件</th>
<th>数据文件或日志用途</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>LcsCdr</p></td>
<td><p>监视服务器的呼叫详细记录（CDR）流程的数据存储</p></td>
</tr>
<tr class="even">
<td><p>LcsCdr</p></td>
<td><p>呼叫详细记录（CDR）数据的事务日志</p></td>
</tr>
<tr class="odd">
<td><p>QoEMetrics</p></td>
<td><p>从监视服务器存储的体验数据文件的质量</p></td>
</tr>
<tr class="even">
<td><p>QoEMetrics</p></td>
<td><p>用于监视数据的事务日志</p></td>
</tr>
<tr class="odd">
<td><p>Lcslog</p></td>
<td><p>用于保留存档服务器上的即时消息和会议数据的数据文件</p></td>
</tr>
<tr class="even">
<td><p>Lcslog</p></td>
<td><p>用于存档数据的事务日志</p></td>
</tr>
</tbody>
</table>


在本主题中，对磁盘和 RAID 集进行引用。 请注意，在 SQL Server 资源的配置中，引用磁盘意味着单个硬件设备。 包含两个分区的硬盘（其中一个包含日志文件和保存数据文件的其他分区）不同于两个磁盘，每个磁盘都专用于日志或数据文件。

在对 RAID 集的参考中，有许多来自不同供应商的不同 RAID 技术。 随着存储区域网络（SAN）的急剧增加，专用于单个系统的 RAID 集将 rarer。 在针对 Lync Server 2013 配置 SQL Server 性能时，应咨询你的 RAID 或 SAN 供应商，以确定你的磁盘布局的最佳配置。

另请注意，并非所有磁盘驱动器都是同等创建的;某些性能比其他更好。 由于转速、硬件缓存大小和其他因素，来自同一制造商的驱动器在性能上可能有所不同。

</div>

<span> </span>

</div>

</div>

</div>

