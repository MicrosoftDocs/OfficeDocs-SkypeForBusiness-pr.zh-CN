---
title: Lync Server 2013：修改拨号计划
description: Lync Server 2013：修改拨号计划。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify a dial plan
ms:assetid: a91f02df-cf60-40cf-82fe-e0342c118b91
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412797(v=OCS.15)
ms:contentKeyID: 48185099
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e173552970c6b1799076b3f3b05d59ed6f0719e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550498"
---
# <a name="modify-a-dial-plan-in-lync-server-2013"></a><span data-ttu-id="88581-103">在 Lync Server 2013 中修改拨号计划</span><span class="sxs-lookup"><span data-stu-id="88581-103">Modify a dial plan in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="88581-104">_**上次修改的主题：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="88581-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="88581-105">要修改现有拨号计划，请执行以下过程中的步骤。</span><span class="sxs-lookup"><span data-stu-id="88581-105">To modify an existing dial plan, perform the steps in the following procedure.</span></span> <span data-ttu-id="88581-106">如果要创建新的拨号计划，请参阅 [在 Lync Server 2013 中创建拨号计划](lync-server-2013-create-a-dial-plan.md)。</span><span class="sxs-lookup"><span data-stu-id="88581-106">If you want to create a new dial plan, see [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span></span>

<div>

## <a name="to-modify-a-dial-plan"></a><span data-ttu-id="88581-107">修改拨号计划</span><span class="sxs-lookup"><span data-stu-id="88581-107">To modify a dial plan</span></span>

1.  <span data-ttu-id="88581-108">以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="88581-108">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="88581-109">有关详细信息，请参阅 [Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="88581-109">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="88581-110">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="88581-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="88581-111">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="88581-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="88581-112">在左侧导航栏中，单击“语音路由”\*\*\*\*，然后单击“拨号计划”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="88581-112">In the left navigation bar, click **Voice Routing** and then click **Dial Plan**.</span></span>

4.  <span data-ttu-id="88581-113">在“拨号计划”\*\*\*\* 页上，双击某个拨号计划名称。</span><span class="sxs-lookup"><span data-stu-id="88581-113">On the **Dial Plan** page, double-click a dial plan name.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="88581-p104">拨号计划的作用域和名称是在创建该拨号计划时设置的，且不能更改。</span><span class="sxs-lookup"><span data-stu-id="88581-p104">The dial plan scope and name were set when the dial plan was created. They cannot be changed.</span></span>

    
    </div>

5.  <span data-ttu-id="88581-116">（可选）在“编辑拨号计划”\*\*\*\* 中，编辑“简单名称”\*\*\*\* 字段，该字段会预填充“名称”\*\*\*\* 字段中显示的相同名称，以指定反映应用该拨号计划的站点、服务或用户的更具描述性的名称。</span><span class="sxs-lookup"><span data-stu-id="88581-116">(Optional) In **Edit Dial Plan**, edit the **Simple name** field, which is prepopulated with the same name that appears in the **Name** field to specify a more descriptive name that reflects the site, service, or user to which the dial plan applies.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="88581-117">在 Lync Server 2013 部署中的所有拨号计划中， <STRONG>简单名称</STRONG> 必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="88581-117">The <STRONG>Simple name</STRONG> must be unique among all dial plans within the Lync Server 2013 deployment.</span></span> <span data-ttu-id="88581-118">该名称不能超过 256 个 Unicode 字符，每个 Unicode 字符可以是字母或数字字符、连字符 (-)、句点 (.)、加号 (+) 或下划线 (_)。</span><span class="sxs-lookup"><span data-stu-id="88581-118">It cannot exceed 256 Unicode characters, each of which can be an alphabetic or numeric character, a hyphen (-), a period (.), a plus sign (+), or an underscore (_).</span></span><BR><span data-ttu-id="88581-119">“简单名称”<STRONG></STRONG>字段中不允许使用空格。</span><span class="sxs-lookup"><span data-stu-id="88581-119">Spaces are not allowed in the <STRONG>Simple name</STRONG> field.</span></span>

    
    </div>

6.  <span data-ttu-id="88581-120">（可选）在“说明”\*\*\*\* 字段中，键入有关拨号计划的描述性信息。</span><span class="sxs-lookup"><span data-stu-id="88581-120">(Optional) In the **Description** field, type descriptive information about the dial plan.</span></span>

7.  <span data-ttu-id="88581-p106">（可选）如果要将此拨号计划用作电话拨入式访问号码的区域，请指定“电话拨入式会议区域”\*\*\*\*。如果不希望将此拨号计划用于电话拨入式访问号码，请将此字段留空。</span><span class="sxs-lookup"><span data-stu-id="88581-p106">(Optional) If you want to use this dial plan as a region for dial-in access numbers, specify a **Dial-in conferencing region**. If you do not want to use this dial plan for dial-in access numbers, leave this field empty.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="88581-123">电话拨入式会议区域需要将电话拨入式会议访问号码与一个或多个拨号计划相关联。</span><span class="sxs-lookup"><span data-stu-id="88581-123">Dial-in conferencing regions are required to associate dial-in conferencing access numbers with one or more dial plans.</span></span>

    
    </div>

8.  <span data-ttu-id="88581-124">（可选）在“外部访问前缀”\*\*\*\* 字段中，指定一个值，该值仅在用户需要拨打一个或多个附加的前导数字（例如 9）以拨通外线时使用。</span><span class="sxs-lookup"><span data-stu-id="88581-124">(Optional) In the **External access prefix** field, specify a value only if users need to dial one or more additional leading digits to get an external line (for example, 9).</span></span> <span data-ttu-id="88581-125">可以键入最长为四个字符的前缀值， (为、、 \# \* 、和 0-9) 。</span><span class="sxs-lookup"><span data-stu-id="88581-125">You can type in a prefix value of up to four characters (that is, \#, \*, and 0-9).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="88581-126">如果指定了外部访问前缀，则不需要创建新的规范化规则来满足前缀。</span><span class="sxs-lookup"><span data-stu-id="88581-126">If you specify an external access prefix, you do not need to create a new normalization rule to accommodate the prefix.</span></span>

    
    </div>

9.  <span data-ttu-id="88581-127">为拨号计划关联并配置规范化规则：</span><span class="sxs-lookup"><span data-stu-id="88581-127">Associate and configure normalization rules for the dial plan:</span></span>
    
      - <span data-ttu-id="88581-128">若要从企业语音部署中提供的所有规范化规则列表中选择一个或多个规则，请单击 " **选择**"。</span><span class="sxs-lookup"><span data-stu-id="88581-128">To choose one or more rules from a list of all normalization rules available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="88581-129">在“选择规范化规则”\*\*\*\* 对话框中，突出显示要与拨号计划关联的规则，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="88581-129">In the **Select Normalization Rules** dialog box, highlight the rules that you want to associate with the dial plan and then click **OK**.</span></span>
    
      - <span data-ttu-id="88581-130">要定义新的规范化规则并将其与拨号计划相关联，请单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="88581-130">To define a new normalization rule and associate it with the dial plan, click **New**.</span></span> <span data-ttu-id="88581-131">有关定义新规则的详细信息，请参阅 [在 Lync Server 2013 中定义规范化规则](lync-server-2013-defining-normalization-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="88581-131">For details about defining a new rule, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="88581-132">要编辑已经与拨号计划关联的规范化规则，请突出显示相应的规则名称，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="88581-132">To edit a normalization rule that is already associated with the dial plan, highlight the rule name and click **Show details**.</span></span> <span data-ttu-id="88581-133">有关编辑规则的详细信息，请参阅 [在 Lync Server 2013 中定义规范化规则](lync-server-2013-defining-normalization-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="88581-133">For details about editing the rule, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="88581-134">要复制现有规范化规则以作为定义新规则的起点，请突出显示相应的规则名称，单击“复制”\*\*\*\*，然后单击“粘贴”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="88581-134">To copy an existing normalization rule to use as a starting point for defining a new rule, highlight the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="88581-135">有关编辑副本的详细信息，请参阅 [在 Lync Server 2013 中定义规范化规则](lync-server-2013-defining-normalization-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="88581-135">For details about editing the copy, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="88581-136">要从拨号计划中删除某个规范化规则，请突出显示相应的规则名称，然后单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="88581-136">To remove a normalization rule from the dial plan, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="88581-137">每个拨号计划都必须至少有一个关联的规范化规则。</span><span class="sxs-lookup"><span data-stu-id="88581-137">Each dial plan must have at least one associated normalization rule.</span></span> <span data-ttu-id="88581-138">有关如何确定拨号计划所需的全部规范化规则的详细信息，请参阅规划文档中的 <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Lync Server 2013 中的拨号计划和规范化规则</A> 。</span><span class="sxs-lookup"><span data-stu-id="88581-138">For details about how to determine all of the normalization rules a dial plan requires, see <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Dial plans and normalization rules in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

10. <span data-ttu-id="88581-p113">验证拨号计划的规范化规则是否已按正确顺序排列。要更改规则在列表中的位置，请突出显示相应的规则名称，然后单击向上箭头或向下箭头。</span><span class="sxs-lookup"><span data-stu-id="88581-p113">Verify that the dial plan’s normalization rules are arranged in the correct order. To change a rule’s position in the list, highlight the rule name and then click the up or down arrow.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="88581-141">Lync Server 从上到下遍历规范化规则列表，并使用第一个与拨打的号码相匹配的规则。</span><span class="sxs-lookup"><span data-stu-id="88581-141">Lync Server traverses the normalization rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="88581-142">如果要配置拨号计划以使拨打号码可以匹配多个规范化规则，请确保限制较严格的规则排在限制较宽松的规则上方。</span><span class="sxs-lookup"><span data-stu-id="88581-142">If you configure a dial plan so that a dialed number can match more than one normalization rule, make sure the more restrictive rules are sorted above the less restrictive ones.</span></span><BR><span data-ttu-id="88581-143">默认情况下， <STRONG>将所有</STRONG> 规范化规则 <STRONG>^ ( \d {11}) $</STRONG> 匹配任意11位数字。</span><span class="sxs-lookup"><span data-stu-id="88581-143">The default <STRONG>Keep All</STRONG> normalization rule <STRONG>^(\d{11})$</STRONG> matches any 11-digit number.</span></span> <span data-ttu-id="88581-144">例如，如果您添加的规范化规则与以1425开头的11位数字相匹配，请确保将 " <STRONG>全部保留</STRONG> " 的值按限制性更强的 <STRONG>^ (1425 \ d {7}) $</STRONG> rule。</span><span class="sxs-lookup"><span data-stu-id="88581-144">If, for example, you add a normalization rule that matches 11-digit numbers that start with 1425, make sure that <STRONG>Keep All</STRONG> is sorted below the more restrictive <STRONG>^(1425\d{7})$</STRONG> rule.</span></span>

    
    </div>

11. <span data-ttu-id="88581-p116">（可选）输入一个号码来测试拨号计划，然后单击“执行”\*\*\*\*。测试结果会显示在“输入要测试的号码”\*\*\*\* 下。</span><span class="sxs-lookup"><span data-stu-id="88581-p116">(Optional) Enter a number to test the dial plan and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="88581-147">您可以保存尚未通过测试的拨号计划，并在稍后对其进行重新配置。</span><span class="sxs-lookup"><span data-stu-id="88581-147">You can save a dial plan that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="88581-148">有关详细信息，请参阅 <A href="lync-server-2013-test-voice-routing.md">在 Lync Server 2013 中测试语音路由</A>。</span><span class="sxs-lookup"><span data-stu-id="88581-148">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

12. <span data-ttu-id="88581-149">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="88581-149">Click **OK**.</span></span>

13. <span data-ttu-id="88581-150">在“拨号计划”\*\*\*\* 页上，单击“提交”\*\*\*\*，然后单击“全部提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="88581-150">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="88581-151">任何时候创建或修改拨号计划，都必须运行“全部提交”<STRONG></STRONG>命令以发布配置更改。</span><span class="sxs-lookup"><span data-stu-id="88581-151">Any time you create or modify a dial plan, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="88581-152">有关详细信息，请参阅操作文档中的在 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 中发布待处理的语音路由配置的更改</A> 。</span><span class="sxs-lookup"><span data-stu-id="88581-152">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="88581-153">另请参阅</span><span class="sxs-lookup"><span data-stu-id="88581-153">See Also</span></span>


[<span data-ttu-id="88581-154">在 Lync Server 2013 中创建拨号计划</span><span class="sxs-lookup"><span data-stu-id="88581-154">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
[<span data-ttu-id="88581-155">在 Lync Server 2013 中发布对语音路由配置所做的挂起更改</span><span class="sxs-lookup"><span data-stu-id="88581-155">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="88581-156">在 Lync Server 2013 中定义规范化规则</span><span class="sxs-lookup"><span data-stu-id="88581-156">Defining normalization rules in Lync Server 2013</span></span>](lync-server-2013-defining-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

