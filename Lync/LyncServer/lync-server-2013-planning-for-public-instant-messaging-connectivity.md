---
title: Lync Server 2013：规划公共即时消息连接
description: Lync Server 2013：规划公共即时消息连接。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for public instant messaging connectivity
ms:assetid: e75e8884-05c7-414a-8014-bc9aa8126fb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205349(v=OCS.15)
ms:contentKeyID: 48185698
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a020a291a39d78aea9271926c99b508a8cd9827
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549288"
---
# <a name="planning-for-public-instant-messaging-connectivity-in-lync-server-2013"></a>在 Lync Server 2013 中规划公共即时消息连接

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-10-07_

公共即时消息连接是一类联合，配置为允许您的内部和外部 Lync Server 2013 用户从以下任一项添加联系人：

  - Messenger 联系人

  - Yahoo\! contacts

  - America Online (AOL) 联系人

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>从2012年9月1日起，Microsoft Lync 公共 IM 连接用户订阅许可证 (PIC USL) 不再可用于购买新的或更新的协议。 拥有主动许可证的客户将能够继续与 Yahoo！联合联合 信使，直到服务关闭日期。 AOL 和 Yahoo！的生命周期结束日期为2014年6月 已宣布。 有关详细信息，请参阅 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的支持公用即时信使连接</A>。</P>
> <LI>
> <P>PIC USL 是 Lync Server 或 Office 通信服务器与 Yahoo！联合所需的每用户、每月订阅许可证。 Messenger. Microsoft 提供此服务的能力因 Yahoo！中的支持而异，将不会续订的底层协议。</P>
> <LI>
> <P>Lync 是前所未有的强大工具，用于跨组织和世界各地的个人进行连接。 与 Windows Live Messenger 的联盟不需要除 Lync Standard CAL 之外的其他用户/设备许可证。 Skype 联盟将添加到此列表中，使 Lync 用户能够通过即时消息和语音访问数百个人。</P></LI></UL>



</div>

此类联盟需要规划以下注意事项：

  - 除了即时消息之外，Windows Live Messenger 用户可以与 Lync Server 2013 用户进行对等音频/视频通信。 您的边缘服务器必须满足特定的端口和协议要求。 有关详细信息，请参阅 [确定 Lync Server 2013 的外部 A/V 防火墙和端口要求](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)。

  - Yahoo 即时消息没有独特的要求，而不是通常在提供联合的典型边缘服务器的规划和部署中使用的要求。

  - 美洲在线要求分配给访问边缘服务的边缘服务器证书具有客户端增强型密钥用法 (EKU) 。

<div>

## <a name="in-this-section"></a>本部分内容

  - [证书摘要-Lync Server 2013 中的公共即时消息连接](lync-server-2013-certificate-summary-public-instant-messaging-connectivity.md)

  - [端口摘要-Lync Server 2013 中的公共即时消息连接](lync-server-2013-port-summary-public-instant-messaging-connectivity.md)

  - [DNS 摘要-Lync Server 2013 中的公共即时消息连接](https://technet.microsoft.com/library/jj618375\(v=ocs.15\))

</div>

</div>

<span> </span>

</div>

</div>

</div>

