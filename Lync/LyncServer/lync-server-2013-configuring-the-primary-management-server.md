---
title: Lync Server 2013：配置主管理服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the primary management server
ms:assetid: 44e2e9a8-c130-4c66-9871-80b1ff11b27c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204844(v=OCS.15)
ms:contentKeyID: 48183986
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a4fee1fa728c3c418c1f837a83248d95df7e7544
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532309"
---
# <a name="configuring-the-primary-management-server-in-lync-server-2013"></a>在 Lync Server 2013 中配置主管理服务器

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-03-19_

为了充分利用 Microsoft Lync Server 2013 中包含的新运行状况监视功能，管理员必须首先指定一台计算机作为你的主管理服务器;在该计算机上，必须安装 System Center Operations Manager 2007 R2 或 System Center Operations Manager 2012。 此外，还必须安装受支持的 SQL Server 版本，才能充当 Operations Manager 后端数据库。 如果您使用的是 System Center Operations Manager 2012，则可以使用以下任一版本的 SQL Server 作为后端数据库：

  - SQL Server 2008 R2 Service Pack 1

  - SQL Server 2008 R2 Service Pack 2

如果您使用的是 System Center Operations Manager 2007 R2，建议您安装 SQL Server 2005 Service Pack 4 或 SQL Server 2008 Service Pack 3。 您还可以使用 SQL Server 2008 R2 作为 System Center Operations Manager 2007 R2 的后端数据库。 有关将 SQL Server 2008 R2 配置为与 System Center Operations Manager 2007 R2 一起使用的详细信息，请参阅本文档的附录1。

当您安装 System Center Operations Manager 2012 或 System Center Operations Manager 2007 R2 时，需要安装该产品的所有组件，包括：

  - 操作数据库

  - 服务器

  - 控制台

  - Windows PowerShell cmdlet

  - Web 控制台

  - Reporting

  - 数据仓库

本文档将不会详细讨论这些组件及其安装。 有关 System Center Operations Manager 2007 R2 的详细信息，请参阅 Operations Manager 2007 R2 文档（网址为） <https://go.microsoft.com/fwlink/p/?linkid=257526> 和 System Center Operations manager 2012 文档（网址为） <https://go.microsoft.com/fwlink/p/?linkid=257527> 。 如果要将 SQL Server 2005 或 SQL Server 2008 Service Pack 1 用作后端数据库，则应遵循这些说明。

如果您使用的是 System Center Operations Manager 2012，则可以使用 SQL Server 2012 作为后端数据库。 有关 SQL Server 2012 的详细信息，请参阅联机丛书 for SQL Server 2012 [https://go.microsoft.com/fwlink/p/?LinkId=257528](https://go.microsoft.com/fwlink/p/?linkid=257528) 。

请注意，每个 Lync Server 部署中只能有一个主管理服务器。 此外，虽然您可以使用 System Center Operations Manager 2012 或 System Center Operations Manager 2007 R2，但您不能同时运行这两个应用程序，您必须选择其中一个。 例如，如果您运行的是 System Center Operations Manager 2012，则所有 System Center agent 也必须运行 System Center Operations Manager 2012。 您不能有一些代理运行 System Center Operations Manager 2012 和其他运行 System Center Operations Manager 2007 R2 的代理。

</div>

<span> </span>

</div>

</div>

</div>

