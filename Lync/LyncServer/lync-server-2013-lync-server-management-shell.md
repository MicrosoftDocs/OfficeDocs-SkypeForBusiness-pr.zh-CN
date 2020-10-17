---
title: Lync Server 2013： Lync Server 命令行管理程序
description: Lync Server 2013： Lync Server 命令行管理程序。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server Management Shell
ms:assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398474(v=OCS.15)
ms:contentKeyID: 48184386
ms.date: 09/20/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45727c42899defcf20ce36e2a27a9268a52ecd71
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543178"
---
# <a name="lync-server-2013-management-shell"></a><span data-ttu-id="188d1-103">Lync Server 2013 命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="188d1-103">Lync Server 2013 Management Shell</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="188d1-104">_**上次修改的主题：** 2017-09-20_</span><span class="sxs-lookup"><span data-stu-id="188d1-104">_**Topic Last Modified:** 2017-09-20_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="188d1-105">Skype for Business cmdlet reference 已移动到 docs.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="188d1-105">Skype for Business cmdlet reference has moved to docs.microsoft.com.</span></span> <span data-ttu-id="188d1-106">单击下面的链接将转到新的 docs.microsoft.com 页面。</span><span class="sxs-lookup"><span data-stu-id="188d1-106">Clicking on the links below will take you to the new docs.microsoft.com page.</span></span> <span data-ttu-id="188d1-107">现在，内容是开放的，可用于通过 GitHub 进行社区贡献。</span><span class="sxs-lookup"><span data-stu-id="188d1-107">The content is now open sourced and available for community contributions through GitHub.</span></span> <span data-ttu-id="188d1-108">对所做的贡献有兴趣？</span><span class="sxs-lookup"><span data-stu-id="188d1-108">Interested in contributing?</span></span> <span data-ttu-id="188d1-109">查看存储库中的自述文件： <A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A></span><span class="sxs-lookup"><span data-stu-id="188d1-109">Check out the README in the repo here: <A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A></span></span>



</div>

<span data-ttu-id="188d1-110">Microsoft Lync Server 2010 引入了一组大型的新的和改进的功能，与 Microsoft Office 通信服务器 2007 R2 中提供的功能相比。</span><span class="sxs-lookup"><span data-stu-id="188d1-110">Microsoft Lync Server 2010 introduced a large set of new and improved features compared to what was available in Microsoft Office Communications Server 2007 R2.</span></span> <span data-ttu-id="188d1-111">其中一项改进是管理实现的方法。</span><span class="sxs-lookup"><span data-stu-id="188d1-111">One improvement is the way in which you manage your implementation.</span></span> <span data-ttu-id="188d1-112">例如，有一个新的用户界面（称为 "Lync Server 控制面板"），它表示在 Microsoft 管理控制台中使用最多的人的巨大转变。</span><span class="sxs-lookup"><span data-stu-id="188d1-112">For example, there’s a new user interface, called the Lync Server Control Panel, which represents a big shift from what most people are used to with the Microsoft Management Console.</span></span> <span data-ttu-id="188d1-113">可管理性的另一个主要改进是包含 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="188d1-113">The other major improvement to manageability is the inclusion of Windows PowerShell.</span></span>

<span data-ttu-id="188d1-114">Windows PowerShell 允许您从命令行管理 Microsoft 应用程序。</span><span class="sxs-lookup"><span data-stu-id="188d1-114">Windows PowerShell allows you to manage Microsoft applications from the command line.</span></span> <span data-ttu-id="188d1-115">它包括命令行环境、特定于产品的命令和完整的脚本语言。</span><span class="sxs-lookup"><span data-stu-id="188d1-115">It includes a command-line environment, product-specific commands, and a full scripting language.</span></span> <span data-ttu-id="188d1-116">Windows PowerShell 首次被引入为2006中的 Windows 操作系统的可下载版本，并被合并为 Microsoft Exchange Server 2007 的可管理性的命令行界面。</span><span class="sxs-lookup"><span data-stu-id="188d1-116">Windows PowerShell was first introduced as a downloadable release for the Windows operating system late in 2006, and was incorporated as the command-line interface for manageability of Microsoft Exchange Server 2007.</span></span> <span data-ttu-id="188d1-117">从那一开始，它将继续增长，并已合并到大多数 Microsoft Server 产品中，这是 Microsoft Lync Server 2013 的最新产品。</span><span class="sxs-lookup"><span data-stu-id="188d1-117">From that point it continued to grow, and it has been incorporated into most of the Microsoft Server products, the most recent of these being Microsoft Lync Server 2013.</span></span> <span data-ttu-id="188d1-118">Lync Server 2010 引入了接近550个产品的特定 cmdlet，您可以使用这些 cmdlet 来管理您的部署的各个方面。</span><span class="sxs-lookup"><span data-stu-id="188d1-118">Lync Server 2010 introduced close to 550 product-specific cmdlets that you can use to manage every aspect of your deployment.</span></span>

<span data-ttu-id="188d1-119">以下各节包含 cmdlet 及其说明的列表。</span><span class="sxs-lookup"><span data-stu-id="188d1-119">The following sections contain a list of cmdlets and their descriptions.</span></span> <span data-ttu-id="188d1-120">也可直接从命令行获取此信息。</span><span class="sxs-lookup"><span data-stu-id="188d1-120">This information is also available directly from the command line.</span></span> <span data-ttu-id="188d1-121">只需在 Lync Server 命令行管理程序命令提示符处键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="188d1-121">Simply type the following at the Lync Server Management Shell command prompt:</span></span>

    Get-Help <cmdlet name> -Full

<span data-ttu-id="188d1-122">例如，要通过命令提示符检索有关 **New-CsVoicePolicy** cmdlet 的帮助，请键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="188d1-122">For example, to retrieve help from the command prompt on the **New-CsVoicePolicy** cmdlet, type the following:</span></span>

    Get-Help New-CsVoicePolicy -Full

<span data-ttu-id="188d1-123">有关在 Lync Server 2013 中了解 Windows PowerShell 的事项：</span><span class="sxs-lookup"><span data-stu-id="188d1-123">Things to know about Windows PowerShell in Lync Server 2013:</span></span>

  - <span data-ttu-id="188d1-124">若要运行 Lync Server cmdlet，请打开 Lync Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="188d1-124">To run the Lync Server cmdlets, open the Lync Server Management Shell.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="188d1-125">如果打开的是 Windows PowerShell 窗口而不是 Lync Server 命令行管理程序，则默认情况下将无法运行 Lync Server cmdlet。</span><span class="sxs-lookup"><span data-stu-id="188d1-125">If you open a Windows PowerShell window rather than the Lync Server Management Shell, by default you will not be able to run the Lync Server cmdlets.</span></span> <span data-ttu-id="188d1-126">若要从 Windows PowerShell 中运行 Lync Server cmdlet，请首先在 Windows PowerShell 命令提示符处键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="188d1-126">To run the Lync Server cmdlets from within Windows PowerShell, first type the following at the Windows PowerShell command prompt:</span></span><BR><span data-ttu-id="188d1-127">Import-Module Lync</span><span class="sxs-lookup"><span data-stu-id="188d1-127">Import-Module Lync</span></span>

    
    </div>

  - <span data-ttu-id="188d1-128">Lync Server 命令行管理程序将自动安装在每个 Lync Server Enterprise Edition 前端服务器或 Standard Edition server 上。</span><span class="sxs-lookup"><span data-stu-id="188d1-128">Lync Server Management Shell is automatically installed on every Lync Server Enterprise Edition Front End Server or Standard Edition server.</span></span>

  - <span data-ttu-id="188d1-129">Lync Server Windows PowerShell 博客中提供了新的和更新的信息、示例脚本和帮助，以了解有关 Windows PowerShell 和 Microsoft Lync Server 2013 cmdlet 的入门和帮助 [https://go.microsoft.com/fwlink/p/?linkId=203150](https://go.microsoft.com/fwlink/p/?linkid=203150) 。</span><span class="sxs-lookup"><span data-stu-id="188d1-129">New and updated information, sample scripts, and help for getting started and learning more about Windows PowerShell and Microsoft Lync Server 2013 cmdlets is available at the Lync Server Windows PowerShell Blog [https://go.microsoft.com/fwlink/p/?linkId=203150](https://go.microsoft.com/fwlink/p/?linkid=203150).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

