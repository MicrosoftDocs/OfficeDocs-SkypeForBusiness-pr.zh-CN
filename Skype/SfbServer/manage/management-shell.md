---
title: Skype for Business Server 命令行管理程序
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
description: Skype for Business Server 命令行管理程序提供了用于服务器管理和管理的命令行界面。 它建立在 Windows PowerShell 之上，包括一套全面的针对 Skype 和旧版 Lync server 产品的管理和管理 cmdlet。
ms.openlocfilehash: 085c8f4a8a454f97dc4fbc640a6f5c8a70baec31
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044254"
---
# <a name="skype-for-business-server-management-shell"></a>Skype for Business Server 命令行管理程序
 
Skype for Business Server 命令行管理程序提供了用于服务器管理和管理的命令行界面。 它建立在 Windows PowerShell 之上，包括一套全面的针对 Skype 和旧版 Lync server 产品的管理和管理 cmdlet。
  
Windows PowerShell 允许您从命令行管理 Microsoft 应用程序。 它包括命令行环境、特定于产品的命令和完整的脚本语言。 Windows PowerShell 首次被引入为2006中的 Windows 操作系统的可下载版本，并被合并为 Microsoft Exchange Server 2007 的可管理性的命令行界面。 它已合并到大多数 Microsoft 服务器产品中，包括从 Lync Server 2010 开始的 Lync 和 Skype 服务器。 Skype for Business Server 命令行管理程序中提供了700以上的 Lync 和 Skype 特定 cmdlet。
  
> [!NOTE]
> Skype for Business cmdlet reference 已移动到 docs.microsoft.com。 单击下面的链接将转到新的 docs.microsoft.com 页面。 现在，内容是开放的，可用于通过 GitHub 进行社区贡献。 对所做的贡献有兴趣？ 查看存储库中的自述文件：[https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)
  
Skype for Business Server 随附700个以上的 cmdlet，使管理员能够使用 Skype for Business Server 命令行管理程序管理 Skype for business Server。 您可以通过键入类似如下的命令，直接从命令行检索有关 cmdlet 的帮助：
  
```PowerShell
Get-Help New-CsVoicePolicy -Full
```

上述命令检索提供的有关 **New-CsVoicePolicy** cmdlet 的完整帮助。 要查看其他 cmdlet 的帮助，请将 **New-CsVoicePolicy** 替换为要检索其帮助信息的 cmdlet 的名称。
  
若要检索可用于管理 Skype for Business Server 的 cmdlet 的完整列表，请在命令行管理程序命令提示符处键入以下内容： 
  
```PowerShell
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



有关在 Skype for Business Server 中了解 Windows PowerShell 的事项：
  
- 若要运行 Skype for Business Server cmdlet，请打开 Skype for Business Server 命令行管理程序。
    
    > [!CAUTION]
    > 如果打开的是 Windows PowerShell 窗口而不是 Skype for Business Server 命令行管理程序，默认情况下，你可能无法运行 Skype cmdlet。 若要从 Windows PowerShell 中运行 Skype for Business Server cmdlet，请首先在 Windows PowerShell 命令提示符处键入以下命令： >`Import-Module SkypeforBusiness`
  
- Skype for business Server 命令行管理程序将自动安装在每个 Skype for Business Server Enterprise Edition 前端服务器或 Standard Edition server 上。
    
- 您可以通过运行[update-help](https://technet.microsoft.com/library/hh849720.aspx) cmdlet 来更新 Skype For Business Server 命令行管理程序帮助内容。 Update-help cmdlet 下载并安装适用于您的计算机上安装的所有模块的最新帮助文件，包括对 Skype for Business cmdlet 的更新。
    
    默认情况下， **update-help** cmdlet 将更新安装在 Skype For business 服务器上的所有模块。 如果只想更新某些模块，可以使用_Module_参数来限制 cmdlet 的作用域。 以下示例仅更新 Skype for Business 模块。
    
  ```PowerShell
  Update-Help -Module SkypeforBusiness
  ```

    如果需要更新未连接到 internet 的服务器上的帮助，可以使用[Save-Help](https://technet.microsoft.com/library/hh849724.aspx) cmdlet 获取帮助的最新版本，并将其保存到指定的位置。 然后，您可以在未连接到 internet 的服务器上使用带有 _-SourcePath_参数的**update-help** cmdlet，从所选位置获取更新的帮助。 下面的示例演示如何将帮助文件保存到网络文件共享，然后从文件共享中更新 Skype for Business 模块的帮助。
    
  ```PowerShell
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
  // Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    有关更多详细信息，请参阅[关于可更新帮助](https://technet.microsoft.com/library/hh847735.aspx)。
    
    > [!NOTE]
    > 如果你远程使用 PowerShell，可能需要允许通过防火墙进行通信。 若要了解有关 PowerShell 远程使用的端口的详细信息，请参阅[Powershell Remoting 使用什么端口？](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/)。
    

