---
title: Lync Server 2013：与 Microsoft Exchange Server 2013 集成
TOCTitle: 集成 Lync Server 2013 和 Exchange Server 2013
ms:assetid: 795dc1c6-524f-4012-8b66-103b55198044
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688098(v=OCS.15)
ms:contentKeyID: 49888470
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 集成 Microsoft Lync Server 2013 和 Microsoft Exchange Server 2013

 

_**上一次修改主题：** 2016-12-08_

Exchange 和 Lync Server 已长期集成和兼容。此集成在其各自的客户端应用程序中最为明显。例如，可在 Microsoft Outlook 中报告 Lync 状态信息；同样，Lync 可使用 Outlook 日历自动更新该状态信息。（例如，每当日历显示您已安排会议时，Lync 会将您的状态更改为“忙碌”。）虽然无需运行 Exchange 即可运行 Lync Server（或反之亦然），毫无疑问，这两种产品的结合使用集中体现了术语“关联后功能更强大”的定义。

此情况在 Microsoft Lync Server 2013 和 Microsoft Exchange Server 2013 的发行版中尤其突出。除了可在 Microsoft Exchange Server 2010 和 Microsoft Lync Server 2010 中找到的统一消息、IM 和状态等功能之外，2013 版本的服务器产品还包括大量新功能。这些功能包括：

  - **Lync 存档集成** 。在 Lync Server 2013 中，管理员仍可以选择将即使消息和 Web 会议脚本存档到 SQL Server（与将这些脚本存档到 Lync Server 2010 中的方式相同）。但是，管理员可以选择将脚本存档到 Exchange 2013 中，并按照 Exchange 存档通信的方式在各个用户邮箱中存储这些脚本。这意味着，可通过单个存储库来存储您的所有电子通信（从 Exchange 和 Lync Server 中），可用于根据需要更轻松地搜索和检索这些存档的通信。

  - **统一的联系人存储库** 。在 Lync Server 2010 中，用户必须维护 Outlook 和 Lync 中的单独联系人列表；实际上，为了确保您在两种产品中具有相同的联系人，您必须维护重复的联系人列表，一个针对 Outlook，另一个针对 Lync。但是，利用 Lync Server 2013，可将用户联系人存储在 Exchange 2013 和统一的联系人存储库中。利用单个联系人存储库，用户只能维护一组联系人，此组联系人在 Lync 2013、Outlook 2013 和 Outlook Web Access 2013 中可用。

  - **从 OWA 计划 Lync 会议**。借助 Lync Server 2013 与 Exchange 2013 的集成，用户可以从 Outlook Web Access 2013 计划 Lync 会议。

  - **高分辨率照片** 。 Lync 2010 只能显示小型联系人照片；这是因为这些照片已存储在 Active Directory 中，并且 Active Directory 对存储的照片实施了 48 像素 x 48 像素的大小限制。但是，利用 Lync Server 2013，可将照片存储在 Microsoft Exchange 中；这将允许 648 像素 x 648 像素大小的高分辨率照片。就像您可能预料的那样，已升级 Lync 2013 以允许显示这些高分辨率的照片。

请记住，这些新功能需要同时使用 Lync Server 2013 和 Exchange 2013。除此之外，希望充分利用这些新功能的用户必须在 Lync Server 2013 和 Exchange 2013 上拥有帐户，并且必须使用最新版本的客户端软件（例如， Lync 2013）。例如，统一的联系人存储库对驻留在 Lync Server 2010 上的用户不可用；同样，高分辨率照片无法显示在 Lync 2010 中。

此文档提供有关集成 Lync Server 2013 和 Exchange 2013 的信息，其中包括有关启用新功能（如存档集成和统一的联系人存储库）的分步信息。本文档并未讨论这两种产品的初始设置和配置。有关部署 Lync Server 2013 的详细信息，请参阅 Lync Server 2013 技术中心，网址为 [http://go.microsoft.com/fwlink/?linkid=246127\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=246127%26clcid=0x804)。有关部署 Exchange 2013 的详细信息，请参阅 Exchange 2013 技术中心，网址为 [http://go.microsoft.com/fwlink/?linkid=268528\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=268528%26clcid=0x804)。

## 本部分内容

[集成 Microsoft Lync Server 2013 和 Microsoft Exchange Server 2013 的先决条件](lync-server-2013-prerequisites-for-integrating-with-exchange-server-2013.md)

[在 Microsoft Lync Server 2013 和 Microsoft Exchange Server 2013 中配置合作伙伴应用程序](lync-server-2013-configuring-partner-applications-in-lync-server-2013-and-exchange-server-2013.md)

[配置 Microsoft Lync Server 2013 以使用 Microsoft Exchange Server 2013 存档](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md)

[配置 Microsoft SharePoint Server 2013 以搜索存档的 Microsoft Lync Server 2013 数据](lync-server-2013-configuring-microsoft-sharepoint-server-2013-to-search-for-archived-lync-server-2013-data.md)

[将 Microsoft Lync Server 2013 配置为使用统一联系人存储](lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md)

[在 Microsoft Lync Server 2013 中配置使用高分辨率照片](lync-server-2013-configuring-the-use-of-high-resolution-photos.md)

[为 Microsoft Lync Server 2013 语音邮件配置 Microsoft Exchange Server 2013 统一消息](lync-server-2013-configuring-microsoft-exchange-server-2013-unified-messaging-for-lync-server-2013-voice-mail.md)

[集成 Microsoft Lync Server 2013 和 Microsoft Outlook Web App 2013](lync-server-2013-integrating-lync-server-and-outlook-web-app-2013.md)

