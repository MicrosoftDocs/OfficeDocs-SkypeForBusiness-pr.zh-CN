---
title: 直接路由连接模拟设备
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: conceptual
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 阅读本文以了解如何将模拟设备与 Microsoft Phone 系统直接路由配合使用。
ms.openlocfilehash: 45128b8806644e4399687787bcce251ccb807d85
ms.sourcegitcommit: a6425a536746e129ab8bda3984b5ae63fb316192
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/07/2020
ms.locfileid: "42558512"
---
# <a name="how-to-use-analog-devices-with-phone-system-direct-routing"></a>如何将模拟设备与电话系统直接路由配合使用

本文介绍如何将模拟设备与电话系统直接路由配合使用。 要将模拟设备连接到直接路由，必须使用模拟电话适配器（ATA），并且此适配器必须由认证的 "边界控制器（SBC）供应商" 支持。 

当用户从模拟设备进行呼叫时，信号和媒体将通过模拟电话适配器（ATA）传递给 SBC。  SBC 将呼叫发送到 Microsoft 团队终结点或基于内部路由表的公共交换电话网络（PSTN）。  当设备进行呼叫时，它所采用的路由取决于为设备创建的路由策略。

在下图中，配置了直接路由，以便任何团队从 + 1425 4XX XX XX 和 + 1425 5XX XX xx 之间的数字进行调用必须采用红色路线（点线），以及与 + 1425 4XX xx XX 和任何其他号码之间的任何 PSTN 呼叫，除了 号码范围 + 1425 5XX XX xx 必须采用蓝色路线（实线）。 

![显示直接路由配置的图表](media/direct-routing-analog-device.png)

## <a name="example--how-to-configure-the-use-of-analog-devices-with-direct-routing"></a>示例：如何通过直接路由配置模拟设备的使用

若要配置使用直接路由的模拟设备，必须将模拟电话适配器连接到 SBC，并将 SBC 配置为使用直接路由。 

此示例将指导你完成以下步骤：

1. 将 SBC 连接到直接路由。
2. 创建 PSTN 使用。
3. 创建一个语音路线，并将其与 PSTN 使用相关联。
4. 将语音路由分配给 PSTN 使用。
5. 启用联机用户。
6. 将语音路由策略分配给用户。
7. 为模拟设备创建语音路由。

有关如何将 ATA 连接到 SBC 和配置 SBC 的信息，请参阅 SBC 制造商配置指南：
- [AudioCodes 配置文档](https://www.audiocodes.com/media/14278/connecting-audiocodes-sbc-with-analog-device-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf)
- [功能区配置文档](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)

## <a name="step-1--connect-the-sbc-to-direct-routing"></a>第 1 步  将 SBC 连接到直接路由

以下命令将配置 SBC 连接，如下所示：

- FQDN sbc.contoso.com
- 发信号端口5068
- 媒体绕过模式
- 向 SBC 转发的通话历史记录信息
- P-声明的标识（PAI）标头与呼叫一起转发 

```
PS C:\> New-CsOnlinePSTNGateway -FQDN sbc.contoso.com -SIPSignalingPort 5068 -ForwardCallHistory $true -ForwardPAI $true -MediaBypass $true -Enabled $true 
```

## <a name="step-2--create-the-pstn-usage"></a>步骤2：创建 PSTN 使用 

下一个命令将创建空的 PSTN 用法。 联机 PSTN 用法是用于呼叫授权的字符串值。 在线 PSTN 使用将在线语音策略链接到一个路线。 此示例将字符串 "Interop" 添加到可用 PSTN 用法的当前列表。 

```
PS C:\> Set-CsOnlinePstnUsage -Identity global -Usage @{add="Interop"} 
```

## <a name="step-3--create-a-voice-route-and-associate-it-with-the-pstn-usage"></a>步骤3：创建语音路由并将其与 PSTN 使用关联：

此命令将创建一个新的在线语音路线，其中包含数字范围 + 1425 XXX xx XX 的标识 "模拟-互操作"。  语音路线适用于联机网关 sbc.contoso.com 的列表，并将该路线与联机 PSTN 使用 "互操作" 关联。 语音路由包括用于标识将通过给定语音路线路由哪些电话号码的正则表达式：

```
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(425)(\d{7}])$" -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "
```

## <a name="step-4-assign-the-voice-route-to-the-pstn-usage"></a>步骤4：将语音路由分配给 PSTN 使用：

此命令使用标识 "AnalogInteropPolicy" 创建新的每用户语音路由策略。 此策略被分配了一个在线 PSTN 使用： "互操作"。

```
PS C:\> New-CsOnlineVoiceRoutingPolicy -Identity "AnalogInteropPolicy" -Name "AnalogInteropPolicy" -OnlinePstnUsages "Interop"
```

## <a name="step-5-enable-the-online-user"></a>步骤5：启用联机用户

此命令使用标识 exampleuser@contoso.com 修改用户帐户。 在这种情况下，修改帐户以启用企业语音、Microsoft VoIP 的 Microsoft 实现以及已启用的语音邮件，并向此用户分配数字 + 14255000000。  应为公司租户中的每个团队用户（不包括 ATA 设备用户）运行此命令。

```
PS C:\> Set-CsUser -Identity "exampleuser@contoso.com" -EnterpriseVoiceEnabled $True -HostedVoiceMail $True -OnPremLineUri "tel:+14255000000"
```

## <a name="step-6-assign-the-voice-route-policy-to-a-user"></a>步骤6：将语音路由策略分配给用户

此命令将每用户联机语音路由策略 AnalogInteropPolicy 分配给具有标识 exampleuser@contoso.com 的用户。  应为公司租户中的每个团队用户（不包括 ATA 设备用户）运行此命令。

```
PS C:\> Grant-CsOnlineVoiceRoutingPolicy -Identity "exampleuser@contoso.com" -PolicyName "AnalogInteropPolicy" 
```

## <a name="step-7--create-a-voice-route-for-an-analog-device"></a>步骤7：为模拟设备创建语音路由

此命令将创建一个在线语音路线，该路线的号码范围 + 1425 4XX XX xx （适用于联机网关 sbc.contoso.com 列表），并将其与在线 PSTN 使用 "互操作" 关联。  应为具有相应电话号码模式的每个模拟设备运行此命令。 或者，在前面的步骤中配置联机语音路由时，可以使用模拟设备的正确数字模式。

```
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(4254)(\d{6}])$"  -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "Interop"
```

## <a name="considerations"></a>考虑事项

- 除非另有说明，模拟设备是可以发送 DTMF 数字的任何设备来发出呼叫。 例如，模拟电话、传真机和投影机呼机。
- 连接到 ATA 的模拟电话无法从团队中搜索。 团队用户必须手动输入与设备关联的电话号码才能调用该设备。  
 

## <a name="see-also"></a>另请参阅

[规划直接路由](direct-routing-plan.md)

[配置直接路由](direct-routing-configure.md)
