---
title: 下载并安装 Skype for Business Online 连接器模块
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9c1cc3dc-7d6d-43ca-8e4a-7763a3f78cb3
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
description: 下载、安装和使用 Skype for Business Online 连接器以创建连接到 Skype for business Online 的远程 Windows PowerShell 会话。
ms.openlocfilehash: 8e9441e152314fafdee8fe8292d0b62a1b17d6da
ms.sourcegitcommit: 5bcc25fb20ed72bac02bc78e40b591e67eb58686
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "46564771"
---
# <a name="download-and-install-the-skype-for-business-online-connector-module"></a>下载并安装 Skype for Business Online 连接器模块

> [!NOTE]
> 最新的[团队 powershell 公共预览版](https://www.powershellgallery.com/packages/MicrosoftTeams/)已与 Skype For Business Online 连接器集成，为团队 PowerShell 管理提供单个模块。

Skype for Business Online 连接器模块包括**CsOnlineSession** cmdlet，可用于创建连接到 Skype For business Online 的远程 Windows PowerShell 会话。 此模块仅在64位计算机上受支持 (请参阅[使用 Windows PowerShell 设置计算机以使用 Skype For Business Online 管理](set-up-your-computer-for-windows-powershell.md)有关详细信息) ，可从 Microsoft 下载中心下载 [https://www.microsoft.com/download/details.aspx?id=39366](https://www.microsoft.com/download/details.aspx?id=39366) 。 下载 SkypeOnlinePowershell.exe 文件，然后完成以下过程：
  
1. 双击 " **SkypeOnlinePowershell.exe** " 文件。
    
2. 在 Skype for Business Online 的 Windows PowerShell 设置向导中的 " **Microsoft 软件许可条款**" 页面上，选择 "**我接受许可协议中的条款**"，然后单击 "**安装**"。 如果出现 "**用户帐户控制**" 对话框，请单击 **"是"** 以继续安装。
    
3. 在 "**已完成 Skype For Business Online，Windows PowerShell 模块**" 页面上，单击 "**完成**"。
    
安装程序将 Skype for Business Online 连接器模块 (和**CsOnlineSession** cmdlet) 复制到你的计算机。 若要访问该模块，请在 "管理员凭据" 下启动 Windows PowerShell 会话，然后运行以下命令：
  
```PowerShell
Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
```

如果你不希望每次启动 Windows PowerShell 时都键入此命令，你可以将该命令添加到你的 Windows PowerShell 配置文件。 若要执行此操作，请在 Windows PowerShell 提示符处键入以下命令，然后按 ENTER：
  
```PowerShell
notepad.exe $profile
```

 出现记事本时，将以下行添加到配置文件中已存在的命令底部 (如果有任何) ：
  
```PowerShell
Import-Module SkypeOnlineConnector
```

保存文件。 下次启动 Windows PowerShell 时，将自动导入 Skype for business Online 连接器模块。 请注意，你将收到一条错误消息，如果你未在 "管理员凭据" 下运行 Windows PowerShell，将不会加载该模块。
  
除了安装 Skype for Business Online 连接器模块之外，SkypeOnlinePowershell.exe 还会安装三个附加组件： 1) 用于处理针对 Skype for business Online 的客户端身份验证的身份服务客户端运行时库 (IDCRL) ，2) .NET Framework 4.5;和 3) Microsoft Visual c + + 2012 可再发行 (x64) 程序包 (版本 11.0.50727) 。 .NET Framework 4.5 提供用于构建和运行 .NET 应用程序（包括 Windows PowerShell）的基础结构。 Visual c + + 可再发行程序包为未安装 Microsoft Visual Studio 2012 的计算机安装 Visual c + + 运行时组件。
  
若要验证您的计算机上当前安装的连接器模块的版本号，请打开 "控制面板"，打开 "**程序和功能**"，然后查看**Skype for Business Online、Windows PowerShell 模块**的版本号。
  
## <a name="related-topics"></a>相关主题
[使用 Windows PowerShell 为 skype for business online 管理设置计算机](set-up-your-computer-for-windows-powershell.md)

  
 
