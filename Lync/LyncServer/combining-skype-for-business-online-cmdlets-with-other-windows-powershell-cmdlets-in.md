---
title: 将 Skype for Business Online cmdlet 与其他 Windows PowerShell cmdlet 结合在一起
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Combining Skype for Business Online cmdlets with other Windows PowerShell cmdlets
ms:assetid: 8bb8800a-f966-4570-8c8b-db87a91ad783
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362816(v=OCS.15)
ms:contentKeyID: 56558835
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6fd92d460ef79f7c4b201873db9a52b1a40c2a11
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837090"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="combining-skype-for-business-online-cmdlets-with-other-windows-powershell-cmdlets-in"></a><span data-ttu-id="0e15e-102">将 Skype for Business Online cmdlet 与其他 Windows PowerShell cmdlet 结合在一起</span><span class="sxs-lookup"><span data-stu-id="0e15e-102">Combining Skype for Business Online cmdlets with other Windows PowerShell cmdlets in</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0e15e-103">_**主题上次修改时间:** 2013-07-05_</span><span class="sxs-lookup"><span data-stu-id="0e15e-103">_**Topic Last Modified:** 2013-07-05_</span></span>

<span data-ttu-id="0e15e-104">使用 Windows PowerShell 连接到 Skype for business Online 时, 将提供大约 40 Skype for business Online cmdlet 供您使用。</span><span class="sxs-lookup"><span data-stu-id="0e15e-104">When you connect to Skype for Business Online by using Windows PowerShell, approximately 40 Skype for Business Online cmdlets will available for your use.</span></span> <span data-ttu-id="0e15e-105">但是, 管理 Skype for Business Online 时, 不仅限于使用这些 40 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0e15e-105">However, you are not limited to using just those 40 cmdlets when managing Skype for Business Online.</span></span> <span data-ttu-id="0e15e-106">除了 Skype for Business Online cmdlet 外, 你还可以使用你的计算机上安装的任何其他 Windows PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0e15e-106">In addition to the Skype for Business Online cmdlets, you can also use any other Windows PowerShell cmdlets that are installed on your computer.</span></span> <span data-ttu-id="0e15e-107">(安装 Windows PowerShell 3.0 时, 还会安装数以百计的核心 Windows PowerShell cmdlet。)你的命令可以混合和匹配 Skype for Business Online cmdlet 以及你的计算机上可用的任何其他 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0e15e-107">(When you install Windows PowerShell 3.0, hundreds of core Windows PowerShell cmdlets are installed, as well.) Your commands can mix and match Skype for Business Online cmdlets and any other cmdlets available on your computer.</span></span>

<span data-ttu-id="0e15e-108">虽然 Windows PowerShell 3.0 中的完整课程不在本文的范围之内, 但下面提供了一些示例, 显示了可能希望混合和匹配 cmdlet 的原因。</span><span class="sxs-lookup"><span data-stu-id="0e15e-108">Although a complete course in Windows PowerShell 3.0 goes beyond the scope of this article, here are a few examples that show why you might want to mix and match cmdlets.</span></span> <span data-ttu-id="0e15e-109">首先, 所有 Skype for Business Online cmdlet 都不包含打印命令, 也不能在 Windows PowerShell 控制台中找到此类命令。</span><span class="sxs-lookup"><span data-stu-id="0e15e-109">First of all, none of the Skype for Business Online cmdlets include a Print command, and no such command can be found in the Windows PowerShell console, either.</span></span> <span data-ttu-id="0e15e-110">那么, 如何获取由 cmdlet 检索的信息的打印输出？</span><span class="sxs-lookup"><span data-stu-id="0e15e-110">So how do you get a printout of the information retrieved by a cmdlet?</span></span> <span data-ttu-id="0e15e-111">一种方法是检索信息, 然后将该信息发送到**打印机**cmdlet:</span><span class="sxs-lookup"><span data-stu-id="0e15e-111">One way is to retrieve the information, and then send that information to the **Out-Printer** cmdlet:</span></span>

    Get-CsTenant | Out-Printer

<span data-ttu-id="0e15e-112">由于不包含任何其他参数,**打印机**cmdlet 返回的所有信息将打印到默认打印机。</span><span class="sxs-lookup"><span data-stu-id="0e15e-112">Because no additional parameters are included, all the information returned by **the Out-Printer** cmdlet will be printed to the default printer.</span></span>

<span data-ttu-id="0e15e-113">同样, 任何 Skype for Business Online cmdlet 都不包含允许你将数据保存到文件的参数。</span><span class="sxs-lookup"><span data-stu-id="0e15e-113">Likewise, none of the Skype for Business Online cmdlets include a parameter that allows you to save data to a file.</span></span> <span data-ttu-id="0e15e-114">但这是正常的: 此命令使用**Out 文件**cmdlet 将返回的信息保存到文本文件 C:\\记录\\承租人:</span><span class="sxs-lookup"><span data-stu-id="0e15e-114">But that’s OK: this command uses the **Out-File** cmdlet to save the returned information to the text file C:\\Logs\\Tenants.txt:</span></span>

    Get-Tenant | Out-File -FilePath "C:\Logs\Tenants.txt"

<span data-ttu-id="0e15e-115">此命令使用**Select-对象**cmdlet 限制在屏幕上返回和显示的数据。</span><span class="sxs-lookup"><span data-stu-id="0e15e-115">And this command uses the **Select-Object** cmdlet to limit the data that is returned and displayed onscreen.</span></span> <span data-ttu-id="0e15e-116">在此示例中, [CsOnlineUser](https://technet.microsoft.com/en-us/library/JJ994026(v=OCS.15)) cmdlet 检索所有 Skype For business Online 用户的信息, 然后使用**Select 对象**cmdlet 将显示的数据限制为用户的标识值及其存档策略:</span><span class="sxs-lookup"><span data-stu-id="0e15e-116">In this example, the [Get-CsOnlineUser](https://technet.microsoft.com/en-us/library/JJ994026(v=OCS.15)) cmdlet retrieves information for all of your Skype for Business Online users, and then the **Select-Object** cmdlet is used to limit the displayed data to the user’s Identity value and their archiving policy:</span></span>

    Get-CsOnlineUser | Select-Object Identity, ArchivingPolicy

<span data-ttu-id="0e15e-117">由于你的计算机上可以使用数百个 cmdlet, 因此你可能无法确定哪些 cmdlet 是 Skype for Business Online cmdlet 以及哪些 cmdlet 不是。</span><span class="sxs-lookup"><span data-stu-id="0e15e-117">Because there will be hundreds of cmdlets available for use on your computer, you might have difficulty determining which cmdlets are Skype for Business Online cmdlets and which ones are not.</span></span> <span data-ttu-id="0e15e-118">若要返回 Skype for Business Online cmdlet (且仅适用于 Skype for business Online cmdlet) 的列表, 必须首先确定包含所有 Skype for Business Online cmdlet 的临时 Windows PowerShell 模块的名称。</span><span class="sxs-lookup"><span data-stu-id="0e15e-118">To return a list of the Skype for Business Online cmdlets (and only Skype for Business Online cmdlets), you must first determine the name of the temporary Windows PowerShell module that contains all the Skype for Business Online cmdlets.</span></span> <span data-ttu-id="0e15e-119">若要执行此操作, 请从 Windows PowerShell 提示符运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="0e15e-119">To do that, run this command from the Windows PowerShell prompt:</span></span>

    Get-Module

<span data-ttu-id="0e15e-120">屏幕上将显示类似于以下内容的信息:</span><span class="sxs-lookup"><span data-stu-id="0e15e-120">Information similar to the following will appear onscreen:</span></span>

    ModuleType Name                 ExportedCommands
    ---------- ----                 ----------------
    Manifest   Microsoft.PowerS...  {Add-Computer, Add-Content, A...}
    Script     tmp_5astd3uh.m5v     {Disable-CsMeetingRoom, Enabl...}

<span data-ttu-id="0e15e-121">带有 ModuleType 脚本的模块是包含 Skype for Business Online cmdlet 的模块。</span><span class="sxs-lookup"><span data-stu-id="0e15e-121">The module with the ModuleType Script is the module that contains the Skype for Business Online cmdlets.</span></span> <span data-ttu-id="0e15e-122">若要返回这些 cmdlet 的列表, 请运行**Get Command** cmdlet, 使用脚本模块的名称作为模块名称:</span><span class="sxs-lookup"><span data-stu-id="0e15e-122">To return a list of those cmdlets, run the **Get-Command** cmdlet, using the name of the Script module as the module name:</span></span>

    Get-Command -Module tmp_5astd3uh.m5v

<span data-ttu-id="0e15e-123">可能有多个模块的 ModuleType 等于脚本。</span><span class="sxs-lookup"><span data-stu-id="0e15e-123">It’s possible that you could have multiple modules with a ModuleType equal to Script.</span></span> <span data-ttu-id="0e15e-124">在这种情况下, 你可以运行以下命令来查明哪个模块包括**CsTenant** cmdlet:</span><span class="sxs-lookup"><span data-stu-id="0e15e-124">In that case, you can run the following command to find out which module includes the **Get-CsTenant** cmdlet:</span></span>

    Get-Command Get-CsTenant

<span data-ttu-id="0e15e-125">为**CsTenant** cmdlet 返回的模块将是包含所有 Skype For business Online cmdlet 的模块:</span><span class="sxs-lookup"><span data-stu-id="0e15e-125">The module returned for the **Get-CsTenant** cmdlet will be the module containing all the Skype for Business Online cmdlets:</span></span>

    CommandType     Name                                               ModuleName
    -----------     ----                                               ----------
    Function        Get-CsTenant                                       tmp_5astd3uh.m5v

<div>

## <a name="see-also"></a><span data-ttu-id="0e15e-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0e15e-126">See Also</span></span>


<span data-ttu-id="0e15e-127">[Windows PowerShell 和 Skype for Business Online 简介](https://technet.microsoft.com/en-us/library/Dn362785(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0e15e-127">[An introduction to Windows PowerShell and Skype for Business Online](https://technet.microsoft.com/en-us/library/Dn362785(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

