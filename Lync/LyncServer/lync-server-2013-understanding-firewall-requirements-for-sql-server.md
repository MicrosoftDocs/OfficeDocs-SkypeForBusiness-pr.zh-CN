---
title: Lync Server 2013：了解 SQL Server 的防火墙要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Understanding firewall requirements for SQL Server
ms:assetid: 31d7df2c-589f-465e-be74-cf6767db190d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425818(v=OCS.15)
ms:contentKeyID: 48183781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba04284106bcd1b0cbf17d214d8ad0b1a1ff9024
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006678"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-firewall-requirements-for-sql-server-with-lync-server-2013"></a>了解使用 Lync Server 2013 的 SQL Server 的防火墙要求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-21_

对于标准版部署，会在安装 Lync Server 2013 期间自动创建防火墙例外。 但是，对于企业版部署，必须在 SQL Server 后端服务器上手动配置防火墙例外。 TCP/CP 协议只允许给定端口对给定 IP 地址使用一次。 这意味着，对于基于 SQL Server 的服务器，可以为默认数据库实例分配默认 TCP 端口 1433。 对于其他任何实例，将需要使用 SQL Server 配置管理器分配唯一并且未使用的端口。 本主题包含以下内容：

  - 使用默认实例时防火墙例外的要求

  - SQL Server Browser 服务的防火墙例外要求

  - 使用命名实例时静态侦听端口的要求

<div>

## <a name="requirements-for-a-firewall-exception-when-using-the-default-instance"></a>使用默认实例时防火墙例外的要求

如果在部署 Lync Server 2013 时对任何数据库使用 SQL Server 默认实例，则使用以下防火墙规则要求来帮助确保从前端池到 SQL Server 默认实例的通信。


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
<th>Direction</th>
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


</div>

<div>

## <a name="requirements-for-a-firewall-exception-for-the-sql-server-browser-service"></a>SQL Server Browser 服务的防火墙例外要求

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
<th>Direction</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>UDP</p></td>
<td><p>1434</p></td>
<td><p>进货</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="requirements-for-static-listening-ports-when-using-named-instances"></a>使用命名实例时静态侦听端口的要求

在 SQL Server 配置中对支持 Lync Server 2013 的数据库使用命名实例时，可以使用 SQL Server 配置管理器配置静态端口。 将静态端口分配至每个命名实例后，在防火墙内为每个静态端口创建例外。


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
<th>Direction</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TCP</p></td>
<td><p>静态定义</p></td>
<td><p>进货</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="sql-server-documentation"></a>SQL Server 文档

Microsoft SQL Server 2012 文档提供了有关如何配置数据库的防火墙访问的详细指南。 有关 Microsoft SQL Server 2012 的详细信息，请参阅位于[http://go.microsoft.com/fwlink/p/?linkId=218031](http://go.microsoft.com/fwlink/p/?linkid=218031)的 "配置 Windows 防火墙以允许 SQL Server 访问"。

</div>

</div>

<span> </span>

</div>

</div>

</div>

