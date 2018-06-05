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
description: 下载和安装，然后使用 Windows PowerShell 3.0 创建连接到 Skype 业务 online 的远程 PowerShell 会话。
ms.openlocfilehash: 9c2b0f02d9da7e44cdb5585314c13a6bafbe58c6
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2018
ms.locfileid: "19568319"
---
# <a name="download-and-install-windows-powershell-30"></a>下载并安装 Windows PowerShell 3.0

如果您使用的 Windows 8.1、 Windows 8、 Windows Server 2012 R2 或 Windows Server 2012，则您应该已经 Windows PowerShell 3.0。 这是因为此应用程序方面与这些操作系统预安装。 
  
如果您运行的 Windows 7 或 Windows Server 2008 R2，您可能还运行 Windows PowerShell 3.0。 但是，也可能是，您可能会运行 2.0 版改为 — 最初附带这些操作系统的版本。 若要确定使用哪个版本的 Microsoft PowerShelll，执行下列操作在 Windows 7 或 Windows Server 2008 R2 的计算机上：
  
1. 单击**开始**，单击**所有程序**、 都**附件**、 都**Windows PowerShell**，，然后都单击**Windows PowerShell**。
    
2. 在 PowerShell 控制台中，键入以下命令，然后按 ENTER:
    
   ```
   Get-Host | Select-Object Version
   ```

3. 然后应控制台窗口中显示类似于以下的信息：
    
    <pre>
    Version <BR>
    ------- <BR>
    3.0
    </pre>

    如果返回的版本号是 3.0，您正在运行 Windows PowerShell 3.0。 如果返回的版本号不是 3.0，您需要安装 Windows PowerShell 3.0。 您可以从[Microsoft 下载中心](https://www.microsoft.com/en-us/download/details.aspx?id=34595)下载 Windows Management Framework 3.0，其中包括 Windows PowerShell 3.0。
  
验证了安装了 Windows PowerShell 3.0 后，您必须确保 PowerShell 确认已配置的运行远程脚本。 为此，请以管理员身份启动 PowerShell。 在 Windows 7、 Windows Server 2008 R2、 Windows Server 2012 或 Windows Server 2012 R2 上执行以下操作：
  
1. 单击**开始**，单击**所有程序**，都单击**附件**，都单击**Windows PowerShell**、 **Windows PowerShell**中，右键单击，然后都单击**以管理员身份运行**。
    
2. 如果出现**用户帐户控制**对话框，请单击**是**以确认您想要管理员凭据运行 PowerShell。
    
如果您运行的 Windows 8，而是完成此过程：
  
1. 访问超级按钮栏，单击**搜索**，然后右键单击**Windows PowerShell**。 您可以快速访问的超级按钮栏 （触摸屏或非触摸屏） 的任何 Windows 8 计算机上，通过按下 Windows 键和 c。
    
2. 在屏幕底部工具栏中，单击**以管理员身份运行**。
    
3. 如果出现**用户帐户控制**对话框，请单击**是**以确认您想要管理员凭据运行 PowerShell。
    
运行 PowerShell 后，您必须更改执行策略，以允许脚本远程运行。 在 PowerShell 控制台中，键入以下命令，然后按 ENTER:
```
Set-ExecutionPolicy RemoteSigned -Force
```
   
 
> [!NOTE]
> 运行上述命令时，您可能会收到以下错误消息： > *Set-executionpolicy： 向注册表项的访问 HKEY_LOCAL_MACHINE\\软件\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft.PowerShell 被拒绝。* 如果您不管理员凭据运行 PowerShell，通常会出现此错误消息。 关闭会话的 PowerShell 中，并以管理员身份启动新的会话。
 
若要验证已正确配置执行策略，在 PowerShell 提示符处键入以下命令，然后按 ENTER:
  
```
Get-ExecutionPolicy
```

如果您获得以下值，然后所有已正确配置：
  
`RemoteSigned`

如果您当前未运行 Windows PowerShell 3.0，您还需要下载并安装 Windows Management Framework 3.0 从 Microsoft 下载中心。 这是一个安装包，包括 Windows PowerShell 3.0 和 Windows 远程管理 (WinRM) 3.0。 如果运行 Windows 7 和尚未更新到 Windows PowerShell 3.0，可能需要此安装软件包。 如果您运行的 Windows Server 2012、 Windows Server 2012 R2、 Windows 8 或 Windows 8.1，应该有无需安装 Windows PowerShell 3.0。 Windows PowerShell 3.0 这些操作系统的亮起预安装。
  
安装 Windows Management Framework 3.0： 之前
  
- 请确保您已下载安装程序包的正确版本。 如果您运行的 64 位版本的 Windows 7，下载 Windows6.1-KB2506143-x64.msu 的文件。 如果您运行的 32 位版本的 Windows 7，下载 Windows6.1-KB2506143-x86.msu 的文件。
    
- 如果在您的计算机上运行 Windows 7，请确保您已安装 Windows 7 Service Pack 1。
    
如果您不确定哪个版本的 Windows 运行的，或者您不确定如果已安装 Windows 7 Service Pack 1，单击**开始**，右键单击**计算机**，然后单击**属性**。 在系统对话框中，将报告此信息。
  
若要安装 Windows Management Framework 3.0，请完成以下过程：
  
1. 双击。MSU 安装文件 （ **Windows6.1-KB2506143-x64.msu**或**Windows6.1-KB2506143-x86.msu**）。
    
2. 下载并安装更新向导，在**阅读 (第 1 个 1) 这些许可条款**页上，单击**我接受**。
    
3. 安装完成后，单击**立即重新启动**以重新启动计算机。
    
已重新启动计算机后，验证，可以启动 Windows PowerShell，可以在管理凭据下运行的应用程序。 若要此操作：
  
1. 单击**开始**，单击**所有程序**，都单击**附件**，都单击**Windows PowerShell**，右键单击**Windows PowerShell** ，然后都单击**以管理员身份运行**。
    
2. 如果用户帐户控制显示对话框，请单击**是**以验证您想要管理员凭据运行 PowerShell。
    
PowerShell 控制台显示时，则应验证 WinRM 服务正在运行并已正确配置。 若要确认服务正在运行，在 PowerShell 提示符处键入以下命令，然后按 ENTER:
  
```
Get-Service winrm
```

然后，有关 WinRM 服务的信息将显示在屏幕上：
  
<pre>
Status   Name               DisplayName
------   ----               -----------
Running  winrm              Windows Remote Management (WS-Manag...
</pre>

如果该服务状态不等于"运行"，通过键入以下命令并按 ENTER 启动 WinRM 服务：
  
```
Start-Service winrm
```

服务已启动后，运行以下命令以确保 WinRM 使用基本身份验证：
  
```
winrm set winrm/config/client/auth '@{Basic="True"}'
```

类似于以下的信息将显示在屏幕上：
  
<pre>
Auth
    Basic = true
    Digest = true
    Kerberos = true
    Negotiate = true
    Certificate = true
    CredSSP = false
</pre>

如果基本身份验证已设置为 true，然后便可以使用 PowerShell 连接到 Skype 业务 online。
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a>相关主题
[为 Windows PowerShell 设置计算机](set-up-your-computer-for-windows-powershell.md) 

  
 