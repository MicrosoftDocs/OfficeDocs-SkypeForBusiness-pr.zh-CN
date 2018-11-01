---
title: Lync Server 2013：DNS 摘要 - 单一控制器
TOCTitle: DNS 摘要 - 单一控制器
ms:assetid: 790ecb56-92cd-41f4-baf6-c290a707aa4d
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205021(v=OCS.15)
ms:contentKeyID: 49313321
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 DNS 摘要 - 单一控制器

 

_**上一次修改主题：** 2015-03-09_

下表包含支持单个 控制器所需的 DNS 记录的摘要。 控制器的角色所需的 DNS 记录与 前端服务器所需的 DNS 记录相似。所需的记录数反映在 控制器证书上所需的使用者替代名称中。与 前端服务器不同， 控制器不承载用户帐户，也不承载 Mobility Services。

### 控制器所需的 DNS 记录

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>位置/类型/端口</th>
<th>FQDN/DNS 记录</th>
<th>IP 地址/FQDN</th>
<th>映射位置/注释</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>内部 DNS/A</p></td>
<td><p>dir01.contoso.net</p></td>
<td><p>控制器</p></td>
<td><p>用于复制和服务器到服务器的 控制器主机记录</p></td>
</tr>
<tr class="even">
<td><p>内部 DNS/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>控制器</p></td>
<td><p>边缘服务器的内部边缘接口中的入站会话初始协议 (SIP)</p></td>
</tr>
<tr class="odd">
<td><p>内部 DNS/A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>控制器</p></td>
<td><p>反向代理中的已发布电话拨入式 Web 服务</p></td>
</tr>
<tr class="even">
<td><p>内部 DNS/A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>控制器</p></td>
<td><p>反向代理中的已发布的会议 Web 服务</p></td>
</tr>
<tr class="odd">
<td><p>内部 DNS/A</p></td>
<td><p>webdirexternal.contoso.com</p></td>
<td><p>控制器</p></td>
<td><p>由 控制器的反向代理 Web 票证外部 Web 服务进行发布和定义</p></td>
</tr>
</tbody>
</table>

