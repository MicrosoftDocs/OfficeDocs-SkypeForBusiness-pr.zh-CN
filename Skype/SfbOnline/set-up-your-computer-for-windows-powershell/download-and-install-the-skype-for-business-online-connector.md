---
title: 下载并安装 for Business Online Connector 模块 Skype
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9c1cc3dc-7d6d-43ca-8e4a-7763a3f78cb3
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: '下载、 安装，然后使用 Business Online Connector 的 Skype 创建连接到 Skype 业务 online 远程 Windows PowerShell 会话。 '
ms.openlocfilehash: deffed8da6b5b7a7c2ae522782f5316744de3394
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23858328"
---
# <a name="download-and-install-the-skype-for-business-online-connector-module"></a>下载并安装 for Business Online Connector 模块 Skype

为业务 Online Connector 模块 Skype 包括**新建 CsOnlineSession** cmdlet，使您能够创建连接到 Skype 业务 online 远程 Windows PowerShell 会话。 此模块只能在 （有关详细信息，请参阅[设置您的计算机的业务联机管理使用 Windows PowerShell 的 Skype](set-up-your-computer-for-windows-powershell.md) ） 的 64 位计算机的受支持，可以从 Microsoft 下载中心获取下载[https://www.microsoft.com/en-us/download/details.aspx?id=39366](https://www.microsoft.com/en-us/download/details.aspx?id=39366)。 下载 SkypeOnlinePowershell.exe 文件，然后完成以下过程：
  
1. 双击**SkypeOnlinePowershell.exe**文件。
    
2. 业务 online Skype，在 Windows PowerShell 安装向导，在**Microsoft 软件许可条款**页中，选择**我接受许可协议中的条款**，然后单击**安装**。 如果出现**用户帐户控制**对话框，请单击**是**以继续安装。
    
3. 在**已完成的业务 Online Windows PowerShell 模块 Skype**页上，单击**完成**。
    
安装程序将复制到您的计算机业务 Online Connector 模块 （和**新建 CsOnlineSession** cmdlet） Skype。 若要访问的模块和启动 Windows PowerShell 会话下管理员凭据，然后运行以下命令：
  
```
Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
```

如果您不希望每次启动 Windows PowerShell，请键入以下命令，您可以将命令添加到 Windows PowerShell 配置文件。 为此，在 Windows PowerShell 提示符处键入以下命令，然后按 ENTER:
  
```
notepad.exe $profile
```

 出现记事本时，添加以下行到底部的配置文件 （如果有） 中已有的命令：
  
```
Import-Module SkypeOnlineConnector
```

保存文件。 下次启动 Windows PowerShell for Business Online Connector 模块 Skype 将自动导入。 注意，您将收到一条错误消息，并将不会加载该模块，如果您不管理员凭据运行 Windows PowerShell。
  
除了安装 for Business Online Connector 模块 Skype，SkypeOnlinePowershell.exe 还安装了三个其他组件： 1) 标识服务客户端运行时库 (IDCRL)，用于处理对业务的 Skype 的客户端身份验证联机;2).NET framework 4.5;以及 3） 的 Microsoft Visual c + + 2012年可再发行软件包 (x64) 程序包 （版本 11.0.50727）。 .NET framework 4.5 提供用于构建和运行.NET 应用程序，包括 Windows PowerShell 的基础结构。 Visual c + + 可再发行软件包安装 Visual c + + 运行时组件没有安装 Microsoft Visual Studio 2012 的计算机。
  
若要验证您的计算机当前安装的连接器模块的版本号，打开控制面板和打开**程序和功能**，然后检查**Windows PowerShell 模块业务 online，Skype**的版本号。
  
## <a name="related-topics"></a>相关主题
[设置您的计算机的业务联机管理使用 Windows PowerShell 的 Skype](set-up-your-computer-for-windows-powershell.md)

  
 