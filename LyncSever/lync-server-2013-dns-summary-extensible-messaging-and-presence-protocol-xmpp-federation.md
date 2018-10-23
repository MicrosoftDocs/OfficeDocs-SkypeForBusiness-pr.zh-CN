---
title: DNS 摘要 - 可扩展消息传递和状态协议 (XMPP) 联盟
TOCTitle: DNS 摘要 - 可扩展消息传递和状态协议 (XMPP) 联盟
ms:assetid: 0f720a2a-8ab5-43cc-882a-ab595ed3cec7
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ618368(v=OCS.15)
ms:contentKeyID: 49312015
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# DNS 摘要 - 可扩展消息传递和状态协议 (XMPP) 联盟

 

_**上一次修改主题：** 2015-03-09_

要为您的部署配置可扩展消息传递和状态协议 (XMPP)，您需要在外部 DNS 服务器中创建两条域名系统 (DNS) 记录，DNS 服务器随后将这些记录解析为您的边缘服务器或边缘池的访问边缘服务。

## 可扩展消息传递和状态协议的 DNS 摘要


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
<th>FQDN</th>
<th>IP 地址/FQDN 主机记录</th>
<th>映射位置/注释</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>外部 DNS/SRV/5269</p></td>
<td><p>_xmpp-server._tcp.contoso.com</p></td>
<td><p>xmpp.contoso.com</p></td>
<td><p>访问边缘服务或边缘池上的 XMPP 代理外部接口。根据需要对所有满足下列条件的内部 SIP 域重复此过程：其中包含启用了 Lync 的用户，并且通过全局策略、用户所在站点的站点策略或应用于启用了 Lync 的用户的用户策略来配置外部访问策略，允许与 XMPP 联系人进行联系。此外，还必须在 XMPP 联盟伙伴策略中配置允许的 XMPP 域。有关其他详细信息，请参阅<strong>另请参见</strong>中的主题</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/A</p></td>
<td><p>xmpp.contoso.com（例如）</p></td>
<td><p>您的承载 XMPP 代理的边缘服务器或边缘池上访问边缘服务的 IP 地址</p></td>
<td><p>指向承载 XMPP 代理服务的访问边缘服务或边缘池。通常情况下，您创建的 SRV 记录将指向此主机（A 或 AAAA）记录</p></td>
</tr>
</tbody>
</table>


## 另请参阅

#### 任务

[在 Lync Server 2013 中设置 XMPP 联盟](lync-server-2013-setting-up-xmpp-federation.md)  

#### 概念

[确定 Lync Server 2013 的 DNS 要求](lync-server-2013-determine-dns-requirements.md)

