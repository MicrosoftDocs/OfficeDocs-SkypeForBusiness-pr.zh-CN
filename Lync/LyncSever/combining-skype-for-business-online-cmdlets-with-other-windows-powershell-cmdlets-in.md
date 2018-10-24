---
title: 将 Lync Online Cmdlet 与其他 Windows PowerShell Cmdlet 组合使用
TOCTitle: 将 Lync Online Cmdlet 与其他 Windows PowerShell Cmdlet 组合使用
ms:assetid: 8bb8800a-f966-4570-8c8b-db87a91ad783
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn362816(v=OCS.15)
ms:contentKeyID: 56271179
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 将 Lync Online Cmdlet 与其他 Windows PowerShell Cmdlet 组合使用

 

_**上一次修改主题：** 2015-06-22_

当您使用 Windows PowerShell 连接到 Skype for Business Online 时，大约 40 个 Skype for Business Online cmdlet 将可供您使用。但是，在管理 Skype for Business Online 时，您不限制为仅使用这 40 个cmdlet。除了 Skype for Business Online cmdlet 之外，您也可以使用您的计算机上安装的任何其他 Windows PowerShell cmdlet。（当您安装 Windows PowerShell 3.0 时，也将安装数百个核心 Windows PowerShell cmdlet。）您的命令可以混合和匹配 Skype for Business Online cmdlet 以及您的计算机上任何其他可用的 cmdlet。

尽管 Windows PowerShell 3.0 中的完整过程超出了本文档的范畴，但是下面介绍了一些示例，显示您可能需要混合和匹配 cmdlet 的原因。首先，没有 Skype for Business Online cmdlet 包括打印命令，并且此类命令都不可在 Windows PowerShell 控制台中找到。那么如何使用 cmdlet 获得检索到的信息的打印输出呢？一种方法是检索信息，然后将该信息发送到 **Out-Printer** cmdlet：

    Get-CsTenant | Out-Printer

由于不包括任何其他参数，**the Out-Printer** cmdlet 返回的所有信息将打印至默认打印机。

同样，没有任何 Skype for Business Online cmdlet 包括允许您将数据保存到文件的参数。然而没关系：此命令使用 **Out-File** cmdlet 将返回的信息保存到文本文件 C:\\Logs\\Tenants.txt：

    Get-Tenant | Out-File -FilePath "C:\Logs\Tenants.txt"

此命令使用 **Select-Object** cmdlet 限制屏幕上返回和显示的数据。在此示例中，[Get-CsOnlineUser](get-csonlineuser.md) cmdlet 检索所有 Skype for Business Online 用户的信息，而 **Select-Object** cmdlet 用于将显示的数据限制为用户的标识值及其存档策略：

    Get-CsOnlineUser | Select-Object Identity, ArchivingPolicy

由于您的计算机上有数百个 cmdlet 可供使用，您可能难以确定哪些 cmdlet 是 Skype for Business Online cmdlet，哪些 cmdlet 不是 Skype for Business Online cmdlet。要返回 Skype for Business Online cmdlet（和仅 Skype for Business Online cmdlet）列表，您必须首先确定包含所有 Skype for Business Online cmdlet 的临时 Windows PowerShell 模块的名称。为此，请从 Windows PowerShell 提示符处运行此命令：

    Get-Module

屏幕上将显示以下类似信息：

    ModuleType Name                 ExportedCommands
    ---------- ----                 ----------------
    Manifest   Microsoft.PowerS...  {Add-Computer, Add-Content, A...}
    Script     tmp_5astd3uh.m5v     {Disable-CsMeetingRoom, Enabl...}

ModuleType 为 Script 的模块是包含 Skype for Business Online cmdlet 的模块。要返回这些 cmdlet 的列表，请使用 Script 模块的名称作为模块名称运行 **Get-Command** cmdlet：

    Get-Command -Module tmp_5astd3uh.m5v

您可能有多个 ModuleType 等于 Script 的模块。在这种情况下，您可以运行以下命令以了解哪些模块包括 **Get-CsTenant** cmdlet：

    Get-Command Get-CsTenant

为 **Get-CsTenant** cmdlet 返回的模块将是包含所有 Skype for Business Online cmdlet 的模块：

    CommandType     Name                                               ModuleName
    -----------     ----                                               ----------
    Function        Get-CsTenant                                       tmp_5astd3uh.m5v

## 另请参阅

#### 概念

[Windows PowerShell 和 Lync Online 简介](an-introduction-to-windows-powershell-and-skype-for-business-online.md)

