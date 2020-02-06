---
title: Skype for Business Server 管理程序
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
description: Skype for Business Server Management Shell 提供用于服务器管理和管理的命令行界面。 它在 Windows PowerShell 上构建，其中包含一组专用于 Skype 和旧版 Lync 服务器产品的全面的管理和管理 cmdlet。
ms.openlocfilehash: 294de750795985d50c6301a88f4b835f1cad78b7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817551"
---
# <a name="skype-for-business-server-management-shell"></a>Skype for Business Server 管理程序
 
Skype for Business Server Management Shell 提供用于服务器管理和管理的命令行界面。 它在 Windows PowerShell 上构建，其中包含一组专用于 Skype 和旧版 Lync 服务器产品的全面的管理和管理 cmdlet。
  
Windows PowerShell 允许你从命令行管理 Microsoft 应用程序。 它包括命令行环境、特定于产品的命令和完整的脚本语言。 Windows PowerShell 第一次引入于2006中的 Windows 操作系统的可下载版本，并已被合并为 Microsoft Exchange Server 2007 的可管理性的命令行界面。 它已合并到大多数 Microsoft 服务器产品中，包括从 Lync Server 2010 开始的 Lync 和 Skype 服务器。 Skype for business Server 命令行管理程序中提供了700以上的 Lync 和 Skype 特定 cmdlet。
  
> [!NOTE]
> Skype for Business cmdlet 参考已移至 docs.microsoft.com。 单击下面的链接将转至新的 docs.microsoft.com 页面。 内容现在是开源的，可通过 GitHub 用于社区投稿。 对投稿感兴趣？ 查看存储库中的自述文件：[https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)
  
Skype for Business 服务器随附有700多个 cmdlet，允许管理员使用 Skype for Business Server 命令行管理器管理 Skype for business 服务器。 您可以通过键入以下类似命令，从命令行直接检索 cmdlet 的相关帮助：
  
```PowerShell
Get-Help New-CsVoicePolicy -Full
```

上述命令检索有关 **New-CsVoicePolicy** cmdlet 的可用完整帮助。 要查看其他 cmdlet 的帮助，请将 **New-CsVoicePolicy** 替换为要检索其帮助信息的 cmdlet 的名称。
  
要检索可用于管理 Skype for Business Server 的 cmdlet 的完整列表，请在 Shell 命令提示符处键入以下内容： 
  
```PowerShell
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



有关在 Skype for Business 服务器中了解 Windows PowerShell 的事项：
  
- 若要运行 Skype for Business 服务器 cmdlet，请打开 Skype for business Server 命令行管理程序。
    
    > [!CAUTION]
    > 如果打开的是 Windows PowerShell 窗口，而不是 Skype for Business Server Management Shell，则默认情况下你可能无法运行 Skype cmdlet。 若要从 Windows PowerShell 中运行 Skype for Business Server cmdlet，请首先在 Windows PowerShell 命令提示符处键入以下内容： >`Import-Module SkypeforBusiness`
  
- Skype for business Server Management Shell 将自动安装在每个 Skype for business 服务器企业版前端服务器或标准版服务器上。
    
- 您可以通过运行[update-help](https://technet.microsoft.com/en-us/library/hh849720.aspx) cmdlet 来更新 Skype For Business Server Management Shell 帮助内容。 Update-Help cmdlet 下载并安装适用于你的计算机上安装的所有模块的最新帮助文件，包括 Skype for Business cmdlet 的更新。
    
    默认情况下， **update-Help** cmdlet 将更新安装在 Skype For business 服务器上的所有模块。 如果您想仅更新特定模块，则可以使用 _Module_ 参数来限制 cmdlet 的作用域。 以下示例仅更新 Skype for Business 模块。
    
  ```PowerShell
  Update-Help -Module SkypeforBusiness
  ```

    如果需要更新未连接到 internet 的服务器上的帮助，您可以使用[Save-help](https://technet.microsoft.com/en-us/library/hh849724.aspx) cmdlet 获取帮助的最新版本，并将其保存到您指定的位置。 然后，你可以在未连接到 internet 的服务器上使用带有 _-SourcePath_参数的**Update-help** cmdlet 从所选位置获取更新的帮助。 以下示例显示了如何将帮助文件保存到网络文件共享，然后从文件共享中更新 Skype for Business 模块的帮助。
    
  ```PowerShell
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
  // Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    有关更多详细信息，请参阅[关于可更新帮助](https://technet.microsoft.com/library/hh847735.aspx)。
    
    > [!NOTE]
    > 如果你远程使用 PowerShell，可能需要允许通过防火墙进行通信。 若要了解有关 PowerShell 远程使用的端口的详细信息，请参阅[Powershell Remoting 使用哪个端口？](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/)。
    

