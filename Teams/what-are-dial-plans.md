---
title: 什么是拨号计划？
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: 2f0cfb59-1ca1-4e31-84ce-09d0b1a7ce1b
ms.tgt.pltfrm: cloud
ms.service:
- skype-for-business-online
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
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
ms.openlocfilehash: 28e0b3d282cba17061f0573b5bd9efe7e27de786
ms.sourcegitcommit: 8a4ed16adc60497510a528784e139075fbae9e55
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "25502355"
---
# <a name="what-are-dial-plans"></a>什么是拨号计划？

拨号计划是一组指定的规范化规则，可将单个用户拨打的电话号码转换为替代格式（通常为 E.164），以用于呼叫授权和呼叫路由。

拨号计划包括一个或多个规范化规则定义如何以不同格式表示的电话号码转换为备用格式。 相同的拨号串可能解析和转换不同的拨号计划中的不同，数量相同拨打根据的拨号计划分配给给定用户，因此可能转换和不同路由。

请参阅[创建和管理拨号计划](create-and-manage-dial-plans.md)创建和管理租户拨号计划。

## <a name="tenant-dial-plan-scope"></a>租户拨号计划范围

拨号计划范围确定可以应用拨号计划的层次结构级别。 范围是与业务服务器 2015年 Skype 中本地部署的不同。 客户端可通过用户登录 Skype for Business Online 时自动提供的配置设置获得相应的拨号计划。 作为管理员，你可以使用 Remote PowerShell 管理和分配拨号计划范围级别。

在业务 online Skype，有两种类型的拨号计划的范围内的服务和租户 （这是您的组织） 范围内。 Office 365 电话系统位于每个国家/地区定义范围内的服务拨号计划。 每个用户自动分配服务的国家/地区拨号计划的与分配给用户的 Office 365 使用率位置匹配。 不能更改服务的国家/地区拨号计划，但您可以创建租户范围内的拨号计划，扩充服务国家/地区拨号计划。 设置客户端，如获得"有效拨号计划"，即服务国家/地区拨号计划和相应范围的租户拨号计划的组合。 因此，在租户拨号计划中不必定义所有规范化规则，因为这些规则已经存在于服务国家/地区拨号计划中。

租户拨号计划可进一步划分为两种范围 - 租户范围或用户范围。如果租户定义并分配了用户范围的拨号计划，那么会为该用户配置由用户的服务国家/地区拨号计划和已分配的用户拨号计划构成的有效拨号计划。如果租户定义租户范围拨号计划但没有分配用户范围的拨号计划，那么会为该用户配置由用户的服务国家/地区拨号计划和租户拨号计划构成的有效拨号计划。

下面是 Skype for Business Online 中拨号计划的继承模型。

![How dial plans are inherited in Skype for Business Online.](media/b2744f33-ebbd-4c23-bfba-1747312ab178.png)

下面是可能的有效拨号计划：

 **服务国家/地区**如果任何租户范围内的用户拨号计划分配给已设置用户不定义任何租户范围内的拨号计划，用户将收到映射到服务的国家/地区与其 Office 365 使用率位置关联的有效拨号计划。

 **租户全局-服务国家/地区**如果租户用户拨号计划是定义的但不是分配给用户，已设置的用户将收到合并的租户拨号计划和服务国家/地区拨号计划与其 Office 365 使用率位置关联组成的有效拨号计划。

 **租户用户-服务国家/地区**定义和分配给用户的租户用户拨号计划，如果已设置的用户将收到合并的租户用户拨号计划和服务国家/地区拨号计划与其 Office 365 使用率位置关联组成的有效拨号计划。

请参阅[创建和管理拨号计划](create-and-manage-dial-plans.md)创建拨号计划的您的租户。

## <a name="planning-for-tenant-dial-plans"></a>规划租户拨号计划

要规划自定义拨号计划，请执行以下步骤：

- **步骤 1**决定是否自定义拨号计划所需增强用户的拨号体验。 通常情况下，需要一个是支持非 E.164 拨号，如扩展或缩写国家/地区拨号。

- **步骤 2**确定是否需要租户全局或租户范围内的用户拨号计划，或两者。 如果用户具有不同的本地拨号需求，则需使用用户范围的拨号计划。

- **第 3 步** 为需要的每个拨号计划确定有效的号码模式。只需要服务级别的国家/地区拨号计划中未定义的号码模式。

- **第 4 步** 制定用于命名拨号计划的组织范围的方案。采用标准命名方案可确保在组织范围内的一致性，还便于维护和更新。

[FastTrack](https://fasttrack.microsoft.com/microsoft365/capabilities?view=voice)具有其他资源和合作伙伴可帮助您实现租户拨号计划。

## <a name="creating-your-new-tenant-dial-plan"></a>创建新租户拨号计划

在创建新拨号计划时，必须填写必填信息。

### <a name="name-and-simple-name"></a>名称和简单名称

对于用户拨号计划，应指定将分配给用户标识的拨号计划的描述性名称。 拨号计划的"简单名称"会用一个派生自拨号计划名称的字符串来预填充。 "简单名称"字段可编辑，这样你便可以为自己的拨号计划创建更具描述性的命名约定。 "简单名称"值不能为空，且必须唯一。 最佳实践是为整个组织制定命名约定，然后在所有网站和用户中一致地使用此约定。

### <a name="description"></a>说明

建议输入对应的拨号计划要应用到的地理位置或用户组的通用可识别名称。

### <a name="external-access-prefix"></a>外部访问前缀

> [!CAUTION]
> [!警告] 当前不支持外部访问前缀。 

如果用户需要拨打一个或多个附加的前导数位（例如，9）来获取外线，则可指定最多包含四个字符（#、* 和 0-9）的外部访问前缀。

> [!NOTE]
> [!注释] 如果指定外部访问前缀，则不必创建附加的规范化规则来涵盖该前缀。 

请参阅[创建和管理拨号计划](create-and-manage-dial-plans.md)创建拨号计划的您的租户。

## <a name="normalization-rules"></a>规范化规则

规范化规则定义如何转换以不同格式表示的电话号码。同一号码字符串可能得到不同的解释和转换，具体取决于拨叫该号码所在的区域。如果用户需要拨打缩写的内部或外部号码，则需要制定规范化规则。

必须为拨号计划分配一条或多条规范化规则。 规范化规则匹配从上到下，因此租户拨号计划中出现的顺序很重要。 例如，如果租户拨号计划有 10 条规范化规则，则会从第一条开始，将拨叫的号码与规范化规则进行逻辑匹配，如果不匹配，则对第二条规则进行匹配，依此类推。 如果与某一条规则匹配，则使用该规则，不再继续匹配其他任何定义的规则。 一个给定的租户拨号计划中最多可以包含 25 条规范化规则。

### <a name="determining-the-required-normalization-rules"></a>确定所需的规范化规则

由于任何租户拨号计划都与给定用户的服务国家/地区拨号计划有效合并，因此可能需要对服务国家/地区拨号计划的规范化规则进行评估，以确定需要哪些租户拨号计划规范化规则。 **Get-CsEffectiveTenantDialPlan** cmdlet 可用于此用途。该 cmdlet 以用户标识作为输入参数，并将所有适用的规范化规则都返回给用户。

### <a name="creating-normalization-rules"></a>创建规范化规则

规范化规则使用 .NET Framework 正则表达式指定服务器为了执行反向号码查找而将拨号字符串转换为 E.164 格式时所用的数字匹配模式。可以通过指定在找到匹配项时要执行的匹配和转换的正则表达式来创建规范化规则。完成之后，你可以输入一个测试号码以验证规范化规则是否可按预期工作。

有关使用.NET Framework 正则表达式的详细信息，请参阅[.NET Framework 正则表达式](https://go.microsoft.com/fwlink/p/?linkId=140927)。

请参阅[创建和管理拨号计划](create-and-manage-dial-plans.md)创建和管理规范化规则租户拨号计划。

### <a name="sample-normalization-rules"></a>示例规范化规则

下表显示以 .NET Framework 正则表达式形式编写的示例规范化规则。这些示例仅用作示例，不用作创建规范化规则的规范性参考。

 **使用.NET Framework 正则表达式的规范化规则**

||||||
|:-----|:-----|:-----|:-----|:-----|
|**规则名称** <br/> |**说明** <br/> |**号码模式** <br/> |**转换** <br/> |**示例** <br/> |
|4digitExtension  <br/> |转换 4 位数分机号。  <br/> |^ (\\d{4}) $  <br/> |+1425555$1  <br/> |将 0100 转换为 +14255550100  <br/> |
|命名为 5digitExtension  <br/> |转换 5 位数分机号。  <br/> |^5 (\\d{4}) $  <br/> |+1425555$1  <br/> |将 50100 转换为 +14255550100  <br/> |
|7digitcallingRedmond  <br/> |将 7 位数号码转换为雷德蒙德本地号码。  <br/> |^ (\\d{7}) $  <br/> |+1425$1  <br/> |将 5550100 转换为 +14255550100  <br/>|
|RedmondOperator  <br/> |将 0 转换为雷德蒙德话务员。  <br/> |^0$  <br/> |+14255550100  <br/> |将 0 转换为 +14255550100  <br/> |
|RedmondSitePrefix  <br/> |转换带有网内前缀 (6) 和雷德蒙德站点代码 (222) 的号码。  <br/> |^6222 (\\d{4}) $  <br/> |+1425555$1  <br/> |将 62220100 转换为 +14255550100  <br/> |
|5digitRange  <br/> |转换以 3-7（含 3 和 7）之间的数字开头的 5 位数分机号。  <br/> |^ ([3-7]\\d{4}) $  <br/> |+ 142555$ 1 <br/> |将 54567 转换为 +14255554567  <br/> |
|PrefixAdded  <br/> |在对第一位和第三位数字有限制的 9 位数号码前添加国家/地区前缀。  <br/> |^ ([2-9]\\d\\d [2-9]\\d{6}) $  <br/> |1$1  <br/> |将 4255554567 转换为 14255554567  <br/> |
|NoTranslation  <br/> |匹配 5 位数，但不转换。  <br/> |^ (\\d{5}) $  <br/> |$1  <br/> |将 34567 转换为 34567  <br/> |

 **上面显示了基于规范化规则的雷德蒙德拨号计划。**


| 下表根据上表显示的规范化规则对用于雷德蒙德、华盛顿、美国的示例拨号计划进行说明。 |
|:---------------------------------------------------------------------------------------------------------------------------------------------------------|
| **雷德蒙德拨号计划** <br/>                                                                                                                              |
| 命名为 5digitExtension <br/>                                                                                                                                    |
| 7digitcallingRedmond <br/>                                                                                                                               |
| RedmondSitePrefix <br/>                                                                                                                                  |
| RedmondOperator <br/>                                                                                                                                    |

> [!NOTE]
> [!注释] 上表中所示的规范化规则名称不包含空格，你可以选择是否要包含。例如，该表中的第一个名称，本应写成"5 digit extension"或"5-digit Extension"，但它仍然有效。 


## <a name="related-topics"></a>相关主题

[创建并管理拨号计划](create-and-manage-dial-plans.md)

[关于转移电话号码的常见问题](transferring-phone-numbers-common-questions.md)

[用于通话套餐的不同类型的电话号码](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[管理组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
[紧急呼叫条款和条件](emergency-calling-terms-and-conditions.md)

[Skype for Business Online：紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)