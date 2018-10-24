---
title: Lync Server 2013：SQL Server 数据和日志文件放置
TOCTitle: SQL Server 数据和日志文件放置
ms:assetid: 67aa525b-8aa3-474f-827e-8e1d4697f30f
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398479(v=OCS.15)
ms:contentKeyID: 49313101
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 的 SQL Server 数据和日志文件放置

 

_**上一次修改主题：** 2015-03-09_

在为 Lync Server 2013  前端池规划和部署 Microsoft SQL Server 2012 或 Microsoft SQL Server 2008 R2 SP1 的过程中，一个重要的注意事项是向物理硬盘中放置数据和日志文件以提高性能。推荐的磁盘配置是使用 6 个轴实现 1+0 RAID 集。使用 Lync Server 部署向导将 前端池及关联的服务器角色和服务（即， 存档和监控服务器、 Lync Server 响应组服务、 Lync Server 呼叫寄存服务）使用的所有数据库和日志文件放置到 RAID 驱动器集上将生成经测试可实现良好性能的配置。下表详细介绍了这些数据库文件以及它们负责的内容。

> [!NOTE]  
> 如果您的策略和 SQL Server 配置需要更专业的安装，可以使用 Lync Server 命令行管理程序将数据库和日志文件安装到任何预定义位置。有关更多详细信息，请参阅 <a href="lync-server-2013-database-installation-using-lync-server-management-shell.md">在 Lync Server 2013 中使用 Lync Server 命令行管理程序安装数据库</a>。


### 中央管理存储的数据和日志文件

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
<td><p>Xds.ldf</p></td>
<td><p>中央管理存储的事务日志文件</p></td>
</tr>
<tr class="even">
<td><p>Xds.mdf</p></td>
<td><p>根据 拓扑生成器定义和发布的内容，维护当前 Lync Server 2013 拓扑的配置。</p></td>
</tr>
<tr class="odd">
<td><p>Lis.mdf</p></td>
<td><p>位置信息服务数据文件</p></td>
</tr>
<tr class="even">
<td><p>Lis.ldf</p></td>
<td><p>位置信息服务数据文件的事务日志</p></td>
</tr>
</tbody>
</table>


### 用户、会议和通讯簿的数据和日志文件

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
<td><p>Rtc.mdf</p></td>
<td><p>永久用户数据（例如，访问控制列表 (ACL)、联系人、安排的会议）</p></td>
</tr>
<tr class="even">
<td><p>Rtc.ldf</p></td>
<td><p>Rtc 数据的事务日志</p></td>
</tr>
<tr class="odd">
<td><p>Rtcdyn.mdf</p></td>
<td><p>维护临时用户数据（状态运行时数据）</p></td>
</tr>
<tr class="even">
<td><p>Rtcdyn.ldf</p></td>
<td><p>Rtcdyn 数据的事务日志</p></td>
</tr>
<tr class="odd">
<td><p>Rtcab.mdf</p></td>
<td><p>实时通信 (RTC) 通讯簿数据库是存储通讯簿服务信息的 SQL Server 存储库</p></td>
</tr>
<tr class="even">
<td><p>Rtcab.ldf</p></td>
<td><p>通讯簿服务的事务日志</p></td>
</tr>
<tr class="odd">
<td><p>Rtclocal.mdb</p></td>
<td><p>托管会议目录</p></td>
</tr>
<tr class="even">
<td><p>Rtcxds.mdf</p></td>
<td><p>维护用户数据的备份</p></td>
</tr>
<tr class="odd">
<td><p>Rtcxds.ldf</p></td>
<td><p>Rtcxds 数据的事务日志</p></td>
</tr>
</tbody>
</table>


### 呼叫寄存和响应组的数据和日志文件

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
<td><p>Cpsdyn.mdf</p></td>
<td><p>呼叫寄存应用程序的动态信息数据库</p></td>
</tr>
<tr class="even">
<td><p>Cpsdyn.ldf</p></td>
<td><p>呼叫寄存应用程序数据文件的事务日志</p></td>
</tr>
<tr class="odd">
<td><p>Rgsconfig.mdf</p></td>
<td><p>用于配置服务的 Lync Server 响应组服务数据文件</p></td>
</tr>
<tr class="even">
<td><p>Rgsconfig.ldf</p></td>
<td><p>用于 响应组应用程序配置的事务日志文件</p></td>
</tr>
<tr class="odd">
<td><p>Rgsdyn.mdf</p></td>
<td><p>运行时操作的响应组服务数据文件</p></td>
</tr>
<tr class="even">
<td><p>Rgsdyn.ldf</p></td>
<td><p>响应组服务运行时数据文件的事务日志</p></td>
</tr>
</tbody>
</table>


### 存档和监控服务器的数据和日志文件

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
<td><p>LcsCdr.mdf</p></td>
<td><p>用于 监控服务器的呼叫详细信息记录 (CDR) 过程的数据存储</p></td>
</tr>
<tr class="even">
<td><p>LcsCdr.ldf</p></td>
<td><p>呼叫详细信息记录 (CDR) 数据的事务日志</p></td>
</tr>
<tr class="odd">
<td><p>QoEMetrics.mdf</p></td>
<td><p>从 监控服务器中存储的用户体验质量数据文件</p></td>
</tr>
<tr class="even">
<td><p>QoEMetrics.ldf</p></td>
<td><p>监控数据的事务日志</p></td>
</tr>
<tr class="odd">
<td><p>Lcslog.mdf</p></td>
<td><p>将即时消息和会议数据保留在 存档服务器上的数据文件</p></td>
</tr>
<tr class="even">
<td><p>Lcslog.ldf</p></td>
<td><p>为数据存档的事务日志</p></td>
</tr>
</tbody>
</table>


本主题引用了磁盘和 RAID 集的相关内容。请注意，SQL Server 资源配置中提及的磁盘表示单个硬件设备。硬盘驱动器包括两个分区，一个分区保存日志文件，另一个分区保存数据文件，这与有两个磁盘，每个磁盘专用于存储日志或数据文件的情况不同。

谈到 RAID 集，不同的供应商提供了几种不同的 RAID 技术。并且，随着存储区域网络 (SAN) 的扩展，专用于单个系统的 RAID 集越来越少。在配置 Lync Server 2013 的 SQL Server 性能时，应咨询 RAID 或 SAN 供应商以确定磁盘布局的最佳配置。

另请注意，创建的磁盘驱动器的性能可能各不相同，一些磁盘驱动器的性能优于其他磁盘驱动器。由于转速、硬件缓存大小以及其他因素，即使是同一制造商的驱动器，性能也会有所不同。

