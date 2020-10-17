---
title: Lync Server 2013：删除现有客户端版本策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing client version policy
ms:assetid: b88aaa25-97ff-4eb6-bd34-b97332cd6890
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ923064(v=OCS.15)
ms:contentKeyID: 50675349
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e8915d828dd81c61e7d0c94f01fb7fdcb70e43a2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525609"
---
# <a name="delete-an-existing-client-version-policy-in-lync-server-2013"></a><span data-ttu-id="6a675-102">在 Lync Server 2013 中删除现有客户端版本策略</span><span class="sxs-lookup"><span data-stu-id="6a675-102">Delete an existing client version policy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6a675-103">_**上次修改的主题：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="6a675-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="6a675-104">如果要删除以前配置的客户端版本策略，可以从 Lync Server 2013 控制面板或 Lync Server 2013 命令行管理程序中将其删除。</span><span class="sxs-lookup"><span data-stu-id="6a675-104">If you want to delete a client version policy that was previously configured, you can delete it from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-delete-client-version-policies-by-using-lync-server-control-panel"></a><span data-ttu-id="6a675-105">使用 Lync Server 控制面板删除客户端版本策略</span><span class="sxs-lookup"><span data-stu-id="6a675-105">To delete client version policies by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="6a675-106">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="6a675-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="6a675-107">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="6a675-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="6a675-108">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="6a675-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="6a675-109">在左侧导航栏中，单击 " **客户端**"，然后单击 " **客户端版本策略** 导航" 按钮。</span><span class="sxs-lookup"><span data-stu-id="6a675-109">In the left navigation bar, click **Clients**, and then click the **Client Version Policy** navigation button.</span></span>

4.  <span data-ttu-id="6a675-110">在 " **客户端版本策略** " 页上，选择要删除的客户端版本策略或策略，单击 " **编辑**"，然后单击 " **删除**"。</span><span class="sxs-lookup"><span data-stu-id="6a675-110">On the **Client Version Policy** page, select the client version policy or policies you want to delete, click **Edit**, and then click **Delete**.</span></span>

</div>

<div>

## <a name="deleting-client-version-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="6a675-111">使用 Windows PowerShell Cmdlet 删除客户端版本策略</span><span class="sxs-lookup"><span data-stu-id="6a675-111">Deleting Client Version Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="6a675-112">您可以使用 **CsClientVersionPolicy** cmdlet 删除客户端版本策略。</span><span class="sxs-lookup"><span data-stu-id="6a675-112">You can delete client version policies by using the **Remove-CsClientVersionPolicy** cmdlet.</span></span> <span data-ttu-id="6a675-113">此 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。</span><span class="sxs-lookup"><span data-stu-id="6a675-113">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="6a675-114">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上的 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="6a675-114">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specific-client-version-policy"></a><span data-ttu-id="6a675-115">删除特定的客户端版本策略</span><span class="sxs-lookup"><span data-stu-id="6a675-115">To remove a specific client version policy</span></span>

  - <span data-ttu-id="6a675-116">此命令将删除应用于 Redmond 站点的客户端版本策略：</span><span class="sxs-lookup"><span data-stu-id="6a675-116">This command deletes the client version policy applied to the Redmond site:</span></span>
    
        Remove-CsClientVersionPolicy -Identity site:Redmond

</div>

<div>

## <a name="to-remove-all-the-client-version-policies-applied-to-the-site-scope"></a><span data-ttu-id="6a675-117">删除应用到站点范围的所有客户端版本策略</span><span class="sxs-lookup"><span data-stu-id="6a675-117">To remove all the client version policies applied to the site scope</span></span>

  - <span data-ttu-id="6a675-118">此命令将删除在站点范围内配置的所有客户端版本策略：</span><span class="sxs-lookup"><span data-stu-id="6a675-118">This command removes all the client version policies configured at the site scope:</span></span>
    
        Get-CsClientVersionPolicy -Fiter "site:*" | Remove-CsClientVersionPolicy

</div>

<div>

## <a name="to-remove-client-version-policies-that-do-not-include-a-specific-user-agent"></a><span data-ttu-id="6a675-119">删除不包含特定用户代理的客户端版本策略</span><span class="sxs-lookup"><span data-stu-id="6a675-119">To remove client version policies that do not include a specific user agent</span></span>

  - <span data-ttu-id="6a675-120">此命令将删除任何不包含 Windows Phone Lync (WPLync) 用户代理规则的客户端版本策略：</span><span class="sxs-lookup"><span data-stu-id="6a675-120">And this command removes any client version policies that do not include a rule for the Windows Phone Lync (WPLync) user agent:</span></span>
    
        Get-CsClientVersionPolicy | Where-Object {$_.Rules -notmatch "UserAgent=WPLync" | Remove-CsClientVersionPolicy

</div>

<span data-ttu-id="6a675-121">有关详细信息，请参阅 [CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsClientVersionPolicy) Cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="6a675-121">For details, see the Help topic for the [Remove-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsClientVersionPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

