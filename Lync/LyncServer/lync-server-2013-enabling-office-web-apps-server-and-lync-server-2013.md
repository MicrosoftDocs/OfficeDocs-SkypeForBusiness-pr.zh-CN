---
title: Lync Server 2013：启用 Office Web Apps Server 和 Lync Server 2013
description: Lync Server 2013：启用 Office Web Apps Server 和 Lync Server 2013。
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
ms.openlocfilehash: a1bf4e09dc29bf344b78df50595258f0663cd731
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546518"
---
# <a name="configuring-integration-with-office-web-apps-server-and-lync-server-2013"></a>配置与 Office Web Apps Server 和 Lync Server 2013 的集成

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2016-08-19_

Lync Server 2013 采用 Office Web Apps Server 来处理 PowerPoint 演示文稿。 有关此方法的优势的信息，请参阅 [Lync Server 2013 中的 web 会议概述](lync-server-2013-web-conferencing-overview.md)。

为了使用这些新功能，管理员必须安装 Office Web Apps Server，并且必须配置 Lync Server 2013 以与 Office Web Apps Server 进行通信。 本文档提供了有关如何配置 Lync Server 2013 以与 Office Web Apps Server 配合使用的信息。 本文档不提供的内容是有关如何安装 Office Web Apps Server 本身的信息。有关此信息，请参阅中的 Microsoft Office Web Apps 部署网站 <https://go.microsoft.com/fwlink/p/?linkid=257525> 。 该指南包括 Office Web Apps Server 的完整必备信息;请注意，Office Web Apps Server 应安装在未运行 Lync Server、Microsoft SQL Server 或任何其他服务器应用程序的独立计算机上。  (不得在该计算机上安装任何版本的 Microsoft Office。 ) 用于运行 Office Web Apps Server 的任何计算机还必须安装一组特定的软件 (包括 .NET Framework 4.5 和 Windows PowerShell 3.0) ;下面的 Microsoft Office Web Apps 部署网站中详细介绍了有关配置证书和 Internet 信息服务 (IIS) 的相关要求 <https://go.microsoft.com/fwlink/p/?linkid=257525> 。

<div>


> [!NOTE]  
> Office Web Apps Server 的最新小版本命名为 Office Online Server，这是由 Lync Server 2013 支持的。 有关更多详细信息，请参阅 <A href="https://technet.microsoft.com/library/jj219456(v=office.16).aspx">Office Online Server 文档</A>。



</div>

本文档包含以下主题领域：

  - [配置 Lync Server 2013 以与 Office Web Apps Server 配合使用](lync-server-2013-configuring-lync-server-2013-to-work-with-office-web-apps-server.md)

  - [使用反向代理服务器在 Lync Server 2013 中发布 Office Web Apps Server](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md)

  - [在 Lync Server 2013 中验证 Office Web Apps Server 的配置](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md)

  - [配置用于 Office Web Apps Server 的 Lync Server 2013 客户端](lync-server-2013-configuring-clients-for-use-with-office-web-apps-server.md)

</div>

<span> </span>

</div>

</div>

</div>

