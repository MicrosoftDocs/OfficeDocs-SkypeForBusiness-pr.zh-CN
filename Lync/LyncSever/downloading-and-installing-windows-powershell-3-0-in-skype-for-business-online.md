---
title: Lync Online：下载和安装 Windows PowerShell 3.0
TOCTitle: 下载和安装 Windows PowerShell 3.0
ms:assetid: 39ae065d-02d7-4ce3-9e6f-6ad550a1777e
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn362783(v=OCS.15)
ms:contentKeyID: 56271132
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Online 中下载和安装 Windows PowerShell 3.0

 

_**上一次修改主题：** 2016-12-08_

如果您使用的是 Windows Server 2012、 Windows Server 2012 R2、Windows 8 或 Windows 8.1，那么您应已有 Windows PowerShell 3.0。这是因为此应用程序随这些操作系统预安装。

如果您正在运行 Windows 7 或 Windows Server 2008 R2，那么您也可能正在运行 Windows PowerShell 3.0。但是，也有可能您运行的是 2.0 版，这是最初随这些操作系统附带的版本。要确定您正在使用的 Windows PowerShell 版本，请在 Windows 7 或 Windows Server 2008 R2 计算机上执行下列操作：UNRESOLVED\_TOKEN\_VAL()UNRESOLVED\_TOKEN\_VAL()

1.  依次单击“开始”、“所有程序”、“附件”、“Windows PowerShell”和“Windows PowerShell”。

2.  在 Windows PowerShell 控制台中，键入以下命令，然后按 Enter：
    
        Get-Host | Select-Object Version

3.  控制台窗口中随后应显示以下类似信息：
    
        Version
        -------
        3.0

如果返回的版本号为 3.0，表明您正在运行 Windows PowerShell 3.0。如果返回的版本号不是 3.0，则您需要安装 Windows PowerShell 3.0。您可以从 [Microsoft 下载中心](http://www.microsoft.com/en-us/download/details.aspx?id=34595)下载 Windows Management Framework 3.o，其中包含 Windows PowerShell 3.0。

在验证是否已安装 Windows PowerShell 3.0 之后，您必须确保 Windows PowerShell 已配置以运行远程脚本。要执行该操作，请以管理员身份启动 Windows PowerShell。在 Windows 7、Windows Server 2008 R2、Windows Server 2012 或 Windows Server 2012 R2 上，执行下列操作：

1.  依次单击“开始”、“所有程序”、“附件”和“Windows PowerShell”，右键单“Windows PowerShell”，然后单击“以管理员身份运行”。

2.  如果显示“用户帐户控制”对话框，请单击“是”以验证您是否希望在管理员凭据下运行 Windows PowerShell。

如果运行的是 Windows 8，请完成此过程：

1.  访问超级按钮栏，单击“搜索”，然后右键单击“Windows PowerShell”。您可以通过按住 Windows 键并按 C 来在任何 Windows 8 计算机（触摸屏或非触摸屏）上快速访问超级按钮栏。

2.  在屏幕底部的工具栏中，单击“以管理员身份运行”。

3.  如果显示“用户帐户控制”对话框，请单击“是”以验证您是否希望在管理员凭据下运行 Windows PowerShell。

在 Windows PowerShell 运行后，您必须更改执行策略以允许运行远程脚本。在 Windows PowerShell 控制台中，键入以下命令，然后按 Enter：

    Set-ExecutionPolicy RemoteSigned -Force

> [!NOTE]  
> 在运行上述命令后，您可能会收到以下错误消息：<br />
Set-ExecutionPolicy：对注册表项&quot;HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\PowerShell\1\ShellIds\Micrsoft.PowerShell&quot;的访问被拒绝。<br />
如果您未在管理员凭据下运行 Windows PowerShell，则通常会出现此错误消息。关闭您的 Windows PowerShell 会话，并以管理员身份启动新会话。



要验证是否已正确配置执行策略，请在 Windows PowerShell 提示符处键入以下内容，然后按 Enter：

    Get-ExecutionPolicy

如果获得以下值，则所有内容已正确配置：

    RemoteSigned

如果您当前未运行 Windows PowerShell 3.0，您也需要从 Microsoft 下载中心下载并安装 Windows Management Framework 3.0。这是包括 Windows PowerShell 3.0 和 Windows Remote Management (WinRM) 3.0 的安装包。如果您运行 Windows 7，并且尚未更新到 Windows PowerShell 3.0，则可能需要此安装包。如果您运行的是 Windows Server 2012、 Windows Server 2012 R2、Windows 8 或 Windows 8.1，则应不需要安装 Windows PowerShell 3.0。 Windows PowerShell 3.0 预安装在这些操作系统上。

在安装 Windows Management Framework 3.0 之前：

  - 确保已下载安装程序包的正确版本。如果您运行的是 64 位版本的 Windows 7，请下载文件 Windows6.1-KB2506143-x64.msu。如果您运行的是 32 位版本的 Windows 7，请下载文件 Windows6.1-KB2506143-x86.msu。

  - 如果您的计算机正在运行 Windows 7，请确保已安装 Windows 7 Service Pack 1。

如果不确定您正在运行的 Windows 版本，或者不确定是否已安装 Windows 7 Service Pack 1，请单击“开始”，右键单击“计算机”，然后单击“属性”。“系统”对话框中将报告此信息：

![显示设置的系统对话框](images/Dn362783.30bff2e8-2862-4dd7-828f-43732f4b9314(OCS.15).png "显示设置的系统对话框")

要安装 Windows Management Framework 3.0，请完成以下过程：

1.  双击 .MSU 安装文件（ **Windows6.1-KB2506143-x64.msu** 或 **Windows6.1-KB2506143-x86.msu**）。

2.  在下载和安装更新向导中的“请阅读许可条款 (1/1)”页面上，单击“我接受”。

3.  安装完成时，单击“立即重启”以重新启动您的计算机。

计算机重新启动后，验证 Windows PowerShell 是否可以启动以及应用程序是否可在管理凭据下运行。若要执行此操作：

1.  依次单击“开始”、“所有程序”、“附件”和“Windows PowerShell”，右键单击“Windows PowerShell”，然后单击“以管理员身份运行”。

2.  如果显示“用户帐户控制”对话框，请单击“是”以验证您是否希望在管理员凭据下运行 Windows PowerShell。

当 Windows PowerShell 控制台出现时，您应该验证 WinRM 服务是否正在运行并且已正确配置。要验证服务是否正在运行，请在 Windows PowerShell 提示符处键入以下命令，然后按 Enter：

    Get-Service winrm

屏幕上将显示有关 WinRM 服务的信息：

    Status   Name               DisplayName
    ------   ----               -----------
    Running  winrm              Windows Remote Management (WS-Manag...

如果服务状态不是"正在运行"，请通过键入以下命令并按 Enter 来启动 WinRM 服务：

    Start-Service winrm

服务启动后，请运行以下命令以确保 WinRM 使用基本身份验证：

    winrm set winrm/config/client/auth '@{Basic="True"}'

屏幕上将显示以下类似信息：

    Auth
        Basic = true
        Digest = true
        Kerberos = true
        Negotiate = true
        Certificate = true
        CredSSP = false

如果基本身份验证设置为 true，那么您可以开始使用 Windows PowerShell 连接到 Skype for Business Online。

