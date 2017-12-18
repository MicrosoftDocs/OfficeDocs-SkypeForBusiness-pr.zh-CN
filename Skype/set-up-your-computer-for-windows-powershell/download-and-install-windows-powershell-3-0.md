---
title: "下载并安装 Windows PowerShell 3.0"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 10/3/2017
ms.audience: Admin
ms.topic: get-started-article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: LIL_Placement
ms.assetid: d739cd71-3c18-42ea-879f-b408bf53b1f4

description: "Download, install, and then use Windows PowerShell 3.0 to create a remote PowerShell session that connects to Skype for Business Online."
---

# 下载并安装 Windows PowerShell 3.0

> [!IMPORTANT]
> 本文是由机器翻译的，请参阅[免责声明]。
  
如果您使用的Windows 8.1、 Windows 8、 Windows Server 2012 R2或Windows Server 2012，您应该已经Windows PowerShell 3.0。这是因为此应用程序出现与这些操作系统上预安装。
  
如果您运行的Windows 7或Windows Server 2008 R2，您可能还运行Windows PowerShell 3.0。但是，也可能是您可能会运行版本 2.0 改为  最初附带这些操作系统的版本。要确定您正在使用哪个版本的Microsoft PowerShelll，请执行下列操作在 Windows 7 或Windows Server 2008 R2计算机上：
  
1. 单击 **开始**、 **所有程序**、 **附件**，单击 **Windows PowerShell**，，然后单击 **Windows PowerShell**。
    
2. 在PowerShell控制台中，键入以下命令，然后再按 ENTER:
    
  ```
  Get-Host | Select-Object Version
  ```

3. 然后应控制台窗口中显示类似于以下信息：
    
  ```
  Version
-------
3.0
  ```

返回的版本号为 3.0，如果您正在运行Windows PowerShell 3.0。返回的版本号不是 3.0，如果您需要安装Windows PowerShell 3.0。您可以从[Microsoft 下载中心](https://www.microsoft.com/en-us/download/details.aspx?id=34595)下载 Windows Management Framework 3.0，其中包括Windows PowerShell 3.0、。
  
验证Windows PowerShell 3.0已安装，必须确保后PowerShell已配置为运行远程脚本。若要执行此操作，请以管理员身份启动PowerShell 。在 Windows 7、 Windows Server 2008 R2、 Windows Server 2012或Windows Server 2012 R2请执行下列操作：
  
1. 单击 **开始**，单击 **所有程序**、 都单击 **附件**，都单击 **Windows PowerShell**、 **Windows PowerShell**，右键单击，然后都单击 **以管理员身份运行**。
    
2. 如果出现 **用户帐户控制**对话框中，单击 **是**以验证您想要运行PowerShell管理员凭据。
    
如果您运行的Windows 8，请改为完成此过程：
  
1. 访问超级按钮栏，单击 **搜索**，然后右键单击 **Windows PowerShell**。您可以快速访问 （触摸屏或非触摸屏） 任何Windows 8计算机上的超级按钮栏，通过按住 Windows 键并按 c。
    
2. 在在屏幕底部的工具栏上，单击 **以管理员身份运行**。
    
3. 如果出现 **用户帐户控制**对话框中，单击 **是**以验证您想要运行PowerShell管理员凭据。
    
运行PowerShell后，您必须更改执行策略以允许远程脚本运行。在PowerShell控制台中，键入以下命令，然后再按 ENTER:
  
```
Set-ExecutionPolicy RemoteSigned -Force
```

> [!NOTE]
> 运行前面的命令时，您可能会收到以下错误消息： > Set-executionpolicy： 访问注册表 key'HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft.PowerShell 被拒绝。 > 如果您未在运行PowerShell管理员凭据，通常会发生此错误消息。关闭您的会话的PowerShell，并以管理员身份启动新会话。 
  
验证已正确配置执行策略，在PowerShell提示时键入以下命令，然后按 ENTER:
  
```
Get-ExecutionPolicy
```

如果您得到了以下值，然后一切已正确配置：
  
```
RemoteSigned
```

如果您当前未运行Windows PowerShell 3.0，您还需要下载并安装 Windows Management Framework 3.0，从 Microsoft 下载中心。这是一个安装包，包括Windows PowerShell 3.0和 Windows 远程管理 (WinRM) 3.0。如果您运行的 Windows 7，并且尚未更新到Windows PowerShell 3.0，则可能需要此安装程序包。如果您正在运行Windows Server 2012、 Windows Server 2012 R2、 Windows 8或Windows 8.1，应不需要安装Windows PowerShell 3.0。Windows PowerShell 3.0附带预安装在这些操作系统上。
  
安装 Windows Management Framework 3.0： 之前
  
- 请确保您已下载安装程序包的正确版本。如果运行的 64 位版本的 Windows 7，请下载 Windows6.1-KB2506143 x64.msu 的文件。如果运行的 32 位版本的 Windows 7，请下载 Windows6.1-KB2506143 x86.msu 的文件。
    
- 如果您您的计算机上运行 Windows 7，请确保您已安装 Windows 7 Service Pack 1。
    
如果您不确定哪个版本的 Windows 您正在运行，或者您不确定如果已安装 Windows 7 Service Pack 1，单击 **开始**，右键单击 **计算机**，然后单击 **属性**。在系统对话框中，将报告此信息。
  
若要安装 Windows Management Framework 3.0，请完成以下过程：
  
1. 双击。MSU 安装文件 （ **Windows6.1-KB2506143 x64.msu**或 **Windows6.1-KB2506143 x86.msu**）。
    
2. 在下载并安装更新向导中，在 **阅读这些许可条款 (1 / 1)**页上，单击 **我接受**。
    
3. 安装完成后，单击 **立即重新启动**重新启动计算机。
    
具有重新启动计算机之后，验证 Windows PowerShell 可以启动和应用程序，可以在管理凭据下运行。若要此操作：
  
1. 单击 **开始**，单击 **所有程序**，都单击 **附件**，都单击 **Windows PowerShell**、 右键单击 **Windows PowerShell** ，然后都单击 **以管理员身份运行**。
    
2. 如果出现用户帐户控制对话框中，单击 **是**以验证您想要运行PowerShell管理员凭据。
    
PowerShell控制台出现时，您应然后验证 WinRM 服务正在运行，并且已正确配置。若要验证该服务正在运行， PowerShell提示符处键入以下命令，然后按 ENTER:
  
```
Get-Service winrm
```

然后在屏幕上，将显示有关 WinRM 服务的信息：
  
```
Status   Name               DisplayName
------   ----               -----------
Running  winrm              Windows Remote Management (WS-Manag...
```

如果该服务的状态不等于"运行"，首先 WinRM 服务键入以下命令并按 ENTER:
  
```
Start-Service winrm
```

启动服务后，请运行以下命令以确保 WinRM 使用基本身份验证：
  
```
winrm set winrm/config/client/auth '@{Basic="True"}'
```

在屏幕上将显示类似于以下信息：
  
```
Auth
    Basic = true
    Digest = true
    Kerberos = true
    Negotiate = true
    Certificate = true
    CredSSP = false
```

如果基本身份验证具有已设置为 true，则您准备好使用PowerShell连接到Skype for Business Online。
  
||
|:-----|
|![领英学习快捷图标。](../images/7e5cb7c8-dc66-4c9a-a16d-a30f10a970bd.png) **刚开始使用 Office 365？**         探索由 LinkedIn Learning 提供的适用于 **Office 365 管理员和 IT 专业人士**的免费视频课程。 |
   
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **机器翻译免责声明**：本文是由无人工介入的计算机系统翻译的。Microsoft 提供机器翻译是为了帮助非英语国家/地区用户方便阅读有关 Microsoft 产品、服务和技术的内容。由于机器翻译的原因，本文可能包含词汇、语法或文法方面的错误。 
  

