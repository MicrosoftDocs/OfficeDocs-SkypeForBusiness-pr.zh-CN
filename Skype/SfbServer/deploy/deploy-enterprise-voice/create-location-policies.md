---
title: 为 Business Server Skype 创建位置策略
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f1878194-c756-4794-8fa1-15dd2118b4b3
description: 阅读本主题可了解如何配置 Business Server 企业语音的增强型紧急服务 (E9-1-1) 在 Skype 的位置策略。
ms.openlocfilehash: 2e3c25586c09e8cb517f781ec9e9dc33c58d81da
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30897982"
---
# <a name="create-location-policies-in-skype-for-business-server"></a>为 Business Server Skype 创建位置策略

阅读本主题可了解如何配置 Business Server 企业语音的增强型紧急服务 (E9-1-1) 在 Skype 的位置策略。 

Skype 业务服务器使用位置策略 Skype 启用客户端注册期间业务客户端 E9-1-1。 位置策略包含定义 E9-1-1 实现方式的设置。 有关详细信息，请参阅[Plan for Business Server Skype 的位置策略](../../plan-your-deployment/enterprise-voice-solution/location-policies.md)。

使用适用于业务 Control Panel Skype 或使用[New-cslocationpolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) cmdlet 定义位置策略。

> [!NOTE]
> Skype 业务服务器现在支持的客户端的多个紧急号码的配置。 如果您想要配置多个紧急号码，则必须按照[Skype 业务服务器中的多个紧急号码规划](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md)和[配置 Skype for Business 中的多个紧急号码](configure-multiple-emergency-numbers.md)中的信息。 

可以编辑全局位置策略，并创建新的带标记的位置策略。客户端所在的子网没有关联位置策略，或没有直接为客户端分配位置策略时，客户端会获取全局策略。向子网或用户分配带标记的策略。 

要创建位置策略，必须使用 RTCUniversalServerAdmins 组成员或 CsVoiceAdministrator 管理角色成员的帐户，或者具有等效管理员权限的帐户。

有关详细信息，请参阅[Plan for Business Server Skype 的位置策略](../../plan-your-deployment/enterprise-voice-solution/location-policies.md)。 此过程中的 Cmdlet 使用通过下列值定义的位置策略。 Cmdlet 参数和值的完整说明，请参阅[New-cslocationpolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps)。


| **元素**                               | **值**                                                                                                                                                                          |
|:------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| EnhancedEmergencyServicesEnabled  <br/>   | **True** <br/>                                                                                                                                                                     |
| LocationRequired  <br/>                   | **免责声明** <br/>                                                                                                                                                               |
| EnhancedEmergencyServiceDisclaimer  <br/> | 您的公司策略要求您设置一个位置。如果不设置位置，紧急情况下，紧急服务将无法找到您。请设置一个位置。  <br/> |
| UseLocationForE911Only  <br/>             | **False** <br/>                                                                                                                                                                    |
| PstnUsage  <br/>                          | **EmergencyUsage** <br/>                                                                                                                                                           |
| EmergencyDialString  <br/>                | **911** <br/>                                                                                                                                                                      |
| EmergencyDialMask  <br/>                  | **112** <br/>                                                                                                                                                                      |
| NotificationUri  <br/>                    | <strong>sip:security@litwareinc.com</strong> <br/>                                                                                                                                 |
| ConferenceUri  <br/>                      | <strong>sip:+14255550123@litwareinc.com</strong> <br/>                                                                                                                             |
| ConferenceMode  <br/>                     | **twoway** <br/>                                                                                                                                                                   |
| LocationRefreshInterval  <br/>            | **2** <br/>                                                                                                                                                                        |

### <a name="to-create-location-policies"></a>创建位置策略

1. 启动 Skype for Business Server 命令行管理程序：依次单击“开始”****、“所有程序”**** 和“Skype for Business 2015”****，然后单击“Skype for Business Server 命令行管理程序”****。

    > [!NOTE]
    > 如果 PstnUsages 的全局列表中还没有 **PstnUsage** 设置，则 CsLocationPolicy 会失败。

2. 也可以选择运行以下 cmdlet 编辑全局位置策略：

   ```
   Set-CsLocationPolicy -Identity Global -EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -PstnUsage "emergencyUsage" -EmergencyDialString "911" -ConferenceMode "twoway" -ConferenceUri "sip:+14255550123@litwareinc.com" -EmergencyDialMask "112" NotificationUri "sip:security@litwareinc.com" -UseLocationForE911Only $true -LocationRefreshInterval 2
   ```

3. 运行以下命令创建带标记的位置策略。

   ```
   New-CsLocationPolicy -Identity Tag:Redmond - EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -UseLocationForE911Only $false -PstnUsage "EmergencyUsage" -EmergencyDialString "911" -EmergencyDialMask "112" -NotificationUri "sip:security@litwareinc.com" -ConferenceUri "sip:+14255550123@litwareinc.com" -ConferenceMode "twoway" -LocationRefreshInterval 2
   ```

4. 运行以下 cmdlet 将步骤 3 中创建的带标记的位置策略应用于用户策略。

   ```
   (Get-CsUser | where { $_.Name -match "UserName" }) | Grant-CsLocationPolicy -PolicyName Redmond
   ```
