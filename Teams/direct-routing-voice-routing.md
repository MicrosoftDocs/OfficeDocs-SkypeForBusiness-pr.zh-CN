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
description: 了解如何通过 Microsoft Phone 系统直接路由配置语音路由。
ms.openlocfilehash: e87d7d04f9b2477d65e08f461ac3ff113b4d0e7c
ms.sourcegitcommit: d85425d9e6022d1bf84b877920640f9cbaf8bdce
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2020
ms.locfileid: "49530989"
---
# <a name="configure-voice-routing-for-direct-routing"></a>为直接路由配置语音路由

本文介绍如何为手机系统直接路由配置语音路由。  这是用于配置直接路由的以下步骤的步骤3：

- 第 1 步 [将 SBC 连接到 Microsoft Phone 系统并验证连接](direct-routing-connect-the-sbc.md) 
- 第 2 步 [为用户启用直接路由、语音和语音邮件](direct-routing-enable-users.md)
- **步骤3。 (本文配置语音路由**) 
- 第 4 步 [将数字转换为备用格式](direct-routing-translate-numbers.md) 

有关设置直接路由所需的所有步骤的信息，请参阅 [配置直接路由](direct-routing-configure.md)。

## <a name="voice-routing-overview"></a>语音路由概述

Microsoft Phone 系统具有一种路由机制，可用于将呼叫发送到特定的会话边界控制器 (SBC) ，具体取决于： 

- 被叫号码模式 
- 被叫号码模式和进行呼叫的特定用户
 
SBCs 可以指定为 "活动" 和 "备份"。 当配置为活动的 SBC 不能用于特定呼叫路由时，该呼叫将路由到 backup SBC。
 
语音路由由以下元素组成： 

- **语音路由策略** -PSTN 使用的容器，可分配给用户或多个用户。 

- **PSTN 用法** -用于语音路由和 PSTN 用途的容器，可在不同的语音路由策略中共享。 

- **语音路由** -一种数字模式和一组联机 PSTN 网关，用于呼叫号码匹配模式的呼叫。

- **联机 PSTN 网关** -指向 sbc 的指针，该指针还存储在通过 SBC 放置调用时应用的配置，例如，将 P 声明身份 (PAI) 或首选编解码器。可添加到语音路由。

## <a name="voice-routing-policy-considerations"></a>语音路由策略注意事项

如果用户具有呼叫计划许可证，则该用户的传出呼叫将通过 Microsoft 呼叫计划 PSTN 基础结构自动路由。 如果将联机语音路由策略配置并分配给呼叫计划用户，则会检查该用户的传出呼叫以确定所拨号码是否与联机语音路由策略中定义的数字模式匹配。 如果存在匹配项，则通过直接路由主干路由呼叫。 如果没有匹配项，则通过呼叫计划 PSTN 基础结构路由呼叫。

> [!CAUTION]
> 如果你配置并应用全球 (组织范围的默认) 联机语音路由策略，则你组织中的所有支持语音的用户将继承该策略，这可能会导致来自呼叫计划用户的 PSTN 呼叫不小心路由到直接路由主干。 如果不希望所有用户都使用全局联机语音路由策略，请配置自定义联机语音路由策略，并将其分配给单个支持语音的用户。

## <a name="example-1-voice-routing-with-one-pstn-usage"></a>示例1：使用一个 PSTN 使用的语音路由

下图显示了一个呼叫流中的语音路由策略的两个示例。

**通话流 1 (左侧) ：** 如果用户拨打 + 1 425 XXX xx 或 + 1 206 XXX xx xx，则该呼叫将路由到 SBC sbc1.contoso.biz 或 sbc2.contoso.biz。 如果 sbc1.contoso.biz 和 sbc2.contoso.biz 都不可用，则呼叫将被丢弃。 

**(右侧) 的 "呼叫流程 2"：** 如果用户拨打 + 1 425 XXX xx 或 + 1 206 XXX xx xx，则该调用首先路由到 SBC sbc1.contoso.biz 或 sbc2.contoso.biz。 如果两个 SBC 均不可用，将尝试使用较低优先级的路由 (sbc3.contoso.biz 和 sbc4.contoso.biz) 。 如果没有 SBCs 可用，将丢弃呼叫。 

![显示语音路由策略示例](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

在这两个示例中，虽然为语音路由分配了优先级，但路由中的 SBCs 按随机顺序尝试。 当两个 SBC 在一个路由中配置时，必须能够在 SBC 或 media 之间路由网络流量，因为可能会在传输中将新的邀请发送到路由中的不同 SBC。

  > [!NOTE]
  > 除非用户也有 Microsoft 通话计划许可证，否则将删除示例配置中除与模式 + 1 425 XXX xx xx 或 + 1 206 XXX xx 之间的任何号码。 如果用户有呼叫计划许可证，则会根据 Microsoft 通话计划的政策自动路由呼叫。 Microsoft 通话计划将自动应用为具有 Microsoft 呼叫计划许可证的所有用户的最后一个路由，并且不需要其他呼叫路由配置。

在下图所示的示例中，添加了一个语音路由，用于将呼叫发送给您的所有其他美国和加拿大的号码 (呼叫号码模式 + 1 XXX XXX xx xx) 。

![显示具有第三个路线的语音路由策略](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

对于所有其他呼叫，如果用户在 Microsoft Phone 系统和 Microsoft 通话计划) 中同时具有两个许可证 (，则使用自动路由。 如果没有与管理员创建的在线语音路线中的数字模式匹配的内容，则呼叫将通过 Microsoft 通话计划进行路由。 如果用户仅有 Microsoft Phone 系统，则呼叫将被丢弃，因为没有可用的匹配规则。

  > [!NOTE]
  > 在此情况下，路由 "其他 + 1" 的优先级值不重要，因为只有一条路线与模式 + 1 XXX XXX xx 相匹配。 如果用户拨打 + 1 324 567 89 89 且 sbc5.contoso.biz 和 sbc6.contoso.biz 都不可用，则呼叫将被丢弃。

下表总结了使用三个语音路由的配置。 在此示例中，所有三个路由都属于同一 PSTN 使用，即 "美国和加拿大"。  所有路线均与 "美国和加拿大" PSTN 使用相关联，PSTN 使用与 "仅美国" 语音路由策略相关联。

|**PSTN 用法**|**语音路由**|**号码模式**|**优先级**|**SBC**|**说明**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|美国和加拿大|"雷德蒙 1"|^\\+ 1 (425 \| 206) # A2\d {7}) $|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|拨打的号码的活动路线 + 1 425 XXX xx XX 或 + 1 206 XXX xx xx|
|美国和加拿大|"雷德蒙 2"|^\\+ 1 (425 \| 206) # A2\d {7}) $|2|sbc3.contoso.biz<br/>sbc4.contoso.biz|已呼叫号码的备份路由 + 1 425 XXX xx XX 或 + 1 206 XXX xx xx|
|美国和加拿大|"其他 + 1"|^\\+ 1 ( \d {10}) $|3|sbc5.contoso.biz<br/>sbc6.contoso.biz|呼叫号码的路由 + 1 XXX XXX xx (，但 + 1 425 XXX xx 或 + 1 206 XXX xx) |
|||||||

## <a name="example-1-configuration-steps"></a>示例1：配置步骤

以下示例显示了如何：

1. 创建单个 PSTN 使用。
2. 配置三个语音路由。
3. 创建语音路由策略。
4. 将策略分配给名为 Spencer Low 的用户。

你可以使用 [Microsoft 团队管理中心](#admincenterexample1) 或 [PowerShell](#powershellexample1) 执行这些步骤。

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心
<a name="admincenterexample1"></a>

#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a>步骤1：创建 "美国和加拿大" PSTN 使用

1. 在 Microsoft 团队管理中心的左侧导航中，转到 "**语音**  >  **直接路由**"，然后在右上角选择 "**管理 PSTN 使用情况记录**"。
2. 单击 " **添加**"，键入 " **美国和加拿大**"，然后单击 " **应用**"。

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a>步骤2：创建三个语音路线 (雷德蒙1、雷德蒙2和其他 + 1) 

以下步骤介绍如何创建语音路由。 使用这些步骤，通过使用前面表中所述的设置，为本示例创建三个名为 Redmond 1、Redmond 2 和其他 + 1 的语音路线。

1. 在 Microsoft 团队管理中心的左侧导航中，转到 "**语音**  >  **直接路由**"，然后选择 "**语音路由**" 选项卡。
2. 单击 " **添加**"，然后输入语音路线的名称和说明。
3. 设置优先级并指定拨出的号码模式。
4. 若要将 SBC 注册到语音路由，请在 " **SBCs 注册 (可选)** 中，单击" **添加 sbcs**"，选择要注册的 SBCs，然后单击" **应用**"。
5. 要添加 PSTN 使用记录，请在 " **PSTN 使用记录 (可选)** 下，单击" **添加 PSTN 使用情况**"，选择要添加的 PSTN 记录，然后单击" **应用**"。
6. 单击“**保存**”。

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a>步骤3：创建名为 "仅美国" 的语音路由策略，并向策略添加 "美国和加拿大" PSTN 使用情况

1. 在 Microsoft 团队管理中心的左侧导航中，转到 "**语音**  >  **语音路由策略**"，然后单击 "**添加**"。
2. **仅键入 US** 作为名称，然后添加说明。
3. 在 " **PSTN 使用记录**" 下，单击 " **添加 PSTN 使用情况**"，选择 "美国和加拿大" PSTN 使用记录，然后单击 " **应用**"。
4. 单击“**保存**”。

若要了解详细信息，请参阅 [管理语音路由策略](manage-voice-routing-policies.md)。

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a>步骤4：将语音路由策略分配给名为 Spencer Low 的用户

1. 在 Microsoft Teams 管理员中心的左侧导航中，转到“用户”，然后单击相应的用户。
2. 单击 " **策略**"，然后单击 " **分配的策略**" 旁边的 " **编辑**"。
3. 在 " **语音路由策略**" 下，选择 "仅美国" 策略，然后单击 " **保存**"。

若要了解详细信息，请参阅 [管理语音路由策略](manage-voice-routing-policies.md)。

### <a name="using-powershell"></a>使用 PowerShell
<a name="powershellexample1"></a>


#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a>步骤1：创建 "美国和加拿大" PSTN 使用

在 Skype for Business Online 中的远程 PowerShell 会话中，键入：

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

通过输入以下内容验证是否已创建使用：

```PowerShell
Get-CSOnlinePSTNUsage
``` 

这将返回可能被截断的名称的列表：

```console
Identity    : Global
Usage        : {testusage, US and Canada, International, karlUsage. . .}
```

以下示例显示运行 `(Get-CSOnlinePSTNUsage).usage` Powershell 命令以显示全名 (未截断) 的结果：

<pre>
 testusage
 US and Canada
 International
 karlUsage
 New test env
 Tallinn Lab Sonus
 karlUsage2
 Unrestricted
 Two trunks
</pre>

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a>步骤2：创建三个语音路线 (雷德蒙1、雷德蒙2和其他 + 1) 

若要在 Skype for business Online 的 PowerShell 会话中创建 "Redmond 1" 路线，请输入：

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

返回：
<pre>
Identity                : Redmond 1
Priority                : 1
Description             :
NumberPattern           : ^\+1(425|206) (\d{7})$
OnlinePstnUsages        : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name                    : Redmond 1
</pre>

若要创建雷德蒙2路线，请输入：

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

若要创建其他 + 1 路线，请输入：

```PowerShell
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > 请确保 NumberPattern 属性中的正则表达式是有效的表达式。 你可以使用此网站对其进行测试： [https://www.regexpal.com](https://www.regexpal.com)

在某些情况下，需要将所有调用路由到同一 SBC;使用-NumberPattern ". *"

将所有调用路由到同一个 SBC。

```PowerShell
Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz
```

通过 `Get-CSOnlineVoiceRoute` 使用如下所示的选项运行 PowerShell 命令验证是否已正确配置路由：

```PowerShell
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
应返回：
<pre>
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
</pre>

在此示例中，自动为 "其他 + 1" 路由分配优先级4。 

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a>步骤3：创建名为 "仅美国" 的语音路由策略，并向策略添加 "美国和加拿大" PSTN 使用情况

在 Skype for Business Online 的 PowerShell 会话中，键入：

```PowerShell
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

此示例中显示了结果：

<pre>
Identity            : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a>步骤4：将语音路由策略分配给名为 Spencer Low 的用户

在 Skype for Business Online 的 PowerShell 会话中，键入：

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"
```

通过输入以下命令验证策略分配：

```PowerShell
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```

该命令将返回以下内容：
<pre>
OnlineVoiceRoutingPolicy
---------------------
US Only
</pre>

## <a name="example-2-voice-routing-with-multiple-pstn-usages"></a>示例2：具有多个 PSTN 用法的语音路由

在示例1中创建的 "语音路由策略" 仅允许拨打美国和加拿大的电话号码，除非还为用户分配了 Microsoft 通话计划许可证。

在下面的示例中，您可以创建 "无限制" 语音路由策略。 该策略重用在示例1中创建的 "美国和加拿大" PSTN 使用情况，以及新的 "国际" PSTN 使用。 此策略将所有其他调用路由到 SBCs sbc2.contoso.biz 和 sbc5.contoso.biz。

显示的示例将 "仅美国" 策略分配给用户 Spencer Low，将 "无限制" 策略分配给用户 John 的，以便按如下方式进行路由：

- Spencer 低–美国的政策。  通话仅允许使用美国和加拿大号码。 当调用 Redmond 数字范围时，必须使用特定的 SBCs 集。 除非向用户分配了通话计划许可证，否则不会路由非美国号码。

- John 的 54777-国际政策。  任何号码都允许通话。 当调用 Redmond 数字范围时，必须使用特定的 SBCs 集。 非 US 数字将使用 sbc2.contoso.biz 和 sbc5.contoso.biz 进行路由。

![显示分配给用户 Spencer 低的语音路由策略](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

对于所有其他呼叫，如果用户在 Microsoft Phone 系统和 Microsoft 通话计划) 中同时具有两个许可证 (，则使用自动路由。 如果没有与管理员创建的在线语音路线中的数字模式匹配的内容，则使用 Microsoft 通话计划路由呼叫。  如果用户仅有 Microsoft Phone 系统，则呼叫将被丢弃，因为没有可用的匹配规则。

![显示分配给用户 John 的的语音路由策略](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

下表总结了路由策略 "无限制" 的用法标识和语音路由。 

|**PSTN 用法**|**语音路由**|**号码模式**|**优先级**|**SBC**|**说明**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|美国和加拿大|"雷德蒙 1"|^\\+ 1 (425 \| 206) # A2\d {7}) $|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|被呼叫方号码的活动路由 + 1 425 XXX XX XX 或 + 1 206 XXX xx xx|
|美国和加拿大|"雷德蒙 2"|^\\+ 1 (425 \| 206) # A2\d {7}) $|2|sbc3.contoso.biz<br/>sbc4.contoso.biz|被呼叫方号码的备份路由 + 1 425 XXX xx XX 或 + 1 206 XXX xx xx|
|美国和加拿大|"其他 + 1"|^\\+ 1 ( \d {10}) $|3|sbc5.contoso.biz<br/>sbc6.contoso.biz|被呼叫方号码的路由 + 1 XXX XXX xx (，但 + 1 425 XXX xx 或 + 1 206 XXX xx) |
|International|International|\d +|4|sbc2.contoso.biz<br/>sbc5.contoso.biz|任何数字模式的路由 |

  > [!NOTE]
  > - 语音路由策略中的 PSTN 用法的顺序非常重要。 使用实例按顺序应用，如果在第一次使用中发现匹配项，则从不计算其他用法。 "国际" PSTN 使用必须位于 "美国和加拿大" PSTN 使用后。 若要更改 PSTN 用法的顺序，请运行 `Set-CSOnlineVoiceRoutingPolicy` 命令。 <br/>例如，若要将订单从 "美国和加拿大" 的第一个和 "国际" 的订单更改为反向顺序，请执行以下操作：<br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - 将自动分配 "其他 + 1" 和 "国际" 语音路由的优先级。 它们的优先级与 "Redmond 1" 和 "雷德蒙 2" 相比，不是很重要。

## <a name="example-2-configuration-steps"></a>示例2：配置步骤

以下示例显示了如何：

1. 创建名为 "国际" 的新 PSTN 使用。
2. 创建名为 "国际" 的新语音路线。
3. 创建名为 "无限制" 的语音路由策略。
4. 将策略分配给用户 John 的一对用户。

你可以使用 [Microsoft 团队管理中心](#admincenterexample2) 或 [PowerShell](#powershellexample2) 执行这些步骤。

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心
<a name="admincenterexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a>步骤1：创建 "国际" PSTN 使用

1. 在 Microsoft 团队管理中心的左侧导航中，转到 "**语音**  >  **直接路由**"，然后在右上角选择 "**管理 PSTN 使用情况记录**"。
2. 单击 " **添加**"，键入 " **国际**"，然后单击 " **应用**"。

#### <a name="step-2-create-the-international-voice-route"></a>步骤2：创建 "国际" 语音路由

1. 在 Microsoft 团队管理中心的左侧导航中，转到 "**语音**  >  **直接路由**"，然后选择 "**语音路由**" 选项卡。
2. 单击 " **添加**"，输入 "国际" 作为名称，然后添加说明。
3. 将 "优先级" 设置为 "4"，然后将 "拨打的号码" 模式设置为 "\d +"。
4. 在 " **SBCs 注册 (可选)** 中，单击" **添加 SBCs**"，选择" sbc2.contoso.biz "和" sbc5.contoso.biz "，然后单击" **应用**"。
5. 在 " **PSTN 使用记录 (可选)**" 下，单击 " **添加 PSTN 使用情况**"，选择 "国际" PSTN 使用记录，然后单击 " **应用**"。
6. 单击“**保存**”。

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions-and-add-the-us-and-canada-and-international-pstn-usages-to-the-policy"></a>步骤3：创建名为 "无限制" 的语音路由策略，并将 "美国和加拿大" 和 "国际" PSTN 使用情况添加到策略

PSTN 使用 "美国和加拿大" 将在此语音路由策略中重复使用，以保留对号码 "+ 1 425 XXX xx" 和 "+ 1 206 XXX xx xx" 的特殊处理，作为本地或本地呼叫。

1. 在 Microsoft 团队管理中心的左侧导航中，转到 "**语音**  >  **语音路由策略**"，然后单击 "**添加**"。
2. 键入 " **无限制** " 作为名称并添加说明。
3. 在 " **PSTN 使用记录**" 下，单击 " **添加 PSTN 使用情况**"，选择 "美国和加拿大" pstn 使用记录，然后选择 "国际" pstn 使用记录。 单击“**应用**”。

    记下 PSTN 用法的顺序：

    - 如果对号码 "+ 1 425 XXX XX XX" 的调用与此示例中配置的用法相同，则呼叫将遵循 "美国和加拿大" 使用中设置的路由，并应用特殊路由逻辑。 也就是说，将首先使用 sbc1.contoso.biz 和 sbc2.contoso.biz 路由呼叫，然后 sbc3.contoso.biz 和 sbc4.contoso.biz 作为备份路由。

    - 如果 "国际" PSTN 使用早于 "美国和加拿大"，则对 + 1 425 XXX xx 的调用将作为路由逻辑的一部分路由到 sbc2.contoso.biz 和 sbc5.contoso.biz。

4. 单击“**保存**”。

若要了解详细信息，请参阅 [管理语音路由策略](manage-voice-routing-policies.md)。

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-john-woods"></a>步骤4：将语音路由策略分配给名为 John 的的用户

1. 在 Microsoft Teams 管理员中心的左侧导航中，转到“用户”，然后单击相应的用户。
2. 单击 " **策略**"，然后单击 " **分配的策略**" 旁边的 " **编辑**"。
3. 在 " **语音路由策略**" 下，选择 "无限制" 策略，然后单击 " **保存**"。

结果是，应用到 John 54777 的语音政策不受限制，并且将遵循呼叫路由的逻辑，可用于美国、加拿大和国际通话。

### <a name="using-powershell"></a>使用 PowerShell
<a name="powershellexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a>步骤1：创建 "国际" PSTN 使用

在 Skype for Business Online 中的远程 PowerShell 会话中，输入：

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

#### <a name="step-2--create-a-new-voice-route-named-international"></a>步骤2：创建名为 "国际" 的新语音路线

```PowerShell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
```
返回：

<pre>
Identity                  : International
Priority                  : 5
Description               :
NumberPattern             : .*
OnlinePstnUsages          : {International}
OnlinePstnGatewayList     : {sbc2.contoso.biz, sbc5.contoso.biz}
Name                      : International
</pre>

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions"></a>步骤3：创建名为 "无限制" 的语音路由策略

PSTN 使用 "Redmond 1" 和 "Redmond" 在此语音路由策略中重复使用，以保留对号码 "+ 1 425 XXX xx" 和 "+ 1 206 XXX xx xx" 的特殊处理，作为本地或本地呼叫。

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

记下 PSTN 用法的顺序：

  - 如果对数字 "+ 1 425 XXX XX XX" 的调用配置为以下示例中所示的使用实例，则呼叫将遵循 "美国和加拿大" 使用中设置的路由，并应用特殊路由逻辑。 也就是说，将首先使用 sbc1.contoso.biz 和 sbc2.contoso.biz 路由呼叫，然后 sbc3.contoso.biz 和 sbc4.contoso.biz 作为备份路由。

  - 如果 "国际" PSTN 使用早于 "美国和加拿大"，则对 + 1 425 XXX xx 的调用将作为路由逻辑的一部分路由到 sbc2.contoso.biz 和 sbc5.contoso.biz。 输入命令：

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

返回：

    <pre>
    Identity              : International 
    OnlinePstnUsages : {US and Canada, International}     
    Description         :  
    RouteType               : BYOT
    </pre>

#### <a name="step-4-assign-the-voice-routing-policy-to-the-user-named-john-woods"></a>步骤4：将语音路由策略分配给名为 John 的的用户

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions"
```

然后使用以下命令验证作业： 

```PowerShell
Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
```

返回：

<pre>
OnlineVoiceRoutingPolicy
------------------------
No Restrictions
</pre>

结果是，应用到 John 54777 的语音政策不受限制，并且将遵循可用于美国、加拿大和国际通话的呼叫路线逻辑。

## <a name="see-also"></a>另请参阅

[规划直接路由](direct-routing-plan.md)

[配置直接路由](direct-routing-configure.md)
