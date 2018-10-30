---
title: 使用 Windows PowerShell 连接到 Lync Online
TOCTitle: 使用 Windows PowerShell 连接到 Lync Online
ms:assetid: 6167dad9-9628-4fdb-bed1-bdb3f7108e64
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn362795(v=OCS.15)
ms:contentKeyID: 56271146
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 使用 Windows PowerShell 连接到 Lync Online

 

_**上一次修改主题：** 2017-03-03_

安装必备软件之后，您可以开始使用 Windows PowerShell 管理 Skype for Business Online。要执行该操作，请首先打开 Windows PowerShell 的标准实例。您无需打开 Windows PowerShell 的特殊实例（类似于 Lync Server 命令行管理程序），也不需要打开控制面板应用或任何其他特殊类型的应用程序。这是因为 Skype for Business Online 管理使用 Windows PowerShell 的远程会话执行。这意味着：

1.  您使用 Windows PowerShell 的普通会话连接到 Skype for Business Online。当远程连接时，您在本地计算机上工作并使用 Windows PowerShell 的本地副本，但是您管理在远程系统上找到的对象（即，Skype for Business Online）。

2.  管理 Skype for Business Online 所需的所有 cmdlet、脚本和其他项目将下载到您的计算机上。这些项目保留在内存中，仅在与 Skype for Business Online 建立的远程会话中可用。请务必记住这一点。当与 Skype for Business Online 建立远程连接时，Skype for Business Online cmdlet（例如，[Get-CsTenant](get-cstenant.md)）将从内存中复制到您的计算机。在您的远程会话中，您能够运行这些 cmdlet。但是，这些 cmdlet 仅在该远程会话中可用。例如，您可以启动另一个 Windows PowerShell 会话，但是在此会话中无需连接到 Skype for Business Online。如果您试图从该会话中运行 **Get-CsTenant** cmdlet，您将收到以下错误消息：
    
        Get-CsTenant : The term 'Get-CsTenant' is not recognized as the name of a cmdlet, function, script file, or operable program. Check the spelling of the name, or if a path was included, verify that the path is correct and try again.
    
    也请注意，在您的硬盘中搜索 **Get-CsTenant** cmdlet（或任何其他 Skype for Business Online cmdlet）将不显示任何内容。这是因为当您创建远程会话时，没有任何内容会实际保存到您的硬盘。

3.  当您关闭您的远程会话时，下载的项目将从您的计算机的内存中删除。例如，您可以使用 **Get-CsTenant** cmdlet 启动 Windows PowerShell 的远程会话，然后关闭该会话。如果重新启动 Windows PowerShell，则 **Get-CsTenant** cmdlet 将不再可用。要获取对 **Get-CsTenant** cmdlet 的访问权限，您需要重新连接到 Skype for Business Online。

> [!NOTE]  
> 如果您使用混合部署，则应按照<a href="using-windows-powershell-in-a-hybrid-deployment-with-skype-for-business-online.md">在混合部署中使用 Windows PowerShell</a>中所述的过程执行操作。



要创建与 Skype for Business Online 的远程连接，请首先在您的本地计算机上启动新的 Windows PowerShell 会话。如果您运行 Windows 7、Windows Server 2008 R2、Windows Server 2012 或 Windows Server 2012 R2 上，请执行下列操作：

  - 依次单击“开始”、“所有程序”、“附件”、“Windows PowerShell”和“Windows PowerShell”。

如果运行的是 Windows 8 或 8.1，请执行此操作：

  - 访问超级按钮栏，单击“搜索”，然后右键单击“Windows PowerShell”。您可以通过按住 Windows 键并按 C 来在任何 Windows 8 或 8.1 计算机（触摸屏或非触摸屏）上快速访问超级按钮栏。

Windows PowerShell 控制台显示后，您必须创建 Windows PowerShell 凭据对象。凭据对象用于将您的用户名和密码安全地传达给 Skype for Business Online。要创建凭据对象，请在 Windows PowerShell 提示符下键入以下命令，然后按 Enter：

    $credential = Get-Credential

> [!NOTE]  
> 在此示例中，您的用户名和密码将存储在变量 $credential 中。您可以将此变量命名为任何所需内容，前提是它遵守 Windows PowerShell 的变量规则。但是，您必须使用某种变量才能存储用户名和密码。否则，您创建的凭据对象在创建之后的片刻就会消失。



按 Enter 之后，您应会看到“Windows PowerShell 凭据”对话框：

![Windows PowerShell 登录凭据](images/Dn362835.0f04e0a1-c9d6-4341-a0bb-ef721c4815fd(OCS.15).png "Windows PowerShell 登录凭据")

在“用户名”框中，键入您的 Skype for Business Online 用户名。在“密码”框中，键入您的 Skype for Business Online 密码（密码将被屏蔽，在屏幕上不可见）。例如，如果您的用户名是 kenmyer@litwareinc.com，您的密码是 p@ssw0rd\!，则对话框将与此类似：

![Windows PowerShell 登录凭据](images/Dn362835.85977a0e-b14a-4aec-a45e-8548e9c9f691(OCS.15).png "Windows PowerShell 登录凭据")

要创建凭据对象，请单击“确定”。如果要验证是否已创建对象，只需在 Windows PowerShell 提示符处键入变量名称，然后按 Enter：

    $credential

Windows PowerShell 将通过向您显示以下类似内容来作出响应：

    UserName                            Password
    --------                            --------
    kenmyer@litwareinc.com              System.Security.SecureString

> [!NOTE]  
> 记住，<strong>Get-Credential</strong> cmdlet 接受您键入的任何凭据，不尝试验证您是否输入了有效的用户名和密码。只有当您试图登录 Skype for Business Online 时，才执行此验证。



在创建凭据对象之后，您可以创建一个与 Skype for Business Online 建立连接的新远程 Windows PowerShell 会话。为此，请在 Windows PowerShell 提示符下键入以下命令，然后按 Enter：

    $session = New-CsOnlineSession -Credential $credential

> [!NOTE]  
> $session 是一个用于保留信息的变量，在这种情况下为有关与 Skype for Business Online 的连接的信息。再说一下，您可以为此变量指定任何名称，只要该名称符合 Windows PowerShell 变量名称准则（例如，名称不应包括空格或标点符号）。



确保如上所示准确地键入命令（变量名称可能例外）。请注意，您的 Skype for Business Online 域的名称无关紧要。不管您的域名如何，**New-CsOnlineSession** cmdlet 都会将您连接到 Office 365 并使用提供的凭据帮您登录。进行连接和身份验证之后，您将基于提供的凭据自动重定向到合适的 URI。

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

您现在可以开始使用 Windows PowerShell 管理 Skype for Business Online 了吗？不能。**New-CsOnlineSession** cmdlet 将连接到 Skype for Business Online 并为您创建一个新会话。但是，您必须将该新会话导入到 Windows PowerShell 控制台中。可通过运行以下命令执行此操作：

    Import-PSSession $session

按 Enter 时，您将看到 Windows PowerShell 控制台中显示与此类似的进度表：

    Creating implicit remoting module . . .
         Getting command information from remote session . . . 16 commands  
              received
         [oooooooooooooooo
         00:00:33 remaining

此时发生的情形是 Windows PowerShell 正在下载管理 Skype for Business Online 所需的 cmdlet 和其他项目。下载完成后，您将在 Windows PowerShell 控制台中看到与此类似的信息：

    ModuleType Name                 ExportedCommands
    ---------- ----                 ----------------
    Script     tmp_5astd3uh.m5v     {Disable-CsMeetingRoom, Enable-Cs ...}

此时，您可以开始使用 Windows PowerShell 管理 Skype for Business Online。要验证下载是否成功并查看可用的 Skype for Business Online cmdlet，您必须首先确定包含所有 Skype for Business Online cmdlet 的临时 Windows PowerShell 模块的名称。为此，请从 Windows PowerShell 提示符处运行此命令：

    Get-Module

屏幕上将显示以下类似信息：

    ModuleType Name                 ExportedCommands
    ---------- ----                 ----------------
    Manifest   Microsoft.PowerS...  {Add-Computer, Add-Content, A...}
    Script     tmp_5astd3uh.m5v     {Disable-CsMeetingRoom, Enabl...}

ModuleType 为 Script 的模块是包含 Skype for Business Online cmdlet 的模块。要返回这些 cmdlet 的列表，请使用 Script 模块的名称作为模块名称运行 **Get-Command** cmdlet：

    Get-Command -Module tmp_5astd3uh.m5v

然后，Windows PowerShell 应显示所有 Skype for Business Online cmdlet 的列表。

在完成您的管理任务后，在关闭 Windows PowerShell 控制台之前，您应始终运行以下命令：

    Remove-PSSession $session

**Remove-PSSession** cmdlet 将您与 Skype for Business Online 断开连接，并关闭远程会话。事实上，如果您试图重新导入会话（通过运行 **Import-PSSession** cmdlet），您将收到以下错误消息：

    Import-PSSession : State of runspace is not valid for this operation.

此消息仅意味着，为了重新连接到 Skype for Business Online，您需要创建新会话。

如果您在关闭 Windows PowerShell 控制台之前忘记删除会话（或者控制台意外关闭），则不会发生任何情况。处于非活动状态 15 分钟后，会话将自动断开连接。但是，默认情况下，每个 Skype for Business Online 管理员仅允许同时与 Skype for Business Online 建立三个连接。如果您关闭 Windows PowerShell 控制台而不删除会话，该关闭的会话仍将计为一个连接，即使此时未使用也是如此。（它将继续计为一个连接直至超时。）例如，您可能打开并关闭 Windows PowerShell 控制台三次，每次都没有删除 Skype for Business Online 会话。如果您打开 Windows PowerShell 并试图建立第四个连接，您的命令将挂起，不建立任何连接。

> [!NOTE]  
> 如果试图建立连接时 Windows PowerShell 挂起，请按 Ctrl-C 终止停滞的命令。



各个管理员只能同时与 Skype for Business Online 租户建立三个连接，而组织可以同时有九个连接。这意味着三个管理员有三个同时连接，或者九个管理员与 Skype for Business Online 建立一个连接等等。然而，再说一次，单个管理员拥有的活动会话不能超过三个。

## 另请参阅

#### 概念

[为您的计算机配置 Lync Online 管理](configuring-your-computer-for-skype-for-business-online-management.md)

