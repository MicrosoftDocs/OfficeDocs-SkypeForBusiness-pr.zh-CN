---
title: Lync Server 2013：查看设备更新配置设置
TOCTitle: 查看设备更新配置设置
ms:assetid: aa6a70a9-bd77-4606-b797-ea6a3bab9cf2
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ994059(v=OCS.15)
ms:contentKeyID: 52061101
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 查看 Lync Server 2013 中的设备更新配置设置

 

_**上一次修改主题：** 2016-12-08_

您可以使用 Lync Server 命令行管理程序和 **Get-CsDeviceUpdateConfiguration** cmdlet 来查看设备更新服务配置设置。可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。

> [!NOTE]  
> 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 <a href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</a>。




  - 
    
    若要查看有关所有语音路由的信息，请在 Lync Server 命令行管理程序中键入以下命令，然后按 Enter：
    
        Get-CsDeviceUpdateConfiguration
    
    此命令会返回类似下列信息：
    
        Identity               : Global
        ValidLogFileTypes      : {Watson, Config, Diaglog, CELog}
        ValidLogFileExtensions : {.dmp, .clg, .clg1, .clg2...}
        MaxLogFileSize         : 1024000
        MaxLogCacheLimit       : 512000
        LogCleanUpInterval     : 10.00:00:00
        LogFlushInterval       : 00:05:00
        LogCleanUpTimeOfDay    :

有关此 cmdlet 的详细信息，请参阅 [Get-CsDeviceUpdateConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsDeviceUpdateConfiguration) 上的帮助主题。

