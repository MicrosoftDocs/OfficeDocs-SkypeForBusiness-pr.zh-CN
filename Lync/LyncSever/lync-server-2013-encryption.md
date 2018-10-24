---
title: Lync Server 2013 加密
TOCTitle: Lync Server 2013 加密
ms:assetid: d18c74a6-385b-407b-98eb-0d525fa38fea
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn481135(v=OCS.15)
ms:contentKeyID: 59679366
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 加密

 

_**上一次修改主题：** 2016-12-08_

Microsoft Lync Server 2013 使用 TLS 和 MTLS 来加密即时消息。无论通信是限制在内部网络还是跨内部网络外围，所有服务器到服务器的通信都需要使用 MTLS。TLS 是可选的，但强烈建议在中介服务器与媒体网关之间使用 TLS。如果在此链接上配置了 TLS，则 MTLS 是必需的。因此，必须使用 中介服务器 信任的 CA 颁发的证书配置网关。

客户端到客户端的通信要求取决于该通信是否跨内部企业防火墙。严格意义上的内部通信既可以使用 TLS（加密即时消息），也可以使用 TCP（不加密即时消息）。

下表汇总了每种类型的通信的协议要求。

### 通信保护

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>通信类型</th>
<th>保护协议</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>服务器到服务器</p></td>
<td><p>MTLS</p></td>
</tr>
<tr class="even">
<td><p>客户端到服务器</p></td>
<td><p>TLS</p></td>
</tr>
<tr class="odd">
<td><p>即时消息和状态</p></td>
<td><p>TLS（如果针对 TLS 配置）</p></td>
</tr>
<tr class="even">
<td><p>音频、视频和媒体的桌面共享</p></td>
<td><p>SRTP</p></td>
</tr>
<tr class="odd">
<td><p>桌面共享（信号）</p></td>
<td><p>TLS</p></td>
</tr>
<tr class="even">
<td><p>Web 会议</p></td>
<td><p>TLS</p></td>
</tr>
<tr class="odd">
<td><p>会议内容下载、通讯簿下载和通讯组扩展</p></td>
<td><p>HTTPS</p></td>
</tr>
</tbody>
</table>


## 媒体加密

媒体通信是使用安全 RTP (SRTP) 进行加密的，SRTP 是为 RTP 通信提供保密性、身份验证和重播攻击保护的实时传输协议 (RTP) 的配置文件。SRTP 使用媒体中继身份验证服务生成的会话密钥响应服务器请求（代表媒体参与者）的成功身份验证。会话密钥受前端服务器提供给媒体中继身份验证服务的商定的用户名和密码保护，并且通过受 TLS 保护的 SIP 通道发送给参与者。解密具有媒体中继服务使用的用户名和密码的受保护的会话密钥，并通过参与者的 TLS 证书和受保护的 SIP 通道以安全方式提供，可允许参与者解密 SRTP 流。此外，中介服务器与其内部下一个跃点之间的双向媒体流也是使用 SRTP 进行加密的。中介服务器与媒体网关之间的双向媒体流未经加密。中介服务器能够支持对媒体网关进行加密，但该网关必须支持 MTLS 和证书存储。

> [!NOTE]  
> Windows Live Messenger 的新版本支持音频/视频 (A/V)。如果要实现 Windows Live Messenger 与 A/V 联盟，则还必须修改 Lync Server 加密级别。默认情况下，加密级别为“必需”。必须使用 Lync Server 命令行管理程序 将此设置更改为“受支持”。有关详细信息，请参阅部署文档中的<a href="lync-server-2013-deploying-external-user-access.md">在 Lync Server 2013 中部署外部用户访问</a>。



在 Microsoft Lync 2013 与 Windows Live 客户端之间未对音频和视频媒体流量进行加密。

## FIPS

如果将 Windows Server 操作系统配置为使用美国联邦信息处理标准 (FIPS) 140-2 算法进行系统加密，则 Lync Server 2013 和 Microsoft Exchange Server 2013 支持 FIPS 140-2 算法。若要实现 FIPS 支持，则必须将每个运行 Lync Server 2013 的服务器配置为支持它。有关 FIPS 兼容算法和如何实现 FIPS 支持的详细信息，请参阅 Microsoft 知识库文章 811833“在 Windows XP 和 Windows 的更高版本中启用‘系统加密：使用 FIPS 兼容的算法来加密、散列和签名’安全设置的影响”，网址为 [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833)。有关 Exchange 2010 中的 FIPS 140-2 支持和限制的详细信息，请参阅“Exchange 2010 SP1 和符合 FIPS 的算法的支持”，网址为 [http://go.microsoft.com/fwlink/p/?LinkId=205335](http://go.microsoft.com/fwlink/p/?linkid=205335)。

