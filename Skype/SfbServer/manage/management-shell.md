---
title: Skype for Business Server 命令行管理程序
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
description: Skype for Business Server 命令行管理程序提供用于服务器管理命令行界面。 它构建于 Windows PowerShell，包括一组全面的管理 cmdlet，这些 cmdlet 特定于 Skype 和旧版 Lync Server 产品。
ms.openlocfilehash: 0653faa542bc9bc579bd7617e40d3efed030569f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816532"
---
# <a name="skype-for-business-server-management-shell"></a>Skype for Business Server 命令行管理程序
 
Skype for Business Server 命令行管理程序提供用于服务器管理命令行界面。 它构建于 Windows PowerShell，包括一组全面的管理 cmdlet，这些 cmdlet 特定于 Skype 和旧版 Lync Server 产品。
  
Windows PowerShell通过命令行管理 Microsoft 应用程序。 它包括命令行环境、特定于产品的命令和完整的脚本语言。 Windows PowerShell在 2006 年后期首次作为 Windows 操作系统的可下载版本引入，并合并为命令行界面，用于实现 Microsoft Exchange Server 2007 的可管理性。 它已合并到大多数 Microsoft Server 产品中，包括从 Lync Server 2010 开始的 Lync 和 Skype 服务器。 Skype for Business Server 命令行管理程序 中提供了 700 多个 Lync 和 Skype 特定 cmdlet。
  
> [!NOTE]
> Skype for Business cmdlet 引用已移动到 docs.microsoft.com。 单击下面的链接将进入新的docs.microsoft.com页面。 内容现已开放源代码，可用于通过 GitHub 提供社区参与。 有兴趣参与？ 在此处查看存储库的自述文： [https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)
  
Skype for Business Server 附带了 700 多个 cmdlet，使管理员能够使用 Skype for Business Server 命令行管理程序管理 Skype for Business Server。 可以通过键入类似于以下的命令直接从命令行检索 cmdlet 的帮助：
  
```PowerShell
Get-Help New-CsVoicePolicy -Full
```

上述命令检索提供的有关 **New-CsVoicePolicy** cmdlet 的完整帮助。 要查看其他 cmdlet 的帮助，请将 **New-CsVoicePolicy** 替换为要检索其帮助信息的 cmdlet 的名称。
  
若要检索可用于管理 Skype for Business Server 的 cmdlet 的完整列表，在命令行管理程序命令提示符下键入以下内容： 
  
```PowerShell
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



有关 Skype for Business Server Windows PowerShell的信息：
  
- 若要运行 Skype for Business Server cmdlet，请打开 Skype for Business Server 命令行管理程序。
    
    > [!CAUTION]
    > 如果打开Windows PowerShell而不是 Skype for Business Server 命令行管理程序，则默认情况下可能无法运行 Skype cmdlet。 若要从内部运行 Skype for Business Server cmdlet Windows PowerShell，首先在命令提示符Windows PowerShell键入以下内容：>  `Import-Module SkypeforBusiness`
  
- Skype for Business Server 命令行管理程序会自动安装在每个 Skype for Business Server Enterprise Edition 前端服务器或 Standard Edition 服务器上。
    
- 可以通过运行 [Update-Help](https://technet.microsoft.com/library/hh849720.aspx) cmdlet 来更新 Skype for Business Server 命令行管理程序 帮助内容。 Update-Help cmdlet 可下载并安装可供计算机上安装的所有模块使用的最新帮助文件，包括 Skype for Business cmdlet 更新。
    
    默认情况下 **，Update-Help** cmdlet 将更新安装在 Skype for Business Server 上的所有模块。 如果只想更新某些模块，可以使用 _Module_ 参数来限制 cmdlet 的范围。 以下示例仅更新 Skype for Business 模块。
    
  ```PowerShell
  Update-Help -Module SkypeforBusiness
  ```

    如果需要更新未连接到 Internet 的服务器上的帮助，可以使用 [Save-Help](https://technet.microsoft.com/library/hh849724.aspx) cmdlet 获取最新版本的帮助并将其保存到指定的位置。 然后，可以在未连接到 Internet 的服务器上将 **Update-Help** cmdlet 与 _-SourcePath_ 参数一同使用，以从所选位置获取更新的帮助。 以下示例演示如何将帮助文件保存到网络文件共享，然后从文件共享更新 Skype for Business 模块的帮助。
    
  ```PowerShell
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
  // Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    有关更多详细信息，请参阅["关于可更新的帮助"。](https://technet.microsoft.com/library/hh847735.aspx)
    
    > [!NOTE]
    > 如果远程使用 PowerShell，可能需要允许通过防火墙通信。 若要了解有关 PowerShell 远程处理使用的端口信息，请参阅["PowerShell 远程处理使用什么端口？"。](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/)
    

