---
title: 端口摘要 - 可扩展消息传递和状态协议 (XMPP) 联盟
TOCTitle: 端口摘要 - 可扩展消息传递和状态协议 (XMPP) 联盟
ms:assetid: 62e98fab-7add-4983-a3fa-dbe74e1c3849
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ618371(v=OCS.15)
ms:contentKeyID: 49313045
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 端口摘要 - 可扩展消息传递和状态协议 (XMPP) 联盟

 

_**上一次修改主题：** 2015-03-09_

为边缘服务器上部署的可扩展消息传递和状态协议 (XMPP) 定义的端口和协议允许从 XMPP 联盟伙伴到边缘服务器的通信，还允许从边缘服务器到 XMPP 联盟伙伴的通信。此外，还在从前端服务器或前端池到边缘服务器或边缘池的面向内部的防火墙上定义了规则。

## 可扩展消息传递和状态协议的防火墙摘要


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>协议/TCP 或 UDP/端口</th>
<th>源（IP 地址）</th>
<th>目标（IP 地址）</th>
<th>备注</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/TCP/5269</p></td>
<td><p>任意</p></td>
<td><p>访问边缘服务接口 IP 地址</p></td>
<td><p>XMPP 的标准服务器到服务器通信端口。允许边缘服务器 XMPP 代理到联盟 XMPP 伙伴的通信</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>访问边缘服务接口 IP 地址</p></td>
<td><p>任意</p></td>
<td><p>XMPP 的标准服务器到服务器通信端口。允许边缘服务器 XMPP 代理到联盟 XMPP 伙伴的通信</p></td>
</tr>
<tr class="odd">
<td><p>XMPP/MTLS/23456</p></td>
<td><p>任意</p></td>
<td><p>内部边缘服务器接口 IP</p></td>
<td><p>从前端服务器或前端池上的 XMPP 网关到边缘服务器的内部 XMPP 流量</p></td>
</tr>
</tbody>
</table>


## 另请参阅

#### 任务

[Lync Server 2013 中的示例 XMPP 配置 – 与 Google Talk 的 XMPP 联盟](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  

#### 其他资源

[在 Lync Server 2013 中管理组织的 XMPP 联盟伙伴](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)

