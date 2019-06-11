---
title: 'Lync Server 2013: 运行语音路由测试案例'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Run voice routing test cases
ms:assetid: fb4d32df-b9ea-4944-8cd7-a6102c78c465
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413068(v=OCS.15)
ms:contentKeyID: 48185948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0cded8f3bf44388103ccf5a33507973817de45ec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822396"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="run-voice-routing-test-cases-in-lync-server-2013"></a><span data-ttu-id="19288-102">在 Lync Server 2013 中运行语音路由测试案例</span><span class="sxs-lookup"><span data-stu-id="19288-102">Run voice routing test cases in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="19288-103">_**主题上次修改时间:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="19288-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="19288-104">你可以在你的语音路由测试案例套件中运行所有测试用例, 也可以运行一个或多个选定的测试用例。</span><span class="sxs-lookup"><span data-stu-id="19288-104">You can run all of the test cases in your voice routing test case suite, or you can run one or more selected test cases.</span></span>

<div>

## <a name="to-run-all-voice-routing-test-cases"></a><span data-ttu-id="19288-105">运行所有语音路由测试案例</span><span class="sxs-lookup"><span data-stu-id="19288-105">To run all voice routing test cases</span></span>

1.  <span data-ttu-id="19288-106">以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="19288-106">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="19288-107">有关详细信息, 请参阅[在 Lync Server 2013 中委派设置权限](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="19288-107">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="19288-108">打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="19288-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="19288-109">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="19288-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="19288-110">在左侧导航栏中, 单击 "**语音路由**", 然后单击 "**测试语音路由**"。</span><span class="sxs-lookup"><span data-stu-id="19288-110">In the left navigation bar, click **Voice Routing** and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="19288-111">在 "**测试语音路由**" 页面上, 单击 "**操作**", 然后单击 "**全部运行**"。</span><span class="sxs-lookup"><span data-stu-id="19288-111">On the **Test Voice Routing** page, click **Action** and then click **Run all**.</span></span>
    
    <span data-ttu-id="19288-112">每个测试用例的 "通过" 或 "失败" 状态显示在 "**通过/失败**" 列中。</span><span class="sxs-lookup"><span data-stu-id="19288-112">The pass or fail status of each test case is shown in the **Pass/fail** column.</span></span> <span data-ttu-id="19288-113">如果测试用例尚未运行, 则 "**通过/失败**" 列中将显示 "N/a"。</span><span class="sxs-lookup"><span data-stu-id="19288-113">If a test case has not yet been run, N/A is shown in the **Pass/fail** column.</span></span>

5.  <span data-ttu-id="19288-114">可选若要查看每个测试用例的详细结果, 请双击测试用例名称。</span><span class="sxs-lookup"><span data-stu-id="19288-114">(Optional) To see detailed results for each test case, double-click the test case name.</span></span> <span data-ttu-id="19288-115">结果将显示在**编辑测试用例**页面右侧的着色区域中:</span><span class="sxs-lookup"><span data-stu-id="19288-115">Results are shown in the shaded area on the right side of the **Edit Test Case** page:</span></span>
    
    1.  <span data-ttu-id="19288-116">**测试结果:** 测试用例运行的整体传递或失败状态。</span><span class="sxs-lookup"><span data-stu-id="19288-116">**Test result:** Overall pass or fail status of the test case run.</span></span>
    
    2.  <span data-ttu-id="19288-117">**规范化规则:** 为此测试用例选择的拨号计划中的第一个规范化规则与已拨打的号码相匹配 ("**要测试的号码**" 字段中的值)。</span><span class="sxs-lookup"><span data-stu-id="19288-117">**Normalization rule:** The first normalization rule in the dial plan selected for this test case that matches the dialed number (the value in the **Number to test** field).</span></span>
    
    3.  <span data-ttu-id="19288-118">**规范化数字:** 规范化规则翻译后拨叫的号码的值。</span><span class="sxs-lookup"><span data-stu-id="19288-118">**Normalized number:** The value of the dialed number after the normalization rule has translated it.</span></span>
    
    4.  <span data-ttu-id="19288-119">**第一 PSTN 使用:** 为此测试用例选择的、与所拨号码匹配的语音策略中的第一个公共交换电话网络 (PSTN) 使用记录。</span><span class="sxs-lookup"><span data-stu-id="19288-119">**First PSTN usage:** The first public switched telephone network (PSTN) usage record in the voice policy selected for this test case that matches the dialed number.</span></span>
    
    5.  <span data-ttu-id="19288-120">**第一条路线:** 第一条在第一条 PSTN 使用记录中与所拨号码相匹配的第一个语音路线。</span><span class="sxs-lookup"><span data-stu-id="19288-120">**First route:** The first voice route in the first PSTN usage record that matches the dialed number.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="19288-121">"<STRONG>预期 PSTN 使用记录</STRONG>" 和 "<STRONG>预期路由</STRONG>" 字段在语音路由测试案例配置中是可选的。</span><span class="sxs-lookup"><span data-stu-id="19288-121">The <STRONG>Expected PSTN usage record</STRONG> and <STRONG>Expected route</STRONG> fields are optional in voice routing test case configuration.</span></span> <span data-ttu-id="19288-122">如果测试用例未指定这些值, 则测试结果中的对应字段将为空。</span><span class="sxs-lookup"><span data-stu-id="19288-122">If the test case does not specify these values, the corresponding field in the test results will be empty.</span></span>

        
        </div>

</div>

<div>

## <a name="to-run-one-or-more-selected-voice-routing-test-cases"></a><span data-ttu-id="19288-123">运行一个或多个所选的语音路由测试案例</span><span class="sxs-lookup"><span data-stu-id="19288-123">To run one or more selected voice routing test cases</span></span>

1.  <span data-ttu-id="19288-124">以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="19288-124">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="19288-125">有关详细信息, 请参阅[在 Lync Server 2013 中委派设置权限](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="19288-125">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="19288-126">打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="19288-126">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="19288-127">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="19288-127">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="19288-128">在左侧导航栏中, 单击 "**语音路由**", 然后单击 "**测试语音路由**"。</span><span class="sxs-lookup"><span data-stu-id="19288-128">In the left navigation bar, click **Voice Routing**, and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="19288-129">在 "**测试语音路由**" 页面上, 单击要运行的测试用例的名称。</span><span class="sxs-lookup"><span data-stu-id="19288-129">On the **Test Voice Routing** page, click the names of the test cases that you want to run.</span></span>

5.  <span data-ttu-id="19288-130">在 "**操作**" 菜单上, 单击 "**运行所选**"。</span><span class="sxs-lookup"><span data-stu-id="19288-130">On the **Action** menu, click **Run selected**.</span></span>
    
    <span data-ttu-id="19288-131">每个测试用例的 "通过" 或 "失败" 状态显示在 "**通过/失败**" 列中。</span><span class="sxs-lookup"><span data-stu-id="19288-131">The pass or fail status of each test case is shown in the **Pass/fail** column.</span></span> <span data-ttu-id="19288-132">如果测试用例尚未运行, 则 "**通过/失败**" 列中将显示 "N/a"。</span><span class="sxs-lookup"><span data-stu-id="19288-132">If a test case has not yet been run, N/A is shown in the **Pass/fail** column.</span></span>

6.  <span data-ttu-id="19288-133">可选若要查看每个测试用例的详细结果, 请双击测试用例名称。</span><span class="sxs-lookup"><span data-stu-id="19288-133">(Optional) To see detailed results for each test case, double-click the test case name.</span></span> <span data-ttu-id="19288-134">结果将显示在**编辑测试用例**页面右侧的着色区域中:</span><span class="sxs-lookup"><span data-stu-id="19288-134">Results are shown in the shaded area on the right side of the **Edit Test Case** page:</span></span>
    
    1.  <span data-ttu-id="19288-135">**测试结果:** 测试用例运行的整体传递或失败状态。</span><span class="sxs-lookup"><span data-stu-id="19288-135">**Test result:** Overall pass or fail status of the test case run.</span></span>
    
    2.  <span data-ttu-id="19288-136">**规范化规则:** 为此测试用例选择的拨号计划中的第一个规范化规则与已拨打的号码相匹配 ("**要测试的号码**" 字段中的值)。</span><span class="sxs-lookup"><span data-stu-id="19288-136">**Normalization rule:** The first normalization rule in the dial plan selected for this test case that matches the dialed number (the value in the **Number to test** field).</span></span>
    
    3.  <span data-ttu-id="19288-137">**规范化数字:** 规范化规则翻译后拨叫的号码的值。</span><span class="sxs-lookup"><span data-stu-id="19288-137">**Normalized number:** The value of the dialed number after the normalization rule has translated it.</span></span>
    
    4.  <span data-ttu-id="19288-138">**第一 PSTN 使用:** 为此测试用例选择的、与所拨号码匹配的语音策略中的第一条 PSTN 使用记录。</span><span class="sxs-lookup"><span data-stu-id="19288-138">**First PSTN usage:** The first PSTN usage record in the voice policy selected for this test case that matches the dialed number.</span></span>
    
    5.  <span data-ttu-id="19288-139">**第一条路线:** 第一条在第一条 PSTN 使用记录中与所拨号码相匹配的第一个语音路线。</span><span class="sxs-lookup"><span data-stu-id="19288-139">**First route:** The first voice route in the first PSTN usage record that matches the dialed number.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="19288-140">"<STRONG>预期 PSTN 使用记录</STRONG>" 和 "<STRONG>预期路由</STRONG>" 字段在语音路由测试案例配置中是可选的。</span><span class="sxs-lookup"><span data-stu-id="19288-140">The <STRONG>Expected PSTN usage record</STRONG> and <STRONG>Expected route</STRONG> fields are optional in voice routing test case configuration.</span></span> <span data-ttu-id="19288-141">如果测试用例未指定这些值, 则测试结果中的对应字段将为空。</span><span class="sxs-lookup"><span data-stu-id="19288-141">If the test case does not specify these values, the corresponding field in the test results will be empty.</span></span>

        
        </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="19288-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="19288-142">See Also</span></span>


[<span data-ttu-id="19288-143">在 Lync Server 2013 中测试语音路由</span><span class="sxs-lookup"><span data-stu-id="19288-143">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
[<span data-ttu-id="19288-144">在 Lync Server 2013 中运行语音路由测试</span><span class="sxs-lookup"><span data-stu-id="19288-144">Running voice routing tests in Lync Server 2013</span></span>](lync-server-2013-running-voice-routing-tests.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

