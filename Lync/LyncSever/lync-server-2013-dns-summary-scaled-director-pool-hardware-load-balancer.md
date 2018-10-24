---
title: Lync Server 2013：DNS 摘要 - 扩展的控制器池、硬件负载平衡器
TOCTitle: DNS 摘要 - 扩展的控制器池、硬件负载平衡器
ms:assetid: 08ba48e6-bfa1-4ab0-bc89-d58ddb9c20af
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204655(v=OCS.15)
ms:contentKeyID: 49311923
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 DNS 摘要 - 扩展的控制器池、硬件负载平衡器

 

_**上一次修改主题：** 2015-03-09_

下表包含支持硬件负载平衡 控制器所需的 DNS 记录的摘要。 控制器的角色需要与 前端服务器类似的 DNS 记录。所需的记录数体现在 控制器证书上所需的使用者替代名称中。与 前端服务器不同， 控制器池不承载用户帐户，也不承载 Mobility Services。

### 使用硬件负载平衡器和 DNS 负载平衡的控制器池所需的 DNS 记录

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
<td><p>用于复制和服务器到服务器通信的控制器主机记录</p></td>
</tr>
<tr class="even">
<td><p>内部 DNS/A</p></td>
<td><p>dirpool01.contoso.net</p></td>
<td><p>控制器池的池 HLB VIP</p></td>
<td><p>DNS 负载平衡 控制器池的主机记录</p></td>
</tr>
<tr class="odd">
<td><p>内部 DNS/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>控制器池 HLB VIP</p></td>
<td><p>边缘服务器内部接口的入站会话初始协议 (SIP)</p></td>
</tr>
<tr class="even">
<td><p>内部 DNS/A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>控制器池 HLB VIP</p></td>
<td><p>反向代理发布的经过硬件负载平衡的 dialin Web 服务</p></td>
</tr>
<tr class="odd">
<td><p>内部 DNS/A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>控制器池 HLB VIP</p></td>
<td><p>反向代理发布的经过硬件负载平衡的 meet Web 服务</p></td>
</tr>
<tr class="even">
<td><p>内部 DNS/A</p></td>
<td><p>webdirexternal.contoso.com</p></td>
<td><p>控制器池 HLB VIP</p></td>
<td><p>反向代理 Web 票证外部 Web 服务为控制器池发布和定义的硬件负载平衡</p></td>
</tr>
</tbody>
</table>

