---
title: 'Lync Server 2013: 规划公共即时消息连接'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for public instant messaging connectivity
ms:assetid: e75e8884-05c7-414a-8014-bc9aa8126fb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205349(v=OCS.15)
ms:contentKeyID: 48185698
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4432484fbd6056d51a38090a18dbe106851d7c0f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824573"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-public-instant-messaging-connectivity-in-lync-server-2013"></a>在 Lync Server 2013 中规划公共即时消息连接

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-10-07_

公用即时消息连接是一种联盟类, 并配置为允许您的内部和外部 Lync Server 2013 用户从以下任何内容添加联系人:

  - Messenger 联系人

  - Yahoo\! 联系人

  - 美国在线 (AOL) 联系人

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>从2012年9月1日起, Microsoft Lync 公共 IM 连接用户订购许可证 (PIC USL) 不再可用于购买新的或续订协议。 具有活动许可证的客户将能够继续与 Yahoo! 进行联盟 Messenger, 直到服务关闭日期。 AOL 和 Yahoo! 的有效期结束日期为2014年6月 已宣布。 有关详细信息, 请参阅<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公共即时消息连接支持</A>。</P>
> <LI>
> <P>PIC USL 是 Lync Server 或 Office 通信服务器与 Yahoo! 联合所需的每用户、每月订阅许可证。 Messenger. Microsoft 提供此服务的能力已由 Yahoo! 的支持 (将不会续订的底层协议) 提供。</P>
> <LI>
> <P>Lync 比以往更多, 是一种强大的工具, 用于跨组织和全球各地的人员进行连接。 与 Windows Live Messenger 的联盟不需要除 Lync 标准 CAL 之外的其他用户/设备许可证。 Skype 联盟将添加到此列表, 使 Lync 用户可以通过 IM 和语音与成百上千人联系。</P></LI></UL>



</div>

此类联合需要以下规划注意事项:

  - 除了即时消息外, Windows Live Messenger 用户可以与 Lync Server 2013 用户进行对等音频/视频通信。 边缘服务器必须满足特定的端口和协议要求。 有关详细信息, 请参阅[确定 Lync Server 2013 的外部 A/V 防火墙和端口要求](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)。

  - Yahoo 即时消息没有独特的要求, 除了通常用于提供联合的典型边缘服务器的规划和部署中。

  - 北美洲联机要求分配给 Access Edge 服务的 Edge 服务器证书具有客户端增强型密钥用法 (EKU)。

<div>

## <a name="in-this-section"></a>本节内容

  - [证书摘要-Lync Server 2013 中的公共即时消息连接](lync-server-2013-certificate-summary-public-instant-messaging-connectivity.md)

  - [端口摘要-Lync Server 2013 中的公共即时消息连接](lync-server-2013-port-summary-public-instant-messaging-connectivity.md)

  - [DNS 摘要-Lync Server 2013 中的公共即时消息连接](https://technet.microsoft.com/en-us/library/jj618375\(v=ocs.15\))

</div>

</div>

<span> </span>

</div>

</div>

</div>

