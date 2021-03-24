---
title: Microsoft Teams 设备监视和警报
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
description: 了解如何使用 Microsoft Teams 管理中心中的 Teams 监视和警报功能主动监视 Teams 设备的运行状况
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: 8c6a4ac89ddc90bcb00cf2741874e49a26ac775f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096472"
---
# <a name="microsoft-teams-device-health-monitoring"></a><span data-ttu-id="39dca-103">Microsoft Teams 设备运行状况监视</span><span class="sxs-lookup"><span data-stu-id="39dca-103">Microsoft Teams device health monitoring</span></span>

<span data-ttu-id="39dca-104">通过 Microsoft Teams 管理中心中的设备运行状况监视，可以主动监视各种 Teams 设备的运行状况。</span><span class="sxs-lookup"><span data-stu-id="39dca-104">Device health monitoring in the Microsoft Teams admin center gives you an ability to proactively monitor the health of various Teams devices.</span></span> <span data-ttu-id="39dca-105">监视设备的脱机状态，并实时接收警报（如果组织中受监视的设备处于脱机状态）。</span><span class="sxs-lookup"><span data-stu-id="39dca-105">Monitor the offline state of a device and receive alerts in real time if the monitored device in your organization goes offline.</span></span>  

<span data-ttu-id="39dca-106">在启动之前，需要租户中的团队/频道创建权限。</span><span class="sxs-lookup"><span data-stu-id="39dca-106">Before you start, you'll need the teams/channel creation permissions in your tenant.</span></span> <span data-ttu-id="39dca-107">[了解更多](/microsoft-365/solutions/manage-creation-of-groups?view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="39dca-107">[Learn More](/microsoft-365/solutions/manage-creation-of-groups?view=o365-worldwide).</span></span>

## <a name="configure-device-state-rule"></a><span data-ttu-id="39dca-108">配置设备状态规则</span><span class="sxs-lookup"><span data-stu-id="39dca-108">Configure device state rule</span></span>

1. <span data-ttu-id="39dca-109">在 Microsoft Teams 管理中心的左侧导航栏中，选择"通知&**警报**  >  **规则"。**</span><span class="sxs-lookup"><span data-stu-id="39dca-109">In the left navigation of the Microsoft Teams admin center, select **Notifications & alerts** > **Rules**.</span></span>

   ![管理中心中的"规则"部分](../media/select-rules.png)

2. <span data-ttu-id="39dca-111">在"**规则"** 页中，选择 **"设备状态规则"。**</span><span class="sxs-lookup"><span data-stu-id="39dca-111">In the **Rules** Page, select **Device state rule**.</span></span>

3. <span data-ttu-id="39dca-112">选择设备以配置用于启用警报的状态规则。</span><span class="sxs-lookup"><span data-stu-id="39dca-112">Select the device to configure the state rule for enabling alerts.</span></span>

    ![Teams 设备状态规则页面。](../media/device-state-rule.png )

## <a name="interpret-the-rule-configuration"></a><span data-ttu-id="39dca-114">解释规则配置</span><span class="sxs-lookup"><span data-stu-id="39dca-114">Interpret the rule configuration</span></span>


|<span data-ttu-id="39dca-115">字段</span><span class="sxs-lookup"><span data-stu-id="39dca-115">Field</span></span> |<span data-ttu-id="39dca-116">说明</span><span class="sxs-lookup"><span data-stu-id="39dca-116">Description</span></span>  |
|--------|-------------|
|<span data-ttu-id="39dca-117">**规则类型**</span><span class="sxs-lookup"><span data-stu-id="39dca-117">**Rule type**</span></span>   |<span data-ttu-id="39dca-118">设备状态规则可帮助你进行有效的管理。</span><span class="sxs-lookup"><span data-stu-id="39dca-118">The device state rule helps you effectively manage.</span></span> <span data-ttu-id="39dca-119">Teams 设备和 被分类为设备管理类型。</span><span class="sxs-lookup"><span data-stu-id="39dca-119">Teams devices and is classified as a device management type.</span></span> <span data-ttu-id="39dca-120">将来，更多设备管理类型的规则可用于监视其他相关功能 (例如：不正常的设备和设备登录状态) 。</span><span class="sxs-lookup"><span data-stu-id="39dca-120">In the future, more rules of device management type will be available to monitor other related capabilities (examples may include: unhealthy device and the sign-in status of device).</span></span>|
|<span data-ttu-id="39dca-121">**条件**</span><span class="sxs-lookup"><span data-stu-id="39dca-121">**Condition**</span></span>   |<span data-ttu-id="39dca-122">如果设备脱机，可以监视其运行状况。</span><span class="sxs-lookup"><span data-stu-id="39dca-122">You can monitor the health of devices if they go offline.</span></span> <span data-ttu-id="39dca-123">[详细了解 Teams](../devices/device-management.md) 管理中心中的设备管理。</span><span class="sxs-lookup"><span data-stu-id="39dca-123">[Learn more](../devices/device-management.md) about device management in Teams admin center.</span></span> |
|<span data-ttu-id="39dca-124">**范围**</span><span class="sxs-lookup"><span data-stu-id="39dca-124">**Scope**</span></span>   |<span data-ttu-id="39dca-125">可以通过提及规则评估频率来指定监视设备运行状况的频率。</span><span class="sxs-lookup"><span data-stu-id="39dca-125">You can specify how frequently you want to monitor device health status by mentioning the rule evaluation frequency.</span></span> <span data-ttu-id="39dca-126">默认情况下，团队设备在脱机时将进行近实时监视。</span><span class="sxs-lookup"><span data-stu-id="39dca-126">By default teams devices will be monitored in near real time if they go offline.</span></span> |
|<span data-ttu-id="39dca-127">**设备用户**</span><span class="sxs-lookup"><span data-stu-id="39dca-127">**Device users**</span></span>   |<span data-ttu-id="39dca-128">可以通过根据已登录的用户选择设备来指定哪些设备需要主动脱机监视。</span><span class="sxs-lookup"><span data-stu-id="39dca-128">You can specify which devices need proactive offline statue monitoring by selecting them based on signed-in users.</span></span> <span data-ttu-id="39dca-129">有关更多详细信息 [，请参阅选择](#select-devices-for-configuration) 设备进行配置。</span><span class="sxs-lookup"><span data-stu-id="39dca-129">Refer to [Select devices for configuration](#select-devices-for-configuration) for more details.</span></span> |
|<span data-ttu-id="39dca-130">**操作**  > **通道警报**</span><span class="sxs-lookup"><span data-stu-id="39dca-130">**Actions** > **Channel alert**</span></span>   |<span data-ttu-id="39dca-131">在"操作"部分中，可以指定要获取其警报的团队频道。</span><span class="sxs-lookup"><span data-stu-id="39dca-131">In the Actions section, you can specify teams channels you want to get alerts for.</span></span> <span data-ttu-id="39dca-132">目前，将创建名为 **"管理员** 警报和通知"的默认团队以及名为 **MonitoringAlerts** 的频道，通知将传递到其中。</span><span class="sxs-lookup"><span data-stu-id="39dca-132">Currently, a default team named **Admin Alerts and Notifications** and channel named **MonitoringAlerts** will be created where notifications will be delivered to.</span></span> <BR/> <BR/> <span data-ttu-id="39dca-133">租户中的全局管理员和 Teams 管理员将自动添加到此默认团队。</span><span class="sxs-lookup"><span data-stu-id="39dca-133">Global administrators and Teams administrators in your tenant will be automatically added to this default team.</span></span>|
|<span data-ttu-id="39dca-134">**操作**  > **Webhook**</span><span class="sxs-lookup"><span data-stu-id="39dca-134">**Actions** > **Webhook**</span></span>   |<span data-ttu-id="39dca-135">还可使用外部 Webhook 和可选 (接收) 。</span><span class="sxs-lookup"><span data-stu-id="39dca-135">You can also get notifications with an external webhook (optional).</span></span> <span data-ttu-id="39dca-136">在将发送 JSON 通知有效负载的 webhook 部分中指定外部公共 Webhook URL。</span><span class="sxs-lookup"><span data-stu-id="39dca-136">Specify an external public webhook URL in the webhook section where a JSON notification payload will be sent.</span></span> <BR/> <BR/>  <span data-ttu-id="39dca-137">通知有效负载（通过 Webhook）可以与组织的其他系统集成，以创建自定义工作流。</span><span class="sxs-lookup"><span data-stu-id="39dca-137">The notification payload, via webhooks, can be integrated with other systems in your organization to create custom workflows.</span></span><br/><br/> 

<span data-ttu-id="39dca-138">**Webhook 的 JSON 有效负载架构：**</span><span class="sxs-lookup"><span data-stu-id="39dca-138">**JSON payload schema for webhook:**</span></span> <BR/><BR/>
<span data-ttu-id="39dca-139"><pre lang="json">{ <br/>    "type": "object",<br>    "properties": { <br/>      "AlertTitle": { "type": "string "} ,<br/>      "DeviceLoggedInUserId": { "type": "string" } ,<br/>      "DeviceId": { "type": "string" } , <br/>      "MetricValues": { <br/>            "type": "object",<br/>            "properties": { <br/>                 "DeviceHealthStatus": { "type": "string"} <br/>            } <br/>       } ,<br/>       "RuleName": { "type": "string"} ,<br/>       "RuleDescription": { "type": "string"} ,<br/>       "RuleFrequency": { "type": "string"} ,<br/>       "RuleType": { "type": "string"} ,<br/>       "TenantId": { "type": "string"} , <br/>       "RuleCondition": { "type": "string"} , <br/>       "AlertRaisedAt": { "type": "string"} <br/>    } <br/>} </pre> <br/></span><span class="sxs-lookup"><span data-stu-id="39dca-139"><pre lang="json">{ <br/>    "type": "object",<br>    "properties": { <br/>      "AlertTitle": { "type": "string "} ,<br/>      "DeviceLoggedInUserId": { "type": "string" } ,<br/>      "DeviceId": { "type": "string" } , <br/>      "MetricValues": { <br/>            "type": "object",<br/>            "properties": { <br/>                 "DeviceHealthStatus": { "type": "string"} <br/>            } <br/>       } ,<br/>       "RuleName": { "type": "string"} ,<br/>       "RuleDescription": { "type": "string"} ,<br/>       "RuleFrequency": { "type": "string"} ,<br/>       "RuleType": { "type": "string"} ,<br/>       "TenantId": { "type": "string"} , <br/>       "RuleCondition": { "type": "string"} , <br/>       "AlertRaisedAt": { "type": "string"} <br/>    } <br/>} </pre> <br/></span></span> 

  <span data-ttu-id="39dca-140">**示例 JSON 有效负载**：</span><span class="sxs-lookup"><span data-stu-id="39dca-140">**Sample JSON payload**:</span></span><br/> <br/> <pre lang="JSON">    { <br/>      <span data-ttu-id="39dca-141">"AlertTitle":"*sample_device_name* of *User_Name* has become offline",</span><span class="sxs-lookup"><span data-stu-id="39dca-141">"AlertTitle":"*sample_device_name* of *User_Name* has become offline",</span></span><br/>      <span data-ttu-id="39dca-142">"DeviceLoggedInUserId": *User_GUID* ,</span><span class="sxs-lookup"><span data-stu-id="39dca-142">"DeviceLoggedInUserId": *User_GUID* ,</span></span><br/>      <span data-ttu-id="39dca-143">"DeviceId": *Device_GUID* , </span><span class="sxs-lookup"><span data-stu-id="39dca-143">"DeviceId": *Device_GUID* , </span></span><br/>      "MetricValues": { <br/>         DeviceHealthStatus": "offline" <br/>            }, <br/>        <br/>       "RuleName": "Device state rule" ,<br/>       "RuleDescription": ":"Alerts when device health status is detected as offline" ,<br/>       "RuleFrequency": "Real-time" ,<br/>       "RuleType": "Device Management" ,<br/>       <span data-ttu-id="39dca-144">"TenantId": *Tenant_GUID* , </span><span class="sxs-lookup"><span data-stu-id="39dca-144">"TenantId": *Tenant_GUID* , </span></span><br/>       "RuleCondition": "DeviceHealthStatus = Offline" , <br/>       "AlertRaisedAt": "2020-02-28T12:49:06Z" <br/>    }  </pre> <br/> 

## <a name="select-devices-for-configuration"></a><span data-ttu-id="39dca-145">选择要配置的设备</span><span class="sxs-lookup"><span data-stu-id="39dca-145">Select devices for configuration</span></span>

1. <span data-ttu-id="39dca-146">可以通过选择登录到这些设备的用户来选择要监视的 Teams 设备。</span><span class="sxs-lookup"><span data-stu-id="39dca-146">You can select Teams devices you want to monitor by selecting users signed in to those devices.</span></span> <span data-ttu-id="39dca-147">从 **"设备** 用户" **部分选择"添加** "。</span><span class="sxs-lookup"><span data-stu-id="39dca-147">Select **Add** from the **Device users** section.</span></span>

2. <span data-ttu-id="39dca-148">选择要监视其设备运行状况的一个或多个用户</span><span class="sxs-lookup"><span data-stu-id="39dca-148">Select one or more users for which you want to monitor device health state</span></span>

   ![在设备运行状况状态规则中添加用户。](../media/select-device-users.png )

   <span data-ttu-id="39dca-150">所选用户列表显示在"设备用户 **"** 部分。</span><span class="sxs-lookup"><span data-stu-id="39dca-150">The selected list of users shows in **Device users** section.</span></span> <span data-ttu-id="39dca-151">可以通过添加或删除用户来修改此列表。</span><span class="sxs-lookup"><span data-stu-id="39dca-151">You can modify this list by adding or removing users.</span></span>

<span data-ttu-id="39dca-152">将监视所选用户列表使用的所有登录设备是否处于脱机运行状况。</span><span class="sxs-lookup"><span data-stu-id="39dca-152">All the sign-in devices used by the selected list of users will be monitored for the offline health state.</span></span>

## <a name="notifications-in-teams-client"></a><span data-ttu-id="39dca-153">Teams 客户端中的通知</span><span class="sxs-lookup"><span data-stu-id="39dca-153">Notifications in Teams client</span></span>

<span data-ttu-id="39dca-154">通知在管理员警报和通知团队的自动创建的 **MonitoringAlerts** 通道 **中** 传递。</span><span class="sxs-lookup"><span data-stu-id="39dca-154">The notifications are delivered in the auto-created **MonitoringAlerts** channel of the **Admin Alerts and Notifications** Team.</span></span>

<span data-ttu-id="39dca-155">设备脱机通知可以包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="39dca-155">A device offline notification can include the following information:</span></span>

- <span data-ttu-id="39dca-156">处于脱机状态的设备名称。</span><span class="sxs-lookup"><span data-stu-id="39dca-156">The device name that's offline.</span></span>
- <span data-ttu-id="39dca-157">脱机设备的用户。</span><span class="sxs-lookup"><span data-stu-id="39dca-157">The user of the offline device.</span></span>
- <span data-ttu-id="39dca-158">设备脱机的时间。</span><span class="sxs-lookup"><span data-stu-id="39dca-158">What time the device went offline.</span></span> <span data-ttu-id="39dca-159"> (目前，时间以 UTC.) </span><span class="sxs-lookup"><span data-stu-id="39dca-159">(Currently, the time is presented in UTC.)</span></span>
- <span data-ttu-id="39dca-160">引发警报的规则类型。</span><span class="sxs-lookup"><span data-stu-id="39dca-160">The type of rule that raised the alert.</span></span>
- <span data-ttu-id="39dca-161">引发警报的原因。</span><span class="sxs-lookup"><span data-stu-id="39dca-161">Why an alert is raised.</span></span>