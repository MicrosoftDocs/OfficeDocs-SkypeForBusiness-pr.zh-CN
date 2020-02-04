---
title: Lync Server 2013：定义前端服务器、即时消息和状态的要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your requirements for Front End Servers, instant messaging, and presence
ms:assetid: c21198bc-520c-4d17-8b84-7ff1475b9b0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412956(v=OCS.15)
ms:contentKeyID: 48185319
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af371d116948d348b49c552dfe53290c1dae1900
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743412"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a>在 Lync Server 2013 中定义前端服务器、即时消息和状态的要求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-10-07_

规划即时消息（IM）和状态的主要任务是确保您有足够的前端服务器供用户使用。

<div>

## <a name="enabling-communication-with-external-users"></a>启用与外部用户的通信

通过使你的用户能够与外部用户进行通信，你可以在 Lync Server 中大大增加投资的优势。 外部用户可能包括：

  - ****   当您的组织的用户在您的防火墙外工作且正在使用其笔记本或其他 Lync Server 设备时，您的组织自己的用户的远程用户。

  - **联盟用户**   来自公司的用户，您可以使用该用户同时运行 Lync Server。 要使用户轻松与这些用户联系，应与这些公司建立联盟关系。

  - ****   公共 IM 服务的公共用户用户，例如由 Internet 服务、Yahoo\!和 AOL 的 Windows Live 网络提供的 IM 服务，以及使用可扩展消息和状态协议（XMPP）的提供商和服务器的用户，如 Google 通话。
    
    <div>
    

    > [!NOTE]  
    > 请注意，对于使用 Windows Live、AOL 和 Yahoo！的公共 IM 连接，可能需要单独的许可证

    
    </div>
    
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

若要启用任何或所有这些方案，你需要部署边缘服务器以帮助在 Lync Server 部署和外部用户之间实现安全通信。 组织的远程用户和联盟组织的用户将能够查看彼此的状态并使用 IM 进行通信。 有关启用与外部用户的通信的详细信息，请参阅规划文档中的[在 Lync Server 2013 中规划外部用户访问](lync-server-2013-planning-for-external-user-access.md)。

</div>

<div>

## <a name="archiving-im-content"></a>将 IM 内容存档

如果您的组织必须遵守合规性规定，则 Lync Server 提供您可以使用的功能。 你可以使用存档功能为组织中的所有用户或仅为你指定的特定用户存档 IM 消息的内容。 有关详细信息，请参阅规划文档中的[在 Lync Server 2013 中规划存档](lync-server-2013-planning-for-archiving.md)。

如果你还部署了 Microsoft Exchange Server 2013，你可以将 Exchange 数据的存档与 Lync Server 数据的存档进行集成，并使用单个工具搜索两种类型的已存档数据。 有关详细信息，请参阅[将 Microsoft Lync server 2013 配置为使用 Microsoft Exchange Server 2013 存档](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

