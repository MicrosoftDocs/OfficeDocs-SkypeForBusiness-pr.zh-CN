---
title: 'Lync Server 2013: 拨号计划和规范化规则'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Dial plans and normalization rules
ms:assetid: fde45195-6eb4-403c-9094-57df7fc0bd2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413082(v=OCS.15)
ms:contentKeyID: 48185960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5d399c49db109a7bac1a1cd3ac430280cb70f665
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830420"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dial-plans-and-normalization-rules-in-lync-server-2013"></a>Lync Server 2013 中的拨号计划和规范化规则

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-09-21_

拨号计划是一组指定的规范化规则，可将指定位置、单个用户或联系人对象的电话号码转换为统一标准 (E.164) 格式，以进行电话授权和呼叫路由。

规范化规则定义如何针对每个指定的位置、用户或联系人对象来路由以不同格式表示的电话号码。同一拨号串的解析和转换可能不同，具体取决于拨打该号码的位置，以及发出呼叫的人员或联系人对象。

<div>

## <a name="dial-plan-scope"></a>拨号计划作用域

拨号计划的*范围*决定了拨号计划的应用层级。 在 Lync Server 中, 可以为用户分配特定的每个用户的拨号计划。 如果未分配用户拨号计划, 则应用注册机构池拨号计划。 如果没有注册机构池拨号计划, 则应用网站拨号计划。 最后，如果没有其他适用于该用户的拨号计划，则会应用全局拨号计划。

客户通过在用户登录到 Lync Server 时提供的带内配置设置来获取拨号计划范围级别。 作为管理员, 你可以使用 Lync Server 控制面板管理和分配拨号计划范围级别。

<div>


> [!NOTE]  
> 服务级别公用电话交换网 (PSTN) 网关拨号计划应用于来自特定网关的传入呼叫。



</div>

拨号计划作用域级别定义如下：

  - **用户拨号计划:** 可以分配给单个用户、组或联系人对象。 当接收到其为用户默认的电话上下文设置的呼叫时，语音应用程序可查找每用户拨号计划。 为便于分配拨号计划，将联系人对象视为单个用户。

  - **池拨号计划:** 可在拓扑中的任何 PSTN 网关或注册机构的服务级别创建。 要定义池拨号计划，必须指定要应用拨号计划的特定服务（PSTN 网关或注册器池）。

  - **网站拨号计划:** 可为整个网站创建, 除了分配有池拨号计划或用户拨号计划的任何用户、组或联系人对象之外。 要定义站点拨号计划，必须指定要应用拨号计划的站点。

  - **全局拨号计划:** 随产品一起安装的默认拨号计划。 可以编辑全局拨号计划，但无法将其删除。 此拨号计划适用于部署中的所有企业语音用户、组和联系人对象, 除非你使用更具体的作用域配置和分配拨号计划。

</div>

<div>

## <a name="planning-for-dial-plans"></a>规划拨号计划

要规划拨号计划，请执行下列步骤：

  - 列出贵组织拥有办事处的全部区域设置。
    
    该列表必须是最新且完整的。随着公司的发展，将需要对该列表进行修订。在拥有许多小型分支机构的大型跨国公司中，这可能会是一个非常耗时的任务。

  - 标识每个站点的有效号码模式。
    
    在规划拨号计划时，最耗时的任务就是确定每个站点的有效号码模式。在某些情况下，尤其是当相应站点位于同一个国家/地区甚至同一个大陆上时，可以将为一个拨号计划编写的规范化规则复制到其他拨号计划中。在另一些情况下，只需对一个拨号计划中的号码进行微小的更改即可将这些号码用于其他拨号计划。

  - 制定组织级别的方案来命名拨号计划。
    
    实行标准命名方案可确保组织内的一致性，并使维护和更新更加容易。

  - 确定单个位置是否需要多个拨号计划。
    
    如果你的组织在多个位置维护单个拨号计划, 你可能仍然需要为从专用分支 exchange (PBX) 迁移的企业语音用户创建单独的拨号计划, 以及哪些用户需要保留其现有的扩展。

  - 确定是否需要每用户拨号计划。 例如, 如果分支站点上有用户已向中心网站注册, 或者如果你拥有在 Survivable 分支设备上注册的用户, 则可以考虑使用每个用户的拨号计划和规范化规则为此类用户进行特殊的拨号方案. 有关详细信息, 请参阅[Lync Server 2013 的分支站点恢复要求](lync-server-2013-branch-site-resiliency-requirements.md)。

  - 确定拨号计划作用域（如本主题上文所述）。

若要创建拨号计划, 请根据需要在以下字段中指定值, 方法是使用 Lync Server 控制面板或 Lync Server 命令行管理程序。

<div>

## <a name="name-and-simple-name"></a>名称和简单名称

对于用户拨号计划，应指定描述性名称，以标识要为其分配拨号计划的用户、组或联系人对象。 对于网站拨号计划, "名称" 字段已预填充网站名称, 不能更改。 对于池拨号计划, "名称" 字段预填充了 PSTN 网关或前端池完全限定的域名 (FQDN), 并且无法更改。

使用从拨号计划名称派生的字符串预填充拨号计划的*简单名称*。 “简单名称”字段是可编辑的，从而使您可以为拨号计划创建更具描述性的命名约定。 “*简单名称*”值不能为空，且必须是唯一的。 最佳实践是为整个组织制定一个命名约定，然后在所有站点和用户中统一使用此约定。

</div>

<div>

## <a name="description"></a>描述

建议您键入一个要应用相应的拨号计划的通用可辨识地理位置名称。例如，如果拨号计划的名称是 London.Contoso.com，则建议的说明将为 London。

</div>

<div>

## <a name="dial-in-conferencing-region"></a>电话拨入式会议区域

如果要部署电话拨入式会议，则需要指定电话拨入式会议区域，以将电话拨入式会议访问号码与拨号计划关联起来。

</div>

<div>

## <a name="external-access-prefix"></a>外部访问前缀

如果用户需要拨一个或多个附加前导数字 (例如\#, \*9) 以获取外部线路, 则可以指定最多四个字符 (、和 0-9) 的外部访问前缀。

<div>


> [!NOTE]  
> 如果指定了外部访问前缀，则不需要另外创建规范化规则来满足前缀。



</div>

</div>

</div>

<div>

## <a name="normalization-rules"></a>规范化规则

规范化规则定义如何针对命名的位置来路由以不同格式表示的电话号码。同一号码字符串的解析和转换方式可能不同，具体取决于拨打该号码的场所。规范化规则是呼叫路由所必需的，因为用户在其联系人列表中输入电话号码时，可以而且确实会使用各种格式。

对用户提供的电话号码进行规范化可以提供一致的格式，从而便于执行以下任务：

  - 将所拨打的号码与预期收件人的 SIP-URI 相匹配。

  - 对呼叫者应用拨号授权规则。

规范化规则可能需要考虑下列号码字段：

  - 拨号计划

  - 国家/地区代码

  - 区号

  - 分机号长度

  - 站点前缀

<div>

## <a name="creating-normalization-rules"></a>创建规范化规则

规范化规则使用 .NET Framework 正则表达式指定数字匹配模式，服务器使用该模式将拨号串转换为 E.164 格式，以便执行反向号码查找。 你可以在 Lync Server 控制面板中创建规范化规则, 方法是手动输入表达式, 或者输入起始位数和要匹配的拨号字符串的长度, 让 Lync Server 控制面板生成相应的正则表达式。 无论采用何种方式，完成操作后，都可以输入一个测试号码来验证规范化规则能否按预期工作。

有关使用 .NET Framework 正则表达式的详细信息, 请参阅的[http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927)".Net Framework 正则表达式"。

</div>

<span id="BKMK_SampleNormalizationRules"></span>

<div>

## <a name="sample-normalization-rules"></a>规范化规则示例

下表显示以 .NET Framework 正则表达式编写的规范化规则示例。这些仅为示例，不应作为创建自己的规范化规则时的规定性参考。

### <a name="table-1normalization-rules-using-net-framework-regular-expressions"></a>表 1. 使用 .NET Framework 正则表达式的规范化规则

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
<th>规则名称</th>
<th>说明</th>
<th>号码模式</th>
<th>转换</th>
<th>示例</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>4digitExtension</p></td>
<td><p>转换 4 位分机号</p></td>
<td><p>^ (\d{4}) $</p></td>
<td><p>+1425555$1</p></td>
<td><p>将 0100 转换为 +14255550100</p></td>
</tr>
<tr class="even">
<td><p>5digitExtension</p></td>
<td><p>转换 5 位分机号</p></td>
<td><p>^ 5 (\d{4}) $</p></td>
<td><p>+1425555$1</p></td>
<td><p>将 50100 转换为 +14255550100</p></td>
</tr>
<tr class="odd">
<td><p>7digitcallingRedmond</p></td>
<td><p>将 7 位号码转换为雷德蒙德本地号码</p></td>
<td><p>^ (\d{7}) $</p></td>
<td><p>+1425$1</p></td>
<td><p>将 5550100 转换为 +14255550100</p></td>
</tr>
<tr class="even">
<td><p>7digitcallingDallas</p></td>
<td><p>将 7 位号码转换为达拉斯本地号码</p></td>
<td><p>^ (\d{7}) $</p></td>
<td><p>+1972$1</p></td>
<td><p>将 5550100 转换为 +19725550100</p></td>
</tr>
<tr class="odd">
<td><p>10digitcallingUS</p></td>
<td><p>转换美国的 10 位号码</p></td>
<td><p>^ (\d{10}) $</p></td>
<td><p>+1$1</p></td>
<td><p>将 2065550100 转换为 +12065550100</p></td>
</tr>
<tr class="even">
<td><p>LDCallingUS</p></td>
<td><p>用美国的长途前缀转换号码</p></td>
<td><p>^ 1 (\d{10}) $</p></td>
<td><p>+$1</p></td>
<td><p>将 12145550100 转换为 +2145550100</p></td>
</tr>
<tr class="odd">
<td><p>IntlCallingUS</p></td>
<td><p>用美国的国际前缀转换号码</p></td>
<td><p>^011(\d*)$</p></td>
<td><p>+$1</p></td>
<td><p>将 01191445550100 转换为 +91445550100</p></td>
</tr>
<tr class="even">
<td><p>RedmondOperator</p></td>
<td><p>将 0 转换为雷德蒙德号码</p></td>
<td><p>^0$</p></td>
<td><p>+14255550100</p></td>
<td><p>将 0 转换为 +14255550100</p></td>
</tr>
<tr class="odd">
<td><p>RedmondSitePrefix</p></td>
<td><p>用网内前缀 (6) 和雷德蒙德站点代码 (222) 转换号码</p></td>
<td><p>^ 6222 (\d{4}) $</p></td>
<td><p>+1425555$1</p></td>
<td><p>将 62220100 转换为 +14255550100</p></td>
</tr>
<tr class="even">
<td><p>NYSitePrefix</p></td>
<td><p>用网内前缀 (6) 和纽约站点代码 (333) 转换号码</p></td>
<td><p>^ 6333 (\d{4}) $</p></td>
<td><p>+1202555$1</p></td>
<td><p>将 63330100 转换为 +12025550100</p></td>
</tr>
<tr class="odd">
<td><p>DallasSitePrefix</p></td>
<td><p>用网内前缀 (6) 和达拉斯站点代码 (444) 转换号码</p></td>
<td><p>^ 6444 (\d{4}) $</p></td>
<td><p>+1972555$1</p></td>
<td><p>将 64440100 转换为 +19725550100</p></td>
</tr>
</tbody>
</table>


下表基于上表中显示的规范化规则，说明了美国华盛顿雷德蒙德的示例拨号计划。

### <a name="table-2-redmond-dial-plan-based-on-normalization-rules-shown-in-table-1"></a>表 2. 基于表 1 中所示规范化规则的雷德蒙德拨号计划

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th>Redmond.forestFQDN</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>5digitExtension</p></td>
</tr>
<tr class="even">
<td><p>7digitcallingRedmond</p></td>
</tr>
<tr class="odd">
<td><p>10digitcallingUS</p></td>
</tr>
<tr class="even">
<td><p>IntlCallingUS</p></td>
</tr>
<tr class="odd">
<td><p>RedmondSitePrefix</p></td>
</tr>
<tr class="even">
<td><p>NYSitePrefix</p></td>
</tr>
<tr class="odd">
<td><p>DallasSitePrefix</p></td>
</tr>
<tr class="even">
<td><p>RedmondOperator</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> [!注释] 上表中所示的规范化规则名称不包含空格，你可以选择是否要包含。例如，该表中的第一个名称，本应写成"5 digit extension"或"5-digit Extension"，但它仍然有效。



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

