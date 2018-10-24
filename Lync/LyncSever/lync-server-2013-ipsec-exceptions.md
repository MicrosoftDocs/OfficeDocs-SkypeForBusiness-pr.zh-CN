---
title: Lync Server 2013 中的 IPsec 例外
TOCTitle: Lync Server 2013 中的 IPsec 例外
ms:assetid: 241f1eca-6f2f-44de-90b1-2cb659cbe27c
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425719(v=OCS.15)
ms:contentKeyID: 49312261
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 IPsec 例外

 

_**上一次修改主题：** 2015-03-09_

对于已经部署了 Internet 协议安全性 (IPsec)（请参阅 IETF RFC 4301-4309）的企业网络，必须在用于传送音频、视频和全景视频的端口范围内禁用 IPsec。提出此建议的动机是需要避免由于 IPsec 协商而在分配媒体端口时产生任何延迟。

下表介绍了建议采用的 IPsec 例外设置。

### 建议采用的 IPsec 例外

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
<td><p>UDP 和 TCP</p></td>
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
<p>服务器</p></td>
<td><p>UDP 和 TCP</p></td>
<td><p>任意</p></td>
<td><p>任意</p></td>
<td><p>不进行身份验证</p></td>
</tr>
<tr class="even">
<td><p>中介服务器出站</p></td>
<td><p>中介</p>
<p>服务器</p></td>
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

