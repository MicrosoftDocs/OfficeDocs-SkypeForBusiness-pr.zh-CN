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
ms.openlocfilehash: 7d5c004a8ea7d4ce851cfa6717abc2483102ed26b5526b49bcbf69f6d495f2b7
ms.sourcegitcommit: 2a76435beaac1e5daa647e93f693ea8672ec0135
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/11/2021
ms.locfileid: "57848717"
---
# <a name="what-are-dial-plans"></a>什么是拨号计划？

拨号计划是一组指定的规范化规则，用于将单个用户拨打的电话号码转换为备用格式 (通常为 E.164) ，以便进行呼叫授权和语音路由。

拨号计划由一个或多个规范化规则组成，这些规则定义如何将以各种格式表示的电话号码转换为备用格式。 同一拨号字符串在不同拨号计划中可能以不同方式解释和转换，因此，根据为给定用户分配的拨号计划，同一拨号号码可能以不同方式转换和路由。 最多可以有 1，000 个租户拨号计划。

请参阅 [创建和管理拨号计划以](create-and-manage-dial-plans.md) 创建和管理租户拨号计划。

## <a name="tenant-dial-plan-scope"></a>租户拨号计划范围

拨号计划范围确定可以应用拨号计划的层次结构级别。 客户端通过预配设置获取相应的拨号计划，这些设置在用户登录到 Teams 时自动提供。 作为管理员，可以使用远程管理中心或远程 PowerShell Microsoft Teams和分配拨号计划范围级别。

在Teams中，有两种类型的拨号计划：服务范围和租户范围 (，适用于组织) 。 服务范围的拨号计划为可用的每个电话系统定义。 系统会自动为每个用户分配与分配给用户的使用位置匹配的服务国家/地区拨号计划。 你无法更改服务国家/地区拨号计划，但可以创建租户范围的拨号计划，用于增强服务国家/地区拨号计划。 在预配客户端时，他们获得"有效拨号计划"，这是服务国家/地区拨号计划和适当范围的租户拨号计划的组合。 因此，在租户拨号计划中不必定义所有规范化规则，因为这些规则已经存在于服务国家/地区拨号计划中。

租户拨号计划可以进一步细分为两个范围 - 租户范围或用户范围。 如果租户定义并分配用户范围的拨号计划，将为该用户预配用户的服务国家/地区拨号计划和分配的用户拨号计划的有效拨号计划。 如果租户定义了租户范围的拨号计划，但没有分配用户范围的拨号计划，则将为该用户预配用户的服务国家/地区拨号计划和租户拨号计划的有效拨号计划。

下面是拨号计划中拨号计划的继承Teams。

![拨号计划的继承Teams](media/b2744f33-ebbd-4c23-bfba-1747312ab178.png)

下面是可能的有效拨号计划：

 **服务国家/地区** 如果未定义租户范围的拨号计划，并且未向预配的用户分配租户用户范围的拨号计划，则用户将收到映射到与其使用位置关联的服务国家/地区的有效拨号计划。

 **租户全局 - 服务国家/地区** 如果定义了租户用户拨号计划，但没有分配给用户，则预配的用户将收到一个有效的拨号计划，其中包括合并的租户拨号计划以及与其使用位置关联的服务国家/地区拨号计划。

 **租户用户 - 服务国家/地区** 如果定义了租户用户拨号计划并将其分配给用户，则预配的用户将收到一个有效的拨号计划，其中包括合并的租户用户拨号计划以及与其使用位置关联的服务国家/地区拨号计划。

请参阅 [创建和管理拨号计划](create-and-manage-dial-plans.md) 以创建租户拨号计划。

> [!NOTE]
> 在未将拨号计划规范化规则应用于拨号号码的情况下，拨号字符串仍规范化为前加"+抄送"，其中 CC 是拨号用户的使用位置的国家/地区代码。 这适用于呼叫计划、直接路由和 PSTN 会议拨出方案。 此外，如果租户拨号计划规范化规则导致号码不是以"+"开始，则呼叫服务将尝试根据租户拨号计划规范化从 Teams 客户端收到的号码，如果不匹配，则根据区域拨号计划。 为了避免双重规范化，建议直接路由客户规范化数字以包含 +，然后使用中继翻译规则删除 +。 

## <a name="planning-for-tenant-dial-plans"></a>规划租户拨号计划

要规划自定义拨号计划，请执行以下步骤：

- **步骤 1** 确定是否需要自定义拨号计划来增强用户拨号体验。 通常，需要支持非 E.164 拨号，例如分机号码或缩写国家/直拨。

- **步骤 2** 确定是否需要租户全局拨号计划或租户用户范围拨号计划，或同时需要这两者。 如果用户具有不同的本地拨号需求，则需使用用户范围的拨号计划。

- **第 3 步** 为需要的每个拨号计划确定有效的号码模式。只需要服务级别的国家/地区拨号计划中未定义的号码模式。

- **第 4 步** 制定用于命名拨号计划的组织范围的方案。采用标准命名方案可确保在组织范围内的一致性，还便于维护和更新。


## <a name="creating-your-new-dial-plan"></a>创建新的拨号计划

在创建新拨号计划时，必须填写必填信息。

### <a name="name-and-simple-name"></a>名称和简单名称

对于用户拨号计划，应指定一个描述性名称，用于标识要为其分配拨号计划的用户。 拨号计划简单名称预填充了派生自拨号计划名称的字符串。 "简单名称"字段可编辑，这样你便可以为自己的拨号计划创建更具描述性的命名约定。 "简单名称"值不能为空，且必须唯一。 最佳实践是为整个组织制定命名约定，然后在所有网站和用户中一致地使用此约定。

### <a name="description"></a>描述

建议输入对应的拨号计划要应用到的地理位置或用户组的通用可识别名称。

### <a name="external-access-prefix"></a>外部访问前缀
<a name="bkexternalprefix"> </a>

如果用户需要拨打一个或多个附加的前导数位（例如，9）来获取外线，则可指定最多包含四个字符（#、* 和 0-9）的外部访问前缀。

> [!NOTE]
> [!注释] 如果指定外部访问前缀，则不必创建附加的规范化规则来涵盖该前缀。

请参阅 [创建和管理拨号计划](create-and-manage-dial-plans.md) 以创建租户拨号计划。

## <a name="normalization-rules"></a>规范化规则
<a name="bknormalizationrule"> </a>

规范化规则定义如何转换以不同格式表示的电话号码。同一号码字符串可能得到不同的解释和转换，具体取决于拨叫该号码所在的区域。如果用户需要拨打缩写的内部或外部号码，则需要制定规范化规则。

必须为拨号计划分配一条或多条规范化规则。 规范化规则从上到下匹配，因此它们在租户拨号计划中的显示顺序非常重要。 例如，如果租户拨号计划有 10 条规范化规则，则会从第一条开始，将拨叫的号码与规范化规则进行逻辑匹配，如果不匹配，则对第二条规则进行匹配，依此类推。 如果与某一条规则匹配，则使用该规则，不再继续匹配其他任何定义的规则。 给定租户拨号计划中最多可以有 50 条规范化规则。

### <a name="determining-the-required-normalization-rules"></a>确定所需的规范化规则

由于任何租户拨号计划有效地与给定用户的服务国家/地区拨号计划合并，因此可能需要评估服务国家/地区拨号计划的规范化规则，以确定需要哪个租户拨号计划规范化规则。 **Get-CsEffectiveTenantDialPlan** cmdlet 可用于此用途。 该 cmdlet 以用户标识作为输入参数，并将所有适用的规范化规则都返回给用户。

### <a name="creating-normalization-rules"></a>创建规范化规则
<a name="createrule"> </a>

规范化规则.NET Framework正则表达式来指定服务器用来将拨号字符串转换为 E.164 格式的数字匹配模式。 可以通过指定在找到匹配项时要执行的匹配和转换的正则表达式来创建规范化规则。 完成之后，你可以输入一个测试号码以验证规范化规则是否可按预期工作。

有关使用正则表达式.NET Framework，请参阅.NET Framework[正则表达式"。](/dotnet/standard/base-types/regular-expressions)

请参阅 [创建和管理拨号计划](create-and-manage-dial-plans.md) ，以创建和管理租户拨号计划的规范化规则。

> [!NOTE]
> 3pip 设备目前不支持将第一个令牌作为可选标记的规范化规则 (例如 Polycom VVX 601 模型) 。 如果要在 3pip 设备上应用具有可选属性的规范化规则，应创建两个规范化规则而不是一个规范化规则。 例如，规则 ^0？ (999) $ 应替换为以下两个规则： (999) $ (Translation：$1) 和 ^0 (999) $ (Translation：$1) 。


### <a name="sample-normalization-rules"></a>示例规范化规则

下表显示以 .NET Framework 正则表达式形式编写的示例规范化规则。这些示例仅用作示例，不用作创建规范化规则的规范性参考。

<a name="regularexpression"></a> 
 **使用正则表达式.NET Framework规范化规则**

| 规则名称<br/> | 描述<br/> | 号码模式<br/> | 转换<br/> | 示例<br/> |
|:-----|:-----|:-----|:-----|:-----|
|4digitExtension  <br/> |转换 4 位数分机号。  <br/> |^(\\d{4})$  <br/> |+1425555$1  <br/> |将 0100 转换为 +14255550100  <br/> |
|5digitExtension  <br/> |转换 5 位数分机号。  <br/> |^5(\\d{4})$  <br/> |+1425555$1  <br/> |将 50100 转换为 +14255550100  <br/> |
|7digitcallingRedmond  <br/> |将 7 位数号码转换为雷德蒙德本地号码。  <br/> |^(\\d{7})$  <br/> |+1425$1  <br/> |将 5550100 转换为 +14255550100  <br/>|
|RedmondOperator  <br/> |将 0 转换为雷德蒙德话务员。  <br/> |^0$  <br/> |+14255550100  <br/> |将 0 转换为 +14255550100  <br/> |
|RedmondSitePrefix  <br/> |转换带有网内前缀 (6) 和雷德蒙德站点代码 (222) 的号码。  <br/> |^6222(\\d{4})$  <br/> |+1425555$1  <br/> |将 62220100 转换为 +14255550100  <br/> |
|5digitRange  <br/> |转换以 3-7（含 3 和 7）之间的数字开头的 5 位数分机号。  <br/> |^([3-7]\\d{4})$  <br/> |+142555$1 <br/> |将 54567 转换为 +14255554567  <br/> |
|PrefixAdded  <br/> |在对第一位和第三位数字有限制的 9 位数号码前添加国家/地区前缀。  <br/> |^([2-9]\\d\\d[2-9]\\d{6})$  <br/> |1$1  <br/> |将 4255554567 转换为 14255554567  <br/> |
|NoTranslation  <br/> |匹配 5 位数，但不转换。  <br/> |^(\\d{5})$  <br/> |$1  <br/> |将 34567 转换为 34567  <br/> |

 **上面显示了基于规范化规则的雷德蒙德拨号计划。**

 下表根据上表显示的规范化规则对用于雷德蒙德、华盛顿、美国的示例拨号计划进行说明。

| 雷德蒙德拨号计划<br/> |
|:-----------------------|                                                                                                                      
| 5digitExtension <br/> |                                                                                                                                    
| 7digitcallingRedmond <br/> |
| RedmondSitePrefix <br/> |
| RedmondOperator <br/> |

> [!NOTE]
> 上表中显示的规范化规则名称不包括空格，但这是一种选择。 例如，该表中的第一个名称，本应写成"5 digit extension"或"5-digit Extension"，但它仍然有效。

## <a name="related-topics"></a>相关主题

[创建并管理拨号计划](create-and-manage-dial-plans.md)

[用于通话套餐的不同类型的电话号码](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[管理你的组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[紧急呼叫条款和条件](emergency-calling-terms-and-conditions.md)

[紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
