---
title: Lync Server 2013：安装 Operation Manager 代理文件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing the Operation Manager agent files
ms:assetid: e2246c44-0c75-43fc-8b04-26e53c5dd572
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205345(v=OCS.15)
ms:contentKeyID: 48185692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c7b658475e911d300d4ec8f6c15320e69ab71e15
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42118845"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-the-operation-manager-agent-files-in-lync-server-2013"></a>在 Lync Server 2013 中安装 Operation Manager 代理文件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-20_

若要在计算机上安装 Operations Manager 代理文件，请完成以下步骤。

1.  在您的 System Center 安装程序媒体上，双击 " **SetupOM**"。

2.  在 System Center Operation Manager 安装程序中，单击 "**安装 Operations Manager 代理**"。

3.  在 System Center 安装向导中，在 "**欢迎使用 System Center Operations Manager 安装**向导" 页上，单击 "**下一步**"。

4.  在 "**目标文件夹**" 页上，选择将在其中安装 Operations Manager 代理文件的文件夹，然后单击 "**下一步**"。

5.  在 "**管理组配置**" 页上，选择 "**指定管理组信息**"，然后单击 "**下一步**"。

6.  在 "**管理组配置**" 页上，在 "**管理组名称**" 框中键入 operations manager 管理组的名称，然后在 "**管理服务器**" 框中键入 operations manager 服务器的主机名称（例如，atl-ws-01-001）。 如果更改了 Operations Manager 使用的端口号，请在 "管理服务器端口" 框中键入新的端口号。 否则，将端口保留为默认值5723，然后单击 "**下一步**"。

7.  在 "**代理操作帐户**" 页上，选择 "**本地系统**"，然后单击 "**下一步**"。

8.  在 " **Microsoft update** " 页上，选择 "**我不想使用 Microsoft 更新**"，然后单击 "**下一步**"。

9.  在 "**准备安装**" 页上，单击 "**安装**"。

10. 在 "**正在完成 System Center Operations Manager 安装向导**" 页上，单击 "**完成**"。

11. 单击“退出”****。

如果使用的是 System Center 2007 R2，可以通过单击 "**开始**"，单击 "**所有程序**"，单击 " **System Center Operations Manager 2007 R2**"，然后单击 " **Operations Manager Shell**" 来验证是否已创建代理。 在 Operations Manager 命令行管理程序中，键入以下 Windows PowerShell 命令，然后按 ENTER：

    Get-Agent 

将在屏幕上显示所有 Operations Manager 代理的列表。

如果使用的是 System Center 2012，请从 Operations 2012 Manager 命令行管理程序中运行以下命令：

    Get-SCOMAgent

</div>

<span> </span>

</div>

</div>

</div>

