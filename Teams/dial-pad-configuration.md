---
title: 团队拨号 pad 配置
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
localization_priority: Normal
f1.keywords:
- NOCSH
description: 了解如何配置团队客户端中的拨号盘，以便用户可以访问公共交换式电话网络（PSTN）功能。
ms.openlocfilehash: 44fcbb766cadaa4b31aa065fae80fdcd48c5453f
ms.sourcegitcommit: a94a267c421a78587b0dbbea5fa167aad2882e9b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/01/2020
ms.locfileid: "45012411"
---
# <a name="dial-pad-configuration"></a>拨号键盘配置

在 "团队客户端" 中，拨号盘使用户能够访问公共交换式电话网络（PSTN）功能。 如果用户配置正确，则使用电话系统许可证的用户可以使用拨号盘。 要显示拨号盘，需要以下条件：

- 用户拥有一个已启用的电话系统（"MCOEV"）许可证
- 用户具有 Microsoft 通话计划或已启用直接路由
- 用户已启用企业语音
- 用户处于联机状态，而不是在本地 Skype for Business 中
- 用户已启用团队调用策略

以下部分介绍了如何使用 PowerShell 检查条件。 在大多数情况下，你需要在 CsOnlineUser cmdlet 的输出中查看各种属性。 示例假设 $user 是用户的 UPN 或 sip 地址。

## <a name="user-has-an-enabled-phone-system-mcoev-license"></a>用户拥有一个已启用的电话系统（"MCOEV"）许可证

必须确保为用户分配的计划显示 " **CapabilityStatus" 属性设置为 "已启用**"，并且**功能计划设置为 "MCOEV** " （电话系统许可证）。 您可能会看到 MCOEV、MCOEV1 等。 所有功能均可接受-只要功能计划以 MCOEV 开始。

若要检查属性是否设置正确，请使用以下命令：

```
Get-CsOnlineUser -Identity $user|select AssignedPlan|fl
```

输出将如下所示。 您只需要检查**CapabilityStatus**和**功能计划**属性：

```
<Plan SubscribedPlanId="2f9eda01-4630-4a5c-bdb3-cf195f22d240"  
   ServiceInstance="MicrosoftCommunicationsOnline/NOAM-0M-DMT" 
   CapabilityStatus="Enabled"  
   AssignedTimestamp="2020-04-21T18:31:13Z" 
   ServicePlanId="4828c8ec-dc2e-4779-b502-87ac9ce28ab7" 
   xmlns="http://schemas.microsoft.com/online/directoryservices/change/2008/11"> 
  <Capability> 
     <Capability Plan="MCOEV" 
     xmlns="http://schemas.microsoft.com/online/MCO/2009/01"/> 
  </Capability>
</Plan>
```


## <a name="user-has-microsoft-calling-plan-or-is-enabled-for-direct-routing"></a>用户具有 Microsoft 通话计划或已启用直接路由

**如果用户具有 Microsoft 通话计划**，则必须确保**CapabilityStatus 属性设置为 "已启用**"，并且**功能计划设置为 "MCOPSTN**"。 您可能会看到 MCOPSTN1、MCOPSTN2 等。 所有功能均可接受-只要功能计划以 MCOPSTN 开始。

若要检查属性，请使用以下命令：

```
Get-CsOnlineUser -Identity $user|select AssignedPlan|fl
```

输出将如下所示。 您只需要检查**CapabilityStatus**和**功能计划**属性：

```  
<Plan SubscribedPlanId="71d1258e-a4e6-443f-884e-0f3d6f644bb1" 
ServiceInstance="MicrosoftCommunicationsOnline/NOAM-0M-DMT" 
CapabilityStatus="Enabled"    
AssignedTimestamp="2018-09-18T18:41:42Z" 
ServicePlanId="5a10155d-f5c1-411a-a8ec-e99aae125390" 
xmlns="http://schemas.microsoft.com/online/directoryservices/change/2008/11">
 <Capability>
    <Capability Plan="MCOPSTN2" 
    xmlns="http://schemas.microsoft.com/online/MCO/2009/01" />
 </Capability>
</Plan>
  ```

**如果用户已启用直接路由**，则必须为该用户分配 OnlineVoiceRoutingPolicy 的非 null 值。 若要检查属性，请使用以下命令：
  
```
Get-CsOnlineUser -Identity $user|Select OnlineVoiceRoutingPolicy 
```

输出应具有非 null 值，例如：

```
OnlineVoiceRoutingPolicy
------------------------
Test_Policy
```

## <a name="user-has-enterprise-voice-enabled"></a>用户已启用企业语音

若要检查用户是否已启用企业语音，请使用以下命令：

```
Get-CsOnlineUser -Identity $user|Select EnterpriseVoiceEnabled
```

输出应如下所示：

```
EnterpriseVoiceEnabled
----------------------
                  True

```
 
## <a name="user-is-homed-online-and-not-in-skype-for-business-on-premises"></a>用户处于联机状态，而不是在本地 Skype for Business 中

若要确保用户在本地托管，而不是在本地 Skype for business 中，RegistrarPool 不得为 null，并且 HostingProvider 必须包含以 "sipfed." 开头的值。  若要检查值，请使用以下命令：

```
Get-CsOnlineUser -Identity $user|Select RegistrarPool, HostingProvider
```

输出应类似于：

```
RegistrarPool                 HostingProvider
-------------                 ---------------
sippoolbn10M02.infra.lync.com sipfed.online.lync.com
```

## <a name="user-has-teams-calling-policy-enabled"></a>用户已启用团队调用策略

用户的有效 TeamsCallingPolicy 必须将 AllowPrivateCalling 设置为 true。  默认情况下，用户继承全局策略，默认情况下，AllowPrivateCallingPolicy 设置为 true。

若要获取用户的 TeamsCallingPolicy，并检查 AllowPrivateCalling 是否设置为 true，请使用以下命令：

```
if (($p=(get-csonlineuser -Identity $user).TeamsCallingPolicy) -eq $null) {Get-CsTeamsCallingPolicy -Identity global} else {get-csteamscallingpolicy -Identity $p}
```

输出应如下所示：

```
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

## <a name="additional-notes"></a>其他笔记

-   在进行上述任何配置更改之后，您可能需要重新启动团队客户端。

-   如果你最近更新了上述任何条件，你可能需要等待几个小时，客户端才能接收新设置。

-   如果您仍然看不到拨号盘，请通过使用以下命令检查是否存在设置错误：

  ```
  Get-CsOnlineUser -Identity $user|Select McoValidationError
  ```

-    如果已超过24小时，但仍有问题，请联系支持人员。


