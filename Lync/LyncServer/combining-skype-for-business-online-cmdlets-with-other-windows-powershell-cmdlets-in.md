---
title: 将 Skype for Business Online cmdlet 与中的其他 Windows PowerShell cmdlet 结合使用
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Combining Skype for Business Online cmdlets with other Windows PowerShell cmdlets
ms:assetid: 8bb8800a-f966-4570-8c8b-db87a91ad783
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362816(v=OCS.15)
ms:contentKeyID: 56558835
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bd4f08370e5aeab6688fdbf2ce13a3e5ccb11a37
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755018"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="combining-skype-for-business-online-cmdlets-with-other-windows-powershell-cmdlets-in"></a>将 Skype for Business Online cmdlet 与中的其他 Windows PowerShell cmdlet 结合使用

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-07-05_

当您使用 Windows PowerShell 连接到 Skype for business Online 时，可以使用大约 40 Skype for Business Online cmdlet。 但是，在管理 Skype for Business Online 时，您并不局限于仅使用这些 40 cmdlet。 除了 Skype for Business Online cmdlet 之外，还可以使用安装在计算机上的任何其他 Windows PowerShell cmdlet。 （在安装 Windows PowerShell 3.0 时，还会安装数百个核心 Windows PowerShell cmdlet。）你的命令可以混合和匹配 Skype for Business Online cmdlet 以及你的计算机上可用的任何其他 cmdlet。

尽管 Windows PowerShell 3.0 中的完整课程不在本文的讨论范围之内，但下面的几个示例展示了您可能需要混合和匹配 cmdlet 的原因。 首先，没有任何 Skype for Business Online cmdlet 包含打印命令，也不能在 Windows PowerShell 控制台中找到此类命令。 那么，如何获取由 cmdlet 检索的信息的打印输出？ 一种方法是检索信息，然后将该信息发送到**打印机**cmdlet：

    Get-CsTenant | Out-Printer

由于不包含任何其他参数，因此**打印机**cmdlet 返回的所有信息将打印到默认打印机。

同样，任何 Skype for Business Online cmdlet 都不包含允许您将数据保存到文件中的参数。 但这也是正常的：此命令使用**Out 文件**cmdlet 将返回的信息保存到文本文件 C： \\ Logs \\Tenants.txt：

    Get-Tenant | Out-File -FilePath "C:\Logs\Tenants.txt"

此命令使用**Select-Object** cmdlet 来限制在屏幕上返回和显示的数据。 在此示例中， [get-csonlineuser](https://technet.microsoft.com/library/JJ994026(v=OCS.15)) cmdlet 检索所有 Skype For business Online 用户的信息，然后使用**Select-Object** cmdlet 将显示的数据限制为用户的标识值及其存档策略：

    Get-CsOnlineUser | Select-Object Identity, ArchivingPolicy

由于在您的计算机上有数百个 cmdlet 可供使用，因此您可能很难确定哪些 cmdlet 是 Skype for Business Online cmdlet，哪些是不是哪些。 若要返回 Skype for Business Online cmdlet （且仅适用于 Skype for business Online cmdlet）的列表，您必须首先确定包含所有 Skype for Business Online cmdlet 的临时 Windows PowerShell 模块的名称。 为此，请在 Windows PowerShell 提示符处运行以下命令：

    Get-Module

屏幕上将显示类似以下内容的信息：

    ModuleType Name                 ExportedCommands
    ---------- ----                 ----------------
    Manifest   Microsoft.PowerS...  {Add-Computer, Add-Content, A...}
    Script     tmp_5astd3uh.m5v     {Disable-CsMeetingRoom, Enabl...}

包含 ModuleType 脚本的模块是包含 Skype for Business Online cmdlet 的模块。 若要返回这些 cmdlet 的列表，请使用脚本模块的名称作为模块名称，以运行**Get 命令**cmdlet：

    Get-Command -Module tmp_5astd3uh.m5v

有可能有一个 ModuleType 等于 Script 的多个模块。 在这种情况下，您可以运行以下命令来找出包含**get-cstenant** cmdlet 的模块：

    Get-Command Get-CsTenant

为**get-cstenant** cmdlet 返回的模块将是包含所有 Skype For business Online cmdlet 的模块：

    CommandType     Name                                               ModuleName
    -----------     ----                                               ----------
    Function        Get-CsTenant                                       tmp_5astd3uh.m5v

<div>

## <a name="see-also"></a>另请参阅


[Windows PowerShell 和 Skype for business Online 简介](https://technet.microsoft.com/library/Dn362785(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

