---
title: "下载并安装 Skype for Business Online 连接器模块"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 5/31/2017
ms.audience: Admin
ms.topic: get-started-article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.assetid: 9c1cc3dc-7d6d-43ca-8e4a-7763a3f78cb3
description: "Download, install, and then use the Skype for Business Online Connector to create a remote Windows PowerShell session that connects to Skype for Business Online.
"
---

# 下载并安装 Skype for Business Online 连接器模块

> [!IMPORTANT]
> 本文是由机器翻译的，请参阅[免责声明](9c1cc3dc-7d6d-43ca-8e4a-7763a3f78cb3.md#MT_Footer)。请在 [此处](https://support.office.com/en-us/article/9c1cc3dc-7d6d-43ca-8e4a-7763a3f78cb3) 中查找本文的英文版本以便参考。
  
Skype for Business Online 连接器模块包括 **New-CsOnlineSession** cmdlet，以便您可以创建连接到Skype for Business Online远程Windows PowerShell会话。此模块，只能在 64 位计算机 （有关详细信息，请参阅[设置您的计算机的 Skype for Business Online 管理使用 Windows PowerShell](set-up-your-computer-for-skype-for-business-online-management-using-windows-powe.md)） 的受支持，可以从在[https://www.microsoft.com/en-us/download/details.aspx?id=39366](https://www.microsoft.com/en-us/download/details.aspx?id=39366)Microsoft 下载中心下载。下载 SkypeOnlinePowershell.exe 文件，然后完成以下过程︰
  
1. 双击 **SkypeOnlinePowershell.exe**文件。
    
2. 在Skype for Business Online，Windows PowerShell 设置向导中的，在 **Microsoft 软件许可条款**页面中，选择 **我接受许可协议的条款**，然后单击 **安装**。如果出现 **用户帐户控制**对话框中，单击 **是**以继续安装。
    
3. 在 **已完成 Skype for Business Online，Windows PowerShell 模块**页上，单击 **完成**。
    
安装程序将Skype for Business Online 连接器模块 （和 **New-CsOnlineSession** cmdlet） 复制到您的计算机。若要访问该模块，启动Windows PowerShell会话管理员凭据，然后运行以下命令︰
  
```
Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
```

如果您不希望每次启动Windows PowerShell键入以下命令，您可以向您Windows PowerShell的配置文件中添加命令。若要执行此操作， Windows PowerShell提示符处键入以下命令，然后按 ENTER:
  
```
notepad.exe $profile
```

记事本出现时，命令 （如果有） 的配置文件中已有的底部添加以下行︰
  
```
Import-Module SkypeOnlineConnector
```

保存文件。下次您启动Windows PowerShell，将自动输入Skype for Business Online 连接器模块 。请注意，您将收到一条错误消息，将不会加载模块，如果您未在运行Windows PowerShell管理员凭据。
  
除了安装Skype for Business Online 连接器模块，SkypeOnlinePowershell.exe 也会安装三个其他组件︰ 1) 身份服务客户端运行时库 (IDCRL)，用来处理客户端到Skype for Business Online; 的身份验证2).NET framework 4.5;然后，3） Microsoft Visual c + + 2012年可再发行程序包 (x64) 程序包 （版本 11.0.50727）。.NET framework 4.5 提供用于创建和运行.NET 应用程序，包括Windows PowerShell基础结构。Visual c + + 可再发行程序包安装计算机没有安装 Microsoft Visual Studio 2012 Visual c + + 运行时的组件。
  
若要验证您的计算机当前已安装的连接线模块的版本号，打开控制面板，打开 **程序和功能** ，然后检查 **Skype for Business Online，Windows PowerShell 模块** 的版本号。
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **机器翻译免责声明**：本文是由无人工介入的计算机系统翻译的。Microsoft 提供机器翻译是为了帮助非英语国家/地区用户方便阅读有关 Microsoft 产品、服务和技术的内容。由于机器翻译的原因，本文可能包含词汇、语法或文法方面的错误。 
  

