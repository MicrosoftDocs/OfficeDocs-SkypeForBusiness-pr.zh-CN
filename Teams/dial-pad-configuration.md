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
# <a name="dial-pad-configuration"></a><span data-ttu-id="e9c47-103">拨号键盘配置</span><span class="sxs-lookup"><span data-stu-id="e9c47-103">Dial pad configuration</span></span>

<span data-ttu-id="e9c47-104">在 "团队客户端" 中，拨号盘使用户能够访问公共交换式电话网络（PSTN）功能。</span><span class="sxs-lookup"><span data-stu-id="e9c47-104">In the Teams client, the dial pad enables users to access Public Switched Telephone Network (PSTN) functionality.</span></span> <span data-ttu-id="e9c47-105">如果用户配置正确，则使用电话系统许可证的用户可以使用拨号盘。</span><span class="sxs-lookup"><span data-stu-id="e9c47-105">The dial pad is available for users with a Phone System license, provided they are configured properly.</span></span> <span data-ttu-id="e9c47-106">要显示拨号盘，需要以下条件：</span><span class="sxs-lookup"><span data-stu-id="e9c47-106">The following criteria are all required for the dial pad to show:</span></span>

- <span data-ttu-id="e9c47-107">用户拥有一个已启用的电话系统（"MCOEV"）许可证</span><span class="sxs-lookup"><span data-stu-id="e9c47-107">User has an enabled Phone System (“MCOEV”) license</span></span>
- <span data-ttu-id="e9c47-108">用户具有 Microsoft 通话计划或已启用直接路由</span><span class="sxs-lookup"><span data-stu-id="e9c47-108">User has Microsoft Calling Plan or is enabled for Direct Routing</span></span>
- <span data-ttu-id="e9c47-109">用户已启用企业语音</span><span class="sxs-lookup"><span data-stu-id="e9c47-109">User has Enterprise Voice enabled</span></span>
- <span data-ttu-id="e9c47-110">用户处于联机状态，而不是在本地 Skype for Business 中</span><span class="sxs-lookup"><span data-stu-id="e9c47-110">User is homed online and not in Skype for Business on premises</span></span>
- <span data-ttu-id="e9c47-111">用户已启用团队调用策略</span><span class="sxs-lookup"><span data-stu-id="e9c47-111">User has Teams Calling Policy enabled</span></span>

<span data-ttu-id="e9c47-112">以下部分介绍了如何使用 PowerShell 检查条件。</span><span class="sxs-lookup"><span data-stu-id="e9c47-112">The following sections describe how to use PowerShell to check the criteria.</span></span> <span data-ttu-id="e9c47-113">在大多数情况下，你需要在 CsOnlineUser cmdlet 的输出中查看各种属性。</span><span class="sxs-lookup"><span data-stu-id="e9c47-113">In most cases, you need to look at various properties in the output of the Get-CsOnlineUser cmdlet.</span></span> <span data-ttu-id="e9c47-114">示例假设 $user 是用户的 UPN 或 sip 地址。</span><span class="sxs-lookup"><span data-stu-id="e9c47-114">Examples assume $user is either the UPN or sip address of the user.</span></span>

## <a name="user-has-an-enabled-phone-system-mcoev-license"></a><span data-ttu-id="e9c47-115">用户拥有一个已启用的电话系统（"MCOEV"）许可证</span><span class="sxs-lookup"><span data-stu-id="e9c47-115">User has an enabled Phone System (“MCOEV”) license</span></span>

<span data-ttu-id="e9c47-116">必须确保为用户分配的计划显示 " **CapabilityStatus" 属性设置为 "已启用**"，并且**功能计划设置为 "MCOEV** " （电话系统许可证）。</span><span class="sxs-lookup"><span data-stu-id="e9c47-116">You must ensure that the assigned plan for the user shows the **CapabilityStatus attribute set to Enabled** and the **Capability Plan set to MCOEV** (Phone System license).</span></span> <span data-ttu-id="e9c47-117">您可能会看到 MCOEV、MCOEV1 等。</span><span class="sxs-lookup"><span data-stu-id="e9c47-117">You might see MCOEV, MCOEV1, and so on.</span></span> <span data-ttu-id="e9c47-118">所有功能均可接受-只要功能计划以 MCOEV 开始。</span><span class="sxs-lookup"><span data-stu-id="e9c47-118">All are acceptable--as long as the Capability Plan starts with MCOEV.</span></span>

<span data-ttu-id="e9c47-119">若要检查属性是否设置正确，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="e9c47-119">To check that the attributes are set correctly, use the following command:</span></span>

```
Get-CsOnlineUser -Identity $user|select AssignedPlan|fl
```

<span data-ttu-id="e9c47-120">输出将如下所示。</span><span class="sxs-lookup"><span data-stu-id="e9c47-120">The output will look like the following.</span></span> <span data-ttu-id="e9c47-121">您只需要检查**CapabilityStatus**和**功能计划**属性：</span><span class="sxs-lookup"><span data-stu-id="e9c47-121">You only need to check the **CapabilityStatus** and the **Capability Plan** attributes:</span></span>

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


## <a name="user-has-microsoft-calling-plan-or-is-enabled-for-direct-routing"></a><span data-ttu-id="e9c47-122">用户具有 Microsoft 通话计划或已启用直接路由</span><span class="sxs-lookup"><span data-stu-id="e9c47-122">User has Microsoft Calling Plan OR is enabled for Direct Routing</span></span>

<span data-ttu-id="e9c47-123">**如果用户具有 Microsoft 通话计划**，则必须确保**CapabilityStatus 属性设置为 "已启用**"，并且**功能计划设置为 "MCOPSTN**"。</span><span class="sxs-lookup"><span data-stu-id="e9c47-123">**If the user has Microsoft Calling Plan**, you must ensure that the **CapabilityStatus attribute is set to Enabled**, and that the **Capability Plan is set to MCOPSTN**.</span></span> <span data-ttu-id="e9c47-124">您可能会看到 MCOPSTN1、MCOPSTN2 等。</span><span class="sxs-lookup"><span data-stu-id="e9c47-124">You might see MCOPSTN1, MCOPSTN2, and so on.</span></span> <span data-ttu-id="e9c47-125">所有功能均可接受-只要功能计划以 MCOPSTN 开始。</span><span class="sxs-lookup"><span data-stu-id="e9c47-125">All are acceptable--as long as the Capability Plan starts with MCOPSTN.</span></span>

<span data-ttu-id="e9c47-126">若要检查属性，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="e9c47-126">To check the attributes, use the following command:</span></span>

```
Get-CsOnlineUser -Identity $user|select AssignedPlan|fl
```

<span data-ttu-id="e9c47-127">输出将如下所示。</span><span class="sxs-lookup"><span data-stu-id="e9c47-127">The output will look like the following.</span></span> <span data-ttu-id="e9c47-128">您只需要检查**CapabilityStatus**和**功能计划**属性：</span><span class="sxs-lookup"><span data-stu-id="e9c47-128">You only need to check the **CapabilityStatus** and the **Capability Plan** attributes:</span></span>

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

<span data-ttu-id="e9c47-129">**如果用户已启用直接路由**，则必须为该用户分配 OnlineVoiceRoutingPolicy 的非 null 值。</span><span class="sxs-lookup"><span data-stu-id="e9c47-129">**If the user is enabled for Direct Routing**, the user must be assigned a non-null value for OnlineVoiceRoutingPolicy.</span></span> <span data-ttu-id="e9c47-130">若要检查属性，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="e9c47-130">To check the attribute, use the following command:</span></span>
  
```
Get-CsOnlineUser -Identity $user|Select OnlineVoiceRoutingPolicy 
```

<span data-ttu-id="e9c47-131">输出应具有非 null 值，例如：</span><span class="sxs-lookup"><span data-stu-id="e9c47-131">The output should have a non-null value, for example:</span></span>

```
OnlineVoiceRoutingPolicy
------------------------
Test_Policy
```

## <a name="user-has-enterprise-voice-enabled"></a><span data-ttu-id="e9c47-132">用户已启用企业语音</span><span class="sxs-lookup"><span data-stu-id="e9c47-132">User has Enterprise Voice enabled</span></span>

<span data-ttu-id="e9c47-133">若要检查用户是否已启用企业语音，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="e9c47-133">To check if the user has Enterprise Voice enabled, use the following command:</span></span>

```
Get-CsOnlineUser -Identity $user|Select EnterpriseVoiceEnabled
```

<span data-ttu-id="e9c47-134">输出应如下所示：</span><span class="sxs-lookup"><span data-stu-id="e9c47-134">The output should look like:</span></span>

```
EnterpriseVoiceEnabled
----------------------
                  True

```
 
## <a name="user-is-homed-online-and-not-in-skype-for-business-on-premises"></a><span data-ttu-id="e9c47-135">用户处于联机状态，而不是在本地 Skype for Business 中</span><span class="sxs-lookup"><span data-stu-id="e9c47-135">User is homed online and not in Skype for Business on premises</span></span>

<span data-ttu-id="e9c47-136">若要确保用户在本地托管，而不是在本地 Skype for business 中，RegistrarPool 不得为 null，并且 HostingProvider 必须包含以 "sipfed." 开头的值。</span><span class="sxs-lookup"><span data-stu-id="e9c47-136">To ensure the user is homed online and not in Skype for Business on premises, the RegistrarPool must not be null and the HostingProvider must contain a value that starts with “sipfed.online.”</span></span>  <span data-ttu-id="e9c47-137">若要检查值，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="e9c47-137">To check the values, use the following command:</span></span>

```
Get-CsOnlineUser -Identity $user|Select RegistrarPool, HostingProvider
```

<span data-ttu-id="e9c47-138">输出应类似于：</span><span class="sxs-lookup"><span data-stu-id="e9c47-138">The output should be similar to:</span></span>

```
RegistrarPool                 HostingProvider
-------------                 ---------------
sippoolbn10M02.infra.lync.com sipfed.online.lync.com
```

## <a name="user-has-teams-calling-policy-enabled"></a><span data-ttu-id="e9c47-139">用户已启用团队调用策略</span><span class="sxs-lookup"><span data-stu-id="e9c47-139">User has Teams Calling Policy enabled</span></span>

<span data-ttu-id="e9c47-140">用户的有效 TeamsCallingPolicy 必须将 AllowPrivateCalling 设置为 true。</span><span class="sxs-lookup"><span data-stu-id="e9c47-140">The user’s effective TeamsCallingPolicy must have AllowPrivateCalling set to true.</span></span>  <span data-ttu-id="e9c47-141">默认情况下，用户继承全局策略，默认情况下，AllowPrivateCallingPolicy 设置为 true。</span><span class="sxs-lookup"><span data-stu-id="e9c47-141">By default, users inherit the global policy, which has AllowPrivateCallingPolicy set to true by default.</span></span>

<span data-ttu-id="e9c47-142">若要获取用户的 TeamsCallingPolicy，并检查 AllowPrivateCalling 是否设置为 true，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="e9c47-142">To get the TeamsCallingPolicy for a user and to check that AllowPrivateCalling is set to true, use the following command:</span></span>

```
if (($p=(get-csonlineuser -Identity $user).TeamsCallingPolicy) -eq $null) {Get-CsTeamsCallingPolicy -Identity global} else {get-csteamscallingpolicy -Identity $p}
```

<span data-ttu-id="e9c47-143">输出应如下所示：</span><span class="sxs-lookup"><span data-stu-id="e9c47-143">The output should look like:</span></span>

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

## <a name="additional-notes"></a><span data-ttu-id="e9c47-144">其他笔记</span><span class="sxs-lookup"><span data-stu-id="e9c47-144">Additional notes</span></span>

-   <span data-ttu-id="e9c47-145">在进行上述任何配置更改之后，您可能需要重新启动团队客户端。</span><span class="sxs-lookup"><span data-stu-id="e9c47-145">You may need to restart the Teams client after making any of these configuration changes.</span></span>

-   <span data-ttu-id="e9c47-146">如果你最近更新了上述任何条件，你可能需要等待几个小时，客户端才能接收新设置。</span><span class="sxs-lookup"><span data-stu-id="e9c47-146">If you recently updated any of the above criteria, you may need to wait a few hours for the client to receive the new settings.</span></span>

-   <span data-ttu-id="e9c47-147">如果您仍然看不到拨号盘，请通过使用以下命令检查是否存在设置错误：</span><span class="sxs-lookup"><span data-stu-id="e9c47-147">If you still don’t see the dial pad, check if there is a provisioning error by using the following command:</span></span>

  ```
  Get-CsOnlineUser -Identity $user|Select McoValidationError
  ```

-    <span data-ttu-id="e9c47-148">如果已超过24小时，但仍有问题，请联系支持人员。</span><span class="sxs-lookup"><span data-stu-id="e9c47-148">If it has been more than 24 hours and you are still seeing problems, contact Support.</span></span>

