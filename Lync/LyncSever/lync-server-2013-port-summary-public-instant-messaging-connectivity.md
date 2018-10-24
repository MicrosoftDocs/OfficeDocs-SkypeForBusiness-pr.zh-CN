---
title: 端口摘要 - 公共即时消息连接
TOCTitle: 端口摘要 - 公共即时消息连接
ms:assetid: f46756ec-1401-4ca2-a4a4-5cd28bcfdc7f
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ618376(v=OCS.15)
ms:contentKeyID: 49314743
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 端口摘要 - 公共即时消息连接

 

_**上一次修改主题：** 2015-03-09_

若要配置支持公共即时消息连接所必需的端口和协议的防火墙，首先应注意 SIP/MTLS/TCP 5061 具有双向性，对于可联系 Lync 客户端的公共 IM 提供商（或对于 Lync 可联系公共 IM 联系人）的联系人功能进行了解释。

Windows Live Messenger 可参与和 Lync 客户端的音频/视频通信。这对您通常作为外部用户在防火墙上支持 Lync 客户端非常类似的防火墙端口和协议配置进行了解释。

> [!IMPORTANT]
> 与以往相比，Lync 是一个更强大的工具，可用于跨多个组织进行联系以及与世界各地的各个用户进行联系。与 Windows Live Messenger 联盟无需 Lync 标准版客户端访问许可证 (CAL) 之外的其他任何用户/设备许可证。Skype 联盟将添加到此列表，使 Lync 用户能够通过 IM 和语音与数亿人联系。<br />
> 与 Messenger 客户端联系人的联盟将于 2013 年 3 月 15 日正式结束，中国内地除外。Skype 将成为以前使用 Messenger 的联盟用户的联盟客户端。


## 防火墙摘要 – 公共即时消息连接


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
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>访问/SIP(MTLS)/TCP/5061</p></td>
<td><p>公共 IM 连接合作伙伴</p></td>
<td><p>边缘服务器访问接口</p></td>
<td><p>用于使用 SIP 的联盟和公共 IM 连接。</p></td>
</tr>
<tr class="even">
<td><p>访问/SIP(MTLS)/TCP/5061</p></td>
<td><p>边缘服务器访问接口</p></td>
<td><p>公共 IM 连接合作伙伴</p></td>
<td><p>用于使用 SIP 的联盟和公共 IM 连接。</p></td>
</tr>
<tr class="odd">
<td><p>访问/SIP(TLS)/TCP/443</p></td>
<td><p>客户端</p></td>
<td><p>边缘服务器访问接口</p></td>
<td><p>外部用户访问的客户端到服务器 SIP 通信。</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50,000-59,999</p></td>
<td><p>边缘服务器访问接口</p></td>
<td><p>Live Messenger 客户端</p></td>
<td><p>用于与 Windows Live Messenger 的 A/V 会话，前提是配置了公共 IM 连接。</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN,MSTURN/UDP/3478</p></td>
<td><p>边缘服务器访问接口</p></td>
<td><p>Live Messenger 客户端</p></td>
<td><p>与 Windows Live Messenger 的公共 IM 连接必需的。</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN,MSTURN/UDP/3478</p></td>
<td><p>Live Messenger 客户端</p></td>
<td><p>边缘服务器访问接口</p></td>
<td><p>与 Windows Live Messenger 的公共 IM 连接必需的。</p></td>
</tr>
</tbody>
</table>


## 另请参阅

#### 概念

[Lync Server 2013 中的外部用户访问方案](lync-server-2013-scenarios-for-external-user-access.md)  
[确定 Lync Server 2013 的外部 A/V 防火墙和端口要求](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

