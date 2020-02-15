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
# <a name="skype-for-business-server-management-shell"></a><span data-ttu-id="542b5-104">Skype for Business Server 命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="542b5-104">Skype for Business Server Management Shell</span></span>
 
<span data-ttu-id="542b5-105">Skype for Business Server 命令行管理程序提供了用于服务器管理和管理的命令行界面。</span><span class="sxs-lookup"><span data-stu-id="542b5-105">The Skype for Business Server Management Shell provides the command line interface for server administration and management.</span></span> <span data-ttu-id="542b5-106">它建立在 Windows PowerShell 之上，包括一套全面的针对 Skype 和旧版 Lync server 产品的管理和管理 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="542b5-106">It is built on Windows PowerShell and includes a comprehensive set of management and administration cmdlets that are specific to Skype and legacy Lync server products.</span></span>
  
<span data-ttu-id="542b5-107">Windows PowerShell 允许您从命令行管理 Microsoft 应用程序。</span><span class="sxs-lookup"><span data-stu-id="542b5-107">Windows PowerShell allows you to manage Microsoft applications from the command line.</span></span> <span data-ttu-id="542b5-108">它包括命令行环境、特定于产品的命令和完整的脚本语言。</span><span class="sxs-lookup"><span data-stu-id="542b5-108">It includes a command-line environment, product-specific commands, and a full scripting language.</span></span> <span data-ttu-id="542b5-109">Windows PowerShell 首次被引入为2006中的 Windows 操作系统的可下载版本，并被合并为 Microsoft Exchange Server 2007 的可管理性的命令行界面。</span><span class="sxs-lookup"><span data-stu-id="542b5-109">Windows PowerShell was first introduced as a downloadable release for the Windows operating system late in 2006, and was incorporated as the command-line interface for manageability of Microsoft Exchange Server 2007.</span></span> <span data-ttu-id="542b5-110">它已合并到大多数 Microsoft 服务器产品中，包括从 Lync Server 2010 开始的 Lync 和 Skype 服务器。</span><span class="sxs-lookup"><span data-stu-id="542b5-110">It has been incorporated into most of the Microsoft Server products, including Lync and Skype servers beginning with Lync Server 2010.</span></span> <span data-ttu-id="542b5-111">Skype for Business Server 命令行管理程序中提供了700以上的 Lync 和 Skype 特定 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="542b5-111">There are over 700 Lync and Skype specific cmdlets available in the Skype for Business Server Management Shell.</span></span>
  
> [!NOTE]
> <span data-ttu-id="542b5-112">Skype for Business cmdlet reference 已移动到 docs.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="542b5-112">Skype for Business cmdlet reference has moved to docs.microsoft.com.</span></span> <span data-ttu-id="542b5-113">单击下面的链接将转到新的 docs.microsoft.com 页面。</span><span class="sxs-lookup"><span data-stu-id="542b5-113">Clicking on the links below will take you to the new docs.microsoft.com page.</span></span> <span data-ttu-id="542b5-114">现在，内容是开放的，可用于通过 GitHub 进行社区贡献。</span><span class="sxs-lookup"><span data-stu-id="542b5-114">The content is now open sourced and available for community contributions through GitHub.</span></span> <span data-ttu-id="542b5-115">对所做的贡献有兴趣？</span><span class="sxs-lookup"><span data-stu-id="542b5-115">Interested in contributing?</span></span> <span data-ttu-id="542b5-116">查看存储库中的自述文件：[https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)</span><span class="sxs-lookup"><span data-stu-id="542b5-116">Check out the README in the repo here: [https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)</span></span>
  
<span data-ttu-id="542b5-117">Skype for Business Server 随附700个以上的 cmdlet，使管理员能够使用 Skype for Business Server 命令行管理程序管理 Skype for business Server。</span><span class="sxs-lookup"><span data-stu-id="542b5-117">Skype for Business Server ships with more than 700 cmdlets that enable administrators to manage Skype for Business Server using the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="542b5-118">您可以通过键入类似如下的命令，直接从命令行检索有关 cmdlet 的帮助：</span><span class="sxs-lookup"><span data-stu-id="542b5-118">You can retrieve help for a cmdlet directly from the command line by typing a command similar to the following:</span></span>
  
```PowerShell
Get-Help New-CsVoicePolicy -Full
```

<span data-ttu-id="542b5-119">上述命令检索提供的有关 **New-CsVoicePolicy** cmdlet 的完整帮助。</span><span class="sxs-lookup"><span data-stu-id="542b5-119">The preceding command retrieves the complete help available for the **New-CsVoicePolicy** cmdlet.</span></span> <span data-ttu-id="542b5-120">要查看其他 cmdlet 的帮助，请将 **New-CsVoicePolicy** 替换为要检索其帮助信息的 cmdlet 的名称。</span><span class="sxs-lookup"><span data-stu-id="542b5-120">To view help for a different cmdlet, substitute **New-CsVoicePolicy** with the name of the cmdlet for which you want to retrieve help.</span></span>
  
<span data-ttu-id="542b5-121">若要检索可用于管理 Skype for Business Server 的 cmdlet 的完整列表，请在命令行管理程序命令提示符处键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="542b5-121">To retrieve a full list of cmdlets available for managing Skype for Business Server, type the following at the shell command prompt:</span></span> 
  
```PowerShell
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



<span data-ttu-id="542b5-122">有关在 Skype for Business Server 中了解 Windows PowerShell 的事项：</span><span class="sxs-lookup"><span data-stu-id="542b5-122">Things to know about Windows PowerShell in Skype for Business Server:</span></span>
  
- <span data-ttu-id="542b5-123">若要运行 Skype for Business Server cmdlet，请打开 Skype for Business Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="542b5-123">To run the Skype for Business Server cmdlets, open the Skype for Business Server Management Shell.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="542b5-124">如果打开的是 Windows PowerShell 窗口而不是 Skype for Business Server 命令行管理程序，默认情况下，你可能无法运行 Skype cmdlet。</span><span class="sxs-lookup"><span data-stu-id="542b5-124">If you open a Windows PowerShell window rather than the Skype for Business Server Management Shell, by default you may not be able to run the Skype cmdlets.</span></span> <span data-ttu-id="542b5-125">若要从 Windows PowerShell 中运行 Skype for Business Server cmdlet，请首先在 Windows PowerShell 命令提示符处键入以下命令： >`Import-Module SkypeforBusiness`</span><span class="sxs-lookup"><span data-stu-id="542b5-125">To run Skype for Business Server cmdlets from within Windows PowerShell, first type the following at the Windows PowerShell command prompt: >  `Import-Module SkypeforBusiness`</span></span>
  
- <span data-ttu-id="542b5-126">Skype for business Server 命令行管理程序将自动安装在每个 Skype for Business Server Enterprise Edition 前端服务器或 Standard Edition server 上。</span><span class="sxs-lookup"><span data-stu-id="542b5-126">Skype for Business Server Management Shell is automatically installed on every Skype for Business Server Enterprise Edition Front End Server or Standard Edition server.</span></span>
    
- <span data-ttu-id="542b5-127">您可以通过运行[update-help](https://technet.microsoft.com/library/hh849720.aspx) cmdlet 来更新 Skype For Business Server 命令行管理程序帮助内容。</span><span class="sxs-lookup"><span data-stu-id="542b5-127">You can update the Skype for Business Server Management Shell help content by running the [Update-Help](https://technet.microsoft.com/library/hh849720.aspx) cmdlet.</span></span> <span data-ttu-id="542b5-128">Update-help cmdlet 下载并安装适用于您的计算机上安装的所有模块的最新帮助文件，包括对 Skype for Business cmdlet 的更新。</span><span class="sxs-lookup"><span data-stu-id="542b5-128">The Update-Help cmdlet downloads and installs the newest help files available for all of the modules installed on your computer, including updates to Skype for Business cmdlets.</span></span>
    
    <span data-ttu-id="542b5-129">默认情况下， **update-help** cmdlet 将更新安装在 Skype For business 服务器上的所有模块。</span><span class="sxs-lookup"><span data-stu-id="542b5-129">By default, the **Update-Help** cmdlet will update all the modules installed on your Skype for Business Server.</span></span> <span data-ttu-id="542b5-130">如果只想更新某些模块，可以使用_Module_参数来限制 cmdlet 的作用域。</span><span class="sxs-lookup"><span data-stu-id="542b5-130">If you want to update only certain modules, you can use the _Module_ parameter to limit the scope of the cmdlet.</span></span> <span data-ttu-id="542b5-131">以下示例仅更新 Skype for Business 模块。</span><span class="sxs-lookup"><span data-stu-id="542b5-131">The following example updates only the Skype for Business module.</span></span>
    
  ```PowerShell
  Update-Help -Module SkypeforBusiness
  ```

    <span data-ttu-id="542b5-132">如果需要更新未连接到 internet 的服务器上的帮助，可以使用[Save-Help](https://technet.microsoft.com/library/hh849724.aspx) cmdlet 获取帮助的最新版本，并将其保存到指定的位置。</span><span class="sxs-lookup"><span data-stu-id="542b5-132">If you need to update the Help on servers that are not connected to the internet, you can use the [Save-Help](https://technet.microsoft.com/library/hh849724.aspx) cmdlet to get the latest version of the help and save it to a location you specify.</span></span> <span data-ttu-id="542b5-133">然后，您可以在未连接到 internet 的服务器上使用带有 _-SourcePath_参数的**update-help** cmdlet，从所选位置获取更新的帮助。</span><span class="sxs-lookup"><span data-stu-id="542b5-133">You can then use the **Update-Help** cmdlet with the _-SourcePath_ parameter on servers not connected to the internet to get the updated help from the location you selected.</span></span> <span data-ttu-id="542b5-134">下面的示例演示如何将帮助文件保存到网络文件共享，然后从文件共享中更新 Skype for Business 模块的帮助。</span><span class="sxs-lookup"><span data-stu-id="542b5-134">The following example shows how to save the help files to a network file share, and then update the help for the Skype for Business module from the file share.</span></span>
    
  ```PowerShell
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
  // Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    <span data-ttu-id="542b5-135">有关更多详细信息，请参阅[关于可更新帮助](https://technet.microsoft.com/library/hh847735.aspx)。</span><span class="sxs-lookup"><span data-stu-id="542b5-135">For more detailed information, see [About Updatable Help](https://technet.microsoft.com/library/hh847735.aspx).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="542b5-136">如果你远程使用 PowerShell，可能需要允许通过防火墙进行通信。</span><span class="sxs-lookup"><span data-stu-id="542b5-136">If you are using PowerShell remotely you may need to allow communication through a firewall.</span></span> <span data-ttu-id="542b5-137">若要了解有关 PowerShell 远程使用的端口的详细信息，请参阅[Powershell Remoting 使用什么端口？](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/)。</span><span class="sxs-lookup"><span data-stu-id="542b5-137">To learn more about the ports PowerShell remoting uses, see [What Port Does PowerShell Remoting Use?](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/).</span></span>
    

