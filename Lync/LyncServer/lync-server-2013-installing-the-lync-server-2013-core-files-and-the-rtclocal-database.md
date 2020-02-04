---
title: 安装 Lync Server 2013 core 文件和 RTCLocal 数据库
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing the Lync Server 2013 core files and the RTCLocal database
ms:assetid: 206f0c1d-40f7-45b6-aa62-88aaef6cf7f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204734(v=OCS.15)
ms:contentKeyID: 48183591
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da8f0dd1fb83c595ed444a487d0321c571a09315
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725992"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-server-2013-core-files-and-the-rtclocal-database"></a>安装 Lync Server 2013 core 文件和 RTCLocal 数据库

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-20_

若要在计算机上安装 Lync Server 2013 core 文件，请完成以下过程。 当安装核心文件时，将自动安装 RTCLocal 数据库。 请注意，不需要在观察程序节点上安装 SQL Server。 相反，系统会自动为您安装 SQL Server Express。

要安装 Lync Server 2013 core 文件和 RTCLocal 数据库，请执行以下操作：

1.  在观察程序节点计算机上，单击 "**开始**"，单击 "**所有程序**"，单击 "**附件**"，右键单击 "**命令提示符**"，然后单击 "以**管理员身份运行**"。

2.  在控制台窗口中，键入以下命令，然后按 ENTER，使用 Lync Server 设置文件的相应路径：
    
        D:\Setup.exe /BootstrapLocalMgmt

若要验证是否已成功安装核心 Lync 服务器组件，请依次单击 "**开始**"、"**所有程序**"、" **lync server 2013**"，然后单击 " **lync server Management Shell**"。 在 Lync Server 2013 命令行管理程序中，键入以下 Windows PowerShell 命令，然后按 ENTER：

    Get-CsWatcherNodeConfiguration

第一次运行此命令时，由于尚未配置任何观察程序节点计算机，因此不会返回任何数据。 只要命令运行时不返回错误，您就可以假设 Lync Server 设置已成功完成。

如果你的观察程序节点计算机位于你的外围网络内，你可以运行以下命令来验证 Lync Server 2013 的安装：

    Get-CsPinPolicy

您将收到与以下内容类似的信息，具体取决于为在您的组织中使用而配置的个人识别码（PIN）策略数：

    Identity             : Global
    Description          :
    MinPasswordLength    : 5
    PINHistoryCount      : 0
    AllowCommonPatterns  : False
    PINLifetime          : 0
    MaximumLogonAttempts :

如果你看到有关 PIN 策略的信息，则表示你已成功安装核心组件。

</div>

<span> </span>

</div>

</div>

</div>

