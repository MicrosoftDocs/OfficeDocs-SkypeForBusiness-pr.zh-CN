---
title: 'Lync Server 2013: 加密'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Encryption for Lync Server 2013
ms:assetid: d18c74a6-385b-407b-98eb-0d525fa38fea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481135(v=OCS.15)
ms:contentKeyID: 59893874
ms.date: 09/14/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 01c989213b050bdb536e95a8a42e8f7b35292eaf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830233"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="encryption-for-lync-server-2013"></a>Lync Server 2013 的加密

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2017-09-14_

Microsoft Lync Server 2013 使用 TLS 和 MTLS 对即时消息进行加密。 无论通信是限制在内部网络还是跨内部网络外围，所有服务器到服务器的通信都需要使用 MTLS。 TLS 是可选的, 但强烈建议在中介服务器和媒体网关之间使用 TLS。 如果在此链接上配置了 TLS，则 MTLS 是必需的。 因此, 网关必须配置来自中介服务器信任的 CA 的证书。

<div>


> [!NOTE]  
> 2014 年发布了关于 SSL 3.0 的安全公告。 在 Lync Server 2013 中禁用 SSL 3.0 是受支持的选项。 若要了解有关安全公告的详细信息<A class=uri href="https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/">https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/</A>, 请参阅。



</div>

<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="安全" alt="security" />安全说明:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>为确保使用最强的加密协议, Lync Server 2013 将按以下顺序向客户端提供 TLS 加密协议: <strong>tls 1.2</strong> 、 <strong>tls 1.1</strong>、 <strong>tls 1.0</strong>。 TLS 是 Lync Server 2013 的一个重要方面, 因此它是维护受支持的环境所必需的。</td>
</tr>
</tbody>
</table>


</div>

客户端到客户端流量的要求取决于该流量是否与内部公司防火墙相交叉。 严格的内部流量可以使用 TLS, 在这种情况下, 会对即时消息进行加密或 TCP, 在这种情况下不会进行加密。

下表汇总了每种类型的通信的协议要求。

### <a name="traffic-protection"></a>通信保护

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
<td><p>TLS（如果已配置 TLS）</p></td>
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


<div>

## <a name="media-encryption"></a>媒体加密

媒体通信使用安全 RTP (SRTP) 进行加密，SRTP 是为 RTP 通信提供保密性、身份验证和重播攻击保护的实时传输协议 (RTP) 的配置文件。 此外，中介服务器与其内部下一个跃点之间的双向媒体流也使用 SRTP 进行加密。 默认情况下, 中介服务器和媒体网关之间的两个方向的媒体均未加密。 中介服务器能够支持对媒体网关进行加密，但该网关必须支持 MTLS 和证书存储。

<div>


> [!NOTE]  
> 新版本的 Windows Live Messenger 支持音频/视频 (A/V)。 如果要实现与 Windows Live Messenger 的 A/V 联合, 还必须修改 Lync 服务器加密级别。 默认情况下，加密级别为“必需”。 您必须使用 Lync Server 命令行管理程序将此设置更改为 "支持"。 有关详细信息, 请参阅部署文档中<A href="lync-server-2013-deploying-external-user-access.md">Lync Server 2013 中的 "部署外部用户访问</A>"。



</div>

音频和视频媒体流量不会在 Microsoft Lync 2013 和 Windows Live 客户端之间加密。

</div>

<div>

## <a name="fips"></a>FIPS

如果将 Windows Server 操作系统配置为使用适用于系统加密的 FIPS 140-2 算法, 则 Lync Server 2013 和 Microsoft Exchange Server 2013 将使用联邦信息处理标准 (FIPS) 140-2 算法的支持操作。 若要实现 FIPS 支持, 必须配置运行 Lync Server 2013 的每台服务器以支持它。 有关使用 FIPS 兼容的算法以及如何实现 FIPS 支持的详细信息, 请参阅 Microsoft 知识库文章 811833: 启用 "系统加密: 将 FIPS 兼容的算法用于加密、哈希和签名" 安全的效果在 Windows XP 和更高版本的 Windows 中设置[http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833)。 有关 FIPS 140-2 支持和 Exchange 2010 中的限制的详细信息, 请参阅 Exchange 2010 SP1 和支持 FIPS 兼容[https://go.microsoft.com/fwlink/p/?LinkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335)的算法。

</div>

</div>

<span> </span>

</div>

</div>

</div>

