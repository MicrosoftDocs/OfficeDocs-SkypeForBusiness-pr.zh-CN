---
title: 从相同的远程 Windows PowerShell 会话管理 Lync Online 和 Microsoft Exchange
TOCTitle: 从相同的远程 Windows PowerShell 会话管理 Lync Online 和 Microsoft Exchange
ms:assetid: 4eb4b5f0-f407-46bd-a2ac-a7ccbc387d51
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn362787(v=OCS.15)
ms:contentKeyID: 56271139
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 从相同的远程 Windows PowerShell 会话管理 Lync Online 和 Microsoft Exchange

 

_**上一次修改主题：** 2015-06-22_

当您订阅 Office 365 时，您不仅能够获得对 Skype for Business Online 的访问权限；而且也可以获得对 Exchange Online 的访问权限。您可以使用 Windows PowerShell 的远程会话管理 Skype for Business Online。您也可以使用 Windows PowerShell 的远程会话管理 Exchange。但是，Skype for Business Online 和 Exchange Online 不共享相同 URI，他们也不使用相同的连接方法。这意味着您需要使用单独的会话管理 Skype for Business Online 和 Exchange。或者，有办法使用 Windows PowerShell 的单个会话管理两个产品吗？

最终，您不仅能够从相同的 Windows PowerShell 示例管理两个产品，而且设置此双重管理会话非常简单。若要开始，请启动 Windows PowerShell 并照常连接到 Skype for Business Online：创建凭据对象，然后创建可连接到 Skype for Business Online 的新会话：

    $credential = Get-Credential "kenmyer@litwareinc.com"
    $lyncSession = New-CsOnlineSession -Credential $credential

下一步，使用类似过程连接到 Exchange Online。请注意，您不需要创建新的凭据对象。您可以继续使用当您登录到 Skype for Business Online 时使用的相同对象 ($credential)：

    $exchangeSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://outlook.office365.com/powershell-liveid/" -Credential $credential -Authentication "Basic" -AllowRedirection

当连接到 Exchange Online 时，您应始终使用 URI https://outlook.office365.com/powershell-liveid/，无论您的 Office 365 URI 如何都是如此。在您经过身份验证后，您将自动重定向到合适的 URI。这样一来，包括 AllowRedirection 参数就特别重要。如果忽略此参数，虽然您会通过身份验证，但重定向将失败，不会将您连接到 Exchange Online：

    New-PSSession : [ps.outlook.com] The WinRM service cannot process the request because the request needs to be sent to a different machine. Use the redirect information to send the request to a new machine.  Redirect location reported: https://pod51043psh.outlook.com/powershell-liveid?PSVersion=3.0 . To automatically connect to the redirected URI, verify  MaximumConnectionRedirectionCount" property of session preference variable "PSSessionOption" and use "AllowRedirection" parameter on the cmdlet.

此时，您应在计算机上运行两个独立的远程会话。要进行验证，请在 Windows PowerShell 提示符处键入以下命令：

    Get-PSSession

您应看到与此显示的屏幕类似的信息：

    Id Name      ComputerName  State   ConfigurationName     Availability
    -- ----      ------------  -----   -----------------     ------------
     1 Session1  pod510w43...  Opened  Microsoft.PowerShell     Available
     2 Session2  up02921vd...  Opened  Microsoft.Exchange       Available

您现在有一对远程会话可导入到您的 Windows PowerShell 本地会话中。要执行该操作，请运行以下两个命令：

    Import-PSSession $lyncSession
    Import-PSSession $exchangeSession

此时，您有 Skype for Business Online 和 Exchange Online cmdlet 可供使用。要进行验证，请运行以下命令并确保获得用户信息：

    Get-CsOnlineUser -ResultSize 1

然后运行以下 Exchange 命令并验证您是否获得邮箱信息：

    Get-Mailbox -ResultSize 1

当您想要结束管理会话时，请确保关闭两个远程会话：

    Remove-PSSession $lyncSession
    Remove-PSSession $exchangeSession

## 另请参阅

#### 概念

[为您的计算机配置 Lync Online 管理](configuring-your-computer-for-skype-for-business-online-management.md)

