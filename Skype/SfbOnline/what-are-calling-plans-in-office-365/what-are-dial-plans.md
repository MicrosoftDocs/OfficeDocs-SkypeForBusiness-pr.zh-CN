---
title: What are dial plans?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: 2f0cfb59-1ca1-4e31-84ce-09d0b1a7ce1b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
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
- Strat_SB_PSTN
description: 'Learn what type of dial calling plans (PSTN Calling dial plans) are available with Office 365 and how to choose one for your organization.  '
search.appverid:
- MED150
- MOE150
ms.openlocfilehash: c24727dec0a9d938b3b0e40ef6f47501944e70e1
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="what-are-dial-plans"></a>What are dial plans?

拨号计划是一组指定的规范化规则，可将单个用户拨打的电话号码转换为替代格式（通常为 E.164），以用于呼叫授权和呼叫路由。
  
A dial plan consists of one or more normalization rules that define how phone numbers expressed in various formats are translated to an alternate format. The same dial string may be interpreted and translated differently in different dial plans, so depending on which dial plan is assigned to a given user, the same dialed number may be translated and routed differently.
  
See [Create and manage dial plans](create-and-manage-dial-plans.md) to create and manage tenant dial plans.
  
## <a name="tenant-dial-plan-scope"></a>租户拨号计划范围

拨号计划范围确定可以应用拨号计划的层次结构级别。 The scopes are different than in a Skype for Business Server 2015 on-premises deployment. 客户端可通过用户登录 Skype for Business Online 时自动提供的配置设置获得相应的拨号计划。 作为管理员，你可以使用 Remote PowerShell 管理和分配拨号计划范围级别。
  
In Skype for Business Online, there are two types of dial plans - service scoped and tenant (which is for your organization) scoped. A service scoped dial plan is defined for every country/region where the Office 365 Phone System is available. Each user is automatically assigned the service country dial plan that matches the Office 365 Usage Location assigned to the user. You can't change the service country dial plan, but you can create tenant scoped dial plans, which augment the service country dial plan. As clients are provisioned, they obtain an "effective dial plan," which is a combination of the service country dial plan and the appropriately scoped tenant dial plan. 因此，在租户拨号计划中不必定义所有规范化规则，因为这些规则已经存在于服务国家/地区拨号计划中。
  
租户拨号计划可进一步划分为两种范围 - 租户范围或用户范围。如果租户定义并分配了用户范围的拨号计划，那么会为该用户配置由用户的服务国家/地区拨号计划和已分配的用户拨号计划构成的有效拨号计划。如果租户定义租户范围拨号计划但没有分配用户范围的拨号计划，那么会为该用户配置由用户的服务国家/地区拨号计划和租户拨号计划构成的有效拨号计划。
  
下面是 Skype for Business Online 中拨号计划的继承模型。
  
![How dial plans are inherited in Skype for Business Online.](../images/b2744f33-ebbd-4c23-bfba-1747312ab178.png)
  
下面是可能的有效拨号计划：
  
 **Service Country** If no tenant scoped dial plan is defined and no tenant user scoped dial plan is assigned to the provisioned user, the user will receive an effective dial plan mapped to the service country associated with their Office 365 Usage Location.
  
 **Tenant Global - Service Country** If a tenant user dial plan is defined but not assigned to a user, the provisioned user will receive an effective dial plan consisting of a merged tenant dial plan and the service country dial plan associated with their Office 365 Usage Location.
  
 **Tenant User - Service Country** If a tenant user dial plan is defined and assigned to a user, the provisioned user will receive an effective dial plan consisting of the merged tenant user dial plan and the service country dial plan associated with their Office 365 Usage Location.
  
See [Create and manage dial plans](create-and-manage-dial-plans.md) to create your tenant dial plans.
  
## <a name="planning-for-tenant-dial-plans"></a>规划租户拨号计划

要规划自定义拨号计划，请执行以下步骤：
  
- **Step 1** Decide whether a custom dial plan is needed to enhance the user dialing experience. Typically, the need for one would be to support non-E.164 dialing, such as extensions or abbreviated national dialing.
    
- **Step 2** Determine whether tenant global or tenant user scoped dial plans are needed, or both. 如果用户具有不同的本地拨号需求，则需使用用户范围的拨号计划。
    
- **第 3 步** 为需要的每个拨号计划确定有效的号码模式。只需要服务级别的国家/地区拨号计划中未定义的号码模式。
    
- **第 4 步** 制定用于命名拨号计划的组织范围的方案。采用标准命名方案可确保在组织范围内的一致性，还便于维护和更新。
    
The [FastTrack](https://fasttrack.microsoft.com/microsoft365/capabilities?view=voice) has additional resources and partners that can assist you with implementing tenant dial plans.
  
## <a name="creating-your-new-tenant-dial-plan"></a>创建新租户拨号计划

在创建新拨号计划时，必须填写必填信息。
  
### <a name="name-and-simple-name"></a>名称和简单名称

For user dial plans, you should specify a descriptive name that identifies to the users the dial plan will be assigned. 拨号计划的"简单名称"会用一个派生自拨号计划名称的字符串来预填充。 "简单名称"字段可编辑，这样你便可以为自己的拨号计划创建更具描述性的命名约定。 "简单名称"值不能为空，且必须唯一。 最佳实践是为整个组织制定命名约定，然后在所有网站和用户中一致地使用此约定。
  
### <a name="description"></a>说明

建议输入对应的拨号计划要应用到的地理位置或用户组的通用可识别名称。
  
### <a name="external-access-prefix"></a>外部访问前缀

> [!CAUTION]
> [!警告] 当前不支持外部访问前缀。 
  
如果用户需要拨打一个或多个附加的前导数位（例如，9）来获取外线，则可指定最多包含四个字符（#、* 和 0-9）的外部访问前缀。
  
> [!NOTE]
> [!注释] 如果指定外部访问前缀，则不必创建附加的规范化规则来涵盖该前缀。 
  
See [Create and manage dial plans](create-and-manage-dial-plans.md) to create your tenant dial plans.
  
## <a name="normalization-rules"></a>规范化规则

规范化规则定义如何转换以不同格式表示的电话号码。同一号码字符串可能得到不同的解释和转换，具体取决于拨叫该号码所在的区域。如果用户需要拨打缩写的内部或外部号码，则需要制定规范化规则。
  
必须为拨号计划分配一条或多条规范化规则。 Normalization rules are matched from top to bottom, so the order in which they appear in a tenant dial plan is important. 例如，如果租户拨号计划有 10 条规范化规则，则会从第一条开始，将拨叫的号码与规范化规则进行逻辑匹配，如果不匹配，则对第二条规则进行匹配，依此类推。 如果与某一条规则匹配，则使用该规则，不再继续匹配其他任何定义的规则。 一个给定的租户拨号计划中最多可以包含 25 条规范化规则。
  
### <a name="determining-the-required-normalization-rules"></a>确定所需的规范化规则

由于任何租户拨号计划都与给定用户的服务国家/地区拨号计划有效合并，因此可能需要对服务国家/地区拨号计划的规范化规则进行评估，以确定需要哪些租户拨号计划规范化规则。 **Get-CsEffectiveTenantDialPlan** cmdlet 可用于此用途。该 cmdlet 以用户标识作为输入参数，并将所有适用的规范化规则都返回给用户。
  
### <a name="creating-normalization-rules"></a>创建规范化规则

规范化规则使用 .NET Framework 正则表达式指定服务器为了执行反向号码查找而将拨号字符串转换为 E.164 格式时所用的数字匹配模式。可以通过指定在找到匹配项时要执行的匹配和转换的正则表达式来创建规范化规则。完成之后，你可以输入一个测试号码以验证规范化规则是否可按预期工作。
  
For details about using .NET Framework regular expressions, see [.NET Framework Regular Expressions](https://go.microsoft.com/fwlink/p/?linkId=140927).
  
See [Create and manage dial plans](create-and-manage-dial-plans.md) to create and manage normalization rules for your tenant dial plans.
  
### <a name="sample-normalization-rules"></a>示例规范化规则

下表显示以 .NET Framework 正则表达式形式编写的示例规范化规则。这些示例仅用作示例，不用作创建规范化规则的规范性参考。
  
 **Normalization rules using .NET Framework regular expressions**
  
||||||
|:-----|:-----|:-----|:-----|:-----|
|**规则名称** <br/> |**说明** <br/> |**号码模式** <br/> |**转换** <br/> |**示例** <br/> |
|4digitExtension  <br/> |转换 4 位数分机号。  <br/> |^(\\d{4})$  <br/> |+1425555$1  <br/> |将 0100 转换为 +14255550100  <br/> |
|5digitExtension  <br/> |转换 5 位数分机号。  <br/> |^5(\\d{4})$  <br/> |+1425555$1  <br/> |将 50100 转换为 +14255550100  <br/> |
|7digitcallingRedmond  <br/> |将 7 位数号码转换为雷德蒙德本地号码。  <br/> |^(\\d{7})$  <br/> |+1425$1  <br/> |将 5550100 转换为 +14255550100  <br/>|
|RedmondOperator  <br/> |将 0 转换为雷德蒙德话务员。  <br/> |^0$  <br/> |+14255550100  <br/> |将 0 转换为 +14255550100  <br/> |
|RedmondSitePrefix  <br/> |转换带有网内前缀 (6) 和雷德蒙德站点代码 (222) 的号码。  <br/> |^6222(\\d{4})$  <br/> |+1425555$1  <br/> |将 62220100 转换为 +14255550100  <br/> |
|5digitRange  <br/> |转换以 3-7（含 3 和 7）之间的数字开头的 5 位数分机号。  <br/> |^([3-7]\\d{4})$  <br/> |+142570$1  <br/> |将 54567 转换为 +14255554567  <br/> |
|PrefixAdded  <br/> |在对第一位和第三位数字有限制的 9 位数号码前添加国家/地区前缀。  <br/> |^([2-9]\\d\\d[2-9]\\d{6})$  <br/> |1$1  <br/> |将 4255554567 转换为 14255554567  <br/> |
|NoTranslation  <br/> |匹配 5 位数，但不转换。  <br/> |^(\\d{5})$  <br/> |$1  <br/> |将 34567 转换为 34567  <br/> |
   
 **上面显示了基于规范化规则的雷德蒙德拨号计划。**
  
下表根据上表显示的规范化规则对用于雷德蒙德、华盛顿、美国的示例拨号计划进行说明。
|:-----| |**Redmond dial plan** <br/> | |5digitExtension <br/> | |7digitcallingRedmond <br/> | |RedmondSitePrefix <br/> | |RedmondOperator <br/> |
   
> [!NOTE]
> [!注释] 上表中所示的规范化规则名称不包含空格，你可以选择是否要包含。例如，该表中的第一个名称，本应写成"5 digit extension"或"5-digit Extension"，但它仍然有效。 
  
## <a name="related-topics"></a>相关主题
[创建并管理拨号计划](create-and-manage-dial-plans.md)

[Skype for Business 和 Microsoft Teams 外接程序许可](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)

[关于转移电话号码的常见问题](transferring-phone-numbers-common-questions.md)

[用于通话套餐的不同类型的电话号码](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[管理你的组织的电话号码](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[紧急呼叫条款和条件](emergency-calling-terms-and-conditions.md)

[Skype for Business Online：紧急呼叫免责声明标签](https://go.microsoft.com/fwlink/?LinkID=692099)

  
 