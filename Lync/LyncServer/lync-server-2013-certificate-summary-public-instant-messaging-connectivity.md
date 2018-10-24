---
title: 证书摘要 - 公共即时消息连接
TOCTitle: 证书摘要 - 公共即时消息连接
ms:assetid: 2b3687ee-50c2-4c1c-880e-8dcf8bd4f309
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ618370(v=OCS.15)
ms:contentKeyID: 49312343
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 证书摘要 - 公共即时消息连接

 

_**上一次修改主题：** 2015-03-09_

若要配置公共即时消息连接的证书，您应该首先注意到这与其他 SIP 联盟类型或标准边缘服务器证书没有区别，只是 America Online (AOL) 要求唯一的证书配置。除了普通的服务器增强型密钥使用 (EKU) 外，America Online 还要求一个或多个证书（对于边缘池）也包含客户端 EKU。客户端 EKU 是对证书的补充，并且是分配给您的边缘服务器的外部公共证书的一部分。

## 证书摘要 – 公共即时消息连接


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
<td><p>访问/边缘外部</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>sip.contoso.com</p>
<p>webcon.contoso.com</p>
<p>sip.fabrikam.com</p></td>
<td><p>如果要部署与 AOL 的公共 IM 连接，则证书必须来自公共 CA，并且必须具有服务器 EKU 和客户端 EKU。该证书分配给以下各项的外部边缘服务器接口：</p>
<ul>
<li><p>访问边缘服务</p></li>
<li><p>Web 会议边缘服务</p></li>
<li><p>A/V 边缘服务</p></li>
</ul>
<p>请注意，根据拓扑生成器中的定义，SAN 将自动添加到证书中。根据需要为其他 SIP 域和其他需要支持的条目添加 SAN 条目。将在 SAN 中复制使用者名称，并且该名称必须在正确的操作中显示。</p></td>
</tr>
</tbody>
</table>


## 另请参阅

#### 概念

[Lync Server 2013 中的外部用户访问方案](lync-server-2013-scenarios-for-external-user-access.md)

