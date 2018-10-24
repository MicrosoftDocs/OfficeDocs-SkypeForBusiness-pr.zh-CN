---
title: Lync Server 2013：公共即时消息支持
TOCTitle: 公共即时消息支持
ms:assetid: 1f45163b-52c6-4a78-b9c8-dfe3abe4e5eb
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204732(v=OCS.15)
ms:contentKeyID: 49312206
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的公共即时消息支持

 

_**上一次修改主题：** 2013-10-07_

Lync Server 2013 支持使用经许可的公共即时消息 (IM) 连接提供程序，以及使用可扩展消息传递和状态协议 (XMPP) 实现特定类型的联盟，以允许 Lync Server 访问使用 Lync 2013 客户端的已配置 XMPP 域合作伙伴。

## 公共 IM 连接提供程序支持

当前支持的公共即时消息连接合作伙伴包括：

  - America Online

  - Windows Live

  - Yahoo\!

若要与 Windows Live 用户通信， Lync Server 2013 需要支持对等 IM 以及音频和视频呼叫。若要与 AOL 和 Yahoo\! 用户通信， Lync Server 2013 需要支持对等 IM。可能需要单独的许可证。

> [!IMPORTANT]  
> <ul>
> <li><p>自 2012 年 9 月 1 日起，新订或续订合同不能再购买 Microsoft Lync 公共 IM 连接用户订阅许可证 (“PIC USL”)。拥有有效许可证的客户可继续与 Yahoo! Messenger 联盟直至服务关闭。AOL 和 Yahoo! 的生命周期结束日期已宣布，为 2014 年 6 月。有关详细信息，请参阅 <a href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公共即时消息连接支持</a>。</p></li>
> <li><p>PIC USL 是一个每用户每月订阅许可证，是 Lync Server 或 Office Communications Server 与 Yahoo! Messenger 联盟所必需的。Microsoft 之所以能够提供此服务离不开 Yahoo! 的支持，但这项支持的基础协议正在逐步终止。</p></li>
> <li><p>Lync 是一个比以往更强大的工具，它实现了人员跨组织、跨地域的连接。除 Lync 标准 CAL 外，与 Windows Live Messenger 联盟不需要任何附加用户/设备许可证。Skype 联盟将添加到此列表中，以便 Lync 用户能够通过 IM 和语音与数亿用户取得联系。</p></li>
> </ul>

## XMPP 联盟支持

XMPP 联盟支持 Lync 用户与使用公共提供程序（如 GTalk）的已配置 XMPP 域用户进行通信。与这些用户的通信包括：

  - 对等 IM 和状态

  - Lync 客户端中 XMPP 联盟联系人的创建

