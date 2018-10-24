---
title: 规划公共即时消息连接
TOCTitle: 规划公共即时消息连接
ms:assetid: e75e8884-05c7-414a-8014-bc9aa8126fb7
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205349(v=OCS.15)
ms:contentKeyID: 49314572
ms.date: 03/09/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 规划公共即时消息连接

 

_**上一次修改主题：** 2017-03-09_

公共即时消息连接是一类联盟，配置该连接是为了允许内外部 Lync Server 2013 用户从以下任何用户中添加联系人：

  - Messenger 联系人

  - Yahoo\! 联系人

  - America Online (AOL) 联系人

> [!IMPORTANT]  
> <ul>
> <li><p>自 2012 年 9 月 1 日起，Microsoft Lync 公共 IM 连接用户订阅许可证 (PIC USL) 将不再用于购买新的或续订协议。具有活动许可证的客户将能继续与 Yahoo! Messenger 联盟，直到服务关闭日期。AOL 和 Yahoo! 的生命周期结束日期已宣布，为 2014 年 6 月。有关详细信息，请参阅 <a href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公共即时消息连接支持</a>。</p></li>
> <li><p>PIC USL 是 Lync Server 或 Office Communications Server 与 Yahoo! Messenger 联盟所必需的每用户、每月订阅许可证。Microsoft 是否能够提供此服务视 Yahoo! 的支持而定，将不续订 Yahoo! 的底层协议。</p></li>
> <li><p>与以往相比，Lync 是一个更强大的工具，可用于跨多个组织进行联系以及与世界各地的各个用户进行联系。与 Windows Live Messenger 联盟无需 Lync Standard CAL 之外的其他任何用户/设备许可证。Skype 联盟将添加到此列表，使 Lync 用户能够通过 IM 和语音与数亿人联系。</p></li>
> </ul>

此类联盟需要规划以下注意事项：

  - Windows Live Messenger 用户可与 Lync Server 2013 用户进行对等音频/可视通信以及即时消息传递。您的边缘服务器必须满足特定端口和协议要求。有关详细信息，请参阅[确定 Lync Server 2013 的外部 A/V 防火墙和端口要求](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)。

  - Yahoo 即时消息除通常在规划和部署提供联盟的典型边缘服务器时使用的要求之外，没有其他独特要求。

  - America Online 要求分配到 访问边缘服务 的 边缘服务器 证书具有一个客户端增强型密钥使用 (EKU)。

## 本部分内容

  - [证书摘要 - 公共即时消息连接](lync-server-2013-certificate-summary-public-instant-messaging-connectivity.md)

  - [端口摘要 - 公共即时消息连接](lync-server-2013-port-summary-public-instant-messaging-connectivity.md)

  - [DNS 摘要 - 公共即时消息连接](https://technet.microsoft.com/zh-cn/library/jj618375\(v=ocs.15\))

