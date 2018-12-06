---
title: 每次启动 Windows PowerShell 时自动连接到 Lync Online
TOCTitle: 每次启动 Windows PowerShell 时自动连接到 Lync Online
ms:assetid: 68f76c36-5dd6-48ea-b19a-d65593199e4c
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn362799(v=OCS.15)
ms:contentKeyID: 56271150
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 每次启动 Windows PowerShell 时自动连接到 Lync Online

 

_**上一次修改主题：** 2015-06-22_

如果您不记得连接到 Skype for Business Online 所需的所有命令，则可以进行配置，以便只需双击快捷方式文件并输入您的 Skype for Business Online 密码，这样即可连接到 Skype for Business Online。

为此，请首先打开记事本（或任何其他文本编辑器），然后粘贴在以下命令中，取代您的 Skype for Business Online 帐户名称（如 kenmyer@litwareinc.com）：

    $credential = Get-Credential "kenmyer@litwareinc.com"
    $session = New-CsOnlineSession -Credential $credential 
    Import-PSSession $session

使用文件扩展名 .PS1 保存文件（例如，C:\\Scripts\\LyncOnline.ps1）。

保存文件后，请完成以下过程以创建可启动 Windows PowerShell 并在启动时运行脚本的桌面快捷方式：

1.  右键单击桌面，单击“新建”，然后单击“快捷方式”。

2.  在“创建快捷方式”向导中，在“请键入项目的位置”框中键入以下内容，然后单击“下一步”（记得使用您刚刚创建的脚本文件的路径）：
    
        powershell.exe -noexit C:\Scripts\LyncOnline.ps1

3.  在“键入该快捷方式的名称”框中，键入快捷方式的名称（例如，**Skype for Business Online**），然后单击“完成”。

4.  下一次您想使用 Windows PowerShell 管理 Skype for Business Online 时，只需双击新的快捷方式并输入密码。该脚本将负责建立连接和设置新的远程会话。

此新会话通常不会存储在变量 $session 中。它通常将被提供会话 ID 1。这不会以任何方式影响您的会话，至少在关闭会话之前都是如此。要执行该操作，您在调用 **Remove-PSSession** cmdlet 时需要引用会话 ID：

    Remove-PSSession 1

您可以通过从 Windows PowerShell 提示符处运行此命令来验证为您的 Skype for Business Online 会话指定的 ID：

    Get-PSSession

## 另请参阅

#### 概念

[为您的计算机配置 Lync Online 管理](configuring-your-computer-for-skype-for-business-online-management.md)

