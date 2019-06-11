---
title: 'Lync Server 2013: 删除存档策略'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deleting an Archiving policy
ms:assetid: 4739a691-41cc-4128-8bb8-6d5a4c02107a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520989(v=OCS.15)
ms:contentKeyID: 48184043
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f151a940958273509191b35ed817409ba52b6dd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830588"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-an-archiving-policy-in-lync-server-2013"></a><span data-ttu-id="e7c71-102">在 Lync Server 2013 中删除存档策略</span><span class="sxs-lookup"><span data-stu-id="e7c71-102">Deleting an Archiving policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e7c71-103">_**主题上次修改时间:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="e7c71-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="e7c71-104">你可以删除用户策略或网站策略。</span><span class="sxs-lookup"><span data-stu-id="e7c71-104">You can delete a user policy or site policy.</span></span> <span data-ttu-id="e7c71-105">无法删除全局策略。</span><span class="sxs-lookup"><span data-stu-id="e7c71-105">The global policy cannot be removed.</span></span> <span data-ttu-id="e7c71-106">如果您尝试删除全局策略, 则 Lync Server 2013 会自动将策略重置为默认值。</span><span class="sxs-lookup"><span data-stu-id="e7c71-106">If you try to delete the global policy, Lync Server 2013 automatically resets the policy to the default values.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e7c71-107">如果为你的部署启用了 Microsoft Exchange 集成, Exchange 策略将控制是否为托管在 Exchange 2013 上的用户启用存档, 并将其邮箱置于原地保留。</span><span class="sxs-lookup"><span data-stu-id="e7c71-107">If you enabled Microsoft Exchange integration for your deployment, Exchange policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="e7c71-108">有关详细信息, 请参阅在部署文档中<A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">使用 Exchange Server 集成时在 Lync Server 2013 中设置存档策略</A>。</span><span class="sxs-lookup"><span data-stu-id="e7c71-108">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-delete-a-user-or-site-policy-for-archiving"></a><span data-ttu-id="e7c71-109">删除用户或网站策略以进行存档</span><span class="sxs-lookup"><span data-stu-id="e7c71-109">To delete a user or site policy for archiving</span></span>

1.  <span data-ttu-id="e7c71-110">使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="e7c71-110">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e7c71-111">打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="e7c71-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e7c71-112">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="e7c71-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e7c71-113">在左侧导航栏中，单击“监控和存档”\*\*\*\*，然后单击“存档策略”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e7c71-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>

4.  <span data-ttu-id="e7c71-114">在存档策略列表中，单击要删除的用户策略或站点策略，再单击“**编辑**”，然后单击“**删除**”。</span><span class="sxs-lookup"><span data-stu-id="e7c71-114">In the list of archiving policies, click the user or site policy that you want to delete, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="e7c71-115">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="e7c71-115">Click **Commit**.</span></span>

</div>

<div>

## <a name="removing-archiving-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="e7c71-116">使用 Windows PowerShell Cmdlet 删除存档策略</span><span class="sxs-lookup"><span data-stu-id="e7c71-116">Removing Archiving Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="e7c71-117">可以使用 Windows PowerShell 和**CsArchivingPolicy** cmdlet 删除存档策略。</span><span class="sxs-lookup"><span data-stu-id="e7c71-117">Archiving policies can be deleted by using Windows PowerShell and the **Remove-CsArchivingPolicy** cmdlet.</span></span> <span data-ttu-id="e7c71-118">此 cmdlet 既可以从 Lync Server 2013 管理外壳运行, 也可以从 Windows PowerShell 的远程会话运行。</span><span class="sxs-lookup"><span data-stu-id="e7c71-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="e7c71-119">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息, 请参阅 Lync Server Windows PowerShell 博客文章 "快速入门: 使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="e7c71-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-archiving-policy"></a><span data-ttu-id="e7c71-120">删除指定的存档策略</span><span class="sxs-lookup"><span data-stu-id="e7c71-120">To remove a specified archiving policy</span></span>

  - <span data-ttu-id="e7c71-121">例如, **CsArchivingPolicy**删除了标识网站: Redmond 的策略。</span><span class="sxs-lookup"><span data-stu-id="e7c71-121">As an example, **Remove-CsArchivingPolicy** deletes the policy with the Identity site:Redmond.</span></span> <span data-ttu-id="e7c71-122">请注意, 当删除在网站范围内配置的策略时, 以前由网站策略管理的用户将由全局存档策略自动控制。</span><span class="sxs-lookup"><span data-stu-id="e7c71-122">Note that, when a policy configured at the site scope is deleted, users previously managed by the site policy will automatically be governed by the global archiving policy instead.</span></span> <span data-ttu-id="e7c71-123">以下命令将删除应用于 Redmond 网站的存档:</span><span class="sxs-lookup"><span data-stu-id="e7c71-123">The following command removes the archiving applied to the Redmond site:</span></span>
    
        Remove-CsArchivingPolicy -Identity site:Redmond

</div>

<div>

## <a name="to-remove-all-the-archiving-policies-applied-to-the-per-user-scope"></a><span data-ttu-id="e7c71-124">删除应用到每用户范围的所有存档策略</span><span class="sxs-lookup"><span data-stu-id="e7c71-124">To remove all the archiving policies applied to the per-user scope</span></span>

  - <span data-ttu-id="e7c71-125">此命令将删除应用到每用户作用域的所有存档策略:</span><span class="sxs-lookup"><span data-stu-id="e7c71-125">This command removes all the archiving policies applied to the per-user scope:</span></span>
    
        Get-CsArchivingPolicy -Filter "tag:*" | Remove-CsArchivingPolicy

</div>

<div>

## <a name="to-remove-all-the-archiving-policies-that-disable-internal-archiving"></a><span data-ttu-id="e7c71-126">删除禁用内部存档的所有存档策略</span><span class="sxs-lookup"><span data-stu-id="e7c71-126">To remove all the archiving policies that disable internal archiving</span></span>

  - <span data-ttu-id="e7c71-127">此命令将删除其中禁用了内部存档的所有存档策略：</span><span class="sxs-lookup"><span data-stu-id="e7c71-127">This command removes all the archiving policies where internal archiving has been disabled:</span></span>
    
        Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False} | Remove-CsArchivingPolicy

</div>

<span data-ttu-id="e7c71-128">有关详细信息, 请参阅[CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsArchivingPolicy) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="e7c71-128">For more information, see the help topic for the [Remove-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsArchivingPolicy) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e7c71-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e7c71-129">See Also</span></span>


[<span data-ttu-id="e7c71-130">在 Lync Server 2013 中管理内部和外部通信的存档</span><span class="sxs-lookup"><span data-stu-id="e7c71-130">Managing the Archiving of internal and external communications in Lync Server 2013</span></span>](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

