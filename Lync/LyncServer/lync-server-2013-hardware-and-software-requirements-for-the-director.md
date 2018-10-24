---
title: Lync Server 2013：控制器的软硬件要求
TOCTitle: 控制器的软硬件要求
ms:assetid: 747b701e-7f97-46fe-91c5-1e8d9addf9f7
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398560(v=OCS.15)
ms:contentKeyID: 49313256
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中控制器的软硬件要求

 

_**上一次修改主题：** 2016-05-19_

本节详细说明了 控制器的软硬件要求，以及支持的 控制器并置方案。

## 控制器的硬件要求

下表列出了 控制器的硬件要求：

### 控制器的硬件要求

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>硬件组件</th>
<th>最低要求</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CPU</p></td>
<td><ul>
<li><p>64 位处理器、四核、2.0 GHz 或更快</p></li>
<li><p>64 位双处理器、双核、2.0 GHz 或更快</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>内存</p></td>
<td><p>4 GB</p></td>
</tr>
<tr class="odd">
<td><p>磁盘</p></td>
<td><ul>
<li><p>转速为 10K RPM 的硬盘驱动器 (HDD)</p></li>
<li><p>性能等于或高于 10K RPM HDD 的高性能固态驱动器 (SSD)</p></li>
<li><p>2 个 RAID 10（条带和镜像）、转速为 15K RPM 的硬盘，用于存储数据库数据文件</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>网络</p></td>
<td><ul>
<li><p>双 1 千兆位每秒 (Gbps) 网络适配器（推荐）</p></li>
<li><p>一个 1 Gbps 网络适配器（支持）</p></li>
</ul></td>
</tr>
</tbody>
</table>


## 控制器的软件要求

只能在运行 Lync Server 2013 Enterprise Edition 的服务器上部署 控制器角色。

控制器要求安装以下 64 位操作系统之一：

  - Windows Server 2008 R2 Standard Service Pack 1 操作系统

  - Windows Server 2008 R2 Enterprise Service Pack 1 操作系统

  - Windows Server 2008 R2 Datacenter Service Pack 1 操作系统

  - Windows Server 2012 Standard 操作系统

  - Windows Server 2012 Datacenter 操作系统

Lync Server 2013 还需要安装主题 [Lync Server 2013 中的其他服务器支持和要求](lync-server-2013-additional-server-support-and-requirements.md)中详述的以下程序和更新。

## 支持的并置

不能将 控制器服务器角色与 Lync Server 2013 中的其他任何服务器角色并置。但是，如果您不部署 控制器， 前端服务器将承担该角色。

