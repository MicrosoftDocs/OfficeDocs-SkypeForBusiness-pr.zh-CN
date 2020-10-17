---
title: 将 Skype for Business Online cmdlet 与中的其他 Windows PowerShell cmdlet 结合使用
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Combining Skype for Business Online cmdlets with other Windows PowerShell cmdlets
ms:assetid: 8bb8800a-f966-4570-8c8b-db87a91ad783
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362816(v=OCS.15)
ms:contentKeyID: 56558835
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eb395820f9f90060ac24b737fab08c7d615727c2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499609"
---
# <a name="combining-skype-for-business-online-cmdlets-with-other-windows-powershell-cmdlets-in"></a><span data-ttu-id="eb6cd-102">将 Skype for Business Online cmdlet 与中的其他 Windows PowerShell cmdlet 结合使用</span><span class="sxs-lookup"><span data-stu-id="eb6cd-102">Combining Skype for Business Online cmdlets with other Windows PowerShell cmdlets in</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eb6cd-103">_**上次修改的主题：** 2013-07-05_</span><span class="sxs-lookup"><span data-stu-id="eb6cd-103">_**Topic Last Modified:** 2013-07-05_</span></span>

<span data-ttu-id="eb6cd-104">当您使用 Windows PowerShell 连接到 Skype for business Online 时，可以使用大约 40 Skype for Business Online cmdlet。</span><span class="sxs-lookup"><span data-stu-id="eb6cd-104">When you connect to Skype for Business Online by using Windows PowerShell, approximately 40 Skype for Business Online cmdlets will available for your use.</span></span> <span data-ttu-id="eb6cd-105">但是，在管理 Skype for Business Online 时，您并不局限于仅使用这些 40 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="eb6cd-105">However, you are not limited to using just those 40 cmdlets when managing Skype for Business Online.</span></span> <span data-ttu-id="eb6cd-106">除了 Skype for Business Online cmdlet 之外，还可以使用安装在计算机上的任何其他 Windows PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="eb6cd-106">In addition to the Skype for Business Online cmdlets, you can also use any other Windows PowerShell cmdlets that are installed on your computer.</span></span> <span data-ttu-id="eb6cd-107"> (安装 Windows PowerShell 3.0 时，还会安装数百个核心 Windows PowerShell cmdlet。 ) 你的命令可能会混合和匹配 Skype for Business Online cmdlet 以及你的计算机上可用的任何其他 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="eb6cd-107">(When you install Windows PowerShell 3.0, hundreds of core Windows PowerShell cmdlets are installed, as well.) Your commands can mix and match Skype for Business Online cmdlets and any other cmdlets available on your computer.</span></span>

<span data-ttu-id="eb6cd-108">尽管 Windows PowerShell 3.0 中的完整课程不在本文的讨论范围之内，但下面的几个示例展示了您可能需要混合和匹配 cmdlet 的原因。</span><span class="sxs-lookup"><span data-stu-id="eb6cd-108">Although a complete course in Windows PowerShell 3.0 goes beyond the scope of this article, here are a few examples that show why you might want to mix and match cmdlets.</span></span> <span data-ttu-id="eb6cd-109">首先，没有任何 Skype for Business Online cmdlet 包含打印命令，也不能在 Windows PowerShell 控制台中找到此类命令。</span><span class="sxs-lookup"><span data-stu-id="eb6cd-109">First of all, none of the Skype for Business Online cmdlets include a Print command, and no such command can be found in the Windows PowerShell console, either.</span></span> <span data-ttu-id="eb6cd-110">那么，如何获取由 cmdlet 检索的信息的打印输出？</span><span class="sxs-lookup"><span data-stu-id="eb6cd-110">So how do you get a printout of the information retrieved by a cmdlet?</span></span> <span data-ttu-id="eb6cd-111">一种方法是检索信息，然后将该信息发送到 **打印机** cmdlet：</span><span class="sxs-lookup"><span data-stu-id="eb6cd-111">One way is to retrieve the information, and then send that information to the **Out-Printer** cmdlet:</span></span>

    Get-CsTenant | Out-Printer

<span data-ttu-id="eb6cd-112">由于不包含任何其他参数，因此 **打印机** cmdlet 返回的所有信息将打印到默认打印机。</span><span class="sxs-lookup"><span data-stu-id="eb6cd-112">Because no additional parameters are included, all the information returned by **the Out-Printer** cmdlet will be printed to the default printer.</span></span>

<span data-ttu-id="eb6cd-113">同样，任何 Skype for Business Online cmdlet 都不包含允许您将数据保存到文件中的参数。</span><span class="sxs-lookup"><span data-stu-id="eb6cd-113">Likewise, none of the Skype for Business Online cmdlets include a parameter that allows you to save data to a file.</span></span> <span data-ttu-id="eb6cd-114">但这也是正常的：此命令使用 **Out 文件** cmdlet 将返回的信息保存到文本文件 C： \\ Logs \\Tenants.txt：</span><span class="sxs-lookup"><span data-stu-id="eb6cd-114">But that’s OK: this command uses the **Out-File** cmdlet to save the returned information to the text file C:\\Logs\\Tenants.txt:</span></span>

    Get-Tenant | Out-File -FilePath "C:\Logs\Tenants.txt"

<span data-ttu-id="eb6cd-115">此命令使用 **Select-Object** cmdlet 来限制在屏幕上返回和显示的数据。</span><span class="sxs-lookup"><span data-stu-id="eb6cd-115">And this command uses the **Select-Object** cmdlet to limit the data that is returned and displayed onscreen.</span></span> <span data-ttu-id="eb6cd-116">在此示例中， [get-csonlineuser](https://technet.microsoft.com/library/JJ994026(v=OCS.15)) cmdlet 检索所有 Skype For business Online 用户的信息，然后使用 **Select-Object** cmdlet 将显示的数据限制为用户的标识值及其存档策略：</span><span class="sxs-lookup"><span data-stu-id="eb6cd-116">In this example, the [Get-CsOnlineUser](https://technet.microsoft.com/library/JJ994026(v=OCS.15)) cmdlet retrieves information for all of your Skype for Business Online users, and then the **Select-Object** cmdlet is used to limit the displayed data to the user’s Identity value and their archiving policy:</span></span>

    Get-CsOnlineUser | Select-Object Identity, ArchivingPolicy

<span data-ttu-id="eb6cd-117">由于在您的计算机上有数百个 cmdlet 可供使用，因此您可能很难确定哪些 cmdlet 是 Skype for Business Online cmdlet，哪些是不是哪些。</span><span class="sxs-lookup"><span data-stu-id="eb6cd-117">Because there will be hundreds of cmdlets available for use on your computer, you might have difficulty determining which cmdlets are Skype for Business Online cmdlets and which ones are not.</span></span> <span data-ttu-id="eb6cd-118">若要返回 Skype for Business Online cmdlet 列表 (且仅) Skype for Business Online cmdlet，必须首先确定包含所有 Skype for Business Online cmdlet 的临时 Windows PowerShell 模块的名称。</span><span class="sxs-lookup"><span data-stu-id="eb6cd-118">To return a list of the Skype for Business Online cmdlets (and only Skype for Business Online cmdlets), you must first determine the name of the temporary Windows PowerShell module that contains all the Skype for Business Online cmdlets.</span></span> <span data-ttu-id="eb6cd-119">为此，请在 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="eb6cd-119">To do that, run this command from the Windows PowerShell prompt:</span></span>

    Get-Module

<span data-ttu-id="eb6cd-120">屏幕上将显示类似以下内容的信息：</span><span class="sxs-lookup"><span data-stu-id="eb6cd-120">Information similar to the following will appear onscreen:</span></span>

    ModuleType Name                 ExportedCommands
    ---------- ----                 ----------------
    Manifest   Microsoft.PowerS...  {Add-Computer, Add-Content, A...}
    Script     tmp_5astd3uh.m5v     {Disable-CsMeetingRoom, Enabl...}

<span data-ttu-id="eb6cd-121">包含 ModuleType 脚本的模块是包含 Skype for Business Online cmdlet 的模块。</span><span class="sxs-lookup"><span data-stu-id="eb6cd-121">The module with the ModuleType Script is the module that contains the Skype for Business Online cmdlets.</span></span> <span data-ttu-id="eb6cd-122">若要返回这些 cmdlet 的列表，请使用脚本模块的名称作为模块名称，以运行 **Get 命令** cmdlet：</span><span class="sxs-lookup"><span data-stu-id="eb6cd-122">To return a list of those cmdlets, run the **Get-Command** cmdlet, using the name of the Script module as the module name:</span></span>

    Get-Command -Module tmp_5astd3uh.m5v

<span data-ttu-id="eb6cd-123">有可能有一个 ModuleType 等于 Script 的多个模块。</span><span class="sxs-lookup"><span data-stu-id="eb6cd-123">It’s possible that you could have multiple modules with a ModuleType equal to Script.</span></span> <span data-ttu-id="eb6cd-124">在这种情况下，您可以运行以下命令来找出包含 **get-cstenant** cmdlet 的模块：</span><span class="sxs-lookup"><span data-stu-id="eb6cd-124">In that case, you can run the following command to find out which module includes the **Get-CsTenant** cmdlet:</span></span>

    Get-Command Get-CsTenant

<span data-ttu-id="eb6cd-125">为 **get-cstenant** cmdlet 返回的模块将是包含所有 Skype For business Online cmdlet 的模块：</span><span class="sxs-lookup"><span data-stu-id="eb6cd-125">The module returned for the **Get-CsTenant** cmdlet will be the module containing all the Skype for Business Online cmdlets:</span></span>

    CommandType     Name                                               ModuleName
    -----------     ----                                               ----------
    Function        Get-CsTenant                                       tmp_5astd3uh.m5v

<div>

## <a name="see-also"></a><span data-ttu-id="eb6cd-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eb6cd-126">See Also</span></span>


<span data-ttu-id="eb6cd-127">[Windows PowerShell 和 Skype for business Online 简介](https://technet.microsoft.com/library/Dn362785(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="eb6cd-127">[An introduction to Windows PowerShell and Skype for Business Online](https://technet.microsoft.com/library/Dn362785(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

