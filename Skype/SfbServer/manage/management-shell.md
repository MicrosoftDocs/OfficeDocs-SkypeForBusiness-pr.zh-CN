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
description: Skype for Business Server 命令行管理程序为服务器管理提供了命令行界面。 它基于Windows PowerShell，包括一套全面的管理 cmdlet，这些 cmdlet 特定于 Skype 和旧 Lync Server 产品。
ms.openlocfilehash: 24da9ac341129239399ea17218be8547f3549d6f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118581"
---
# <a name="skype-for-business-server-management-shell"></a><span data-ttu-id="86e6b-104">Skype for Business Server 命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="86e6b-104">Skype for Business Server Management Shell</span></span>
 
<span data-ttu-id="86e6b-105">Skype for Business Server 命令行管理程序为服务器管理提供了命令行界面。</span><span class="sxs-lookup"><span data-stu-id="86e6b-105">The Skype for Business Server Management Shell provides the command line interface for server administration and management.</span></span> <span data-ttu-id="86e6b-106">它基于Windows PowerShell，包括一套全面的管理 cmdlet，这些 cmdlet 特定于 Skype 和旧 Lync Server 产品。</span><span class="sxs-lookup"><span data-stu-id="86e6b-106">It is built on Windows PowerShell and includes a comprehensive set of management and administration cmdlets that are specific to Skype and legacy Lync server products.</span></span>
  
<span data-ttu-id="86e6b-107">Windows PowerShell通过命令行管理 Microsoft 应用程序。</span><span class="sxs-lookup"><span data-stu-id="86e6b-107">Windows PowerShell allows you to manage Microsoft applications from the command line.</span></span> <span data-ttu-id="86e6b-108">它包括命令行环境、特定于产品的命令和完整的脚本语言。</span><span class="sxs-lookup"><span data-stu-id="86e6b-108">It includes a command-line environment, product-specific commands, and a full scripting language.</span></span> <span data-ttu-id="86e6b-109">Windows PowerShell在 2006 年后期首次作为 Windows 操作系统的可下载版本引入，并合并为命令行界面，用于实现 Microsoft Exchange Server 2007 的可管理性。</span><span class="sxs-lookup"><span data-stu-id="86e6b-109">Windows PowerShell was first introduced as a downloadable release for the Windows operating system late in 2006, and was incorporated as the command-line interface for manageability of Microsoft Exchange Server 2007.</span></span> <span data-ttu-id="86e6b-110">它已合并到大多数 Microsoft Server 产品中，包括 Lync 和 Skype 服务器（从 Lync Server 2010 开始）。</span><span class="sxs-lookup"><span data-stu-id="86e6b-110">It has been incorporated into most of the Microsoft Server products, including Lync and Skype servers beginning with Lync Server 2010.</span></span> <span data-ttu-id="86e6b-111">Skype for Business Server 命令行管理程序 中提供了 700 多个 Lync 和 Skype 特定 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="86e6b-111">There are over 700 Lync and Skype specific cmdlets available in the Skype for Business Server Management Shell.</span></span>
  
> [!NOTE]
> <span data-ttu-id="86e6b-112">Skype for Business cmdlet 引用已移动到 docs.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="86e6b-112">Skype for Business cmdlet reference has moved to docs.microsoft.com.</span></span> <span data-ttu-id="86e6b-113">单击下面的链接将进入新的 docs.microsoft.com 页面。</span><span class="sxs-lookup"><span data-stu-id="86e6b-113">Clicking on the links below will take you to the new docs.microsoft.com page.</span></span> <span data-ttu-id="86e6b-114">内容现在是开源的，并且可以通过 GitHub 供社区参与。</span><span class="sxs-lookup"><span data-stu-id="86e6b-114">The content is now open sourced and available for community contributions through GitHub.</span></span> <span data-ttu-id="86e6b-115">有兴趣参与？</span><span class="sxs-lookup"><span data-stu-id="86e6b-115">Interested in contributing?</span></span> <span data-ttu-id="86e6b-116">在此处查看存储库的自述文： [https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)</span><span class="sxs-lookup"><span data-stu-id="86e6b-116">Check out the README in the repo here: [https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)</span></span>
  
<span data-ttu-id="86e6b-117">Skype for Business Server 附带了 700 多个 cmdlet，使管理员能够使用 Skype for Business Server 命令行管理程序管理 Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="86e6b-117">Skype for Business Server ships with more than 700 cmdlets that enable administrators to manage Skype for Business Server using the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="86e6b-118">通过键入类似于以下的命令，可以直接从命令行检索 cmdlet 的帮助：</span><span class="sxs-lookup"><span data-stu-id="86e6b-118">You can retrieve help for a cmdlet directly from the command line by typing a command similar to the following:</span></span>
  
```PowerShell
Get-Help New-CsVoicePolicy -Full
```

<span data-ttu-id="86e6b-119">上述命令检索提供的有关 **New-CsVoicePolicy** cmdlet 的完整帮助。</span><span class="sxs-lookup"><span data-stu-id="86e6b-119">The preceding command retrieves the complete help available for the **New-CsVoicePolicy** cmdlet.</span></span> <span data-ttu-id="86e6b-120">要查看其他 cmdlet 的帮助，请将 **New-CsVoicePolicy** 替换为要检索其帮助信息的 cmdlet 的名称。</span><span class="sxs-lookup"><span data-stu-id="86e6b-120">To view help for a different cmdlet, substitute **New-CsVoicePolicy** with the name of the cmdlet for which you want to retrieve help.</span></span>
  
<span data-ttu-id="86e6b-121">若要检索可用于管理 Skype for Business Server 的 cmdlet 的完整列表，在命令行管理程序命令提示符中键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="86e6b-121">To retrieve a full list of cmdlets available for managing Skype for Business Server, type the following at the shell command prompt:</span></span> 
  
```PowerShell
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



<span data-ttu-id="86e6b-122">有关 Skype for Business Server Windows PowerShell的信息：</span><span class="sxs-lookup"><span data-stu-id="86e6b-122">Things to know about Windows PowerShell in Skype for Business Server:</span></span>
  
- <span data-ttu-id="86e6b-123">若要运行 Skype for Business Server cmdlet，请打开 Skype for Business Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="86e6b-123">To run the Skype for Business Server cmdlets, open the Skype for Business Server Management Shell.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="86e6b-124">如果打开Windows PowerShell窗口，而不是 Skype for Business Server 命令行管理程序，则默认情况下可能无法运行 Skype cmdlet。</span><span class="sxs-lookup"><span data-stu-id="86e6b-124">If you open a Windows PowerShell window rather than the Skype for Business Server Management Shell, by default you may not be able to run the Skype cmdlets.</span></span> <span data-ttu-id="86e6b-125">若要从内部运行 Skype for Business Server cmdlet Windows PowerShell，首先在命令提示符Windows PowerShell键入以下内容：>  `Import-Module SkypeforBusiness`</span><span class="sxs-lookup"><span data-stu-id="86e6b-125">To run Skype for Business Server cmdlets from within Windows PowerShell, first type the following at the Windows PowerShell command prompt: >  `Import-Module SkypeforBusiness`</span></span>
  
- <span data-ttu-id="86e6b-126">Skype for Business Server 命令行管理程序会自动安装在每个 Skype for Business Server Enterprise Edition 前端服务器或 Standard Edition 服务器上。</span><span class="sxs-lookup"><span data-stu-id="86e6b-126">Skype for Business Server Management Shell is automatically installed on every Skype for Business Server Enterprise Edition Front End Server or Standard Edition server.</span></span>
    
- <span data-ttu-id="86e6b-127">可以通过运行 [Update-Help](/powershell/module/microsoft.powershell.core/update-help) cmdlet 来更新 Skype for Business Server 命令行管理程序帮助内容。</span><span class="sxs-lookup"><span data-stu-id="86e6b-127">You can update the Skype for Business Server Management Shell help content by running the [Update-Help](/powershell/module/microsoft.powershell.core/update-help) cmdlet.</span></span> <span data-ttu-id="86e6b-128">the Update-Help cmdlet downloads and installs the new help files available for all the modules installed on your computer， including updates to Skype for Business cmdlets.</span><span class="sxs-lookup"><span data-stu-id="86e6b-128">The Update-Help cmdlet downloads and installs the newest help files available for all of the modules installed on your computer, including updates to Skype for Business cmdlets.</span></span>
    
    <span data-ttu-id="86e6b-129">默认情况下 **，Update-Help** cmdlet 将更新安装在 Skype for Business Server 上的所有模块。</span><span class="sxs-lookup"><span data-stu-id="86e6b-129">By default, the **Update-Help** cmdlet will update all the modules installed on your Skype for Business Server.</span></span> <span data-ttu-id="86e6b-130">如果只想更新某些模块，可以使用 _Module_ 参数来限制 cmdlet 的范围。</span><span class="sxs-lookup"><span data-stu-id="86e6b-130">If you want to update only certain modules, you can use the _Module_ parameter to limit the scope of the cmdlet.</span></span> <span data-ttu-id="86e6b-131">以下示例仅更新 Skype for Business 模块。</span><span class="sxs-lookup"><span data-stu-id="86e6b-131">The following example updates only the Skype for Business module.</span></span>
    
  ```PowerShell
  Update-Help -Module SkypeforBusiness
  ```

    <span data-ttu-id="86e6b-132">如果需要更新未连接到 Internet 的服务器的"帮助"，可以使用 [Save-Help](/powershell/module/microsoft.powershell.core/save-help) cmdlet 获取最新版本的帮助，并将其保存到指定的位置。</span><span class="sxs-lookup"><span data-stu-id="86e6b-132">If you need to update the Help on servers that are not connected to the internet, you can use the [Save-Help](/powershell/module/microsoft.powershell.core/save-help) cmdlet to get the latest version of the help and save it to a location you specify.</span></span> <span data-ttu-id="86e6b-133">然后，可以在未连接到 Internet 的服务器上将 **Update-Help** cmdlet 与 _-SourcePath_ 参数一同使用，从所选位置获取更新的帮助。</span><span class="sxs-lookup"><span data-stu-id="86e6b-133">You can then use the **Update-Help** cmdlet with the _-SourcePath_ parameter on servers not connected to the internet to get the updated help from the location you selected.</span></span> <span data-ttu-id="86e6b-134">以下示例演示如何将帮助文件保存到网络文件共享，然后从文件共享更新 Skype for Business 模块的帮助。</span><span class="sxs-lookup"><span data-stu-id="86e6b-134">The following example shows how to save the help files to a network file share, and then update the help for the Skype for Business module from the file share.</span></span>
    
  ```PowerShell
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
  // Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    <span data-ttu-id="86e6b-135">有关更多详细信息，请参阅关于 [可更新的帮助](/powershell/module/microsoft.powershell.core/about/about_updatable_help)。</span><span class="sxs-lookup"><span data-stu-id="86e6b-135">For more detailed information, see [About Updatable Help](/powershell/module/microsoft.powershell.core/about/about_updatable_help).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="86e6b-136">如果远程使用 PowerShell，可能需要允许通过防火墙通信。</span><span class="sxs-lookup"><span data-stu-id="86e6b-136">If you are using PowerShell remotely you may need to allow communication through a firewall.</span></span> <span data-ttu-id="86e6b-137">若要详细了解 PowerShell 远程处理使用的端口，请参阅 What [Port Does PowerShell Remoting Use？。](/archive/blogs/christwe/what-port-does-powershell-remoting-use)</span><span class="sxs-lookup"><span data-stu-id="86e6b-137">To learn more about the ports PowerShell remoting uses, see [What Port Does PowerShell Remoting Use?](/archive/blogs/christwe/what-port-does-powershell-remoting-use).</span></span>
