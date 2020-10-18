---
title: Lync Server 2013：删除存档策略
description: Lync Server 2013：删除存档策略。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting an Archiving policy
ms:assetid: 4739a691-41cc-4128-8bb8-6d5a4c02107a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520989(v=OCS.15)
ms:contentKeyID: 48184043
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ecf465a62cf8f54777b03a1634d9a95f1b565c9b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575798"
---
# <a name="deleting-an-archiving-policy-in-lync-server-2013"></a><span data-ttu-id="125dd-103">在 Lync Server 2013 中删除存档策略</span><span class="sxs-lookup"><span data-stu-id="125dd-103">Deleting an Archiving policy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="125dd-104">_**上次修改的主题：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="125dd-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="125dd-105">可以删除用户策略或站点策略。</span><span class="sxs-lookup"><span data-stu-id="125dd-105">You can delete a user policy or site policy.</span></span> <span data-ttu-id="125dd-106">无法删除全局策略。</span><span class="sxs-lookup"><span data-stu-id="125dd-106">The global policy cannot be removed.</span></span> <span data-ttu-id="125dd-107">如果您尝试删除全局策略，Lync Server 2013 会自动将策略重置为默认值。</span><span class="sxs-lookup"><span data-stu-id="125dd-107">If you try to delete the global policy, Lync Server 2013 automatically resets the policy to the default values.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="125dd-108">如果为您的部署启用了 Microsoft Exchange 集成，Exchange 策略将控制是否为驻留在 Exchange 2013 上的用户启用存档，并将其邮箱置于 In-Place 保留状态。</span><span class="sxs-lookup"><span data-stu-id="125dd-108">If you enabled Microsoft Exchange integration for your deployment, Exchange policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="125dd-109">有关详细信息，请参阅部署文档中的 <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">使用 Exchange Server 集成时，请参阅在 Lync Server 2013 中设置存档策略</A> 。</span><span class="sxs-lookup"><span data-stu-id="125dd-109">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-delete-a-user-or-site-policy-for-archiving"></a><span data-ttu-id="125dd-110">删除用户存档策略或站点存档策略</span><span class="sxs-lookup"><span data-stu-id="125dd-110">To delete a user or site policy for archiving</span></span>

1.  <span data-ttu-id="125dd-111">使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="125dd-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="125dd-112">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="125dd-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="125dd-113">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="125dd-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="125dd-114">在左侧导航栏中，单击 **“监控和存档”**，然后单击 **“存档策略”**。</span><span class="sxs-lookup"><span data-stu-id="125dd-114">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>

4.  <span data-ttu-id="125dd-115">在存档策略列表中，单击要删除的用户策略或站点策略，再单击“编辑”\*\*\*\*，然后单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="125dd-115">In the list of archiving policies, click the user or site policy that you want to delete, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="125dd-116">单击“提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="125dd-116">Click **Commit**.</span></span>

</div>

<div>

## <a name="removing-archiving-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="125dd-117">使用 Windows PowerShell Cmdlet 删除存档策略</span><span class="sxs-lookup"><span data-stu-id="125dd-117">Removing Archiving Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="125dd-118">可以使用 Windows PowerShell 和 **new-csarchivingpolicy** cmdlet 删除存档策略。</span><span class="sxs-lookup"><span data-stu-id="125dd-118">Archiving policies can be deleted by using Windows PowerShell and the **Remove-CsArchivingPolicy** cmdlet.</span></span> <span data-ttu-id="125dd-119">此 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。</span><span class="sxs-lookup"><span data-stu-id="125dd-119">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="125dd-120">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上的 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="125dd-120">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-archiving-policy"></a><span data-ttu-id="125dd-121">删除指定的存档策略</span><span class="sxs-lookup"><span data-stu-id="125dd-121">To remove a specified archiving policy</span></span>

  - <span data-ttu-id="125dd-p105">作为示例，**Remove-CsArchivingPolicy** 删除了 Identity 为 site:Redmond 的策略。请注意，删除站点作用域的策略时，全局存档策略将自动控制网站策略之前管理的用户。以下命令删除适用于 Redmond 站点的策略：</span><span class="sxs-lookup"><span data-stu-id="125dd-p105">As an example, **Remove-CsArchivingPolicy** deletes the policy with the Identity site:Redmond. Note that, when a policy configured at the site scope is deleted, users previously managed by the site policy will automatically be governed by the global archiving policy instead. The following command removes the archiving applied to the Redmond site:</span></span>
    
        Remove-CsArchivingPolicy -Identity site:Redmond

</div>

<div>

## <a name="to-remove-all-the-archiving-policies-applied-to-the-per-user-scope"></a><span data-ttu-id="125dd-125">删除应用于每用户作用域的所有存档策略</span><span class="sxs-lookup"><span data-stu-id="125dd-125">To remove all the archiving policies applied to the per-user scope</span></span>

  - <span data-ttu-id="125dd-126">此命令将删除所有适用于每用户范围的存档策略：</span><span class="sxs-lookup"><span data-stu-id="125dd-126">This command removes all the archiving policies applied to the per-user scope:</span></span>
    
        Get-CsArchivingPolicy -Filter "tag:*" | Remove-CsArchivingPolicy

</div>

<div>

## <a name="to-remove-all-the-archiving-policies-that-disable-internal-archiving"></a><span data-ttu-id="125dd-127">删除禁用内部存档的所有存档策略</span><span class="sxs-lookup"><span data-stu-id="125dd-127">To remove all the archiving policies that disable internal archiving</span></span>

  - <span data-ttu-id="125dd-128">此命令将删除其中禁用了内部存档的所有存档策略：</span><span class="sxs-lookup"><span data-stu-id="125dd-128">This command removes all the archiving policies where internal archiving has been disabled:</span></span>
    
        Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False} | Remove-CsArchivingPolicy

</div>

<span data-ttu-id="125dd-129">有关详细信息，请参阅 [new-csarchivingpolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsArchivingPolicy) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="125dd-129">For more information, see the help topic for the [Remove-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsArchivingPolicy) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="125dd-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="125dd-130">See Also</span></span>


[<span data-ttu-id="125dd-131">在 Lync Server 2013 中管理内部和外部通信的存档</span><span class="sxs-lookup"><span data-stu-id="125dd-131">Managing the Archiving of internal and external communications in Lync Server 2013</span></span>](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

