---
title: Skype for Business Server 2015 的安装先决条件
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 2ef91a1e-2899-44c8-8e2c-527cb9114a0a
description: 'Summary: Learn about the servers and server roles you must configure before you install Skype for Business Server 2015. Download a free trial of Skype for Business Server 2015 from the Microsoft Evaluation center at: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: 6f84b4f0a95c45297ad809e6b04217e711c3dd5e
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="install-prerequisites-for-skype-for-business-server-2015"></a>Skype for Business Server 2015 的安装先决条件
 
**Summary:** Learn about the servers and server roles you must configure before you install Skype for Business Server 2015. Download a free trial of Skype for Business Server 2015 from the [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
安装必备软件包括通过在拓扑中的每台服务器上安装所需的角色和功能来设置 Windows Server。 这些要求基于服务器将在拓扑中承担的角色。 第 1 步至第 5 步可以按任意顺序执行。 但是，第 6、7、8 步必须在第 1 步至第 5 步之后按图表所示顺序执行。 安装必备软件是 8 个步骤中的第 1 步。
  
![概述图表 - 安装必备组件。](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a>设置 Windows Server

Skype for Business Server 2015 requires the Windows Server operating system and a number of prerequisites before it can be installed. For details on planning for prerequisites, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md). 
  
> [!TIP]
> 此过程使用 Windows Server 2012 R2。如果您要使用其他版本的 Windows Server，该过程可能略有不同。 
  
> [!IMPORTANT]
> Before you begin, make sure that Windows Server is up-to-date by using Windows Update. 
  
![Windows Server 最新版本。](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
观看视频，了解**安装必备组件**的步骤：
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/02447c2a-5b26-432f-aad6-b9b05cc93478?autoplay=false]
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a>为前端服务器安装必要的角色和功能

1. 打开服务器管理器，然后单击“**添加角色和功能**”。
    
2. 阅读“**开始之前**”页以熟悉如何在 Windows Server 中安装角色和功能，然后单击“**下一步**”。
    
3. 选择“**基于角色或基于功能的安装**”，然后单击“**下一步**”。
    
4. Select the server on which you will be installing Skype for Business Server 2015, and click **Next**.
    
5. 选择“**Web 服务器 (IIS)**”角色，在必要功能窗口弹出时，单击“**添加功能**”，然后单击“**下一步**”。
    
6. Make sure the software features listed in [Software that should be installed before a Skype for Business Server 2015 deployment](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#Software) are on the server that will run Skype for Business Server 2015. Here's an abbreviated list:
    
   - .NET Framework Features
    
   - WCF 服务
    
   - HTTP 激活
    
    > [!NOTE]
    > HTTP 激活需要其他功能。单击选择 HTTP 激活时弹出的警告对话框上的“**添加功能**”。
  
   - Media Foundation (required by Front End Servers and Standard Edition servers used for conferencing.)
    
   - 远程服务器管理工具
    
   - 角色管理工具
    
   - AD DS 
    
   - AD LDS
    
   - Windows Identity Foundation 3.5
    
7. 单击“**下一步**”继续执行向导。
    
8. 阅读有关 **Web 服务器角色 (IIS)** 的说明，然后单击“**下一步**”。
    
9. 选择以下 **Web 服务器 (IIS) 角色服务**。
    
   - 常见的 HTTP 功能
    
   - 默认文档
    
   - 目录浏览
    
   - HTTP 错误
    
   - 静态内容
    
   - 运行状况和诊断
    
   - HTTP 日志记录
    
   - 日志记录工具
    
   - 跟踪
    
   - 性能
    
   - 静态内容压缩
    
   - 动态内容压缩
    
   - 安全性
    
   - 请求筛选
    
   - 客户端证书映射身份验证
    
   - Windows 身份验证
    
   - 应用程序开发
    
   - .NET Extensibility 3.5
    
   - .NET Extensibility 4.5
    
   - ASP.NET 3.5
    
   - ASP.NET 4.5
    
   - ISAPI 扩展
    
   - ISAPI 筛选器
    
   - 管理工具
    
   - IIS 管理控制台
    
   - IIS 管理脚本和工具
    
10. 单击“**下一步**”继续执行向导。
    
11. 检查安装选择以确保选中了所有必要组件，然后单击“**安装**”。
    
    > [!CAUTION]
    > Windows Server 2012 R2 不会默认安装必要功能的所有源文件。 如果服务器未连接 Internet，您需要插入 Windows Server 2012 R2 媒体并选择“**指定备用源路径**”以安装必要功能。 源文件位于 sources\sxs 目录中。 例如，如果 Windows Server 2012 R2 媒体在驱动器 D 中，则您将路径设为 `d:\sources\sxs`。 > It is important that you have the latest updates from Windows Update. 如果您没有连接到 Internet，您需要手动安装所有相关更新以及更新所需的必备软件。 
  
12. 当出现对话框表示已完成安装时，您需要重新启动服务器以完成该流程。
    
13. 再次运行 **Windows Update** 以检查安装的角色和服务是否存在可用更新。
    
14. If you will be using Skype for Business Server Control Panel on this server then you must also install Silverlight. To install Silverlight, see [Microsoft Silverlight](https://www.microsoft.com/silverlight/).
    
可通过运行以下 PowerShell 命令来安装必备组件。 注意，该命令会按特定顺序查找源文件。 如果您处于联机状态，该命令可访问 Windows Update。 但是，如果您处于脱机状态，则需要确保源文件可被该命令使用。 For more information about using PowerShell to install roles and features, see [Install or Uninstall Roles, Role Services, or Features](https://technet.microsoft.com/en-us/library/hh831809.aspx) and [Install-WindowsFeature](https://technet.microsoft.com/en-us/library/jj205467.aspx). 在安装必备软件后，即使是使用 PowerShell 命令执行的，也不要忘记再次运行 Windows Update。
```
Add-WindowsFeature NET-Framework-Core, RSAT-ADDS, Windows-Identity-Foundation, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Dir-Browsing, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, BITS
```

> [!IMPORTANT]
> 执行前端服务器以外的角色（例如控制器、持久聊天或边缘角色）的服务器具备自己的先决条件。 For details on the exact prerequisites required by each server type, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md). 
  

