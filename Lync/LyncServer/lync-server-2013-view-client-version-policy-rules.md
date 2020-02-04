---
title: Lync Server 2013：查看客户端版本策略规则
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View client version policy rules
ms:assetid: f3a0215f-f72f-4e9b-a07b-25858dc4203a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ923060(v=OCS.15)
ms:contentKeyID: 50675350
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b64dce1b74be8ed1aed0c5d1f515910341f57c52
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757466"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-client-version-policy-rules-in-lync-server-2013"></a><span data-ttu-id="b69ba-102">在 Lync Server 2013 中查看客户端版本策略规则</span><span class="sxs-lookup"><span data-stu-id="b69ba-102">View client version policy rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b69ba-103">_**主题上次修改时间：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="b69ba-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="b69ba-104">客户端版本策略由一组客户端版本策略规则组成。</span><span class="sxs-lookup"><span data-stu-id="b69ba-104">A client version policy is made up of a set of client version policy rules.</span></span> <span data-ttu-id="b69ba-105">这些规则定义在用户尝试使用特定客户端和客户端版本登录时应采取的操作。</span><span class="sxs-lookup"><span data-stu-id="b69ba-105">These rules define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span> <span data-ttu-id="b69ba-106">你可以从 Lync Server 2013 控制面板或 Lync Server 2013 管理外壳查看客户端版本策略规则。</span><span class="sxs-lookup"><span data-stu-id="b69ba-106">You can view client version policy rules from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-view-client-version-policy-rules-by-using-lync-server-control-panel"></a><span data-ttu-id="b69ba-107">使用 Lync Server "控制面板" 查看客户端版本策略规则</span><span class="sxs-lookup"><span data-stu-id="b69ba-107">To view client version policy rules by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="b69ba-108">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="b69ba-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b69ba-109">打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="b69ba-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b69ba-110">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="b69ba-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b69ba-111">在左侧导航栏中，单击 "**客户端**"，然后单击 "**客户端版本策略**导航" 按钮。</span><span class="sxs-lookup"><span data-stu-id="b69ba-111">In the left navigation bar, click **Clients**, and then click the **Client Version Policy** navigation button.</span></span>

4.  <span data-ttu-id="b69ba-112">在 "**客户端版本策略**" 页面上，双击要查看的客户端版本策略。</span><span class="sxs-lookup"><span data-stu-id="b69ba-112">On the **Client Version Policy** page, double-click a client version policy you want to view.</span></span>

5.  <span data-ttu-id="b69ba-113">这些规则将显示在 "**编辑客户端版本策略**" 页面上。</span><span class="sxs-lookup"><span data-stu-id="b69ba-113">The rules appear on the **Edit Client Version Policy** page.</span></span> <span data-ttu-id="b69ba-114">若要查看规则的详细信息，请选择规则，然后单击 "**显示详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="b69ba-114">To view the details for a rule, select the rule, and then click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-client-version-policy-rules-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="b69ba-115">使用 Windows PowerShell Cmdlet 查看客户端版本策略规则</span><span class="sxs-lookup"><span data-stu-id="b69ba-115">Viewing Client Version Policy Rules by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="b69ba-116">你可以使用 Lync Server 命令行管理程序和**CsClientVersionPolicyRule** cmdlet 查看客户端版本策略规则。</span><span class="sxs-lookup"><span data-stu-id="b69ba-116">You can view client version policy rules by using Lync Server Management Shell and the **Get-CsClientVersionPolicyRule** cmdlet.</span></span> <span data-ttu-id="b69ba-117">此 cmdlet 既可以从 Lync Server 2013 管理外壳运行，也可以从 Windows PowerShell 的远程会话运行。</span><span class="sxs-lookup"><span data-stu-id="b69ba-117">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="b69ba-118">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="b69ba-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-client-version-policy-rules"></a><span data-ttu-id="b69ba-119">查看客户端版本策略规则</span><span class="sxs-lookup"><span data-stu-id="b69ba-119">To view client version policy rules</span></span>

  - <span data-ttu-id="b69ba-120">若要查看客户端版本策略规则，请在 Lync Server 命令行管理程序中键入以下命令，然后按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="b69ba-120">To view the client version policy rules, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsClientVersionPolicyRule
    
    <span data-ttu-id="b69ba-121">这将针对每个配置的规则返回类似于以下内容的信息：</span><span class="sxs-lookup"><span data-stu-id="b69ba-121">That will return information similar to this for each configured rule:</span></span>
    
        Identity          : Global/2336c611-a243-4c5d-994b-eea8a524d0e4
        Priority          : 0
        RuleId            : 2336c611-a243-4c5d-994b-eea8a524d0e4
        Description       :
        Action            : Block
        ActionUrl         :
        MajorVersion      : 1
        MinorVersion      : 3
        BuildNumber       :
        QfeNumber         :
        UserAgent         : RTC
        UserAgentFullName :
        Enabled           : True
        CompareOp         : LEQ

</div>

<span data-ttu-id="b69ba-122">有关详细信息，请参阅[CsClientVersionPolicyRule](https://docs.microsoft.com/powershell/module/skype/Get-CsClientVersionPolicyRule) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="b69ba-122">For details, see the help topic for the [Get-CsClientVersionPolicyRule](https://docs.microsoft.com/powershell/module/skype/Get-CsClientVersionPolicyRule) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

