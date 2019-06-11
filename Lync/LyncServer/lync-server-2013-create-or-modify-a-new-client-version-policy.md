---
title: 'Lync Server 2013: 创建或修改新的客户端版本策略'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a new client version policy
ms:assetid: 4be6e449-aa82-4b46-abb1-d31281573a72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898476(v=OCS.15)
ms:contentKeyID: 50873756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 64e9d9d2879d4633b1775f8934186b8b01992d13
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830779"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-new-client-version-policy-in-lync-server-2013"></a><span data-ttu-id="13c2f-102">在 Lync Server 2013 中创建或修改新的客户端版本策略</span><span class="sxs-lookup"><span data-stu-id="13c2f-102">Create or modify a new client version policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="13c2f-103">_**主题上次修改时间:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="13c2f-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="13c2f-104">你可以使用客户端版本策略指定你的环境支持的客户端版本。</span><span class="sxs-lookup"><span data-stu-id="13c2f-104">You can use client version policies to specify the versions of clients that are supported in your environment.</span></span> <span data-ttu-id="13c2f-105">使用客户端版本有助于减少与支持多个客户端版本相关的成本。</span><span class="sxs-lookup"><span data-stu-id="13c2f-105">Using client versioning can help reduce the costs associated with supporting multiple client versions.</span></span> <span data-ttu-id="13c2f-106">它还可以改进整体用户体验, 因为当客户端的早期版本和更高版本的客户端交互时, 可用的功能可以受到较早版本的客户端的限制。</span><span class="sxs-lookup"><span data-stu-id="13c2f-106">It can also improve the overall user experience, because when earlier and later versions of clients interact, the available features can be limited by the earlier version of the client.</span></span> <span data-ttu-id="13c2f-107">可以从 Lync Server 2013 控制面板或 Lync Server 2013 管理外壳程序创建或修改客户端版本策略。</span><span class="sxs-lookup"><span data-stu-id="13c2f-107">You can create or modify client version policies from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-create-or-modify-client-version-policies-by-using-lync-server-control-panel"></a><span data-ttu-id="13c2f-108">使用 Lync Server "控制面板" 创建或修改客户端版本策略</span><span class="sxs-lookup"><span data-stu-id="13c2f-108">To create or modify client version policies by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="13c2f-109">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="13c2f-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="13c2f-110">打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="13c2f-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="13c2f-111">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="13c2f-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="13c2f-112">在左侧导航栏中, 单击 "**客户端**"。</span><span class="sxs-lookup"><span data-stu-id="13c2f-112">In the left navigation bar, click **Clients**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="13c2f-113">默认情况下, "<STRONG>客户端版本策略</STRONG>" 选项卡处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="13c2f-113">The <STRONG>Client Version Policy</STRONG> tab is selected by default.</span></span>

    
    </div>

4.  <span data-ttu-id="13c2f-114">在 "**客户端版本策略**" 页面上, 执行下列操作之一:</span><span class="sxs-lookup"><span data-stu-id="13c2f-114">On the **Client Version Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="13c2f-115">若要创建客户端版本策略, 请单击 "**新建**", 选择 "**网站策略**"、"**池策略**" 或 "**用户策略**", 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="13c2f-115">To create a client version policy, click **New**, select **Site policy**, **Pool policy**, or **User policy**, and then click **OK**.</span></span>
    
      - <span data-ttu-id="13c2f-116">若要修改全局策略或其他现有的客户端版本策略, 请选择该策略, 单击 "**编辑**", 然后单击 "**显示详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="13c2f-116">To modify the global policy or another existing client version policy, select the policy, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="13c2f-117">在 "**编辑客户端版本策略**" 页面上, 创建或修改规则, 如在[Lync Server 2013 中创建或修改新的客户端版本策略规则](lync-server-2013-create-or-modify-a-new-client-version-policy-rule.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="13c2f-117">On the **Edit Client Version Policy** page, create or modify rules as described in [Create or modify a new client version policy rule in Lync Server 2013](lync-server-2013-create-or-modify-a-new-client-version-policy-rule.md).</span></span>

</div>

<div>

## <a name="creating-or-modifying-client-version-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="13c2f-118">使用 Windows PowerShell Cmdlet 创建或修改客户端版本策略</span><span class="sxs-lookup"><span data-stu-id="13c2f-118">Creating or Modifying Client Version Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="13c2f-119">你可以使用**CsClientVersionPolicy** cmdlet 创建客户端版本策略, 并使用**CsClientVersionPolicy** cmdlet 对其进行修改。</span><span class="sxs-lookup"><span data-stu-id="13c2f-119">You can create client version policies by using the **New-CsClientVersionPolicy** cmdlet, and modify them by using the **Set-CsClientVersionPolicy** cmdlet.</span></span> <span data-ttu-id="13c2f-120">这些 cmdlet 既可以从 Lync Server 2013 管理外壳运行, 也可以从 Windows PowerShell 的远程会话运行。</span><span class="sxs-lookup"><span data-stu-id="13c2f-120">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="13c2f-121">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息, 请参阅 Lync Server Windows PowerShell 博客文章 "快速入门: 使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="13c2f-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-new-site-scoped-client-version-policy"></a><span data-ttu-id="13c2f-122">创建新的网站范围的客户端版本策略</span><span class="sxs-lookup"><span data-stu-id="13c2f-122">To create a new site-scoped client version policy</span></span>

  - <span data-ttu-id="13c2f-123">以下命令将创建应用于 Redmond 网站的新客户端版本策略。</span><span class="sxs-lookup"><span data-stu-id="13c2f-123">The following command creates a new client version policy applied to the Redmond site.</span></span> <span data-ttu-id="13c2f-124">由于没有指定任何其他参数, 新策略将使用默认的客户端版本设置。</span><span class="sxs-lookup"><span data-stu-id="13c2f-124">Because no additional parameters are specified, the new policy will use the default client version settings.</span></span>
    
        New-CsClientVersionPolicy -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-per-user-client-version-policy"></a><span data-ttu-id="13c2f-125">创建新的基于用户的客户端版本策略</span><span class="sxs-lookup"><span data-stu-id="13c2f-125">To create a new per-user client version policy</span></span>

  - <span data-ttu-id="13c2f-126">若要创建每用户策略, 请使用类似下面的命令:</span><span class="sxs-lookup"><span data-stu-id="13c2f-126">To create a per-user policy, use a command similar to this:</span></span>
    
        New-CsClientVersionPolicy -Identity "RedmondClientVersionPolicy"

</div>

<span data-ttu-id="13c2f-127">有关详细信息, 请参阅[CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientVersionPolicy) Cmdlet 和[CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionPolicy) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="13c2f-127">For details, see the Help topics for the [New-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientVersionPolicy) cmdlet and the [Set-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

