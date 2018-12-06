---
title: 查看 CDR 配置信息
TOCTitle: 查看 CDR 配置信息
ms:assetid: 77bd553f-da89-4c84-a5d0-2f7e91d04383
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688096(v=OCS.15)
ms:contentKeyID: 49888469
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 查看 CDR 配置信息

 

_**上一次修改主题：** 2013-02-23_

利用呼叫详细信息记录 (CDR)，可以跟踪对等即时消息会话、IP 语音 (VoIP) 电话呼叫和会议呼叫等的使用情况。此使用情况数据包含有关呼叫者、被叫方、呼叫时间及通话时长的信息。

在安装 Microsoft Lync Server 2013 时，系统将为您创建一个 CDR 配置设置的全局集合。管理员还可以选择创建可应用于各个站点的自定义设置集合。可使用 Lync Server 控制面板或 [Get-CsCdrConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsCdrConfiguration) cmdlet 查看您组织中使用的 CDR 配置设置。

## 使用 Lync Server 控制面板查看 CDR 配置信息

1.  在 Lync Server 控制面板中，单击“监控和存档”。

2.  所有 CDR 配置设置的列表将显示在“呼叫详细信息记录”选项卡中；对于每个设置集合，您将看到集合“名称”；是否已启用 CDR（“CDR”属性）；是否已启用清除（“CDR 清除”属性）。若要查看有关某个集合的详细信息，请双击此集合或选择相应的集合，单击“编辑”，然后单击“显示详细信息”。请注意，您一次只能查看一个 CDR 配置设置集合的详细信息。

## 使用 Lync Server 命令行管理程序 cmdlet 查看 CDR 配置信息

还可以使用 Lync Server 命令行管理程序和 Get-CsCdrConfiguration cmdlet 查看 CDR 配置设置。可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## 查看 CDR 配置信息

  - 若要查看有关您的所有 CDR 配置设置的信息，请在 Lync Server 命令行管理程序中键入以下命令，然后按 Enter：
    
        Get-CsCdrConfiguration
    
    这将返回与以下内容类似的信息：
    
        Identity               : Global
        EnableCDR              : True
        EnablePurging          : True
        KeepCallDetailForDays  : 90
        KeepErrorReportForDays : 60
        PurgeHourOfDay         : 2

有关详细信息，请参阅 [Get-CsCdrConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsCdrConfiguration) cmdlet 的帮助主题。

