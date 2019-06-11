---
title: Lync Server 2013：创建语音路由测试用例
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a voice routing test case
ms:assetid: 43a07a5b-2f20-462a-81e5-d628c18391e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425935(v=OCS.15)
ms:contentKeyID: 48183979
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a98e8b9400b0a268474429ad464b1aef7bbbe56
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830856"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-voice-routing-test-case-in-lync-server-2013"></a><span data-ttu-id="3390e-102">在 Lync Server 2013 中创建语音路由测试用例</span><span class="sxs-lookup"><span data-stu-id="3390e-102">Create a voice routing test case in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3390e-103">_**主题上次修改时间:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="3390e-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<div>

## <a name="to-create-a-test-case"></a><span data-ttu-id="3390e-104">创建测试用例</span><span class="sxs-lookup"><span data-stu-id="3390e-104">To create a test case</span></span>

1.  <span data-ttu-id="3390e-105">以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="3390e-105">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="3390e-106">有关详细信息, 请参阅[在 Lync Server 2013 中委派设置权限](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="3390e-106">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="3390e-107">打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="3390e-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3390e-108">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="3390e-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3390e-109">在左侧导航栏中, 单击 "**语音路由**", 然后单击 "**测试语音路由**"。</span><span class="sxs-lookup"><span data-stu-id="3390e-109">In the left navigation bar, click **Voice Routing** and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="3390e-110">在 "**测试语音路由**" 页面上, 单击 "**新建**" 以创建新的测试用例。</span><span class="sxs-lookup"><span data-stu-id="3390e-110">On the **Test Voice Routing** page, click **New** to create a new test case.</span></span>

5.  <span data-ttu-id="3390e-111">在 "**名称**" 中, 为测试用例键入一个唯一名称。</span><span class="sxs-lookup"><span data-stu-id="3390e-111">In **Name**, type in a unique name for the test case.</span></span>
    
    <span data-ttu-id="3390e-112">该名称必须在企业语音部署中的所有语音路由测试案例中是唯一的。</span><span class="sxs-lookup"><span data-stu-id="3390e-112">The name must be unique among all voice routing test cases in your Enterprise Voice deployment.</span></span> <span data-ttu-id="3390e-113">它的长度最多为32个字符, 并且可以包含任何字母数字字符, 除了反斜杠 (\\)、句号 (.) 或下划线 (\_)。</span><span class="sxs-lookup"><span data-stu-id="3390e-113">It can be up to 32 characters in length and may contain any alphanumeric characters, in addition to the backslash (\\), period (.), or underscore (\_).</span></span>

6.  <span data-ttu-id="3390e-114">在 "**要测试的已拨号码**" 中, 键入要用于测试为此测试用例指定的路由配置的已拨号码。</span><span class="sxs-lookup"><span data-stu-id="3390e-114">In **Dialed number to test**, type in the dialed number that you want to use to test the routing configuration that you specify for this test case.</span></span> <span data-ttu-id="3390e-115">根据拨号计划、路由和语音策略, 此数字将标准化并显示为输出。</span><span class="sxs-lookup"><span data-stu-id="3390e-115">Based on the dial plan, route, and voice policy, this number will be normalized and displayed as output.</span></span>

7.  <span data-ttu-id="3390e-116">在 "**拨号计划**" 列表中, 选择运行测试时要使用的拨号计划。</span><span class="sxs-lookup"><span data-stu-id="3390e-116">In the **Dial Plan** list, select the dial plan to use when running the test.</span></span> <span data-ttu-id="3390e-117">默认值为全局拨号计划。</span><span class="sxs-lookup"><span data-stu-id="3390e-117">Default is the Global dial plan.</span></span>

8.  <span data-ttu-id="3390e-118">在 "**语音策略**" 列表中, 选择运行测试时要使用的语音策略。</span><span class="sxs-lookup"><span data-stu-id="3390e-118">In the **Voice Policy** list, select the voice policy to use when running the test.</span></span> <span data-ttu-id="3390e-119">默认值为全局语音策略。</span><span class="sxs-lookup"><span data-stu-id="3390e-119">Default is the Global voice policy.</span></span>

9.  <span data-ttu-id="3390e-120">在 "**预期翻译**" 中, 按照你希望在翻译后查看的格式键入电话号码。</span><span class="sxs-lookup"><span data-stu-id="3390e-120">In **Expected translation**, type in the phone number in the format you expect to see it after translation.</span></span> <span data-ttu-id="3390e-121">这是在所选拨号计划中匹配的第一个规范化规则之后, 你正在测试的电话号码的值。</span><span class="sxs-lookup"><span data-stu-id="3390e-121">This is the value of the phone number that you are testing after it has been translated by the first normalization rule that matches in the selected dial plan.</span></span> <span data-ttu-id="3390e-122">当你运行测试用例时, 如果你测试的数字未导致**预期转换**中的值, 则测试失败。</span><span class="sxs-lookup"><span data-stu-id="3390e-122">When you run the test case, if the number you are testing does not result in the value in **Expected translation**, the test fails.</span></span>

10. <span data-ttu-id="3390e-123">可选在 "**预期的 PSTN 使用情况**" 列表中, 你可以选择你希望在运行测试用例时使用的公共交换电话网络 (PSTN) 使用记录 (基于指定的拨号计划和语音策略)。</span><span class="sxs-lookup"><span data-stu-id="3390e-123">(Optional) In the **Expected PSTN usage** list, you can select the public switched telephone network (PSTN) usage record that you expect to be used when you run the test case, based on the specified dial plan and voice policy.</span></span> <span data-ttu-id="3390e-124">如果使用不同的 PSTN 使用记录, 测试将失败。</span><span class="sxs-lookup"><span data-stu-id="3390e-124">If a different PSTN usage record is used, the test fails.</span></span>

11. <span data-ttu-id="3390e-125">可选在 "**预期的路由**" 列表中, 你可以根据指定的拨号计划和语音策略选择你希望在运行测试用例时使用的语音路线。</span><span class="sxs-lookup"><span data-stu-id="3390e-125">(Optional) In the **Expected route** list, you can select the voice route that you expect to be used when you run the test case, based on the specified dial plan and voice policy.</span></span> <span data-ttu-id="3390e-126">如果使用不同的语音路由, 测试将失败。</span><span class="sxs-lookup"><span data-stu-id="3390e-126">If a different voice route is used, the test fails.</span></span>

12. <span data-ttu-id="3390e-127">可选单击 "**运行**" 以运行测试用例。</span><span class="sxs-lookup"><span data-stu-id="3390e-127">(Optional) Click **Run** to run the test case.</span></span> <span data-ttu-id="3390e-128">结果将显示在页面的右侧面板中。</span><span class="sxs-lookup"><span data-stu-id="3390e-128">The results are shown in the right panel of the page.</span></span>

13. <span data-ttu-id="3390e-129">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="3390e-129">Click **OK**.</span></span>

14. <span data-ttu-id="3390e-130">单击“提交”\*\*\*\*，然后单击“全部提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3390e-130">Click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3390e-131">创建语音路由测试用例时, 必须运行 "<STRONG>全部提交</STRONG>" 命令以发布配置更改。</span><span class="sxs-lookup"><span data-stu-id="3390e-131">Whenever you create a voice routing test case, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="3390e-132">有关详细信息, 请参阅操作文档中的<A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 中的 "发布待处理的语音路由配置更改"</A> 。</span><span class="sxs-lookup"><span data-stu-id="3390e-132">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>
    
    <span data-ttu-id="3390e-133">如果测试中使用的拨号计划规范化以加号 (例如 + 12065551219) 开头的电话号码, 则该计划可能会导致语音路由测试失败。</span><span class="sxs-lookup"><span data-stu-id="3390e-133">If the dial plan being employed in the test normalizes phone numbers that begin with a plus sign (for example, +12065551219), that plan might cause the voice routing test to fail.</span></span> <span data-ttu-id="3390e-134">(拨号计划和语音路由将正常工作; 事实上, CsDialPlan 将成功。</span><span class="sxs-lookup"><span data-stu-id="3390e-134">(The dial plan and the voice route will work; in fact, Test-CsDialPlan will succeed.</span></span> <span data-ttu-id="3390e-135">但是, 语音路由测试可能失败。)当测试语音路线时, 请注意这一点。</span><span class="sxs-lookup"><span data-stu-id="3390e-135">However, the voice routing test might fail.) This is something to keep in mind when testing voice routes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3390e-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3390e-136">See Also</span></span>


[<span data-ttu-id="3390e-137">在 Lync Server 2013 中导出语音路由测试用例</span><span class="sxs-lookup"><span data-stu-id="3390e-137">Export voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-export-voice-routing-test-cases.md)  
[<span data-ttu-id="3390e-138">在 Lync Server 2013 中导入语音路由测试用例</span><span class="sxs-lookup"><span data-stu-id="3390e-138">Import voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-import-voice-routing-test-cases.md)  


[<span data-ttu-id="3390e-139">在 Lync Server 2013 中配置拨号计划</span><span class="sxs-lookup"><span data-stu-id="3390e-139">Configuring dial plans in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-plans.md)  
[<span data-ttu-id="3390e-140">在 Lync Server 2013 中配置语音策略、PSTN 使用记录和语音路由</span><span class="sxs-lookup"><span data-stu-id="3390e-140">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

