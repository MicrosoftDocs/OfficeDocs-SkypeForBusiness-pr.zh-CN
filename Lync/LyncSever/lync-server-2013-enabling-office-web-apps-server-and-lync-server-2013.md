---
title: 'Lync Server 2013：启用 Office Web Apps Server 和 Lync Server 2013 '
TOCTitle: 启用 Office Web Apps Server 和 Lync Server 2013
ms:assetid: 3370ab55-9949-4f32-b88b-5cffed6aaad8
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204792(v=OCS.15)
ms:contentKeyID: 49312441
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 配置与 Office Web Apps Server 和 Lync Server 2013 的集成

 

_**上一次修改主题：** 2016-12-08_

Lync Server 2013 使用 Office Web Apps Server 来处理 PowerPoint 演示文稿。有关此方法的优势的信息，请参阅 [Lync Server 2013 中的 Web 会议概述](lync-server-2013-web-conferencing-overview.md)。

为使用这些新功能，管理员必须安装 Office Web Apps Server 并且他们必须配置 Lync Server 2013 以便与 Office Web Apps Server 进行通信。本文档提供有关如何将 Lync Server 2013 配置为与 Office Web Apps Server 一起使用的信息。本文档未提供有关如何安装 Office Web Apps Server 本身的信息；有关该信息，请参阅 Microsoft Office Web Apps 部署网站（网址为 <http://go.microsoft.com/fwlink/p/?linkid=257525>）。本指南包括有关 Office Web Apps Server 的完整前提条件信息；请注意，应将 Office Web Apps Server 安装到未运行 Lync Server、Microsoft SQL Server 或其他任何服务器应用程序的独立计算机上。（您不得在该计算机上安装 Microsoft Office 的任何版本。）用于运行 Office Web Apps Server 的任何计算机也必须安装有一组特定的软件（包括 .NET Framework 4.5 和 Windows PowerShell 3.0）；这些要求以及有关配置证书和 Internet Information Services (IIS) 的信息将在 Microsoft Office Web Apps 部署网站（网址为 <http://go.microsoft.com/fwlink/p/?linkid=257525>）中详细讨论。

本文档涵盖下列主题领域：

  - [将 Lync Server 2013 配置为使用 Office Web Apps 服务器](lync-server-2013-configuring-lync-server-2013-to-work-with-office-web-apps-server.md)

  - [在 Lync Server 2013 中使用反向代理服务器发布 Office Web Apps Server](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md)

  - [在 Lync Server 2013 中验证 Office Web Apps Server 的配置](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md)

  - [在 Lync Server 2013 中将客户端配置为与 Office Web Apps Server 结合使用](lync-server-2013-configuring-clients-for-use-with-office-web-apps-server.md)

