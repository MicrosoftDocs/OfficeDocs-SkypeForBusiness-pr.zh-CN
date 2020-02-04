---
title: Lync Server 2013 IM 和状态
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IM and presence
ms:assetid: 6a93ae95-3b64-410b-ab72-74dea232f065
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417162(v=OCS.15)
ms:contentKeyID: 48184398
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57f57d4fae488a7d4946a0adb1f8350d02114a7d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742382"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="im-and-presence-in-lync-server-2013"></a>Lync Server 2013 中的 IM 和状态

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-10-07_

即时消息（IM）和联机状态会自动安装在任何 Lync Server 部署中。

*联机状态*信息使用户能够使用适当的通信形式在适当的时间处理同事，以获得更高效的工作环境。 用户的状态是信息的集合，其中包括可用性、通信意愿、其他笔记（如位置和状态），以及如何联系用户。 在 Lync Server 中，"联机状态" 已增强，包含图片、位置信息和一组丰富的状态，包括 "已关闭工作"、"请勿打扰" 和 "回退"，除了基本状态，如 "可用"、"忙碌" 和 "正在开会"。 管理员还可以定义自定义的特定于组织的状态。

联系人管理和用户访问选项使用户能够控制其他人可以查看哪些信息。 用户可以设置不同级别的联系人，每个级别的联系人都可以查看不同级别的状态信息。

只需查看联系人列表，用户即可找到他们需要了解的所有内容。 简单的彩色图标表示其他用户的状态，还会显示图片和位置。

随着 Lync 服务器和其他产品（如 Outlook 和 SharePoint）之间的集成，每当出现联系人的姓名时（例如在电子邮件中或在团队网站上），也会显示状态和联系人信息。 此外，如果你部署 Exchange 2013，Lync Server 和 Exchange 2013 可以共享一个统一的联系人存储，这些存储可由任意一种产品的客户端访问。

通过在 Lync Server 中发送即时消息，用户可以通过及时的信息快速处理彼此的消息。 如果您愿意，您的用户也可以与公共 IM 网络（如 MSN/Windows Live、Yahoo\!和 AOL）的用户进行通信。 请注意，对于使用 Windows Live、AOL 和 Yahoo 的公共 IM 连接，可能需要单独的许可证\! Lync 服务器还包括可扩展消息和状态协议（XMPP）兼容性，以便你的用户可以与 Google 通话等 XMPP 服务用户交换 IM 消息和状态信息。

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>从2012年9月1日起，Microsoft Lync 公共 IM 连接用户订阅许可证（"PIC USL"）不再可用于购买新的或续订协议。 具有活动许可证的客户将能够继续与 Yahoo！进行联盟 Messenger，直到服务关闭日期。 AOL 和 Yahoo！的有效期结束日期为2014年6月 已宣布。 有关详细信息，请参阅<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公共即时消息连接支持</A>。</P>
> <LI>
> <P>PIC USL 是 Lync Server 或 Office 通信服务器与 Yahoo！联合所需的每个每个用户每月订阅许可证。 Messenger. Microsoft 提供此服务的能力已作为对 Yahoo！的支持，它的底层协议被向下缠绕。</P>
> <LI>
> <P>Lync 比以往更多，是一种强大的工具，用于跨组织和全球各地的人员进行连接。 与 Windows Live Messenger 的联盟不需要除 Lync 标准 CAL 之外的其他用户/设备许可证。 Skype 联盟将添加到此列表，使 Lync 用户可以通过 IM 和语音与成百上千人联系。</P></LI></UL>



</div>

"对话历史记录" 使用户能够跟踪旧的 IM 对话，并检索可能已由 IM 月前通信的信息。

持久聊天功能使用户能够参与在一段时间内保持的基于主题的多方聊天。 发布到聊天室（讨论论坛）的邮件可能是永久性的（即，随着时间的推移而推出），因此来自不同地点和部门的人员可以参与，即使他们不在同一时间进行联机也是如此。

如果你的组织必须遵循合规性规定，你可以部署邮件存档功能以存档你组织中的所有用户的即时消息的内容，或仅针对你指定的特定用户存档即时消息的内容。 如果你还部署 Exchange 2013，你的 IM 存档可以与 Exchange 的就地保留功能集成，以便为你的符合性提供单一的管理体验。

</div>

<span> </span>

</div>

</div>

</div>

