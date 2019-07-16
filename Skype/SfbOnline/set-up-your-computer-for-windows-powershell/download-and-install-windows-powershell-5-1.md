---
title: 下载并安装 Windows PowerShell 5。1
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
f1keywords: None
ms.custom:
- PowerShell
- LIL_Placement
description: 下载、安装, 然后使用 Windows PowerShell 5.1 创建连接到 Skype for Business Online 的远程 PowerShell 会话。
ms.openlocfilehash: 5afca0ef1fd5d7437c3974de1424a664c99ab1a1
ms.sourcegitcommit: 9c54fd0a51ece8624155dc543d5df922834aa51e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/16/2019
ms.locfileid: "35701549"
---
# <a name="download-and-install-windows-powershell-51"></a>下载并安装 Windows PowerShell 5。1

如果你使用的是 Windows 10 周年更新或 Windows Server 2016, 你应该已经拥有 Windows PowerShell 5.1。 这是因为此应用程序预装了这些操作系统。
  
若要确定你使用的是哪个版本的 Microsoft PowerShelll, 请在 Windows 7 或 Windows Server 2008 R2 或 Windows Server 2012 计算机上执行以下操作:
  
1. 依次单击 "**开始**"、"**所有程序**"、"**附件**"、" **Windows PowerShell**", 然后单击 " **windows powershell**"。
    
2. 在 PowerShell 控制台中, 键入以下命令, 然后按 ENTER:
    
   ```
   Get-Host | Select-Object Version
   ```

3. 随后应在控制台窗口中显示类似于以下内容的信息:
    
    <pre>
    Version <BR>
    ------- <BR>
    4.0
    </pre>

    如果返回的版本号为 5.1, 则您运行的是 Windows PowerShell 5.1。 如果返回的版本号不是 5.1, 则需要安装 Windows PowerShell 5.1。 你可以从[Microsoft 下载中心](https://www.microsoft.com/en-us/download/details.aspx?id=54616)下载 Windows Management Framework 5.1, 其中包括 windows PowerShell 5.1。
  
验证是否安装了 Windows PowerShell 5.1 后, 必须确保已将 PowerShell 配置为运行远程脚本。 若要执行此操作, 请以管理员身份启动 PowerShell。 在 Windows 7、Windows Server 2008 R2、Windows Server 2012 或 Windows Server 2012 R2 上执行以下操作:
  
1. 单击 "**开始**", 单击 "**所有程序**", 单击 "**附件**", 单击 " **Windows PowerShell**", 右键单击 " **windows Powershell**", 然后单击 "以**管理员身份运行**"。
    
2. 如果出现 "**用户帐户控制**" 对话框, 请单击 **"是"** 以验证你希望在 "管理员凭据" 下运行 PowerShell。
    
如果你运行的是 Windows 8, 请改为完成此过程:
  
1. 访问超级按钮栏, 单击 "**搜索**", 然后右键单击 " **Windows PowerShell**"。 你可以通过按住 Windows 键并按 C, 在任何 Windows 8 计算机上 (触摸屏幕或非触摸屏幕) 快速访问超级按钮栏。
    
2. 在屏幕底部的工具栏中, 单击 "**以管理员身份运行**"。
    
3. 如果出现 "**用户帐户控制**" 对话框, 请单击 **"是"** 以验证你希望在 "管理员凭据" 下运行 PowerShell。
    
在运行 PowerShell 后, 必须更改执行策略以允许运行远程脚本。 在 PowerShell 控制台中, 键入以下命令, 然后按 ENTER:
```
Set-ExecutionPolicy RemoteSigned -Force
```
   
 
> [!NOTE]
> 运行上述命令时, 你可能会收到以下错误消息: > *Set-set-executionpolicy:\\访问注册表 key'HKEY_LOCAL_MACHINE 软件\\Microsoft\\PowerShell\\1 ShellIds\\\\"Micrsoft" 被拒绝。* 如果你未在 "管理员凭据" 下运行 PowerShell, 通常会出现此错误消息。 关闭 PowerShell 会话, 并以管理员身份启动新会话。
 
若要验证是否已正确配置执行策略, 请在 PowerShell 提示符处键入以下内容, 然后按 ENTER:
  
```
Get-ExecutionPolicy
```

如果返回以下值, 则所有内容均已正确配置:
  
`RemoteSigned`

如果当前未运行 Windows PowerShell 5.1, 你还需要从 Microsoft 下载中心下载并安装 Windows Management Framework 5.1。 这是一个包含 Windows PowerShell 5.1 和 Windows 远程管理 (WinRM) 3.0 的安装包。 例如, 如果运行的是 Windows 7 SP1, 但尚未更新到 Windows PowerShell 5.1, 则可能需要此安装程序包。 如果你运行的是 Windows Server 2016 或 Windows 10 周年更新, 则不需要安装 Windows PowerShell 5.1。 在这些操作系统上预装了 Windows PowerShell 5.1。
  
安装 Windows Management Framework 5.1 之前:
  
- 请确保下载了正确版本的安装程序包。 如果你运行的是64位版本的 Windows 7 SP1, 请下载 Win7AndW2K8R2-KB3191566-x64 文件。 如果你运行的是32位版本的 Windows 7, 请下载 Win7-KB3191566-x86 文件。
    
- 如果您在计算机上运行的是 Windows 7, 请确保已安装 Windows 7 Service Pack 1。

如果不确定运行的是哪个版本的 Windows, 或者不确定是否已安装 Windows 7 Service Pack 1, 请单击 "**开始**", 右键单击 "**计算机**", 然后单击 "**属性**"。 此信息将在 "系统" 对话框中报告。
  
若要安装 Windows Management Framework 5.1, 请完成[安装和配置 WMF 5.1](https://docs.microsoft.com/powershell/wmf/setup/install-configure)中的过程。
  
重新启动计算机后, 请验证 Windows PowerShell 是否可以启动, 并且该应用程序可以在 "管理凭据" 下运行。 为此, 请执行以下操作:
  
1. 依次单击 "**开始**"、"**所有程序**"、"**附件**"、" **Windows PowerShell**", 右键单击 " **windows Powershell** ", 然后单击 "以**管理员身份运行**"。
    
2. 如果出现 "用户帐户控制" 对话框, 请单击 **"是"** 以验证你希望在 "管理员凭据" 下运行 PowerShell。
    
当 PowerShell 控制台出现时, 应验证 WinRM 服务是否正在运行且已正确配置。 若要验证该服务是否正在运行, 请在 PowerShell 提示符处键入以下命令, 然后按 ENTER:
  
```
Get-Service winrm
```

然后, 有关 WinRM 服务的信息将显示在屏幕上:
  
<pre>
Status   Name               DisplayName
------   ----               -----------
Running  winrm              Windows Remote Management (WS-Manag...
</pre>

如果服务状态不等于 "正在运行", 请通过键入以下命令来启动 WinRM 服务, 然后按 ENTER:
  
```
Start-Service winrm
```

服务启动后, 请运行以下命令以确保 WinRM 使用基本身份验证:
  
```
winrm set winrm/config/client/auth '@{Basic="True"}'
```

屏幕上将显示类似于以下内容的信息:
  
<pre>
Auth
    Basic = true
    Digest = true
    Kerberos = true
    Negotiate = true
    Certificate = true
    CredSSP = false
</pre>

如果基本身份验证已设置为 true, 则可以使用 PowerShell 连接到 Skype for Business Online。
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a>相关主题
[为 Windows PowerShell 设置计算机](set-up-your-computer-for-windows-powershell.md) 

  
 
