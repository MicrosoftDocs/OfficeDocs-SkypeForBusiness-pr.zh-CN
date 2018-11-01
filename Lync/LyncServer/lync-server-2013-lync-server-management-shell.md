---
title: Lync Server 命令行管理程序
TOCTitle: Lync Server 命令行管理程序
ms:assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398474(v=OCS.15)
ms:contentKeyID: 49313090
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 命令行管理程序

 

_**上一次修改主题：** 2016-12-08_

与 Microsoft Office Communications Server 2007 R2 中提供的功能相比，Microsoft Lync Server 2010 引入了许多新增和改进的功能。其中一项改进是管理实现的方法。例如，名为 Lync Server 控制面板的新用户界面为大多数人习惯使用的 Microsoft 管理控制台带来了重大转变。管理功能的另一项重大改进是纳入了 Windows PowerShell。

Windows PowerShell 使您可以从命令行管理 Microsoft 应用程序。它包括命令行环境、特定于产品的命令和完整的脚本语言。2006 年年底首次将 Windows PowerShell 作为 Windows 操作系统的可下载版本引入，并且合并为 Microsoft Exchange Server 2007 管理功能的命令行界面。此后，它继续发展并且已合并到大多数 Microsoft Server 产品中，其中最新的产品是 Microsoft Lync Server 2013。Lync Server 2010 引入了近 550 种特定于产品的 cmdlet，您可以使用这些 cmdlet 管理部署的每个方面。

以下各节包含 cmdlet 及其说明的列表。也可直接从命令行获取此信息。只需在 Lync Server 命令行管理程序命令提示符处键入以下内容：

    Get-Help <cmdlet name> -Full

例如，要通过命令提示符检索有关 **New-CsVoicePolicy** cmdlet 的帮助，请键入以下内容：

    Get-Help New-CsVoicePolicy -Full

了解关于 Lync Server 2013 中 Windows PowerShell 的功能：

  - 要运行 Lync Server cmdlet，请打开 Lync Server 命令行管理程序。
    
    > [!WARNING]  
	> 如果打开 Windows PowerShell 窗口，而不是 Lync Server 命令行管理程序，则默认情况下将无法运行 Lync Server cmdlet。要在 Windows PowerShell 中运行 Lync Server cmdlet，请先在 Windows PowerShell 命令提示符处键入以下内容：<br />
    > Import-Module Lync


  - Lync Server 命令行管理程序会自动安装在每台 Lync Server Enterprise Edition 前端服务器或 Standard Edition Server 上。

  - 有关新增和更新的信息、示例脚本和入门帮助，以及有关 Windows PowerShell 和 Microsoft Lync Server 2013 cmdlet 的详细信息，请访问 Lync Server Windows PowerShell 博客，网址为 [http://go.microsoft.com/fwlink/?linkid=203150\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=203150%26clcid=0x804)。

