---
title: Lync Server 2013：运行非正式语音路由测试
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Run informal voice routing tests
ms:assetid: ea0e6059-bf04-4b03-b6d3-8f5534b731e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399049(v=OCS.15)
ms:contentKeyID: 48185904
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d8edac9a9bd955165a2e20197fd340ea80c2e27a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007751"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="run-informal-voice-routing-tests-in-lync-server-2013"></a><span data-ttu-id="a138a-102">在 Lync Server 2013 中运行非正式语音路由测试</span><span class="sxs-lookup"><span data-stu-id="a138a-102">Run informal voice routing tests in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a138a-103">_**上次修改的主题：** 2012-08-07_</span><span class="sxs-lookup"><span data-stu-id="a138a-103">_**Topic Last Modified:** 2012-08-07_</span></span>

<span data-ttu-id="a138a-p101">在创建实际测试用例之前，可以使用“创建语音路由测试用例信息”\*\*\*\* 对话框运行非正式的测试。对测试结果感到满意后，可以通过相应的选项将其保存为正式测试用例。</span><span class="sxs-lookup"><span data-stu-id="a138a-p101">You can use the **Create voice routing test case information** dialog box to run informal tests before creating an actual test case. When you are satisfied with the outcome of a test, you have the option of saving it as a formal test case.</span></span>

<div>

## <a name="to-run-an-informal-voice-routing-test"></a><span data-ttu-id="a138a-106">运行非正式语音路由测试</span><span class="sxs-lookup"><span data-stu-id="a138a-106">To run an informal voice routing test</span></span>

1.  <span data-ttu-id="a138a-107">以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="a138a-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="a138a-108">有关详细信息，请参阅[Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="a138a-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="a138a-109">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="a138a-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a138a-110">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="a138a-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a138a-111">在左侧导航栏中，单击“语音路由”\*\*\*\*，然后单击“测试语音路由”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a138a-111">In the left navigation bar, click **Voice Routing**, and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="a138a-112">在“测试语音路由”\*\*\*\* 页上，单击“创建语音路由测试用例信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a138a-112">On the **Test Voice Routing** page, click **Create voice routing test case information**.</span></span>

5.  <span data-ttu-id="a138a-p104">在“拨打的号码”\*\*\*\* 字段中，键入要用于此测试的电话号码。将对该号码进行规范化处理，并显示在“结果”\*\*\*\* 窗格的“规范化号码”\*\*\*\* 字段中。</span><span class="sxs-lookup"><span data-stu-id="a138a-p104">In the **Dialed number** field, type in the phone number you want to use for this test. This number will be normalized and displayed in the **Normalized number** field of the **Results** pane.</span></span>

6.  <span data-ttu-id="a138a-p105">在“拨号计划”\*\*\*\* 列表中，选择要用于测试已拨号码的拨号计划。默认为全局拨号计划。</span><span class="sxs-lookup"><span data-stu-id="a138a-p105">In the **Dial plan** list, select the dial plan to use for testing the dialed number. Default is the Global dial plan.</span></span>
    
    <span data-ttu-id="a138a-117">运行测试时，该拨号计划中第一个匹配已拨号码的规范化规则将显示在“结果”\*\*\*\* 窗格的“规范化规则”\*\*\*\* 字段中。</span><span class="sxs-lookup"><span data-stu-id="a138a-117">When you run the test, the first normalization rule in this dial plan that matches the dialed number will be displayed in the **Normalization rule** field of the **Results** pane.</span></span>

7.  <span data-ttu-id="a138a-p106">在“语音策略”\*\*\*\* 列表中，选择要用于测试已拨号码的语音策略。默认为全局语音策略。</span><span class="sxs-lookup"><span data-stu-id="a138a-p106">In the **Voice Policy** list, select the voice policy to use for testing the dialed number. Default is the Global voice policy.</span></span>
    
    <span data-ttu-id="a138a-p107">运行测试时，该语音策略中第一条匹配的 PSTN 用法记录将显示在“结果”\*\*\*\* 窗格的“第一个 PSTN 用法”\*\*\*\* 字段中。另外，与此 PSTN 用法记录关联的第一个匹配的语音路由将显示在“第一个路由”\*\*\*\* 字段中。</span><span class="sxs-lookup"><span data-stu-id="a138a-p107">When you run the test, the first matching PSTN usage record in this voice policy will be displayed in the **First PSTN usage** field of the **Results** pane. Also, the first matching voice route that is associated with this PSTN usage record will be displayed in the **First route** field.</span></span>

8.  <span data-ttu-id="a138a-122">（可选）如果要根据分配给特定用户的语音策略测试已拨号码，请选中“从用户填充”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="a138a-122">(Optional) Select the **Populate from user** check box if you want to test the dialed number against the voice policy assigned to a particular user.</span></span>
    
    1.  <span data-ttu-id="a138a-123">单击“浏览”\*\*\*\* 以显示“选择企业语音用户”\*\*\*\* 对话框。</span><span class="sxs-lookup"><span data-stu-id="a138a-123">Click **Browse** to display the **Select Enterprise Voice Users** dialog box.</span></span>
    
    2.  <span data-ttu-id="a138a-124">单击“查找”\*\*\*\* 以显示已启用企业语音的用户列表。</span><span class="sxs-lookup"><span data-stu-id="a138a-124">Click **Find** to display the list of users who are enabled for Enterprise Voice.</span></span>
    
    3.  <span data-ttu-id="a138a-p108">双击要将为其分配的语音策略用于该测试的用户名。现在“策略”\*\*\*\* 字段中填充了分配给所选用户的语音策略。</span><span class="sxs-lookup"><span data-stu-id="a138a-p108">Double-click the user name whose assigned voice policy you want to use for this test. The **Policy** field is now populated with the voice policy assigned to the selected user.</span></span>
    
    <span data-ttu-id="a138a-p109">运行测试时，该语音策略中第一条匹配的公用电话交换网 (PSTN) 用法记录将显示在“结果”\*\*\*\* 窗格的“第一个 PSTN 用法”\*\*\*\* 字段中。另外，与此 PSTN 用法记录关联的第一个匹配的语音路由将显示在“第一个路由”\*\*\*\* 字段中。</span><span class="sxs-lookup"><span data-stu-id="a138a-p109">When you run the test, the first matching public switched telephone network (PSTN) usage record in this voice policy will be displayed in the **First PSTN usage** field of the **Results** pane. Also, the first matching voice route that is associated with this PSTN usage record will be displayed in the **First route** field.</span></span>

9.  <span data-ttu-id="a138a-p110">单击“运行”\*\*\*\* 以运行测试用例。结果显示在对话框的右侧面板中。</span><span class="sxs-lookup"><span data-stu-id="a138a-p110">Click **Run** to run the test case. The results are shown in the right panel of the dialog box.</span></span>

10. <span data-ttu-id="a138a-131">（可选）如果要将该测试配置保存为正式测试用例，单击“另存为”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a138a-131">(Optional) Click **Save as** if you want to save this test configuration as a formal test case.</span></span>
    
    1.  <span data-ttu-id="a138a-132">在“保存语音路由测试用例信息”\*\*\*\* 对话框的“名称”\*\*\*\* 字段中，为测试用例键入唯一的名称。</span><span class="sxs-lookup"><span data-stu-id="a138a-132">In the **Name** field of the **Save Voice Routing Test Case Information** dialog box, type a unique name for the test case.</span></span>
        
        <span data-ttu-id="a138a-133">此名称在企业语音部署中的所有语音路由测试用例中必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="a138a-133">The name must be unique among all voice routing test cases in your Enterprise Voice deployment.</span></span> <span data-ttu-id="a138a-134">它的长度最高为32个字符，并且可以包含任何字母数字字符，除了反斜杠（\\）、句点（.）或下划线（\_）。</span><span class="sxs-lookup"><span data-stu-id="a138a-134">It can be up to 32 characters in length and may contain any alphanumeric characters, in addition to the backslash (\\), period (.), or underscore (\_).</span></span>
    
    2.  <span data-ttu-id="a138a-p112">请注意，“保存语音路由测试用例信息”\*\*\*\* 对话框中的其余字段都是只读字段，并且预填充非正式测试配置\*\* 和结果。确认这是要为测试用例保存的配置。</span><span class="sxs-lookup"><span data-stu-id="a138a-p112">Note that the remaining fields on the **Save Voice Routing Test Case Information** dialog box are read-only, and are prepopulated from the informal test configuration *and* results. Verify that this is the configuration that you want to save for the test case.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a138a-137">测试结果中的值用于预填充“保存语音路由测试用例信息”<STRONG></STRONG>对话框中的字段，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a138a-137">Values from the test results are used to prepopulate fields on the <STRONG>Save Voice Routing Test Case Information</STRONG> dialog box as follows:</span></span> 
        > <UL>
        > <LI>
        > <P><span data-ttu-id="a138a-138">“预期转换”<STRONG></STRONG>使用“规范化号码”<STRONG></STRONG>字段中的值进行预填充。</span><span class="sxs-lookup"><span data-stu-id="a138a-138"><STRONG>Expected translation</STRONG> is prepopulated with the value in the <STRONG>Normalized number</STRONG> field.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="a138a-139">“预期路由”<STRONG></STRONG>使用“第一个路由”<STRONG></STRONG>字段中的值进行预填充。</span><span class="sxs-lookup"><span data-stu-id="a138a-139"><STRONG>Expected route</STRONG> is prepopulated with the value in the <STRONG>First route</STRONG> field.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="a138a-140">“预期 PSTN 用法记录”<STRONG></STRONG>使用“第一个 PSTN 用法”<STRONG></STRONG>字段中的值进行预填充。</span><span class="sxs-lookup"><span data-stu-id="a138a-140"><STRONG>Expected PSTN usage record</STRONG> is prepopulated with the value in the <STRONG>First PSTN usage</STRONG> field.</span></span></P></LI></UL><span data-ttu-id="a138a-p113">如果在测试运行期间未找到上述任何值的匹配内容，“保存语音路由测试用例信息”<STRONG></STRONG>对话框中的对应字段将为空。</span><span class="sxs-lookup"><span data-stu-id="a138a-p113">If matches for any of these values were not found during the test run, the corresponding field is empty on the <STRONG>Save Voice Routing Test Case Information</STRONG> dialog box.   </span></span></div>
    
    3.  <span data-ttu-id="a138a-142">单击“确定”\*\*\*\* 保存测试用例，或单击“取消”\*\*\*\* 返回“查看语音路由测试用例信息”\*\*\*\* 对话框以在保存前进一步完善测试。</span><span class="sxs-lookup"><span data-stu-id="a138a-142">Click **Ok** to save the test case, or click **Cancel** to return to return to the **View voice routing test case information** dialog box to further develop the test before saving it.</span></span>

11. <span data-ttu-id="a138a-143">单击“提交”\*\*\*\*，然后单击“全部提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a138a-143">Click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a138a-144">任何时候创建语音路由测试用例，都必须运行“全部提交”<STRONG></STRONG>命令以发布测试用例。</span><span class="sxs-lookup"><span data-stu-id="a138a-144">Whenever you create a voice routing test case, you must run the <STRONG>Commit all</STRONG> command to publish the test case.</span></span> <span data-ttu-id="a138a-145">有关详细信息，请参阅操作文档中的在<A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 中发布待处理的语音路由配置的更改</A>。</span><span class="sxs-lookup"><span data-stu-id="a138a-145">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a138a-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a138a-146">See Also</span></span>


[<span data-ttu-id="a138a-147">在 Lync Server 2013 中创建语音路由测试用例</span><span class="sxs-lookup"><span data-stu-id="a138a-147">Create a voice routing test case in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-routing-test-case.md)  
[<span data-ttu-id="a138a-148">在 Lync Server 2013 中运行语音路由测试用例</span><span class="sxs-lookup"><span data-stu-id="a138a-148">Run voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-run-voice-routing-test-cases.md)  
[<span data-ttu-id="a138a-149">在 Lync Server 2013 中导出语音路由测试用例</span><span class="sxs-lookup"><span data-stu-id="a138a-149">Export voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-export-voice-routing-test-cases.md)  
[<span data-ttu-id="a138a-150">在 Lync Server 2013 中导入语音路由测试用例</span><span class="sxs-lookup"><span data-stu-id="a138a-150">Import voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-import-voice-routing-test-cases.md)  


[<span data-ttu-id="a138a-151">在 Lync Server 2013 中配置拨号计划</span><span class="sxs-lookup"><span data-stu-id="a138a-151">Configuring dial plans in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-plans.md)  
[<span data-ttu-id="a138a-152">在 Lync Server 2013 中配置语音策略、PSTN 用法记录和语音路由</span><span class="sxs-lookup"><span data-stu-id="a138a-152">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

