---
title: Lync Server 2013：定义前端服务器、即时消息和状态的要求
TOCTitle: 定义前端服务器、即时消息和状态的要求
ms:assetid: c21198bc-520c-4d17-8b84-7ff1475b9b0a
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412956(v=OCS.15)
ms:contentKeyID: 49314156
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中定义前端服务器、即时消息和状态的要求

 

_**上一次修改主题：** 2013-10-07_

规划即时消息 (IM) 和状态的主要任务是确保为用户准备足够的前端服务器。

## 启用与外部用户的通信

通过允许您的用户与外部用户进行通信，可大大增加在 Lync Server 中投资的收益。外部用户可能包括：

  - **远程用户** 在防火墙外工作并使用其便携式计算机或其他 Lync Server 设备的组织的内部用户。

  - **联盟用户** 来自合作公司同时也运行 Lync Server 的用户。要使用户轻松与这些用户联系，应与这些公司建立联盟关系。

  - **公共用户** 公共 IM 服务（例如，Internet 服务的 Windows Live 网络、Yahoo\! 和 AOL 提供的 IM 服务）的用户，以及使用可扩展消息传递和状态协议 (XMPP) 的提供商和服务器（例如，Google Talk）的用户。
    
    > [!NOTE]  
    > 请注意，与 Windows Live、AOL 和 Yahoo! 的公共 IM 连接可能需要使用单独的许可证。
    
    > [!IMPORTANT]  
	> <ul>
    > <li><p>自 2012 年 9 月 1 日起，新订或续订合同不能再购买 Microsoft Lync 公共 IM 连接用户订阅许可证 (“PIC USL”)。拥有有效许可证的客户可继续与 Yahoo! Messenger 联盟直至服务关闭。AOL 和 Yahoo! 的生命周期结束日期已宣布，为 2014 年 6 月。有关详细信息，请参阅 <a href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公共即时消息连接支持</a>。</p></li>
    > <li><p>PIC USL 是一个每用户每月订阅许可证，是 Lync Server 或 Office Communications Server 与 Yahoo! Messenger 联盟所必需的。Microsoft 之所以能够提供此服务离不开 Yahoo! 的支持，但这项支持的基础协议正在逐步终止。</p></li>
    > <li><p>Lync 是一个比以往更强大的工具，它实现了人员跨组织、跨地域的连接。除 Lync 标准 CAL 外，与 Windows Live Messenger 联盟不需要任何附加用户/设备许可证。Skype 联盟将添加到此列表中，以便 Lync 用户能够通过 IM 和语音与数亿用户取得联系。</p></li>
    > </ul>

要实现任意或所有这些方案，需要部署边缘服务器以帮助启用 Lync Server 部署和外部用户之间的安全通信。组织的远程用户和联盟组织的用户将能够查看彼此的状态并使用 IM 进行通信。有关启用与外部用户的通信的详细信息，请参阅规划文档中的 [在 Lync Server 2013 中规划外部用户访问](lync-server-2013-planning-for-external-user-access.md)。

## 存档 IM 内容

如果组织必须遵守合规性要求， Lync Server 会提供可以使用的功能。您可以使用存档功能为组织中的所有用户或仅为您指定的特定用户存档 IM 消息的内容。有关详细信息，请参阅规划文档中的 [在 Lync Server 2013 中规划存档](lync-server-2013-planning-for-archiving.md)。

如果您还部署了 Microsoft Exchange Server 2013，则可以将 Exchange 数据的存档与 Lync Server 数据的存档进行集成，并使用一个工具同时搜索这两种类型的存档数据。有关详细信息，请参阅 [配置 Microsoft Lync Server 2013 以使用 Microsoft Exchange Server 2013 存档](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md)。

