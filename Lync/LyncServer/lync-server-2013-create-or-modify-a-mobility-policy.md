---
title: Lync Server 2013：创建或修改移动策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a mobility policy
ms:assetid: fc2dfea0-2215-440d-9f4b-7c985da29211
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721946(v=OCS.15)
ms:contentKeyID: 49733884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f64e74b389b268027e06b2f4103b0c828c5be6f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758046"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-mobility-policy-in-lync-server-2013"></a><span data-ttu-id="57cb2-102">在 Lync Server 2013 中创建或修改移动策略</span><span class="sxs-lookup"><span data-stu-id="57cb2-102">Create or modify a mobility policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="57cb2-103">_**主题上次修改时间：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="57cb2-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="57cb2-104">你可以创建或修改移动策略，以允许移动用户为 Lync 功能使用支持的移动设备，例如即时消息（IM）、状态和联系人。</span><span class="sxs-lookup"><span data-stu-id="57cb2-104">You can create or modify mobility policy to allow mobile users to use supported mobile devices for Lync functionality such as instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="57cb2-105">可以从 Lync Server 2013 控制面板或 Lync Server 2013 管理外壳程序创建或修改移动策略</span><span class="sxs-lookup"><span data-stu-id="57cb2-105">You can create or modify mobility policies from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell</span></span>

<div>

## <a name="to-create-a-mobility-policy-with-lync-server-control-panel"></a><span data-ttu-id="57cb2-106">使用 Lync Server "控制面板" 创建移动策略</span><span class="sxs-lookup"><span data-stu-id="57cb2-106">To create a mobility policy with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="57cb2-107">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="57cb2-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="57cb2-108">打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="57cb2-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="57cb2-109">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="57cb2-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="57cb2-110">在左侧导航栏中，单击 "**客户端**"，然后单击 "**移动策略**导航" 按钮。</span><span class="sxs-lookup"><span data-stu-id="57cb2-110">In the left navigation bar, click **Clients**, and then click the **Mobility Policy** navigation button.</span></span>

4.  <span data-ttu-id="57cb2-111">在 "**移动策略**" 页面上，单击 "**新建**"，然后执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="57cb2-111">On the **Mobility Policy** page, click **New**, and do one of the following:</span></span>
    
    1.  <span data-ttu-id="57cb2-112">若要创建网站移动策略，请单击 "**网站策略**"，单击网站，单击 **"确定**"，查看默认设置，如果需要，可进行任何更改。</span><span class="sxs-lookup"><span data-stu-id="57cb2-112">To create a site mobility policy, click **Site policy**, click a site, click **OK**, review the default settings, and, if you want to, make any changes.</span></span>
    
    2.  <span data-ttu-id="57cb2-113">若要创建用户移动策略，请单击 "**用户策略**"，键入名称，查看默认设置，如果需要，请进行任何更改。</span><span class="sxs-lookup"><span data-stu-id="57cb2-113">To create a user mobility policy, click **User policy**, type a name, review the default settings, and if you want to, make any changes.</span></span>

5.  <span data-ttu-id="57cb2-114">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="57cb2-114">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-a-mobility-policy-with-lync-server-control-panel"></a><span data-ttu-id="57cb2-115">使用 Lync Server "控制面板" 修改移动策略</span><span class="sxs-lookup"><span data-stu-id="57cb2-115">To modify a mobility policy with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="57cb2-116">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="57cb2-116">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="57cb2-117">打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="57cb2-117">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="57cb2-118">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="57cb2-118">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="57cb2-119">在左侧导航栏中，单击 "**客户端**"，然后单击 "**移动策略**导航" 按钮。</span><span class="sxs-lookup"><span data-stu-id="57cb2-119">In the left navigation bar, click **Clients**, and then click the **Mobility Policy** navigation button.</span></span>

4.  <span data-ttu-id="57cb2-120">在 "**移动策略**" 页面上，单击现有移动策略之一。</span><span class="sxs-lookup"><span data-stu-id="57cb2-120">On the **Mobility Policy** page, click one of the existing mobility policies.</span></span>

5.  <span data-ttu-id="57cb2-121">在“编辑”\*\*\*\* 菜单上，单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="57cb2-121">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="57cb2-122">编辑任何设置。</span><span class="sxs-lookup"><span data-stu-id="57cb2-122">Edit any of the settings.</span></span>

7.  <span data-ttu-id="57cb2-123">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="57cb2-123">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-external-access-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="57cb2-124">使用 Windows PowerShell Cmdlet 创建外部访问策略</span><span class="sxs-lookup"><span data-stu-id="57cb2-124">Creating External Access Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="57cb2-125">你可以使用 Windows PowerShell 和**CsMobilityPolicy** cmdlet 创建移动策略（在网站范围或每用户范围内）。</span><span class="sxs-lookup"><span data-stu-id="57cb2-125">You can create mobility policies (at the site scope or the per-user scope) by using Windows PowerShell and the **New-CsMobilityPolicy** cmdlet.</span></span> <span data-ttu-id="57cb2-126">此外，你可以使用**CsMobilityPolicy** cmdlet 修改你的任何现有策略，包括全局策略。</span><span class="sxs-lookup"><span data-stu-id="57cb2-126">Additionally, you can use the **Set-CsMobilityPolicy** cmdlet to modify any of your existing policies, including the global policy.</span></span> <span data-ttu-id="57cb2-127">这些 cmdlet 既可以从 Lync Server 2013 管理外壳运行，也可以从 Windows PowerShell 的远程会话运行。</span><span class="sxs-lookup"><span data-stu-id="57cb2-127">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="57cb2-128">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="57cb2-128">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-mobility-policy-at-the-site-scope"></a><span data-ttu-id="57cb2-129">在网站范围内创建移动策略</span><span class="sxs-lookup"><span data-stu-id="57cb2-129">To create a mobility policy at the site scope</span></span>

  - <span data-ttu-id="57cb2-130">此命令为 Redmond 网站创建新的移动策略：</span><span class="sxs-lookup"><span data-stu-id="57cb2-130">This command creates a new mobility policy for the Redmond site:</span></span>
    
        New-CsMobilityPolicy -Identity "site:Redmond"
    
    <span data-ttu-id="57cb2-131">由于前面的命令中未指定任何参数（强制标识参数除外），因此策略将对其所有属性使用默认值。</span><span class="sxs-lookup"><span data-stu-id="57cb2-131">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the policies will use the default values for all its properties.</span></span>

</div>

<div>

## <a name="to-create-a-mobility-policy-at-the-per-user-scope"></a><span data-ttu-id="57cb2-132">在每用户范围内创建移动策略</span><span class="sxs-lookup"><span data-stu-id="57cb2-132">To create a mobility policy at the per-user scope</span></span>

  - <span data-ttu-id="57cb2-133">若要在每用户范围内创建移动策略，请为策略指定唯一标识：</span><span class="sxs-lookup"><span data-stu-id="57cb2-133">To create a mobility policy at the per-user scope, specify a unique Identity for the policy:</span></span>
    
        New-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-a-mobility-policy"></a><span data-ttu-id="57cb2-134">创建移动策略时更改单个属性值</span><span class="sxs-lookup"><span data-stu-id="57cb2-134">To change a single property value when creating a mobility policy</span></span>

  - <span data-ttu-id="57cb2-135">若要创建使用不同属性值的策略，请包含相应的参数和参数值。</span><span class="sxs-lookup"><span data-stu-id="57cb2-135">To create policies that use different property values, include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="57cb2-136">例如，此命令将创建通过工作禁用呼叫的移动策略：</span><span class="sxs-lookup"><span data-stu-id="57cb2-136">For example, this command creates mobility policy that disables Call via Work:</span></span>
    
        New-CsMobilityPolicy -Identity "site:Redmond" -EnableOutsideVoice $False

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-a-mobility-policy"></a><span data-ttu-id="57cb2-137">创建移动策略时更改多个属性值</span><span class="sxs-lookup"><span data-stu-id="57cb2-137">To change multiple property values when creating a mobility policy</span></span>

  - <span data-ttu-id="57cb2-138">可以通过包含多个参数来修改多个属性值。</span><span class="sxs-lookup"><span data-stu-id="57cb2-138">Multiple property values can be modified by including multiple parameters.</span></span> <span data-ttu-id="57cb2-139">例如，此命令将创建一个策略，该策略通过工作禁用移动和呼叫：</span><span class="sxs-lookup"><span data-stu-id="57cb2-139">For example, this command creates a policy that disables both mobility and Call via Work:</span></span>
    
        New-CsMobilityPolicy "site:Redmond" -EnableMobility $False -EnableOutsideVoice $False

</div>

<span data-ttu-id="57cb2-140">有关详细信息，请参阅[新的-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy)和[CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="57cb2-140">For details, see the Help topic for the [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy) and the [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy) cmdlets.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="57cb2-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="57cb2-141">See Also</span></span>


[<span data-ttu-id="57cb2-142">在 Lync Server 2013 中配置移动策略</span><span class="sxs-lookup"><span data-stu-id="57cb2-142">Configuring mobility policy in Lync Server 2013</span></span>](lync-server-2013-configuring-mobility-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

