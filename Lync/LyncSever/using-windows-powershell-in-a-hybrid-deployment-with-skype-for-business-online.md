---
title: 在混合部署中使用 Windows PowerShell
TOCTitle: 在混合部署中使用 Windows PowerShell
ms:assetid: b19625d4-4b68-403c-a072-5296aa590556
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn362835(v=OCS.15)
ms:contentKeyID: 56271195
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在混合部署中使用 Windows PowerShell

 

_**上一次修改主题：** 2015-06-22_

在混合部署中，组织将一些用户驻留在 Lync Server 2013 的内部部署版本上，而其他用户驻留在 Skype for Business Online 上。您可以使用单个 Windows PowerShell 会话同时管理 Lync Server 的内部部署版本和 Skype for Business Online 租户。为此，您需要了解两个重要事项：

1.  如何同时与 Lync Server 和 Skype for Business Online 建立连接。

2.  如何从此同时连接引用 Skype for Business Online 设置。

同时与 Lync Server 和 Skype for Business Online 建立连接真的非常简单。为此，请首先照常连接 Lync Server：启动 Lync Server 命令行管理程序 或创建与前端池的远程连接。成功连接到 Lync Server 的内部部署版本之后，您可以按照仅连接到 Skype for Business Online 时使用的相同过程连接到 Skype for Business Online。要建立此连接，您必须首先使用您的 Office 365 登录信息创建 Windows PowerShell 凭据对象。为此，请在 Windows PowerShell 提示符处键入以下内容，然后按 Enter：

    $credential = Get-Credential

按 Enter 之后，您应会看到“Windows PowerShell 凭据”对话框：

![Windows PowerShell 登录凭据](images/Dn362835.0f04e0a1-c9d6-4341-a0bb-ef721c4815fd(OCS.15).png "Windows PowerShell 登录凭据")

在“用户名”框中，键入您的 Skype for Business Online 名称。在“密码”框中，键入您的 Skype for Business Online 密码（密码将被屏蔽，在屏幕上不可见）。例如，如果您的用户名是 kenmyer@litwareinc.com，您的密码是 p@ssw0rd\!，则对话框将与此类似：

![Windows PowerShell 登录凭据](images/Dn362835.85977a0e-b14a-4aec-a45e-8548e9c9f691(OCS.15).png "Windows PowerShell 登录凭据")

要创建凭据对象，请单击“确定”。在创建凭据对象之后，您可以通过运行以下命令连接到 Skype for Business Online：

    $session = New-CsOnlineSession -Credential $credential

确保如上所示准确地键入。请注意，您的 Skype for Business Online 域的名称无关紧要。**New-CsOnlineSession** cmdlet 会将您连接到 Office 365 并使用提供的凭据帮您登录。进行连接和进行身份验证之后，您将自动重定向到合适的 URI。

如果连接成功，您将在 Windows PowerShell 控制台中看到与此类似的消息：

    VERBOSE: Determining domain to admin
    VERBOSE: AdminDomain = litwareinc.com
    VERBOSE: Discovering PowerShell endpoint URI
    VERBOSE: TargetUri = https://webdir0d.litwareinc.com/OcsPowerShellLiveId
    VERBOSE: Requesting authentication token
    VERBOSE: Success
    VERBOSE: Initializing remote session
    VERBOSE: Success
    Id Name       ComputerName    State        ConfigurationName     Availability -- ----       ------------    -----        -----------------     ------------
    2 Session2    litwarein...    Opened       Microsoft.PowerShell  Available

在成功地与 Skype for Business Online 建立连接之后，请通过运行以下类似命令导入该会话：

    Import-PSSession $session -AllowClobber

> [!NOTE]  
> AllowClobber 参数可确保导入所有 Skype for Business Online cmdlet，包括名称与常规 Lync Server cmdlet 相同的那些 cmdlet。这些 cmdlet 数量庞大，因为大多数 Skype for Business Online cmdlet（包括 <a href="get-csmeetingconfiguration.md">Get-CsMeetingConfiguration</a>、<a href="new-csexumcontact.md">New-CsExUmContact</a>、<a href="remove-csvoicepolicy.md">Remove-CsVoicePolicy</a> 等）都具有内部部署对等项。成对的 cmdlet（例如，Lync Server<strong>Get-CsMeetingConfiguration</strong> cmdlet 和 Skype for Business Online<strong>Get-CsMeetingConfiguration</strong> cmdlet）是相同的：您使用哪个 cmdlet 无关紧要。使用 AllowClobber 参数的唯一理由是阻止警告消息出现在您的屏幕上。


此时，您可以开始管理 Lync Server 和 Skype for Business Online 的内部部署版本。目前，您可能也有一个重要问题：如何区别 Lync Server 策略和设置与 Skype for Business Online 策略和设置？例如，您可能想要更改全局会议配置设置。为此，请运行此命令：

    Set-CsMeetingConfiguration -Identity "global" -AdmitAnonymousUsersByDefault $False

此命令将修改全局设置。但是哪些全局设置呢？Lync Server 内部部署？Skype for Business Online？两者？都不？

在这种特殊情况下，将修改内部部署设置。如何得知呢？因为命令中不包括 Tenant 参数。如果您同时连接到 Lync Server 内部部署和 Skype for Business Online，可以在其中任一平台上工作的 cmdlet 将对 Lync Server 运行，除非您有其他指示。进行其他指示的唯一方法是在运行命令时包括 Tenant 参数。例如，此命令将更新租户 ID 为 bf19b7db-6960-41e5-a139-2aa373474354 的 Skype for Business Online 租户的全局设置：

    Set-CsMeetingConfiguration -Identity "global" -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -AdmitAnonymousUsersByDefault $False

Tenant 参数非常重要。此命令返回 Lync Server 内部部署的全局外部访问策略：

    Get-CsExternalAccessPolicy -Identity "global"

而此命令返回您的 Skype for Business Online 租户的全局外部访问策略：

    Get-CsExternalAccessPolicy -Identity "global" -Tenant "bf19b7db-6960-41e5-a139-2aa373474354"

记住，共有大约 700 多个内部部署 cmdlet。但是，这些 cmdlet 绝大多数都没有 Tenant 参数，意味着它们不能与 Skype for Business Online 一起使用。也请注意，少量 cmdlet 有 Tenant 参数，但是不适用于与 Skype for Business Online 一起使用。要检索可与 Skype for Business Online 一起使用的确切的一组 cmdlet，请从 Windows PowerShell 提示符处运行此命令：

    Get-Module

屏幕上将显示以下类似信息：

    ModuleType Name                 ExportedCommands
    ---------- ----                 ----------------
    Manifest   Microsoft.PowerS...  {Add-Computer, Add-Content, A...}
    Script     tmp_5astd3uh.m5v     {Disable-CsMeetingRoom, Enabl...}

ModuleType 为 Script 的模块是包含 Skype for Business Online cmdlet 的模块。要返回这些 cmdlet 的列表，请使用 Script 模块的名称作为模块名称运行 **Get-Command** cmdlet：

    Get-Command -Module tmp_5astd3uh.m5v

然后，Windows PowerShell 应显示所有 Skype for Business Online cmdlet 的列表。

**解决混合部署中的连接问题**

在某些情况下，管理员使用内部部署帐户（例如 administrator@litwareinc.net）而不是 Office 365 帐户（例如 administrator@litwareinc.onmicrosoft.com）登录 Office 365 时可能会遇到问题。如果目录同步正常工作，则您应能够使用任一帐户登录；这是混合部署的优点之一。但是，在一些情况下，管理员已无法使用其内部部署帐户登录。这通常是由于自动发现将登录操作指向 Lync Server 的内部部署安装而不是 Office 365 导致的。

幸运的是，有一种轻松的方法可解决此问题。当使用 **New-CsOnlineSession** cmdlet 登录 Office 365 时，请仅包括 OverrideAdminDomain 参数，后跟 Office 365 域名。例如，要使用帐户 administrator@litwareinc.net 登录到 Office 365，请包括 OverrideAdminDomain 参数，后跟域名 litwareinc.onmicrosoft.com：

    $session = New-CsOnlineSession -Credential $credential -OverrideAdminDomain "litwareinc.onmicrosoft.com"

该命令会显式将登录尝试定向到 Office 365 服务器和 litwareinc.onmicrosoft.com 域。

