---
title: Microsoft Teams设备监视和警报
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: vapati
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
description: 了解如何使用 Teams 管理中心中的 Microsoft Teams 监视和警报功能主动监视 Teams 设备的运行状况
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: cca6be8274d26efe661a7a928ebb568aa054cfab2fb62206ee8f3649b37f4ea0
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54336183"
---
# <a name="microsoft-teams-device-health-monitoring"></a>Microsoft Teams设备运行状况监视

通过管理中心中的Microsoft Teams运行状况监视，你可以主动监视各种设备Teams运行状况。 监视设备的脱机状态，并实时接收警报（如果组织中受监视的设备脱机）。  

在启动之前，你将需要租户中的团队/频道创建权限。 [了解更多信息](/microsoft-365/solutions/manage-creation-of-groups?view=o365-worldwide)。

## <a name="configure-device-state-rule"></a>配置设备状态规则

1. 在管理中心的左侧导航Microsoft Teams，选择"通知&**规则**  >  **"。**

   ![管理中心的规则部分](../media/select-rules.png)

2. 在"**规则"** 页中，选择 **"设备状态规则"。**

3. 选择设备以配置用于启用警报的状态规则。

    ![Teams设备状态规则页。](../media/device-state-rule.png )

## <a name="interpret-the-rule-configuration"></a>解释规则配置


|字段 |说明  |
|--------|-------------|
|**规则类型**   |设备状态规则可帮助你有效管理。 Teams设备，并归类为设备管理类型。 将来，设备管理类型的更多规则可用于监视其他相关功能 (示例可能包括：不正常设备和设备登录) 。|
|**Condition**   |如果设备脱机，你可以监视设备的运行状况。 [详细了解管理](../devices/device-management.md)中心中的Teams管理。 |
|**Scope**   |可以通过提及规则评估频率来指定要监视设备运行状况的频率。 默认情况下，如果团队设备脱机，将几乎实时监视这些设备。 |
|**设备用户**   |你可以根据登录用户选择哪些设备来指定需要主动脱机监视的设备。 有关更多详细信息 [，请参阅选择](#select-devices-for-configuration) 设备进行配置。 |
|**操作**  > **频道警报**   |在"操作"部分，可以指定要获取警报的团队频道。 目前，将创建名为 **"管理员警报和** 通知"的默认团队和名为 **MonitoringAlerts** 的频道，通知将传递到其中。 <BR/> <BR/> 将自动将Teams中的全局管理员和管理员添加到此默认团队。|
|**操作**  > **Webhook**   |您还可以通过外部 Webhook 和可选 (获取) 。 在将发送 JSON 通知负载的 webhook 部分中指定外部公共 webhook URL。 <BR/> <BR/>  通知有效负载（通过 webhook）可以与组织的其他系统集成以创建自定义工作流。<br/><br/> 

**Webhook 的 JSON 有效负载架构：** <BR/><BR/>
<pre lang="json">{ <br/>    "type": "object",<br>    "properties": { <br/>      "AlertTitle": { "type": "string "} ,<br/>      "DeviceLoggedInUserId": { "type": "string" } ,<br/>      "DeviceId": { "type": "string" } , <br/>      "MetricValues": { <br/>            "type": "object",<br/>            "properties": { <br/>                 "DeviceHealthStatus": { "type": "string"} <br/>            } <br/>       } ,<br/>       "RuleName": { "type": "string"} ,<br/>       "RuleDescription": { "type": "string"} ,<br/>       "RuleFrequency": { "type": "string"} ,<br/>       "RuleType": { "type": "string"} ,<br/>       "TenantId": { "type": "string"} , <br/>       "RuleCondition": { "type": "string"} , <br/>       "AlertRaisedAt": { "type": "string"} <br/>    } <br/>} </pre> <br/> 

  **示例 JSON 有效负载**：<br/> <br/> <pre lang="JSON">    { <br/>      "AlertTitle":"*sample_device_name* of *User_Name* has become offline",<br/>      "DeviceLoggedInUserId": *User_GUID* ,<br/>      "DeviceId": *Device_GUID* , <br/>      "MetricValues": { <br/>         DeviceHealthStatus": "offline" <br/>            }, <br/>        <br/>       "RuleName": "Device state rule" ,<br/>       "RuleDescription": ":"Alerts when device health status is detected as offline" ,<br/>       "RuleFrequency": "Real-time" ,<br/>       "RuleType": "Device Management" ,<br/>       "TenantId": *Tenant_GUID* , <br/>       "RuleCondition": "DeviceHealthStatus = Offline" , <br/>       "AlertRaisedAt": "2020-02-28T12:49:06Z" <br/>    }  </pre> <br/> 

## <a name="select-devices-for-configuration"></a>选择设备进行配置

1. 通过选择Teams设备的用户，可以选择要监视的设备。 从 **设备** 用户 **部分选择添加** 。

2. 选择要监视其设备运行状况的一个或多个用户

   ![在设备运行状况状态规则中添加用户。](../media/select-device-users.png )

   所选用户列表显示在"设备用户 **"** 部分。 可以通过添加或删除用户来修改此列表。

所选用户列表使用的所有登录设备都将受到监视，以便处于脱机运行状况状态。

## <a name="notifications-in-teams-client"></a>Teams中的通知

通知在管理员通知和通知团队的自动创建的 **MonitoringAlerts** **频道中** 传递。

设备脱机通知可以包含以下信息：

- 处于脱机状态的设备名称。
- 脱机设备的用户。
- 设备脱机的时间。  (当前，时间以 UTC.) 
- 引发警报的规则类型。
- 引发警报的原因。