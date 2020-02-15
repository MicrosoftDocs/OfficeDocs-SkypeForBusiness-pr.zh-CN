---
title: Lync Server 2013：拨号计划和规范化规则
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial plans and normalization rules
ms:assetid: fde45195-6eb4-403c-9094-57df7fc0bd2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413082(v=OCS.15)
ms:contentKeyID: 48185960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4adcd2cd6bebfb0797427d15819399c9b2b9f86d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036752"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dial-plans-and-normalization-rules-in-lync-server-2013"></a><span data-ttu-id="c6314-102">Lync Server 2013 中的拨号计划和规范化规则</span><span class="sxs-lookup"><span data-stu-id="c6314-102">Dial plans and normalization rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c6314-103">_**上次修改的主题：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="c6314-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="c6314-104">拨号计划是一组指定的规范化规则，可将指定位置、单个用户或联系人对象的电话号码转换为统一标准 (E.164) 格式，以进行电话授权和呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="c6314-104">A dial plan is a named set of normalization rules that translates phone numbers for a named location, individual user, or contact object into a single standard (E.164) format for purposes of phone authorization and call routing.</span></span>

<span data-ttu-id="c6314-105">规范化规则定义如何针对每个指定的位置、用户或联系人对象来路由以不同格式表示的电话号码。</span><span class="sxs-lookup"><span data-stu-id="c6314-105">Normalization rules define how phone numbers expressed in various formats are to be routed for each specified location, user, or contact object.</span></span> <span data-ttu-id="c6314-106">相同的拨号字符串可能会以不同的方式进行解释和转换，具体取决于拨打该号码的位置以及进行呼叫的人员或联系人对象。</span><span class="sxs-lookup"><span data-stu-id="c6314-106">The same dial string may be interpreted and translated differently, depending on the location from which it is dialed and the person or contact object making the call.</span></span>

<div>

## <a name="dial-plan-scope"></a><span data-ttu-id="c6314-107">拨号计划作用域</span><span class="sxs-lookup"><span data-stu-id="c6314-107">Dial Plan Scope</span></span>

<span data-ttu-id="c6314-108">拨号计划的“作用域”\*\* 决定了拨号计划的应用层级。</span><span class="sxs-lookup"><span data-stu-id="c6314-108">A dial plan’s *scope* determines the hierarchical level at which the dial plan can be applied.</span></span> <span data-ttu-id="c6314-109">在 Lync Server 中，可以为用户分配特定的每用户拨号计划。</span><span class="sxs-lookup"><span data-stu-id="c6314-109">In Lync Server, a user can be assigned a specific per-user dial plan.</span></span> <span data-ttu-id="c6314-110">如果没有分配用户拨号计划，则会应用注册器池拨号计划。</span><span class="sxs-lookup"><span data-stu-id="c6314-110">If a user dial plan is not assigned, the Registrar pool dial plan is applied.</span></span> <span data-ttu-id="c6314-111">如果没有注册器池拨号计划，则会应用站点拨号计划。</span><span class="sxs-lookup"><span data-stu-id="c6314-111">If there is no Registrar pool dial plan, the site dial plan is applied.</span></span> <span data-ttu-id="c6314-112">最后，如果没有其他适用于该用户的拨号计划，则会应用全局拨号计划。</span><span class="sxs-lookup"><span data-stu-id="c6314-112">Finally, if there is no other dial plan applicable to the user, the global dial plan is applied.</span></span>

<span data-ttu-id="c6314-113">客户端通过在用户登录 Lync Server 时提供的带内设置设置获取拨号计划作用域级别。</span><span class="sxs-lookup"><span data-stu-id="c6314-113">Clients obtain dial plan scope levels through in-band provisioning settings that are provided when users log on to Lync Server.</span></span> <span data-ttu-id="c6314-114">作为管理员，您可以使用 Lync Server 控制面板管理和分配拨号计划作用域级别。</span><span class="sxs-lookup"><span data-stu-id="c6314-114">As the administrator, you can manage and assign dial plan scope levels by using Lync Server Control Panel.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c6314-115">服务级公用电话交换网（PSTN）网关拨号计划应用于来自特定网关的传入呼叫。</span><span class="sxs-lookup"><span data-stu-id="c6314-115">The service level public switched telephone network (PSTN) gateway dial plan is applied to the incoming calls from a particular gateway.</span></span>



</div>

<span data-ttu-id="c6314-116">拨号计划作用域级别定义如下：</span><span class="sxs-lookup"><span data-stu-id="c6314-116">Dial plan scope levels are defined as follows:</span></span>

  - <span data-ttu-id="c6314-117">**用户拨号计划：** 可分配给各个用户、组或联系人对象。</span><span class="sxs-lookup"><span data-stu-id="c6314-117">**User dial plan:** Can be assigned to individual users, groups, or contact objects.</span></span> <span data-ttu-id="c6314-118">在收到呼叫时，语音应用程序可以查找每用户拨号计划，并将手机上下文设置为 "用户-默认"。</span><span class="sxs-lookup"><span data-stu-id="c6314-118">Voice applications can look up a per-user dial plan when a call is received with the phone-context set to user-default.</span></span> <span data-ttu-id="c6314-119">出于分配拨号计划的目的，contact 对象被视为单个用户。</span><span class="sxs-lookup"><span data-stu-id="c6314-119">For the purpose of assigning a dial plan, a contact object is treated as an individual user.</span></span>

  - <span data-ttu-id="c6314-120">**池拨号计划：** 可在您的拓扑中的任何 PSTN 网关或注册器的服务级别创建。</span><span class="sxs-lookup"><span data-stu-id="c6314-120">**Pool dial plan:** Can be created at the service level for any PSTN gateway or Registrar in your topology.</span></span> <span data-ttu-id="c6314-121">要定义池拨号计划，必须指定要应用拨号计划的特定服务（PSTN 网关或注册器池）。</span><span class="sxs-lookup"><span data-stu-id="c6314-121">To define a pool dial plan, you must specify the particular service (PSTN gateway or Registrar pool) to which the dial plan applies.</span></span>

  - <span data-ttu-id="c6314-122">**网站拨号计划：** 可以为整个网站创建，但分配了池拨号计划或用户拨号计划的任何用户、组或联系人对象除外。</span><span class="sxs-lookup"><span data-stu-id="c6314-122">**Site dial plan:** Can be created for an entire site, except for any users, groups, or contact objects that are assigned a pool dial plan or user dial plan.</span></span> <span data-ttu-id="c6314-123">要定义站点拨号计划，必须指定要应用拨号计划的站点。</span><span class="sxs-lookup"><span data-stu-id="c6314-123">To define a site dial plan, you must specify the site to which the dial plan applies.</span></span>

  - <span data-ttu-id="c6314-124">**全局拨号计划：** 随产品一起安装的默认拨号计划。</span><span class="sxs-lookup"><span data-stu-id="c6314-124">**Global dial plan:** The default dial plan installed with the product.</span></span> <span data-ttu-id="c6314-125">可以编辑全局拨号计划，但无法将其删除。</span><span class="sxs-lookup"><span data-stu-id="c6314-125">You can edit the global dial plan, but you cannot delete it.</span></span> <span data-ttu-id="c6314-126">此拨号计划适用于部署中的所有企业语音用户、组和联系人对象，除非您使用更具体的作用域配置和分配拨号计划。</span><span class="sxs-lookup"><span data-stu-id="c6314-126">This dial plan applies to all Enterprise Voice users, groups, and contact objects in your deployment, unless you configure and assign a dial plan with a more specific scope.</span></span>

</div>

<div>

## <a name="planning-for-dial-plans"></a><span data-ttu-id="c6314-127">规划拨号计划</span><span class="sxs-lookup"><span data-stu-id="c6314-127">Planning for Dial Plans</span></span>

<span data-ttu-id="c6314-128">若要规划拨号计划，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="c6314-128">To plan a dial plan, follow these steps:</span></span>

  - <span data-ttu-id="c6314-129">列出组织拥有 office 的所有区域设置。</span><span class="sxs-lookup"><span data-stu-id="c6314-129">List all the locales in which your organization has an office.</span></span>
    
    <span data-ttu-id="c6314-130">列表必须是最新的，并且是完整的。</span><span class="sxs-lookup"><span data-stu-id="c6314-130">The list must be up-to-date and complete.</span></span> <span data-ttu-id="c6314-131">随着公司的发展，将需要对该列表进行修订。</span><span class="sxs-lookup"><span data-stu-id="c6314-131">It will need to be revised as company organization evolves.</span></span> <span data-ttu-id="c6314-132">在具有多个小型分支机构的大型跨国公司中，这可能是一项非常耗时的任务。</span><span class="sxs-lookup"><span data-stu-id="c6314-132">In a large, multinational company with numerous small branch offices, this can be a time-consuming task.</span></span>

  - <span data-ttu-id="c6314-133">标识每个网站的有效数字模式。</span><span class="sxs-lookup"><span data-stu-id="c6314-133">Identify valid number patterns for each site.</span></span>
    
    <span data-ttu-id="c6314-p109">在规划拨号计划时，最耗时的任务就是确定每个站点的有效号码模式。在某些情况下，尤其是当相应站点位于同一个国家/地区甚至同一个大陆上时，可以将为一个拨号计划编写的规范化规则复制到其他拨号计划中。在另一些情况下，只需对一个拨号计划中的号码进行微小的更改即可将这些号码用于其他拨号计划。</span><span class="sxs-lookup"><span data-stu-id="c6314-p109">The most time-consuming part of planning your dial plans is identifying the valid number patterns for each site. In some cases, you may be able to copy normalization rules that you have written for one dial plan to other dial plans, especially if the corresponding sites are within the same country/region or even continent. In other cases, small changes to numbers in one dial plan may be enough to use them in other dial plans.</span></span>

  - <span data-ttu-id="c6314-137">开发用于命名拨号计划的组织范围的方案。</span><span class="sxs-lookup"><span data-stu-id="c6314-137">Develop an organization-wide scheme for naming dial plans.</span></span>
    
    <span data-ttu-id="c6314-138">实行标准命名方案可确保组织内的一致性，并使维护和更新更加容易。</span><span class="sxs-lookup"><span data-stu-id="c6314-138">Adopting a standard naming scheme assures consistency across an organization and makes maintenance and updates easier.</span></span>

  - <span data-ttu-id="c6314-139">确定单个位置是否需要多个拨号计划。</span><span class="sxs-lookup"><span data-stu-id="c6314-139">Decide whether multiple dial plans are required for a single location.</span></span>
    
    <span data-ttu-id="c6314-140">如果您的组织在多个位置维护单个拨号计划，您可能仍需要为从专用交换机（PBX）迁移的企业语音用户创建单独的拨号计划，并且需要保留其现有分机的用户。</span><span class="sxs-lookup"><span data-stu-id="c6314-140">If your organization maintains a single dial plan across multiple locations, you may still need to create a separate dial plan for Enterprise Voice users who are migrating from a private branch exchange (PBX) and who need to have their existing extensions retained.</span></span>

  - <span data-ttu-id="c6314-141">确定是否需要每用户拨号计划。</span><span class="sxs-lookup"><span data-stu-id="c6314-141">Decide whether per-user dial plans are required.</span></span> <span data-ttu-id="c6314-142">例如，如果在使用中央站点注册的分支站点上有用户，或者如果您拥有在 Survivable 分支设备上注册的用户，则可以考虑使用每用户拨号计划和规范化规则的此类用户的特殊拨号方案。.</span><span class="sxs-lookup"><span data-stu-id="c6314-142">For example, if you have users at a branch site who are registered with the central site or if you have users who are registered on a Survivable Branch Appliance, you can consider special dialing scenarios for such users using per-user dial plans and normalization rules.</span></span> <span data-ttu-id="c6314-143">有关详细信息，请参阅[Lync Server 2013 的分支站点恢复要求](lync-server-2013-branch-site-resiliency-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c6314-143">For details, see [Branch-site resiliency requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).</span></span>

  - <span data-ttu-id="c6314-144">确定拨号计划作用域（如本主题前面所述）。</span><span class="sxs-lookup"><span data-stu-id="c6314-144">Determine dial plan scope (as previously described in this topic).</span></span>

<span data-ttu-id="c6314-145">若要创建拨号计划，请根据需要通过使用 Lync Server 控制面板或 Lync Server 命令行管理程序来指定以下字段中的值。</span><span class="sxs-lookup"><span data-stu-id="c6314-145">To create a dial plan, you specify values in the following fields, as required, by using Lync Server Control Panel or Lync Server Management Shell.</span></span>

<div>

## <a name="name-and-simple-name"></a><span data-ttu-id="c6314-146">名称和简单名称</span><span class="sxs-lookup"><span data-stu-id="c6314-146">Name and Simple Name</span></span>

<span data-ttu-id="c6314-147">对于用户拨号计划，应指定用于标识将向其分配拨号计划的用户、组或联系人对象的描述性名称。</span><span class="sxs-lookup"><span data-stu-id="c6314-147">For user dial plans, you should specify a descriptive name that identifies the users, groups, or contact objects to which the dial plan will be assigned.</span></span> <span data-ttu-id="c6314-148">对于站点拨号计划，“名称”字段会使用站点名称预先填充，且不能更改。</span><span class="sxs-lookup"><span data-stu-id="c6314-148">For site dial plans, the Name field is prepopulated with the site name and cannot be changed.</span></span> <span data-ttu-id="c6314-149">对于池拨号计划，"名称" 字段会使用 PSTN 网关或前端池完全限定域名（FQDN）进行预填充，且不能更改。</span><span class="sxs-lookup"><span data-stu-id="c6314-149">For pool dial plans, the Name field is prepopulated with the PSTN gateway or Front End pool fully qualified domain name (FQDN) and cannot be changed.</span></span>

<span data-ttu-id="c6314-150">拨号计划“简单名称”\*\* 会使用派生自拨号计划名称的字符串预先填充。</span><span class="sxs-lookup"><span data-stu-id="c6314-150">The dial plan *Simple Name* is prepopulated with a string that is derived from the dial plan name.</span></span> <span data-ttu-id="c6314-151">"简单名称" 字段是可编辑的，这使您可以为拨号计划创建更具描述性的命名约定。</span><span class="sxs-lookup"><span data-stu-id="c6314-151">The Simple Name field is editable, which enables you to create a more descriptive naming convention for your dial plans.</span></span> <span data-ttu-id="c6314-152">\*\*“简单名称”值不能为空，且必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="c6314-152">The *Simple Name* value cannot be empty and must be unique.</span></span> <span data-ttu-id="c6314-153">最佳做法是为整个组织制定命名约定，然后在所有网站和用户中一致地使用此约定。</span><span class="sxs-lookup"><span data-stu-id="c6314-153">A best practice is to develop a naming convention for your entire organization and then use this convention consistently across all sites and users.</span></span>

</div>

<div>

## <a name="description"></a><span data-ttu-id="c6314-154">说明</span><span class="sxs-lookup"><span data-stu-id="c6314-154">Description</span></span>

<span data-ttu-id="c6314-p113">建议您键入一个要应用相应的拨号计划的通用可辨识地理位置名称。例如，如果拨号计划的名称是 London.Contoso.com，则建议的说明将为 London。</span><span class="sxs-lookup"><span data-stu-id="c6314-p113">We recommend that you type the common, recognizable name of the geographic location to which the corresponding dial plan applies. For example, if the dial plan name is London.Contoso.com, the recommended description would be London.</span></span>

</div>

<div>

## <a name="dial-in-conferencing-region"></a><span data-ttu-id="c6314-157">电话拨入式会议区域</span><span class="sxs-lookup"><span data-stu-id="c6314-157">Dial-in Conferencing Region</span></span>

<span data-ttu-id="c6314-158">如果要部署电话拨入式会议，则需要指定电话拨入式会议区域，以将电话拨入式会议访问号码与拨号计划关联起来。</span><span class="sxs-lookup"><span data-stu-id="c6314-158">If you are deploying dial-in conferencing, you will need to specify a dial-in conferencing region to associate dial-in conferencing access numbers with a dial plan.</span></span>

</div>

<div>

## <a name="external-access-prefix"></a><span data-ttu-id="c6314-159">外部访问前缀</span><span class="sxs-lookup"><span data-stu-id="c6314-159">External Access Prefix</span></span>

<span data-ttu-id="c6314-160">如果用户需要拨打一个或多个附加的前导数字（\#例如\*9）以获取外部线路，则可以指定最多为四个字符（、和0-9）的外部访问前缀。</span><span class="sxs-lookup"><span data-stu-id="c6314-160">You can specify an external access prefix of up to four characters (\#, \*, and 0-9) if users need to dial one or more additional leading digits (for example, 9) to get an external line.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c6314-161">如果指定了外部访问前缀，则不需要另外创建规范化规则来满足前缀。</span><span class="sxs-lookup"><span data-stu-id="c6314-161">If you specify an external access prefix, you do not need to create an additional normalization rule to accommodate the prefix.</span></span>



</div>

</div>

</div>

<div>

## <a name="normalization-rules"></a><span data-ttu-id="c6314-162">规范化规则</span><span class="sxs-lookup"><span data-stu-id="c6314-162">Normalization Rules</span></span>

<span data-ttu-id="c6314-163">规范化规则定义如何针对命名的位置来路由以不同格式表示的电话号码。</span><span class="sxs-lookup"><span data-stu-id="c6314-163">Normalization rules define how phone numbers expressed in various formats are to be routed for the named location.</span></span> <span data-ttu-id="c6314-164">相同的号码字符串可能会以不同的方式进行解释和转换，具体取决于从中拨号的区域设置。</span><span class="sxs-lookup"><span data-stu-id="c6314-164">The same number string may be interpreted and translated differently, depending on the locale from which it is dialed.</span></span> <span data-ttu-id="c6314-165">规范化规则是呼叫路由所必需的，因为用户在其联系人列表中输入电话号码时，可以而且确实会使用各种格式。</span><span class="sxs-lookup"><span data-stu-id="c6314-165">Normalization rules are necessary for call routing because users can, and do, use various formats when entering phone numbers in their Contacts lists.</span></span>

<span data-ttu-id="c6314-166">规范化用户提供的电话号码提供了一个一致的格式，可促进以下任务：</span><span class="sxs-lookup"><span data-stu-id="c6314-166">Normalizing user-supplied phone numbers provides a consistent format that facilitates the following tasks:</span></span>

  - <span data-ttu-id="c6314-167">将已拨打的号码与预期收件人的 SIP URI 进行匹配。</span><span class="sxs-lookup"><span data-stu-id="c6314-167">Match a dialed number to the intended recipient’s SIP-URI.</span></span>

  - <span data-ttu-id="c6314-168">将拨号授权规则应用于呼叫方。</span><span class="sxs-lookup"><span data-stu-id="c6314-168">Apply dialing authorization rules to the calling party.</span></span>

<span data-ttu-id="c6314-169">规范化规则可能需要考虑下列号码字段：</span><span class="sxs-lookup"><span data-stu-id="c6314-169">The following number fields are among those that your normalization rules may need to account for:</span></span>

  - <span data-ttu-id="c6314-170">拨号计划</span><span class="sxs-lookup"><span data-stu-id="c6314-170">Dial plan</span></span>

  - <span data-ttu-id="c6314-171">国家/地区代码</span><span class="sxs-lookup"><span data-stu-id="c6314-171">Country code</span></span>

  - <span data-ttu-id="c6314-172">区域代码</span><span class="sxs-lookup"><span data-stu-id="c6314-172">Area code</span></span>

  - <span data-ttu-id="c6314-173">分机号长度</span><span class="sxs-lookup"><span data-stu-id="c6314-173">Length of extension</span></span>

  - <span data-ttu-id="c6314-174">站点前缀</span><span class="sxs-lookup"><span data-stu-id="c6314-174">Site prefix</span></span>

<div>

## <a name="creating-normalization-rules"></a><span data-ttu-id="c6314-175">创建规范化规则</span><span class="sxs-lookup"><span data-stu-id="c6314-175">Creating Normalization Rules</span></span>

<span data-ttu-id="c6314-176">规范化规则使用 .NET Framework 正则表达式指定数字匹配模式，服务器使用该模式将拨号串转换为 E.164 格式，以便执行反向号码查找。</span><span class="sxs-lookup"><span data-stu-id="c6314-176">Normalization rules use .NET Framework regular expressions to specify numeric match patterns that the server uses to translate dial strings to E.164 format for the purpose of performing reverse number lookup.</span></span> <span data-ttu-id="c6314-177">可以在 Lync Server 控制面板中创建规范化规则，方法是手动输入表达式，或者输入起始数字和要匹配的拨号字符串的长度，让 Lync Server 控制面板生成相应的正则表达式。</span><span class="sxs-lookup"><span data-stu-id="c6314-177">You create normalization rules in the Lync Server Control Panel either by entering the expressions manually, or by entering the starting digits and the length of the dial strings to be matched and letting the Lync Server Control Panel generate the corresponding regular expression for you.</span></span> <span data-ttu-id="c6314-178">无论采用何种方式，完成操作后，都可以输入一个测试号码来验证规范化规则能否按预期工作。</span><span class="sxs-lookup"><span data-stu-id="c6314-178">Either way, when you finish, you can enter a test number to verify that the normalization rule works as expected.</span></span>

<span data-ttu-id="c6314-179">有关使用 .NET Framework 正则表达式的详细信息，请参阅位于的[http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927)".Net Framework 正则表达式"。</span><span class="sxs-lookup"><span data-stu-id="c6314-179">For details about using .NET Framework regular expressions, see ".NET Framework Regular Expressions" at [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927).</span></span>

</div>

<span id="BKMK_SampleNormalizationRules"></span>

<div>

## <a name="sample-normalization-rules"></a><span data-ttu-id="c6314-180">规范化规则示例</span><span class="sxs-lookup"><span data-stu-id="c6314-180">Sample Normalization Rules</span></span>

<span data-ttu-id="c6314-p116">下表显示以 .NET Framework 正则表达式编写的规范化规则示例。这些仅为示例，不应作为创建自己的规范化规则时的规定性参考。</span><span class="sxs-lookup"><span data-stu-id="c6314-p116">The following table shows sample normalization rules that are written as .NET Framework regular expressions. The samples are examples only and are not meant to be a prescriptive reference for creating your own normalization rules.</span></span>

### <a name="table-1normalization-rules-using-net-framework-regular-expressions"></a><span data-ttu-id="c6314-183">表 1. 使用 .NET Framework 正则表达式的规范化规则</span><span class="sxs-lookup"><span data-stu-id="c6314-183">Table 1.Normalization Rules Using .NET Framework Regular Expressions</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c6314-184">规则名称</span><span class="sxs-lookup"><span data-stu-id="c6314-184">Rule name</span></span></th>
<th><span data-ttu-id="c6314-185">说明</span><span class="sxs-lookup"><span data-stu-id="c6314-185">Description</span></span></th>
<th><span data-ttu-id="c6314-186">号码模式</span><span class="sxs-lookup"><span data-stu-id="c6314-186">Number pattern</span></span></th>
<th><span data-ttu-id="c6314-187">Translation</span><span class="sxs-lookup"><span data-stu-id="c6314-187">Translation</span></span></th>
<th><span data-ttu-id="c6314-188">示例</span><span class="sxs-lookup"><span data-stu-id="c6314-188">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c6314-189">4digitExtension</span><span class="sxs-lookup"><span data-stu-id="c6314-189">4digitExtension</span></span></p></td>
<td><p><span data-ttu-id="c6314-190">转换 4 位分机号</span><span class="sxs-lookup"><span data-stu-id="c6314-190">Translates 4-digit extensions</span></span></p></td>
<td><p><span data-ttu-id="c6314-191">^ （\d{4}） $</span><span class="sxs-lookup"><span data-stu-id="c6314-191">^(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="c6314-192">+ 1425555 $ 1</span><span class="sxs-lookup"><span data-stu-id="c6314-192">+1425555$1</span></span></p></td>
<td><p><span data-ttu-id="c6314-193">将 0100 转换为 +14255550100</span><span class="sxs-lookup"><span data-stu-id="c6314-193">0100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6314-194">5digitExtension</span><span class="sxs-lookup"><span data-stu-id="c6314-194">5digitExtension</span></span></p></td>
<td><p><span data-ttu-id="c6314-195">转换 5 位分机号</span><span class="sxs-lookup"><span data-stu-id="c6314-195">Translates 5-digit extensions</span></span></p></td>
<td><p><span data-ttu-id="c6314-196">^ 5 （\d{4}） $</span><span class="sxs-lookup"><span data-stu-id="c6314-196">^5(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="c6314-197">+ 1425555 $ 1</span><span class="sxs-lookup"><span data-stu-id="c6314-197">+1425555$1</span></span></p></td>
<td><p><span data-ttu-id="c6314-198">将 50100 转换为 +14255550100</span><span class="sxs-lookup"><span data-stu-id="c6314-198">50100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6314-199">7digitcallingRedmond</span><span class="sxs-lookup"><span data-stu-id="c6314-199">7digitcallingRedmond</span></span></p></td>
<td><p><span data-ttu-id="c6314-200">将 7 位号码转换为雷德蒙德本地号码</span><span class="sxs-lookup"><span data-stu-id="c6314-200">Translates 7-digit numbers to Redmond local numbers</span></span></p></td>
<td><p><span data-ttu-id="c6314-201">^ （\d{7}） $</span><span class="sxs-lookup"><span data-stu-id="c6314-201">^(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="c6314-202">+ 1425 $ 1</span><span class="sxs-lookup"><span data-stu-id="c6314-202">+1425$1</span></span></p></td>
<td><p><span data-ttu-id="c6314-203">将 5550100 转换为 +14255550100</span><span class="sxs-lookup"><span data-stu-id="c6314-203">5550100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6314-204">7digitcallingDallas</span><span class="sxs-lookup"><span data-stu-id="c6314-204">7digitcallingDallas</span></span></p></td>
<td><p><span data-ttu-id="c6314-205">将 7 位号码转换为达拉斯本地号码</span><span class="sxs-lookup"><span data-stu-id="c6314-205">Translates 7-digit numbers to Dallas local numbers</span></span></p></td>
<td><p><span data-ttu-id="c6314-206">^ （\d{7}） $</span><span class="sxs-lookup"><span data-stu-id="c6314-206">^(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="c6314-207">+ 1972 $ 1</span><span class="sxs-lookup"><span data-stu-id="c6314-207">+1972$1</span></span></p></td>
<td><p><span data-ttu-id="c6314-208">将 5550100 转换为 +19725550100</span><span class="sxs-lookup"><span data-stu-id="c6314-208">5550100 is translated to +19725550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6314-209">10digitcallingUS</span><span class="sxs-lookup"><span data-stu-id="c6314-209">10digitcallingUS</span></span></p></td>
<td><p><span data-ttu-id="c6314-210">转换美国的 10 位号码</span><span class="sxs-lookup"><span data-stu-id="c6314-210">Translates 10-digit numbers in the United States</span></span></p></td>
<td><p><span data-ttu-id="c6314-211">^ （\d{10}） $</span><span class="sxs-lookup"><span data-stu-id="c6314-211">^(\d{10})$</span></span></p></td>
<td><p><span data-ttu-id="c6314-212">+ 1 $ 1</span><span class="sxs-lookup"><span data-stu-id="c6314-212">+1$1</span></span></p></td>
<td><p><span data-ttu-id="c6314-213">将 2065550100 转换为 +12065550100</span><span class="sxs-lookup"><span data-stu-id="c6314-213">2065550100 is translated to +12065550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6314-214">LDCallingUS</span><span class="sxs-lookup"><span data-stu-id="c6314-214">LDCallingUS</span></span></p></td>
<td><p><span data-ttu-id="c6314-215">用美国的长途前缀转换号码</span><span class="sxs-lookup"><span data-stu-id="c6314-215">Translates numbers with long distance prefixes in the United States</span></span></p></td>
<td><p><span data-ttu-id="c6314-216">^ 1 （\d{10}） $</span><span class="sxs-lookup"><span data-stu-id="c6314-216">^1(\d{10})$</span></span></p></td>
<td><p><span data-ttu-id="c6314-217">+ $1</span><span class="sxs-lookup"><span data-stu-id="c6314-217">+$1</span></span></p></td>
<td><p><span data-ttu-id="c6314-218">将 12145550100 转换为 +2145550100</span><span class="sxs-lookup"><span data-stu-id="c6314-218">12145550100 is translated to +2145550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6314-219">IntlCallingUS</span><span class="sxs-lookup"><span data-stu-id="c6314-219">IntlCallingUS</span></span></p></td>
<td><p><span data-ttu-id="c6314-220">用美国的国际前缀转换号码</span><span class="sxs-lookup"><span data-stu-id="c6314-220">Translates numbers with international prefixes in the United States</span></span></p></td>
<td><p><span data-ttu-id="c6314-221">^ 011 （\d \*） $</span><span class="sxs-lookup"><span data-stu-id="c6314-221">^011(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="c6314-222">+ $1</span><span class="sxs-lookup"><span data-stu-id="c6314-222">+$1</span></span></p></td>
<td><p><span data-ttu-id="c6314-223">将 01191445550100 转换为 +91445550100</span><span class="sxs-lookup"><span data-stu-id="c6314-223">01191445550100 is translated to +91445550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6314-224">RedmondOperator</span><span class="sxs-lookup"><span data-stu-id="c6314-224">RedmondOperator</span></span></p></td>
<td><p><span data-ttu-id="c6314-225">将 0 转换为雷德蒙德号码</span><span class="sxs-lookup"><span data-stu-id="c6314-225">Translates 0 to Redmond Operator</span></span></p></td>
<td><p><span data-ttu-id="c6314-226">^ $0</span><span class="sxs-lookup"><span data-stu-id="c6314-226">^0$</span></span></p></td>
<td><p><span data-ttu-id="c6314-227">+ 14255550100</span><span class="sxs-lookup"><span data-stu-id="c6314-227">+14255550100</span></span></p></td>
<td><p><span data-ttu-id="c6314-228">将 0 转换为 +14255550100</span><span class="sxs-lookup"><span data-stu-id="c6314-228">0 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6314-229">RedmondSitePrefix</span><span class="sxs-lookup"><span data-stu-id="c6314-229">RedmondSitePrefix</span></span></p></td>
<td><p><span data-ttu-id="c6314-230">用网内前缀 (6) 和雷德蒙德站点代码 (222) 转换号码</span><span class="sxs-lookup"><span data-stu-id="c6314-230">Translates numbers with on-net prefix (6) and Redmond site code (222)</span></span></p></td>
<td><p><span data-ttu-id="c6314-231">^ 6222 （\d{4}） $</span><span class="sxs-lookup"><span data-stu-id="c6314-231">^6222(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="c6314-232">+ 1425555 $ 1</span><span class="sxs-lookup"><span data-stu-id="c6314-232">+1425555$1</span></span></p></td>
<td><p><span data-ttu-id="c6314-233">将 62220100 转换为 +14255550100</span><span class="sxs-lookup"><span data-stu-id="c6314-233">62220100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6314-234">NYSitePrefix</span><span class="sxs-lookup"><span data-stu-id="c6314-234">NYSitePrefix</span></span></p></td>
<td><p><span data-ttu-id="c6314-235">用网内前缀 (6) 和纽约站点代码 (333) 转换号码</span><span class="sxs-lookup"><span data-stu-id="c6314-235">Translates numbers with on-net prefix (6) and NY site code (333)</span></span></p></td>
<td><p><span data-ttu-id="c6314-236">^ 6333 （\d{4}） $</span><span class="sxs-lookup"><span data-stu-id="c6314-236">^6333(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="c6314-237">+ 1202555 $ 1</span><span class="sxs-lookup"><span data-stu-id="c6314-237">+1202555$1</span></span></p></td>
<td><p><span data-ttu-id="c6314-238">将 63330100 转换为 +12025550100</span><span class="sxs-lookup"><span data-stu-id="c6314-238">63330100 is translated to +12025550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6314-239">DallasSitePrefix</span><span class="sxs-lookup"><span data-stu-id="c6314-239">DallasSitePrefix</span></span></p></td>
<td><p><span data-ttu-id="c6314-240">用网内前缀 (6) 和达拉斯站点代码 (444) 转换号码</span><span class="sxs-lookup"><span data-stu-id="c6314-240">Translates numbers with on-net prefix (6) and Dallas site code (444)</span></span></p></td>
<td><p><span data-ttu-id="c6314-241">^ 6444 （\d{4}） $</span><span class="sxs-lookup"><span data-stu-id="c6314-241">^6444(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="c6314-242">+ 1972555 $ 1</span><span class="sxs-lookup"><span data-stu-id="c6314-242">+1972555$1</span></span></p></td>
<td><p><span data-ttu-id="c6314-243">将 64440100 转换为 +19725550100</span><span class="sxs-lookup"><span data-stu-id="c6314-243">64440100 is translated to +19725550100</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c6314-244">下表基于上表中显示的规范化规则，说明了美国华盛顿雷德蒙德的示例拨号计划。</span><span class="sxs-lookup"><span data-stu-id="c6314-244">The following table illustrates a sample dial plan for Redmond, Washington, United States, based on the normalization rules shown in the previous table.</span></span>

### <a name="table-2-redmond-dial-plan-based-on-normalization-rules-shown-in-table-1"></a><span data-ttu-id="c6314-p117">表 2. 基于表 1 中所示规范化规则的雷德蒙德拨号计划</span><span class="sxs-lookup"><span data-stu-id="c6314-p117">Table 2. Redmond Dial Plan Based on Normalization Rules Shown in Table 1</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c6314-247">Redmond forestFQDN</span><span class="sxs-lookup"><span data-stu-id="c6314-247">Redmond.forestFQDN</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c6314-248">5digitExtension</span><span class="sxs-lookup"><span data-stu-id="c6314-248">5digitExtension</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6314-249">7digitcallingRedmond</span><span class="sxs-lookup"><span data-stu-id="c6314-249">7digitcallingRedmond</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6314-250">10digitcallingUS</span><span class="sxs-lookup"><span data-stu-id="c6314-250">10digitcallingUS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6314-251">IntlCallingUS</span><span class="sxs-lookup"><span data-stu-id="c6314-251">IntlCallingUS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6314-252">RedmondSitePrefix</span><span class="sxs-lookup"><span data-stu-id="c6314-252">RedmondSitePrefix</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6314-253">NYSitePrefix</span><span class="sxs-lookup"><span data-stu-id="c6314-253">NYSitePrefix</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6314-254">DallasSitePrefix</span><span class="sxs-lookup"><span data-stu-id="c6314-254">DallasSitePrefix</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6314-255">RedmondOperator</span><span class="sxs-lookup"><span data-stu-id="c6314-255">RedmondOperator</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="c6314-p118">上表中显示的规范化规则名称不包括空格，但是您可以选择包括空格。例如，表中的第一个名称可以写作“5 digit extension”或“5-digit Extension”，这些名称仍然有效。</span><span class="sxs-lookup"><span data-stu-id="c6314-p118">The normalization rules names shown in the preceding table do not include spaces, but this is a matter of choice. The first name in the table, for example, could have been written "5 digit extension" or "5-digit Extension" and still be valid.</span></span>



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

