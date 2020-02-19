---
title: Lync Server 2013：端口摘要-单个控制器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Single Director
ms:assetid: 079c1414-723f-4499-b7d4-a0d7121c1626
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204648(v=OCS.15)
ms:contentKeyID: 48183322
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8515785f66101df3af0d7d35de565ba344e2b91a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139173"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---single-director-in-lync-server-2013"></a>Lync Server 2013 中的端口摘要-单一控制器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-20_

单个控制器的防火墙端口要求由用于从内部接口或反向代理的面向内部网络中的控制器建立通信的端口组成。 Microsoft Lync Server 2013 默认情况下需要从反向代理向控制器以及前端池和前端服务器打开端口 HTTP/TCP 8080 和 HTTPS/TCP 4443。 此外，还必须存在从边缘服务器内部接口到控制器以及前端池和前端服务器的会话初始协议（SIP）通信。 SIP 协议使用从边缘服务器到前端池和前端服务器的 SIP/MTLS/TCP 5061。 还必须创建一个允许从 Director、前端池和前端服务器到边缘服务器内部接口的 SIP/MTLS/TCP 5061 通信的规则。

### <a name="single-director-ports-and-protocols-for-firewall-definitions"></a>防火墙定义的单个控制器端口和协议

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>角色/协议/TCP 或 UDP/端口</th>
<th>源 IP 地址</th>
<th>目标 IP 地址</th>
<th>备注</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP 8080</p></td>
<td><p>反向代理内部接口</p></td>
<td><p>控制器</p></td>
<td><p>与反向代理的外部一方最初接收到的通信将发送到控制器和前端服务器 web 服务</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP 4443</p></td>
<td><p>反向代理内部接口</p></td>
<td><p>控制器</p></td>
<td><p>与反向代理的外部一方最初接收到的通信将发送到控制器和前端服务器 web 服务</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 444</p></td>
<td><p>控制器</p></td>
<td><p>前端服务器或前端池</p></td>
<td><p>控制器与前端服务器之间的服务器间通信</p></td>
</tr>
<tr class="even">
<td><p>HTTP/TCP 80</p></td>
<td><p>内部客户端</p></td>
<td><p>控制器 web 服务</p></td>
<td><p>控制器向内部和外部客户端提供 web 服务。</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 443</p></td>
<td><p>内部客户端</p></td>
<td><p>控制器 web 服务</p></td>
<td><p>控制器向内部和外部客户端提供 web 服务。</p></td>
</tr>
<tr class="even">
<td><p>SIP/MTLS/TCP 5061</p></td>
<td><p>边缘服务器内部接口</p></td>
<td><p>控制器</p></td>
<td><p>从边缘服务器到控制器以及前端服务器的 SIP 通信。</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50001</p></td>
<td><p>任意</p></td>
<td><p>边缘服务器内部接口</p></td>
<td><p>集中日志记录服务控制器 (ClsController.exe) 或代理 (ClasAgent.exe) 命令和日志集合</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50002</p></td>
<td><p>任意</p></td>
<td><p>边缘服务器内部接口</p></td>
<td><p>集中日志记录服务控制器 (ClsController.exe) 或代理 (ClasAgent.exe) 命令和日志集合</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50003</p></td>
<td><p>任意</p></td>
<td><p>边缘服务器内部接口</p></td>
<td><p>集中日志记录服务控制器 (ClsController.exe) 或代理 (ClasAgent.exe) 命令和日志集合</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

