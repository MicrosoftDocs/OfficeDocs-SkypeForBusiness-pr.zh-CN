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
description: 了解如何在客户端中配置拨号盘Teams，以便用户可以使用 PSTN (电话) 网络。
ms.openlocfilehash: 6f67aeda059505ec5c1e78d117407f0e9703f732
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58627614"
---
# <a name="dial-pad-configuration"></a>拨号盘配置

在 Teams 客户端中，拨号盘允许用户使用 PSTN (公用电话) 网络。 拨号盘可供具有 电话系统许可证的用户使用，但必须正确配置。 拨号盘需要满足以下条件才能显示：

- 用户具有已启用电话系统 ("MCOEV") 许可证
- 用户具有 Microsoft 呼叫计划或已启用直接路由
- 用户已启用企业语音
- 用户是联机的，而不是Skype for Business本地
- 用户已启用Teams策略

以下部分介绍如何使用 PowerShell 检查条件。 在大多数情况下，需要查看 Get-CsOnlineUser cmdlet 的输出中的各种属性。 示例假定$user是用户的 UPN 或 sip 地址。

## <a name="user-has-an-enabled-phone-system-mcoev-license"></a>用户具有已启用电话系统 ("MCOEV") 许可证

必须确保为用户分配的计划显示设置为 Enabled 的 **CapabilityStatus** 属性，并将"功能计划"设置为 **"MCOEV" (电话系统** 许可证) 。 可能会看到 MCOEV、MCOEV1 等。 只要功能计划以 MCOEV 开头，所有都是可接受的。

若要检查属性是否正确设置，请使用以下命令：

```
Get-CsOnlineUser -Identity $user|select AssignedPlan|fl
```

输出如下所示。 只需检查 **CapabilityStatus** 和 **功能计划** 属性：

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


## <a name="user-has-microsoft-calling-plan-or-is-enabled-for-direct-routing"></a>用户具有 Microsoft 呼叫计划或已启用直接路由

**如果用户具有 Microsoft 呼叫计划**，则必须确保 **CapabilityStatus** 属性设置为"已启用"，并且"功能 **计划"设置为"MCOPSTN"。** 可能会看到 MCOPSTN1、MCOPSTN2 等。 只要功能计划以 MCOPSTN 开头，所有都是可接受的。

若要检查属性，请使用以下命令：

```
Get-CsOnlineUser -Identity $user|select AssignedPlan|fl
```

输出如下所示。 只需检查 **CapabilityStatus** 和 **功能计划** 属性：

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

**如果为用户启用了直接路由**，则必须为用户分配 OnlineVoiceRoutingPolicy 的非 null 值。 若要检查 属性，请使用以下命令：
  
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
 
## <a name="user-is-homed-online-and-not-in-skype-for-business-on-premises"></a>用户是联机的，而不是Skype for Business本地

为了确保用户联机托管，而不是在本地Skype for Business，RegistrarPool 不得为 null，HostingProvider 必须包含以"sipfed.online"开头的值。  若要检查值，请使用以下命令：

```
Get-CsOnlineUser -Identity $user|Select RegistrarPool, HostingProvider
```

输出应类似于：

```
RegistrarPool                 HostingProvider
-------------                 ---------------
sippoolbn10M02.infra.lync.com sipfed.online.lync.com
```

## <a name="user-has-teams-calling-policy-enabled"></a>用户已启用Teams策略

用户的有效 TeamsCallingPolicy 必须将 AllowPrivateCalling 设置为 true。  默认情况下，用户继承全局策略，默认情况下，该策略将 AllowPrivateCallingPolicy 设置为 true。

若要获取用户的 TeamsCallingPolicy 并检查 AllowPrivateCalling 是否设置为 true，请使用以下命令：

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

## <a name="additional-notes"></a>其他说明

-   进行上述任何配置更改Teams重启客户端。

-   如果最近更新了上述任何条件，可能需要等待几个小时，客户端才能收到新设置。

-   如果仍未看到拨号盘，请通过以下命令检查是否有预配错误：

  ```
  Get-CsOnlineUser -Identity $user|Select McoValidationError
  ```

-    如果已超过 24 小时，但仍遇到问题，请联系支持人员。


