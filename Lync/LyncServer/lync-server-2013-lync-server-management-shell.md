---
title: Lync Server 2013： Lync Server 命令行管理程序
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
ms.openlocfilehash: d519b647eae4937af10a38673803484a253baef7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742182"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-management-shell"></a><span data-ttu-id="4776d-102">Lync Server 2013 命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="4776d-102">Lync Server 2013 Management Shell</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4776d-103">_**主题上次修改时间：** 2017-09-20_</span><span class="sxs-lookup"><span data-stu-id="4776d-103">_**Topic Last Modified:** 2017-09-20_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4776d-104">Skype for Business cmdlet 参考已移至 docs.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="4776d-104">Skype for Business cmdlet reference has moved to docs.microsoft.com.</span></span> <span data-ttu-id="4776d-105">单击下面的链接将转至新的 docs.microsoft.com 页面。</span><span class="sxs-lookup"><span data-stu-id="4776d-105">Clicking on the links below will take you to the new docs.microsoft.com page.</span></span> <span data-ttu-id="4776d-106">内容现在是开源的，可通过 GitHub 用于社区投稿。</span><span class="sxs-lookup"><span data-stu-id="4776d-106">The content is now open sourced and available for community contributions through GitHub.</span></span> <span data-ttu-id="4776d-107">对投稿感兴趣？</span><span class="sxs-lookup"><span data-stu-id="4776d-107">Interested in contributing?</span></span> <span data-ttu-id="4776d-108">查看存储库中的自述文件：<A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A></span><span class="sxs-lookup"><span data-stu-id="4776d-108">Check out the README in the repo here: <A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A></span></span>



</div>

<span data-ttu-id="4776d-109">Microsoft Lync Server 2010 引入了一组大型的新功能和改进功能，与 Microsoft Office 通信服务器 2007 R2 中的可用功能相比较。</span><span class="sxs-lookup"><span data-stu-id="4776d-109">Microsoft Lync Server 2010 introduced a large set of new and improved features compared to what was available in Microsoft Office Communications Server 2007 R2.</span></span> <span data-ttu-id="4776d-110">一个改进是你管理实现的方式。</span><span class="sxs-lookup"><span data-stu-id="4776d-110">One improvement is the way in which you manage your implementation.</span></span> <span data-ttu-id="4776d-111">例如，有一个新的用户界面，称为 Lync Server 控制面板，它表示与大多数人在 Microsoft 管理控制台中的最大转变。</span><span class="sxs-lookup"><span data-stu-id="4776d-111">For example, there’s a new user interface, called the Lync Server Control Panel, which represents a big shift from what most people are used to with the Microsoft Management Console.</span></span> <span data-ttu-id="4776d-112">易管理性的另一重大改进是包含 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="4776d-112">The other major improvement to manageability is the inclusion of Windows PowerShell.</span></span>

<span data-ttu-id="4776d-113">Windows PowerShell 允许你从命令行管理 Microsoft 应用程序。</span><span class="sxs-lookup"><span data-stu-id="4776d-113">Windows PowerShell allows you to manage Microsoft applications from the command line.</span></span> <span data-ttu-id="4776d-114">它包括命令行环境、特定于产品的命令和完整的脚本语言。</span><span class="sxs-lookup"><span data-stu-id="4776d-114">It includes a command-line environment, product-specific commands, and a full scripting language.</span></span> <span data-ttu-id="4776d-115">Windows PowerShell 第一次引入于2006中的 Windows 操作系统的可下载版本，并已被合并为 Microsoft Exchange Server 2007 的可管理性的命令行界面。</span><span class="sxs-lookup"><span data-stu-id="4776d-115">Windows PowerShell was first introduced as a downloadable release for the Windows operating system late in 2006, and was incorporated as the command-line interface for manageability of Microsoft Exchange Server 2007.</span></span> <span data-ttu-id="4776d-116">从此时起，它将持续增长，并已合并到大多数 Microsoft 服务器产品中，最新的是 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="4776d-116">From that point it continued to grow, and it has been incorporated into most of the Microsoft Server products, the most recent of these being Microsoft Lync Server 2013.</span></span> <span data-ttu-id="4776d-117">Lync Server 2010 引入了一些特定于550的特定 cmdlet，可用于管理你的部署的各个方面。</span><span class="sxs-lookup"><span data-stu-id="4776d-117">Lync Server 2010 introduced close to 550 product-specific cmdlets that you can use to manage every aspect of your deployment.</span></span>

<span data-ttu-id="4776d-118">以下各节包含 cmdlet 及其说明的列表。</span><span class="sxs-lookup"><span data-stu-id="4776d-118">The following sections contain a list of cmdlets and their descriptions.</span></span> <span data-ttu-id="4776d-119">也可直接从命令行获取此信息。</span><span class="sxs-lookup"><span data-stu-id="4776d-119">This information is also available directly from the command line.</span></span> <span data-ttu-id="4776d-120">只需在 Lync Server Management Shell 命令提示符处键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="4776d-120">Simply type the following at the Lync Server Management Shell command prompt:</span></span>

    Get-Help <cmdlet name> -Full

<span data-ttu-id="4776d-121">例如，要通过命令提示符检索有关 **New-CsVoicePolicy** cmdlet 的帮助，请键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="4776d-121">For example, to retrieve help from the command prompt on the **New-CsVoicePolicy** cmdlet, type the following:</span></span>

    Get-Help New-CsVoicePolicy -Full

<span data-ttu-id="4776d-122">有关在 Lync Server 2013 中了解 Windows PowerShell 的事项：</span><span class="sxs-lookup"><span data-stu-id="4776d-122">Things to know about Windows PowerShell in Lync Server 2013:</span></span>

  - <span data-ttu-id="4776d-123">若要运行 Lync Server cmdlet，请打开 Lync Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="4776d-123">To run the Lync Server cmdlets, open the Lync Server Management Shell.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="4776d-124">如果打开的是 Windows PowerShell 窗口而不是 Lync Server Management Shell，则默认情况下你将无法运行 Lync Server cmdlet。</span><span class="sxs-lookup"><span data-stu-id="4776d-124">If you open a Windows PowerShell window rather than the Lync Server Management Shell, by default you will not be able to run the Lync Server cmdlets.</span></span> <span data-ttu-id="4776d-125">若要从 Windows PowerShell 中运行 Lync Server cmdlet，请首先在 Windows PowerShell 命令提示符处键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="4776d-125">To run the Lync Server cmdlets from within Windows PowerShell, first type the following at the Windows PowerShell command prompt:</span></span><BR><span data-ttu-id="4776d-126">导入模块 Lync</span><span class="sxs-lookup"><span data-stu-id="4776d-126">Import-Module Lync</span></span>

    
    </div>

  - <span data-ttu-id="4776d-127">Lync Server 命令行管理程序自动安装在每个 Lync Server 企业版前端服务器或标准版服务器上。</span><span class="sxs-lookup"><span data-stu-id="4776d-127">Lync Server Management Shell is automatically installed on every Lync Server Enterprise Edition Front End Server or Standard Edition server.</span></span>

  - <span data-ttu-id="4776d-128">有关 Windows PowerShell 和 Microsoft Lync Server 2013 cmdlet 的新增和更新信息、示例脚本以及有关 Windows PowerShell 和 Microsoft Lync Server cmdlet 的详细信息，请访问 Lync [https://go.microsoft.com/fwlink/p/?linkId=203150](https://go.microsoft.com/fwlink/p/?linkid=203150)Server Windows PowerShell 博客。</span><span class="sxs-lookup"><span data-stu-id="4776d-128">New and updated information, sample scripts, and help for getting started and learning more about Windows PowerShell and Microsoft Lync Server 2013 cmdlets is available at the Lync Server Windows PowerShell Blog [https://go.microsoft.com/fwlink/p/?linkId=203150](https://go.microsoft.com/fwlink/p/?linkid=203150).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

