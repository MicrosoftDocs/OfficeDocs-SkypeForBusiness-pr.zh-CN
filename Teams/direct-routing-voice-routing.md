---
title: 为直接路由配置呼叫路由
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 了解如何使用 Microsoft 直接路由配置呼叫路由。
ms.openlocfilehash: a7f80a71aa83e255efe81b82ce57026ed0749165
ms.sourcegitcommit: 507e186972bcbc56c1547a1b9f357bfd38170b5a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/27/2022
ms.locfileid: "68046662"
---
# <a name="configure-call-routing-for-direct-routing"></a>为直接路由配置呼叫路由

本文介绍如何为直接路由配置呼叫路由。 这是配置直接路由的以下步骤的第 3 步：

- 第 1 步 [将 SBC 与 Microsoft Phone 系统连接并验证连接](direct-routing-connect-the-sbc.md) 
- 第 2 步 [为用户启用直接路由、语音和语音邮件](direct-routing-enable-users.md)
- **步骤 3.配置呼叫路由** (本文) 
- 第 4 步 [将数字转换为备用格式](direct-routing-translate-numbers.md) 

有关设置直接路由所需的所有步骤的信息，请参阅 [配置直接路由](direct-routing-configure.md)。

## <a name="call-routing-overview"></a>呼叫路由概述

Microsoft 电话系统有一个路由机制，允许基于以下情况将呼叫发送到特定会话边界控制器 (SBC) ： 

- 调用的数字模式 
- 调用的号码模式加上进行呼叫的特定用户
 
SBC 可以指定为活动和备份。 当配置为活动状态的 SBC 不可用于特定的调用路由时，调用将路由到备份 SBC。
 
呼叫路由由以下元素组成： 

- **呼叫路由策略** – 也称为语音路由策略。 PSTN 使用情况的容器，可分配给用户或多个用户。 

- **PSTN 用法** - 语音路由和 PSTN 用法的容器，可在不同的语音路由策略中共享。 

- **语音路由** - 用于调用号码与模式匹配的呼叫的数字模式和联机 PSTN 网关集。

- **联机 PSTN 网关** - 指向 SBC 的指针，该指针还存储通过 SBC 进行调用时应用的配置，例如转发 P-Asserted-Identity (PAI) 或首选编解码器;可以添加到语音路由。

## <a name="voice-routing-policy-considerations"></a>语音路由策略注意事项

如果用户具有呼叫计划许可证，则该用户的传出呼叫会自动通过 Microsoft 呼叫计划 PSTN 基础结构路由。 如果配置联机语音路由策略并将其分配给呼叫计划用户，则会检查该用户的传出呼叫，以确定拨号号码是否与联机语音路由策略中定义的数字模式匹配。 如果存在匹配项，则通过直接路由中继路由调用。 如果没有匹配项，则通过呼叫计划 PSTN 基础结构路由调用。

> [!CAUTION]
> 如果配置并应用全局 (组织范围内的默认) 联机语音路由策略，组织中所有启用语音的用户都将继承该策略，这可能会导致呼叫计划和运算符连接用户的 PSTN 呼叫无意中路由到直接路由中继。 如果不希望所有用户都使用全局联机语音路由策略，请配置自定义联机语音路由策略并将其分配给单个启用语音的用户。

## <a name="example-1-voice-routing-with-one-pstn-usage"></a>示例 1：使用一个 PSTN 的语音路由

下图显示了呼叫流中语音路由策略的两个示例。

**左侧的呼叫流 1 () ：** 如果用户调用 +1 425 XXX XX XX 或 +1 206 XXX XX XX，则调用将路由到 SBC sbc1.contoso.biz 或 sbc2.contoso.biz。 如果 sbc1.contoso.biz 和 sbc2.contoso.biz 都不可用，则会删除调用。 

**右侧的调用流 2 () ：** 如果用户调用 +1 425 XXX XX XX 或 +1 206 XXX XX，则调用将首先路由到 SBC sbc1.contoso.biz 或 sbc2.contoso.biz。 如果两个 SBC 都不可用，则将尝试优先级较低的路由 (sbc3.contoso.biz 和 sbc4.contoso.biz) 。 如果没有可用的 SBC，则会删除调用。 

![显示语音路由策略示例。](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

在这两个示例中，分配语音路由优先级时，将随机尝试路由中的 SBC。

  > [!NOTE]
  > 除非用户还具有 Microsoft 呼叫计划许可证，否则将删除对任何号码的调用，但与示例配置中的模式 +1 425 XXX XX XX 或 +1 206 XXX XX XX 匹配的数字除外。 如果用户具有呼叫计划许可证，则会根据 Microsoft 呼叫计划的策略自动路由呼叫。 Microsoft 呼叫计划自动应用为所有拥有 Microsoft 呼叫计划许可证的用户的最后一个路由，不需要其他呼叫路由配置。

在下图所示的示例中，添加了一个语音路由，用于向调用号码模式 +1 XXX XXX XX XX) 的调用发送对所有其他美国和加拿大号码的呼叫 (。

![显示带有第三个路由的语音路由策略。](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

对于所有其他呼叫，如果用户 (Microsoft Phone System 和 Microsoft 呼叫计划) 同时拥有许可证，则使用自动路由。 如果没有任何内容与管理员创建的联机语音路由中的号码模式匹配，则通过 Microsoft 呼叫计划路由呼叫。 如果用户只有 Microsoft Phone 系统，则会因为没有可用的匹配规则而放弃呼叫。

  > [!NOTE]
  > 在这种情况下，路由“其他 +1”的优先级值并不重要，因为只有一个路由与模式 +1 XXX XXX XX XX 匹配。 如果用户调用 +1 324 567 89 89，并且 sbc5.contoso.biz 和 sbc6.contoso.biz 都不可用，则调用将删除。

下表总结了使用三个语音路由的配置。 在此示例中，所有三个路由都是相同 PSTN 使用情况“美国和加拿大”的一部分。  所有路由都与“美国和加拿大”PSTN 使用情况相关联，PSTN 使用率与“仅限美国”语音路由策略相关联。

|**PSTN 用法**|**语音路由**|**号码模式**|**优先级**|**Sbc**|**说明**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|美国和加拿大|“Redmond 1”|^\\+1 (425\|206)  (\d{7}) $|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|调用数字的活动路由 +1 425 XXX XX XX 或 +1 206 XXX XX XX|
|美国和加拿大|“Redmond 2”|^\\+1 (425\|206)  (\d{7}) $|2|sbc3.contoso.biz<br/>sbc4.contoso.biz|调用数字 +1 425 XXX XX XX 或 +1 206 XXX XX XX 的备份路由|
|美国和加拿大|“其他 +1”|^\\+1 (\d{10}) $|3|sbc5.contoso.biz<br/>sbc6.contoso.biz|除 +1 425 XXX XX XX 或 +1 206 XXX XX XX (外，调用数字 +1 XXX XX XX XX 的路由) |
|||||||

## <a name="example-1-configuration-steps"></a>示例 1：配置步骤

以下示例演示如何：

1. 创建单个 PSTN 使用情况。
2. 配置三个语音路由。
3. 创建语音路由策略。
4. 将策略分配给名为 Spencer Low 的用户。

可以使用 [Microsoft Teams 管理中心](#admincenterexample1) 或 [PowerShell](#powershellexample1) 执行这些步骤。

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心
<a name="admincenterexample1"></a>

#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a>步骤 1：创建“美国和加拿大”PSTN 使用情况

1. 在 Microsoft Teams 管理中心的左侧导航中，转到 **语音** > **直接路由**，然后在右上角选择 **“管理 PSTN 使用情况记录**”。
2. 单击 **“添加**”，键入 **“美国和加拿大**”，然后单击“ **应用**”。

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a>步骤 2： (Redmond 1、Redmond 2 和其他 +1) 创建三个语音路由

以下步骤介绍如何创建语音路由。 使用这些步骤使用前面表中所述的设置，为此示例创建名为 Redmond 1、Redmond 2 和其他 +1 的三个语音路由。

1. 在 Microsoft Teams 管理中心的左侧导航中，转到 **语音** > **直接路由**，然后选择 **“语音路由** ”选项卡。
2. 单击 **“添加**”，然后输入语音路由的名称和说明。
3. 设置优先级并指定拨号号码模式。
4. 若要使用语音路由注册 SBC，请在 **注册 (可选) 的 SBC** 下，单击 **“添加 SBC”**，选择要注册的 SBC，然后单击“ **应用**”。
5. 若要添加 PSTN 使用情况记录， **请在 PSTN 使用情况记录 (可选)** 下，单击 **“添加 PSTN 使用情况**”，选择要添加的 PSTN 记录，然后单击“ **应用**”。
6. 单击“**保存**”。

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a>步骤 3：创建名为“仅限美国”的语音路由策略，并将“美国和加拿大”PSTN 使用情况添加到策略

1. 在 Microsoft Teams 管理中心的左侧导航中，转到 **语音** > **路由策略**，然后单击 **“添加**”。
2. **键入“仅美国**”作为名称并添加说明。
3. 在 **PSTN 使用情况记录** 下，单击 **“添加 PSTN 使用情况**”，选择“美国和加拿大”PSTN 使用情况记录，然后单击“ **应用**”。
4. 单击“**保存**”。

若要了解详细信息，请参阅 [“管理语音路由策略](manage-voice-routing-policies.md)”。

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a>步骤 4：将语音路由策略分配给名为 Spencer Low 的用户

1. 在 Microsoft Teams 管理员中心的左侧导航中，转到“用户”，然后单击相应的用户。
2. 单击 **“策略**”，然后在 **“分配的策略**”旁边单击 **“编辑**”。
3. 在 **语音路由策略** 下，选择“仅限美国”策略，然后单击“ **保存**”。

若要了解详细信息，请参阅 [“管理语音路由策略](manage-voice-routing-policies.md)”。

### <a name="using-powershell"></a>使用 PowerShell
<a name="powershellexample1"></a>


#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a>步骤 1：创建“美国和加拿大”PSTN 使用情况

在 Skype for Business Online 的远程 PowerShell 会话中，键入：

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

输入以下内容验证是否已创建使用情况：

```PowerShell
Get-CSOnlinePSTNUsage
``` 

这会返回可能被截断的名称列表：

```console
Identity    : Global
Usage        : {testusage, US and Canada, International, karlUsage. . .}
```

下面的示例演示运行 `(Get-CSOnlinePSTNUsage).usage` PowerShell 命令以显示全名 (未截断) 的结果：

```console
 testusage
 US and Canada
 International
 karlUsage
 New test env
 Tallinn Lab Sonus
 karlUsage2
 Unrestricted
 Two trunks
```

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a>步骤 2： (Redmond 1、Redmond 2 和其他 +1) 创建三个语音路由

若要创建“Redmond 1”路由，请在 Skype for Business Online 的 PowerShell 会话中输入：

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

这将返回：

```console
Identity                : Redmond 1
Priority                : 1
Description             :
NumberPattern           : ^\+1(425|206) (\d{7})$
OnlinePstnUsages        : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name                    : Redmond 1
```

若要创建 Redmond 2 路由，请输入：

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

若要创建其他 +1 路由，请输入：

```PowerShell
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > 确保 NumberPattern 属性中的正则表达式是有效的表达式。 可以使用以下网站对其进行测试： [https://www.regexpal.com](https://www.regexpal.com)

在某些情况下，需要将所有调用路由到同一 SBC;use -NumberPattern “.*”

将所有调用路由到同一 SBC。

```PowerShell
Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz
```

使用以下选项运行 `Get-CSOnlineVoiceRoute` PowerShell 命令，验证是否已正确配置路由：

```PowerShell
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
应返回：

```console
Identity            : Redmond 1 
Priority               : 1
Description         : 
NumberPattern         : ^\+1(425|206) (\d{7})$
OnlinePstnUsages     : {US and Canada}     
OnlinePstnGatewayList    : {sbc1.contoso.biz, sbc2.contoso.biz}
Name             : Redmond 1
Identity        : Redmond 2 
Priority               : 2
Description         : 
NumberPattern         : ^\+1(425|206) (\d{7})$
OnlinePstnUsages     : {US and Canada}     
OnlinePstnGatewayList    : {sbc3.contoso.biz, sbc4.contoso.biz}
Name             : Redmond 2
    
Identity        : Other +1 
Priority               : 4
Description         : 
NumberPattern         : ^\+1(\d{10})$
OnlinePstnUsages     : {US and Canada}     
OnlinePstnGatewayList    : {sbc5.contoso.biz, sbc6.contoso.biz}
Name             : Other +1
```

在该示例中，路由“其他 +1”自动分配优先级 4。 

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a>步骤 3：创建名为“仅限美国”的语音路由策略，并将“美国和加拿大”PSTN 使用情况添加到策略

在 Skype for Business Online 的 PowerShell 会话中，键入：

```PowerShell
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

此示例中显示了此结果：

```console
Identity            : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
```

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a>步骤 4：将语音路由策略分配给名为 Spencer Low 的用户

在 Skype for Business Online 的 PowerShell 会话中，键入：

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"
```

输入以下命令验证策略分配：

```PowerShell
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```

该命令返回以下内容：

```console
OnlineVoiceRoutingPolicy
---------------------
US Only
```

## <a name="example-2-voice-routing-with-multiple-pstn-usages"></a>示例 2：具有多个 PSTN 用法的语音路由

示例 1 中创建的语音路由策略仅允许拨打美国和加拿大的电话号码，除非 Microsoft 呼叫计划许可证也分配给用户。

在下面的示例中，可以创建“无限制”语音路由策略。 该策略重复使用示例 1 中创建的“美国和加拿大”PSTN 使用情况，以及新的“国际”PSTN 使用情况。 此策略将所有其他调用路由到 SBC sbc2.contoso.biz 和 sbc5.contoso.biz。

显示的示例将“仅限美国”策略分配给用户 Spencer Low，并将“无限制”策略分配给用户 John Woods，以便路由按如下所示进行：

- 斯宾塞低 - 美国唯一的政策。  仅允许拨打美国和加拿大号码。 调用 Redmond 号码范围时，必须使用特定的 SBC 集。 除非将呼叫计划许可证分配给用户，否则不会路由非美国号码。

- 约翰·伍兹 – 国际政策。  允许调用任何号码。 调用 Redmond 号码范围时，必须使用特定的 SBC 集。 将使用 sbc2.contoso.biz 和 sbc5.contoso.biz 路由非美国数字。

![显示分配给用户 Spencer Low 的语音路由策略。](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

对于所有其他呼叫，如果用户同时拥有 Microsoft 电话系统 (和 Microsoft 呼叫计划) 的许可证，则使用自动路由。 如果与管理员创建的联机语音路由中的号码模式不匹配，则使用 Microsoft 呼叫计划路由呼叫。  如果用户只有 Microsoft Phone 系统，则呼叫会被删除，因为没有可用的匹配规则。

![显示分配给用户 John Woods 的语音路由策略。](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

下表汇总了路由策略“无限制”使用指定和语音路由。 

| PSTN 用法 | 语音路由 | 号码模式 | 优先级 | Sbc | 说明 |
|:-----|:-----|:-----|:-----|:-----|:-----|
|美国和加拿大|“Redmond 1”|^\\+1 (425\|206)  (\d{7}) $|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|被调用方号码的活动路由 +1 425 XXX XX XX 或 +1 206 XXX XX XX|
|美国和加拿大|“Redmond 2”|^\\+1 (425\|206)  (\d{7}) $|2|sbc3.contoso.biz<br/>sbc4.contoso.biz|被调用方号码 +1 425 XXX XX XX 或 +1 206 XXX XX XX 的备份路由|
|美国和加拿大|“其他 +1”|^\\+1 (\d{10}) $|3|sbc5.contoso.biz<br/>sbc6.contoso.biz|被调用方号码 +1 XXX XXX XX XX (的路由，但 +1 425 XXX XX XX 或 +1 206 XXX XX XX) |
|International|International|\d+|4|sbc2.contoso.biz<br/>sbc5.contoso.biz|任意数字模式的路由 |

  > [!NOTE]
  > - 语音路由策略中的 PSTN 使用顺序至关重要。 使用情况按顺序应用，如果在第一个用法中找到匹配项，则不会评估其他用法。 “国际”PSTN 使用量必须放在“美国和加拿大”PSTN 使用情况之后。 若要更改 PSTN 使用情况的顺序，请运行该 `Set-CSOnlineVoiceRoutingPolicy` 命令。 <br/>例如，若要将订单从“美国和加拿大”第一和“国际”第二更改为反向订单运行：<br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - 自动分配“其他 +1”和“国际”语音路由的优先级。 只要他们的优先级低于 “雷德蒙德 1” 和 “雷德蒙德 2”， 它们并不重要。

## <a name="example-2-configuration-steps"></a>示例 2：配置步骤

以下示例演示如何：

1. 创建名为“国际”的新 PSTN 用法。
2. 创建名为“国际”的新语音路由。
3. 创建名为“无限制”的语音路由策略。
4. 将策略分配给用户 John Woods。

可以使用 [Microsoft Teams 管理中心](#admincenterexample2) 或 [PowerShell](#powershellexample2) 执行这些步骤。

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心
<a name="admincenterexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a>步骤 1：创建“国际”PSTN 使用情况

1. 在 Microsoft Teams 管理中心的左侧导航中，转到 **语音** > **直接路由**，然后在右上角选择 **“管理 PSTN 使用情况记录**”。
2. 单击 **“添加**”，键入 **“国际**”，然后单击“ **应用**”。

#### <a name="step-2-create-the-international-voice-route"></a>步骤 2：创建“国际”语音路由

1. 在 Microsoft Teams 管理中心的左侧导航中，转到 **语音** > **直接路由**，然后选择 **“语音路由** ”选项卡。
2. 单击 **“添加**”，输入“International”作为名称，然后添加说明。
3. 将优先级设置为 4，然后将拨号号码模式设置为 \d+。
4. 在 **注册 (可选) 的 SBC** 下，单击 **“添加 SBC”**，选择 sbc2.contoso.biz 并 sbc5.contoso.biz，然后单击“ **应用**”。
5. 在 **PSTN 使用情况记录 (可选)** 下，单击 **“添加 PSTN 使用情况**”，选择“国际”PSTN 使用情况记录，然后单击“ **应用**”。
6. 单击“**保存**”。

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions-and-add-the-us-and-canada-and-international-pstn-usages-to-the-policy"></a>步骤 3：创建名为“无限制”的语音路由策略，并将“美国和加拿大”和“国际”PSTN 使用情况添加到策略

此语音路由策略中重复使用 PSTN 使用情况“US and Canada”，以保留对号码“+1 425 XXX XX XX”和“+1 206 XXX XX XX”作为本地或本地调用的呼叫的特殊处理。

1. 在 Microsoft Teams 管理中心的左侧导航中，转到 **语音** > **路由策略**，然后单击 **“添加**”。
2. 键入 **“无限制** ”作为名称并添加说明。
3. 在 **PSTN 使用情况记录** 下，单击 **“添加 PSTN 使用情况**”，选择“美国和加拿大”PSTN 使用情况记录，然后选择“国际”PSTN 使用情况记录。 单击“**应用**”。

    记下 PSTN 使用情况的顺序：

    - 如果调用的号码“+1 425 XXX XX XX”的使用情况已配置为本示例中所示，则调用遵循“美国和加拿大”使用情况中设置的路由，并应用特殊路由逻辑。 也就是说，调用先使用 sbc1.contoso.biz 路由并 sbc2.contoso.biz，然后 sbc3.contoso.biz 并 sbc4.contoso.biz 作为备份路由。

    - 如果“国际”PSTN 使用率位于“美国和加拿大”之前，则对 +1 425 XXX XX XX 的调用将路由到 sbc2.contoso.biz，并在路由逻辑中 sbc5.contoso.biz。

4. 单击“**保存**”。

若要了解详细信息，请参阅 [“管理语音路由策略](manage-voice-routing-policies.md)”。

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-john-woods"></a>步骤 4：将语音路由策略分配给名为 John Woods 的用户

1. 在 Microsoft Teams 管理员中心的左侧导航中，转到“用户”，然后单击相应的用户。
2. 单击 **“策略**”，然后在 **“分配的策略**”旁边单击 **“编辑**”。
3. 在 **语音路由策略** 下，选择“无限制”策略，然后单击“ **保存**”。

结果是，适用于约翰·伍兹通话的语音政策不受限制，将遵循美国、加拿大和国际通话的呼叫路由逻辑。

### <a name="using-powershell"></a>使用 PowerShell
<a name="powershellexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a>步骤 1：创建“国际”PSTN 使用情况

在 Skype for Business Online 的远程 PowerShell 会话中，输入：

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

#### <a name="step-2--create-a-new-voice-route-named-international"></a>步骤 2：创建名为“International”的新语音路由

```PowerShell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
```

这将返回：

```console
Identity                  : International
Priority                  : 5
Description               :
NumberPattern             : .*
OnlinePstnUsages          : {International}
OnlinePstnGatewayList     : {sbc2.contoso.biz, sbc5.contoso.biz}
Name                      : International
```

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions"></a>步骤 3：创建名为“无限制”的语音路由策略

此语音路由策略中重复使用 PSTN 用法“Redmond 1”和“Redmond”，以保留对呼叫号码“+1 425 XXX XX XX”和“+1 206 XXX XX XX”作为本地或本地呼叫的特殊处理。

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

记下 PSTN 使用情况的顺序：

  - 如果调用的号码“+1 425 XXX XX XX”的使用情况配置如下例所示，则调用遵循“美国和加拿大”使用情况中设置的路由，并应用特殊路由逻辑。 也就是说，调用先使用 sbc1.contoso.biz 路由并 sbc2.contoso.biz，然后 sbc3.contoso.biz 并 sbc4.contoso.biz 作为备份路由。

  - 如果“国际”PSTN 使用率位于“美国和加拿大”之前，则对 +1 425 XXX XX XX 的调用将路由到 sbc2.contoso.biz，并在路由逻辑中 sbc5.contoso.biz。 输入命令：

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

这将返回：

```console
    Identity              : International 
    OnlinePstnUsages : {US and Canada, International}     
    Description         :  
    RouteType               : BYOT
```

#### <a name="step-4-assign-the-voice-routing-policy-to-the-user-named-john-woods"></a>步骤 4：将语音路由策略分配给名为 John Woods 的用户

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions"
```

然后使用命令验证分配： 

```PowerShell
Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
```

这将返回：

```console
OnlineVoiceRoutingPolicy
------------------------
No Restrictions
```

结果是，适用于约翰·伍兹通话的语音政策不受限制，将遵循美国、加拿大和国际通话的呼叫路由逻辑。

## <a name="run-a-self-diagnostics-tool"></a>运行自我诊断工具

Microsoft 365 管理员用户有权访问可在租户中运行的诊断，以验证用户是否正确配置了直接路由。 

> [!NOTE]
>此功能不适用于 Microsoft 365 政府版、由世纪互联运营的 Microsoft 365版或 Microsoft 365 德国版。

选择“运行测试”，如下所示。 这会在Microsoft 365 管理中心填充诊断。
>> [!div class="nextstepaction"]
>> [运行测试：Teams 直接路由](https://aka.ms/TeamsDirectRoutingDiag)

诊断执行大量验证。

## <a name="see-also"></a>另请参阅

[规划直接路由](direct-routing-plan.md)

[配置直接路由](direct-routing-configure.md)
