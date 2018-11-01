---
title: 安装 Lync Server 2013 核心文件和 RTCLocal 数据库
TOCTitle: 安装 Lync Server 2013 核心文件和 RTCLocal 数据库
ms:assetid: 206f0c1d-40f7-45b6-aa62-88aaef6cf7f6
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204734(v=OCS.15)
ms:contentKeyID: 49312223
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 安装 Lync Server 2013 核心文件和 RTCLocal 数据库

 

_**上一次修改主题：** 2012-10-20_

若要在计算机上安装 Lync Server 2013 核心文件，请完成以下过程。在您安装核心文件时会自动安装 RTCLocal 数据库。请注意，您无需在观察程序节点上安装 SQL Server，系统会为您自动安装 SQL Server Express。

若要安装 Lync Server 2013 核心文件和 RTCLocal 数据库，请执行以下操作：

1.  在观察程序节点计算机上，依次单击“开始”、“所有程序”、“附件”，右键单击“命令提示符”，然后单击“以管理员身份运行”。

2.  在控制台窗口中，键入以下命令后按 Enter，以转到 Lync Server 安装文件的相应路径：
    
        D:\Setup.exe /BootstrapLocalMgmt

若要验证是否已成功安装核心 Lync Server 组件，请依次单击“开始”、“所有程序”、“Lync Server 2013”和“Lync Server 命令行管理程序”。在 Lync Server 2013 命令行管理程序中，键入以下 Windows PowerShell 命令，然后按 Enter：

    Get-CsWatcherNodeConfiguration

首次运行此命令时，不会返回任何数据，因为您尚未配置任何观察程序节点计算机。只要此命令运行而不返回错误，您就可以认为已成功完成 Lync Server 安装。

如果您的观察程序节点计算机位于您的外围网络内部，则可以运行以下命令来验证 Lync Server 2013 安装：

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

