---
title: 什么是拨号计划？
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: 2f0cfb59-1ca1-4e31-84ce-09d0b1a7ce1b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: '了解 Office 365 哪种类型的拨号计划 （PSTN 呼叫拨号计划） 的呼叫，以及如何为您的组织选择一种。  '
ms.openlocfilehash: d0a803316326ca4bc4909ad0e15fa4bfc75a3d00
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23889469"
---
# <a name="what-are-dial-plans"></a><span data-ttu-id="5b3aa-103">什么是拨号计划？</span><span class="sxs-lookup"><span data-stu-id="5b3aa-103">What are dial plans?</span></span>

<span data-ttu-id="5b3aa-104">拨号计划是一组指定的规范化规则，可将单个用户拨打的电话号码转换为替代格式（通常为 E.164），以用于呼叫授权和呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="5b3aa-104">A dial plan is a named set of normalization rules that translate dialed phone numbers by an individual user into an alternate format (typically E.164) for purposes of call authorization and call routing.</span></span>
  
<span data-ttu-id="5b3aa-105">拨号计划包括一个或多个规范化规则定义如何以不同格式表示的电话号码转换为备用格式。</span><span class="sxs-lookup"><span data-stu-id="5b3aa-105">A dial plan consists of one or more normalization rules that define how phone numbers expressed in various formats are translated to an alternate format.</span></span> <span data-ttu-id="5b3aa-106">相同的拨号串可能解析和转换不同的拨号计划中的不同，数量相同拨打根据的拨号计划分配给给定用户，因此可能转换和不同路由。</span><span class="sxs-lookup"><span data-stu-id="5b3aa-106">The same dial string may be interpreted and translated differently in different dial plans, so depending on which dial plan is assigned to a given user, the same dialed number may be translated and routed differently.</span></span>
  
<span data-ttu-id="5b3aa-107">请参阅[创建和管理拨号计划](/SkypeForBusiness/what-are-calling-plans-in-office-365/create-and-manage-dial-plans)创建和管理租户拨号计划。</span><span class="sxs-lookup"><span data-stu-id="5b3aa-107">See [Create and manage dial plans](/SkypeForBusiness/what-are-calling-plans-in-office-365/create-and-manage-dial-plans) to create and manage tenant dial plans.</span></span>
  
## <a name="tenant-dial-plan-scope"></a><span data-ttu-id="5b3aa-108">租户拨号计划范围</span><span class="sxs-lookup"><span data-stu-id="5b3aa-108">Tenant dial plan scope</span></span>

<span data-ttu-id="5b3aa-109">拨号计划范围确定可以应用拨号计划的层次结构级别。</span><span class="sxs-lookup"><span data-stu-id="5b3aa-109">A dial plan's scope determines the hierarchical level at which the dial plan can be applied.</span></span> <span data-ttu-id="5b3aa-110">范围是与业务服务器 2015年 Skype 中本地部署的不同。</span><span class="sxs-lookup"><span data-stu-id="5b3aa-110">The scopes are different than in a Skype for Business Server 2015 on-premises deployment.</span></span> <span data-ttu-id="5b3aa-111">客户端可通过用户登录 Skype for Business Online 时自动提供的配置设置获得相应的拨号计划。</span><span class="sxs-lookup"><span data-stu-id="5b3aa-111">Clients obtain the appropriate dial plan through provisioning settings that are automatically provided when users log on to Skype for Business Online.</span></span> <span data-ttu-id="5b3aa-112">作为管理员，你可以使用 Remote PowerShell 管理和分配拨号计划范围级别。</span><span class="sxs-lookup"><span data-stu-id="5b3aa-112">As an administrator, you can manage and assign dial plan scope levels by using Remote PowerShell.</span></span>
  
<span data-ttu-id="5b3aa-113">在业务 online Skype，有两种类型的拨号计划的范围内的服务和租户 （这是您的组织） 范围内。</span><span class="sxs-lookup"><span data-stu-id="5b3aa-113">In Skype for Business Online, there are two types of dial plans - service scoped and tenant (which is for your organization) scoped.</span></span> <span data-ttu-id="5b3aa-114">Office 365 电话系统位于每个国家/地区定义范围内的服务拨号计划。</span><span class="sxs-lookup"><span data-stu-id="5b3aa-114">A service scoped dial plan is defined for every country/region where the Office 365 Phone System is available.</span></span> <span data-ttu-id="5b3aa-115">每个用户自动分配服务的国家/地区拨号计划的与分配给用户的 Office 365 使用率位置匹配。</span><span class="sxs-lookup"><span data-stu-id="5b3aa-115">Each user is automatically assigned the service country dial plan that matches the Office 365 Usage Location assigned to the user.</span></span> <span data-ttu-id="5b3aa-116">不能更改服务的国家/地区拨号计划，但您可以创建租户范围内的拨号计划，扩充服务国家/地区拨号计划。</span><span class="sxs-lookup"><span data-stu-id="5b3aa-116">You can't change the service country dial plan, but you can create tenant scoped dial plans, which augment the service country dial plan.</span></span> <span data-ttu-id="5b3aa-117">设置客户端，如获得"有效拨号计划"，即服务国家/地区拨号计划和相应范围的租户拨号计划的组合。</span><span class="sxs-lookup"><span data-stu-id="5b3aa-117">As clients are provisioned, they obtain an "effective dial plan," which is a combination of the service country dial plan and the appropriately scoped tenant dial plan.</span></span> <span data-ttu-id="5b3aa-118">因此，在租户拨号计划中不必定义所有规范化规则，因为这些规则已经存在于服务国家/地区拨号计划中。</span><span class="sxs-lookup"><span data-stu-id="5b3aa-118">Therefore, it's not necessary to define all normalization rules in tenant dial plans as they might already exist in the service country dial plan.</span></span>
  
<span data-ttu-id="5b3aa-p104">租户拨号计划可进一步划分为两种范围 - 租户范围或用户范围。如果租户定义并分配了用户范围的拨号计划，那么会为该用户配置由用户的服务国家/地区拨号计划和已分配的用户拨号计划构成的有效拨号计划。如果租户定义租户范围拨号计划但没有分配用户范围的拨号计划，那么会为该用户配置由用户的服务国家/地区拨号计划和租户拨号计划构成的有效拨号计划。</span><span class="sxs-lookup"><span data-stu-id="5b3aa-p104">Tenant dial plans can be further broken into two scopes - tenant scope or user scope. If a tenant defines and assigns a user scoped dial plan, then that user will be provisioned with an effective dial plan of the user's service country dial plan and the assigned user dial plan. If a tenant defines a tenant scoped dial plan but doesn't assign a user scoped dial plan, then that user will be provisioned with an effective dial plan of the user's service country dial plan and the tenant dial plan.</span></span>
  
<span data-ttu-id="5b3aa-122">下面是 Skype for Business Online 中拨号计划的继承模型。</span><span class="sxs-lookup"><span data-stu-id="5b3aa-122">The following is the inheritance model of dial plans in Skype for Business Online.</span></span>
  
![How dial plans are inherited in Skype for Business Online.](media/b2744f33-ebbd-4c23-bfba-1747312ab178.png)
  
<span data-ttu-id="5b3aa-124">下面是可能的有效拨号计划：</span><span class="sxs-lookup"><span data-stu-id="5b3aa-124">The following are the possible effective dial plans:</span></span>
  
 <span data-ttu-id="5b3aa-125">**服务国家/地区**如果任何租户范围内的用户拨号计划分配给已设置用户不定义任何租户范围内的拨号计划，用户将收到映射到服务的国家/地区与其 Office 365 使用率位置关联的有效拨号计划。</span><span class="sxs-lookup"><span data-stu-id="5b3aa-125">**Service Country** If no tenant scoped dial plan is defined and no tenant user scoped dial plan is assigned to the provisioned user, the user will receive an effective dial plan mapped to the service country associated with their Office 365 Usage Location.</span></span>
  
 <span data-ttu-id="5b3aa-126">**租户全局-服务国家/地区**如果租户用户拨号计划是定义的但不是分配给用户，已设置的用户将收到合并的租户拨号计划和服务国家/地区拨号计划与其 Office 365 使用率位置关联组成的有效拨号计划。</span><span class="sxs-lookup"><span data-stu-id="5b3aa-126">**Tenant Global - Service Country** If a tenant user dial plan is defined but not assigned to a user, the provisioned user will receive an effective dial plan consisting of a merged tenant dial plan and the service country dial plan associated with their Office 365 Usage Location.</span></span>
  
 <span data-ttu-id="5b3aa-127">**租户用户-服务国家/地区**定义和分配给用户的租户用户拨号计划，如果已设置的用户将收到合并的租户用户拨号计划和服务国家/地区拨号计划与其 Office 365 使用率位置关联组成的有效拨号计划。</span><span class="sxs-lookup"><span data-stu-id="5b3aa-127">**Tenant User - Service Country** If a tenant user dial plan is defined and assigned to a user, the provisioned user will receive an effective dial plan consisting of the merged tenant user dial plan and the service country dial plan associated with their Office 365 Usage Location.</span></span>
  
<span data-ttu-id="5b3aa-128">请参阅[创建和管理拨号计划](/SkypeForBusiness/what-are-calling-plans-in-office-365/create-and-manage-dial-plans)创建拨号计划的您的租户。</span><span class="sxs-lookup"><span data-stu-id="5b3aa-128">See [Create and manage dial plans](/SkypeForBusiness/what-are-calling-plans-in-office-365/create-and-manage-dial-plans) to create your tenant dial plans.</span></span>
  
## <a name="planning-for-tenant-dial-plans"></a><span data-ttu-id="5b3aa-129">规划租户拨号计划</span><span class="sxs-lookup"><span data-stu-id="5b3aa-129">Planning for tenant dial plans</span></span>

<span data-ttu-id="5b3aa-130">要规划自定义拨号计划，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="5b3aa-130">To plan custom dial plans, follow these steps:</span></span>
  
- <span data-ttu-id="5b3aa-131">**步骤 1**决定是否自定义拨号计划所需增强用户的拨号体验。</span><span class="sxs-lookup"><span data-stu-id="5b3aa-131">**Step 1** Decide whether a custom dial plan is needed to enhance the user dialing experience.</span></span> <span data-ttu-id="5b3aa-132">通常情况下，需要一个是支持非 E.164 拨号，如扩展或缩写国家/地区拨号。</span><span class="sxs-lookup"><span data-stu-id="5b3aa-132">Typically, the need for one would be to support non-E.164 dialing, such as extensions or abbreviated national dialing.</span></span>
    
- <span data-ttu-id="5b3aa-133">**步骤 2**确定是否需要租户全局或租户范围内的用户拨号计划，或两者。</span><span class="sxs-lookup"><span data-stu-id="5b3aa-133">**Step 2** Determine whether tenant global or tenant user scoped dial plans are needed, or both.</span></span> <span data-ttu-id="5b3aa-134">如果用户具有不同的本地拨号需求，则需使用用户范围的拨号计划。</span><span class="sxs-lookup"><span data-stu-id="5b3aa-134">User scoped dial plans are needed if users have different local dialing requirements.</span></span>
    
- <span data-ttu-id="5b3aa-p107">**第 3 步** 为需要的每个拨号计划确定有效的号码模式。只需要服务级别的国家/地区拨号计划中未定义的号码模式。</span><span class="sxs-lookup"><span data-stu-id="5b3aa-p107">**Step 3** Identify valid number patterns for each required dial plan. Only the number patterns that are not defined in the service level country dial plans are required.</span></span>
    
- <span data-ttu-id="5b3aa-p108">**第 4 步** 制定用于命名拨号计划的组织范围的方案。采用标准命名方案可确保在组织范围内的一致性，还便于维护和更新。</span><span class="sxs-lookup"><span data-stu-id="5b3aa-p108">**Step 4** Develop an organization-wide scheme for naming dial plans. Adopting a standard naming scheme assures consistency across an organization and makes maintenance and updates easier.</span></span>
    
<span data-ttu-id="5b3aa-139">[FastTrack](https://fasttrack.microsoft.com/microsoft365/capabilities?view=voice)具有其他资源和合作伙伴可帮助您实现租户拨号计划。</span><span class="sxs-lookup"><span data-stu-id="5b3aa-139">The [FastTrack](https://fasttrack.microsoft.com/microsoft365/capabilities?view=voice) has additional resources and partners that can assist you with implementing tenant dial plans.</span></span>
  
## <a name="creating-your-new-tenant-dial-plan"></a><span data-ttu-id="5b3aa-140">创建新租户拨号计划</span><span class="sxs-lookup"><span data-stu-id="5b3aa-140">Creating your new tenant dial plan</span></span>

<span data-ttu-id="5b3aa-141">在创建新拨号计划时，必须填写必填信息。</span><span class="sxs-lookup"><span data-stu-id="5b3aa-141">When you create a new dial plan, you must put in the information that is required.</span></span>
  
### <a name="name-and-simple-name"></a><span data-ttu-id="5b3aa-142">名称和简单名称</span><span class="sxs-lookup"><span data-stu-id="5b3aa-142">Name and simple name</span></span>

<span data-ttu-id="5b3aa-143">对于用户拨号计划，应指定将分配给用户标识的拨号计划的描述性名称。</span><span class="sxs-lookup"><span data-stu-id="5b3aa-143">For user dial plans, you should specify a descriptive name that identifies to the users the dial plan will be assigned.</span></span> <span data-ttu-id="5b3aa-144">拨号计划的"简单名称"会用一个派生自拨号计划名称的字符串来预填充。</span><span class="sxs-lookup"><span data-stu-id="5b3aa-144">The dial plan Simple Name is prepopulated with a string that is derived from the dial plan name.</span></span> <span data-ttu-id="5b3aa-145">"简单名称"字段可编辑，这样你便可以为自己的拨号计划创建更具描述性的命名约定。</span><span class="sxs-lookup"><span data-stu-id="5b3aa-145">The Simple Name field is editable, which enables you to create a more descriptive naming convention for your dial plans.</span></span> <span data-ttu-id="5b3aa-146">"简单名称"值不能为空，且必须唯一。</span><span class="sxs-lookup"><span data-stu-id="5b3aa-146">The Simple Name value cannot be empty and must be unique.</span></span> <span data-ttu-id="5b3aa-147">最佳实践是为整个组织制定命名约定，然后在所有网站和用户中一致地使用此约定。</span><span class="sxs-lookup"><span data-stu-id="5b3aa-147">A best practice is to develop a naming convention for your entire organization and then use this convention consistently across all sites and users.</span></span>
  
### <a name="description"></a><span data-ttu-id="5b3aa-148">说明</span><span class="sxs-lookup"><span data-stu-id="5b3aa-148">Description</span></span>

<span data-ttu-id="5b3aa-149">建议输入对应的拨号计划要应用到的地理位置或用户组的通用可识别名称。</span><span class="sxs-lookup"><span data-stu-id="5b3aa-149">We recommend that you type the common, recognizable name of the geographic location or group of users to which the corresponding dial plan applies.</span></span>
  
### <a name="external-access-prefix"></a><span data-ttu-id="5b3aa-150">外部访问前缀</span><span class="sxs-lookup"><span data-stu-id="5b3aa-150">External access prefix</span></span>

> [!CAUTION]
> <span data-ttu-id="5b3aa-151">[!警告] 当前不支持外部访问前缀。</span><span class="sxs-lookup"><span data-stu-id="5b3aa-151">External access prefix isn't currently supported.</span></span> 
  
<span data-ttu-id="5b3aa-152">如果用户需要拨打一个或多个附加的前导数位（例如，9）来获取外线，则可指定最多包含四个字符（#、\* 和 0-9）的外部访问前缀。</span><span class="sxs-lookup"><span data-stu-id="5b3aa-152">You can specify an external access prefix of up to four characters (#, \*, and 0-9) if users need to dial one or more additional leading digits (for example, 9) to get an external line.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5b3aa-153">[!注释] 如果指定外部访问前缀，则不必创建附加的规范化规则来涵盖该前缀。</span><span class="sxs-lookup"><span data-stu-id="5b3aa-153">If you specify an external access prefix, you don't need to create an additional normalization rule to accommodate the prefix.</span></span> 
  
<span data-ttu-id="5b3aa-154">请参阅[创建和管理拨号计划](/SkypeForBusiness/what-are-calling-plans-in-office-365/create-and-manage-dial-plans)创建拨号计划的您的租户。</span><span class="sxs-lookup"><span data-stu-id="5b3aa-154">See [Create and manage dial plans](/SkypeForBusiness/what-are-calling-plans-in-office-365/create-and-manage-dial-plans) to create your tenant dial plans.</span></span>
  
## <a name="normalization-rules"></a><span data-ttu-id="5b3aa-155">规范化规则</span><span class="sxs-lookup"><span data-stu-id="5b3aa-155">Normalization rules</span></span>

<span data-ttu-id="5b3aa-p110">规范化规则定义如何转换以不同格式表示的电话号码。同一号码字符串可能得到不同的解释和转换，具体取决于拨叫该号码所在的区域。如果用户需要拨打缩写的内部或外部号码，则需要制定规范化规则。</span><span class="sxs-lookup"><span data-stu-id="5b3aa-p110">Normalization rules define how phone numbers expressed in various formats are to be translated. The same number string may be interpreted and translated differently, depending on the locale from which it is dialed. Normalization rules may be necessary if users need to be able to dial abbreviated internal or external numbers.</span></span>
  
<span data-ttu-id="5b3aa-159">必须为拨号计划分配一条或多条规范化规则。</span><span class="sxs-lookup"><span data-stu-id="5b3aa-159">One or more normalization rules must be assigned to the dial plan.</span></span> <span data-ttu-id="5b3aa-160">规范化规则匹配从上到下，因此租户拨号计划中出现的顺序很重要。</span><span class="sxs-lookup"><span data-stu-id="5b3aa-160">Normalization rules are matched from top to bottom, so the order in which they appear in a tenant dial plan is important.</span></span> <span data-ttu-id="5b3aa-161">例如，如果租户拨号计划有 10 条规范化规则，则会从第一条开始，将拨叫的号码与规范化规则进行逻辑匹配，如果不匹配，则对第二条规则进行匹配，依此类推。</span><span class="sxs-lookup"><span data-stu-id="5b3aa-161">For example, if a tenant dial plan has 10 normalization rules, the dialed number matching logic will be tried starting with the first normalization rule, if there isn't a match then the second, and so forth.</span></span> <span data-ttu-id="5b3aa-162">如果与某一条规则匹配，则使用该规则，不再继续匹配其他任何定义的规则。</span><span class="sxs-lookup"><span data-stu-id="5b3aa-162">If a match is made, that rule is used and there is no effort to match any other rules that are defined.</span></span> <span data-ttu-id="5b3aa-163">一个给定的租户拨号计划中最多可以包含 25 条规范化规则。</span><span class="sxs-lookup"><span data-stu-id="5b3aa-163">There can be a maximum of 25 normalization rules in a given tenant dial plan.</span></span>
  
### <a name="determining-the-required-normalization-rules"></a><span data-ttu-id="5b3aa-164">确定所需的规范化规则</span><span class="sxs-lookup"><span data-stu-id="5b3aa-164">Determining the required normalization rules</span></span>

<span data-ttu-id="5b3aa-p112">由于任何租户拨号计划都与给定用户的服务国家/地区拨号计划有效合并，因此可能需要对服务国家/地区拨号计划的规范化规则进行评估，以确定需要哪些租户拨号计划规范化规则。 **Get-CsEffectiveTenantDialPlan** cmdlet 可用于此用途。该 cmdlet 以用户标识作为输入参数，并将所有适用的规范化规则都返回给用户。</span><span class="sxs-lookup"><span data-stu-id="5b3aa-p112">Because any tenant dial plan is effectively merged with a given user's service country dial plan it, it is likely that the service country dial plan's normalization rules need to be evaluated in order to determine which tenant dial plan normalization rules are needed. The **Get-CsEffectiveTenantDialPlan** cmdlet can be used for this purpose. The cmdlet takes the user's identity as the input parameter and will return all normalization rules that are applicable to the user.</span></span>
  
### <a name="creating-normalization-rules"></a><span data-ttu-id="5b3aa-168">创建规范化规则</span><span class="sxs-lookup"><span data-stu-id="5b3aa-168">Creating normalization rules</span></span>

<span data-ttu-id="5b3aa-p113">规范化规则使用 .NET Framework 正则表达式指定服务器为了执行反向号码查找而将拨号字符串转换为 E.164 格式时所用的数字匹配模式。可以通过指定在找到匹配项时要执行的匹配和转换的正则表达式来创建规范化规则。完成之后，你可以输入一个测试号码以验证规范化规则是否可按预期工作。</span><span class="sxs-lookup"><span data-stu-id="5b3aa-p113">Normalization rules use .NET Framework regular expressions to specify numeric match patterns that the server uses to translate dial strings to E.164 format for the purpose of performing reverse number lookup. Normalization rules can be created by specifying the regular expression for the match and the translation to be done when a match is found. When you finish, you can enter a test number to verify that the normalization rule works as expected.</span></span>
  
<span data-ttu-id="5b3aa-172">有关使用.NET Framework 正则表达式的详细信息，请参阅[.NET Framework 正则表达式](https://go.microsoft.com/fwlink/p/?linkId=140927)。</span><span class="sxs-lookup"><span data-stu-id="5b3aa-172">For details about using .NET Framework regular expressions, see [.NET Framework Regular Expressions](https://go.microsoft.com/fwlink/p/?linkId=140927).</span></span>
  
<span data-ttu-id="5b3aa-173">请参阅[创建和管理拨号计划](/SkypeForBusiness/what-are-calling-plans-in-office-365/create-and-manage-dial-plans)创建和管理规范化规则租户拨号计划。</span><span class="sxs-lookup"><span data-stu-id="5b3aa-173">See [Create and manage dial plans](/SkypeForBusiness/what-are-calling-plans-in-office-365/create-and-manage-dial-plans) to create and manage normalization rules for your tenant dial plans.</span></span>
  
### <a name="sample-normalization-rules"></a><span data-ttu-id="5b3aa-174">示例规范化规则</span><span class="sxs-lookup"><span data-stu-id="5b3aa-174">Sample normalization rules</span></span>

<span data-ttu-id="5b3aa-p114">下表显示以 .NET Framework 正则表达式形式编写的示例规范化规则。这些示例仅用作示例，不用作创建规范化规则的规范性参考。</span><span class="sxs-lookup"><span data-stu-id="5b3aa-p114">The following table shows sample normalization rules that are written as .NET Framework regular expressions. The samples are examples only and are not meant to be a prescriptive reference for creating your own normalization rules.</span></span>
  
 <span data-ttu-id="5b3aa-177">**使用.NET Framework 正则表达式的规范化规则**</span><span class="sxs-lookup"><span data-stu-id="5b3aa-177">**Normalization rules using .NET Framework regular expressions**</span></span>
  
||||||
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5b3aa-178">**规则名称**</span><span class="sxs-lookup"><span data-stu-id="5b3aa-178">**Rule name**</span></span> <br/> |<span data-ttu-id="5b3aa-179">**说明**</span><span class="sxs-lookup"><span data-stu-id="5b3aa-179">**Description**</span></span> <br/> |<span data-ttu-id="5b3aa-180">**号码模式**</span><span class="sxs-lookup"><span data-stu-id="5b3aa-180">**Number pattern**</span></span> <br/> |<span data-ttu-id="5b3aa-181">**转换**</span><span class="sxs-lookup"><span data-stu-id="5b3aa-181">**Translation**</span></span> <br/> |<span data-ttu-id="5b3aa-182">**示例**</span><span class="sxs-lookup"><span data-stu-id="5b3aa-182">**Example**</span></span> <br/> |
|<span data-ttu-id="5b3aa-183">4digitExtension</span><span class="sxs-lookup"><span data-stu-id="5b3aa-183">4digitExtension</span></span>  <br/> |<span data-ttu-id="5b3aa-184">转换 4 位数分机号。</span><span class="sxs-lookup"><span data-stu-id="5b3aa-184">Translates 4-digit extensions.</span></span>  <br/> |<span data-ttu-id="5b3aa-185">^ (\\d{4}) $</span><span class="sxs-lookup"><span data-stu-id="5b3aa-185">^(\\d{4})$</span></span>  <br/> |<span data-ttu-id="5b3aa-186">+1425555$1</span><span class="sxs-lookup"><span data-stu-id="5b3aa-186">+1425555$1</span></span>  <br/> |<span data-ttu-id="5b3aa-187">将 0100 转换为 +14255550100</span><span class="sxs-lookup"><span data-stu-id="5b3aa-187">0100 is translated to +14255550100</span></span>  <br/> |
|<span data-ttu-id="5b3aa-188">命名为 5digitExtension</span><span class="sxs-lookup"><span data-stu-id="5b3aa-188">5digitExtension</span></span>  <br/> |<span data-ttu-id="5b3aa-189">转换 5 位数分机号。</span><span class="sxs-lookup"><span data-stu-id="5b3aa-189">Translates 5-digit extensions.</span></span>  <br/> |<span data-ttu-id="5b3aa-190">^5 (\\d{4}) $</span><span class="sxs-lookup"><span data-stu-id="5b3aa-190">^5(\\d{4})$</span></span>  <br/> |<span data-ttu-id="5b3aa-191">+1425555$1</span><span class="sxs-lookup"><span data-stu-id="5b3aa-191">+1425555$1</span></span>  <br/> |<span data-ttu-id="5b3aa-192">将 50100 转换为 +14255550100</span><span class="sxs-lookup"><span data-stu-id="5b3aa-192">50100 is translated to +14255550100</span></span>  <br/> |
|<span data-ttu-id="5b3aa-193">7digitcallingRedmond</span><span class="sxs-lookup"><span data-stu-id="5b3aa-193">7digitcallingRedmond</span></span>  <br/> |<span data-ttu-id="5b3aa-194">将 7 位数号码转换为雷德蒙德本地号码。</span><span class="sxs-lookup"><span data-stu-id="5b3aa-194">Translates 7-digit numbers to Redmond local numbers.</span></span>  <br/> |<span data-ttu-id="5b3aa-195">^ (\\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="5b3aa-195">^(\\d{7})$</span></span>  <br/> |<span data-ttu-id="5b3aa-196">+1425$1</span><span class="sxs-lookup"><span data-stu-id="5b3aa-196">+1425$1</span></span>  <br/> |<span data-ttu-id="5b3aa-197">将 5550100 转换为 +14255550100</span><span class="sxs-lookup"><span data-stu-id="5b3aa-197">5550100 is translated to +14255550100</span></span>  <br/>|
|<span data-ttu-id="5b3aa-198">RedmondOperator</span><span class="sxs-lookup"><span data-stu-id="5b3aa-198">RedmondOperator</span></span>  <br/> |<span data-ttu-id="5b3aa-199">将 0 转换为雷德蒙德话务员。</span><span class="sxs-lookup"><span data-stu-id="5b3aa-199">Translates 0 to Redmond Operator.</span></span>  <br/> |<span data-ttu-id="5b3aa-200">^0$</span><span class="sxs-lookup"><span data-stu-id="5b3aa-200">^0$</span></span>  <br/> |<span data-ttu-id="5b3aa-201">+14255550100</span><span class="sxs-lookup"><span data-stu-id="5b3aa-201">+14255550100</span></span>  <br/> |<span data-ttu-id="5b3aa-202">将 0 转换为 +14255550100</span><span class="sxs-lookup"><span data-stu-id="5b3aa-202">0 is translated to +14255550100</span></span>  <br/> |
|<span data-ttu-id="5b3aa-203">RedmondSitePrefix</span><span class="sxs-lookup"><span data-stu-id="5b3aa-203">RedmondSitePrefix</span></span>  <br/> |<span data-ttu-id="5b3aa-204">转换带有网内前缀 (6) 和雷德蒙德站点代码 (222) 的号码。</span><span class="sxs-lookup"><span data-stu-id="5b3aa-204">Translates numbers with on-net prefix (6) and Redmond site code (222).</span></span>  <br/> |<span data-ttu-id="5b3aa-205">^6222 (\\d{4}) $</span><span class="sxs-lookup"><span data-stu-id="5b3aa-205">^6222(\\d{4})$</span></span>  <br/> |<span data-ttu-id="5b3aa-206">+1425555$1</span><span class="sxs-lookup"><span data-stu-id="5b3aa-206">+1425555$1</span></span>  <br/> |<span data-ttu-id="5b3aa-207">将 62220100 转换为 +14255550100</span><span class="sxs-lookup"><span data-stu-id="5b3aa-207">62220100 is translated to +14255550100</span></span>  <br/> |
|<span data-ttu-id="5b3aa-208">5digitRange</span><span class="sxs-lookup"><span data-stu-id="5b3aa-208">5digitRange</span></span>  <br/> |<span data-ttu-id="5b3aa-209">转换以 3-7（含 3 和 7）之间的数字开头的 5 位数分机号。</span><span class="sxs-lookup"><span data-stu-id="5b3aa-209">Translates 5-digit extensions starting with the digit range between 3-7 inclusive.</span></span>  <br/> |<span data-ttu-id="5b3aa-210">^ ([3-7]\\d{4}) $</span><span class="sxs-lookup"><span data-stu-id="5b3aa-210">^([3-7]\\d{4})$</span></span>  <br/> |<span data-ttu-id="5b3aa-211">+ 142555$ 1</span><span class="sxs-lookup"><span data-stu-id="5b3aa-211">+142555$1</span></span> <br/> |<span data-ttu-id="5b3aa-212">将 54567 转换为 +14255554567</span><span class="sxs-lookup"><span data-stu-id="5b3aa-212">54567 is translated to +14255554567</span></span>  <br/> |
|<span data-ttu-id="5b3aa-213">PrefixAdded</span><span class="sxs-lookup"><span data-stu-id="5b3aa-213">PrefixAdded</span></span>  <br/> |<span data-ttu-id="5b3aa-214">在对第一位和第三位数字有限制的 9 位数号码前添加国家/地区前缀。</span><span class="sxs-lookup"><span data-stu-id="5b3aa-214">Adds a country prefix in front of a 9 digit number with restrictions on the first and third digits.</span></span>  <br/> |<span data-ttu-id="5b3aa-215">^ ([2-9]\\d\\d [2-9]\\d{6}) $</span><span class="sxs-lookup"><span data-stu-id="5b3aa-215">^([2-9]\\d\\d[2-9]\\d{6})$</span></span>  <br/> |<span data-ttu-id="5b3aa-216">1$1</span><span class="sxs-lookup"><span data-stu-id="5b3aa-216">1$1</span></span>  <br/> |<span data-ttu-id="5b3aa-217">将 4255554567 转换为 14255554567</span><span class="sxs-lookup"><span data-stu-id="5b3aa-217">4255554567 is translated to 14255554567</span></span>  <br/> |
|<span data-ttu-id="5b3aa-218">NoTranslation</span><span class="sxs-lookup"><span data-stu-id="5b3aa-218">NoTranslation</span></span>  <br/> |<span data-ttu-id="5b3aa-219">匹配 5 位数，但不转换。</span><span class="sxs-lookup"><span data-stu-id="5b3aa-219">Match 5 digits but no translation.</span></span>  <br/> |<span data-ttu-id="5b3aa-220">^ (\\d{5}) $</span><span class="sxs-lookup"><span data-stu-id="5b3aa-220">^(\\d{5})$</span></span>  <br/> |<span data-ttu-id="5b3aa-221">$1</span><span class="sxs-lookup"><span data-stu-id="5b3aa-221">$1</span></span>  <br/> |<span data-ttu-id="5b3aa-222">将 34567 转换为 34567</span><span class="sxs-lookup"><span data-stu-id="5b3aa-222">34567 is translated to 34567</span></span>  <br/> |
   
 <span data-ttu-id="5b3aa-223">**上面显示了基于规范化规则的雷德蒙德拨号计划。**</span><span class="sxs-lookup"><span data-stu-id="5b3aa-223">**Redmond dial plan based on normalization rules shown above.**</span></span>
  
<span data-ttu-id="5b3aa-224">下表根据上表显示的规范化规则对用于雷德蒙德、华盛顿、美国的示例拨号计划进行说明。</span><span class="sxs-lookup"><span data-stu-id="5b3aa-224">The following table illustrates a sample dial plan for Redmond, Washington, United States, based on the normalization rules shown in the previous table.</span></span>
<span data-ttu-id="5b3aa-225">|:-----| |**雷德蒙德拨号计划**</span><span class="sxs-lookup"><span data-stu-id="5b3aa-225">|:-----| |**Redmond dial plan**</span></span> <br/> <span data-ttu-id="5b3aa-226">| | 命名为 5digitExtension</span><span class="sxs-lookup"><span data-stu-id="5b3aa-226">| |5digitExtension</span></span> <br/> <span data-ttu-id="5b3aa-227">| | 7digitcallingRedmond</span><span class="sxs-lookup"><span data-stu-id="5b3aa-227">| |7digitcallingRedmond</span></span> <br/> <span data-ttu-id="5b3aa-228">| |RedmondSitePrefix</span><span class="sxs-lookup"><span data-stu-id="5b3aa-228">| |RedmondSitePrefix</span></span> <br/> <span data-ttu-id="5b3aa-229">| |RedmondOperator</span><span class="sxs-lookup"><span data-stu-id="5b3aa-229">| |RedmondOperator</span></span> <br/> |
   
> [!NOTE]
> <span data-ttu-id="5b3aa-p116">[!注释] 上表中所示的规范化规则名称不包含空格，你可以选择是否要包含。例如，该表中的第一个名称，本应写成"5 digit extension"或"5-digit Extension"，但它仍然有效。</span><span class="sxs-lookup"><span data-stu-id="5b3aa-p116">The normalization rules names shown in the preceding table do not include spaces, but this is a matter of choice. The first name in the table, for example, could have been written "5 digit extension" or "5-digit Extension" and still be valid.</span></span> 
  

## <a name="related-topics"></a><span data-ttu-id="5b3aa-232">相关主题</span><span class="sxs-lookup"><span data-stu-id="5b3aa-232">Related topics</span></span>

[<span data-ttu-id="5b3aa-233">创建并管理拨号计划</span><span class="sxs-lookup"><span data-stu-id="5b3aa-233">Create and manage dial plans</span></span>](/SkypeForBusiness/what-are-calling-plans-in-office-365/create-and-manage-dial-plans)

[<span data-ttu-id="5b3aa-234">关于转移电话号码的常见问题</span><span class="sxs-lookup"><span data-stu-id="5b3aa-234">Transferring phone numbers common questions</span></span>](transferring-phone-numbers-common-questions.md)

[<span data-ttu-id="5b3aa-235">用于通话套餐的不同类型的电话号码</span><span class="sxs-lookup"><span data-stu-id="5b3aa-235">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

<span data-ttu-id="5b3aa-236">[管理组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
[紧急呼叫条款和条件](emergency-calling-terms-and-conditions.md)</span><span class="sxs-lookup"><span data-stu-id="5b3aa-236">[Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
[Emergency calling terms and conditions](emergency-calling-terms-and-conditions.md)</span></span>

<span data-ttu-id="5b3aa-237">[Skype for Business Online：紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="5b3aa-237">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>