---
title: 下载并安装 Windows PowerShell 5.1
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: d739cd71-3c18-42ea-879f-b408bf53b1f4
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
- LIL_Placement
description: 下载、安装并使用 Windows PowerShell 5.1 创建连接到 Skype for Business Online 的远程 PowerShell 会话。
ms.openlocfilehash: 227023d5c86b99a66ecdbdabd3b2973d0383a534
ms.sourcegitcommit: ac922addbc1422b5c41273a2e03196efb2ed7770
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41831145"
---
# <a name="download-and-install-windows-powershell-51"></a>下载并安装 Windows PowerShell 5.1

如果使用的是 Windows 10 周年更新或 Windows Server 2016，则应已拥有 Windows PowerShell 5.1。 这是因为此应用程序随这些操作系统预安装。
  
要确定你使用的是什么版本的 Microsoft PowerShelll，请在 Windows 7 或 Windows Server 2008 R2 或 Windows Server 2012 计算机上执行以下步骤：
  
1. 依次单击“**开始**”、“**所有程序**”、“**附件**”和“**Windows PowerShell**”，然后单击“**Windows PowerShell**”。
    
2. 在 PowerShell 控制台中，键入以下命令，然后按 ENTER：
    
   ```PowerShell
   Get-Host | Select-Object Version
   ```

3. 控制台窗口中随后应显示以下类似信息：
    
    <pre>
    Version <BR>
    ------- <BR>
    4.0
    </pre>

    如果返回的版本号为 5.1，表明正在运行 Windows PowerShell 5.1。 如果返回的版本号不是 5.1，则需要安装 Windows PowerShell 5.1。 可从 [Microsoft 下载中心](https://www.microsoft.com/en-us/download/details.aspx?id=54616)下载 Windows Management Framework 5.1（其中包括 Windows PowerShell 5.1）。
  
验证已安装 Windows PowerShell 5.1 后，必须确保 PowerShell 已配置为可以运行远程脚本。 为此，以管理员身份启动 PowerShell。 在 Windows 7、Windows Server 2008 R2、Windows Server 2012 或 Windows Server 2012 R2 上执行以下操作：
  
1. 单击“**启动**”，依次单击“**所有程序**”、“**附件**”、“**Windows PowerShell**”，然后右键单击“**Windows PowerShell**”，单击“**以管理员身份运行**”。
    
2. 如果显示“**用户帐户控制**”对话框，单击“**是**”确定要通过管理员凭据运行 PowerShell。
    
如果运行的是 Windows 8，请完成此过程：
  
1. 访问超级按钮栏，单击“**搜索**”，然后右键单击“**Windows PowerShell**”。 可以通过按住 Windows 键并按 C 来在任何 Windows 8 计算机（触摸屏或非触摸屏）上快速访问超级按钮栏。
    
2. 在屏幕底部的工具栏中，单击“**以管理员身份运行**”。
    
3. 如果显示“**用户帐户控制**”对话框，单击“**是**”确定要通过管理员凭据运行 PowerShell。
    
在 PowerShell 运行后，必须更改执行策略以允许运行远程脚本。 在 PowerShell 控制台中，键入以下命令，然后按 ENTER：
```PowerShell
Set-ExecutionPolicy RemoteSigned -Force
```
   
 
> [!NOTE]
> 运行上述命令后，可能会收到以下错误消息：> *Set-ExecutionPolicy：对注册表项“HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft.PowerShell”的访问被拒绝。* 如果未在管理员凭据下运行 PowerShell，则通常会出现此错误消息。 关闭 PowerShell 会话，并以管理员身份启动新会话。
 
要验证是否已正确配置执行策略，请在 PowerShell 提示符处键入以下内容，然后按 Enter：
  
```PowerShell
Get-ExecutionPolicy
```

如果获得以下值，则所有内容已正确配置：
  
`RemoteSigned`

如果当前未运行 Windows PowerShell 5.1，则还需要从 Microsoft 下载中心下载并安装 Windows Management Framework 5.1。 这是一个安装程序包，包含 Windows PowerShell 5.1 和 Windows 远程管理 (WinRM) 3.0。 例如，如果运行的是 Windows 7 SP1，并且尚未更新到 Windows PowerShell 5.1，则可能需要此安装程序包。 如果运行的是 Windows Server 2016 或 Windows 10 周年更新，则无需安装 Windows PowerShell 5.1。 这些操作系统上预装了 Windows PowerShell 5.1。
  
在安装 Windows Management Framework 5.1 之前：
  
- 确保已下载安装程序包的正确版本。 如果运行的是 64 位版本的 Windows 7 SP1，请下载文件 Win7AndW2K8R2-KB3191566-x64.ZIP。 如果运行的是 32 位版本的 Windows 7，请下载文件 Win7-KB3191566-x86.ZIP。
    
- 如果计算机正在运行 Windows 7，请确保已安装 Windows 7 Service Pack 1。

如果不确定正在运行的 Windows 版本，或者不确定是否已安装 Windows 7 Service Pack 1，请单击“**开始**”，右键单击“**计算机**”，然后单击“**属性**”。 “系统”对话框中将报告此信息。
  
要安装 Windows Management Framework 5.1，请完成[安装和配置 WMF 5.1](https://docs.microsoft.com/powershell/scripting/wmf/setup/install-configure) 中的程序。
  
计算机重新启动后，验证 Windows PowerShell 是否可以启动以及应用程序是否可在管理凭据下运行。 要执行此操作：
  
1. 单击“**启动**”，依次单击“**所有程序**”、“**附件**”、“**Windows PowerShell**”，然后右键单击“**Windows PowerShell**”，单击“**以管理员身份运行**”。
    
2. 如果显示“用户帐户控制”对话框，单击“**是**”确定要通过管理员凭据运行 PowerShell。
    
当 PowerShell 控制台出现时，应该验证 WinRM 服务是否正在运行并且已正确配置。 要验证服务是否正在运行，请在 PowerShell 提示符处键入以下命令，然后按 Enter：
  
```PowerShell
Get-Service winrm
```

屏幕上将显示有关 WinRM 服务的信息：
  
<pre>
Status   Name               DisplayName
------   ----               -----------
Running  winrm              Windows Remote Management (WS-Manag...
</pre>

如果服务状态不是“正在运行”，请通过键入以下命令并按 Enter 来启动 WinRM 服务：
  
```PowerShell
Start-Service winrm
```

服务启动后，请运行以下命令以确保 WinRM 使用基本身份验证：
  
```PowerShell
winrm set winrm/config/client/auth '@{Basic="True"}'
```

屏幕上将显示以下类似信息：
  
<pre>
Auth
    Basic = true
    Digest = true
    Kerberos = true
    Negotiate = true
    Certificate = true
    CredSSP = false
</pre>

如果基本身份验证设置为 true，则可以开始使用 PowerShell 连接 Skype for Business Online。
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a>相关主题
[为 Windows PowerShell 设置计算机](set-up-your-computer-for-windows-powershell.md) 

  
 
