---
title: Lync Server 2013：安装 SQL Server Reporting Services
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing SQL Server Reporting Services
ms:assetid: 638a1d0c-1ac7-4735-83f2-4df3d03c7cf9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204957(v=OCS.15)
ms:contentKeyID: 48184345
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6342743486e3a3261e297d602ceb994d421dc13c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726002"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-sql-server-reporting-services-in-lync-server-2013"></a>在 Lync Server 2013 中安装 SQL Server Reporting Services

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-06-20_

如果您打算使用 Microsoft Lync Server 2013 监视报告（有关详细信息，请参阅本文档的下一节），必须首先安装 SQL Server Reporting Services;可以在安装 Microsoft SQL Server 时或在安装 SQL Server 之后的任何时间安装 Reporting Services。 如果你未安装 SQL Server，则请按照本文档之前提供的说明操作。 安装 SQL Server 时，确保在“功能选择”页上选择 Reporting Services。 这将安装 SQL Server Reporting Services。

如果你已安装 SQL Server 但未安装 SQL Server Reporting Services，你可以根据需要按照相应的 SQL Server 2008 R2 或 SQL Server 2012 的相应指令集添加该功能。

若要验证是否已成功安装 reporting Services，请完成以下步骤：

1.  如果你运行的是 Microsoft SQL Server 2008 R2，请单击 "**开始**"，单击 "**所有程序**"，单击 " **Microsoft SQL Server 2008 R2**"，单击 "**配置工具**"，然后单击 " **Reporting Services 配置管理器**"。
    
    如果你运行的是 Microsoft SQL Server 2012，请单击 "**开始**"，单击 "**所有程序**"，单击 " **Microsoft SQL Server 2012**"，单击 "**配置工具**"，然后单击 " **Reporting Services 配置管理器**"。

2.  在 " **Reporting Services 配置连接**" 对话框中，验证服务器名称是否显示在 "**服务器名称**" 框中，以及存储监视数据的 SQL server 实例的名称是否显示在 "**报表服务器实例**" 框中。 单击 "**连接**"。

在 Reporting Services 配置管理器中，报表服务器状态窗格应显示已安装 SQL Server Reporting Services 且报表服务当前正在运行：报表服务器状态应显示为 "**已启动**"，"**开始**" 按钮应灰显且不可用。 如果报告服务未运行，请单击 "**开始**" 以启动该服务。

如果报表服务器数据库名称标签旁边未列出任何数据库，请执行以下操作：

1.  在 Reporting Services 配置管理器中，单击 "**数据库**"。

2.  在报表服务器数据库窗格中，单击 "**更改数据库**"。

3.  在报表服务器数据库配置向导的 "操作" 窗格中，选择 "**创建新的报表服务器数据库**"，然后单击 "**下一步**"。

4.  在报表服务器数据库配置向导的 "数据库服务器" 窗格中，验证 "**服务器名称**"、"**身份验证类型**" 和 "**用户名**" 框中列出的信息是否正确。 单击 "**测试连接**" 以验证是否可以与数据库服务器建立连接，然后单击 "**下一步**"。

5.  在报表服务器数据库配置向导的 "数据库" 窗格中，接受 "**数据库名称**"、"**语言**" 和 "**报表服务器" 模式**的默认值，然后单击 "**下一步**"。

6.  在报表服务器数据库配置向导的 "凭据" 窗格中，验证 "**身份验证类型**" 下拉列表和 "**用户名**" 和 "**密码**" 框中列出的信息是否正确，然后单击 "**下一步**"。

7.  在报表服务器数据库配置向导的 "摘要" 窗格中，单击 "**下一步**"。

8.  在报表服务器数据库配置向导中的 "进度" 和 "完成" 窗格中，单击 "**完成**"。

若要验证报告服务 Url 是否已配置，请单击 " **Web 服务 url**"。 您应看到标题**报表服务器 Web 服务 url**下列出一个或多个 url。 单击其中每个 Url，验证您是否可以访问本地安装 SQL Server Reporting Services 的主页。

</div>

<span> </span>

</div>

</div>

</div>

