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
ms.openlocfilehash: c1c60768311f4fbf832f3dbe2ac4a0c2e8e55298
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145391"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="integrating-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a>集成 Microsoft Lync Server 2013 和 Microsoft Exchange Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-07-09_

Exchange 和 Lync Server 的集成和兼容性历史记录较长。 此集成在其各自的客户端应用程序中最为明显。 例如，可以在 Microsoft Outlook 中报告 Lync 状态信息;同样，Lync 也可以使用 Outlook 日历自动更新该状态信息。 （例如，当您的日历显示您已安排会议时，Lync 可以随时将您的状态更改为 "忙碌"。）虽然您无需运行 Exchange 即可运行 Lync Server （反之亦然），但毫无疑问，使用这两个产品的 epitomizes 对术语 "更好地结合" 的定义。

这在 Microsoft Lync Server 2013 和 Microsoft Exchange Server 2013 发布时尤其如此。 除了在 Microsoft Exchange Server 2010 和 Microsoft Lync Server 2010 中找到的功能（如统一消息和 IM 和状态）之外，服务器产品的2013版本还包括许多新功能。 这些功能包括：

  - **Lync 存档集成**。 在 Lync Server 2013 中，管理员仍可以选择将即时消息和 Web 会议脚本存档到 SQL Server （与在 Lync Server 2010 中存档这些脚本的方式相同）。 然而，管理员也可以选择将脚本存档为 Exchange 2013，并以与 Exchange 存档通信相同的方式将这些脚本存储在各个用户邮箱中。 这意味着您的所有电子通信（来自 Exchange 和 Lync Server）的单个存储库，这样就可以更轻松地搜索和检索这些已存档的通信，这是需要发生的。

  - **统一的联系人存储库**。 在 Lync Server 2010 中，用户必须在 Outlook 和 Lync 中维护单独的联系人列表;事实上，为了确保您必须在两个产品中都有相同的联系人，您必须维护重复的联系人列表，一个用于 Outlook，一个用于 Lync。 但是，使用 Lync Server 2013，用户联系人可以存储在 Exchange 2013 和统一联系人存储中。 使用单个联系人存储区使用户可以仅维护一组联系人，在 Lync 2013、Outlook 2013 和 Outlook Web Access 2013 中提供了相同的联系人集。

  - **来自 OWA 的 Lync 会议计划**。 借助 Lync Server 2013 和 Exchange 2013 集成，用户可以从 Outlook Web Access 2013 中安排 Lync 会议。

  - **高分辨率照片**。 Lync 2010 只能显示你的联系人的小照片;这是因为这些照片存储在 Active Directory 中，Active Directory 在存储的照片上的48像素大小限制为48像素。 但是，使用 Lync Server 2013，照片可以存储在 Microsoft Exchange 中;，可提供高分辨率的照片，最大为648像素 x 648 像素。 正如您所期望的那样，Lync 2013 已升级为允许显示这些高分辨率照片。

请注意，这些新功能需要同时使用 Lync Server 2013 和 Exchange 2013。 此外，希望充分利用这些新功能的用户必须在 Lync Server 2013 和 Exchange 2013 上拥有帐户，并且必须使用最新版本的客户端软件（例如 Lync 2013）。 例如，统一联系人存储对驻留在 Lync Server 2010 上的用户不可用;同样，在 Lync 2010 中无法显示高分辨率照片。

本文档提供有关集成 Lync Server 2013 和 Exchange 2013 的信息。 其中包括有关启用新功能（如存档集成和统一的联系人存储库）的分步信息。 本文档不能执行的操作是讨论这两种产品的初始设置和配置。 有关部署 Lync Server 2013 的详细信息，请参阅 Lync Server 2013 技术[https://go.microsoft.com/fwlink/p/?LinkId=246127](https://go.microsoft.com/fwlink/p/?linkid=246127)中心（网址为）。 有关部署 Exchange 2013 的详细信息，请参阅 Exchange 2013 技术[https://go.microsoft.com/fwlink/p/?LinkId=268528](https://go.microsoft.com/fwlink/p/?linkid=268528)中心（网址为）。

<div>

## <a name="in-this-section"></a>本部分内容

[集成 Microsoft Lync Server 2013 和 Microsoft Exchange Server 2013 的先决条件](lync-server-2013-prerequisites-for-integrating-with-exchange-server-2013.md)

[在 Microsoft Lync Server 2013 和 Microsoft Exchange Server 2013 中配置合作伙伴应用程序](lync-server-2013-configuring-partner-applications-in-lync-server-2013-and-exchange-server-2013.md)

[配置 Microsoft Lync Server 2013 以使用 Microsoft Exchange Server 2013 存档](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md)

[配置 Microsoft SharePoint Server 2013 以搜索存档的 Microsoft Lync Server 2013 数据](lync-server-2013-configuring-microsoft-sharepoint-server-2013-to-search-for-archived-lync-server-2013-data.md)

[配置 Microsoft Lync Server 2013 以使用统一的联系人存储库](lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md)

[在 Microsoft Lync Server 2013 中配置高分辨率照片的使用](lync-server-2013-configuring-the-use-of-high-resolution-photos.md)

[为 Microsoft Lync Server 2013 语音邮件配置 Microsoft Exchange Server 2013 统一消息](lync-server-2013-configuring-microsoft-exchange-server-2013-unified-messaging-for-lync-server-2013-voice-mail.md)

[集成 Microsoft Lync Server 2013 和 Microsoft Outlook Web App 2013](lync-server-2013-integrating-lync-server-and-outlook-web-app-2013.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

