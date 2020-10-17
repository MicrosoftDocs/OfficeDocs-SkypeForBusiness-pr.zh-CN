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
ms.openlocfilehash: 26e4b9c2814b8e9e5bf57e2e798b4b803d7401fb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507259"
---
# <a name="im-and-presence-in-lync-server-2013"></a>Lync Server 2013 中的 IM 和状态

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-10-07_

即时消息 (IM) 和状态将自动安装在任何 Lync Server 部署中。

通过*状态* 信息，用户可以在适当的时间使用适当的交流方式与同事沟通，从而形成更高效的工作环境。 用户的状态是包含忙闲状态、通信意愿、其他注释（如位置和状态）和用户联系方式在内的信息集合。 在 Lync Server 中，状态为增强，其中包含图片、位置信息和丰富的状态集状态，包括 "已关闭工作"、"请勿打扰" 和 "回退" 等基本状态（如 "可用"、"忙" 和 "在会议中"）。 管理员还可以定义自定义的特定于组织的状态。

联系人管理和用户访问选项使用户能够控制其他人可以查看的信息。用户可以设置各种联系人级别，每个联系人级别可以查看不同级别的状态信息。

只需查看联系人列表，用户就可以快速找到需要了解的所有内容。简单的带颜色图标可指示其他用户的状态，还会显示图片和位置。

随着 Lync Server 和其他产品（如 Outlook 和 SharePoint）之间的集成，只要出现联系人的名称（如电子邮件或团队网站），也会显示状态和联系人信息。 此外，如果部署 Exchange 2013，Lync Server 和 Exchange 2013 可以共享统一的联系人存储库，这两个产品的客户端都可以访问它。

在 Lync Server 中使用即时消息，用户可以使用及时的信息快速消息。 如果你愿意，你的用户也可以与公共 IM 网络（如 MSN/Windows Live、Yahoo 和 AOL）的用户进行通信 \! 。 请注意，与 Windows Live、AOL 和 Yahoo 的公共 IM 连接可能需要单独的许可证\! Lync Server 还包括可扩展消息和状态协议 (XMPP) 兼容性，因此您的用户可以使用 XMPP 服务（如 Google 谈话）的用户交换 IM 消息和状态信息。

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>从2012年9月1日起，Microsoft Lync 公共 IM 连接用户订阅许可证 ( "PIC USL" ) 不再可用于购买新的或更新的协议。 拥有主动许可证的客户将能够继续与 Yahoo！联合联合 信使，直到服务关闭日期。 AOL 和 Yahoo！的生命周期结束日期为2014年6月 已宣布。 有关详细信息，请参阅 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的支持公用即时信使连接</A>。</P>
> <LI>
> <P>PIC USL 是 Lync Server 或 Office 通信服务器与 Yahoo！联合所需的每个用户每月订阅许可证。 Messenger. Microsoft 提供此服务的能力因 Yahoo！中的支持而受到了支持，其下凸的底层协议。</P>
> <LI>
> <P>Lync 是前所未有的强大工具，用于跨组织和世界各地的个人进行连接。 与 Windows Live Messenger 的联盟不需要除 Lync Standard CAL 之外的其他用户/设备许可证。 Skype 联合身份验证将添加到此列表中，使 Lync 用户可以使用即时消息和语音访问成百上千人。</P></LI></UL>



</div>

用户可以使用对话历史记录跟踪以前的 IM 对话，并检索可能在几个月前通过 IM 进行的通信信息。

持久聊天功能使用户能够参与在一段时间内保持的基于主题的多个会话。 张贴到聊天室（论坛）的消息可以持久保存（即长时间可供访问），以使来自不同地点和部门的人员即使在并不全部同时在线的情况下也能加入聊天室。

如果组织必须遵守合规性要求，则可以部署消息存档功能以存档组织中所有用户或仅某些指定用户的即时消息内容。 如果还部署 Exchange 2013，您的 IM 存档可以与 Exchange 的 In-Place 保留功能集成，以便为您的符合性提供单一的管理体验。

</div>

<span> </span>

</div>

</div>

</div>

