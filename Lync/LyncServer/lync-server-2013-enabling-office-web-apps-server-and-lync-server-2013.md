---
title: Lync Server 2013：启用 Office Web Apps Server 和 Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling Office Web Apps Server and Lync Server 2013
ms:assetid: 3370ab55-9949-4f32-b88b-5cffed6aaad8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204792(v=OCS.15)
ms:contentKeyID: 48183790
ms.date: 08/19/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37715182ba704f71bad463044ec9b47cea8f777b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735782"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-integration-with-office-web-apps-server-and-lync-server-2013"></a>配置与 Office Web Apps Server 和 Lync Server 2013 的集成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2016-08-19_

Lync Server 2013 使用 Office Web Apps 服务器处理 PowerPoint 演示文稿。 有关此方法的优势的信息，请参阅[Lync Server 2013 中的 web 会议概述](lync-server-2013-web-conferencing-overview.md)。

若要使用这些新功能，管理员必须安装 Office Web Apps 服务器，并且必须将 Lync Server 2013 配置为与 Office Web Apps 服务器通信。 本文档提供有关如何将 Lync Server 2013 配置为使用 Office Web Apps 服务器的信息。 本文档不提供的信息是有关如何安装 Office Web Apps 服务器本身的信息;有关这些信息，请参阅 Microsoft Office Web Apps 部署网站<http://go.microsoft.com/fwlink/p/?linkid=257525>。 该指南包括 Office Web Apps 服务器的完整必备信息;请注意，Office Web Apps 服务器应安装在未运行 Lync Server、Microsoft SQL Server 或任何其他服务器应用程序的独立计算机上。 （您不能在该计算机上安装任何版本的 Microsoft Office。）任何用于运行 Office Web Apps 服务器的计算机还必须安装一组特定的软件（包括 .NET Framework 4.5 和 Windows PowerShell 3.0）;有关配置证书和 Internet 信息服务（IIS）的这些要求以及有关配置证书和 Internet 信息服务（IIS）的信息，请参阅 Microsoft <http://go.microsoft.com/fwlink/p/?linkid=257525>Office Web Apps 部署网站中的详细讨论。

<div>


> [!NOTE]  
> Office Web Apps 服务器的最新小版本称为 "Office Online Server"，该服务器受 Lync Server 2013 支持。 有关更多详细信息，请参阅<A href="https://technet.microsoft.com/en-us/library/jj219456(v=office.16).aspx">Office Online Server 文档</A>。



</div>

本文档包含以下主题区域：

  - [将 Lync Server 2013 配置为使用 Office Web Apps 服务器](lync-server-2013-configuring-lync-server-2013-to-work-with-office-web-apps-server.md)

  - [使用反向代理服务器在 Lync Server 2013 中发布 Office Web Apps 服务器](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md)

  - [在 Lync Server 2013 中验证 Office Web Apps 服务器的配置](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md)

  - [配置 Lync Server 2013 客户端以与 Office Web Apps 服务器配合使用](lync-server-2013-configuring-clients-for-use-with-office-web-apps-server.md)

</div>

<span> </span>

</div>

</div>

</div>

