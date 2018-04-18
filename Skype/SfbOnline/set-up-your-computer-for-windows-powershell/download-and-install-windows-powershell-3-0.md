---
title: 下载并安装 Windows PowerShell 3.0
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: d739cd71-3c18-42ea-879f-b408bf53b1f4
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
- LIL_Placement
description: 下载、 安装和使用 Windows PowerShell 3.0 创建远程 PowerShell 会话连接到 Skype 的在线业务。
ms.openlocfilehash: e3f1ca14b5c9e134ee5186b6c441fc948d1ef65b
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="download-and-install-windows-powershell-30"></a>下载并安装 Windows PowerShell 3.0

如果您使用的 Windows 8.1、 Windows 8、 Windows Server 2012 R2 或 Windows Server 2012，您应该已经 Windows PowerShell 3.0。 这是因为此应用程序是使用这些操作系统预装。 
  
如果您运行的 Windows 7 或 Windows Server 2008 R2，您可能也在运行 Windows PowerShell 3.0。 但是，也可能是您可能会运行版本 2.0 相反 — — 这些操作系统附带的原装的版本。 要确定正在使用哪个版本的 Microsoft PowerShelll，请执行下列操作在 Windows 7 计算机或 Windows Server 2008 R2 计算机上：
  
1. 单击**开始**，单击**所有程序**，都单击**附件**，都单击**Windows PowerShell**，，然后都单击**Windows PowerShell**。
    
2. 在 PowerShell 控制台中，键入以下命令，然后按 enter 键：
    
    ```
   Get-Host | Select-Object Version
   ```

3. 然后会在控制台窗口中显示类似于以下的信息：
    
    ```
    Version
    -------
    3.0
    ```

    返回的版本号为 3.0，如果您正在运行 Windows PowerShell 3.0。 如果返回的版本号不是 3.0，您将需要安装 Windows PowerShell 3.0。 您可以从[Microsoft 下载中心](https://www.microsoft.com/en-us/download/details.aspx?id=34595)下载 Windows 管理框架 3.0，其中包括 Windows PowerShell 3.0。
  
已验证安装了 Windows PowerShell 3.0 后，必须确保 PowerShell 确认已为运行远程脚本配置。 要做到这一点，请以管理员身份启动 PowerShell。 在 Windows 7，Windows Server 2008 R2、 Windows Server 2012 或 Windows Server 2012 R2 上执行以下操作：
  
1. 单击**开始**，单击**所有程序**，都单击**附件**，都单击**Windows PowerShell**、 **Windows PowerShell**，用鼠标右键单击，然后都单击**以管理员身份运行**。
    
2. 如果出现**用户帐户控制**对话框，请单击**是**以确认您想要在管理员凭据下运行 PowerShell。
    
如果您运行的 Windows 8，而是完成此过程：
  
1. 访问的魅力栏，单击**搜索**框中，然后用鼠标右键单击**Windows PowerShell**。 您可以快速访问 （触摸屏或非触摸屏） 的任何 Windows 8 计算机上的魅力栏下 Windows 键，然后按 c。
    
2. 在屏幕底部工具栏中，单击**以管理员身份运行**。
    
3. 如果出现**用户帐户控制**对话框，请单击**是**以确认您想要在管理员凭据下运行 PowerShell。
    
PowerShell 运行后，您必须更改执行策略以允许远程脚本的运行。 在 PowerShell 控制台中，键入以下命令，然后按 enter 键：
```
Set-ExecutionPolicy RemoteSigned -Force
```
    > [!NOTE]
    >  When you run the preceding command, you might receive the following error message:> *Set-ExecutionPolicy : Access to the registry key'HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft.PowerShell' is denied.* This error message typically occurs if you are not running PowerShell under administrator credentials. Close your session of PowerShell, and start a new session as an administrator. 
  
要验证已正确配置执行策略，PowerShell 提示符处键入以下内容，然后按 enter 键：
  
```
Get-ExecutionPolicy
```

如果您得到以下值，然后一切都已正确配置：
  
```
RemoteSigned
```

如果您当前未运行的 Windows PowerShell 3.0，您还需要下载并安装从 Microsoft 下载中心获取 Windows 管理框架 3.0。 这是一个安装包，包括 Windows PowerShell 3.0 和 Windows 远程管理 (WinRM) 3.0。 如果运行 Windows 7，而且尚未更新到 Windows PowerShell 3.0，则可能需要此安装程序包。 如果您运行的 Windows Server 2012、 Windows Server 2012 R2、 Windows 8 或 Windows 8.1，应该不需要安装 Windows PowerShell 3.0。 这些操作系统时预安装 Windows PowerShell 3.0。
  
在安装 Windows 管理框架 3.0： 之前
  
- 请确保您已下载的安装软件包的正确版本。 如果您运行的 64 位版本的 Windows 7，下载的文件 Windows6.1-KB2506143-x64.msu。 如果您运行的 32 位版本的 Windows 7，下载的文件 Windows6.1-KB2506143-x86.msu。
    
- 如果您在您的计算机上运行 Windows 7，请确保您已安装了 Windows 7 Service Pack 1。
    
如果您不确定哪个版本的 Windows 正在运行，或者您不能确定如果已经安装了 Windows 7 Service Pack 1，单击**开始**，右键单击**计算机**，然后单击**属性**。 在系统对话框还会报告此信息。
  
要安装 Windows 管理框架 3.0，请完成以下过程：
  
1. 双击。MSU 安装文件 （ **Windows6.1-KB2506143-x64.msu**或**Windows6.1-KB2506143-x86.msu**）。
    
2. 在下载并安装更新向导中，在**阅读这些许可条款 (第 1 个 1)**页上，单击**我接受**。
    
3. 安装完成后，请单击**立即重新启动**以重新启动您的计算机。
    
重新启动计算机后，请验证 Windows PowerShell 可以启动和应用程序，可以在管理凭据下运行。 若要此操作：
  
1. 单击**开始**单击**所有程序**，都单击**附件**、 **Windows PowerShell**用鼠标右键单击**Windows PowerShell**和，然后都单击**以管理员身份运行**。
    
2. 如果出现对话框，用户帐户控制，请单击**是**以确认您要在管理员凭据下运行 PowerShell。
    
当 PowerShell 控制台出现时，然后应验证 WinRM 服务正在运行并已正确配置。 若要验证该服务正在运行，PowerShell 提示符处键入以下命令，然后按 enter 键：
  
```
Get-Service winrm
```

然后，WinRM 服务有关的信息将显示在屏幕上：
  
```
Status   Name               DisplayName
------   ----               -----------
Running  winrm              Windows Remote Management (WS-Manag...
```

如果服务状态不等于"正在运行"，通过键入以下命令，然后按 enter 键启动 WinRM 服务：
  
```
Start-Service winrm
```

在服务启动后，运行以下命令来确保 WinRM 使用基本身份验证：
  
```
winrm set winrm/config/client/auth '@{Basic="True"}'
```

类似于以下的信息将显示在屏幕上：
  
```
Auth
    Basic = true
    Digest = true
    Kerberos = true
    Negotiate = true
    Certificate = true
    CredSSP = false
```

如果基本的身份验证已设置为 true，然后您就可以使用 PowerShell 将连接到 Skype 的在线业务。
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a>相关主题
[为 Windows PowerShell 设置计算机](set-up-your-computer-for-windows-powershell.md) 

  
 