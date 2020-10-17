---
title: Lync Server 2013：管理观察程序节点
description: Lync Server 2013：管理观察程序节点。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing watcher nodes
ms:assetid: 66deaf49-a71f-4a6e-ada0-ea8b688ee921
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688078(v=OCS.15)
ms:contentKeyID: 49733674
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1795b09bbca73d8157cf796ceeaaeafb9cc2ebc5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556608"
---
# <a name="managing-watcher-nodes-in-lync-server-2013"></a><span data-ttu-id="f0391-103">在 Lync Server 2013 中管理观察程序节点</span><span class="sxs-lookup"><span data-stu-id="f0391-103">Managing watcher nodes in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f0391-104">_**上次修改的主题：** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="f0391-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="f0391-105">除了修改在观察程序节点上执行的综合事务，管理员还可使用 **Set-CsWatcherNodeConfiguration** cmdlet 执行两个其他重要任务：启用和禁用观察程序节点，以及将观察程序节点配置为在运行其测试时使用内部 URL 或外部 URL。</span><span class="sxs-lookup"><span data-stu-id="f0391-105">In addition to modifying the synthetic transactions that are executed on a watcher node, administrators can also use the **Set-CsWatcherNodeConfiguration** cmdlet to carry out two other important tasks: enabling and disabling the watcher node, and configuring the watcher node to use either internal URLs or external URLs when running its tests.</span></span>

<span data-ttu-id="f0391-106">默认情况下，观察程序节点旨在定期运行其所有启用的综合事务。</span><span class="sxs-lookup"><span data-stu-id="f0391-106">By default, watcher nodes are designed to periodically run all their enabled synthetic transactions.</span></span> <span data-ttu-id="f0391-107">但是，有时您可能需要暂停这些事务。</span><span class="sxs-lookup"><span data-stu-id="f0391-107">Sometimes, however, you may need to suspend those transactions.</span></span> <span data-ttu-id="f0391-108">例如，如果观察程序节点临时断开了网络连接，则没有必要运行综合事务。</span><span class="sxs-lookup"><span data-stu-id="f0391-108">For example, if the watcher node is temporarily disconnected from the network, then there is no reason to run the synthetic transactions.</span></span> <span data-ttu-id="f0391-109">没有网络连接，这些事务必定失败。</span><span class="sxs-lookup"><span data-stu-id="f0391-109">Without network connectivity, those transactions are guaranteed to fail.</span></span> <span data-ttu-id="f0391-110">如果要暂时禁用观察程序节点，请在 Lync Server 命令行管理程序中运行与以下内容类似的命令：</span><span class="sxs-lookup"><span data-stu-id="f0391-110">If you want to temporarily disable a watcher node, run a command similar to this from the Lync Server Management Shell:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False

<span data-ttu-id="f0391-p102">此命令将禁止在观察程序节点 atl-watcher- 001.litwareinc.com 上执行综合事务。若要恢复综合事务的执行，请将 Enabled 属性设置回 True ($True)：</span><span class="sxs-lookup"><span data-stu-id="f0391-p102">This command will disable the execution of synthetic transactions on the watcher node atl-watcher- 001.litwareinc.com. To resume execution of the synthetic transactions, set the Enabled property back to True ($True):</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True

<div>


> [!NOTE]  
> <span data-ttu-id="f0391-113">Enabled 属性可用于启用或禁用观察程序节点。</span><span class="sxs-lookup"><span data-stu-id="f0391-113">The Enabled property can be used to turn watcher nodes on or off.</span></span> <span data-ttu-id="f0391-114">如果要永久删除观察程序节点，请使用 <STRONG>Remove-CsWatcherNodeConfiguration</STRONG> cmdlet：</span><span class="sxs-lookup"><span data-stu-id="f0391-114">If you want to permanently delete a watcher node, use the <STRONG>Remove-CsWatcherNodeConfiguration</STRONG> cmdlet:</span></span><BR><span data-ttu-id="f0391-115">Remove-CsWatcherNodeConfiguration –Identity "atl-watcher-001.litwareinc.com"</span><span class="sxs-lookup"><span data-stu-id="f0391-115">Remove-CsWatcherNodeConfiguration –Identity "atl-watcher-001.litwareinc.com"</span></span><BR><span data-ttu-id="f0391-116">此命令将删除指定计算机中的所有观察程序节点配置设置，这将防止计算机自动运行综合事务。</span><span class="sxs-lookup"><span data-stu-id="f0391-116">That command removes all the watcher node configuration settings from the specified computer, which prevents the computer from automatically running synthetic transactions.</span></span> <span data-ttu-id="f0391-117">但是，该命令不会卸载 System Center agent 文件或 Lync Server 2013 系统文件。</span><span class="sxs-lookup"><span data-stu-id="f0391-117">However, the command does not uninstall the System Center agent files or the Lync Server 2013 system files.</span></span>



</div>

<span data-ttu-id="f0391-p105">默认情况下，观察程序节点在执行其测试时使用组织的外部 URL。但是，还可将观察程序节点配置为使用组织的内部 URL。这使管理员可验证位于外围网络内的用户的 URL 访问权限。若要将观察程序节点配置为使用内部 URL 而不是外部 URL，请将 UseInternalWebUrls 属性设置为 True ($True)：</span><span class="sxs-lookup"><span data-stu-id="f0391-p105">By default, watcher nodes use an organization's external URLs when conducting their tests. However, watcher nodes can also be configured to use the organization's internal URLs. This enables administrators to verify URL access for users located inside the perimeter network. To configure a watcher node to use internal URLs instead of external URLs, set the UseInternalWebUrls property to True ($True):</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True

<span data-ttu-id="f0391-122">如果将此属性重置为默认值 False ($False)，则观察程序将使用外部 URL：</span><span class="sxs-lookup"><span data-stu-id="f0391-122">If you reset this property to the default value of False ($False), the watcher will then use the external URLs:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False

</div>

<span> </span>

</div>

</div>

</div>

