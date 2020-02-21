---
title: Lync Server 2013：创建语音路由测试用例
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a voice routing test case
ms:assetid: 43a07a5b-2f20-462a-81e5-d628c18391e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425935(v=OCS.15)
ms:contentKeyID: 48183979
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9fac6f65d1bb1c04b8d8597454df775f8545d2a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205748"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-voice-routing-test-case-in-lync-server-2013"></a><span data-ttu-id="4b48d-102">在 Lync Server 2013 中创建语音路由测试用例</span><span class="sxs-lookup"><span data-stu-id="4b48d-102">Create a voice routing test case in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4b48d-103">_**上次修改的主题：** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="4b48d-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<div>

## <a name="to-create-a-test-case"></a><span data-ttu-id="4b48d-104">创建测试用例</span><span class="sxs-lookup"><span data-stu-id="4b48d-104">To create a test case</span></span>

1.  <span data-ttu-id="4b48d-105">以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="4b48d-105">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="4b48d-106">有关详细信息，请参阅[Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="4b48d-106">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="4b48d-107">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="4b48d-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4b48d-108">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="4b48d-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4b48d-109">在左侧导航栏中，单击“语音路由”\*\*\*\*，然后单击“测试语音路由”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4b48d-109">In the left navigation bar, click **Voice Routing** and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="4b48d-110">在“测试语音路由”\*\*\*\* 页上，单击“新建”\*\*\*\* 创建新的测试用例。</span><span class="sxs-lookup"><span data-stu-id="4b48d-110">On the **Test Voice Routing** page, click **New** to create a new test case.</span></span>

5.  <span data-ttu-id="4b48d-111">在“名称”\*\*\*\* 字段中，键入测试用例的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="4b48d-111">In **Name**, type in a unique name for the test case.</span></span>
    
    <span data-ttu-id="4b48d-112">此名称在企业语音部署中的所有语音路由测试用例中必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="4b48d-112">The name must be unique among all voice routing test cases in your Enterprise Voice deployment.</span></span> <span data-ttu-id="4b48d-113">它的长度最高为32个字符，并且可以包含任何字母数字字符，除了反斜杠（\\）、句点（.）或下划线（\_）。</span><span class="sxs-lookup"><span data-stu-id="4b48d-113">It can be up to 32 characters in length and may contain any alphanumeric characters, in addition to the backslash (\\), period (.), or underscore (\_).</span></span>

6.  <span data-ttu-id="4b48d-p104">在“要测试的拨打号码”\*\*\*\* 中，键入要用于测试为此测试用例指定的路由配置的拨打号码。基于拨号计划、路由和语音策略，将对此号码进行规范化，并作为输出内容予以显示。</span><span class="sxs-lookup"><span data-stu-id="4b48d-p104">In **Dialed number to test**, type in the dialed number that you want to use to test the routing configuration that you specify for this test case. Based on the dial plan, route, and voice policy, this number will be normalized and displayed as output.</span></span>

7.  <span data-ttu-id="4b48d-p105">在“拨号计划”\*\*\*\* 列表中，选择在运行测试时要使用的拨号计划。默认为全局拨号计划。</span><span class="sxs-lookup"><span data-stu-id="4b48d-p105">In the **Dial Plan** list, select the dial plan to use when running the test. Default is the Global dial plan.</span></span>

8.  <span data-ttu-id="4b48d-p106">在“语音策略”\*\*\*\* 列表中，选择在运行测试时要使用的语音策略。默认为全局语音策略。</span><span class="sxs-lookup"><span data-stu-id="4b48d-p106">In the **Voice Policy** list, select the voice policy to use when running the test. Default is the Global voice policy.</span></span>

9.  <span data-ttu-id="4b48d-p107">在“预期转换”\*\*\*\* 中，按照预期的转换后的格式键入电话号码。这是要测试的电话号码在按照选定拨号计划中匹配的第一个规范化规则进行转换后的值。在运行测试用例时，如果要测试的号码没有生成“预期转换”\*\*\*\* 中的值，则测试失败。</span><span class="sxs-lookup"><span data-stu-id="4b48d-p107">In **Expected translation**, type in the phone number in the format you expect to see it after translation. This is the value of the phone number that you are testing after it has been translated by the first normalization rule that matches in the selected dial plan. When you run the test case, if the number you are testing does not result in the value in **Expected translation**, the test fails.</span></span>

10. <span data-ttu-id="4b48d-p108">（可选）在“预期 PSTN 用法”\*\*\*\* 列表中，可以根据指定的拨号计划和语音策略选择在运行测试用例时预期使用的公用电话交换网 (PSTN) 用法记录。如果使用不同的 PSTN 用法记录，则测试失败。</span><span class="sxs-lookup"><span data-stu-id="4b48d-p108">(Optional) In the **Expected PSTN usage** list, you can select the public switched telephone network (PSTN) usage record that you expect to be used when you run the test case, based on the specified dial plan and voice policy. If a different PSTN usage record is used, the test fails.</span></span>

11. <span data-ttu-id="4b48d-p109">（可选）在“预期路由”\*\*\*\* 列表中，可以根据指定的拨号计划和语音策略选择在运行测试用例时预期使用的语音路由。如果使用不同的语音路由，则测试失败。</span><span class="sxs-lookup"><span data-stu-id="4b48d-p109">(Optional) In the **Expected route** list, you can select the voice route that you expect to be used when you run the test case, based on the specified dial plan and voice policy. If a different voice route is used, the test fails.</span></span>

12. <span data-ttu-id="4b48d-p110">（可选）单击“运行”\*\*\*\* 以运行测试用例。结果将显示在页面的右侧面板中。</span><span class="sxs-lookup"><span data-stu-id="4b48d-p110">(Optional) Click **Run** to run the test case. The results are shown in the right panel of the page.</span></span>

13. <span data-ttu-id="4b48d-129">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4b48d-129">Click **OK**.</span></span>

14. <span data-ttu-id="4b48d-130">单击“提交”\*\*\*\*，然后单击“全部提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4b48d-130">Click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4b48d-131">只要您创建语音路由测试用例，就必须运行“全部提交”<STRONG></STRONG>命令以发布配置更改。</span><span class="sxs-lookup"><span data-stu-id="4b48d-131">Whenever you create a voice routing test case, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="4b48d-132">有关详细信息，请参阅操作文档中的在<A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 中发布待处理的语音路由配置的更改</A>。</span><span class="sxs-lookup"><span data-stu-id="4b48d-132">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>
    
    <span data-ttu-id="4b48d-133">如果在测试中使用的拨号计划规范化以加号（例如，+ 12065551219）开头的电话号码，则该计划可能会导致语音路由测试失败。</span><span class="sxs-lookup"><span data-stu-id="4b48d-133">If the dial plan being employed in the test normalizes phone numbers that begin with a plus sign (for example, +12065551219), that plan might cause the voice routing test to fail.</span></span> <span data-ttu-id="4b48d-134">（拨号计划和语音路由将正常运行，实际上，Grant-csdialplan 将会成功。</span><span class="sxs-lookup"><span data-stu-id="4b48d-134">(The dial plan and the voice route will work; in fact, Test-CsDialPlan will succeed.</span></span> <span data-ttu-id="4b48d-135">但是，语音路由测试可能会失败。在测试语音路由时，需要记住这一点。</span><span class="sxs-lookup"><span data-stu-id="4b48d-135">However, the voice routing test might fail.) This is something to keep in mind when testing voice routes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4b48d-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4b48d-136">See Also</span></span>


[<span data-ttu-id="4b48d-137">在 Lync Server 2013 中导出语音路由测试用例</span><span class="sxs-lookup"><span data-stu-id="4b48d-137">Export voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-export-voice-routing-test-cases.md)  
[<span data-ttu-id="4b48d-138">在 Lync Server 2013 中导入语音路由测试用例</span><span class="sxs-lookup"><span data-stu-id="4b48d-138">Import voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-import-voice-routing-test-cases.md)  


[<span data-ttu-id="4b48d-139">在 Lync Server 2013 中配置拨号计划</span><span class="sxs-lookup"><span data-stu-id="4b48d-139">Configuring dial plans in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-plans.md)  
[<span data-ttu-id="4b48d-140">在 Lync Server 2013 中配置语音策略、PSTN 用法记录和语音路由</span><span class="sxs-lookup"><span data-stu-id="4b48d-140">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

