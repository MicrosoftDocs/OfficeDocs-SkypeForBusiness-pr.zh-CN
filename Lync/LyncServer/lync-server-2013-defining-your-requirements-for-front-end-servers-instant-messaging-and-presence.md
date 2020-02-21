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
ms.openlocfilehash: 9be82373d33dafba7a5cf3e967b162ab5d33b01e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213712"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a>在 Lync Server 2013 中定义对前端服务器、即时消息和状态的要求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-10-07_

规划即时消息 (IM) 和状态的主要任务是确保为用户准备足够的前端服务器。

<div>

## <a name="enabling-communication-with-external-users"></a>启用与外部用户的通信

您可以通过使用户能够与外部用户进行通信，从而大大提高您的投资在 Lync Server 中的优势。 外部用户可能包括：

  - ****   当您的组织的用户在防火墙外工作并使用其便携式计算机或其他 Lync Server 设备时，远程用户。

  - **联合用户**   来自公司的用户，你可以与其他人一起运行 Lync Server。 若要使您的用户能够轻松地与这些用户联系，您可以创建与这些公司的联盟关系。

  - **公共用户**   ：公共 IM 服务的用户，例如 Internet 服务、Yahoo\!和 AOL 的 Windows Live 网络提供的 IM 服务、使用可扩展消息和服务器的提供程序和服务器（如 Google 谈话）的用户。
    
    <div>
    

    > [!NOTE]  
    > 请注意，与 Windows Live、AOL 和 Yahoo! 的公共 IM 连接可能需要使用单独的许可证。

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P>从2012年9月1日起，Microsoft Lync 公共 IM 连接用户订阅许可证（"PIC USL"）不再可用于购买新的或更新的协议。 拥有主动许可证的客户将能够继续与 Yahoo！联合联合 信使，直到服务关闭日期。 AOL 和 Yahoo！的生命周期结束日期为2014年6月 已宣布。 有关详细信息，请参阅<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的支持公用即时信使连接</A>。</P>
    > <LI>
    > <P>PIC USL 是 Lync Server 或 Office 通信服务器与 Yahoo！联合所需的每个用户每月订阅许可证。 Messenger. Microsoft 提供此服务的能力因 Yahoo！中的支持而受到了支持，其下凸的底层协议。</P>
    > <LI>
    > <P>Lync 是前所未有的强大工具，用于跨组织和世界各地的个人进行连接。 与 Windows Live Messenger 的联盟不需要除 Lync Standard CAL 之外的其他用户/设备许可证。 Skype 联合身份验证将添加到此列表中，使 Lync 用户可以使用即时消息和语音访问成百上千人。</P></LI></UL>

    
    </div>

若要启用任何或所有这些方案，需要部署边缘服务器以帮助启用 Lync Server 部署和外部用户之间的安全通信。 组织的远程用户和联盟组织的用户将能够查看彼此的状态并使用 IM 进行通信。 有关启用与外部用户的通信的详细信息，请参阅规划文档中的在[Lync Server 2013 中规划外部用户访问](lync-server-2013-planning-for-external-user-access.md)。

</div>

<div>

## <a name="archiving-im-content"></a>存档 IM 内容

如果您的组织必须遵守合规性管理法规，Lync Server 提供了您可以使用的功能。 您可以使用存档为组织中的所有用户或仅为您指定的特定用户存档 IM 消息的内容。 有关详细信息，请参阅规划文档中的在[Lync Server 2013 中规划存档](lync-server-2013-planning-for-archiving.md)。

如果还部署了 Microsoft Exchange Server 2013，则可以将 Exchange 数据的存档与 Lync Server 数据的存档进行集成，并使用单个工具搜索两种类型的存档数据。 有关详细信息，请参阅[配置 Microsoft Lync Server 2013 以使用 Microsoft Exchange Server 2013 存档](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

