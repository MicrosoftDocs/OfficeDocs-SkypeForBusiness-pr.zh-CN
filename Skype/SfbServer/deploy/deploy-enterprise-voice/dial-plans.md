---
title: 在 Skype for Business Server 2015 中创建或修改拨号计划
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d2fef3d0-7e78-4591-b712-d62ac71d71a5
description: 摘要： 了解如何创建或修改拨号计划使用 Skype 业务 Server Control Panel。
ms.openlocfilehash: 9ded641ead3aef5cb6b42b27ca06da34ba9133c6
ms.sourcegitcommit: a5b8b0a1e5ae5eb718e296ca6df6687368ee9174
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2018
ms.locfileid: "19501061"
---
# <a name="create-or-modify-a-dial-plan-in-skype-for-business-server-2015"></a><span data-ttu-id="bb641-103">在 Skype for Business Server 2015 中创建或修改拨号计划</span><span class="sxs-lookup"><span data-stu-id="bb641-103">Create or modify a dial plan in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="bb641-104">**摘要：** 了解如何创建或修改拨号计划使用 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="bb641-104">**Summary:** Learn how to create or modify a dial plan by using the Skype for Business Server Control Panel.</span></span>
  
### <a name="to-create-a-dial-plan"></a><span data-ttu-id="bb641-105">创建拨号计划</span><span class="sxs-lookup"><span data-stu-id="bb641-105">To create a dial plan</span></span>

1. <span data-ttu-id="bb641-106">打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="bb641-106">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="bb641-107">在左侧导航栏中，单击“语音路由”****，然后单击“拨号计划”****。</span><span class="sxs-lookup"><span data-stu-id="bb641-107">In the left navigation bar, click **Voice Routing** and then click **Dial Plan**.</span></span>
    
3. <span data-ttu-id="bb641-108">在“拨号计划”**** 页上，单击“新建”****，然后为拨号计划选择作用域：</span><span class="sxs-lookup"><span data-stu-id="bb641-108">On the **Dial Plan** page, click **New** and select a scope for the dial plan:</span></span>
    
   - <span data-ttu-id="bb641-109">“站点拨号计划”**** 将应用于整个站点，分配给用户拨号计划的用户或组除外。</span><span class="sxs-lookup"><span data-stu-id="bb641-109">**Site dial plan** applies to an entire site, except any users or groups that are assigned to a user dial plan.</span></span> <span data-ttu-id="bb641-110">如果您选择的拨号计划作用域的**网站**，您必须从**选择站点**对话框中选择的网站。</span><span class="sxs-lookup"><span data-stu-id="bb641-110">If you select **Site** for a dial plan's scope, you must choose the site from the **Select a Site** dialog box.</span></span> <span data-ttu-id="bb641-111">如果已经为站点创建了拨号计划，则该站点不会显示在“选择站点”**** 对话框中。</span><span class="sxs-lookup"><span data-stu-id="bb641-111">If a dial plan has already been created for a site, the site does not appear in the **Select a Site** dialog box.</span></span>
    
   - <span data-ttu-id="bb641-112">“池拨号计划”**** 可以应用于公用电话交换网 (PSTN) 网关或注册器。</span><span class="sxs-lookup"><span data-stu-id="bb641-112">**Pool dial plan** can apply to a public switched telephone network (PSTN) gateway or a Registrar.</span></span> <span data-ttu-id="bb641-113">如果您选择的拨号计划作用域的**池**，从**选择服务**对话框中选择的 PSTN 网关或注册器。</span><span class="sxs-lookup"><span data-stu-id="bb641-113">If you select **Pool** for a dial plan's scope, choose the PSTN gateway or Registrar from the **Select a Service** dialog box.</span></span> <span data-ttu-id="bb641-114">如果已经为服务（PSTN 网关或注册器）创建了拨号计划，则该服务不会显示在列表中。</span><span class="sxs-lookup"><span data-stu-id="bb641-114">If a dial plan has already been created for a service (PSTN gateway or Registrar), the service does not appear in the list.</span></span>
    
   - <span data-ttu-id="bb641-115">“用户拨号计划”**** 可以应用于指定的用户或组。</span><span class="sxs-lookup"><span data-stu-id="bb641-115">**User dial plan** can be applied to specified users or groups.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="bb641-116">选择拨号计划作用域后，就无法更改。</span><span class="sxs-lookup"><span data-stu-id="bb641-116">After you select the dial plan scope, it cannot be changed.</span></span> 
  
4. <span data-ttu-id="bb641-p103">如果要创建用户拨号计划，请在“新建拨号计划”**** 对话框的“名称”**** 字段中输入描述性名称。保存此名称后，就无法更改。</span><span class="sxs-lookup"><span data-stu-id="bb641-p103">If you are creating a user dial plan, enter a descriptive name in the **Name** field on the **New Dial Plan** dialog box. After this name is saved, it cannot be changed.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="bb641-119">对于站点拨号计划，**名称**字段会使用站点名称预先填充，且无法更改。 > 对于池拨号计划，**名称**字段会使用 PSTN 网关或注册器名称预先填充，且不能更改。</span><span class="sxs-lookup"><span data-stu-id="bb641-119">For site dial plans, the **Name** field is prepopulated with the site name and cannot be changed.> For pool dial plans, the **Name** field is prepopulated with the PSTN gateway or Registrar name and cannot be changed.</span></span>
  
5. <span data-ttu-id="bb641-p104">“简单名称”**** 字段会使用与“名称”**** 字段中显示的相同名称预先填充。您可以选择编辑该字段来指定描述性更强的名称，以反映应用该拨号计划的站点、服务或用户。</span><span class="sxs-lookup"><span data-stu-id="bb641-p104">The **Simple name** field is prepopulated with the same name that appears in the **Name** field. You can optionally edit this field to specify a more descriptive name that reflects the site, service, or user to which the dial plan applies.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="bb641-122">此“简单名称”**** 在部署中的所有拨号计划内必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="bb641-122">The **Simple name** must be unique among all dial plans in your deployment.</span></span> <span data-ttu-id="bb641-123">它不能超过 256 个 Unicode 字符，其中每个可以是一个字母或数字字符，连字符 （-）、 句点 （.） 或下划线 (_)。 >**不支持**字符 RFC 3966 标准中定义包括空格和保留的字符 (http://www.ietf.org/rfc/rfc3966.txt)。</span><span class="sxs-lookup"><span data-stu-id="bb641-123">It cannot exceed 256 Unicode characters, each of which can be an alphabetic or numeric character, a hyphen (-), a period (.), or an underscore (_).> Characters **not supported** include spaces and Reserved characters as defined in RFC 3966 (http://www.ietf.org/rfc/rfc3966.txt).</span></span> <span data-ttu-id="bb641-124">保留的**简单名称**中**不支持**字符，包括： >";""/""?"":""@""&amp;""=""+""$""、"</span><span class="sxs-lookup"><span data-stu-id="bb641-124">Reserved characters that are **not supported** in the **Simple Name** include the following:> ";" "/" "?" ":" "@" "&amp;" "=" "+" "$" ","</span></span> 
  
6. <span data-ttu-id="bb641-125">（可选）在“说明”**** 字段中，您可以键入有关拨号计划的其他描述性信息。</span><span class="sxs-lookup"><span data-stu-id="bb641-125">(Optional) In the **Description** field, you can type additional descriptive information about the dial plan.</span></span>
    
7. <span data-ttu-id="bb641-p106">（可选）如果要将此拨号计划用作电话拨入式访问号码的区域，请指定“电话拨入式会议区域”****。如果不希望将此拨号计划用于电话拨入式访问号码，请将此字段留空。</span><span class="sxs-lookup"><span data-stu-id="bb641-p106">(Optional) If you want to use this dial plan as a region for dial-in access numbers, specify a **Dial-in conferencing region**. If you do not want to use this dial plan for dial-in access numbers, leave this field empty.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="bb641-128">电话拨入式会议区域需要将电话拨入式会议访问号码与一个或多个拨号计划相关联。</span><span class="sxs-lookup"><span data-stu-id="bb641-128">Dial-in conferencing regions are required to associate dial-in conferencing access numbers with one or more dial plans.</span></span> 
  
8. <span data-ttu-id="bb641-p107">（可选）在“外部访问前缀”\*\*\*\* 字段中，指定一个值，该值仅在用户需要拨打一个或多个附加的前导数字（例如 9）以拨通外线时使用。键入的前缀值不得超过四个字符（#、\* 和 0-9）。</span><span class="sxs-lookup"><span data-stu-id="bb641-p107">(Optional) In the **External access prefix** field, specify a value only if users need to dial one or more additional leading digits (for example, 9) to get an external line. You can type in a prefix value of up to four characters (#, \*, and 0-9).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="bb641-131">如果指定了外部访问前缀，则不需要创建新的规范化规则来满足前缀。</span><span class="sxs-lookup"><span data-stu-id="bb641-131">If you specify an external access prefix, you do not need to create a new normalization rule to accommodate the prefix.</span></span> 
  
9. <span data-ttu-id="bb641-132">按如下所示为拨号计划关联并配置规范化规则：</span><span class="sxs-lookup"><span data-stu-id="bb641-132">Associate and configure normalization rules for the dial plan as follows:</span></span>
    
    - <span data-ttu-id="bb641-133">若要从所有企业语音部署中可用的规范化规则的列表中选择一个或多个规则，请单击**选择**。</span><span class="sxs-lookup"><span data-stu-id="bb641-133">To choose one or more rules from a list of all normalization rules available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="bb641-134">在“选择规范化规则”**** 中，突出显示要与拨号计划关联的规则，然后单击“确定”****。</span><span class="sxs-lookup"><span data-stu-id="bb641-134">In **Select Normalization Rules**, highlight the rules you want to associate with the dial plan and then click **OK**.</span></span>
    
   - <span data-ttu-id="bb641-135">要定义新的规范化规则并将其与拨号计划相关联，请单击“新建”****。</span><span class="sxs-lookup"><span data-stu-id="bb641-135">To define a new normalization rule and associate it with the dial plan, click **New**.</span></span> <span data-ttu-id="bb641-136">有关定义新的规则的详细信息，请参阅[创建或修改规范化规则中的业务 2015 Skype](normalization-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="bb641-136">For details about defining a new rule, see [Create or modify a normalization rule in Skype for Business 2015](normalization-rules.md).</span></span>
    
   - <span data-ttu-id="bb641-137">要编辑已经与拨号计划关联的规范化规则，请突出显示相应的规则名称，然后单击“显示详细信息”****。</span><span class="sxs-lookup"><span data-stu-id="bb641-137">To edit a normalization rule that is already associated with the dial plan, highlight the rule name and click **Show details**.</span></span> 
    
   - <span data-ttu-id="bb641-138">要复制现有规范化规则以作为定义新规则的起点，请突出显示相应的规则名称，单击“复制”****，然后单击“粘贴”****。</span><span class="sxs-lookup"><span data-stu-id="bb641-138">To copy an existing normalization rule to use as a starting point for defining a new rule, highlight the rule name and click **Copy**, and then click **Paste**.</span></span> 
    
   - <span data-ttu-id="bb641-139">要从拨号计划中删除某个规范化规则，请突出显示相应的规则名称，然后单击“删除”****。</span><span class="sxs-lookup"><span data-stu-id="bb641-139">To remove a normalization rule from the dial plan, highlight the rule name and click **Remove**.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="bb641-140">每个拨号计划都必须至少有一个关联的规范化规则。</span><span class="sxs-lookup"><span data-stu-id="bb641-140">Each dial plan must have at least one associated normalization rule.</span></span> <span data-ttu-id="bb641-141">有关如何确定的规范化规则的所有拨号计划都需要，请参阅规划文档中的[规划出站语音路由中的业务服务器 2015 Skype](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md) 。</span><span class="sxs-lookup"><span data-stu-id="bb641-141">For information about how to determine all of the normalization rules a dial plan requires, see [Plan for outbound voice routing in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md) in the Planning documentation.</span></span>
  
10. <span data-ttu-id="bb641-142">确认正确的顺序排列的拨号计划的规范化规则。</span><span class="sxs-lookup"><span data-stu-id="bb641-142">Verify that the dial plan's normalization rules are arranged in the correct order.</span></span> <span data-ttu-id="bb641-143">若要更改列表中的规则的位置，请突出显示相应的规则名称然后单击向上或向下箭头。</span><span class="sxs-lookup"><span data-stu-id="bb641-143">To change a rule's position in the list, highlight the rule name and then click the up or down arrow.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="bb641-144">Skype 业务服务器从上向下遍历规范化规则列表，并使用第一个匹配已拨的号码的规则。</span><span class="sxs-lookup"><span data-stu-id="bb641-144">Skype for Business Server traverses the normalization rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="bb641-145">如果要配置拨号计划以使拨打号码可以匹配多个规范化规则，请确保限制较严格的规则排在限制较宽松的规则上方。</span><span class="sxs-lookup"><span data-stu-id="bb641-145">If you configure a dial plan so that a dialed number can match more than one normalization rule, make sure the more restrictive rules are sorted above the less restrictive ones.</span></span> <span data-ttu-id="bb641-146">> 的默认**保留所有**规范化规则 ^(\d{11})$ 匹配任何 11 位数字。</span><span class="sxs-lookup"><span data-stu-id="bb641-146">> The default **Keep All** normalization rule^(\d{11})$ matches any 11-digit number.</span></span> <span data-ttu-id="bb641-147">例如，如果您添加规范化规则相匹配的开始 1425年 11 位数字号码，请确保，下面更严格排序**全部保留**^(1425\d{7})$ 规则。</span><span class="sxs-lookup"><span data-stu-id="bb641-147">For example, if you add a normalization rule that matches 11-digit numbers that start with 1425, make sure that **Keep All** is sorted below the more restrictive^(1425\d{7})$ rule.</span></span>
  
11. <span data-ttu-id="bb641-p113">（可选）输入一个号码来测试拨号计划，然后单击“执行”****。测试结果会显示在“输入要测试的号码”**** 下。</span><span class="sxs-lookup"><span data-stu-id="bb641-p113">(Optional) Enter a number to test the dial plan and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>
    
12. <span data-ttu-id="bb641-150">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="bb641-150">Click **OK**.</span></span> 
    
13. <span data-ttu-id="bb641-151">在“拨号计划”**** 页上，单击“提交”****，然后单击“全部提交”****。</span><span class="sxs-lookup"><span data-stu-id="bb641-151">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="bb641-152">任何时候创建拨号计划，都必须运行“全部提交”**** 命令以发布配置更改。</span><span class="sxs-lookup"><span data-stu-id="bb641-152">Any time you create a dial plan, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="bb641-153">有关详细信息，请参阅操作文档中的[挂起更改语音路由配置中的业务 2015 Skype 的发布](voice-route-config-changes.md)。</span><span class="sxs-lookup"><span data-stu-id="bb641-153">For details, see [Publish pending changes to the voice routing configuration in Skype for Business 2015](voice-route-config-changes.md) in the Operations documentation.</span></span>
  
### <a name="to-modify-a-dial-plan"></a><span data-ttu-id="bb641-154">修改拨号计划</span><span class="sxs-lookup"><span data-stu-id="bb641-154">To modify a dial plan</span></span>

1.  <span data-ttu-id="bb641-155">以 RTCUniversalServerAdmins 组成员或 CsVoiceAdministrator、 CsServerAdministrator 或 CsAdministrator 角色的成员身份登录到计算机。</span><span class="sxs-lookup"><span data-stu-id="bb641-155">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="bb641-156">有关详细信息，请参阅**Delegate Setup Permissions**。</span><span class="sxs-lookup"><span data-stu-id="bb641-156">For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="bb641-157">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="bb641-157">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="bb641-158">在左侧导航栏中，单击“语音路由”****，然后单击“拨号计划”****。</span><span class="sxs-lookup"><span data-stu-id="bb641-158">In the left navigation bar, click **Voice Routing** and then click **Dial Plan**.</span></span>
    
4. <span data-ttu-id="bb641-159">在“拨号计划”**** 页上，双击某个拨号计划名称。</span><span class="sxs-lookup"><span data-stu-id="bb641-159">On the **Dial Plan** page, double-click a dial plan name.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="bb641-p116">拨号计划的作用域和名称是在创建该拨号计划时设置的，且不能更改。</span><span class="sxs-lookup"><span data-stu-id="bb641-p116">The dial plan scope and name were set when the dial plan was created. They cannot be changed.</span></span> 
  
5. <span data-ttu-id="bb641-162">（可选）在“编辑拨号计划”**** 中，编辑“简单名称”**** 字段，该字段会预填充“名称”**** 字段中显示的相同名称，以指定反映应用该拨号计划的站点、服务或用户的更具描述性的名称。</span><span class="sxs-lookup"><span data-stu-id="bb641-162">(Optional) In **Edit Dial Plan**, edit the **Simple name** field, which is prepopulated with the same name that appears in the **Name** field to specify a more descriptive name that reflects the site, service, or user to which the dial plan applies.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="bb641-163">**简单名称**必须是唯一的 Lync Server 2013 部署中的所有拨号计划。</span><span class="sxs-lookup"><span data-stu-id="bb641-163">The **Simple name** must be unique among all dial plans within the Lync Server 2013 deployment.</span></span> <span data-ttu-id="bb641-164">它不能超过 256 个 Unicode 字符，其中每个可以是一个字母或数字字符，连字符 （-）、 句点 （.）、 一个加号 （+），或一个下划线 (_)。 >**简单名称**字段中不允许使用空格。</span><span class="sxs-lookup"><span data-stu-id="bb641-164">It cannot exceed 256 Unicode characters, each of which can be an alphabetic or numeric character, a hyphen (-), a period (.), a plus sign (+), or an underscore (_).> Spaces are not allowed in the **Simple name** field.</span></span>
  
6. <span data-ttu-id="bb641-165">（可选）在“说明”**** 字段中，键入有关拨号计划的描述性信息。</span><span class="sxs-lookup"><span data-stu-id="bb641-165">(Optional) In the **Description** field, type descriptive information about the dial plan.</span></span>
    
7. <span data-ttu-id="bb641-p118">（可选）如果要将此拨号计划用作电话拨入式访问号码的区域，请指定“电话拨入式会议区域”****。如果不希望将此拨号计划用于电话拨入式访问号码，请将此字段留空。</span><span class="sxs-lookup"><span data-stu-id="bb641-p118">(Optional) If you want to use this dial plan as a region for dial-in access numbers, specify a **Dial-in conferencing region**. If you do not want to use this dial plan for dial-in access numbers, leave this field empty.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="bb641-168">电话拨入式会议区域需要将电话拨入式会议访问号码与一个或多个拨号计划相关联。</span><span class="sxs-lookup"><span data-stu-id="bb641-168">Dial-in conferencing regions are required to associate dial-in conferencing access numbers with one or more dial plans.</span></span> 
  
8. <span data-ttu-id="bb641-p119">（可选）在“外部访问前缀”\*\*\*\* 字段中，指定一个值，该值仅在用户需要拨打一个或多个附加的前导数字（例如 9）以拨通外线时使用。键入的前缀值不得超过四个字符（即 #、\* 和 0-9）。</span><span class="sxs-lookup"><span data-stu-id="bb641-p119">(Optional) In the **External access prefix** field, specify a value only if users need to dial one or more additional leading digits to get an external line (for example, 9). You can type in a prefix value of up to four characters (that is, #, \*, and 0-9).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="bb641-171">如果指定了外部访问前缀，则不需要创建新的规范化规则来满足前缀。</span><span class="sxs-lookup"><span data-stu-id="bb641-171">If you specify an external access prefix, you do not need to create a new normalization rule to accommodate the prefix.</span></span> 
  
9. <span data-ttu-id="bb641-172">为拨号计划关联并配置规范化规则：</span><span class="sxs-lookup"><span data-stu-id="bb641-172">Associate and configure normalization rules for the dial plan:</span></span>
    
   - <span data-ttu-id="bb641-173">若要从所有企业语音部署中可用的规范化规则的列表中选择一个或多个规则，请单击**选择**。</span><span class="sxs-lookup"><span data-stu-id="bb641-173">To choose one or more rules from a list of all normalization rules available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="bb641-174">在“选择规范化规则”**** 对话框中，突出显示要与拨号计划关联的规则，然后单击“确定”****。</span><span class="sxs-lookup"><span data-stu-id="bb641-174">In the **Select Normalization Rules** dialog box, highlight the rules that you want to associate with the dial plan and then click **OK**.</span></span>
    
   - <span data-ttu-id="bb641-175">要定义新的规范化规则并将其与拨号计划相关联，请单击“新建”****。</span><span class="sxs-lookup"><span data-stu-id="bb641-175">To define a new normalization rule and associate it with the dial plan, click **New**.</span></span> <span data-ttu-id="bb641-176">有关定义新的规则的详细信息，请参阅[创建或修改规范化规则中的业务 2015 Skype](normalization-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="bb641-176">For details about defining a new rule, see [Create or modify a normalization rule in Skype for Business 2015](normalization-rules.md).</span></span>
    
   - <span data-ttu-id="bb641-177">要编辑已经与拨号计划关联的规范化规则，请突出显示相应的规则名称，然后单击“显示详细信息”****。</span><span class="sxs-lookup"><span data-stu-id="bb641-177">To edit a normalization rule that is already associated with the dial plan, highlight the rule name and click **Show details**.</span></span> 
    
   - <span data-ttu-id="bb641-178">要复制现有规范化规则以作为定义新规则的起点，请突出显示相应的规则名称，单击“复制”****，然后单击“粘贴”****。</span><span class="sxs-lookup"><span data-stu-id="bb641-178">To copy an existing normalization rule to use as a starting point for defining a new rule, highlight the rule name and click **Copy**, and then click **Paste**.</span></span> 
    
   - <span data-ttu-id="bb641-179">要从拨号计划中删除某个规范化规则，请突出显示相应的规则名称，然后单击“删除”****。</span><span class="sxs-lookup"><span data-stu-id="bb641-179">To remove a normalization rule from the dial plan, highlight the rule name and click **Remove**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="bb641-180">每个拨号计划都必须至少有一个关联的规范化规则。</span><span class="sxs-lookup"><span data-stu-id="bb641-180">Each dial plan must have at least one associated normalization rule.</span></span> <span data-ttu-id="bb641-181">计划都需要有关如何确定的规范化规则的所有拨入详细信息，请参阅规划文档中的[规划出站语音路由中的业务服务器 2015 Skype](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md) 。</span><span class="sxs-lookup"><span data-stu-id="bb641-181">For details about how to determine all of the normalization rules a dial plan requires, see [Plan for outbound voice routing in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md) in the Planning documentation.</span></span>
  
10. <span data-ttu-id="bb641-182">确认正确的顺序排列的拨号计划的规范化规则。</span><span class="sxs-lookup"><span data-stu-id="bb641-182">Verify that the dial plan's normalization rules are arranged in the correct order.</span></span> <span data-ttu-id="bb641-183">若要更改列表中的规则的位置，请突出显示相应的规则名称然后单击向上或向下箭头。</span><span class="sxs-lookup"><span data-stu-id="bb641-183">To change a rule's position in the list, highlight the rule name and then click the up or down arrow.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="bb641-184">Skype 业务服务器从上向下遍历规范化规则列表，并使用第一个匹配已拨的号码的规则。</span><span class="sxs-lookup"><span data-stu-id="bb641-184">Skype for Business Server traverses the normalization rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="bb641-185">如果要配置拨号计划以使拨打号码可以匹配多个规范化规则，请确保限制较严格的规则排在限制较宽松的规则上方。</span><span class="sxs-lookup"><span data-stu-id="bb641-185">If you configure a dial plan so that a dialed number can match more than one normalization rule, make sure the more restrictive rules are sorted above the less restrictive ones.</span></span> <span data-ttu-id="bb641-186">> 的默认**保留所有**规范化规则 ^(\d{11})$ 匹配任何 11 位数字。</span><span class="sxs-lookup"><span data-stu-id="bb641-186">> The default **Keep All** normalization rule^(\d{11})$ matches any 11-digit number.</span></span> <span data-ttu-id="bb641-187">如果，例如，添加规范化规则相匹配的开始 1425年 11 位数字号码，请确保，下面更严格排序**全部保留**^(1425\d{7})$ 规则。</span><span class="sxs-lookup"><span data-stu-id="bb641-187">If, for example, you add a normalization rule that matches 11-digit numbers that start with 1425, make sure that **Keep All** is sorted below the more restrictive^(1425\d{7})$ rule.</span></span>
  
11. <span data-ttu-id="bb641-p125">（可选）输入一个号码来测试拨号计划，然后单击“执行”****。测试结果会显示在“输入要测试的号码”**** 下。</span><span class="sxs-lookup"><span data-stu-id="bb641-p125">(Optional) Enter a number to test the dial plan and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="bb641-190">您可以保存尚未通过测试的拨号计划，并在稍后对其进行重新配置。</span><span class="sxs-lookup"><span data-stu-id="bb641-190">You can save a dial plan that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="bb641-191">有关详细信息，请参阅[测试语音路由](http://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx)。</span><span class="sxs-lookup"><span data-stu-id="bb641-191">For details, see [Testing Voice Routing](http://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx).</span></span> 
  
12. <span data-ttu-id="bb641-192">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="bb641-192">Click **OK**.</span></span> 
    
13. <span data-ttu-id="bb641-193">在“拨号计划”**** 页上，单击“提交”****，然后单击“全部提交”****。</span><span class="sxs-lookup"><span data-stu-id="bb641-193">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="bb641-194">任何时候创建或修改拨号计划，都必须运行“全部提交”**** 命令以发布配置更改。</span><span class="sxs-lookup"><span data-stu-id="bb641-194">Any time you create or modify a dial plan, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="bb641-195">有关详细信息，请参阅操作文档中的[挂起更改语音路由配置中的业务 2015 Skype 的发布](voice-route-config-changes.md)。</span><span class="sxs-lookup"><span data-stu-id="bb641-195">For details, see [Publish pending changes to the voice routing configuration in Skype for Business 2015](voice-route-config-changes.md) in the Operations documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="bb641-196">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bb641-196">See also</span></span>

[<span data-ttu-id="bb641-197">挂起更改语音路由配置中的业务 2015 Skype 的发布</span><span class="sxs-lookup"><span data-stu-id="bb641-197">Publish pending changes to the voice routing configuration in Skype for Business 2015</span></span>](voice-route-config-changes.md)