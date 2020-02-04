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
ms.openlocfilehash: 0f75e9b6f8c3f7eb7151cf0d67a62f5e2a03a65f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725952"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-operation-manager-agent-files-in-lync-server-2013"></a>在 Lync Server 2013 中安装 Operation Manager 代理文件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-20_

若要在计算机上安装 Operations Manager 代理文件，请完成以下步骤。

1.  在系统中心设置媒体上，双击 " **SetupOM**"。

2.  在 System Center Operation Manager 安装程序中，单击 "**安装 Operations Manager 代理**"。

3.  在 System Center 设置向导中的 "**欢迎使用 System Center Operations Manager 安装程序**向导" 页面上，单击 "**下一步**"。

4.  在 "**目标文件夹**" 页面上，选择将安装 Operations Manager 代理文件的文件夹，然后单击 "**下一步**"。

5.  在 "**管理组配置**" 页面上，选择 "**指定管理组信息**"，然后单击 "**下一步**"。

6.  在 "**管理组配置**" 页面上，在 "**管理组名称**" 框中键入 operations manager 管理组的名称，然后在 "**管理服务器**" 框中键入 operations manager 服务器的主机名（如 "atl-scom-001"）。 如果您更改了 Operations Manager 使用的端口号，请在 "管理服务器端口" 框中键入新的端口号。 否则，将该端口保留为默认值5723，然后单击 "**下一步**"。

7.  在 "**代理操作帐户**" 页面上，选择 "**本地系统**"，然后单击 "**下一步**"。

8.  在 " **Microsoft 更新**" 页面上，选择 "**我不想使用 Microsoft 更新**"，然后单击 "**下一步**"。

9.  在 "**准备安装**" 页面上，单击 "**安装**"。

10. 在 "**正在完成 System Center Operations Manager 安装向导**" 页面上，单击 "**完成**"。

11. 单击“退出”****。

如果您使用的是 System Center 2007 R2，则可以通过单击 "**开始**"，单击 "**所有程序**"，单击 " **System Center Operations Manager 2007 R2**"，然后单击 " **Operations Manager 外壳**程序" 来验证是否已创建代理。 In the Operations Manager Shell, type the following Windows PowerShell command, and then press ENTER:

    Get-Agent 

将在屏幕上显示所有 Operations Manager 代理的列表。

如果您使用的是 System Center 2012，请从操作2012管理器外壳程序运行此命令：

    Get-SCOMAgent

</div>

<span> </span>

</div>

</div>

</div>

