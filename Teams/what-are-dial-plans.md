---
title: 什么是拨号计划？
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: ms.teamsadmincenter.voice.dialplans.overview
ms.custom:
- Calling Plans
description: '了解团队中提供了何种类型的拨号呼叫计划（PSTN 呼叫拨号计划），以及如何为你的组织选择一个类型的拨号呼叫计划。  '
ms.openlocfilehash: f23dd2797f70b41a4bed8fd3ddc4bf467dd459db
ms.sourcegitcommit: 0dba0ad1f8f00415c6437cadabed0548ce3281b1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2019
ms.locfileid: "39919285"
---
# <a name="what-are-dial-plans"></a><span data-ttu-id="f3f79-103">什么是拨号计划？</span><span class="sxs-lookup"><span data-stu-id="f3f79-103">What are dial plans?</span></span>

<span data-ttu-id="f3f79-104">拨号计划是一组指定的规范化规则，可将单个用户拨打的电话号码转换为替代格式（通常为 E.164），以用于呼叫授权和呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="f3f79-104">A dial plan is a named set of normalization rules that translate dialed phone numbers by an individual user into an alternate format (typically E.164) for purposes of call authorization and call routing.</span></span>

<span data-ttu-id="f3f79-p101">拨号计划包含一个或多个规范化规则，这些规则定义以各种格式表示的电话号码如何转换为备用格式。在不同的拨号计划中，相同的拨号字符串可能以不同的方式进行解释和转换，因此，根据为给定用户分配的拨号计划，相同的拨号号码可能会以不同的方式进行转换和路由。</span><span class="sxs-lookup"><span data-stu-id="f3f79-p101">A dial plan consists of one or more normalization rules that define how phone numbers expressed in various formats are translated to an alternate format. The same dial string may be interpreted and translated differently in different dial plans, so depending on which dial plan is assigned to a given user, the same dialed number may be translated and routed differently.</span></span>

<span data-ttu-id="f3f79-107">请参阅[创建和管理拨号计划](create-and-manage-dial-plans.md)以创建和管理租户拨号计划。</span><span class="sxs-lookup"><span data-stu-id="f3f79-107">See [Create and manage dial plans](create-and-manage-dial-plans.md) to create and manage tenant dial plans.</span></span>

## <a name="tenant-dial-plan-scope"></a><span data-ttu-id="f3f79-108">租户拨号计划范围</span><span class="sxs-lookup"><span data-stu-id="f3f79-108">Tenant dial plan scope</span></span>

<span data-ttu-id="f3f79-p102">拨号计划的作用域确定可应用拨号计划的层次结构级别。客户通过预配设置来获得相应的拨号计划，用户可在用户登录到团队时自动提供这些设置。作为管理员，你可以使用 Microsoft 团队管理中心或远程 PowerShell 管理和分配拨号计划范围级别。</span><span class="sxs-lookup"><span data-stu-id="f3f79-p102">A dial plan's scope determines the hierarchical level at which the dial plan can be applied. Clients get the appropriate dial plan through provisioning settings that are automatically provided when users sign in to Teams. As an admin, you can manage and assign dial plan scope levels by using the Microsoft Teams admin center or Remote PowerShell.</span></span>

<span data-ttu-id="f3f79-112">在团队中，有两种类型的拨号计划：服务范围和租户范围的（适用于您的组织）。</span><span class="sxs-lookup"><span data-stu-id="f3f79-112">In Teams, there are two types of dial plans: service-scoped and tenant-scoped (which is for your organization.</span></span> <span data-ttu-id="f3f79-113">服务范围内的拨号计划是针对电话系统可用的每个国家或地区定义的。</span><span class="sxs-lookup"><span data-stu-id="f3f79-113">A service-scoped dial plan is defined for every country or region where Phone System is available.</span></span> <span data-ttu-id="f3f79-114">系统会自动为每位用户分配与分配给用户的使用位置相匹配的服务国家/地区拨号计划。</span><span class="sxs-lookup"><span data-stu-id="f3f79-114">Each user is automatically assigned the service country dial plan that matches the usage location assigned to the user.</span></span> <span data-ttu-id="f3f79-115">您无法更改服务的国家/地区拨号计划，但您可以创建租户范围内的拨号计划，这将补充该服务的国家/地区拨号计划。</span><span class="sxs-lookup"><span data-stu-id="f3f79-115">You can't change the service country dial plan, but you can create tenant scoped dial plans, which augment the service country dial plan.</span></span> <span data-ttu-id="f3f79-116">在客户端预配时，它们将获得 "有效的拨号计划"，它是服务国家/地区拨号计划和适当范围的租户拨号计划的组合。</span><span class="sxs-lookup"><span data-stu-id="f3f79-116">As clients are provisioned, they obtain an "effective dial plan," which is a combination of the service country dial plan and the appropriately scoped tenant dial plan.</span></span> <span data-ttu-id="f3f79-117">因此，在租户拨号计划中不必定义所有规范化规则，因为这些规则已经存在于服务国家/地区拨号计划中。</span><span class="sxs-lookup"><span data-stu-id="f3f79-117">Therefore, it's not necessary to define all normalization rules in tenant dial plans as they might already exist in the service country dial plan.</span></span>

<span data-ttu-id="f3f79-118">租户拨号计划可以进一步分解为两个范围：租户-范围或用户范围。</span><span class="sxs-lookup"><span data-stu-id="f3f79-118">Tenant dial plans can be further broken into two scopes - tenant-scope or user-scope.</span></span> <span data-ttu-id="f3f79-119">如果租户定义并分配用户范围的拨号计划，则该用户将通过有效拨号计划设置用户的服务国家/地区拨号计划和分配的用户拨号计划。</span><span class="sxs-lookup"><span data-stu-id="f3f79-119">If a tenant defines and assigns a user-scoped dial plan, that user will be provisioned with an effective dial plan of the user's service country dial plan and the assigned user dial plan.</span></span> <span data-ttu-id="f3f79-120">如果租户定义租户范围的拨号计划，但未分配用户范围的拨号计划，则该用户将使用用户的服务国家/地区拨号计划和租户拨号计划的有效拨号计划进行设置。</span><span class="sxs-lookup"><span data-stu-id="f3f79-120">If a tenant defines a tenant-scoped dial plan but doesn't assign a user-scoped dial plan, then that user will be provisioned with an effective dial plan of the user's service country dial plan and the tenant dial plan.</span></span>

<span data-ttu-id="f3f79-121">以下是团队中拨号计划的继承模型。</span><span class="sxs-lookup"><span data-stu-id="f3f79-121">The following is the inheritance model of dial plans in Teams.</span></span>

![如何在团队中继承拨号计划](media/b2744f33-ebbd-4c23-bfba-1747312ab178.png)

<span data-ttu-id="f3f79-123">下面是可能的有效拨号计划：</span><span class="sxs-lookup"><span data-stu-id="f3f79-123">The following are the possible effective dial plans:</span></span>

 <span data-ttu-id="f3f79-124">**服务国家/地区**如果未定义租户范围内的拨号计划，并且未将租户用户范围内的拨号计划分配给预配的用户，则用户将收到一个有效的拨号计划，该计划映射到与其使用位置关联的服务所在的国家/地区。</span><span class="sxs-lookup"><span data-stu-id="f3f79-124">**Service Country** If no tenant scoped dial plan is defined and no tenant user scoped dial plan is assigned to the provisioned user, the user will receive an effective dial plan mapped to the service country associated with their usage location.</span></span>

 <span data-ttu-id="f3f79-125">**租户全球服务国家/地区**如果定义了租户用户拨号计划，但未将其分配给用户，则预配用户将收到一套有效的拨号计划，其中包含合并的租户拨号计划和与其使用位置相关联的服务国家/地区拨号计划。</span><span class="sxs-lookup"><span data-stu-id="f3f79-125">**Tenant Global - Service Country** If a tenant user dial plan is defined but not assigned to a user, the provisioned user will receive an effective dial plan consisting of a merged tenant dial plan and the service country dial plan associated with their usage location.</span></span>

 <span data-ttu-id="f3f79-126">**租户用户服务国家/地区**如果定义了租户用户拨号计划并将其分配给用户，则预配用户将收到一套有效的拨号计划，其中包含合并的租户用户拨号计划和与其使用位置相关联的服务国家/地区拨号计划。</span><span class="sxs-lookup"><span data-stu-id="f3f79-126">**Tenant User - Service Country** If a tenant user dial plan is defined and assigned to a user, the provisioned user will receive an effective dial plan consisting of the merged tenant user dial plan and the service country dial plan associated with their usage location.</span></span>

<span data-ttu-id="f3f79-127">请参阅[创建和管理拨号计划](create-and-manage-dial-plans.md)以创建租户拨号计划。</span><span class="sxs-lookup"><span data-stu-id="f3f79-127">See [Create and manage dial plans](create-and-manage-dial-plans.md) to create your tenant dial plans.</span></span>

## <a name="planning-for-tenant-dial-plans"></a><span data-ttu-id="f3f79-128">规划租户拨号计划</span><span class="sxs-lookup"><span data-stu-id="f3f79-128">Planning for tenant dial plans</span></span>

<span data-ttu-id="f3f79-129">要规划自定义拨号计划，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="f3f79-129">To plan custom dial plans, follow these steps:</span></span>

- <span data-ttu-id="f3f79-130">**步骤 1**确定是否需要自定义拨号计划来增强用户的拨号体验。</span><span class="sxs-lookup"><span data-stu-id="f3f79-130">**Step 1** Decide whether a custom dial plan is needed to enhance the user dialing experience.</span></span> <span data-ttu-id="f3f79-131">通常，只需支持非 E：164拨号，例如分机或缩写的国内拨号。</span><span class="sxs-lookup"><span data-stu-id="f3f79-131">Typically, the need for one would be to support non-E.164 dialing, such as extensions or abbreviated national dialing.</span></span>

- <span data-ttu-id="f3f79-132">**步骤 2**确定是否需要租户全局或租户用户范围的拨号计划。</span><span class="sxs-lookup"><span data-stu-id="f3f79-132">**Step 2** Determine whether tenant global or tenant user scoped dial plans are needed, or both.</span></span> <span data-ttu-id="f3f79-133">如果用户具有不同的本地拨号需求，则需使用用户范围的拨号计划。</span><span class="sxs-lookup"><span data-stu-id="f3f79-133">User scoped dial plans are needed if users have different local dialing requirements.</span></span>

- <span data-ttu-id="f3f79-p107">**第 3 步** 为需要的每个拨号计划确定有效的号码模式。只需要服务级别的国家/地区拨号计划中未定义的号码模式。</span><span class="sxs-lookup"><span data-stu-id="f3f79-p107">**Step 3** Identify valid number patterns for each required dial plan. Only the number patterns that are not defined in the service level country dial plans are required.</span></span>

- <span data-ttu-id="f3f79-p108">**第 4 步** 制定用于命名拨号计划的组织范围的方案。采用标准命名方案可确保在组织范围内的一致性，还便于维护和更新。</span><span class="sxs-lookup"><span data-stu-id="f3f79-p108">**Step 4** Develop an organization-wide scheme for naming dial plans. Adopting a standard naming scheme assures consistency across an organization and makes maintenance and updates easier.</span></span>

<span data-ttu-id="f3f79-138">[FastTrack](https://fasttrack.microsoft.com/microsoft365/capabilities?view=voice)具有可帮助你实施租户拨号计划的其他资源和合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="f3f79-138">The [FastTrack](https://fasttrack.microsoft.com/microsoft365/capabilities?view=voice) has additional resources and partners that can assist you with implementing tenant dial plans.</span></span>

## <a name="creating-your-new-tenant-dial-plan"></a><span data-ttu-id="f3f79-139">创建新租户拨号计划</span><span class="sxs-lookup"><span data-stu-id="f3f79-139">Creating your new tenant dial plan</span></span>

<span data-ttu-id="f3f79-140">在创建新拨号计划时，必须填写必填信息。</span><span class="sxs-lookup"><span data-stu-id="f3f79-140">When you create a new dial plan, you must put in the information that is required.</span></span>

### <a name="name-and-simple-name"></a><span data-ttu-id="f3f79-141">名称和简单名称</span><span class="sxs-lookup"><span data-stu-id="f3f79-141">Name and simple name</span></span>

<span data-ttu-id="f3f79-142">对于用户拨号计划，你应该指定一个描述性名称，用于标识将分配给拨号计划的用户。</span><span class="sxs-lookup"><span data-stu-id="f3f79-142">For user dial plans, you should specify a descriptive name that identifies to the users the dial plan will be assigned.</span></span> <span data-ttu-id="f3f79-143">将使用从拨号计划名称派生的字符串预先填充拨号计划的简单名称。</span><span class="sxs-lookup"><span data-stu-id="f3f79-143">The dial plan Simple Name is pre-populated with a string that is derived from the dial plan name.</span></span> <span data-ttu-id="f3f79-144">"简单名称"字段可编辑，这样你便可以为自己的拨号计划创建更具描述性的命名约定。</span><span class="sxs-lookup"><span data-stu-id="f3f79-144">The Simple Name field is editable, which enables you to create a more descriptive naming convention for your dial plans.</span></span> <span data-ttu-id="f3f79-145">"简单名称"值不能为空，且必须唯一。</span><span class="sxs-lookup"><span data-stu-id="f3f79-145">The Simple Name value cannot be empty and must be unique.</span></span> <span data-ttu-id="f3f79-146">最佳实践是为整个组织制定命名约定，然后在所有网站和用户中一致地使用此约定。</span><span class="sxs-lookup"><span data-stu-id="f3f79-146">A best practice is to develop a naming convention for your entire organization and then use this convention consistently across all sites and users.</span></span>

### <a name="description"></a><span data-ttu-id="f3f79-147">描述</span><span class="sxs-lookup"><span data-stu-id="f3f79-147">Description</span></span>

<span data-ttu-id="f3f79-148">建议输入对应的拨号计划要应用到的地理位置或用户组的通用可识别名称。</span><span class="sxs-lookup"><span data-stu-id="f3f79-148">We recommend that you type the common, recognizable name of the geographic location or group of users to which the corresponding dial plan applies.</span></span>

### <a name="external-access-prefix"></a><span data-ttu-id="f3f79-149">外部访问前缀</span><span class="sxs-lookup"><span data-stu-id="f3f79-149">External access prefix</span></span>
<span data-ttu-id="f3f79-150"><a name="bkexternalprefix"> </a></span><span class="sxs-lookup"><span data-stu-id="f3f79-150"></span></span>

<span data-ttu-id="f3f79-151">如果用户需要拨打一个或多个附加的前导数位（例如，9）来获取外线，则可指定最多包含四个字符（#、\* 和 0-9）的外部访问前缀。</span><span class="sxs-lookup"><span data-stu-id="f3f79-151">You can specify an external access prefix of up to four characters (#, \*, and 0-9) if users need to dial one or more additional leading digits (for example, 9) to get an external line.</span></span>

> [!NOTE]
> <span data-ttu-id="f3f79-152">[!注释] 如果指定外部访问前缀，则不必创建附加的规范化规则来涵盖该前缀。</span><span class="sxs-lookup"><span data-stu-id="f3f79-152">If you specify an external access prefix, you don't need to create an additional normalization rule to accommodate the prefix.</span></span>

<span data-ttu-id="f3f79-153">请参阅[创建和管理拨号计划](create-and-manage-dial-plans.md)以创建租户拨号计划。</span><span class="sxs-lookup"><span data-stu-id="f3f79-153">See [Create and manage dial plans](create-and-manage-dial-plans.md) to create your tenant dial plans.</span></span>

## <a name="normalization-rules"></a><span data-ttu-id="f3f79-154">规范化规则</span><span class="sxs-lookup"><span data-stu-id="f3f79-154">Normalization rules</span></span>
<span data-ttu-id="f3f79-155"><a name="bknormalizationrule"> </a></span><span class="sxs-lookup"><span data-stu-id="f3f79-155"></span></span>

<span data-ttu-id="f3f79-p110">规范化规则定义如何转换以不同格式表示的电话号码。同一号码字符串可能得到不同的解释和转换，具体取决于拨叫该号码所在的区域。如果用户需要拨打缩写的内部或外部号码，则需要制定规范化规则。</span><span class="sxs-lookup"><span data-stu-id="f3f79-p110">Normalization rules define how phone numbers expressed in various formats are to be translated. The same number string may be interpreted and translated differently, depending on the locale from which it is dialed. Normalization rules may be necessary if users need to be able to dial abbreviated internal or external numbers.</span></span>

<span data-ttu-id="f3f79-159">必须为拨号计划分配一条或多条规范化规则。</span><span class="sxs-lookup"><span data-stu-id="f3f79-159">One or more normalization rules must be assigned to the dial plan.</span></span> <span data-ttu-id="f3f79-160">规范化规则从上到下匹配，因此它们在租户拨号计划中的显示顺序非常重要。</span><span class="sxs-lookup"><span data-stu-id="f3f79-160">Normalization rules are matched from top to bottom, so the order in which they appear in a tenant dial plan is important.</span></span> <span data-ttu-id="f3f79-161">例如，如果租户拨号计划有 10 条规范化规则，则会从第一条开始，将拨叫的号码与规范化规则进行逻辑匹配，如果不匹配，则对第二条规则进行匹配，依此类推。</span><span class="sxs-lookup"><span data-stu-id="f3f79-161">For example, if a tenant dial plan has 10 normalization rules, the dialed number matching logic will be tried starting with the first normalization rule, if there isn't a match then the second, and so forth.</span></span> <span data-ttu-id="f3f79-162">如果与某一条规则匹配，则使用该规则，不再继续匹配其他任何定义的规则。</span><span class="sxs-lookup"><span data-stu-id="f3f79-162">If a match is made, that rule is used and there is no effort to match any other rules that are defined.</span></span> <span data-ttu-id="f3f79-163">一个给定的租户拨号计划中最多可以包含 25 条规范化规则。</span><span class="sxs-lookup"><span data-stu-id="f3f79-163">There can be a maximum of 25 normalization rules in a given tenant dial plan.</span></span>

### <a name="determining-the-required-normalization-rules"></a><span data-ttu-id="f3f79-164">确定所需的规范化规则</span><span class="sxs-lookup"><span data-stu-id="f3f79-164">Determining the required normalization rules</span></span>

<span data-ttu-id="f3f79-p112">由于任何租户拨号计划都与给定用户的服务国家/地区拨号计划有效合并，因此可能需要对服务国家/地区拨号计划的规范化规则进行评估，以确定需要哪些租户拨号计划规范化规则。 **Get-CsEffectiveTenantDialPlan** cmdlet 可用于此用途。该 cmdlet 以用户标识作为输入参数，并将所有适用的规范化规则都返回给用户。</span><span class="sxs-lookup"><span data-stu-id="f3f79-p112">Because any tenant dial plan is effectively merged with a given user's service country dial plan it, it is likely that the service country dial plan's normalization rules need to be evaluated in order to determine which tenant dial plan normalization rules are needed. The **Get-CsEffectiveTenantDialPlan** cmdlet can be used for this purpose. The cmdlet takes the user's identity as the input parameter and will return all normalization rules that are applicable to the user.</span></span>

### <a name="creating-normalization-rules"></a><span data-ttu-id="f3f79-168">创建规范化规则</span><span class="sxs-lookup"><span data-stu-id="f3f79-168">Creating normalization rules</span></span>
<span data-ttu-id="f3f79-169"><a name="createrule"> </a> <a name="regularexpression"> </a></span><span class="sxs-lookup"><span data-stu-id="f3f79-169"></span></span>

<span data-ttu-id="f3f79-p113">规范化规则使用 .NET Framework 正则表达式指定服务器为了执行反向号码查找而将拨号字符串转换为 E.164 格式时所用的数字匹配模式。可以通过指定在找到匹配项时要执行的匹配和转换的正则表达式来创建规范化规则。完成之后，你可以输入一个测试号码以验证规范化规则是否可按预期工作。</span><span class="sxs-lookup"><span data-stu-id="f3f79-p113">Normalization rules use .NET Framework regular expressions to specify numeric match patterns that the server uses to translate dial strings to E.164 format for the purpose of performing reverse number lookup. Normalization rules can be created by specifying the regular expression for the match and the translation to be done when a match is found. When you finish, you can enter a test number to verify that the normalization rule works as expected.</span></span>

<span data-ttu-id="f3f79-173">有关使用 .NET Framework 正则表达式的详细信息，请参阅[.Net Framework 正则表达式](https://go.microsoft.com/fwlink/p/?linkId=140927)。</span><span class="sxs-lookup"><span data-stu-id="f3f79-173">For details about using .NET Framework regular expressions, see [.NET Framework Regular Expressions](https://go.microsoft.com/fwlink/p/?linkId=140927).</span></span>

<span data-ttu-id="f3f79-174">请参阅[创建和管理拨号计划](create-and-manage-dial-plans.md)以创建和管理租户拨号计划的规范化规则。</span><span class="sxs-lookup"><span data-stu-id="f3f79-174">See [Create and manage dial plans](create-and-manage-dial-plans.md) to create and manage normalization rules for your tenant dial plans.</span></span>

### <a name="sample-normalization-rules"></a><span data-ttu-id="f3f79-175">示例规范化规则</span><span class="sxs-lookup"><span data-stu-id="f3f79-175">Sample normalization rules</span></span>

<span data-ttu-id="f3f79-p114">下表显示以 .NET Framework 正则表达式形式编写的示例规范化规则。这些示例仅用作示例，不用作创建规范化规则的规范性参考。</span><span class="sxs-lookup"><span data-stu-id="f3f79-p114">The following table shows sample normalization rules that are written as .NET Framework regular expressions. The samples are examples only and are not meant to be a prescriptive reference for creating your own normalization rules.</span></span>

 <span data-ttu-id="f3f79-178">**使用 .NET Framework 正则表达式的规范化规则**<a name="#regularexpression"> </a></span><span class="sxs-lookup"><span data-stu-id="f3f79-178">**Normalization rules using .NET Framework regular expressions**<a name="#regularexpression"> </a></span></span>

||||||
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f3f79-179">**规则名称**</span><span class="sxs-lookup"><span data-stu-id="f3f79-179">**Rule name**</span></span> <br/> |<span data-ttu-id="f3f79-180">**说明**</span><span class="sxs-lookup"><span data-stu-id="f3f79-180">**Description**</span></span> <br/> |<span data-ttu-id="f3f79-181">**号码模式**</span><span class="sxs-lookup"><span data-stu-id="f3f79-181">**Number pattern**</span></span> <br/> |<span data-ttu-id="f3f79-182">**转换**</span><span class="sxs-lookup"><span data-stu-id="f3f79-182">**Translation**</span></span> <br/> |<span data-ttu-id="f3f79-183">**示例**</span><span class="sxs-lookup"><span data-stu-id="f3f79-183">**Example**</span></span> <br/> |
|<span data-ttu-id="f3f79-184">4digitExtension</span><span class="sxs-lookup"><span data-stu-id="f3f79-184">4digitExtension</span></span>  <br/> |<span data-ttu-id="f3f79-185">转换 4 位数分机号。</span><span class="sxs-lookup"><span data-stu-id="f3f79-185">Translates 4-digit extensions.</span></span>  <br/> |<span data-ttu-id="f3f79-186">^(\\d{4})$</span><span class="sxs-lookup"><span data-stu-id="f3f79-186">^(\\d{4})$</span></span>  <br/> |<span data-ttu-id="f3f79-187">+1425555$1</span><span class="sxs-lookup"><span data-stu-id="f3f79-187">+1425555$1</span></span>  <br/> |<span data-ttu-id="f3f79-188">将 0100 转换为 +14255550100</span><span class="sxs-lookup"><span data-stu-id="f3f79-188">0100 is translated to +14255550100</span></span>  <br/> |
|<span data-ttu-id="f3f79-189">5digitExtension</span><span class="sxs-lookup"><span data-stu-id="f3f79-189">5digitExtension</span></span>  <br/> |<span data-ttu-id="f3f79-190">转换 5 位数分机号。</span><span class="sxs-lookup"><span data-stu-id="f3f79-190">Translates 5-digit extensions.</span></span>  <br/> |<span data-ttu-id="f3f79-191">^5(\\d{4})$</span><span class="sxs-lookup"><span data-stu-id="f3f79-191">^5(\\d{4})$</span></span>  <br/> |<span data-ttu-id="f3f79-192">+1425555$1</span><span class="sxs-lookup"><span data-stu-id="f3f79-192">+1425555$1</span></span>  <br/> |<span data-ttu-id="f3f79-193">将 50100 转换为 +14255550100</span><span class="sxs-lookup"><span data-stu-id="f3f79-193">50100 is translated to +14255550100</span></span>  <br/> |
|<span data-ttu-id="f3f79-194">7digitcallingRedmond</span><span class="sxs-lookup"><span data-stu-id="f3f79-194">7digitcallingRedmond</span></span>  <br/> |<span data-ttu-id="f3f79-195">将 7 位数号码转换为雷德蒙德本地号码。</span><span class="sxs-lookup"><span data-stu-id="f3f79-195">Translates 7-digit numbers to Redmond local numbers.</span></span>  <br/> |<span data-ttu-id="f3f79-196">^(\\d{7})$</span><span class="sxs-lookup"><span data-stu-id="f3f79-196">^(\\d{7})$</span></span>  <br/> |<span data-ttu-id="f3f79-197">+1425$1</span><span class="sxs-lookup"><span data-stu-id="f3f79-197">+1425$1</span></span>  <br/> |<span data-ttu-id="f3f79-198">将 5550100 转换为 +14255550100</span><span class="sxs-lookup"><span data-stu-id="f3f79-198">5550100 is translated to +14255550100</span></span>  <br/>|
|<span data-ttu-id="f3f79-199">RedmondOperator</span><span class="sxs-lookup"><span data-stu-id="f3f79-199">RedmondOperator</span></span>  <br/> |<span data-ttu-id="f3f79-200">将 0 转换为雷德蒙德话务员。</span><span class="sxs-lookup"><span data-stu-id="f3f79-200">Translates 0 to Redmond Operator.</span></span>  <br/> |<span data-ttu-id="f3f79-201">^0$</span><span class="sxs-lookup"><span data-stu-id="f3f79-201">^0$</span></span>  <br/> |<span data-ttu-id="f3f79-202">+14255550100</span><span class="sxs-lookup"><span data-stu-id="f3f79-202">+14255550100</span></span>  <br/> |<span data-ttu-id="f3f79-203">将 0 转换为 +14255550100</span><span class="sxs-lookup"><span data-stu-id="f3f79-203">0 is translated to +14255550100</span></span>  <br/> |
|<span data-ttu-id="f3f79-204">RedmondSitePrefix</span><span class="sxs-lookup"><span data-stu-id="f3f79-204">RedmondSitePrefix</span></span>  <br/> |<span data-ttu-id="f3f79-205">转换带有网内前缀 (6) 和雷德蒙德站点代码 (222) 的号码。</span><span class="sxs-lookup"><span data-stu-id="f3f79-205">Translates numbers with on-net prefix (6) and Redmond site code (222).</span></span>  <br/> |<span data-ttu-id="f3f79-206">^6222(\\d{4})$</span><span class="sxs-lookup"><span data-stu-id="f3f79-206">^6222(\\d{4})$</span></span>  <br/> |<span data-ttu-id="f3f79-207">+1425555$1</span><span class="sxs-lookup"><span data-stu-id="f3f79-207">+1425555$1</span></span>  <br/> |<span data-ttu-id="f3f79-208">将 62220100 转换为 +14255550100</span><span class="sxs-lookup"><span data-stu-id="f3f79-208">62220100 is translated to +14255550100</span></span>  <br/> |
|<span data-ttu-id="f3f79-209">5digitRange</span><span class="sxs-lookup"><span data-stu-id="f3f79-209">5digitRange</span></span>  <br/> |<span data-ttu-id="f3f79-210">转换以 3-7（含 3 和 7）之间的数字开头的 5 位数分机号。</span><span class="sxs-lookup"><span data-stu-id="f3f79-210">Translates 5-digit extensions starting with the digit range between 3-7 inclusive.</span></span>  <br/> |<span data-ttu-id="f3f79-211">^([3-7]\\d{4})$</span><span class="sxs-lookup"><span data-stu-id="f3f79-211">^([3-7]\\d{4})$</span></span>  <br/> |<span data-ttu-id="f3f79-212">+ 142555 $ 1</span><span class="sxs-lookup"><span data-stu-id="f3f79-212">+142555$1</span></span> <br/> |<span data-ttu-id="f3f79-213">将 54567 转换为 +14255554567</span><span class="sxs-lookup"><span data-stu-id="f3f79-213">54567 is translated to +14255554567</span></span>  <br/> |
|<span data-ttu-id="f3f79-214">PrefixAdded</span><span class="sxs-lookup"><span data-stu-id="f3f79-214">PrefixAdded</span></span>  <br/> |<span data-ttu-id="f3f79-215">在对第一位和第三位数字有限制的 9 位数号码前添加国家/地区前缀。</span><span class="sxs-lookup"><span data-stu-id="f3f79-215">Adds a country prefix in front of a 9 digit number with restrictions on the first and third digits.</span></span>  <br/> |<span data-ttu-id="f3f79-216">^([2-9]\\d\\d[2-9]\\d{6})$</span><span class="sxs-lookup"><span data-stu-id="f3f79-216">^([2-9]\\d\\d[2-9]\\d{6})$</span></span>  <br/> |<span data-ttu-id="f3f79-217">1$1</span><span class="sxs-lookup"><span data-stu-id="f3f79-217">1$1</span></span>  <br/> |<span data-ttu-id="f3f79-218">将 4255554567 转换为 14255554567</span><span class="sxs-lookup"><span data-stu-id="f3f79-218">4255554567 is translated to 14255554567</span></span>  <br/> |
|<span data-ttu-id="f3f79-219">NoTranslation</span><span class="sxs-lookup"><span data-stu-id="f3f79-219">NoTranslation</span></span>  <br/> |<span data-ttu-id="f3f79-220">匹配 5 位数，但不转换。</span><span class="sxs-lookup"><span data-stu-id="f3f79-220">Match 5 digits but no translation.</span></span>  <br/> |<span data-ttu-id="f3f79-221">^(\\d{5})$</span><span class="sxs-lookup"><span data-stu-id="f3f79-221">^(\\d{5})$</span></span>  <br/> |<span data-ttu-id="f3f79-222">$1</span><span class="sxs-lookup"><span data-stu-id="f3f79-222">$1</span></span>  <br/> |<span data-ttu-id="f3f79-223">将 34567 转换为 34567</span><span class="sxs-lookup"><span data-stu-id="f3f79-223">34567 is translated to 34567</span></span>  <br/> |

 <span data-ttu-id="f3f79-224">**上面显示了基于规范化规则的雷德蒙德拨号计划。**</span><span class="sxs-lookup"><span data-stu-id="f3f79-224">**Redmond dial plan based on normalization rules shown above.**</span></span>

 <span data-ttu-id="f3f79-225">下表根据上表显示的规范化规则对用于雷德蒙德、华盛顿、美国的示例拨号计划进行说明。</span><span class="sxs-lookup"><span data-stu-id="f3f79-225">The following table illustrates a sample dial plan for Redmond, Washington, United States, based on the normalization rules shown in the previous table.</span></span>

| |
|:---------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="f3f79-226">**雷德蒙德拨号计划**</span><span class="sxs-lookup"><span data-stu-id="f3f79-226">**Redmond dial plan**</span></span> <br/>                                                                                                                              |
| <span data-ttu-id="f3f79-227">5digitExtension</span><span class="sxs-lookup"><span data-stu-id="f3f79-227">5digitExtension</span></span> <br/>                                                                                                                                    |
| <span data-ttu-id="f3f79-228">7digitcallingRedmond</span><span class="sxs-lookup"><span data-stu-id="f3f79-228">7digitcallingRedmond</span></span> <br/>                                                                                                                               |
| <span data-ttu-id="f3f79-229">RedmondSitePrefix</span><span class="sxs-lookup"><span data-stu-id="f3f79-229">RedmondSitePrefix</span></span> <br/>                                                                                                                                  |
| <span data-ttu-id="f3f79-230">RedmondOperator</span><span class="sxs-lookup"><span data-stu-id="f3f79-230">RedmondOperator</span></span> <br/>                                                                                                                                    |

> [!NOTE]
> <span data-ttu-id="f3f79-231">上表中所示的规范化规则名称不包含空格，但这是选择的重要内容。</span><span class="sxs-lookup"><span data-stu-id="f3f79-231">The normalization rules names shown in the preceding table don't include spaces, but this is a matter of choice.</span></span> <span data-ttu-id="f3f79-232">例如，该表中的第一个名称，本应写成"5 digit extension"或"5-digit Extension"，但它仍然有效。</span><span class="sxs-lookup"><span data-stu-id="f3f79-232">The first name in the table, for example, could have been written "5 digit extension" or "5-digit Extension" and still be valid.</span></span>

## <a name="related-topics"></a><span data-ttu-id="f3f79-233">相关主题</span><span class="sxs-lookup"><span data-stu-id="f3f79-233">Related topics</span></span>

[<span data-ttu-id="f3f79-234">创建并管理拨号计划</span><span class="sxs-lookup"><span data-stu-id="f3f79-234">Create and manage dial plans</span></span>](create-and-manage-dial-plans.md)

[<span data-ttu-id="f3f79-235">用于通话套餐的不同类型的电话号码</span><span class="sxs-lookup"><span data-stu-id="f3f79-235">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="f3f79-236">管理你的组织的电话号码</span><span class="sxs-lookup"><span data-stu-id="f3f79-236">Manage phone numbers for your organization</span></span>](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[<span data-ttu-id="f3f79-237">紧急呼叫条款和条件</span><span class="sxs-lookup"><span data-stu-id="f3f79-237">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)

<span data-ttu-id="f3f79-238">[紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="f3f79-238">[Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
