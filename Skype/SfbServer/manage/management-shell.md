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
description: Skype 的业务服务器管理外壳程序提供命令行界面的服务器管理和管理。 它构建在 Windows PowerShell，并包括一套全面的管理和管理特定于 Skype 和旧式 Lync 服务器产品的 cmdlet。
ms.openlocfilehash: e4eb5f183af29dd5f9932fb15cdb86a0f78e7840
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="skype-for-business-server-2015-management-shell"></a>Skype for Business Server 2015 命令行管理程序
 
Skype 的业务服务器管理外壳程序提供命令行界面的服务器管理和管理。 它构建在 Windows PowerShell，并包括一套全面的管理和管理特定于 Skype 和旧式 Lync 服务器产品的 cmdlet。
  
Windows PowerShell 允许您从命令行管理 Microsoft 应用程序。 它包括命令行环境、特定于产品的命令和完整的脚本语言。 Windows PowerShell 最晚在 2006 年，第一次作为一个可下载版本 Windows 操作系统的引入，并纳入为 Microsoft Exchange Server 2007年的可管理性的命令行接口。 它已合并成包括 Lync 和 Skype 开头 Lync Server 2010 中的服务器的 Microsoft 服务器产品的大部分。 Skype 的业务服务器管理外壳程序中有 700 Lync 和 Skype 的特定 cmdlet。
  
> [!NOTE]
> Skype 业务 cmdlet 引用移到 docs.microsoft.com。单击下面的链接将进入新的 docs.microsoft.com 页。 内容现在是开源的，可通过 GitHub 用于社区投稿。 对投稿感兴趣？ 请查阅此处 repo 中的自述文件：[https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)
  
Skype 的业务服务器 2015年附带使管理员能够管理的业务服务器的业务服务器管理外壳使用 Skype 的 Skype 的 700 多个 cmdlet。 您可以通过键入以下类似命令，从命令行直接检索 cmdlet 的相关帮助：
  
```
Get-Help New-CsVoicePolicy -Full
```

上面的命令检索可用于**新建 CsVoicePolicy** cmdlet 的完整帮助。 若要查看其他 cmdlet 的帮助，请替换为具有您要为其检索帮助该 cmdlet 名称**新建 CsVoicePolicy** 。
  
要检索可用于管理 Skype for Business Server 的 cmdlet 的完整列表，请在 Shell 命令提示符处键入以下内容： 
  
```
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



了解 Windows PowerShell 在 Skype 业务服务器的注意事项：
  
- 若要运行业务服务器 cmdlet 的 Skype，业务服务器管理外壳程序打开 Skype。
    
    > [!CAUTION]
    > 如果您打开 Windows PowerShell 窗口，而不是 Skype 业务服务器管理外壳，默认情况下您可能不能运行 Skype cmdlet。 要运行 Skype 业务服务器 cmdlet 从 Windows PowerShell 中，首先键入以下 Windows PowerShell 命令提示符处： >`Import-Module SkypeforBusiness`
  
- 在每一个 Skype 业务服务器企业版前端服务器或标准版服务器上自动安装 Skype 的业务服务器管理程序。
    
- 您可以通过运行[更新帮助](https://technet.microsoft.com/en-us/library/hh849720.aspx)cmdlet 更新 Skype 业务服务器管理外壳程序帮助内容。 更新帮助 cmdlet 下载并安装最新的帮助文件可用于所有模块包括 Skype 业务 cmdlet 的更新您计算机上安装。
    
    默认情况下，**更新帮助**cmdlet 将更新为业务服务器在您 Skype 上安装的所有模块。 如果您想要更新特定的模块，可以使用_模块_参数来限制该 cmdlet 的范围。 下面的示例更新仅 Skype 业务模块。
    
  ```
  Update-Help -Module SkypeforBusiness
  ```

    如果您需要更新未连接到 internet 的服务器上的帮助，可以使用[保存帮助](https://technet.microsoft.com/en-us/library/hh849724.aspx)cmdlet 以获取最新版本的帮助，并将其保存到您指定的位置。 然后可以在未连接到 internet 的服务器上_的源路径_参数与使用**更新帮助**cmdlet 从您选定的位置获取更新的帮助。 下面的示例演示如何将帮助文件保存到网络文件共享，然后更新该文件共享上的 Skype 业务模块的帮助。
    
  ```
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
// Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    有关更多详细信息，请参阅[关于更新帮助](https://technet.microsoft.com/library/hh847735.aspx)。
    

