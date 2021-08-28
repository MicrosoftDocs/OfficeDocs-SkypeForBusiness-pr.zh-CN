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
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
description: 命令行Skype for Business Server命令行管理程序为服务器管理提供了命令行界面。 它基于Windows PowerShell，包括一套全面的管理 cmdlet，这些 cmdlet 特定于 Skype 和旧 Lync Server 产品。
ms.openlocfilehash: dbff67d52d616d55d8e183ffab91126f8546f1b1
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58609289"
---
# <a name="skype-for-business-server-management-shell"></a>Skype for Business Server 命令行管理程序
 
命令行Skype for Business Server命令行管理程序为服务器管理提供了命令行界面。 它基于Windows PowerShell，包括一套全面的管理 cmdlet，这些 cmdlet 特定于 Skype 和旧 Lync Server 产品。
  
Windows PowerShell通过命令行管理 Microsoft 应用程序。 它包括命令行环境、特定于产品的命令和完整的脚本语言。 Windows PowerShell在 2006 年后期首次作为 Windows 操作系统的可下载版本引入，并合并为 Microsoft Exchange Server 2007 的命令行界面。 它已合并到大多数 Microsoft Server 产品中，包括 Lync 和 Skype Lync Server 2010 开始的服务器。 在命令行管理程序中Skype 700 多个 Lync 和 Skype for Business Server cmdlet。
  
> [!NOTE]
> Skype for Business cmdlet 引用已移动到 docs.microsoft.com。 单击下面的链接将进入新的 docs.microsoft.com 页面。 内容现在是开源的，可用于通过 GitHub。 有兴趣参与？ 在此处查看存储库的自述文： [https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)
  
Skype for Business Server 700 多个 cmdlet，使管理员能够Skype for Business Server命令行管理程序Skype for Business Server管理程序。 通过键入类似于以下的命令，可以直接从命令行检索 cmdlet 的帮助：
  
```PowerShell
Get-Help New-CsVoicePolicy -Full
```

上述命令检索提供的有关 **New-CsVoicePolicy** cmdlet 的完整帮助。要查看其他 cmdlet 的帮助，请将 **New-CsVoicePolicy** 替换为要检索其帮助信息的 cmdlet 的名称。
  
若要检索可用于管理 Skype for Business Server 的完整 cmdlet 列表，在命令行管理程序命令提示符中键入以下内容： 
  
```PowerShell
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



有关在服务Windows PowerShell的Skype for Business Server：
  
- 若要运行 Skype for Business Server cmdlet，请打开 Skype for Business Server 命令行管理程序。
    
    > [!CAUTION]
    > 如果您打开Windows PowerShell而不是命令行管理Skype for Business Server，则默认情况下可能无法运行 Skype cmdlet。 若要从 Skype for Business Server运行 cmdlet，Windows PowerShell在命令提示符下键入Windows PowerShell：>`Import-Module SkypeforBusiness`
  
- Skype for Business Server命令行管理程序会自动安装在前端Skype for Business Server Enterprise Edition服务器或 Standard Edition服务器上。
    
- 可以通过运行[Update-Skype for Business Server](/powershell/module/microsoft.powershell.core/update-help) Cmdlet 来更新命令行管理程序帮助内容。 此 Update-Help cmdlet 可下载并安装可供您计算机上安装的所有模块使用的最新帮助文件，包括更新 Skype for Business cmdlet。
    
    默认情况下 **，Update-Help** cmdlet 将更新安装在您的 Skype for Business Server。 如果只想更新某些模块，可以使用 _Module_ 参数来限制 cmdlet 的范围。 以下示例仅更新Skype for Business模块。
    
  ```PowerShell
  Update-Help -Module SkypeforBusiness
  ```

    如果需要更新未连接到 Internet 的服务器的"帮助"，可以使用 [Save-Help](/powershell/module/microsoft.powershell.core/save-help) cmdlet 获取最新版本的帮助，并将其保存到指定的位置。 然后，可以在未连接到 Internet 的服务器上将 **Update-Help** cmdlet 与 _-SourcePath_ 参数一同使用，从所选位置获取更新的帮助。 以下示例演示如何将帮助文件保存到网络文件共享，然后从文件共享中更新 Skype for Business 模块的帮助。
    
  ```PowerShell
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
  // Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    有关更多详细信息，请参阅关于 [可更新的帮助](/powershell/module/microsoft.powershell.core/about/about_updatable_help)。
    
    > [!NOTE]
    > 如果远程使用 PowerShell，可能需要允许通过防火墙通信。 若要详细了解 PowerShell 远程处理使用的端口，请参阅 What [Port Does PowerShell Remoting Use？。](/archive/blogs/christwe/what-port-does-powershell-remoting-use)
