---
title: Lync Server 2013 IM 和状态
TOCTitle: IM 和状态
ms:assetid: 6a93ae95-3b64-410b-ab72-74dea232f065
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg417162(v=OCS.15)
ms:contentKeyID: 49313133
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 IM 和状态

 

_**上一次修改主题：** 2013-10-07_

即时消息 (IM) 和状态会自动安装到任何 Lync Server 部署中。

通过*状态* 信息，用户可以在适当的时间使用适当的交流方式与同事沟通，从而形成更高效的工作环境。用户的状态是包含忙闲状态、通信意愿、其他注释（如位置和状态）和用户联系方式在内的信息集合。Lync Server 中增强的状态功能提供图片、位置信息和一组丰富的状态，其中包括诸如“有空”、“忙碌”和“正在开会”等基本状态以及“下班”、“请勿打扰”和“马上回来”等。管理员还可以定义自定义的特定于组织的状态。

联系人管理和用户访问选项使用户能够控制其他人可以查看的信息。用户可以设置各种联系人级别，每个联系人级别可以查看不同级别的状态信息。

只需查看联系人列表，用户就可以快速找到需要了解的所有内容。简单的带颜色图标可指示其他用户的状态，还会显示图片和位置。

在将 Lync Server 和其他产品（如 Outlook 和 SharePoint）集成后，只要显示联系人姓名（如在电子邮件中或在团队网站上），就会同时显示其状态和联系信息。此外，如果部署 Exchange 2013，则 Lync Server 和 Exchange 2013 可共享统一的联系人存储库，该存储库可由任一产品的客户端访问。

通过 Lync Server 中的即时消息，用户可以彼此快速发送即时信息。如果愿意，您的用户还可以与公共 IM 网络（如 MSN/Windows Live、Yahoo\! 和 AOL）的用户进行通信。请注意，与 Windows Live、AOL 和 Yahoo\! 的公共 IM 连接可能需要使用单独的许可证。 Lync Server 还包括可扩展消息传递和状态协议 (XMPP) 兼容性，因此您的用户可以与 XMPP 服务（如 Google Talk）的用户交换 IM 消息和状态信息。

> [!IMPORTANT]  
> <ul>
> <li><p>自 2012 年 9 月 1 日起，新订或续订合同不能再购买 Microsoft Lync 公共 IM 连接用户订阅许可证 (“PIC USL”)。拥有有效许可证的客户可继续与 Yahoo! Messenger 联盟直至服务关闭。AOL 和 Yahoo! 的生命周期结束日期已宣布，为 2014 年 6 月。有关详细信息，请参阅 <a href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公共即时消息连接支持</a>。</p></li>
> <li><p>PIC USL 是一个每用户每月订阅许可证，是 Lync Server 或 Office Communications Server 与 Yahoo! Messenger 联盟所必需的。Microsoft 之所以能够提供此服务离不开 Yahoo! 的支持，但这项支持的基础协议正在逐步终止。</p></li>
> <li><p>Lync 是一个比以往更强大的工具，它实现了人员跨组织、跨地域的连接。除 Lync 标准 CAL 外，与 Windows Live Messenger 联盟不需要任何附加用户/设备许可证。Skype 联盟将添加到此列表中，以便 Lync 用户能够通过 IM 和语音与数亿用户取得联系。</p></li>
> </ul>


用户可以使用对话历史记录跟踪以前的 IM 对话，并检索可能在几个月前通过 IM 进行的通信信息。

利用 持久聊天功能，用户可以参加持续进行的、基于主题的多方对话。张贴到聊天室（论坛）的消息可以持久保存（即长时间可供访问），以使来自不同地点和部门的人员即使在并不全部同时在线的情况下也能加入聊天室。

如果组织必须遵守合规性要求，则可以部署消息存档功能以存档组织中所有用户或仅某些指定用户的即时消息内容。如果还部署 Exchange 2013，则可将 IM 存档与 Exchange 的就地保留功能集成，以便提供针对合规性的单一管理体验。

