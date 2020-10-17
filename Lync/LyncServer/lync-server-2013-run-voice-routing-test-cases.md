---
title: Lync Server 2013：运行语音路由测试用例
description: Lync Server 2013：运行语音路由测试用例。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Run voice routing test cases
ms:assetid: fb4d32df-b9ea-4944-8cd7-a6102c78c465
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413068(v=OCS.15)
ms:contentKeyID: 48185948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e521216a12fba6b78913e7f4a79432809bb6e252
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566788"
---
# <a name="run-voice-routing-test-cases-in-lync-server-2013"></a><span data-ttu-id="61aa6-103">在 Lync Server 2013 中运行语音路由测试用例</span><span class="sxs-lookup"><span data-stu-id="61aa6-103">Run voice routing test cases in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="61aa6-104">_**上次修改的主题：** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="61aa6-104">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="61aa6-105">您可以运行语音路由测试用例套件中的所有测试用例，也可以运行一个或多个选定的测试用例。</span><span class="sxs-lookup"><span data-stu-id="61aa6-105">You can run all of the test cases in your voice routing test case suite, or you can run one or more selected test cases.</span></span>

<div>

## <a name="to-run-all-voice-routing-test-cases"></a><span data-ttu-id="61aa6-106">运行所有语音路由测试用例</span><span class="sxs-lookup"><span data-stu-id="61aa6-106">To run all voice routing test cases</span></span>

1.  <span data-ttu-id="61aa6-107">以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="61aa6-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="61aa6-108">有关详细信息，请参阅 [Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="61aa6-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="61aa6-109">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="61aa6-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="61aa6-110">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="61aa6-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="61aa6-111">在左侧导航栏中，单击“语音路由”\*\*\*\*，然后单击“测试语音路由”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="61aa6-111">In the left navigation bar, click **Voice Routing** and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="61aa6-112">在“测试语音路由”\*\*\*\* 页上，单击“操作”\*\*\*\*，然后单击“运行所有”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="61aa6-112">On the **Test Voice Routing** page, click **Action** and then click **Run all**.</span></span>
    
    <span data-ttu-id="61aa6-p103">“通过/失败”\*\*\*\* 列中会显示每个测试用例的通过状态或失败状态。如果测试用例尚未运行，则“通过/失败”\*\*\*\* 列中会显示 N/A。</span><span class="sxs-lookup"><span data-stu-id="61aa6-p103">The pass or fail status of each test case is shown in the **Pass/fail** column. If a test case has not yet been run, N/A is shown in the **Pass/fail** column.</span></span>

5.  <span data-ttu-id="61aa6-p104">（可选）要查看每个测试用例的详细结果，请双击该测试用例的名称。结果会显示在“编辑测试用例”\*\*\*\* 页右侧的阴影区域中：</span><span class="sxs-lookup"><span data-stu-id="61aa6-p104">(Optional) To see detailed results for each test case, double-click the test case name. Results are shown in the shaded area on the right side of the **Edit Test Case** page:</span></span>
    
    1.  <span data-ttu-id="61aa6-117">**测试结果：** 测试用例运行的整体 pass 或 fail 状态。</span><span class="sxs-lookup"><span data-stu-id="61aa6-117">**Test result:** Overall pass or fail status of the test case run.</span></span>
    
    2.  <span data-ttu-id="61aa6-118">**规范化规则：** 为此测试用例选择的拨号计划中的第一个规范化规则与所拨打的号码相匹配 (" **要测试的数字** " 字段) 中的值。</span><span class="sxs-lookup"><span data-stu-id="61aa6-118">**Normalization rule:** The first normalization rule in the dial plan selected for this test case that matches the dialed number (the value in the **Number to test** field).</span></span>
    
    3.  <span data-ttu-id="61aa6-119">**正常化的数字：** 规范化规则翻译后拨叫的号码的值。</span><span class="sxs-lookup"><span data-stu-id="61aa6-119">**Normalized number:** The value of the dialed number after the normalization rule has translated it.</span></span>
    
    4.  <span data-ttu-id="61aa6-120">**第一个 PSTN 用法：** 在为此测试用例选择的语音策略中，第一个公用电话交换网 (PSTN) 使用情况记录与所拨打的号码相匹配。</span><span class="sxs-lookup"><span data-stu-id="61aa6-120">**First PSTN usage:** The first public switched telephone network (PSTN) usage record in the voice policy selected for this test case that matches the dialed number.</span></span>
    
    5.  <span data-ttu-id="61aa6-121">**第一个路由：** 第一个与所拨打的号码相匹配的 PSTN 用法记录中的第一个语音路由。</span><span class="sxs-lookup"><span data-stu-id="61aa6-121">**First route:** The first voice route in the first PSTN usage record that matches the dialed number.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="61aa6-p105">在语音路由测试用例配置中，“预期 PSTN 用法记录”<STRONG></STRONG>和“预期路由”<STRONG></STRONG>字段是可选的。如果测试用例不指定这些值，则测试结果中对应的字段为空。</span><span class="sxs-lookup"><span data-stu-id="61aa6-p105">The <STRONG>Expected PSTN usage record</STRONG> and <STRONG>Expected route</STRONG> fields are optional in voice routing test case configuration. If the test case does not specify these values, the corresponding field in the test results will be empty.</span></span>

        
        </div>

</div>

<div>

## <a name="to-run-one-or-more-selected-voice-routing-test-cases"></a><span data-ttu-id="61aa6-124">运行一个或多个所选语音路由测试用例</span><span class="sxs-lookup"><span data-stu-id="61aa6-124">To run one or more selected voice routing test cases</span></span>

1.  <span data-ttu-id="61aa6-125">以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="61aa6-125">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="61aa6-126">有关详细信息，请参阅 [Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="61aa6-126">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="61aa6-127">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="61aa6-127">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="61aa6-128">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="61aa6-128">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="61aa6-129">在左侧导航栏中，单击“语音路由”\*\*\*\*，然后单击“测试语音路由”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="61aa6-129">In the left navigation bar, click **Voice Routing**, and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="61aa6-130">在“测试语音路由”\*\*\*\* 页上，单击要运行的测试用例的名称。</span><span class="sxs-lookup"><span data-stu-id="61aa6-130">On the **Test Voice Routing** page, click the names of the test cases that you want to run.</span></span>

5.  <span data-ttu-id="61aa6-131">在“操作”\*\*\*\* 菜单上，单击“运行所选项”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="61aa6-131">On the **Action** menu, click **Run selected**.</span></span>
    
    <span data-ttu-id="61aa6-p108">“通过/失败”\*\*\*\* 列中会显示每个测试用例的通过状态或失败状态。如果测试用例尚未运行，则“通过/失败”\*\*\*\* 列中会显示 N/A。</span><span class="sxs-lookup"><span data-stu-id="61aa6-p108">The pass or fail status of each test case is shown in the **Pass/fail** column. If a test case has not yet been run, N/A is shown in the **Pass/fail** column.</span></span>

6.  <span data-ttu-id="61aa6-p109">（可选）要查看每个测试用例的详细结果，请双击该测试用例的名称。结果会显示在“编辑测试用例”\*\*\*\* 页右侧的阴影区域中：</span><span class="sxs-lookup"><span data-stu-id="61aa6-p109">(Optional) To see detailed results for each test case, double-click the test case name. Results are shown in the shaded area on the right side of the **Edit Test Case** page:</span></span>
    
    1.  <span data-ttu-id="61aa6-136">**测试结果：** 测试用例运行的整体 pass 或 fail 状态。</span><span class="sxs-lookup"><span data-stu-id="61aa6-136">**Test result:** Overall pass or fail status of the test case run.</span></span>
    
    2.  <span data-ttu-id="61aa6-137">**规范化规则：** 为此测试用例选择的拨号计划中的第一个规范化规则与所拨打的号码相匹配 (" **要测试的数字** " 字段) 中的值。</span><span class="sxs-lookup"><span data-stu-id="61aa6-137">**Normalization rule:** The first normalization rule in the dial plan selected for this test case that matches the dialed number (the value in the **Number to test** field).</span></span>
    
    3.  <span data-ttu-id="61aa6-138">**正常化的数字：** 规范化规则翻译后拨叫的号码的值。</span><span class="sxs-lookup"><span data-stu-id="61aa6-138">**Normalized number:** The value of the dialed number after the normalization rule has translated it.</span></span>
    
    4.  <span data-ttu-id="61aa6-139">**第一个 PSTN 用法：** 为此测试用例选择的语音策略中的第一个 PSTN 用法记录与所拨打的号码相匹配。</span><span class="sxs-lookup"><span data-stu-id="61aa6-139">**First PSTN usage:** The first PSTN usage record in the voice policy selected for this test case that matches the dialed number.</span></span>
    
    5.  <span data-ttu-id="61aa6-140">**第一个路由：** 第一个与所拨打的号码相匹配的 PSTN 用法记录中的第一个语音路由。</span><span class="sxs-lookup"><span data-stu-id="61aa6-140">**First route:** The first voice route in the first PSTN usage record that matches the dialed number.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="61aa6-p110">在语音路由测试用例配置中，“预期 PSTN 用法记录”<STRONG></STRONG>和“预期路由”<STRONG></STRONG>字段是可选的。如果测试用例不指定这些值，则测试结果中对应的字段为空。</span><span class="sxs-lookup"><span data-stu-id="61aa6-p110">The <STRONG>Expected PSTN usage record</STRONG> and <STRONG>Expected route</STRONG> fields are optional in voice routing test case configuration. If the test case does not specify these values, the corresponding field in the test results will be empty.</span></span>

        
        </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="61aa6-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="61aa6-143">See Also</span></span>


[<span data-ttu-id="61aa6-144">在 Lync Server 2013 中测试语音路由</span><span class="sxs-lookup"><span data-stu-id="61aa6-144">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
[<span data-ttu-id="61aa6-145">在 Lync Server 2013 中运行语音路由测试</span><span class="sxs-lookup"><span data-stu-id="61aa6-145">Running voice routing tests in Lync Server 2013</span></span>](lync-server-2013-running-voice-routing-tests.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

