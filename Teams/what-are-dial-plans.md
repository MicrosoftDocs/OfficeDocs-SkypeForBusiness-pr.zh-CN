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
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.voice.dialplans.overview
- Calling Plans
description: '了解 PSTN 呼叫 (套餐) 哪些类型的Teams以及如何为组织选择一个。  '
ms.openlocfilehash: 010065c32135d893b15bcc692e84a1b59269650d
ms.sourcegitcommit: 127f9fdf05b93ee3af4244224e1c32a45d73d3ee
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/21/2021
ms.locfileid: "53046219"
---
# <a name="what-are-dial-plans"></a><span data-ttu-id="c78c9-103">什么是拨号计划？</span><span class="sxs-lookup"><span data-stu-id="c78c9-103">What are dial plans?</span></span>

<span data-ttu-id="c78c9-104">拨号计划是一组指定的规范化规则，可将单个用户拨打的电话号码转换为替代格式（通常为 E.164），以用于呼叫授权和呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="c78c9-104">A dial plan is a named set of normalization rules that translate dialed phone numbers by an individual user into an alternate format (typically E.164) for purposes of call authorization and call routing.</span></span>

<span data-ttu-id="c78c9-105">拨号计划由一个或多个规范化规则组成，这些规则定义如何将以各种格式表示的电话号码转换为备用格式。</span><span class="sxs-lookup"><span data-stu-id="c78c9-105">A dial plan consists of one or more normalization rules that define how phone numbers expressed in various formats are translated to an alternate format.</span></span> <span data-ttu-id="c78c9-106">同一拨号字符串在不同拨号计划中可能以不同方式解释和转换，因此，根据为给定用户分配的拨号计划，同一个拨号号码可能以不同方式转换和路由。</span><span class="sxs-lookup"><span data-stu-id="c78c9-106">The same dial string may be interpreted and translated differently in different dial plans, so depending on which dial plan is assigned to a given user, the same dialed number may be translated and routed differently.</span></span> <span data-ttu-id="c78c9-107">最多可以有 1，000 个租户拨号计划。</span><span class="sxs-lookup"><span data-stu-id="c78c9-107">There can be a maximum of 1,000 tenant dial plans.</span></span>

<span data-ttu-id="c78c9-108">请参阅 [创建和管理拨号计划以](create-and-manage-dial-plans.md) 创建和管理租户拨号计划。</span><span class="sxs-lookup"><span data-stu-id="c78c9-108">See [Create and manage dial plans](create-and-manage-dial-plans.md) to create and manage tenant dial plans.</span></span>

## <a name="tenant-dial-plan-scope"></a><span data-ttu-id="c78c9-109">租户拨号计划范围</span><span class="sxs-lookup"><span data-stu-id="c78c9-109">Tenant dial plan scope</span></span>

<span data-ttu-id="c78c9-110">拨号计划范围确定可以应用拨号计划的层次结构级别。</span><span class="sxs-lookup"><span data-stu-id="c78c9-110">A dial plan's scope determines the hierarchical level at which the dial plan can be applied.</span></span> <span data-ttu-id="c78c9-111">客户端通过预配设置获取相应的拨号计划，这些设置在用户登录到 Teams 时自动提供。</span><span class="sxs-lookup"><span data-stu-id="c78c9-111">Clients get the appropriate dial plan through provisioning settings that are automatically provided when users sign in to Teams.</span></span> <span data-ttu-id="c78c9-112">作为管理员，可以使用远程管理中心或远程 PowerShell Microsoft Teams和分配拨号计划范围级别。</span><span class="sxs-lookup"><span data-stu-id="c78c9-112">As an admin, you can manage and assign dial plan scope levels by using the Microsoft Teams admin center or Remote PowerShell.</span></span>

<span data-ttu-id="c78c9-113">在Teams中，有两种类型的拨号计划：服务范围和租户范围 (适用于组织的) 。</span><span class="sxs-lookup"><span data-stu-id="c78c9-113">In Teams, there are two types of dial plans: service-scoped and tenant-scoped (which is for your organization).</span></span> <span data-ttu-id="c78c9-114">服务范围的拨号计划为可用的每个电话系统定义。</span><span class="sxs-lookup"><span data-stu-id="c78c9-114">A service-scoped dial plan is defined for every country or region where Phone System is available.</span></span> <span data-ttu-id="c78c9-115">系统会自动为每个用户分配与分配给用户的使用位置匹配的服务国家/地区拨号计划。</span><span class="sxs-lookup"><span data-stu-id="c78c9-115">Each user is automatically assigned the service country dial plan that matches the usage location assigned to the user.</span></span> <span data-ttu-id="c78c9-116">你无法更改服务国家/地区拨号计划，但可以创建租户范围的拨号计划，用于增强服务国家/地区拨号计划。</span><span class="sxs-lookup"><span data-stu-id="c78c9-116">You can't change the service country dial plan, but you can create tenant scoped dial plans, which augment the service country dial plan.</span></span> <span data-ttu-id="c78c9-117">在预配客户端时，他们获得"有效拨号计划"，这是服务国家/地区拨号计划和适当范围的租户拨号计划的组合。</span><span class="sxs-lookup"><span data-stu-id="c78c9-117">As clients are provisioned, they obtain an "effective dial plan," which is a combination of the service country dial plan and the appropriately scoped tenant dial plan.</span></span> <span data-ttu-id="c78c9-118">因此，在租户拨号计划中不必定义所有规范化规则，因为这些规则已经存在于服务国家/地区拨号计划中。</span><span class="sxs-lookup"><span data-stu-id="c78c9-118">Therefore, it's not necessary to define all normalization rules in tenant dial plans as they might already exist in the service country dial plan.</span></span>

<span data-ttu-id="c78c9-119">租户拨号计划可以进一步细分为两个范围 - 租户范围或用户范围。</span><span class="sxs-lookup"><span data-stu-id="c78c9-119">Tenant dial plans can be further broken into two scopes - tenant-scope or user-scope.</span></span> <span data-ttu-id="c78c9-120">如果租户定义并分配用户范围的拨号计划，将为该用户预配用户的服务国家/地区拨号计划和分配的用户拨号计划的有效拨号计划。</span><span class="sxs-lookup"><span data-stu-id="c78c9-120">If a tenant defines and assigns a user-scoped dial plan, that user will be provisioned with an effective dial plan of the user's service country dial plan and the assigned user dial plan.</span></span> <span data-ttu-id="c78c9-121">如果租户定义了租户范围的拨号计划，但没有分配用户范围的拨号计划，则将为该用户预配用户的服务国家/地区拨号计划和租户拨号计划的有效拨号计划。</span><span class="sxs-lookup"><span data-stu-id="c78c9-121">If a tenant defines a tenant-scoped dial plan but doesn't assign a user-scoped dial plan, then that user will be provisioned with an effective dial plan of the user's service country dial plan and the tenant dial plan.</span></span>

<span data-ttu-id="c78c9-122">下面是拨号计划中拨号计划的继承Teams。</span><span class="sxs-lookup"><span data-stu-id="c78c9-122">The following is the inheritance model of dial plans in Teams.</span></span>

![拨号计划的继承Teams](media/b2744f33-ebbd-4c23-bfba-1747312ab178.png)

<span data-ttu-id="c78c9-124">下面是可能的有效拨号计划：</span><span class="sxs-lookup"><span data-stu-id="c78c9-124">The following are the possible effective dial plans:</span></span>

 <span data-ttu-id="c78c9-125">**服务国家/地区** 如果未定义租户范围的拨号计划，并且未向预配的用户分配租户用户范围的拨号计划，则用户将收到映射到与其使用位置关联的服务国家/地区的有效拨号计划。</span><span class="sxs-lookup"><span data-stu-id="c78c9-125">**Service Country** If no tenant scoped dial plan is defined and no tenant user scoped dial plan is assigned to the provisioned user, the user will receive an effective dial plan mapped to the service country associated with their usage location.</span></span>

 <span data-ttu-id="c78c9-126">**租户全局 - 服务国家/地区** 如果定义了租户用户拨号计划，但没有分配给用户，则预配的用户将收到一个有效的拨号计划，其中包括合并的租户拨号计划以及与其使用位置关联的服务国家/地区拨号计划。</span><span class="sxs-lookup"><span data-stu-id="c78c9-126">**Tenant Global - Service Country** If a tenant user dial plan is defined but not assigned to a user, the provisioned user will receive an effective dial plan consisting of a merged tenant dial plan and the service country dial plan associated with their usage location.</span></span>

 <span data-ttu-id="c78c9-127">**租户用户 - 服务国家/地区** 如果定义了租户用户拨号计划并将其分配给用户，则预配的用户将收到一个有效的拨号计划，其中包括合并的租户用户拨号计划以及与其使用位置关联的服务国家/地区拨号计划。</span><span class="sxs-lookup"><span data-stu-id="c78c9-127">**Tenant User - Service Country** If a tenant user dial plan is defined and assigned to a user, the provisioned user will receive an effective dial plan consisting of the merged tenant user dial plan and the service country dial plan associated with their usage location.</span></span>

<span data-ttu-id="c78c9-128">请参阅 [创建和管理拨号计划](create-and-manage-dial-plans.md) 以创建租户拨号计划。</span><span class="sxs-lookup"><span data-stu-id="c78c9-128">See [Create and manage dial plans](create-and-manage-dial-plans.md) to create your tenant dial plans.</span></span>

> [!NOTE]
> <span data-ttu-id="c78c9-129">在未将拨号计划规范化规则应用于拨号号码的情况下，拨号字符串仍规范化为在"+抄送"前，其中 CC 是拨号用户的使用位置的国家/地区代码。</span><span class="sxs-lookup"><span data-stu-id="c78c9-129">In the scenario where no dial plan normalization rules apply to a dialed number, the dialed string is still normalized to prepend "+CC" where CC is the country code of the dialing user's usage location.</span></span> <span data-ttu-id="c78c9-130">这适用于呼叫计划、直接路由和 PSTN 会议拨出方案。</span><span class="sxs-lookup"><span data-stu-id="c78c9-130">This applies to Calling Plans, Direct Routing and PSTN Conference dial-out scenarios.</span></span> <span data-ttu-id="c78c9-131">此外，如果租户拨号计划规范化规则导致号码不是以"+"开始，则呼叫服务将尝试根据租户拨号计划规范化从 Teams 客户端收到的号码，如果不匹配，则针对区域拨号计划。</span><span class="sxs-lookup"><span data-stu-id="c78c9-131">Additionally, if a tenant dial plan normalization rule results in a number that does not start with "+", the calling service will attempt to normalize the number received from the Teams client based on the tenant dial plan, and if not matched, on the region dial plan.</span></span> <span data-ttu-id="c78c9-132">为了避免双重规范化，建议直接路由客户规范化数字以包含 +，然后使用中继翻译规则删除 +。</span><span class="sxs-lookup"><span data-stu-id="c78c9-132">To avoid double normalization, it's recommended that Direct Routing customers normalize numbers to include a + and then remove the + using Trunk Translation rules.</span></span> 

## <a name="planning-for-tenant-dial-plans"></a><span data-ttu-id="c78c9-133">规划租户拨号计划</span><span class="sxs-lookup"><span data-stu-id="c78c9-133">Planning for tenant dial plans</span></span>

<span data-ttu-id="c78c9-134">要规划自定义拨号计划，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="c78c9-134">To plan custom dial plans, follow these steps:</span></span>

- <span data-ttu-id="c78c9-135">**步骤 1** 确定是否需要自定义拨号计划来增强用户拨号体验。</span><span class="sxs-lookup"><span data-stu-id="c78c9-135">**Step 1** Decide whether a custom dial plan is needed to enhance the user dialing experience.</span></span> <span data-ttu-id="c78c9-136">通常，需要支持非 E.164 拨号，例如分机号码或缩写国家/直拨。</span><span class="sxs-lookup"><span data-stu-id="c78c9-136">Typically, the need for one would be to support non-E.164 dialing, such as extensions or abbreviated national dialing.</span></span>

- <span data-ttu-id="c78c9-137">**步骤 2** 确定是否需要租户全局拨号计划或租户用户范围拨号计划，或同时需要这两者。</span><span class="sxs-lookup"><span data-stu-id="c78c9-137">**Step 2** Determine whether tenant global or tenant user scoped dial plans are needed, or both.</span></span> <span data-ttu-id="c78c9-138">如果用户具有不同的本地拨号需求，则需使用用户范围的拨号计划。</span><span class="sxs-lookup"><span data-stu-id="c78c9-138">User scoped dial plans are needed if users have different local dialing requirements.</span></span>

- <span data-ttu-id="c78c9-p108">**第 3 步** 为需要的每个拨号计划确定有效的号码模式。只需要服务级别的国家/地区拨号计划中未定义的号码模式。</span><span class="sxs-lookup"><span data-stu-id="c78c9-p108">**Step 3** Identify valid number patterns for each required dial plan. Only the number patterns that are not defined in the service level country dial plans are required.</span></span>

- <span data-ttu-id="c78c9-p109">**第 4 步** 制定用于命名拨号计划的组织范围的方案。采用标准命名方案可确保在组织范围内的一致性，还便于维护和更新。</span><span class="sxs-lookup"><span data-stu-id="c78c9-p109">**Step 4** Develop an organization-wide scheme for naming dial plans. Adopting a standard naming scheme assures consistency across an organization and makes maintenance and updates easier.</span></span>


## <a name="creating-your-new-dial-plan"></a><span data-ttu-id="c78c9-143">创建新的拨号计划</span><span class="sxs-lookup"><span data-stu-id="c78c9-143">Creating your new dial plan</span></span>

<span data-ttu-id="c78c9-144">在创建新拨号计划时，必须填写必填信息。</span><span class="sxs-lookup"><span data-stu-id="c78c9-144">When you create a new dial plan, you must put in the information that is required.</span></span>

### <a name="name-and-simple-name"></a><span data-ttu-id="c78c9-145">名称和简单名称</span><span class="sxs-lookup"><span data-stu-id="c78c9-145">Name and simple name</span></span>

<span data-ttu-id="c78c9-146">对于用户拨号计划，应指定一个描述性名称，用于标识要为其分配拨号计划的用户。</span><span class="sxs-lookup"><span data-stu-id="c78c9-146">For user dial plans, you should specify a descriptive name that identifies the users to which the dial plan will be assigned.</span></span> <span data-ttu-id="c78c9-147">拨号计划简单名称预填充了派生自拨号计划名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="c78c9-147">The dial plan Simple Name is pre-populated with a string that is derived from the dial plan name.</span></span> <span data-ttu-id="c78c9-148">"简单名称"字段可编辑，这样你便可以为自己的拨号计划创建更具描述性的命名约定。</span><span class="sxs-lookup"><span data-stu-id="c78c9-148">The Simple Name field is editable, which enables you to create a more descriptive naming convention for your dial plans.</span></span> <span data-ttu-id="c78c9-149">"简单名称"值不能为空，且必须唯一。</span><span class="sxs-lookup"><span data-stu-id="c78c9-149">The Simple Name value cannot be empty and must be unique.</span></span> <span data-ttu-id="c78c9-150">最佳实践是为整个组织制定命名约定，然后在所有网站和用户中一致地使用此约定。</span><span class="sxs-lookup"><span data-stu-id="c78c9-150">A best practice is to develop a naming convention for your entire organization and then use this convention consistently across all sites and users.</span></span>

### <a name="description"></a><span data-ttu-id="c78c9-151">描述</span><span class="sxs-lookup"><span data-stu-id="c78c9-151">Description</span></span>

<span data-ttu-id="c78c9-152">建议输入对应的拨号计划要应用到的地理位置或用户组的通用可识别名称。</span><span class="sxs-lookup"><span data-stu-id="c78c9-152">We recommend that you type the common, recognizable name of the geographic location or group of users to which the corresponding dial plan applies.</span></span>

### <a name="external-access-prefix"></a><span data-ttu-id="c78c9-153">外部访问前缀</span><span class="sxs-lookup"><span data-stu-id="c78c9-153">External access prefix</span></span>
<span data-ttu-id="c78c9-154"><a name="bkexternalprefix"> </a></span><span class="sxs-lookup"><span data-stu-id="c78c9-154"><a name="bkexternalprefix"> </a></span></span>

<span data-ttu-id="c78c9-155">如果用户需要拨打一个或多个附加的前导数位（例如，9）来获取外线，则可指定最多包含四个字符（#、\* 和 0-9）的外部访问前缀。</span><span class="sxs-lookup"><span data-stu-id="c78c9-155">You can specify an external access prefix of up to four characters (#, \*, and 0-9) if users need to dial one or more additional leading digits (for example, 9) to get an external line.</span></span>

> [!NOTE]
> <span data-ttu-id="c78c9-156">[!注释] 如果指定外部访问前缀，则不必创建附加的规范化规则来涵盖该前缀。</span><span class="sxs-lookup"><span data-stu-id="c78c9-156">If you specify an external access prefix, you don't need to create an additional normalization rule to accommodate the prefix.</span></span>

<span data-ttu-id="c78c9-157">请参阅 [创建和管理拨号计划](create-and-manage-dial-plans.md) 以创建租户拨号计划。</span><span class="sxs-lookup"><span data-stu-id="c78c9-157">See [Create and manage dial plans](create-and-manage-dial-plans.md) to create your tenant dial plans.</span></span>

## <a name="normalization-rules"></a><span data-ttu-id="c78c9-158">规范化规则</span><span class="sxs-lookup"><span data-stu-id="c78c9-158">Normalization rules</span></span>
<span data-ttu-id="c78c9-159"><a name="bknormalizationrule"> </a></span><span class="sxs-lookup"><span data-stu-id="c78c9-159"><a name="bknormalizationrule"> </a></span></span>

<span data-ttu-id="c78c9-p111">规范化规则定义如何转换以不同格式表示的电话号码。同一号码字符串可能得到不同的解释和转换，具体取决于拨叫该号码所在的区域。如果用户需要拨打缩写的内部或外部号码，则需要制定规范化规则。</span><span class="sxs-lookup"><span data-stu-id="c78c9-p111">Normalization rules define how phone numbers expressed in various formats are to be translated. The same number string may be interpreted and translated differently, depending on the locale from which it is dialed. Normalization rules may be necessary if users need to be able to dial abbreviated internal or external numbers.</span></span>

<span data-ttu-id="c78c9-163">必须为拨号计划分配一条或多条规范化规则。</span><span class="sxs-lookup"><span data-stu-id="c78c9-163">One or more normalization rules must be assigned to the dial plan.</span></span> <span data-ttu-id="c78c9-164">规范化规则从上到下匹配，因此它们在租户拨号计划中的显示顺序非常重要。</span><span class="sxs-lookup"><span data-stu-id="c78c9-164">Normalization rules are matched from top to bottom, so the order in which they appear in a tenant dial plan is important.</span></span> <span data-ttu-id="c78c9-165">例如，如果租户拨号计划有 10 条规范化规则，则会从第一条开始，将拨叫的号码与规范化规则进行逻辑匹配，如果不匹配，则对第二条规则进行匹配，依此类推。</span><span class="sxs-lookup"><span data-stu-id="c78c9-165">For example, if a tenant dial plan has 10 normalization rules, the dialed number matching logic will be tried starting with the first normalization rule, if there isn't a match then the second, and so forth.</span></span> <span data-ttu-id="c78c9-166">如果与某一条规则匹配，则使用该规则，不再继续匹配其他任何定义的规则。</span><span class="sxs-lookup"><span data-stu-id="c78c9-166">If a match is made, that rule is used and there is no effort to match any other rules that are defined.</span></span> <span data-ttu-id="c78c9-167">给定租户拨号计划中最多可以有 50 条规范化规则。</span><span class="sxs-lookup"><span data-stu-id="c78c9-167">There can be a maximum of 50 normalization rules in a given tenant dial plan.</span></span>

### <a name="determining-the-required-normalization-rules"></a><span data-ttu-id="c78c9-168">确定所需的规范化规则</span><span class="sxs-lookup"><span data-stu-id="c78c9-168">Determining the required normalization rules</span></span>

<span data-ttu-id="c78c9-169">由于任何租户拨号计划有效地与给定用户的服务国家/地区拨号计划合并，因此可能需要评估服务国家/地区拨号计划的规范化规则，以确定需要哪个租户拨号计划规范化规则。</span><span class="sxs-lookup"><span data-stu-id="c78c9-169">Because any tenant dial plan is effectively merged with a given user's service country dial plan, it is likely that the service country dial plan's normalization rules need to be evaluated in order to determine which tenant dial plan normalization rules are needed.</span></span> <span data-ttu-id="c78c9-170">**Get-CsEffectiveTenantDialPlan** cmdlet 可用于此用途。</span><span class="sxs-lookup"><span data-stu-id="c78c9-170">The **Get-CsEffectiveTenantDialPlan** cmdlet can be used for this purpose.</span></span> <span data-ttu-id="c78c9-171">该 cmdlet 以用户标识作为输入参数，并将所有适用的规范化规则都返回给用户。</span><span class="sxs-lookup"><span data-stu-id="c78c9-171">The cmdlet takes the user's identity as the input parameter and will return all normalization rules that are applicable to the user.</span></span>

### <a name="creating-normalization-rules"></a><span data-ttu-id="c78c9-172">创建规范化规则</span><span class="sxs-lookup"><span data-stu-id="c78c9-172">Creating normalization rules</span></span>
<span data-ttu-id="c78c9-173"><a name="createrule"> </a></span><span class="sxs-lookup"><span data-stu-id="c78c9-173"><a name="createrule"> </a></span></span>

<span data-ttu-id="c78c9-174">规范化规则.NET Framework正则表达式来指定服务器用来将拨号字符串转换为 E.164 格式的数字匹配模式。</span><span class="sxs-lookup"><span data-stu-id="c78c9-174">Normalization rules use .NET Framework regular expressions to specify numeric match patterns that the server uses to translate dial strings to E.164 format.</span></span> <span data-ttu-id="c78c9-175">可以通过指定在找到匹配项时要执行的匹配和转换的正则表达式来创建规范化规则。</span><span class="sxs-lookup"><span data-stu-id="c78c9-175">Normalization rules can be created by specifying the regular expression for the match and the translation to be done when a match is found.</span></span> <span data-ttu-id="c78c9-176">完成之后，你可以输入一个测试号码以验证规范化规则是否可按预期工作。</span><span class="sxs-lookup"><span data-stu-id="c78c9-176">When you finish, you can enter a test number to verify that the normalization rule works as expected.</span></span>

<span data-ttu-id="c78c9-177">有关使用正则表达式.NET Framework，请参阅.NET Framework[正则表达式"。](/dotnet/standard/base-types/regular-expressions)</span><span class="sxs-lookup"><span data-stu-id="c78c9-177">For details about using .NET Framework regular expressions, see [.NET Framework Regular Expressions](/dotnet/standard/base-types/regular-expressions).</span></span>

<span data-ttu-id="c78c9-178">请参阅 [创建和管理拨号计划](create-and-manage-dial-plans.md) ，以创建和管理租户拨号计划的规范化规则。</span><span class="sxs-lookup"><span data-stu-id="c78c9-178">See [Create and manage dial plans](create-and-manage-dial-plans.md) to create and manage normalization rules for your tenant dial plans.</span></span>

> [!NOTE]
> <span data-ttu-id="c78c9-179">3pip 设备目前不支持将第一个令牌作为可选标记的规范化规则 (例如 Polycom VVX 601 模型) 。</span><span class="sxs-lookup"><span data-stu-id="c78c9-179">Normalization rules with the first token as optional are currently not supported on 3pip devices (for example, Polycom VVX 601 model).</span></span> <span data-ttu-id="c78c9-180">如果要在 3pip 设备上应用具有可选属性的规范化规则，应创建两个规范化规则而不是一个规范化规则。</span><span class="sxs-lookup"><span data-stu-id="c78c9-180">If you want to apply normalization rules with optionality on 3pip devices, you should create two normalization rules instead of one.</span></span> <span data-ttu-id="c78c9-181">例如，规则 ^0？ (999) $ 应替换为以下两个规则： (999) $ (Translation：$1) 和 ^0 (999) $ (Translation：$1) 。</span><span class="sxs-lookup"><span data-stu-id="c78c9-181">For example, the rule ^0?(999)$ should be replaced by the following two rules: (999)$ (Translation:$1) and ^0(999)$ (Translation:$1).</span></span>


### <a name="sample-normalization-rules"></a><span data-ttu-id="c78c9-182">示例规范化规则</span><span class="sxs-lookup"><span data-stu-id="c78c9-182">Sample normalization rules</span></span>

<span data-ttu-id="c78c9-p116">下表显示以 .NET Framework 正则表达式形式编写的示例规范化规则。这些示例仅用作示例，不用作创建规范化规则的规范性参考。</span><span class="sxs-lookup"><span data-stu-id="c78c9-p116">The following table shows sample normalization rules that are written as .NET Framework regular expressions. The samples are examples only and are not meant to be a prescriptive reference for creating your own normalization rules.</span></span>

<span data-ttu-id="c78c9-185"><a name="regularexpression"></a> 
 **使用正则表达式.NET Framework规范化规则**</span><span class="sxs-lookup"><span data-stu-id="c78c9-185"><a name="regularexpression"> </a>
**Normalization rules using .NET Framework regular expressions**</span></span>

| <span data-ttu-id="c78c9-186">规则名称</span><span class="sxs-lookup"><span data-stu-id="c78c9-186">Rule name</span></span><br/> | <span data-ttu-id="c78c9-187">描述</span><span class="sxs-lookup"><span data-stu-id="c78c9-187">Description</span></span><br/> | <span data-ttu-id="c78c9-188">号码模式</span><span class="sxs-lookup"><span data-stu-id="c78c9-188">Number pattern</span></span><br/> | <span data-ttu-id="c78c9-189">转换</span><span class="sxs-lookup"><span data-stu-id="c78c9-189">Translation</span></span><br/> | <span data-ttu-id="c78c9-190">示例</span><span class="sxs-lookup"><span data-stu-id="c78c9-190">Example</span></span><br/> |
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c78c9-191">4digitExtension</span><span class="sxs-lookup"><span data-stu-id="c78c9-191">4digitExtension</span></span>  <br/> |<span data-ttu-id="c78c9-192">转换 4 位数分机号。</span><span class="sxs-lookup"><span data-stu-id="c78c9-192">Translates 4-digit extensions.</span></span>  <br/> |<span data-ttu-id="c78c9-193">^(\\d{4})$</span><span class="sxs-lookup"><span data-stu-id="c78c9-193">^(\\d{4})$</span></span>  <br/> |<span data-ttu-id="c78c9-194">+1425555$1</span><span class="sxs-lookup"><span data-stu-id="c78c9-194">+1425555$1</span></span>  <br/> |<span data-ttu-id="c78c9-195">将 0100 转换为 +14255550100</span><span class="sxs-lookup"><span data-stu-id="c78c9-195">0100 is translated to +14255550100</span></span>  <br/> |
|<span data-ttu-id="c78c9-196">5digitExtension</span><span class="sxs-lookup"><span data-stu-id="c78c9-196">5digitExtension</span></span>  <br/> |<span data-ttu-id="c78c9-197">转换 5 位数分机号。</span><span class="sxs-lookup"><span data-stu-id="c78c9-197">Translates 5-digit extensions.</span></span>  <br/> |<span data-ttu-id="c78c9-198">^5(\\d{4})$</span><span class="sxs-lookup"><span data-stu-id="c78c9-198">^5(\\d{4})$</span></span>  <br/> |<span data-ttu-id="c78c9-199">+1425555$1</span><span class="sxs-lookup"><span data-stu-id="c78c9-199">+1425555$1</span></span>  <br/> |<span data-ttu-id="c78c9-200">将 50100 转换为 +14255550100</span><span class="sxs-lookup"><span data-stu-id="c78c9-200">50100 is translated to +14255550100</span></span>  <br/> |
|<span data-ttu-id="c78c9-201">7digitcallingRedmond</span><span class="sxs-lookup"><span data-stu-id="c78c9-201">7digitcallingRedmond</span></span>  <br/> |<span data-ttu-id="c78c9-202">将 7 位数号码转换为雷德蒙德本地号码。</span><span class="sxs-lookup"><span data-stu-id="c78c9-202">Translates 7-digit numbers to Redmond local numbers.</span></span>  <br/> |<span data-ttu-id="c78c9-203">^(\\d{7})$</span><span class="sxs-lookup"><span data-stu-id="c78c9-203">^(\\d{7})$</span></span>  <br/> |<span data-ttu-id="c78c9-204">+1425$1</span><span class="sxs-lookup"><span data-stu-id="c78c9-204">+1425$1</span></span>  <br/> |<span data-ttu-id="c78c9-205">将 5550100 转换为 +14255550100</span><span class="sxs-lookup"><span data-stu-id="c78c9-205">5550100 is translated to +14255550100</span></span>  <br/>|
|<span data-ttu-id="c78c9-206">RedmondOperator</span><span class="sxs-lookup"><span data-stu-id="c78c9-206">RedmondOperator</span></span>  <br/> |<span data-ttu-id="c78c9-207">将 0 转换为雷德蒙德话务员。</span><span class="sxs-lookup"><span data-stu-id="c78c9-207">Translates 0 to Redmond Operator.</span></span>  <br/> |<span data-ttu-id="c78c9-208">^0$</span><span class="sxs-lookup"><span data-stu-id="c78c9-208">^0$</span></span>  <br/> |<span data-ttu-id="c78c9-209">+14255550100</span><span class="sxs-lookup"><span data-stu-id="c78c9-209">+14255550100</span></span>  <br/> |<span data-ttu-id="c78c9-210">将 0 转换为 +14255550100</span><span class="sxs-lookup"><span data-stu-id="c78c9-210">0 is translated to +14255550100</span></span>  <br/> |
|<span data-ttu-id="c78c9-211">RedmondSitePrefix</span><span class="sxs-lookup"><span data-stu-id="c78c9-211">RedmondSitePrefix</span></span>  <br/> |<span data-ttu-id="c78c9-212">转换带有网内前缀 (6) 和雷德蒙德站点代码 (222) 的号码。</span><span class="sxs-lookup"><span data-stu-id="c78c9-212">Translates numbers with on-net prefix (6) and Redmond site code (222).</span></span>  <br/> |<span data-ttu-id="c78c9-213">^6222(\\d{4})$</span><span class="sxs-lookup"><span data-stu-id="c78c9-213">^6222(\\d{4})$</span></span>  <br/> |<span data-ttu-id="c78c9-214">+1425555$1</span><span class="sxs-lookup"><span data-stu-id="c78c9-214">+1425555$1</span></span>  <br/> |<span data-ttu-id="c78c9-215">将 62220100 转换为 +14255550100</span><span class="sxs-lookup"><span data-stu-id="c78c9-215">62220100 is translated to +14255550100</span></span>  <br/> |
|<span data-ttu-id="c78c9-216">5digitRange</span><span class="sxs-lookup"><span data-stu-id="c78c9-216">5digitRange</span></span>  <br/> |<span data-ttu-id="c78c9-217">转换以 3-7（含 3 和 7）之间的数字开头的 5 位数分机号。</span><span class="sxs-lookup"><span data-stu-id="c78c9-217">Translates 5-digit extensions starting with the digit range between 3-7 inclusive.</span></span>  <br/> |<span data-ttu-id="c78c9-218">^([3-7]\\d{4})$</span><span class="sxs-lookup"><span data-stu-id="c78c9-218">^([3-7]\\d{4})$</span></span>  <br/> |<span data-ttu-id="c78c9-219">+142555$1</span><span class="sxs-lookup"><span data-stu-id="c78c9-219">+142555$1</span></span> <br/> |<span data-ttu-id="c78c9-220">将 54567 转换为 +14255554567</span><span class="sxs-lookup"><span data-stu-id="c78c9-220">54567 is translated to +14255554567</span></span>  <br/> |
|<span data-ttu-id="c78c9-221">PrefixAdded</span><span class="sxs-lookup"><span data-stu-id="c78c9-221">PrefixAdded</span></span>  <br/> |<span data-ttu-id="c78c9-222">在对第一位和第三位数字有限制的 9 位数号码前添加国家/地区前缀。</span><span class="sxs-lookup"><span data-stu-id="c78c9-222">Adds a country prefix in front of a 9 digit number with restrictions on the first and third digits.</span></span>  <br/> |<span data-ttu-id="c78c9-223">^([2-9]\\d\\d[2-9]\\d{6})$</span><span class="sxs-lookup"><span data-stu-id="c78c9-223">^([2-9]\\d\\d[2-9]\\d{6})$</span></span>  <br/> |<span data-ttu-id="c78c9-224">1$1</span><span class="sxs-lookup"><span data-stu-id="c78c9-224">1$1</span></span>  <br/> |<span data-ttu-id="c78c9-225">将 4255554567 转换为 14255554567</span><span class="sxs-lookup"><span data-stu-id="c78c9-225">4255554567 is translated to 14255554567</span></span>  <br/> |
|<span data-ttu-id="c78c9-226">NoTranslation</span><span class="sxs-lookup"><span data-stu-id="c78c9-226">NoTranslation</span></span>  <br/> |<span data-ttu-id="c78c9-227">匹配 5 位数，但不转换。</span><span class="sxs-lookup"><span data-stu-id="c78c9-227">Match 5 digits but no translation.</span></span>  <br/> |<span data-ttu-id="c78c9-228">^(\\d{5})$</span><span class="sxs-lookup"><span data-stu-id="c78c9-228">^(\\d{5})$</span></span>  <br/> |<span data-ttu-id="c78c9-229">$1</span><span class="sxs-lookup"><span data-stu-id="c78c9-229">$1</span></span>  <br/> |<span data-ttu-id="c78c9-230">将 34567 转换为 34567</span><span class="sxs-lookup"><span data-stu-id="c78c9-230">34567 is translated to 34567</span></span>  <br/> |

 <span data-ttu-id="c78c9-231">**上面显示了基于规范化规则的雷德蒙德拨号计划。**</span><span class="sxs-lookup"><span data-stu-id="c78c9-231">**Redmond dial plan based on normalization rules shown above.**</span></span>

 <span data-ttu-id="c78c9-232">下表根据上表显示的规范化规则对用于雷德蒙德、华盛顿、美国的示例拨号计划进行说明。</span><span class="sxs-lookup"><span data-stu-id="c78c9-232">The following table illustrates a sample dial plan for Redmond, Washington, United States, based on the normalization rules shown in the previous table.</span></span>

| <span data-ttu-id="c78c9-233">雷德蒙德拨号计划</span><span class="sxs-lookup"><span data-stu-id="c78c9-233">Redmond dial plan</span></span><br/> |
|:-----------------------|                                                                                                                      
| <span data-ttu-id="c78c9-234">5digitExtension</span><span class="sxs-lookup"><span data-stu-id="c78c9-234">5digitExtension</span></span> <br/> |                                                                                                                                    
| <span data-ttu-id="c78c9-235">7digitcallingRedmond</span><span class="sxs-lookup"><span data-stu-id="c78c9-235">7digitcallingRedmond</span></span> <br/> |
| <span data-ttu-id="c78c9-236">RedmondSitePrefix</span><span class="sxs-lookup"><span data-stu-id="c78c9-236">RedmondSitePrefix</span></span> <br/> |
| <span data-ttu-id="c78c9-237">RedmondOperator</span><span class="sxs-lookup"><span data-stu-id="c78c9-237">RedmondOperator</span></span> <br/> |

> [!NOTE]
> <span data-ttu-id="c78c9-238">上表中显示的规范化规则名称不包括空格，但这是一种选择。</span><span class="sxs-lookup"><span data-stu-id="c78c9-238">The normalization rules names shown in the preceding table don't include spaces, but this is a matter of choice.</span></span> <span data-ttu-id="c78c9-239">例如，该表中的第一个名称，本应写成"5 digit extension"或"5-digit Extension"，但它仍然有效。</span><span class="sxs-lookup"><span data-stu-id="c78c9-239">The first name in the table, for example, could have been written "5 digit extension" or "5-digit Extension" and still be valid.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c78c9-240">相关主题</span><span class="sxs-lookup"><span data-stu-id="c78c9-240">Related topics</span></span>

[<span data-ttu-id="c78c9-241">创建并管理拨号计划</span><span class="sxs-lookup"><span data-stu-id="c78c9-241">Create and manage dial plans</span></span>](create-and-manage-dial-plans.md)

[<span data-ttu-id="c78c9-242">用于通话套餐的不同类型的电话号码</span><span class="sxs-lookup"><span data-stu-id="c78c9-242">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="c78c9-243">管理你的组织的电话号码</span><span class="sxs-lookup"><span data-stu-id="c78c9-243">Manage phone numbers for your organization</span></span>](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[<span data-ttu-id="c78c9-244">紧急呼叫条款和条件</span><span class="sxs-lookup"><span data-stu-id="c78c9-244">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)

<span data-ttu-id="c78c9-245">[紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="c78c9-245">[Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
