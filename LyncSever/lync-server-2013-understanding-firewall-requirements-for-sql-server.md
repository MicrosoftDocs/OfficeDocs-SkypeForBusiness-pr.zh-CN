---
title: Lync Server 2013：了解 SQL Server 的防火墙要求
TOCTitle: 了解 SQL Server 的防火墙要求
ms:assetid: 31d7df2c-589f-465e-be74-cf6767db190d
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425818(v=OCS.15)
ms:contentKeyID: 49312424
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 了解 SQL Server 与 Lync Server 2013 一起使用时的防火墙要求

 

_**上一次修改主题：** 2016-12-08_

对于 标准版 部署，在安装 Lync Server 2013 期间会自动创建防火墙例外。但是，对于 企业版 部署，必须在 SQL Server 后端服务器上手动配置防火墙例外。TCP/CP 协议只允许给定端口对给定 IP 地址使用一次。这意味着，对于基于 SQL Server 的服务器，可以为默认数据库实例分配默认 TCP 端口 1433。对于其他任何实例，将需要使用 SQL Server 配置管理器分配唯一并且未使用的端口。本主题包含以下内容：

  - 使用默认实例时防火墙例外的要求

  - SQL Server Browser 服务的防火墙例外要求

  - 使用命名实例时静态侦听端口的要求

## 使用默认实例时防火墙例外的要求

如果部署 Lync Server 2013 时将 SQL Server 默认实例用于任何数据库，则将使用以下防火墙规则要求来帮助确保从前端池到 SQL Server 默认实例的通信。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>协议</th>
<th>端口</th>
<th>方向</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TCP</p></td>
<td><p>1433</p></td>
<td><p>入站至 SQL Server</p></td>
</tr>
</tbody>
</table>


## SQL Server Browser 服务的防火墙例外要求

SQL Server Browser 服务将查找数据库实例，并与配置为供该实例（命名实例或默认实例）使用的端口进行通信。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>协议</th>
<th>端口</th>
<th>方向</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>UDP</p></td>
<td><p>1434</p></td>
<td><p>Inbound</p></td>
</tr>
</tbody>
</table>


## 使用命名实例时静态侦听端口的要求

将 SQL Server 配置中的命名实例用于支持 Lync Server 2013 的数据库时，应使用 SQL Server 配置管理器配置静态端口。将静态端口分配至每个命名实例后，在防火墙内为每个静态端口创建例外。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>协议</th>
<th>端口</th>
<th>方向</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TCP</p></td>
<td><p>静态定义</p></td>
<td><p>Inbound</p></td>
</tr>
</tbody>
</table>


## SQL Server 文档

Microsoft SQL Server 2012 文档提供有关如何为数据库配置防火墙访问的详细指导。有关 Microsoft SQL Server 2012 的详细信息，请参阅“配置 Windows 防火墙以允许 SQL Server 访问”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=218031](http://go.microsoft.com/fwlink/p/?linkid=218031)。

