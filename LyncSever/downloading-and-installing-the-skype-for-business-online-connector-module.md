---
title: 下载和安装 Lync Online 连接器模块
TOCTitle: 下载和安装 Lync Online 连接器模块
ms:assetid: a0c87219-b642-4201-85d4-a85c2163d1eb
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn362829(v=OCS.15)
ms:contentKeyID: 56271184
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 下载和安装 Lync Online 连接器模块

 

_**上一次修改主题：** 2016-12-08_

Skype for Business Online 连接器模块包括 **New-CsOnlineSession** cmdlet，它使您能够创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持（有关详细信息，请参阅[为您的计算机配置 Lync Online 管理](configuring-your-computer-for-skype-for-business-online-management.md)），可以从 Microsoft 下载中心下载，网址为 [http://go.microsoft.com/fwlink/?LinkId=294688](http://go.microsoft.com/fwlink/?linkid=294688)。下载 LyncOnlinePowershell.exe 文件，然后完成以下过程：

1.  双击“LyncOnlinePowershell.exe”文件。

2.  在 Skype for Business Online 租户 PowerShell 设置向导中，在“Microsoft Software License Terms”页面上，选择“I accept the terms in the License Agreement”，然后单击“Install”。如果显示“User Account Control”对话框，请单击“Yes”以继续安装。

3.  在“Completed the Microsoft Lync Online, Tenant PowerShell Setup”页面上，单击“Finish”。

安装程序会将 Skype for Business Online 连接器模块（和 **New-CsOnlineSession** cmdlet）复制到您的本地计算机。要访问模块，请在管理员凭据下启动 Windows PowerShell 会话，然后运行以下命令：

    Import-Module LyncOnlineConnector

如果不希望每次启动 Windows PowerShell 时都键入此命令，您可以将命令添加到您的 Windows PowerShell 配置文件。为此，请在 Windows PowerShell 提示符下键入以下命令，然后按 Enter：

    notepad.exe $profile

当记事本出现时，请将以下行添加到配置文件（如果有）中已有的命令底部：

    Import-Module LyncOnlineConnector

保存文件。 下一次启动 Windows PowerShell 时，Skype for Business Online 连接器模块将自动导入。请注意，如果您未在管理员凭据下运行 Windows PowerShell，那么您将收到错误消息，并且模块不会加载。

除了安装 Skype for Business Online 连接器模块之外，LyncOnlinePowershell.exe 也会安装两个附加组件：.NET Framework 4.5 和 Microsoft Visual C++ 2012 可再发行组件包 (x64)（版本 11.0.50727）。.NET Framework 4.5 提供用于构建和运行 .NET 应用程序的基础结构（包括 Windows PowerShell）。Visual C++ 可再发行组件包将为未安装 Microsoft Visual Studio 2012 的计算机安装 Visual C++ 运行时组件。

## 另请参阅

#### 概念

[为您的计算机配置 Lync Online 管理](configuring-your-computer-for-skype-for-business-online-management.md)

