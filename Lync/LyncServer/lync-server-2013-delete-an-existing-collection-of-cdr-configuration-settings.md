---
title: 删除 CDR 配置设置的现有集合
TOCTitle: 删除 CDR 配置设置的现有集合
ms:assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688128(v=OCS.15)
ms:contentKeyID: 49888506
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 删除 CDR 配置设置的现有集合

 

_**上一次修改主题：** 2013-02-23_

利用呼叫详细信息记录 (CDR)，可以跟踪对等即时消息会话、IP 语音 (VoIP) 电话呼叫和会议呼叫等的使用情况。此使用情况数据包含有关呼叫者、被叫方、呼叫时间及通话时长的信息。

在安装 Microsoft Lync Server 2013 时，系统将为您创建一个 CDR 配置设置的全局集合。管理员还可以选择创建可应用于各个站点的自定义设置集合。根据设计，在站点范围配置的设置优先于在全局范围配置的设置。如果您删除站点范围的设置，则在该站点中使用全局设置管理 CDR。

请注意，您也可以“删除”全局设置。但是，这不会实际删除全局设置，而是将该集合中的所有属性重置为其默认值。例如，默认情况下，将在 CDR 配置设置集合中启用清除。假定您修改全局集合以便禁用清除。如果您稍后删除全局设置，则所有属性都将被重置为其默认值。在此情况下，这意味着将再次启用清除。

可使用 Lync Server 控制面板或 [Remove-CsCdrConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsCdrConfiguration) cmdlet 删除 CDR 配置设置。

## 使用 Lync Server 控制面板删除 CDR 配置设置

1.  在 Lync Server 控制面板中，单击“监控和存档”。

2.  在“呼叫详细信息记录”选项卡上，选择要删除的 CDR 设置的集合。若要删除多个集合，请单击第一个集合，然后在按住 Ctrl 键的同时单击其他集合。

3.  单击“编辑”，然后单击“删除”。

4.  在Lync Server 控制面板对话框中，单击“确定”。

## 使用 Lync Server 命令行管理程序 cmdlet 删除 CDR 配置设置

您可以使用 Windows PowerShell 和 **Remove-CsCdrConfiguration** cmdlet 删除呼叫详细信息记录配置设置。此 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## 删除指定的 CDR 配置设置集合

  - 此命令删除适用于 Redmond 站点的 CDR 配置设置：
    
        Remove-CsCdrConfiguration -Identity "site:Redmond"

## 删除适用于站点范围的所有 CDR 配置设置

  - 此命令删除适用于站点范围的所有 CDR 配置设置：
    
        Get-CsCdrConfiguration -Filter "site:*" | Remove-CsCdrConfiguration

## 删除禁用呼叫详细信息记录的 CDR 配置设置

  - 此命令删除已禁用呼叫详细信息记录的所有 CDR 配置设置：
    
        Get-CsCdrConfiguration | Where-Object {$_.EnableCDR -eq $False} | Remove-CsCdrConfiguration

有关详细信息，请参阅 [Remove-CsCdrConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsCdrConfiguration) cmdlet 的帮助主题。

