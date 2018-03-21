---
title: "下载并安装 Skype 业务在线连接器模块"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 9c1cc3dc-7d6d-43ca-8e4a-7763a3f78cb3
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
description: "下载、 安装和使用 Skype 业务在线连接器创建远程 Windows PowerShell 会话连接到 Skype 的在线业务。 "
ms.openlocfilehash: 4b4f611cae3ca46629de42b122ef4e9238402c98
ms.sourcegitcommit: 371a699df0c13f44d2cb6511ba7eaafe047be92c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/27/2018
---
# <a name="download-and-install-the-skype-for-business-online-connector-module"></a>下载并安装 Skype 业务在线连接器模块

Skype 业务在线连接器模块包括**新建 CsOnlineSession** cmdlet，它使您能够创建远程 Windows PowerShell 会话连接到 Skype 的在线业务。 本模块中，这支持仅在 （有关详细信息，请参阅[设置计算机上的 Skype 使用 Windows PowerShell 的在线业务管理](set-up-your-computer-for-windows-powershell.md)） 的 64 位计算机上，可从[https:// 在 Microsoft 下载中心下载www.microsoft.com/en-us/download/details.aspx?id=39366](https://www.microsoft.com/en-us/download/details.aspx?id=39366)。 下载 SkypeOnlinePowershell.exe 文件，然后完成下面的过程：
  
1. 双击**SkypeOnlinePowershell.exe**文件。
    
2. 在 Skype 的在线业务，Windows PowerShell 安装向导中的，在**Microsoft 软件许可条款**页中，选择**我接受许可协议中的条款**，然后单击**安装**。 如果出现**用户帐户控制**对话框，请单击**是**以继续安装。
    
3. 在**已完成的业务联机，Windows PowerShell 模块 Skype**页上，单击**完成**。
    
安装程序复制到您的计算机业务在线连接器模块 （以及**新建 CsOnlineSession** cmdlet） Skype。 若要访问的模块，启动 Windows PowerShell 会话管理员凭据，然后运行以下命令：
  
```
Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
```

如果您不希望每次启动 Windows PowerShell 键入以下命令，可以对 Windows PowerShell 配置文件中添加命令。 要做到这一点，在 Windows PowerShell 提示符下键入以下命令，然后按 enter 键：
  
```
notepad.exe $profile
```

 记事本出现时，到底端的配置文件 （如果有的话） 中已有的命令中添加以下行：
  
```
Import-Module SkypeOnlineConnector
```

保存该文件。 下次启动 Windows PowerShell Skype 业务在线连接器模块将自动导入。 注意，您将收到错误消息，并且将不会加载该模块，如果不在管理员凭据下运行 Windows PowerShell。
  
除了安装 Skype 业务在线连接器模块，SkypeOnlinePowershell.exe 还安装了三个其他组件： 1) 标识服务客户端运行时库 (IDCRL)，用来处理业务的 Skype 的客户端身份验证联机;2).net 4.5。以及 3） Microsoft Visual C++ 2012年可再发行组件 (x64) 软件包 （11.0.50727 版）。 .NET framework 4.5 提供了用于构建和运行.NET 应用程序，包括 Windows PowerShell 的基础结构。 Visual C++ 可再发行组件包安装计算机没有安装 Microsoft Visual Studio 2012 Visual C++ 运行时的组件。
  
要验证当前安装在计算机的连接器模块的版本号，请打开控制面板，打开**程序和功能**，然后检查**Skype 业务在线，Windows PowerShell 模块**的版本号。
  
## <a name="related-topics"></a>相关主题
[设置计算机上的 Skype 业务在线管理使用 Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

## <a name="feedback"></a>反馈意见？
提供产品反馈意见或让我们知道我们所执行的信息，请参阅[Skype 业务反馈](https://www.skypefeedback.com)。