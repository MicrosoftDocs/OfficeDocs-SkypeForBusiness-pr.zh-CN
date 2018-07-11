---
title: Skype for Business Server 2015 命令行管理程序
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 9/20/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
description: 业务 Server 命令行管理程序 Skype 服务器管理和管理提供命令行界面。 它基于 Windows PowerShell，并包含一组全面的管理和管理特定于 Skype 和旧式 Lync server 产品的 cmdlet。
ms.openlocfilehash: 50e76784526a3430c6e91a3c6cfdd76962fda3cd
ms.sourcegitcommit: 8c3dcfc564c489f4d33bd5f391a5a66b99ded07e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/11/2018
ms.locfileid: "20266879"
---
# <a name="skype-for-business-server-2015-management-shell"></a>Skype for Business Server 2015 命令行管理程序
 
业务 Server 命令行管理程序 Skype 服务器管理和管理提供命令行界面。 它基于 Windows PowerShell，并包含一组全面的管理和管理特定于 Skype 和旧式 Lync server 产品的 cmdlet。
  
Windows PowerShell，可以从命令行管理 Microsoft 应用程序。 它包括命令行环境、特定于产品的命令和完整的脚本语言。 Windows PowerShell 首次引入的 Windows 操作系统的可下载版本作为最晚在 2006 年，并已合并为可管理性的 Microsoft Exchange Server 2007 的命令行接口。 它已合并到大多数 Microsoft 服务器产品，包括 Lync 和 Skype 开头 Lync Server 2010 的服务器。 Skype 的业务 Server 命令行管理程序中提供了 700 Lync 和 Skype 的特定 cmdlet。
  
> [!NOTE]
> Skype for Business cmdlet 参考已移至 docs.microsoft.com。 单击下面的链接将转至新的 docs.microsoft.com 页面。 内容现在是开源的，可通过 GitHub 用于社区投稿。 对投稿感兴趣？ 查看自述文件在此处 repo 中：[https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)
  
Skype 的业务服务器 2015年附带使管理员能够管理对业务 Server 命令行管理程序中使用 Skype 的业务服务器 Skype 的多个 700 cmdlet。 您可以通过键入以下类似命令，从命令行直接检索 cmdlet 的相关帮助：
  
```
Get-Help New-CsVoicePolicy -Full
```

上述命令检索可用于**New-csvoicepolicy** cmdlet 的完整帮助。 若要查看不同 cmdlet 的帮助，请替换为您要为其检索帮助 cmdlet 的名称 **-New-csvoicepolicy** 。
  
要检索可用于管理 Skype for Business Server 的 cmdlet 的完整列表，请在 Shell 命令提示符处键入以下内容： 
  
```
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



项关键须知 Skype 中的 Windows PowerShell 业务服务器：
  
- 若要运行 Business Server cmdlet Skype，打开 Skype 业务 Server Management Shell。
    
    > [!CAUTION]
    > 如果您的业务 Server 命令行管理程序中打开 Windows PowerShell 窗口而不是 Skype 后，默认情况下您可能无法运行的 Skype cmdlet。 若要运行 Skype 的业务 Server cmdlet 从 Windows PowerShell 中，首先键入以下 Windows PowerShell 命令提示符处： >`Import-Module SkypeforBusiness`
  
- 每个 Skype 业务 Server Enterprise Edition 前端服务器或 Standard Edition server 上自动安装 Business Server Management Shell 的 Skype。
    
- 您可以通过运行[更新帮助](https://technet.microsoft.com/en-us/library/hh849720.aspx)cmdlet 更新业务 Server 命令行管理程序帮助内容 Skype。 更新帮助 cmdlet 下载并安装的最新帮助文件提供的所有模块包括 Skype 业务 cmdlet 更新您计算机上安装。
    
    默认情况下，**更新帮助**cmdlet 将更新业务服务器安装在您 Skype 上的所有模块。 如果您想要更新只有某些模块，您可以使用_模块_参数来限制范围的 cmdlet。 下面的示例更新仅 for Business 模块 Skype。
    
  ```
  Update-Help -Module SkypeforBusiness
  ```

    如果您需要更新的帮助未连接到 internet 的服务器上，您可以使用[保存帮助](https://technet.microsoft.com/en-us/library/hh849724.aspx)cmdlet 获取帮助的最新版本，并将其保存到您指定的位置。 然后可以使用 _-SourcePath_参数未连接到 internet 的服务器上使用**更新帮助**cmdlet 获取所选的位置更新的帮助。 下面的示例演示如何帮助文件保存到网络文件共享，然后更新从文件共享的业务模块 Skype 的帮助。
    
  ```
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
  // Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    有关详细信息，请参阅[有关可更新帮助](https://technet.microsoft.com/library/hh847735.aspx)。
    
    > [!NOTE]
    > 如果您使用的 PowerShell 远程您可能需要允许通过防火墙的通信。 若要了解有关 PowerShell 远程处理使用的端口的详细信息，请参阅[哪些端口不 PowerShell 远程处理使用？](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/)。
    

