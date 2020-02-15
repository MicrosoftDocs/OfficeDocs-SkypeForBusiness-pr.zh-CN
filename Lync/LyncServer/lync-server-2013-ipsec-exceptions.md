---
title: Lync Server 2013 IPsec 例外
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IPsec exceptions
ms:assetid: 241f1eca-6f2f-44de-90b1-2cb659cbe27c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425719(v=OCS.15)
ms:contentKeyID: 48183627
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: db7291674485dec30211d88e2739b0da89fb334f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035054"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ipsec-exceptions-in-lync-server-2013"></a>Lync Server 2013 中的 IPsec 例外

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-06-27_

对于已经部署了 Internet 协议安全性 (IPsec)（请参阅 IETF RFC 4301-4309）的企业网络，必须在用于传送音频、视频和全景视频的端口范围内禁用 IPsec。提出此建议的动机是需要避免由于 IPsec 协商而在分配媒体端口时产生任何延迟。

下表介绍了建议采用的 IPsec 例外设置。

### <a name="recommended-ipsec-exceptions"></a>建议采用的 IPsec 例外

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th>规则名称</th>
<th>源 IP</th>
<th>目标 IP</th>
<th>协议</th>
<th>源端口</th>
<th>目标端口</th>
<th>身份验证要求</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>A/V 边缘服务器内部入站</p></td>
<td><p>任意</p></td>
<td><p>A/V 边缘服务器内部</p></td>
<td><p>UDP 和 TCP</p></td>
<td><p>任意</p></td>
<td><p>任意</p></td>
<td><p>不进行身份验证</p></td>
</tr>
<tr class="even">
<td><p>A/V 边缘服务器外部入站</p></td>
<td><p>任意</p></td>
<td><p>A/V 边缘服务器外部</p></td>
<td><p>UDP 和 TCP</p></td>
<td><p>任意</p></td>
<td><p>任意</p></td>
<td><p>不进行身份验证</p></td>
</tr>
<tr class="odd">
<td><p>A/V 边缘服务器内部出站</p></td>
<td><p>A/V 边缘服务器内部</p></td>
<td><p>任意</p></td>
<td><p>UDP &amp; TCP</p></td>
<td><p>任意</p></td>
<td><p>任意</p></td>
<td><p>不进行身份验证</p></td>
</tr>
<tr class="even">
<td><p>A/V 边缘服务器外部出站</p></td>
<td><p>A/V 边缘服务器外部</p></td>
<td><p>任意</p></td>
<td><p>UDP 和 TCP</p></td>
<td><p>任意</p></td>
<td><p>任意</p></td>
<td><p>不进行身份验证</p></td>
</tr>
<tr class="odd">
<td><p>中介服务器入站</p></td>
<td><p>任意</p></td>
<td><p>中介</p>
<p>服务器（s）</p></td>
<td><p>UDP 和 TCP</p></td>
<td><p>任意</p></td>
<td><p>任意</p></td>
<td><p>不进行身份验证</p></td>
</tr>
<tr class="even">
<td><p>中介服务器出站</p></td>
<td><p>中介</p>
<p>服务器（s）</p></td>
<td><p>任意</p></td>
<td><p>UDP 和 TCP</p></td>
<td><p>任意</p></td>
<td><p>任意</p></td>
<td><p>不进行身份验证</p></td>
</tr>
<tr class="odd">
<td><p>会议助理入站</p></td>
<td><p>任意</p></td>
<td><p>运行会议助理的前端服务器</p></td>
<td><p>UDP 和 TCP</p></td>
<td><p>任意</p></td>
<td><p>任意</p></td>
<td><p>不进行身份验证</p></td>
</tr>
<tr class="even">
<td><p>会议助理出站</p></td>
<td><p>运行会议助理的前端服务器</p></td>
<td><p>任意</p></td>
<td><p>UDP 和 TCP</p></td>
<td><p>任意</p></td>
<td><p>任意</p></td>
<td><p>不进行身份验证</p></td>
</tr>
<tr class="odd">
<td><p>A/V 会议入站</p></td>
<td><p>任意</p></td>
<td><p>前端服务器</p></td>
<td><p>UDP 和 TCP</p></td>
<td><p>任意</p></td>
<td><p>任意</p></td>
<td><p>不进行身份验证</p></td>
</tr>
<tr class="even">
<td><p>A/V 会议出站</p></td>
<td><p>前端服务器</p></td>
<td><p>任意</p></td>
<td><p>UDP 和 TCP</p></td>
<td><p>任意</p></td>
<td><p>任意</p></td>
<td><p>不进行身份验证</p></td>
</tr>
<tr class="odd">
<td><p>Exchange 入站</p></td>
<td><p>任意</p></td>
<td><p>Exchange 统一消息</p></td>
<td><p>UDP 和 TCP</p></td>
<td><p>任意</p></td>
<td><p>任意</p></td>
<td><p>不进行身份验证</p></td>
</tr>
<tr class="even">
<td><p>应用程序共享服务器入站</p></td>
<td><p>任意</p></td>
<td><p>应用程序共享服务器</p></td>
<td><p>TCP</p></td>
<td><p>任意</p></td>
<td><p>任意</p></td>
<td><p>不进行身份验证</p></td>
</tr>
<tr class="odd">
<td><p>应用程序共享服务器出站</p></td>
<td><p>应用程序共享服务器</p></td>
<td><p>任意</p></td>
<td><p>TCP</p></td>
<td><p>任意</p></td>
<td><p>任意</p></td>
<td><p>不进行身份验证</p></td>
</tr>
<tr class="even">
<td><p>Exchange 出站</p></td>
<td><p>Exchange 统一消息</p></td>
<td><p>任意</p></td>
<td><p>UDP 和 TCP</p></td>
<td><p>任意</p></td>
<td><p>任意</p></td>
<td><p>不进行身份验证</p></td>
</tr>
<tr class="odd">
<td><p>客户端</p></td>
<td><p>任意</p></td>
<td><p>任意</p></td>
<td><p>UDP</p></td>
<td><p>指定的媒体端口范围</p></td>
<td><p>任意</p></td>
<td><p>不进行身份验证</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

