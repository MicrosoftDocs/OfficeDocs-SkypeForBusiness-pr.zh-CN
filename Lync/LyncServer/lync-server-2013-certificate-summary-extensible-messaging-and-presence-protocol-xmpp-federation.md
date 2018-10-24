---
title: 证书摘要 - 可扩展消息传递和状态协议 (XMPP) 联盟
TOCTitle: 证书摘要 - 可扩展消息传递和状态协议 (XMPP) 联盟
ms:assetid: b059a34e-99df-40af-91fe-fe2aa52841f6
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ618374(v=OCS.15)
ms:contentKeyID: 49313965
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 证书摘要 - 可扩展消息传递和状态协议 (XMPP) 联盟

 

_**上一次修改主题：** 2015-03-09_

用于启用并与可扩展消息传递和状态协议 (XMPP) 伙伴建立通信的证书要求需要 XMPP 域的其他记录。作为使用者替代名称 (SAN) 包含在证书上的记录将成为可以参与 XMPP 通信的域。如果要针对整个域启用 XMPP，则该域可以是根级别域（例如，contoso.com），或者要针对用户的子集启用 XMPP，该域也可以是选定的子域（例如，corp.contoso.com、finance.contoso.com）。

## 可扩展消息传递和状态协议的证书摘要


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
<td><p>分配给边缘服务器或边缘池的访问边缘服务</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>webcon.contoso.com</p>
<p>sip.contoso.com</p>
<p>sip.fabrikam.com</p>
<p>contoso.com</p></td>
<td><p>前三个 SAN 条目是完整边缘服务器的常规 SAN 条目。contoso.com 是在根域级别与 XMPP 伙伴联盟所需的条目。此条目将允许 XMPP 用于后缀为 contoso.com 的所有域。</p></td>
</tr>
</tbody>
</table>


## 另请参阅

#### 任务

[Lync Server 2013 中的示例 XMPP 配置 – 与 Google Talk 的 XMPP 联盟](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  

#### 概念

[在 Lync Server 2013 中规划边缘服务器证书](lync-server-2013-plan-for-edge-server-certificates.md)  

#### 其他资源

[为 Lync Server 2013 设置边缘证书](lync-server-2013-set-up-edge-certificates.md)  
[Request-CsCertificate](https://docs.microsoft.com/en-us/powershell/module/skype/Request-CsCertificate)  
[Set-CsCertificate](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCertificate)

