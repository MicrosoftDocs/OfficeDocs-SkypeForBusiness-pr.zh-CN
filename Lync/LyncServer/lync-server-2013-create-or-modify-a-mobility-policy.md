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
ms.openlocfilehash: a240c55b4478c5cf5f67a4f0774b1979e884b3b0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207998"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-mobility-policy-in-lync-server-2013"></a><span data-ttu-id="8931e-102">在 Lync Server 2013 中创建或修改移动策略</span><span class="sxs-lookup"><span data-stu-id="8931e-102">Create or modify a mobility policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8931e-103">_**上次修改的主题：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="8931e-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="8931e-104">您可以创建可修改移动策略以允许移动用户使用受支持的移动设备来实现 Lync 功能，例如，即时消息 (IM)、状态和联系人。</span><span class="sxs-lookup"><span data-stu-id="8931e-104">You can create or modify mobility policy to allow mobile users to use supported mobile devices for Lync functionality such as instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="8931e-105">您可以从 Lync Server 2013 控制面板或 Lync Server 2013 命令行管理程序创建或修改移动策略</span><span class="sxs-lookup"><span data-stu-id="8931e-105">You can create or modify mobility policies from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell</span></span>

<div>

## <a name="to-create-a-mobility-policy-with-lync-server-control-panel"></a><span data-ttu-id="8931e-106">使用 Lync Server 控制面板创建移动策略</span><span class="sxs-lookup"><span data-stu-id="8931e-106">To create a mobility policy with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="8931e-107">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="8931e-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8931e-108">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="8931e-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8931e-109">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="8931e-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8931e-110">在左侧导航栏中，单击“客户端”\*\*\*\*，然后单击“移动策略”\*\*\*\* 导航按钮。</span><span class="sxs-lookup"><span data-stu-id="8931e-110">In the left navigation bar, click **Clients**, and then click the **Mobility Policy** navigation button.</span></span>

4.  <span data-ttu-id="8931e-111">在 "**移动策略**" 页上，单击 "**新建**"，然后执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="8931e-111">On the **Mobility Policy** page, click **New**, and do one of the following:</span></span>
    
    1.  <span data-ttu-id="8931e-112">要创建站点移动策略，请依次单击“站点策略”\*\*\*\*、“站点”和“确定”\*\*\*\*，查看默认设置，且如果需要，可做任何更改。</span><span class="sxs-lookup"><span data-stu-id="8931e-112">To create a site mobility policy, click **Site policy**, click a site, click **OK**, review the default settings, and, if you want to, make any changes.</span></span>
    
    2.  <span data-ttu-id="8931e-113">要创建用户移动策略，请单击“用户策略”\*\*\*\*，键入名称，查看默认设置，且如果需要，可做任何更改。</span><span class="sxs-lookup"><span data-stu-id="8931e-113">To create a user mobility policy, click **User policy**, type a name, review the default settings, and if you want to, make any changes.</span></span>

5.  <span data-ttu-id="8931e-114">单击“提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8931e-114">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-a-mobility-policy-with-lync-server-control-panel"></a><span data-ttu-id="8931e-115">使用 Lync Server 控制面板修改移动策略</span><span class="sxs-lookup"><span data-stu-id="8931e-115">To modify a mobility policy with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="8931e-116">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="8931e-116">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8931e-117">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="8931e-117">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8931e-118">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="8931e-118">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8931e-119">在左侧导航栏中，单击“客户端”\*\*\*\*，然后单击“移动策略”\*\*\*\* 导航按钮。</span><span class="sxs-lookup"><span data-stu-id="8931e-119">In the left navigation bar, click **Clients**, and then click the **Mobility Policy** navigation button.</span></span>

4.  <span data-ttu-id="8931e-120">在 "**移动策略**" 页上，单击某个现有移动策略。</span><span class="sxs-lookup"><span data-stu-id="8931e-120">On the **Mobility Policy** page, click one of the existing mobility policies.</span></span>

5.  <span data-ttu-id="8931e-121">在“编辑”\*\*\*\* 菜单上，单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8931e-121">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="8931e-122">编辑任何设置。</span><span class="sxs-lookup"><span data-stu-id="8931e-122">Edit any of the settings.</span></span>

7.  <span data-ttu-id="8931e-123">单击“提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8931e-123">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-external-access-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="8931e-124">使用 Windows PowerShell Cmdlet 创建外部访问策略</span><span class="sxs-lookup"><span data-stu-id="8931e-124">Creating External Access Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="8931e-125">您可以使用 Windows PowerShell 和**set-csmobilitypolicy** cmdlet 创建移动策略（在站点范围或每用户范围内）。</span><span class="sxs-lookup"><span data-stu-id="8931e-125">You can create mobility policies (at the site scope or the per-user scope) by using Windows PowerShell and the **New-CsMobilityPolicy** cmdlet.</span></span> <span data-ttu-id="8931e-126">另外，可以使用 **Set-CsMobilityPolicy** cmdlet 修改任何现有策略，包括全局策略。</span><span class="sxs-lookup"><span data-stu-id="8931e-126">Additionally, you can use the **Set-CsMobilityPolicy** cmdlet to modify any of your existing policies, including the global policy.</span></span> <span data-ttu-id="8931e-127">这些 cmdlet 可从 Lync Server 2013 命令行管理程序或 Windows PowerShell 的远程会话中运行。</span><span class="sxs-lookup"><span data-stu-id="8931e-127">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="8931e-128">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。</span><span class="sxs-lookup"><span data-stu-id="8931e-128">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-mobility-policy-at-the-site-scope"></a><span data-ttu-id="8931e-129">在站点范围创建移动策略</span><span class="sxs-lookup"><span data-stu-id="8931e-129">To create a mobility policy at the site scope</span></span>

  - <span data-ttu-id="8931e-130">此命令可用于为 Redmond 站点创建新的移动策略：</span><span class="sxs-lookup"><span data-stu-id="8931e-130">This command creates a new mobility policy for the Redmond site:</span></span>
    
        New-CsMobilityPolicy -Identity "site:Redmond"
    
    <span data-ttu-id="8931e-131">因为在上述命令中没有指定任何参数（不是必需的 Identity 参数），所以这些策略会为其所有属性使用默认值。</span><span class="sxs-lookup"><span data-stu-id="8931e-131">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the policies will use the default values for all its properties.</span></span>

</div>

<div>

## <a name="to-create-a-mobility-policy-at-the-per-user-scope"></a><span data-ttu-id="8931e-132">在每用户范围创建移动策略</span><span class="sxs-lookup"><span data-stu-id="8931e-132">To create a mobility policy at the per-user scope</span></span>

  - <span data-ttu-id="8931e-133">要在每用户作用域创建移动策略，请为该策略指定唯一身份：</span><span class="sxs-lookup"><span data-stu-id="8931e-133">To create a mobility policy at the per-user scope, specify a unique Identity for the policy:</span></span>
    
        New-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-a-mobility-policy"></a><span data-ttu-id="8931e-134">创建移动策略时更改单个属性值</span><span class="sxs-lookup"><span data-stu-id="8931e-134">To change a single property value when creating a mobility policy</span></span>

  - <span data-ttu-id="8931e-p105">要创建使用不同属性值的策略，请包括属性参数和属性值。例如，此命令可创建禁用单位电话的移动策略：</span><span class="sxs-lookup"><span data-stu-id="8931e-p105">To create policies that use different property values, include the appropriate parameter and parameter value. For example, this command creates mobility policy that disables Call via Work:</span></span>
    
        New-CsMobilityPolicy -Identity "site:Redmond" -EnableOutsideVoice $False

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-a-mobility-policy"></a><span data-ttu-id="8931e-137">创建移动策略时更改多个属性值</span><span class="sxs-lookup"><span data-stu-id="8931e-137">To change multiple property values when creating a mobility policy</span></span>

  - <span data-ttu-id="8931e-p106">通过包括多个参数可修改多个属性值。例如，此命令可用于创建禁用移动和单位电话的策略：</span><span class="sxs-lookup"><span data-stu-id="8931e-p106">Multiple property values can be modified by including multiple parameters. For example, this command creates a policy that disables both mobility and Call via Work:</span></span>
    
        New-CsMobilityPolicy "site:Redmond" -EnableMobility $False -EnableOutsideVoice $False

</div>

<span data-ttu-id="8931e-140">有关详细信息，请参阅 [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy) 和 [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="8931e-140">For details, see the Help topic for the [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy) and the [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy) cmdlets.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8931e-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8931e-141">See Also</span></span>


[<span data-ttu-id="8931e-142">在 Lync Server 2013 中配置移动策略</span><span class="sxs-lookup"><span data-stu-id="8931e-142">Configuring mobility policy in Lync Server 2013</span></span>](lync-server-2013-configuring-mobility-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

