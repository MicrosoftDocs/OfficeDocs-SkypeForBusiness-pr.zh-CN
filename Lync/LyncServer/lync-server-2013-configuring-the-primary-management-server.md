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
ms.openlocfilehash: 7d6cb7d0f27413449873cb8a0d8498aec230fdfd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734612"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-primary-management-server-in-lync-server-2013"></a>在 Lync Server 2013 中配置主管理服务器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2014-03-19_

为了充分利用 Microsoft Lync Server 2013 中包含的新运行状况监视功能，管理员必须首先指定一个计算机作为你的主管理服务器;在该计算机上，必须安装 System Center Operations Manager 2007 R2 或 System Center Operations Manager 2012。 此外，必须安装受支持的 SQL Server 版本才能充当 Operations Manager 后端数据库。 如果您使用的是 System Center Operations Manager 2012，则可以使用以下任意版本的 SQL Server 作为后端数据库：

  - SQL Server 2008 R2 Service Pack 1

  - SQL Server 2008 R2 Service Pack 2

如果您使用的是 System Center Operations Manager 2007 R2，建议安装 SQL Server 2005 Service Pack 4 或 SQL Server 2008 Service Pack 3。 你还可以将 SQL Server 2008 R2 用作 System Center Operations Manager 2007 R2 的后端数据库。 有关将 SQL Server 2008 R2 配置为与 System Center Operations Manager 2007 R2 配合使用的详细信息，请参阅本文档的附录1。

安装 System Center Operations Manager 2012 或 System Center Operations Manager 2007 R2 时，你需要安装该产品的所有组件，包括：

  - 操作数据库

  - 服务器

  - 控制台

  - Windows PowerShell cmdlet

  - Web 控制台

  - 报告

  - 数据仓库

这些组件及其安装将不会在本文档中详细讨论。 有关 System Center Operations Manager 2007 R2 的详细信息，请参阅中的 Operations Manager 2007 <http://go.microsoft.com/fwlink/p/?linkid=257526> R2 文档和 System Center operations Manager 2012 文档<http://go.microsoft.com/fwlink/p/?linkid=257527>。 如果你打算使用 SQL Server 2005 或 SQL Server 2008 Service Pack 1 作为后端数据库，则应遵循这些说明。

如果您使用的是 System Center Operations Manager 2012，则可以使用 SQL Server 2012 作为后端数据库。 有关 SQL Server 2012 的详细信息，请参阅 SQL Server 2012 的联机[http://go.microsoft.com/fwlink/p/?LinkId=257528](http://go.microsoft.com/fwlink/p/?linkid=257528)丛书。

请记住，每个 Lync 服务器部署中只能有一个主管理服务器。 此外，虽然您可以使用 System Center Operations Manager 2012 或 System Center Operations Manager 2007 R2，但您不能同时运行这两个应用程序，必须选择其中一个。 例如，如果您运行的是 System Center Operations Manager 2012，则所有 System Center agent 也必须运行 System Center Operations Manager 2012。 无法让某些代理运行 System Center Operations Manager 2012 和其他运行 System Center Operations Manager 2007 R2 的代理。

</div>

<span> </span>

</div>

</div>

</div>

