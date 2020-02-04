---
title: 将 Skype for Business Online cmdlet 与其他 Windows PowerShell cmdlet 结合在一起
ms.reviewer: ''
ms.author: kenwith
author: kenwith
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
ms.openlocfilehash: e7d0dd6070eb3c69b23f03e56bf542025c221b15
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727973"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="combining-skype-for-business-online-cmdlets-with-other-windows-powershell-cmdlets-in"></a>将 Skype for Business Online cmdlet 与其他 Windows PowerShell cmdlet 结合在一起

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-07-05_

使用 Windows PowerShell 连接到 Skype for business Online 时，将提供大约 40 Skype for business Online cmdlet 供您使用。 但是，管理 Skype for Business Online 时，不仅限于使用这些 40 cmdlet。 除了 Skype for Business Online cmdlet 外，你还可以使用你的计算机上安装的任何其他 Windows PowerShell cmdlet。 （安装 Windows PowerShell 3.0 时，还会安装数以百计的核心 Windows PowerShell cmdlet。）你的命令可以混合和匹配 Skype for Business Online cmdlet 以及你的计算机上可用的任何其他 cmdlet。

虽然 Windows PowerShell 3.0 中的完整课程不在本文的范围之内，但下面提供了一些示例，显示了可能希望混合和匹配 cmdlet 的原因。 首先，所有 Skype for Business Online cmdlet 都不包含打印命令，也不能在 Windows PowerShell 控制台中找到此类命令。 那么，如何获取由 cmdlet 检索的信息的打印输出？ 一种方法是检索信息，然后将该信息发送到**打印机**cmdlet：

    Get-CsTenant | Out-Printer

由于不包含任何其他参数，**打印机**cmdlet 返回的所有信息将打印到默认打印机。

同样，任何 Skype for Business Online cmdlet 都不包含允许你将数据保存到文件的参数。 但这是正常的：此命令使用**Out 文件**cmdlet 将返回的信息保存到文本文件 C：\\记录\\承租人：

    Get-Tenant | Out-File -FilePath "C:\Logs\Tenants.txt"

此命令使用**Select-对象**cmdlet 限制在屏幕上返回和显示的数据。 在此示例中， [CsOnlineUser](https://technet.microsoft.com/en-us/library/JJ994026(v=OCS.15)) cmdlet 检索所有 Skype For business Online 用户的信息，然后使用**Select 对象**cmdlet 将显示的数据限制为用户的标识值及其存档策略：

    Get-CsOnlineUser | Select-Object Identity, ArchivingPolicy

由于你的计算机上可以使用数百个 cmdlet，因此你可能无法确定哪些 cmdlet 是 Skype for Business Online cmdlet 以及哪些 cmdlet 不是。 若要返回 Skype for Business Online cmdlet （且仅适用于 Skype for business Online cmdlet）的列表，必须首先确定包含所有 Skype for Business Online cmdlet 的临时 Windows PowerShell 模块的名称。 若要执行此操作，请从 Windows PowerShell 提示符运行以下命令：

    Get-Module

屏幕上将显示类似于以下内容的信息：

    ModuleType Name                 ExportedCommands
    ---------- ----                 ----------------
    Manifest   Microsoft.PowerS...  {Add-Computer, Add-Content, A...}
    Script     tmp_5astd3uh.m5v     {Disable-CsMeetingRoom, Enabl...}

带有 ModuleType 脚本的模块是包含 Skype for Business Online cmdlet 的模块。 若要返回这些 cmdlet 的列表，请运行**Get Command** cmdlet，使用脚本模块的名称作为模块名称：

    Get-Command -Module tmp_5astd3uh.m5v

可能有多个模块的 ModuleType 等于脚本。 在这种情况下，你可以运行以下命令来查明哪个模块包括**CsTenant** cmdlet：

    Get-Command Get-CsTenant

为**CsTenant** cmdlet 返回的模块将是包含所有 Skype For business Online cmdlet 的模块：

    CommandType     Name                                               ModuleName
    -----------     ----                                               ----------
    Function        Get-CsTenant                                       tmp_5astd3uh.m5v

<div>

## <a name="see-also"></a>另请参阅


[Windows PowerShell 和 Skype for Business Online 简介](https://technet.microsoft.com/en-us/library/Dn362785(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

