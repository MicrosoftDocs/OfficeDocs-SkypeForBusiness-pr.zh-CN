---
title: Microsoft Teams设备监视和警报
author: cazawideh
ms.author: czawideh
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: vapati
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
description: 了解如何在Microsoft Teams管理中心使用Teams监视和警报功能主动监视Teams设备的运行状况
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: 22b67a0c046c3abb0643503948d67b77abb0e690
ms.sourcegitcommit: f3c380f745af4c3aaa2720234860b45696a0c333
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2022
ms.locfileid: "64737611"
---
# <a name="microsoft-teams-device-health-monitoring"></a>Microsoft Teams设备运行状况监视

Microsoft Teams管理中心的设备运行状况监视使你能够主动监视各种Teams设备的运行状况。 监视设备的脱机状态，并在组织中受监视的设备脱机时实时接收警报。  

在开始之前，需要租户中的团队/频道创建权限。 [了解详细信息](/microsoft-365/solutions/manage-creation-of-groups?view=o365-worldwide)。

## <a name="configure-device-state-rule"></a>配置设备状态规则

1. 在Microsoft Teams管理中心的左侧导航中，选择 **“通知”& alertsRules** > 。

   ![管理中心的“规则”部分。](../media/select-rules.png)

2. 在 **“规则** ”页中，选择 **“设备状态”规则**。

3. 选择要配置状态规则以启用警报的设备。

    ![Teams设备状态规则页。](../media/device-state-rule.png )

## <a name="interpret-the-rule-configuration"></a>解释规则配置


|字段 |说明  |
|--------|-------------|
|**规则类型**   |设备状态规则可帮助你有效地进行管理。 Teams设备，并分类为设备管理类型。 将来，将有更多的设备管理类型的规则可用于监视其他相关功能 (示例可能包括：不正常的设备和设备) 的登录状态。|
|**条件**   |如果设备脱机，则可以监视设备的运行状况。 [详细了解](../devices/device-management.md)Teams管理中心的设备管理。 |
|**范围**   |可以通过提及规则评估频率来指定监视设备运行状况的频率。 默认情况下，如果团队设备脱机，将近乎实时地进行监视。 |
|**设备用户**   |可以通过根据已登录用户选择设备来指定需要主动脱机雕像监视的设备。 有关更多详细信息，请参阅 [“选择设备”进行配置](#select-devices-for-configuration) 。 |
|**行动** > **通道警报**   |在“操作”部分中，可以指定要获取警报的团队通道。 目前，将创建一个名为“ **管理警报”和“通知”的** 默认团队，以及名为 **MonitoringAlerts 的** 通道，将通知传送到其中。 <BR/> <BR/> 租户中的全局管理员和Teams管理员将自动添加到此默认团队。|
|**行动** > **Webhook**   |还可以使用外部 Webhook (可选) 获取通知。 在将发送 JSON 通知有效负载的 Webhook 部分中指定外部公共 Webhook URL。 <BR/> <BR/>  通过 Webhook 的通知有效负载可以与组织中的其他系统集成，以创建自定义工作流。<br/><br/> 

**Webhook 的 JSON 有效负载架构：** <BR/><BR/>
<pre lang="json">{ <br/>    "type": "object",<br>    "properties": { <br/>      "AlertTitle": { "type": "string "} ,<br/>      "DeviceLoggedInUserId": { "type": "string" } ,<br/>      "DeviceId": { "type": "string" } , <br/>      "MetricValues": { <br/>            "type": "object",<br/>            "properties": { <br/>                 "DeviceHealthStatus": { "type": "string"} <br/>            } <br/>       } ,<br/>       "RuleName": { "type": "string"} ,<br/>       "RuleDescription": { "type": "string"} ,<br/>       "RuleFrequency": { "type": "string"} ,<br/>       "RuleType": { "type": "string"} ,<br/>       "TenantId": { "type": "string"} , <br/>       "RuleCondition": { "type": "string"} , <br/>       "AlertRaisedAt": { "type": "string"} <br/>    } <br/>} </pre> <br/> 

  **示例 JSON 有效负载**：<br/> <br/> <pre lang="JSON">    { <br/>      "AlertTitle":"*sample_device_name* of *User_Name* has become offline",<br/>      "DeviceLoggedInUserId": *User_GUID* ,<br/>      "DeviceId": *Device_GUID* , <br/>      "MetricValues": { <br/>         "DeviceHealthStatus": "offline" <br/>            }, <br/>        <br/>       "RuleName": "Device state rule" ,<br/>       "RuleDescription": "Alerts when device health status is detected as offline" ,<br/>       "RuleFrequency": "Real-time" ,<br/>       "RuleType": "Device Management" ,<br/>       "TenantId": *Tenant_GUID* , <br/>       "RuleCondition": "DeviceHealthStatus = Offline" , <br/>       "AlertRaisedAt": "2020-02-28T12:49:06Z" <br/>    }  </pre> <br/> 

## <a name="select-devices-for-configuration"></a>选择设备进行配置

1. 可以选择登录到这些设备的用户，选择要监视的Teams设备。 从 **“设备用户**”部分选择 **“添加**”。

2. 选择要监视其设备运行状况状态的一个或多个用户

   ![在设备运行状况状态规则中添加用户。](../media/select-device-users.png )

   所选用户列表显示在 **“设备用户”** 部分。 可以通过添加或删除用户来修改此列表。

将监视所选用户列表使用的所有登录设备是否处于脱机运行状况状态。

## <a name="notifications-in-teams-client"></a>Teams客户端中的通知

通知在 **管理警报和通知** 团队的自动创建的 **MonitoringAlerts** 通道中传递。 你将在设备脱机后 15 分钟内收到警报。 

设备脱机通知可以包含以下信息：

- 脱机的设备名称。
- 脱机设备的用户。
- 设备脱机时间。  (目前，时间显示在 UTC.) 
- 引发警报的规则的类型。
- 引发警报的原因。
