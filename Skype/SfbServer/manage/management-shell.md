---
title: Skype for Business Server 管理程序
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
description: 业务 Server 命令行管理程序 Skype 服务器管理和管理提供命令行界面。 它基于 Windows PowerShell，并包含一组全面的管理和管理特定于 Skype 和旧式 Lync server 产品的 cmdlet。
ms.openlocfilehash: 243ff7a684bb14f73ef9f4836ce00e8048fbb236
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199229"
---
# <a name="skype-for-business-server-management-shell"></a><span data-ttu-id="63807-104">Skype for Business Server 管理程序</span><span class="sxs-lookup"><span data-stu-id="63807-104">Skype for Business Server Management Shell</span></span>
 
<span data-ttu-id="63807-105">业务 Server 命令行管理程序 Skype 服务器管理和管理提供命令行界面。</span><span class="sxs-lookup"><span data-stu-id="63807-105">The Skype for Business Server Management Shell provides the command line interface for server administration and management.</span></span> <span data-ttu-id="63807-106">它基于 Windows PowerShell，并包含一组全面的管理和管理特定于 Skype 和旧式 Lync server 产品的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="63807-106">It is built on Windows PowerShell and includes a comprehensive set of management and administration cmdlets that are specific to Skype and legacy Lync server products.</span></span>
  
<span data-ttu-id="63807-107">Windows PowerShell，可以从命令行管理 Microsoft 应用程序。</span><span class="sxs-lookup"><span data-stu-id="63807-107">Windows PowerShell allows you to manage Microsoft applications from the command line.</span></span> <span data-ttu-id="63807-108">它包括命令行环境、特定于产品的命令和完整的脚本语言。</span><span class="sxs-lookup"><span data-stu-id="63807-108">It includes a command-line environment, product-specific commands, and a full scripting language.</span></span> <span data-ttu-id="63807-109">Windows PowerShell 首次引入的 Windows 操作系统的可下载版本作为最晚在 2006 年，并已合并为可管理性的 Microsoft Exchange Server 2007 的命令行接口。</span><span class="sxs-lookup"><span data-stu-id="63807-109">Windows PowerShell was first introduced as a downloadable release for the Windows operating system late in 2006, and was incorporated as the command-line interface for manageability of Microsoft Exchange Server 2007.</span></span> <span data-ttu-id="63807-110">它已合并到大多数 Microsoft 服务器产品，包括 Lync 和 Skype 开头 Lync Server 2010 的服务器。</span><span class="sxs-lookup"><span data-stu-id="63807-110">It has been incorporated into most of the Microsoft Server products, including Lync and Skype servers beginning with Lync Server 2010.</span></span> <span data-ttu-id="63807-111">Skype 的业务 Server 命令行管理程序中提供了 700 Lync 和 Skype 的特定 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="63807-111">There are over 700 Lync and Skype specific cmdlets available in the Skype for Business Server Management Shell.</span></span>
  
> [!NOTE]
> <span data-ttu-id="63807-112">Skype for Business cmdlet 参考已移至 docs.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="63807-112">Skype for Business cmdlet reference has moved to docs.microsoft.com.</span></span> <span data-ttu-id="63807-113">单击下面的链接将转至新的 docs.microsoft.com 页面。</span><span class="sxs-lookup"><span data-stu-id="63807-113">Clicking on the links below will take you to the new docs.microsoft.com page.</span></span> <span data-ttu-id="63807-114">内容现在是开源的，可通过 GitHub 用于社区投稿。</span><span class="sxs-lookup"><span data-stu-id="63807-114">The content is now open sourced and available for community contributions through GitHub.</span></span> <span data-ttu-id="63807-115">对投稿感兴趣？</span><span class="sxs-lookup"><span data-stu-id="63807-115">Interested in contributing?</span></span> <span data-ttu-id="63807-116">查看自述文件在此处 repo 中：[https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)</span><span class="sxs-lookup"><span data-stu-id="63807-116">Check out the README in the repo here: [https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)</span></span>
  
<span data-ttu-id="63807-117">Skype 业务服务器附带使管理员能够管理对业务 Server 命令行管理程序中使用 Skype 的业务服务器 Skype 的多个 700 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="63807-117">Skype for Business Server ships with more than 700 cmdlets that enable administrators to manage Skype for Business Server using the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="63807-118">您可以通过键入以下类似命令，从命令行直接检索 cmdlet 的相关帮助：</span><span class="sxs-lookup"><span data-stu-id="63807-118">You can retrieve help for a cmdlet directly from the command line by typing a command similar to the following:</span></span>
  
```
Get-Help New-CsVoicePolicy -Full
```

<span data-ttu-id="63807-119">上述命令检索有关 **New-CsVoicePolicy** cmdlet 的可用完整帮助。</span><span class="sxs-lookup"><span data-stu-id="63807-119">The preceding command retrieves the complete help available for the **New-CsVoicePolicy** cmdlet.</span></span> <span data-ttu-id="63807-120">要查看其他 cmdlet 的帮助，请将 **New-CsVoicePolicy** 替换为要检索其帮助信息的 cmdlet 的名称。</span><span class="sxs-lookup"><span data-stu-id="63807-120">To view help for a different cmdlet, substitute **New-CsVoicePolicy** with the name of the cmdlet for which you want to retrieve help.</span></span>
  
<span data-ttu-id="63807-121">要检索可用于管理 Skype for Business Server 的 cmdlet 的完整列表，请在 Shell 命令提示符处键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="63807-121">To retrieve a full list of cmdlets available for managing Skype for Business Server, type the following at the shell command prompt:</span></span> 
  
```
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



<span data-ttu-id="63807-122">项关键须知 Skype 中的 Windows PowerShell 业务服务器：</span><span class="sxs-lookup"><span data-stu-id="63807-122">Things to know about Windows PowerShell in Skype for Business Server:</span></span>
  
- <span data-ttu-id="63807-123">若要运行 Business Server cmdlet Skype，打开 Skype 业务 Server Management Shell。</span><span class="sxs-lookup"><span data-stu-id="63807-123">To run the Skype for Business Server cmdlets, open the Skype for Business Server Management Shell.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="63807-124">如果您的业务 Server 命令行管理程序中打开 Windows PowerShell 窗口而不是 Skype 后，默认情况下您可能无法运行的 Skype cmdlet。</span><span class="sxs-lookup"><span data-stu-id="63807-124">If you open a Windows PowerShell window rather than the Skype for Business Server Management Shell, by default you may not be able to run the Skype cmdlets.</span></span> <span data-ttu-id="63807-125">若要运行 Skype 的业务 Server cmdlet 从 Windows PowerShell 中，首先键入以下 Windows PowerShell 命令提示符处： >`Import-Module SkypeforBusiness`</span><span class="sxs-lookup"><span data-stu-id="63807-125">To run Skype for Business Server cmdlets from within Windows PowerShell, first type the following at the Windows PowerShell command prompt: >  `Import-Module SkypeforBusiness`</span></span>
  
- <span data-ttu-id="63807-126">每个 Skype 业务 Server Enterprise Edition 前端服务器或 Standard Edition server 上自动安装 Business Server Management Shell 的 Skype。</span><span class="sxs-lookup"><span data-stu-id="63807-126">Skype for Business Server Management Shell is automatically installed on every Skype for Business Server Enterprise Edition Front End Server or Standard Edition server.</span></span>
    
- <span data-ttu-id="63807-127">您可以通过运行[更新帮助](https://technet.microsoft.com/en-us/library/hh849720.aspx)cmdlet 更新业务 Server 命令行管理程序帮助内容 Skype。</span><span class="sxs-lookup"><span data-stu-id="63807-127">You can update the Skype for Business Server Management Shell help content by running the [Update-Help](https://technet.microsoft.com/en-us/library/hh849720.aspx) cmdlet.</span></span> <span data-ttu-id="63807-128">更新帮助 cmdlet 下载并安装的最新帮助文件提供的所有模块包括 Skype 业务 cmdlet 更新您计算机上安装。</span><span class="sxs-lookup"><span data-stu-id="63807-128">The Update-Help cmdlet downloads and installs the newest help files available for all of the modules installed on your computer, including updates to Skype for Business cmdlets.</span></span>
    
    <span data-ttu-id="63807-129">默认情况下，**更新帮助**cmdlet 将更新业务服务器安装在您 Skype 上的所有模块。</span><span class="sxs-lookup"><span data-stu-id="63807-129">By default, the **Update-Help** cmdlet will update all the modules installed on your Skype for Business Server.</span></span> <span data-ttu-id="63807-130">如果您想仅更新特定模块，则可以使用 _Module_ 参数来限制 cmdlet 的作用域。</span><span class="sxs-lookup"><span data-stu-id="63807-130">If you want to update only certain modules, you can use the _Module_ parameter to limit the scope of the cmdlet.</span></span> <span data-ttu-id="63807-131">下面的示例更新仅 for Business 模块 Skype。</span><span class="sxs-lookup"><span data-stu-id="63807-131">The following example updates only the Skype for Business module.</span></span>
    
  ```
  Update-Help -Module SkypeforBusiness
  ```

    <span data-ttu-id="63807-132">如果您需要更新的帮助未连接到 internet 的服务器上，您可以使用[保存帮助](https://technet.microsoft.com/en-us/library/hh849724.aspx)cmdlet 获取帮助的最新版本，并将其保存到您指定的位置。</span><span class="sxs-lookup"><span data-stu-id="63807-132">If you need to update the Help on servers that are not connected to the internet, you can use the [Save-Help](https://technet.microsoft.com/en-us/library/hh849724.aspx) cmdlet to get the latest version of the help and save it to a location you specify.</span></span> <span data-ttu-id="63807-133">然后可以使用 _-SourcePath_参数未连接到 internet 的服务器上使用**更新帮助**cmdlet 获取所选的位置更新的帮助。</span><span class="sxs-lookup"><span data-stu-id="63807-133">You can then use the **Update-Help** cmdlet with the _-SourcePath_ parameter on servers not connected to the internet to get the updated help from the location you selected.</span></span> <span data-ttu-id="63807-134">下面的示例演示如何帮助文件保存到网络文件共享，然后更新从文件共享的业务模块 Skype 的帮助。</span><span class="sxs-lookup"><span data-stu-id="63807-134">The following example shows how to save the help files to a network file share, and then update the help for the Skype for Business module from the file share.</span></span>
    
  ```
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
  // Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    <span data-ttu-id="63807-135">有关详细信息，请参阅[有关可更新帮助](https://technet.microsoft.com/library/hh847735.aspx)。</span><span class="sxs-lookup"><span data-stu-id="63807-135">For more detailed information, see [About Updatable Help](https://technet.microsoft.com/library/hh847735.aspx).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="63807-136">如果您使用的 PowerShell 远程您可能需要允许通过防火墙的通信。</span><span class="sxs-lookup"><span data-stu-id="63807-136">If you are using PowerShell remotely you may need to allow communication through a firewall.</span></span> <span data-ttu-id="63807-137">若要了解有关 PowerShell 远程处理使用的端口的详细信息，请参阅[哪些端口不 PowerShell 远程处理使用？](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/)。</span><span class="sxs-lookup"><span data-stu-id="63807-137">To learn more about the ports PowerShell remoting uses, see [What Port Does PowerShell Remoting Use?](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/).</span></span>
    

