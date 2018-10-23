---
title: Lync Server 2013：证书摘要 - 反向代理
TOCTitle: 证书摘要 - 反向代理
ms:assetid: f2b9a53f-aead-413d-81e9-4a294a010fbb
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205381(v=OCS.15)
ms:contentKeyID: 49314723
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的证书摘要 - 反向代理

 

_**上一次修改主题：** 2015-03-09_

反向代理的证书要求比 边缘服务器的证书要求简单许多。所提供的流程图显示了必需的要求。随附表显示与我们已在 边缘服务器讨论中审查的方案相关的典型证书使用者名称和使用者替代名称。有关 边缘服务器方案的更多详细信息，请参阅： [Lync Server 2013 中的外部用户访问方案](lync-server-2013-scenarios-for-external-user-access.md)。

**反向代理的证书流程图**

![边缘服务器的流程图](images/JJ205381.026045d7-1b4b-4651-b32f-2d43a7161198(OCS.15).jpg "边缘服务器的流程图")

### 反向代理：外部接口

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>组件</th>
<th>使用者名称</th>
<th>使用者替代名称 (SAN)/顺序</th>
<th>备注</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>反向代理</p></td>
<td><p>webext.contoso.com</p></td>
<td><p>webext.contoso.com</p>
<p>webdirext.contoso.com</p>
<p>dialin.contoso.com</p>
<p>meet.contoso.com</p>
<p>officewebapps01.contoso.com</p>
<p>lyncdiscover.contoso.com</p>
<p>（可选）:*.contoso.com</p></td>
<td><p>证书必须由公共 CA 颁发，并且必须包含服务器 EKU。服务包括通讯簿服务、用于会议的通讯组扩展 Office Web Apps 和 Lync IP 设备发布规则。使用者替代名称包括：</p>
<ul>
<li><p>适用于 前端服务器或 前端池的外部 Web 服务 FQDN</p></li>
<li><p>适用于控制器或控制器池的外部 Web 服务 FQDN</p></li>
<li><p>电话拨入式会议</p></li>
<li><p>联机会议发布规则</p></li>
<li><p>用于会议的 Office Web Apps</p></li>
<li><p>Lyncdiscover（自动发现）</p></li>
</ul>
<p>可选通配符将替换 meet 和 dialin SAN</p></td>
</tr>
</tbody>
</table>

