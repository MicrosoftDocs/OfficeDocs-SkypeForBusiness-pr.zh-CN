---
title: 为直接路由配置语音路由
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 了解如何使用 Microsoft Phone 系统直接路由配置语音路由。
ms.openlocfilehash: 9330c3bf8200ed84fa9f7c534e794af887097b8d
ms.sourcegitcommit: 3fc6fb528806f967bdc80671761cd45c32db6516
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/26/2021
ms.locfileid: "51383976"
---
# <a name="configure-voice-routing-for-direct-routing"></a>为直接路由配置语音路由

本文介绍如何为电话系统直接路由配置语音路由。  这是配置直接路由的以下步骤的步骤 3：

- 第 1 步 [将 SBC 与 Microsoft Phone System 连接并验证连接](direct-routing-connect-the-sbc.md) 
- 第 2 步 [为用户启用直接路由、语音和语音邮件](direct-routing-enable-users.md)
- **步骤 3.配置语音路由** (本文) 
- 第 4 步 [将数字转换为备用格式](direct-routing-translate-numbers.md) 

有关设置直接路由所需的所有步骤的信息，请参阅 [配置直接路由](direct-routing-configure.md)。

## <a name="voice-routing-overview"></a>语音路由概述

Microsoft Phone System 具有一种路由机制，允许将呼叫发送到 SBC (特定会话边界控制器) 基于： 

- 调用的编号模式 
- 被调用的号码模式加上进行呼叫的特定用户
 
可以将 SDC 指定为活动和备份。 如果配置为活动的 SBC 不可用于特定的调用路由，则调用将路由到备份 SBC。
 
语音路由由以下元素组成： 

- **语音路由** 策略 - PSTN 用法的容器，可分配给用户或多个用户。 

- **PSTN 使用情况** - 用于语音路由和 PSTN 使用情况的容器，可在不同的语音路由策略中共享。 

- **语音路由** - 呼叫号码与模式匹配的呼叫使用的一个号码模式和一组联机 PSTN 网关。

- **联机 PSTN** 网关 - 指向 SBC 的指针，该 SBC 还存储通过 SBC 进行呼叫时应用的配置，例如转发 P-Asserted-Identity (PAI) 或首选编解码器;可添加到语音路由。

## <a name="voice-routing-policy-considerations"></a>语音路由策略注意事项

如果用户具有呼叫计划许可证，该用户的传出呼叫将通过 Microsoft 呼叫计划 PSTN 基础结构自动路由。 如果配置在线语音路由策略并将其分配给呼叫计划用户，将检查该用户的传出呼叫，以确定拨叫号码是否与在线语音路由策略中定义的号码模式匹配。 如果存在匹配项，则通过直接路由中继路由调用。 如果没有匹配项，则呼叫将通过呼叫计划 PSTN 基础结构进行路由。

> [!CAUTION]
> 如果配置并应用全局 (组织范围的默认) 在线语音路由策略，则组织中所有支持语音的用户都将继承该策略，这可能会导致呼叫计划用户的 PSTN 呼叫无意中路由到直接路由中继。 如果不希望所有用户使用全局联机语音路由策略，请配置自定义联机语音路由策略并将其分配给启用了语音的单个用户。

## <a name="example-1-voice-routing-with-one-pstn-usage"></a>示例 1：使用一个 PSTN 的语音路由

下图显示了呼叫流中语音路由策略的两个示例。

**调用左侧 (流 1) ：** 如果用户拨打 +1 425 XXX XX 或 +1 206 XXX XX XX，该呼叫将路由到 SBC sbc1.contoso.biz 或 sbc2.contoso.biz。 如果 sbc1.contoso.biz 和 sbc2.contoso.biz 都不可用，将丢弃调用。 

**调用右侧 (流 2) ：** 如果用户拨打 +1 425 XXX XX 或 +1 206 XXX XX XX，该呼叫将首先路由到 SBC sbc1.contoso.biz 或 sbc2.contoso.biz。 如果两个 SBC 都不可用，将尝试优先级较低的路由 (sbc3.contoso.biz sbc4.contoso.biz) 。 如果没有任何 SDC 可用，将丢弃调用。 

![显示语音路由策略示例](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

在这两个示例中，当为语音路由分配优先级时，将随机尝试路由中的 SDC。

  > [!NOTE]
  > 除非用户也有 Microsoft 呼叫计划许可证，否则将删除示例配置中与模式 +1 425 XXX XX XX 或 +1 206 XXX XX XX 匹配的号码以外的任何号码。 如果用户具有呼叫计划许可证，则根据 Microsoft 呼叫计划的策略自动路由呼叫。 Microsoft 呼叫计划自动作为最后一个路由应用到具有 Microsoft 呼叫计划许可证的所有用户，不需要其他呼叫路由配置。

在下图所示的示例中，添加了一个语音路由，用于将呼叫发送到所有其他美国和加拿大号码， (呼叫号码模式 +1 XXX XXX XX XX) 。

![显示具有第三个路由的语音路由策略](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

对于所有其他呼叫，如果用户同时拥有 Microsoft Phone System (和 Microsoft 呼叫) 许可证，则使用自动路由。 如果没有任何内容与管理员创建的联机语音路由中的号码模式匹配，则呼叫将通过 Microsoft 呼叫计划进行路由。 如果用户只有 Microsoft Phone System，则呼叫将被删除，因为没有匹配的规则可用。

  > [!NOTE]
  > 在这种情况下，路由"其他 +1"的优先级值并不重要，因为只有一个路由与模式 +1 XXX XXX XX XX 匹配。 如果用户拨打了 +1 324 567 89 89，sbc5.contoso.biz 和 sbc6.contoso.biz 都不可用，则呼叫将被删除。

下表总结了使用三个语音路由的配置。 此示例中，所有三个路由都是同一 PSTN 用法"美国和加拿大"的一部分。  所有路由都与"美国和加拿大"PSTN 使用情况相关联，PSTN 使用情况与"仅美国"语音路由策略相关联。

|**PSTN 用法**|**语音路由**|**号码模式**|**优先级**|**SBC**|**说明**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|美国和加拿大|"Redmond 1"|^\\+1 (425 \| 206)  (\d {7}) $|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|被叫号码的活动路由 +1 425 XXX XX XX 或 +1 206 XXX XX XX|
|美国和加拿大|"Redmond 2"|^\\+1 (425 \| 206)  (\d {7}) $|2|sbc3.contoso.biz<br/>sbc4.contoso.biz|被叫号码的备份路由 +1 425 XXX XX XX 或 +1 206 XXX XX XX|
|美国和加拿大|"其他 +1"|^\\+1 (\d {10}) $|3|sbc5.contoso.biz<br/>sbc6.contoso.biz|被叫号码 +1 XXX XXX XX XX 的路由 (+1 425 XXX XX XX 或 +1 206 XXX XX XX) |
|||||||

## <a name="example-1-configuration-steps"></a>示例 1：配置步骤

以下示例演示如何：

1. 创建单个 PSTN 使用情况。
2. 配置三个语音路由。
3. 创建语音路由策略。
4. 将策略分配给名为 Spencer Low 的用户。

可以使用 Microsoft [Teams 管理中心或](#admincenterexample1) [PowerShell](#powershellexample1) 执行这些步骤。

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心
<a name="admincenterexample1"></a>

#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a>步骤 1：创建"美国和加拿大"PSTN 使用情况

1. 在 Microsoft Teams 管理中心的左侧导航中，转到"**语音** 直接路由"，然后在右上角选择"管理  >  **PSTN 使用记录"。**
2. 单击 **"添加**"，**键入"美国和加拿大**"，然后单击"应用 **"。**

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a>步骤 2：创建三 (Redmond 1、Redmond 2 和其他 +1 语音路由) 

以下步骤介绍如何创建语音路由。 使用这些步骤，使用上表中概述的设置为此示例创建名为 Redmond 1、Redmond 2 和 Other +1 的三个语音路由。

1. 在 Microsoft Teams 管理中心的左侧导航中，转到"**语音**  >  **直接路由**"，然后选择"**语音路由"** 选项卡。
2. 单击 **"** 添加"，然后输入语音路由的名称和说明。
3. 设置优先级并指定拨号号码模式。
4. 若要使用语音路由注册 SBC，请在注册了 (可选) 的 SBC 下，单击"添加 **SBC"，** 选择要注册的 SBC，然后单击"应用 **"。** ****
5. 若要添加 PSTN 使用记录，请在 **"PSTN** 使用记录" (可选) "下，单击"添加 PSTN 使用情况"，选择要添加的 **PSTN** 记录，然后单击"应用 **"。**
6. 单击“**保存**”。

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a>步骤 3：创建名为"仅美国"的语音路由策略，将"美国和加拿大"PSTN 使用情况添加到策略

1. 在 Microsoft Teams 管理中心的左侧导航栏中，转到"**语音**  >  **语音路由策略**"，然后单击"添加 **"。**
2. 键入 **"仅美国** "作为名称并添加说明。
3. 在 **"PSTN 使用记录"** 下，单击"**添加 PSTN 使用情况**"，选择"美国和加拿大"PSTN 使用记录，然后单击"应用 **"。**
4. 单击“**保存**”。

有关详细信息，请参阅管理 [语音路由策略](manage-voice-routing-policies.md)。

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a>步骤 4：将语音路由策略分配给名为 Spencer Low 的用户

1. 在 Microsoft Teams 管理员中心的左侧导航中，转到“用户”，然后单击相应的用户。
2. 单击 **"策略**"，然后在"**分配的策略"旁边** 单击"**编辑"。**
3. 在 **"语音路由策略"** 下，选择"仅美国"策略，然后单击"保存 **"。**

有关详细信息，请参阅管理 [语音路由策略](manage-voice-routing-policies.md)。

### <a name="using-powershell"></a>使用 PowerShell
<a name="powershellexample1"></a>


#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a>步骤 1：创建"美国和加拿大"PSTN 使用情况

在 Skype for Business Online 的远程 PowerShell 会话中，键入：

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

输入以下代码，验证是否创建了使用情况：

```PowerShell
Get-CSOnlinePSTNUsage
``` 

这将返回可能被截断的名称列表：

```console
Identity    : Global
Usage        : {testusage, US and Canada, International, karlUsage. . .}
```

以下示例显示了运行 PowerShell 命令以显示完整名称的结果， (`(Get-CSOnlinePSTNUsage).usage` 不会被截断) ：

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

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a>步骤 2：创建三 (Redmond 1、Redmond 2 和其他 +1 语音路由) 

若要创建"Redmond 1"路由，请在 Skype for Business Online 的 PowerShell 会话中输入：

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

若要创建 Redmond 2 路线，请输入：

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

若要创建"其他 +1"路由，请输入：

```PowerShell
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > 请确保 NumberPattern 属性中的正则表达式是有效的表达式。 可以使用此网站测试它： [https://www.regexpal.com](https://www.regexpal.com)

在某些情况下，需要将所有调用路由到同一 SBC;use -NumberPattern ".*"

将所有调用路由到同一 SBC。

```PowerShell
Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz
```

使用如下所示的选项运行 PowerShell 命令， `Get-CSOnlineVoiceRoute` 验证是否正确配置了路由：

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

在示例中，路由"其他 +1"已自动分配优先级 4。 

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a>步骤 3：创建名为"仅美国"的语音路由策略，将"美国和加拿大"PSTN 使用情况添加到策略

在 Skype for Business Online 的 PowerShell 会话中，键入：

```PowerShell
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

此示例中显示了结果：

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

## <a name="example-2-voice-routing-with-multiple-pstn-usages"></a>示例 2：使用多个 PSTN 的语音路由

在示例 1 中创建的语音路由策略仅允许呼叫美国和加拿大的电话号码，除非 Microsoft 呼叫计划许可证也分配给用户。

在下面的示例中，可以创建"无限制"语音路由策略。 该策略重复使用在示例 1 中创建的"美国和加拿大"PSTN 使用情况，以及新的"国际"PSTN 使用情况。 此策略将所有其他调用路由到 SDC sbc2.contoso.biz sbc5.contoso.biz。

显示的示例将"仅美国"策略分配给用户 Spencer Low，将"无限制"策略分配给用户 John 一并路由，如下所示：

- Spencer Low - 仅美国策略。  仅允许拨打美国和加拿大号码。 调用 Redmond 号码范围时，必须使用特定的 SDC 集。 除非将呼叫计划许可证分配给用户，否则不会路由非美国号码。

- John John - 国际策略。  允许对任意号码进行呼叫。 调用 Redmond 号码范围时，必须使用特定的 SDC 集。 非美国号码将使用 sbc2.contoso.biz 和 sbc5.contoso.biz。

![显示分配给用户 Spencer Low 的语音路由策略](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

对于所有其他呼叫，如果用户同时拥有 Microsoft Phone System (和 Microsoft 呼叫) 许可证，则使用自动路由。 如果没有任何内容与管理员创建的联机语音路由中的号码模式匹配，则使用 Microsoft 呼叫计划路由呼叫。  如果用户只有 Microsoft Phone System，则呼叫将被删除，因为没有匹配的规则可用。

![显示分配给用户 John Routing 的语音路由策略](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

下表汇总了路由策略"无限制"使用指示和语音路由。 

| PSTN 用法 | 语音路由 | 号码模式 | 优先级 | SBC | 说明 |
|:-----|:-----|:-----|:-----|:-----|:-----|
|美国和加拿大|"Redmond 1"|^\\+1 (425 \| 206)  (\d {7}) $|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|被叫号码的活动路由 +1 425 XXX XX XX 或 +1 206 XXX XX XX|
|美国和加拿大|"Redmond 2"|^\\+1 (425 \| 206)  (\d {7}) $|2|sbc3.contoso.biz<br/>sbc4.contoso.biz|被叫号码的备份路由 +1 425 XXX XX XX 或 +1 206 XXX XX XX|
|美国和加拿大|"其他 +1"|^\\+1 (\d {10}) $|3|sbc5.contoso.biz<br/>sbc6.contoso.biz|被叫号码的路由 +1 XXX XXX XX XX (+1 425 XXX XX 或 +1 206 XXX XX XX) |
|International|International|\d+|4|sbc2.contoso.biz<br/>sbc5.contoso.biz|任意数字模式的路由 |

  > [!NOTE]
  > - 语音路由策略中的 PSTN 使用顺序至关重要。 按顺序排列使用情况，如果第一次使用时发现匹配项，则永远不会评估其他使用情况。 "国际"PSTN 使用必须在"美国和加拿大"PSTN 使用之后。 若要更改 PSTN 使用情况的顺序，请运行 `Set-CSOnlineVoiceRoutingPolicy` 命令。 <br/>例如，若要将订单从"美国和加拿大"第一个更改为"国际"秒更改为反向顺序运行：<br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - 将自动分配"其他 +1"和"国际"语音路由的优先级。 只要优先级低于"雷德蒙德 1"和"雷德蒙德 2"，就无关紧要。

## <a name="example-2-configuration-steps"></a>示例 2：配置步骤

以下示例演示如何：

1. 创建名为"国际"的新 PSTN 使用情况。
2. 创建名为"国际"的新语音路由。
3. 创建名为"无限制"的语音路由策略。
4. 将策略分配给用户 John John。。

可以使用 Microsoft [Teams 管理中心或](#admincenterexample2) [PowerShell](#powershellexample2) 执行这些步骤。

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心
<a name="admincenterexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a>步骤 1：创建"国际"PSTN 使用情况

1. 在 Microsoft Teams 管理中心的左侧导航中，转到"**语音** 直接路由"，然后在右上角选择"管理  >  **PSTN 使用记录"。**
2. 单击 **"添加**"，键入 **"国际**"，然后单击"**应用"。**

#### <a name="step-2-create-the-international-voice-route"></a>步骤 2：创建"国际"语音路由

1. 在 Microsoft Teams 管理中心的左侧导航中，转到"**语音**  >  **直接路由**"，然后选择"**语音路由"** 选项卡。
2. 单击 **"添加**"，输入"国际"作为名称，然后添加说明。
3. 将优先级设置为 4，然后将拨号号码模式设置为 \d+。
4. 在 **注册了可选** (的) 下，单击"添加 **SDC"，** 选择"sbc2.contoso.biz"sbc5.contoso.biz"，然后单击"应用 **"。**
5. 在 **"PSTN 使用** (") "下，单击"添加 **PSTN** 使用情况"，选择"国际"PSTN 使用记录，然后单击"应用 **"。**
6. 单击“**保存**”。

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions-and-add-the-us-and-canada-and-international-pstn-usages-to-the-policy"></a>步骤 3：创建名为"无限制"的语音路由策略，将"美国和加拿大"和"国际"PSTN 使用情况添加到策略

此语音路由策略中重复使用 PSTN 使用"美国和加拿大"，以保留对号码"+1 425 XXX XX"和"+1 206 XXX XX XX"作为本地或本地呼叫的呼叫的特殊处理。

1. 在 Microsoft Teams 管理中心的左侧导航栏中，转到"**语音**  >  **语音路由策略**"，然后单击"添加 **"。**
2. 键入 **"无限制"** 作为名称并添加说明。
3. 在 **"PSTN 使用记录"** 下，单击"添加 **PSTN** 使用情况"，选择"美国和加拿大"PSTN 使用记录，然后选择"国际"PSTN 使用记录。 单击“**应用**”。

    记下 PSTN 使用顺序：

    - 如果调用号码为"+1 425 XXX XX"，并且使用配置了此示例中的用法，则调用将遵循"美国和加拿大"使用情况中设置的路由，并应用特殊的路由逻辑。 也就是说，首先使用 sbc1.contoso.biz 和 sbc2.contoso.biz 路由 sbc3.contoso.biz，sbc4.contoso.biz 作为备份路由。

    - 如果"国际"PSTN 用量在"美国和加拿大"之前，则作为路由逻辑的一部分，对 +1 425 XXX XX XX 的呼叫将路由到 sbc2.contoso.biz 和 sbc5.contoso.biz。

4. 单击“**保存**”。

有关详细信息，请参阅管理 [语音路由策略](manage-voice-routing-policies.md)。

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-john-woods"></a>步骤 4：将语音路由策略分配给名为 John Woods 的用户

1. 在 Microsoft Teams 管理员中心的左侧导航中，转到“用户”，然后单击相应的用户。
2. 单击 **"策略**"，然后在"**分配的策略"旁边** 单击"**编辑"。**
3. 在 **"语音路由策略"** 下，选择"无限制"策略，然后单击"保存 **"。**

结果是，应用于 John Unrestrict 的呼叫的语音策略不受限制，并且将遵循适用于美国、加拿大和国际呼叫的呼叫路由逻辑。

### <a name="using-powershell"></a>使用 PowerShell
<a name="powershellexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a>步骤 1：创建"国际"PSTN 使用情况

在 Skype for Business Online 的远程 PowerShell 会话中，输入：

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

#### <a name="step-2--create-a-new-voice-route-named-international"></a>步骤 2：创建名为"International"的新语音路由

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

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions"></a>步骤 3：创建名为"无限制"的语音路由策略

PSTN 用法"Redmond 1"和"Redmond"在此语音路由策略中重复使用，以保留对号码"+1 425 XXX XX"和"+1 206 XXX XX XX"作为本地或本地呼叫的呼叫的特殊处理。

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

记下 PSTN 使用顺序：

  - 如果调用号码"+1 425 XXX XX"并配置了如下示例所示的用法，则调用将遵循"美国和加拿大"使用情况中设置的路由，并应用特殊的路由逻辑。 也就是说，首先使用 sbc1.contoso.biz 和 sbc2.contoso.biz 路由 sbc3.contoso.biz，sbc4.contoso.biz 作为备份路由。

  - 如果"国际"PSTN 用量在"美国和加拿大"之前，则作为路由逻辑的一部分，对 +1 425 XXX XX XX 的呼叫将路由到 sbc2.contoso.biz 和 sbc5.contoso.biz。 输入命令：

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

然后使用 命令验证分配： 

```PowerShell
Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
```

这将返回：

```console
OnlineVoiceRoutingPolicy
------------------------
No Restrictions
```

结果是，应用于 John Unrestrict 的呼叫的语音策略不受限制，并且将遵循适用于美国、加拿大和国际呼叫的呼叫路由逻辑。

## <a name="see-also"></a>另请参阅

[规划直接路由](direct-routing-plan.md)

[配置直接路由](direct-routing-configure.md)
