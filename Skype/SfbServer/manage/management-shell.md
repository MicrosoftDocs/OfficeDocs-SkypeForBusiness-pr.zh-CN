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
# <a name="skype-for-business-server-2015-management-shell"></a><span data-ttu-id="5b13f-104">Skype for Business Server 2015 命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="5b13f-104">Skype for Business Server 2015 Management Shell</span></span>
 
<span data-ttu-id="5b13f-105">Skype 的业务服务器管理外壳程序提供命令行界面的服务器管理和管理。</span><span class="sxs-lookup"><span data-stu-id="5b13f-105">The Skype for Business Server Management Shell provides the command line interface for server administration and management.</span></span> <span data-ttu-id="5b13f-106">它构建在 Windows PowerShell，并包括一套全面的管理和管理特定于 Skype 和旧式 Lync 服务器产品的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="5b13f-106">It is built on Windows PowerShell and includes a comprehensive set of management and administration cmdlets that are specific to Skype and legacy Lync server products.</span></span>
  
<span data-ttu-id="5b13f-107">Windows PowerShell 允许您从命令行管理 Microsoft 应用程序。</span><span class="sxs-lookup"><span data-stu-id="5b13f-107">Windows PowerShell allows you to manage Microsoft applications from the command line.</span></span> <span data-ttu-id="5b13f-108">它包括命令行环境、特定于产品的命令和完整的脚本语言。</span><span class="sxs-lookup"><span data-stu-id="5b13f-108">It includes a command-line environment, product-specific commands, and a full scripting language.</span></span> <span data-ttu-id="5b13f-109">Windows PowerShell 最晚在 2006 年，第一次作为一个可下载版本 Windows 操作系统的引入，并纳入为 Microsoft Exchange Server 2007年的可管理性的命令行接口。</span><span class="sxs-lookup"><span data-stu-id="5b13f-109">Windows PowerShell was first introduced as a downloadable release for the Windows operating system late in 2006, and was incorporated as the command-line interface for manageability of Microsoft Exchange Server 2007.</span></span> <span data-ttu-id="5b13f-110">它已合并成包括 Lync 和 Skype 开头 Lync Server 2010 中的服务器的 Microsoft 服务器产品的大部分。</span><span class="sxs-lookup"><span data-stu-id="5b13f-110">It has been incorporated into most of the Microsoft Server products, including Lync and Skype servers beginning with Lync Server 2010.</span></span> <span data-ttu-id="5b13f-111">Skype 的业务服务器管理外壳程序中有 700 Lync 和 Skype 的特定 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="5b13f-111">There are over 700 Lync and Skype specific cmdlets available in the Skype for Business Server Management Shell.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5b13f-112">Skype 业务 cmdlet 引用移到 docs.microsoft.com。单击下面的链接将进入新的 docs.microsoft.com 页。</span><span class="sxs-lookup"><span data-stu-id="5b13f-112">Skype for Business cmdlet reference has moved to docs.microsoft.com. Clicking on the links below will take you to the new docs.microsoft.com page.</span></span> <span data-ttu-id="5b13f-113">内容现在是开源的，可通过 GitHub 用于社区投稿。</span><span class="sxs-lookup"><span data-stu-id="5b13f-113">The content is now open sourced and available for community contributions through GitHub.</span></span> <span data-ttu-id="5b13f-114">对投稿感兴趣？</span><span class="sxs-lookup"><span data-stu-id="5b13f-114">Interested in contributing?</span></span> <span data-ttu-id="5b13f-115">请查阅此处 repo 中的自述文件：[https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)</span><span class="sxs-lookup"><span data-stu-id="5b13f-115">Check out the README in the repo here: [https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)</span></span>
  
<span data-ttu-id="5b13f-116">Skype 的业务服务器 2015年附带使管理员能够管理的业务服务器的业务服务器管理外壳使用 Skype 的 Skype 的 700 多个 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="5b13f-116">Skype for Business Server 2015 ships with more than 700 cmdlets that enable administrators to manage Skype for Business Server using the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="5b13f-117">您可以通过键入以下类似命令，从命令行直接检索 cmdlet 的相关帮助：</span><span class="sxs-lookup"><span data-stu-id="5b13f-117">You can retrieve help for a cmdlet directly from the command line by typing a command similar to the following:</span></span>
  
```
Get-Help New-CsVoicePolicy -Full
```

<span data-ttu-id="5b13f-118">上面的命令检索可用于**新建 CsVoicePolicy** cmdlet 的完整帮助。</span><span class="sxs-lookup"><span data-stu-id="5b13f-118">The preceding command retrieves the complete help available for the **New-CsVoicePolicy** cmdlet.</span></span> <span data-ttu-id="5b13f-119">若要查看其他 cmdlet 的帮助，请替换为具有您要为其检索帮助该 cmdlet 名称**新建 CsVoicePolicy** 。</span><span class="sxs-lookup"><span data-stu-id="5b13f-119">To view help for a different cmdlet, substitute **New-CsVoicePolicy** with the name of the cmdlet for which you want to retrieve help.</span></span>
  
<span data-ttu-id="5b13f-120">要检索可用于管理 Skype for Business Server 的 cmdlet 的完整列表，请在 Shell 命令提示符处键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="5b13f-120">To retrieve a full list of cmdlets available for managing Skype for Business Server, type the following at the shell command prompt:</span></span> 
  
```
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



<span data-ttu-id="5b13f-121">了解 Windows PowerShell 在 Skype 业务服务器的注意事项：</span><span class="sxs-lookup"><span data-stu-id="5b13f-121">Things to know about Windows PowerShell in Skype for Business Server:</span></span>
  
- <span data-ttu-id="5b13f-122">若要运行业务服务器 cmdlet 的 Skype，业务服务器管理外壳程序打开 Skype。</span><span class="sxs-lookup"><span data-stu-id="5b13f-122">To run the Skype for Business Server cmdlets, open the Skype for Business Server Management Shell.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="5b13f-123">如果您打开 Windows PowerShell 窗口，而不是 Skype 业务服务器管理外壳，默认情况下您可能不能运行 Skype cmdlet。</span><span class="sxs-lookup"><span data-stu-id="5b13f-123">If you open a Windows PowerShell window rather than the Skype for Business Server Management Shell, by default you may not be able to run the Skype cmdlets.</span></span> <span data-ttu-id="5b13f-124">要运行 Skype 业务服务器 cmdlet 从 Windows PowerShell 中，首先键入以下 Windows PowerShell 命令提示符处： >`Import-Module SkypeforBusiness`</span><span class="sxs-lookup"><span data-stu-id="5b13f-124">To run Skype for Business Server cmdlets from within Windows PowerShell, first type the following at the Windows PowerShell command prompt: >  `Import-Module SkypeforBusiness`</span></span>
  
- <span data-ttu-id="5b13f-125">在每一个 Skype 业务服务器企业版前端服务器或标准版服务器上自动安装 Skype 的业务服务器管理程序。</span><span class="sxs-lookup"><span data-stu-id="5b13f-125">Skype for Business Server Management Shell is automatically installed on every Skype for Business Server Enterprise Edition Front End Server or Standard Edition server.</span></span>
    
- <span data-ttu-id="5b13f-126">您可以通过运行[更新帮助](https://technet.microsoft.com/en-us/library/hh849720.aspx)cmdlet 更新 Skype 业务服务器管理外壳程序帮助内容。</span><span class="sxs-lookup"><span data-stu-id="5b13f-126">You can update the Skype for Business Server Management Shell help content by running the [Update-Help](https://technet.microsoft.com/en-us/library/hh849720.aspx) cmdlet.</span></span> <span data-ttu-id="5b13f-127">更新帮助 cmdlet 下载并安装最新的帮助文件可用于所有模块包括 Skype 业务 cmdlet 的更新您计算机上安装。</span><span class="sxs-lookup"><span data-stu-id="5b13f-127">The Update-Help cmdlet downloads and installs the newest help files available for all of the modules installed on your computer, including updates to Skype for Business cmdlets.</span></span>
    
    <span data-ttu-id="5b13f-128">默认情况下，**更新帮助**cmdlet 将更新为业务服务器在您 Skype 上安装的所有模块。</span><span class="sxs-lookup"><span data-stu-id="5b13f-128">By default, the **Update-Help** cmdlet will update all the modules installed on your Skype for Business Server.</span></span> <span data-ttu-id="5b13f-129">如果您想要更新特定的模块，可以使用_模块_参数来限制该 cmdlet 的范围。</span><span class="sxs-lookup"><span data-stu-id="5b13f-129">If you want to update only certain modules, you can use the _Module_ parameter to limit the scope of the cmdlet.</span></span> <span data-ttu-id="5b13f-130">下面的示例更新仅 Skype 业务模块。</span><span class="sxs-lookup"><span data-stu-id="5b13f-130">The following example updates only the Skype for Business module.</span></span>
    
  ```
  Update-Help -Module SkypeforBusiness
  ```

    <span data-ttu-id="5b13f-131">如果您需要更新未连接到 internet 的服务器上的帮助，可以使用[保存帮助](https://technet.microsoft.com/en-us/library/hh849724.aspx)cmdlet 以获取最新版本的帮助，并将其保存到您指定的位置。</span><span class="sxs-lookup"><span data-stu-id="5b13f-131">If you need to update the Help on servers that are not connected to the internet, you can use the [Save-Help](https://technet.microsoft.com/en-us/library/hh849724.aspx) cmdlet to get the latest version of the help and save it to a location you specify.</span></span> <span data-ttu-id="5b13f-132">然后可以在未连接到 internet 的服务器上_的源路径_参数与使用**更新帮助**cmdlet 从您选定的位置获取更新的帮助。</span><span class="sxs-lookup"><span data-stu-id="5b13f-132">You can then use the **Update-Help** cmdlet with the _-SourcePath_ parameter on servers not connected to the internet to get the updated help from the location you selected.</span></span> <span data-ttu-id="5b13f-133">下面的示例演示如何将帮助文件保存到网络文件共享，然后更新该文件共享上的 Skype 业务模块的帮助。</span><span class="sxs-lookup"><span data-stu-id="5b13f-133">The following example shows how to save the help files to a network file share, and then update the help for the Skype for Business module from the file share.</span></span>
    
  ```
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
// Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    <span data-ttu-id="5b13f-134">有关更多详细信息，请参阅[关于更新帮助](https://technet.microsoft.com/library/hh847735.aspx)。</span><span class="sxs-lookup"><span data-stu-id="5b13f-134">For more detailed information, see [About Updatable Help](https://technet.microsoft.com/library/hh847735.aspx).</span></span>
    

