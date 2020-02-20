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
ms.openlocfilehash: 17b3b1925607a80f143c57e6185c7a709b19ee0c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146745"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-server-2013-core-files-and-the-rtclocal-database"></a>安装 Lync Server 2013 core 文件和 RTCLocal 数据库

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-20_

若要在计算机上安装 Lync Server 2013 core 文件，请完成以下过程。 当您安装核心文件时，将自动安装 RTCLocal 数据库。 请注意，不需要在观察程序节点上安装 SQL Server。 相反，系统会自动为你安装 SQL Server Express。

若要安装 Lync Server 2013 core 文件和 RTCLocal 数据库，请执行以下操作：

1.  在观察程序节点计算机上，依次单击“开始”****、“所有程序”****、“附件”****，右键单击“命令提示符”****，然后单击“以管理员身份运行”****。

2.  在控制台窗口中，键入以下命令，然后按 ENTER，并使用适用于 Lync Server 安装程序文件的路径：
    
        D:\Setup.exe /BootstrapLocalMgmt

若要验证是否已成功安装核心 Lync Server 组件，请依次单击 "**开始**"、"**所有程序**"、" **lync server 2013**"，然后单击 " **lync server Management Shell**"。 在 "Lync Server 2013 命令行管理程序" 中，键入以下 Windows PowerShell 命令，然后按 ENTER：

    Get-CsWatcherNodeConfiguration

首次运行此命令时，不会返回任何数据，因为您尚未配置任何观察程序节点计算机。 只要命令在不返回错误的情况下运行，您就可以假定 Lync Server 安装程序已成功完成。

如果您的观察程序节点计算机位于您的外围网络中，则可以运行以下命令来验证 Lync Server 2013 的安装：

    Get-CsPinPolicy

根据配置用于您的组织的个人标识号 (PIN) 策略的数目，您将收到如下信息：

    Identity             : Global
    Description          :
    MinPasswordLength    : 5
    PINHistoryCount      : 0
    AllowCommonPatterns  : False
    PINLifetime          : 0
    MaximumLogonAttempts :

如果显示有关您的 PIN 策略的信息，表明您已成功安装核心组件。

</div>

<span> </span>

</div>

</div>

</div>

