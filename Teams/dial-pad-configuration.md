---
title: Teams拨号盘配置
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: 了解如何在Teams客户端中配置拨号盘，以便用户可以访问公共交换电话网络 (PSTN) 功能。
ms.openlocfilehash: 6aa5edf8f57574fa08a224541772c1f9e662f9ca
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676150"
---
# <a name="dial-pad-configuration"></a>拨号盘配置

在Teams客户端中，拨号盘使用户能够访问公共交换电话网络 (PSTN) 功能。 拨号盘适用于具有电话系统许可证的用户，前提是已正确配置。 拨号盘必须满足以下条件才能显示：

- 用户已启用电话系统 (“MCOEV”) 许可证
- 用户具有 Microsoft 呼叫计划、运营商连接或已启用直接路由
- 用户已启用企业语音
- 用户处于联机状态，而不是本地Skype for Business
- 用户已启用Teams调用策略

以下部分介绍如何使用 PowerShell 检查条件。 在大多数情况下，需要查看Get-CsOnlineUser cmdlet 输出中的各种属性。 示例假定$user是用户的 UPN 或 sip 地址。

## <a name="user-has-an-enabled-phone-system-mcoev-license"></a>用户已启用电话系统 (“MCOEV”) 许可证

确保为用户分配的计划显示 **设置为“已启用”的 CapabilityStatus 属性**，并将 **功能设置为 MCOEV** (电话系统许可证) 。 你可能会看到 MCOEV、MCOEV1 等。 所有操作都是可接受的-只要功能以 MCOEV 开头。

若要检查属性是否设置正确，请使用以下命令：

```PowerShell
(Get-CsOnlineUser -Identity $user).AssignedPlan
```

输出如下所示。 只需检查 **CapabilityStatus** 和 **功能** 属性：

```PowerShell
AssignedTimestamp   Capability      CapabilityStatus ServiceInstance                          ServicePlanId
-----------------   ----------      ---------------- ---------------                          -------------
07-02-2020 12:28:48 MCOEV           Enabled          MicrosoftCommunicationsOnline/NOAM-4A-S7 4828c8ec-dc2e-4779-b502-...
07-02-2020 12:28:48 Teams           Enabled          TeamspaceAPI/NA001                       57ff2da0-773e-42df-b2af-...
```

## <a name="user-has-microsoft-calling-plan-operator-connect-or-is-enabled-for-direct-routing"></a>用户已启用 Microsoft 呼叫计划，运营商连接 OR 已启用直接路由

**如果用户有 Microsoft 呼叫计划**，请确保 **将 CapabilityStatus 属性设置为“已启用**”，并且功能 **设置为 MCOPSTN**。 你可能会看到 MCOPSTN1、MCOPSTN2 等。 所有操作都是可接受的-只要功能以 MCOPSTN 开头。

若要检查属性，请使用以下命令：

```PowerShell
(Get-CsOnlineUser -Identity $user).AssignedPlan
```

输出如下所示。 只需检查 **CapabilityStatus** 和 **功能** 属性：

```PowerShell
AssignedTimestamp   Capability      CapabilityStatus ServiceInstance                          ServicePlanId
-----------------   ----------      ---------------- ---------------                          -------------
07-02-2020 12:28:48 MCOEV           Enabled          MicrosoftCommunicationsOnline/NOAM-4A-S7 4828c8ec-dc2e-4779-b502-...
07-02-2020 12:28:48 MCOPSTN2        Enabled          MicrosoftCommunicationsOnline/NOAM-4A-S7 5a10155d-f5c1-411a-a8ec-...
07-02-2020 12:28:48 Teams           Enabled          TeamspaceAPI/NA001                       57ff2da0-773e-42df-b2af-...
```

**如果为用户启用了运营商连接**，则用户必须具有 TeamsCarrierEmergencyCallRoutingPolicy 的非 null 值。 若要检查属性，请使用以下命令：

```PowerShell
Get-CsOnlineUser -Identity $user|Select TeamsCarrierEmergencyCallRoutingPolicy
```

输出应具有非 null 值，例如：

```PowerShell
TeamsCarrierEmergencyCallRoutingPolicy
--------------------------------------
Synergy_98d1a5cb-d3e6-4306-885e-69a95f2da5c3
```

**如果为用户启用了直接路由**，则必须为用户分配 OnlineVoiceRoutingPolicy 的非 null 值。 若要检查属性，请使用以下命令：

```PowerShell
Get-CsOnlineUser -Identity $user|Select OnlineVoiceRoutingPolicy
```

输出应具有非 null 值，例如：

```PowerShell
OnlineVoiceRoutingPolicy
------------------------
Test_Policy
```

## <a name="user-has-enterprise-voice-enabled"></a>用户已启用企业语音

若要检查用户是否已启用企业语音，请使用以下命令：

```PowerShell
Get-CsOnlineUser -Identity $user|Select EnterpriseVoiceEnabled
```

输出应如下所示：

```PowerShell
EnterpriseVoiceEnabled
----------------------
                  True
```

## <a name="user-is-homed-online-and-not-in-skype-for-business-on-premises"></a>用户处于联机状态，而不是本地Skype for Business

为了确保用户处于联机状态，而不是本地Skype for Business，RegistrarPool 不得为 null，HostingProvider 必须包含以“sipfed.online”开头的值。  若要检查这些值，请使用以下命令：

```PowerShell
Get-CsOnlineUser -Identity $user|Select RegistrarPool, HostingProvider
```

输出应类似于：

```PowerShell
RegistrarPool                 HostingProvider
-------------                 ---------------
sippoolbn10M02.infra.lync.com sipfed.online.lync.com
```

## <a name="user-has-teams-calling-policy-enabled"></a>用户已启用Teams调用策略

用户的有效 TeamsCallingPolicy 必须将 AllowPrivateCalling 设置为 true。  默认情况下，用户继承全局策略，默认情况下，AllowPrivateCallingPolicy 设置为 true。

若要获取用户的 TeamsCallingPolicy 并检查 AllowPrivateCalling 是否设置为 true，请使用以下命令：

```PowerShell
if (($p=Get-CsUserPolicyAssignment -Identity $user -PolicyType TeamsCallingPolicy) -eq $null) {Get-CsTeamsCallingPolicy -Identity Global} else {Get-CsTeamsCallingPolicy -Identity $p.PolicyName}
```

输出应如下所示：

```PowerShell
Identity                   : Global
Description                :
AllowPrivateCalling        : True
AllowWebPSTNCalling        : True
AllowVoicemail             : UserOverride
AllowCallGroups            : True
AllowDelegation            : True
AllowCallForwardingToUser  : True
AllowCallForwardingToPhone : True
PreventTollBypass          : False
BusyOnBusyEnabledType      : Disabled
MusicOnHoldEnabledType     : Enabled
```

## <a name="additional-notes"></a>其他说明

- 在进行上述任何配置更改后，可能需要重启Teams客户端。

- 如果最近更新了上述任何条件，则可能需要等待几个小时，客户端才能接收新设置。

- 如果仍然看不到拨号盘，请使用以下命令检查是否存在预配错误：

  ```PowerShell
  Get-CsOnlineUser -Identity $user|Select UserValidationErrors
  ```

- 如果超过 24 小时，但仍遇到问题，请联系支持人员。
