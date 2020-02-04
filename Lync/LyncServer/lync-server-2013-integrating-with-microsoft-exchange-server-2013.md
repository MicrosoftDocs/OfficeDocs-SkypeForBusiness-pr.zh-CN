---
title: Lync Server 2013：与 Microsoft Exchange Server 2013 集成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Integrating Lync Server 2013 and Exchange Server 2013
ms:assetid: 795dc1c6-524f-4012-8b66-103b55198044
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688098(v=OCS.15)
ms:contentKeyID: 49733697
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1467f6a570f83908eb5809f9493303bdc91c169
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725852"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="integrating-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a>集成 Microsoft Lync Server 2013 和 Microsoft Exchange Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2014-07-09_

Exchange 和 Lync 服务器的集成和兼容性历史记录很长。 此集成在其各自的客户端应用程序中最显著。 例如，可以在 Microsoft Outlook 中报告 Lync 状态信息;同样，Lync 可以使用 Outlook 日历自动更新该状态信息。 （例如，当你的日历显示你已安排会议时，Lync 可以随时将你的状态更改为 "忙碌"。）虽然您不必运行 Exchange 即可运行 Lync Server （反之亦然），但很不用怀疑使用这两个产品，epitomizes "更好的"。

在发布 Microsoft Lync Server 2013 和 Microsoft Exchange Server 2013 时尤其如此。 除了在 Microsoft Exchange Server 2010 和 Microsoft Lync Server 2010 中找到的功能（如统一消息和 IM 和状态）之外，服务器产品的2013版本包括许多新功能。 这些功能包括以下内容：

  - **Lync 存档集成**。 在 Lync Server 2013 中，管理员仍然可以选择将即时消息和 Web 会议脚本存档到 SQL Server （与在 Lync Server 2010 中存档这些脚本的方式相同）。 但是，管理员可以选择将脚本存档到 Exchange 2013，将这些脚本存储在单个用户邮箱中，就像 Exchange 存档通信一样。 这意味着用于所有电子通信的单个存储库（来自 Exchange 和 Lync 服务器），这样就可以更轻松地搜索和检索这些存档的通信。

  - **统一联系人存储**。 在 Lync Server 2010 中，用户必须在 Outlook 和 Lync 中维护单独的联系人列表;实际上，为确保您在两种产品中都可以使用相同的联系人，您必须维护重复的联系人列表，一个用于 Outlook，另一个用于 Lync。 但是，使用 Lync Server 2013，用户联系人可以存储在 Exchange 2013 和统一联系人存储中。 使用单个联系人存储可使用户只保留一组联系人，其中一组联系人在 Lync 2013、Outlook 2013 和 Outlook Web Access 2013 中可用。

  - **从 OWA 安排 Lync 会议**。 使用 Lync Server 2013 和 Exchange 2013 集成，用户可以从 Outlook Web Access 2013 中安排 Lync 会议。

  - **高分辨率照片**。 Lync 2010 仅显示您的联系人的少量照片;这是因为这些照片存储在 Active Directory 中，并且 Active Directory 在存储的照片上施加48像素大小限制的48像素。 但是，对于 Lync Server 2013，照片可以存储在 Microsoft Exchange 中;这允许高分辨率的照片，最大为648像素乘以648像素。 正如你所料，Lync 2013 已升级为允许显示这些高分辨率的照片。

请记住，这些新功能需要同时使用 Lync Server 2013 和 Exchange 2013。 此外，希望充分利用这些新功能的用户必须在 Lync Server 2013 和 Exchange 2013 上拥有帐户，并且必须使用最新版本的客户端软件（如 Lync 2013）。 例如，在 Lync Server 2010 上托管的用户不能使用 "统一联系人存储";同样，无法在 Lync 2010 中显示高分辨率照片。

本文档提供有关如何集成 Lync Server 2013 和 Exchange 2013 的信息。 包括有关启用新功能（如存档集成和统一联系人存储）的分步信息。 本文档不执行的操作是讨论这两种产品的初始设置和配置。 有关部署 Lync Server 2013 的详细信息，请参阅 Lync Server 2013 技术[http://go.microsoft.com/fwlink/p/?LinkId=246127](http://go.microsoft.com/fwlink/p/?linkid=246127)中心。 有关部署 Exchange 2013 的详细信息，请参阅 Exchange 2013 技术[http://go.microsoft.com/fwlink/p/?LinkId=268528](http://go.microsoft.com/fwlink/p/?linkid=268528)中心。

<div>

## <a name="in-this-section"></a>本节内容

[集成 Microsoft Lync Server 2013 和 Microsoft Exchange Server 2013 的先决条件](lync-server-2013-prerequisites-for-integrating-with-exchange-server-2013.md)

[在 Microsoft Lync Server 2013 和 Microsoft Exchange Server 2013 中配置合作伙伴应用程序](lync-server-2013-configuring-partner-applications-in-lync-server-2013-and-exchange-server-2013.md)

[将 Microsoft Lync Server 2013 配置为使用 Microsoft Exchange Server 2013 存档](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md)

[配置 Microsoft SharePoint Server 2013 以搜索已存档的 Microsoft Lync Server 2013 数据](lync-server-2013-configuring-microsoft-sharepoint-server-2013-to-search-for-archived-lync-server-2013-data.md)

[将 Microsoft Lync Server 2013 配置为使用统一联系人存储](lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md)

[在 Microsoft Lync Server 2013 中配置高分辨率照片的使用](lync-server-2013-configuring-the-use-of-high-resolution-photos.md)

[为 Microsoft Lync Server 2013 语音邮件配置 Microsoft Exchange Server 2013 统一消息](lync-server-2013-configuring-microsoft-exchange-server-2013-unified-messaging-for-lync-server-2013-voice-mail.md)

[集成 Microsoft Lync Server 2013 和 Microsoft Outlook Web App 2013](lync-server-2013-integrating-lync-server-and-outlook-web-app-2013.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

