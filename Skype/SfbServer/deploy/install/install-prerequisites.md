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
description: '摘要： 了解服务器和服务器角色的业务服务器 2015年安装 Skype 之前必须配置。 有关从 Microsoft 评估中心的业务服务器 2015年下载免费试用版的 Skype: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server。'
ms.openlocfilehash: 350f64a2808e51866cd5720cb1955259ff773c81
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="install-prerequisites-for-skype-for-business-server-2015"></a>Skype for Business Server 2015 的安装先决条件
 
**摘要：**了解有关服务器和服务器角色的业务服务器 2015年安装 Skype 之前必须配置。 有关从[Microsoft 评估中心](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)业务服务器 2015年下载 Skype 的免费试用版。
  
安装必备软件包括通过在拓扑中的每台服务器上安装所需的角色和功能来设置 Windows Server。 这些要求基于服务器将在拓扑中承担的角色。 第 1 步至第 5 步可以按任意顺序执行。 但是，第 6、7、8 步必须在第 1 步至第 5 步之后按图表所示顺序执行。 安装必备软件是 8 个步骤中的第 1 步。
  
![概述图表 - 安装必备组件。](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a>设置 Windows Server

Skype 的业务服务器 2015年要求 Windows 服务器操作系统和多个系统必备组件才能安装。 有关规划系统必备组件的详细信息，请参阅[业务服务器 2015年的 Skype 的服务要求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。 
  
> [!TIP]
> 此过程使用 Windows Server 2012 R2。如果您要使用其他版本的 Windows Server，该过程可能略有不同。 
  
> [!IMPORTANT]
> 在开始之前，请确保 Windows 服务器是通过 Windows 更新保持最新。 
  
![Windows Server 最新版本。](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
观看视频，了解**安装必备组件**的步骤：
  
![您的浏览器不支持视频。 安装 Microsoft Silverlight、Adobe Flash Player 或 Internet Explorer 9。](../../media/MSN_Video_Widget.gif)
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a>为前端服务器安装必要的角色和功能

1. 打开服务器管理器，然后单击“**添加角色和功能**”。
    
2. 阅读“**开始之前**”页以熟悉如何在 Windows Server 中安装角色和功能，然后单击“**下一步**”。
    
3. 选择“**基于角色或基于功能的安装**”，然后单击“**下一步**”。
    
4. 选择的服务器要安装 Skype 业务服务器 2015，并单击**下一步**。
    
5. 选择“**Web 服务器 (IIS)**”角色，在必要功能窗口弹出时，单击“**添加功能**”，然后单击“**下一步**”。
    
6. 确保软件功能[，应安装之前的业务服务器 2015年部署 Skype 软件](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#Software)中列出将运行业务服务器 2015 Skype 的服务器上。 下面是一个简短的列表：
    
   - .NET Framework 功能
    
   - WCF 服务
    
   - HTTP 激活
    
    > [!NOTE]
    > HTTP 激活需要其他功能。单击选择 HTTP 激活时弹出的警告对话框上的“**添加功能**”。
  
   - 媒体基础 （所必需的前端服务器和标准版用于会议的服务器）。
    
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
    > Windows Server 2012 R2 不会默认安装必要功能的所有源文件。 如果服务器未连接 Internet，您需要插入 Windows Server 2012 R2 媒体并选择“**指定备用源路径**”以安装必要功能。 源文件位于 sources\sxs 目录中。 例如，如果 Windows Server 2012 R2 媒体在驱动器 D 中，则您将路径设为 `d:\sources\sxs`。 > 很重要，必须从 Windows 更新最新的更新。 如果您没有连接到 Internet，您需要手动安装所有相关更新以及更新所需的必备软件。 
  
12. 当出现对话框表示已完成安装时，您需要重新启动服务器以完成该流程。
    
13. 再次运行 **Windows Update** 以检查安装的角色和服务是否存在可用更新。
    
14. 如果您将使用 Skype 业务服务器控件面板在此服务器上，然后还必须安装 Silverlight。 若要安装 Silverlight，请参阅[Microsoft Silverlight](https://www.microsoft.com/silverlight/)。
    
可通过运行以下 PowerShell 命令来安装必备组件。 注意，该命令会按特定顺序查找源文件。 如果您处于联机状态，该命令可访问 Windows Update。 但是，如果您处于脱机状态，则需要确保源文件可被该命令使用。 有关使用 PowerShell 安装角色和功能的详细信息，请参阅[安装或卸载角色、 角色服务或功能](https://technet.microsoft.com/en-us/library/hh831809.aspx)，并[安装 WindowsFeature](https://technet.microsoft.com/en-us/library/jj205467.aspx)。 在安装必备软件后，即使是使用 PowerShell 命令执行的，也不要忘记再次运行 Windows Update。
```
Add-WindowsFeature NET-Framework-Core, RSAT-ADDS, Windows-Identity-Foundation, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Dir-Browsing, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, BITS
```

> [!IMPORTANT]
> 执行前端服务器以外的角色（例如控制器、持久聊天或边缘角色）的服务器具备自己的先决条件。 每个服务器类型所需的精确系统必备组件的详细信息，请参阅[业务服务器 2015年的 Skype 的服务要求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。 
  

