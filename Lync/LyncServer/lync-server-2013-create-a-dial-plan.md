---
title: 'Lync Server 2013: 创建拨号计划'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a dial plan
ms:assetid: d2fef3d0-7e78-4591-b712-d62ac71d71a5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398909(v=OCS.15)
ms:contentKeyID: 48185424
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8734ce4503ef62eb0fc04aab376f2819d1fc8fea
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837144"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-dial-plan-in-lync-server-2013"></a><span data-ttu-id="74906-102">在 Lync Server 2013 中创建拨号计划</span><span class="sxs-lookup"><span data-stu-id="74906-102">Create a dial plan in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74906-103">_**主题上次修改时间:** 2013-10-24_</span><span class="sxs-lookup"><span data-stu-id="74906-103">_**Topic Last Modified:** 2013-10-24_</span></span>

<span data-ttu-id="74906-104">若要创建新的拨号计划, 请执行以下过程中的步骤。</span><span class="sxs-lookup"><span data-stu-id="74906-104">To create a new dial plan, perform the steps in the following procedure.</span></span> <span data-ttu-id="74906-105">如果要编辑拨号计划, 请参阅[在 Lync Server 2013 中修改拨号计划](lync-server-2013-modify-a-dial-plan.md)。</span><span class="sxs-lookup"><span data-stu-id="74906-105">If you want to edit a dial plan, see [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span>

<div>

## <a name="to-create-a-dial-plan"></a><span data-ttu-id="74906-106">创建拨号计划</span><span class="sxs-lookup"><span data-stu-id="74906-106">To create a dial plan</span></span>

1.  <span data-ttu-id="74906-107">以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="74906-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="74906-108">有关详细信息, 请参阅[在 Lync Server 2013 中委派设置权限](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="74906-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="74906-109">打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="74906-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="74906-110">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="74906-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="74906-111">在左侧导航栏中，单击“语音路由”\*\*\*\*，然后单击“拨号计划”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="74906-111">In the left navigation bar, click **Voice Routing** and then click **Dial Plan**.</span></span>

4.  <span data-ttu-id="74906-112">在“拨号计划”\*\*\*\* 页上，单击“新建”\*\*\*\*，然后为拨号计划选择作用域：</span><span class="sxs-lookup"><span data-stu-id="74906-112">On the **Dial Plan** page, click **New** and select a scope for the dial plan:</span></span>
    
      - <span data-ttu-id="74906-p104">“站点拨号计划”\*\*\*\* 将应用于整个站点，分配给用户拨号计划的用户或组除外。如果选择“站点”\*\*\*\* 作为拨号计划的作用域，则必须从“选择站点”\*\*\*\* 对话框中选择站点。如果已经为站点创建了拨号计划，则该站点不会显示在“选择站点”\*\*\*\* 对话框中。</span><span class="sxs-lookup"><span data-stu-id="74906-p104">**Site dial plan** applies to an entire site, except any users or groups that are assigned to a user dial plan. If you select **Site** for a dial plan’s scope, you must choose the site from the **Select a Site** dialog box. If a dial plan has already been created for a site, the site does not appear in the **Select a Site** dialog box.</span></span>
    
      - <span data-ttu-id="74906-p105">“池拨号计划”\*\*\*\* 可以应用于公用电话交换网 (PSTN) 网关或注册器。如果选择“池”\*\*\*\* 作为拨号计划的作用域，则从“选择服务”\*\*\*\* 对话框中选择 PSTN 网关或注册器。如果已经为服务（PSTN 网关或注册器）创建了拨号计划，则该服务不会显示在列表中。</span><span class="sxs-lookup"><span data-stu-id="74906-p105">**Pool dial plan** can apply to a public switched telephone network (PSTN) gateway or a Registrar. If you select **Pool** for a dial plan’s scope, choose the PSTN gateway or Registrar from the **Select a Service** dialog box. If a dial plan has already been created for a service (PSTN gateway or Registrar), the service does not appear in the list.</span></span>
    
      - <span data-ttu-id="74906-119">“用户拨号计划”\*\*\*\* 可以应用于指定的用户或组。</span><span class="sxs-lookup"><span data-stu-id="74906-119">**User dial plan** can be applied to specified users or groups.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="74906-120">选择拨号计划作用域后，就无法更改。</span><span class="sxs-lookup"><span data-stu-id="74906-120">After you select the dial plan scope, it cannot be changed.</span></span>

    
    </div>

5.  <span data-ttu-id="74906-p106">如果要创建用户拨号计划，请在“新建拨号计划”\*\*\*\* 对话框的“名称”\*\*\*\* 字段中输入描述性名称。保存此名称后，就无法更改。</span><span class="sxs-lookup"><span data-stu-id="74906-p106">If you are creating a user dial plan, enter a descriptive name in the **Name** field on the **New Dial Plan** dialog box. After this name is saved, it cannot be changed.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="74906-123">对于站点拨号计划，“名称”<STRONG></STRONG>字段会使用站点名称预先填充，且不能更改。</span><span class="sxs-lookup"><span data-stu-id="74906-123">For site dial plans, the <STRONG>Name</STRONG> field is prepopulated with the site name and cannot be changed.</span></span><BR><span data-ttu-id="74906-124">对于池拨号计划，“名称”<STRONG></STRONG>字段会使用 PSTN 网关或注册器名称预先填充，且不能更改。</span><span class="sxs-lookup"><span data-stu-id="74906-124">For pool dial plans, the <STRONG>Name</STRONG> field is prepopulated with the PSTN gateway or Registrar name and cannot be changed.</span></span>

    
    </div>

6.  <span data-ttu-id="74906-p107">“简单名称”\*\*\*\* 字段会使用与“名称”\*\*\*\* 字段中显示的相同名称预先填充。您可以选择编辑该字段来指定描述性更强的名称，以反映应用该拨号计划的站点、服务或用户。</span><span class="sxs-lookup"><span data-stu-id="74906-p107">The **Simple name** field is prepopulated with the same name that appears in the **Name** field. You can optionally edit this field to specify a more descriptive name that reflects the site, service, or user to which the dial plan applies.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="74906-127"><STRONG>简单名称</STRONG>必须在 Lync Server 部署中的所有拨号计划中是唯一的。</span><span class="sxs-lookup"><span data-stu-id="74906-127">The <STRONG>Simple name</STRONG> must be unique among all dial plans within the Lync Server deployment.</span></span> <span data-ttu-id="74906-128">该名称不能超过 256 个 Unicode 字符，每个 Unicode 字符可以是字母或数字字符、连字符 (-)、句点 (.) 或下划线 (_)。</span><span class="sxs-lookup"><span data-stu-id="74906-128">It cannot exceed 256 Unicode characters, each of which can be an alphabetic or numeric character, a hyphen (-), a period (.), or an underscore (_).</span></span><BR><span data-ttu-id="74906-129"><STRONG>不支持</STRONG>的字符包括 RFC 3966 (http://www.ietf.org/rfc/rfc3966.txt).) 中定义的空格和保留字符。</span><span class="sxs-lookup"><span data-stu-id="74906-129">Characters <STRONG>not supported</STRONG> include spaces and Reserved characters as defined in RFC 3966 (http://www.ietf.org/rfc/rfc3966.txt).</span></span> <span data-ttu-id="74906-130">“简单名称”<STRONG></STRONG>中<STRONG>不支持的</STRONG>保留字符包括：</span><span class="sxs-lookup"><span data-stu-id="74906-130">Reserved characters that are <STRONG>not supported</STRONG> in the <STRONG>Simple Name</STRONG> include the following:</span></span><BR><span data-ttu-id="74906-131">";""/" "?"":" "@" "&amp;" "=" "+" "$" ","</span><span class="sxs-lookup"><span data-stu-id="74906-131">";" "/" "?" ":" "@" "&amp;" "=" "+" "$" ","</span></span>

    
    </div>

7.  <span data-ttu-id="74906-132">（可选）在“说明”\*\*\*\* 字段中，您可以键入有关拨号计划的其他描述性信息。</span><span class="sxs-lookup"><span data-stu-id="74906-132">(Optional) In the **Description** field, you can type additional descriptive information about the dial plan.</span></span>

8.  <span data-ttu-id="74906-p110">（可选）如果要将此拨号计划用作电话拨入式访问号码的区域，请指定“电话拨入式会议区域”\*\*\*\*。如果不希望将此拨号计划用于电话拨入式访问号码，请将此字段留空。</span><span class="sxs-lookup"><span data-stu-id="74906-p110">(Optional) If you want to use this dial plan as a region for dial-in access numbers, specify a **Dial-in conferencing region**. If you do not want to use this dial plan for dial-in access numbers, leave this field empty.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="74906-135">电话拨入式会议区域需要将电话拨入式会议访问号码与一个或多个拨号计划相关联。</span><span class="sxs-lookup"><span data-stu-id="74906-135">Dial-in conferencing regions are required to associate dial-in conferencing access numbers with one or more dial plans.</span></span>

    
    </div>

9.  <span data-ttu-id="74906-136">（可选）在“外部访问前缀”\*\*\*\* 字段中，指定一个值，该值仅在用户需要拨打一个或多个附加的前导数字（例如 9）以拨通外线时使用。</span><span class="sxs-lookup"><span data-stu-id="74906-136">(Optional) In the **External access prefix** field, specify a value only if users need to dial one or more additional leading digits (for example, 9) to get an external line.</span></span> <span data-ttu-id="74906-137">你可以键入最多四个字符 (\#、 \*和 0-9) 的前缀值。</span><span class="sxs-lookup"><span data-stu-id="74906-137">You can type in a prefix value of up to four characters (\#, \*, and 0-9).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="74906-138">如果指定了外部访问前缀，则不需要创建新的规范化规则来满足前缀。</span><span class="sxs-lookup"><span data-stu-id="74906-138">If you specify an external access prefix, you do not need to create a new normalization rule to accommodate the prefix.</span></span>

    
    </div>

10. <span data-ttu-id="74906-139">按如下所示为拨号计划关联并配置规范化规则：</span><span class="sxs-lookup"><span data-stu-id="74906-139">Associate and configure normalization rules for the dial plan as follows:</span></span>
    
      - <span data-ttu-id="74906-140">若要从您的企业语音部署中可用的所有规范化规则列表中选择一个或多个规则, 请单击 "**选择**"。</span><span class="sxs-lookup"><span data-stu-id="74906-140">To choose one or more rules from a list of all normalization rules available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="74906-141">在“选择规范化规则”\*\*\*\* 中，突出显示要与拨号计划关联的规则，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="74906-141">In **Select Normalization Rules**, highlight the rules you want to associate with the dial plan and then click **OK**.</span></span>
    
      - <span data-ttu-id="74906-142">要定义新的规范化规则并将其与拨号计划相关联，请单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="74906-142">To define a new normalization rule and associate it with the dial plan, click **New**.</span></span> <span data-ttu-id="74906-143">有关定义新规则的详细信息, 请参阅[在 Lync Server 2013 中定义规范化规则](lync-server-2013-defining-normalization-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="74906-143">For details about defining a new rule, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="74906-144">要编辑已经与拨号计划关联的规范化规则，请突出显示相应的规则名称，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="74906-144">To edit a normalization rule that is already associated with the dial plan, highlight the rule name and click **Show details**.</span></span> <span data-ttu-id="74906-145">有关编辑规则的详细信息, 请参阅[在 Lync Server 2013 中定义规范化规则](lync-server-2013-defining-normalization-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="74906-145">For details about editing the rule, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="74906-146">要复制现有规范化规则以作为定义新规则的起点，请突出显示相应的规则名称，单击“复制”\*\*\*\*，然后单击“粘贴”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="74906-146">To copy an existing normalization rule to use as a starting point for defining a new rule, highlight the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="74906-147">有关编辑副本的详细信息, 请参阅[在 Lync Server 2013 中定义规范化规则](lync-server-2013-defining-normalization-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="74906-147">For details about editing the copy, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="74906-148">要从拨号计划中删除某个规范化规则，请突出显示相应的规则名称，然后单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="74906-148">To remove a normalization rule from the dial plan, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="74906-149">每个拨号计划都必须至少有一个关联的规范化规则。</span><span class="sxs-lookup"><span data-stu-id="74906-149">Each dial plan must have at least one associated normalization rule.</span></span> <span data-ttu-id="74906-150">有关如何确定拨号计划所需的所有规范化规则的信息, 请参阅规划文档中的<A href="lync-server-2013-dial-plans-and-normalization-rules.md">Lync Server 2013 中的 "拨号计划和规范规则</A>"。</span><span class="sxs-lookup"><span data-stu-id="74906-150">For information about how to determine all of the normalization rules a dial plan requires, see <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Dial plans and normalization rules in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

11. <span data-ttu-id="74906-p117">验证拨号计划的规范化规则是否已按正确顺序排列。要更改规则在列表中的位置，请突出显示相应的规则名称，然后单击向上箭头或向下箭头。</span><span class="sxs-lookup"><span data-stu-id="74906-p117">Verify that the dial plan’s normalization rules are arranged in the correct order. To change a rule’s position in the list, highlight the rule name and then click the up or down arrow.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="74906-153">Lync 服务器从上到下遍历规范化规则列表, 并使用与所拨号码匹配的第一个规则。</span><span class="sxs-lookup"><span data-stu-id="74906-153">Lync Server traverses the normalization rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="74906-154">如果要配置拨号计划以使拨打号码可以匹配多个规范化规则，请确保限制较严格的规则排在限制较宽松的规则上方。</span><span class="sxs-lookup"><span data-stu-id="74906-154">If you configure a dial plan so that a dialed number can match more than one normalization rule, make sure the more restrictive rules are sorted above the less restrictive ones.</span></span><BR><span data-ttu-id="74906-155">默认情况下, "所有规范化规则<STRONG>^{11}(\d) $</STRONG> "<STRONG>将</STRONG>与任何11位数字匹配。</span><span class="sxs-lookup"><span data-stu-id="74906-155">The default <STRONG>Keep All</STRONG> normalization rule <STRONG>^(\d{11})$</STRONG> matches any 11-digit number.</span></span> <span data-ttu-id="74906-156">例如, 如果你添加的规范化规则与以1425开头的11位数字相匹配, 请确保 "<STRONG>全部保留</STRONG>" 按限制性<STRONG>^ (1425 d{7}) $</STRONG>规则为准则排序。</span><span class="sxs-lookup"><span data-stu-id="74906-156">For example, if you add a normalization rule that matches 11-digit numbers that start with 1425, make sure that <STRONG>Keep All</STRONG> is sorted below the more restrictive <STRONG>^(1425\d{7})$</STRONG> rule.</span></span>

    
    </div>

12. <span data-ttu-id="74906-p120">（可选）输入一个号码来测试拨号计划，然后单击“执行”\*\*\*\*。测试结果会显示在“输入要测试的号码”\*\*\*\* 下。</span><span class="sxs-lookup"><span data-stu-id="74906-p120">(Optional) Enter a number to test the dial plan and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="74906-159">您可以保存尚未通过测试的拨号计划，并在稍后对其进行重新配置。</span><span class="sxs-lookup"><span data-stu-id="74906-159">You can save a dial plan that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="74906-160">有关详细信息, 请参阅<A href="lync-server-2013-test-voice-routing.md">在 Lync Server 2013 中测试语音路由</A>。</span><span class="sxs-lookup"><span data-stu-id="74906-160">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

13. <span data-ttu-id="74906-161">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="74906-161">Click **OK**.</span></span>

14. <span data-ttu-id="74906-162">在“拨号计划”\*\*\*\* 页上，单击“提交”\*\*\*\*，然后单击“全部提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="74906-162">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="74906-163">任何时候创建拨号计划，都必须运行“全部提交”<STRONG></STRONG>命令以发布配置更改。</span><span class="sxs-lookup"><span data-stu-id="74906-163">Any time you create a dial plan, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="74906-164">有关详细信息, 请参阅操作文档中的<A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 中的 "发布待处理的语音路由配置更改"</A> 。</span><span class="sxs-lookup"><span data-stu-id="74906-164">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="74906-165">另请参阅</span><span class="sxs-lookup"><span data-stu-id="74906-165">See Also</span></span>


[<span data-ttu-id="74906-166">在 Lync Server 2013 中修改拨号计划</span><span class="sxs-lookup"><span data-stu-id="74906-166">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)  
[<span data-ttu-id="74906-167">将挂起的更改发布到 Lync Server 2013 中的语音路由配置</span><span class="sxs-lookup"><span data-stu-id="74906-167">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="74906-168">在 Lync Server 2013 中定义规范化规则</span><span class="sxs-lookup"><span data-stu-id="74906-168">Defining normalization rules in Lync Server 2013</span></span>](lync-server-2013-defining-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

