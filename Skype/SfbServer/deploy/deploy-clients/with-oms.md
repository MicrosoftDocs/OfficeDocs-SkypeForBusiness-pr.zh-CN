---
title: 使用 OMS 部署 Skype 会议室系统 v2 管理
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 4/20/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d86ff657-ee92-4b06-aee3-d4c43090bdcb
description: 本文讨论如何在使用 Microsoft 操作管理套件集成的端到端方式中部署的 Skype 会议室系统 v2 设备管理。
ms.openlocfilehash: 7d8dc8a7e7f5a74c68fbc7bf5ecb98664c2b02ad
ms.sourcegitcommit: 1cb8ab7d1e3debb84f051be404403e4a116ee741
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/21/2018
---
# <a name="deploy-skype-room-systems-v2-management-with-oms"></a><span data-ttu-id="a77f7-103">使用 OMS 部署 Skype 会议室系统 v2 管理</span><span class="sxs-lookup"><span data-stu-id="a77f7-103">Deploy Skype Room Systems v2 management with OMS</span></span>
 
<span data-ttu-id="a77f7-104">本文讨论如何设置和使用 Microsoft 操作管理套件部署 Skype 会议室系统 v2 设备的集成的端到端管理。</span><span class="sxs-lookup"><span data-stu-id="a77f7-104">This article discusses how to set up and deploy integrated, end-to-end management of Skype Room Systems v2 devices by using Microsoft Operations Management Suite.</span></span>
  
<span data-ttu-id="a77f7-105">您可以配置 Microsoft 操作管理套件提供基本的遥测和通知将帮助您管理 Skype 会议室内设备。</span><span class="sxs-lookup"><span data-stu-id="a77f7-105">You can configure Microsoft Operations Management Suite to provide basic telemetry and alerts that will help you manage Skype meeting room devices.</span></span> <span data-ttu-id="a77f7-106">随着您管理解决方案逐渐成熟，您可能决定部署其他数据和管理功能，以创建设备的可用性和性能的详细的视图。</span><span class="sxs-lookup"><span data-stu-id="a77f7-106">As your management solution matures, you might decide to deploy additional data and management capabilities to create a more detailed view of device availability and performance.</span></span>

<span data-ttu-id="a77f7-107">按照本指南，您可以使用类似下面的示例仪表板获取设备可用性、 应用程序和硬件运行状况和 Skype 会议室系统 v2 应用程序版本分发报告的详细的状态。</span><span class="sxs-lookup"><span data-stu-id="a77f7-107">By following this guide, you can use a dashboard like the following example to get detailed status reporting for device availability, application and hardware health, and Skype Room Systems v2 application version distribution.</span></span>

<span data-ttu-id="a77f7-108">![示例 OMS 视图 SR v2](../../media/Deploy_OMS_1.png "示例 OMS 视图 SR v2")</span><span class="sxs-lookup"><span data-stu-id="a77f7-108">![Sample OMS view for SRS v2](../../media/Deploy_OMS_1.png "Sample OMS view for SRS v2")</span></span>
  
<span data-ttu-id="a77f7-109">你需要在高级别执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="a77f7-109">At a high level, you need to perform the following tasks:</span></span>


1.  [<span data-ttu-id="a77f7-110">验证操作管理套件配置</span><span class="sxs-lookup"><span data-stu-id="a77f7-110">Validate Operations Management Suite configuration</span></span>](with-oms.md#validate_OMS)
2.  [<span data-ttu-id="a77f7-111">配置操作管理套件管理安装程序测试设备</span><span class="sxs-lookup"><span data-stu-id="a77f7-111">Configure test devices for Operations Management Suite management setup</span></span>](with-oms.md#configure_test_devices)
3.  [<span data-ttu-id="a77f7-112">映射自定义字段</span><span class="sxs-lookup"><span data-stu-id="a77f7-112">Map custom fields</span></span>](with-oms.md#Custom_fields)
4.  [<span data-ttu-id="a77f7-113">操作管理套件中定义的 Skype 会议室系统 v2 视图</span><span class="sxs-lookup"><span data-stu-id="a77f7-113">Define the Skype Room Systems v2 views in Operations Management Suite</span></span>](with-oms.md#Define_Views)
5.  [<span data-ttu-id="a77f7-114">定义通知</span><span class="sxs-lookup"><span data-stu-id="a77f7-114">Define alerts</span></span>](with-oms.md#Alerts)
6.  [<span data-ttu-id="a77f7-115">配置所有设备的操作管理套件</span><span class="sxs-lookup"><span data-stu-id="a77f7-115">Configure all devices for Operations Management Suite</span></span>](with-oms.md#configure_all_devices)
7.  [<span data-ttu-id="a77f7-116">配置其他操作管理套件解决方案</span><span class="sxs-lookup"><span data-stu-id="a77f7-116">Configure additional Operations Management Suite solutions</span></span>](with-oms.md#Solutions)

> [!IMPORTANT]
> <span data-ttu-id="a77f7-117">使用最少配置操作管理套件可以监视运行 Windows 操作系统的计算机，但仍有一些需要在开始部署到所有 Skype 会议室系统的代理之前的 Skype 会议室系统特定步骤设备。</span><span class="sxs-lookup"><span data-stu-id="a77f7-117">Although with minimal configuration, the Operations Management Suite can monitor a computer running a Windows operating system, there are still some Skype Room Systems–specific steps that you need to take before you start deploying agents to all Skype Room Systems devices.</span></span>
> <span data-ttu-id="a77f7-118">因此，我们强烈建议您受控的安装和配置正确的顺序执行所有配置步骤。</span><span class="sxs-lookup"><span data-stu-id="a77f7-118">Therefore, we highly recommend you perform all configuration steps in the right order for a controlled setup and configuration.</span></span> <span data-ttu-id="a77f7-119">最终结果的质量很大程度取决于的初始配置的质量。</span><span class="sxs-lookup"><span data-stu-id="a77f7-119">The quality of the end result very much depends on the quality of the initial configuration.</span></span>

## <a name="validate-operations-management-suite-configuration"></a><span data-ttu-id="a77f7-120">验证操作管理套件配置</span><span class="sxs-lookup"><span data-stu-id="a77f7-120">Validate Operations Management Suite configuration</span></span>
<span data-ttu-id="a77f7-121"><a name="validate_OMS"> </a></span><span class="sxs-lookup"><span data-stu-id="a77f7-121"></span></span>

<span data-ttu-id="a77f7-122">您需要具有要开始从 Skype 会议室系统设备收集日志操作管理套件工作区。</span><span class="sxs-lookup"><span data-stu-id="a77f7-122">You need to have an Operations Management Suite workspace to start collecting logs from Skype Room Systems devices.</span></span> <span data-ttu-id="a77f7-123">工作区是使用其自己的数据存储库、 数据源和解决方案的唯一日志分析环境。</span><span class="sxs-lookup"><span data-stu-id="a77f7-123">A workspace is a unique Log Analytics environment with its own data repository, data sources, and solutions.</span></span> <span data-ttu-id="a77f7-124">如果您已有现有日志分析工作区，您可能使用它来监视 Skype 会议室系统部署，或者您可以创建需要专用的日志分析工作区特定于您 Skype 会议室系统监控。</span><span class="sxs-lookup"><span data-stu-id="a77f7-124">If you already have an existing Log Analytics workspace, you might use it to monitor your Skype Room Systems deployment or you can create a dedicated Log Analytics workspace specific to your Skype Room Systems monitoring needs.</span></span>

<span data-ttu-id="a77f7-125">如果您需要创建新的日志分析工作区，请按照[创建 Azure 门户中的日志分析工作区](https://docs.microsoft.com/azure/log-analytics/log-analytics-quick-create-workspace)一文中的说明</span><span class="sxs-lookup"><span data-stu-id="a77f7-125">If you need to create a new Log Analytics workspace, follow the instructions in the article [Create a Log Analytics workspace in the Azure portal](https://docs.microsoft.com/azure/log-analytics/log-analytics-quick-create-workspace)</span></span>

> [!NOTE]
> <span data-ttu-id="a77f7-126">若要使用日志分析与操作管理套件，您需要具有活动的 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="a77f7-126">To use Log Analytics with Operations Management Suite, you need to have an active Azure subscription.</span></span> <span data-ttu-id="a77f7-127">如果您没有 Azure 订阅，您可以创建[免费的试用订阅](https://azure.microsoft.com/free)作为起点。</span><span class="sxs-lookup"><span data-stu-id="a77f7-127">If you don’t have an Azure subscription, you can create [a free trial subscription](https://azure.microsoft.com/free) as a starting point.</span></span>


### <a name="configure-operations-management-suite-to-collect-skype-room-systems-event-logs"></a><span data-ttu-id="a77f7-128">配置操作管理套件收集 Skype 会议室系统事件日志</span><span class="sxs-lookup"><span data-stu-id="a77f7-128">Configure Operations Management Suite to collect Skype Room Systems event logs</span></span>

<span data-ttu-id="a77f7-129">日志分析仅收集在设置中指定的 Windows 事件日志中的事件。</span><span class="sxs-lookup"><span data-stu-id="a77f7-129">Log Analytics only collects events from the Windows event logs that are specified in the settings.</span></span> <span data-ttu-id="a77f7-130">为每个日志中，会收集仅将所选的严重级别的事件。</span><span class="sxs-lookup"><span data-stu-id="a77f7-130">For each log, only the events with the selected severities are collected.</span></span>

<span data-ttu-id="a77f7-131">您需要配置操作管理套件收集监视 Skype 会议室系统设备和应用程序状态所需的日志。</span><span class="sxs-lookup"><span data-stu-id="a77f7-131">You need to configure Operations Management Suite to collect the logs required to monitor Skype Room Systems device and application status.</span></span> <span data-ttu-id="a77f7-132">Skype 会议室系统 v2 设备使用 Skype 会议室系统事件日志。</span><span class="sxs-lookup"><span data-stu-id="a77f7-132">Skype Room Systems v2 devices use the Skype Room Systems event log.</span></span>

<span data-ttu-id="a77f7-133">配置操作管理套件收集 Skype 会议室系统事件，请参阅[日志分析中的 Windows 事件日志数据源](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events)</span><span class="sxs-lookup"><span data-stu-id="a77f7-133">To configure Operations Management Suite to collect the Skype Room Systems events, see [Windows event log data sources in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events)</span></span>

<span data-ttu-id="a77f7-134">![事件日志设置](../../media/Deploy_OMS_2.png "事件日志设置")</span><span class="sxs-lookup"><span data-stu-id="a77f7-134">![Event log settings](../../media/Deploy_OMS_2.png "Event log settings")</span></span>


> [!IMPORTANT]
> <span data-ttu-id="a77f7-135">Skype 会议室系统事件日志中，选择，然后选择**错误**、**警告**和**信息**复选框。</span><span class="sxs-lookup"><span data-stu-id="a77f7-135">Select the Skype Room System event log, and then select the **Error**, **Warning**, and **Information** check boxes.</span></span>

## <a name="configure-test-devices-for-operations-management-suite-setup"></a><span data-ttu-id="a77f7-136">配置操作管理套件安装程序测试设备</span><span class="sxs-lookup"><span data-stu-id="a77f7-136">Configure test devices for Operations Management Suite setup</span></span>
<span data-ttu-id="a77f7-137"><a name="configure_test_devices"> </a></span><span class="sxs-lookup"><span data-stu-id="a77f7-137"></span></span>

<span data-ttu-id="a77f7-138">您需要准备操作管理套件能够监视 Skype 会议室系统相关的事件。</span><span class="sxs-lookup"><span data-stu-id="a77f7-138">You need to prepare Operations Management Suite to be able to monitor Skype Room Systems–related events.</span></span> <span data-ttu-id="a77f7-139">启动时，您需要将操作管理套件代理部署到只是一个或两个 Skype 会议室系统设备物理访问并且具有这些测试设备生成一些数据，并将其推送到日志分析工作区。</span><span class="sxs-lookup"><span data-stu-id="a77f7-139">To start with, you need to deploy Operations Management Suite agents to just one or two Skype Room Systems devices that you have physical access to and have those test devices generate some data and push it to the Log Analytics workspace.</span></span>

### <a name="install-operations-management-suite-agents-to-test-devices"></a><span data-ttu-id="a77f7-140">安装到测试设备的操作管理套件代理</span><span class="sxs-lookup"><span data-stu-id="a77f7-140">Install Operations Management Suite agents to test devices</span></span>

<span data-ttu-id="a77f7-141">使用[到 Azure 中的日志分析服务的连接的 Windows 计算机](https://docs.microsoft.com/azure/log-analytics/log-analytics-agent-windows)中提供的说明，将操作管理套件代理部署到测试设备上。</span><span class="sxs-lookup"><span data-stu-id="a77f7-141">Deploy the Operations Management Suite agent to the test devices by using the instructions provided in [Connect Windows computers to the Log Analytics service in Azure](https://docs.microsoft.com/azure/log-analytics/log-analytics-agent-windows).</span></span> <span data-ttu-id="a77f7-142">本文提供有关部署监控代理的 Windows，获取操作管理套件工作区 ID 说明的步骤的详细的信息和主键获取 Skype 会议室系统设备连接到您操作管理套件部署，以及验证代理连接到分析日志的步骤。</span><span class="sxs-lookup"><span data-stu-id="a77f7-142">This article gives detailed information about the steps for deploying Microsoft Monitoring Agent for Windows, instructions for obtaining the Operations Management Suite Workspace ID and the primary key to get Skype Room Systems devices connected to your Operations Management Suite deployment, and steps to verify agent connectivity to Log Analytics.</span></span>

### <a name="generate-sample-skype-room-systems-events"></a><span data-ttu-id="a77f7-143">生成示例 Skype 会议室系统事件</span><span class="sxs-lookup"><span data-stu-id="a77f7-143">Generate sample Skype Room Systems events</span></span>

<span data-ttu-id="a77f7-144">操作管理套件代理部署到测试设备后，验证所需的事件日志数据收集日志分析。</span><span class="sxs-lookup"><span data-stu-id="a77f7-144">After the Operations Management Suite agent is deployed onto the test devices, verify that the required event log data is collected by Log Analytics.</span></span>

1.  <span data-ttu-id="a77f7-145">登录到[Microsoft 操作管理套件门户](http://aka.ms/omsportal)。</span><span class="sxs-lookup"><span data-stu-id="a77f7-145">Sign in to the [Microsoft Operations Management Suite portal](http://aka.ms/omsportal).</span></span>

2.  <span data-ttu-id="a77f7-146">列出由 Skype 会议室系统设备生成的事件：</span><span class="sxs-lookup"><span data-stu-id="a77f7-146">List the events generated by a Skype Room Systems device:</span></span>
    1.  <span data-ttu-id="a77f7-147">转到**日志搜索**并使用查询来检索将具有自定义字段的记录。</span><span class="sxs-lookup"><span data-stu-id="a77f7-147">Go to **Log Search** and use a query to retrieve the records that will have the custom field.</span></span>
    2.  <span data-ttu-id="a77f7-148">示例查询：`Event | where Source == "SRS-App"`</span><span class="sxs-lookup"><span data-stu-id="a77f7-148">Sample query: `Event | where Source == "SRS-App"`</span></span>

3.  <span data-ttu-id="a77f7-149">确保查询返回包含成功检测信号事件的日志记录。</span><span class="sxs-lookup"><span data-stu-id="a77f7-149">Make sure that the query returns log records that include successful heartbeat events.</span></span>

4.  <span data-ttu-id="a77f7-150">生成硬件问题，并验证的操作管理套件中记录所需的事件。</span><span class="sxs-lookup"><span data-stu-id="a77f7-150">Generate a hardware issue, and validate that the required events are logged in Operations Management Suite.</span></span>
    1.  <span data-ttu-id="a77f7-151">拔下测试 Skype 会议室系统系统上的外围设备之一。</span><span class="sxs-lookup"><span data-stu-id="a77f7-151">Unplug one of the peripheral devices on the test Skype Room Systems system.</span></span> <span data-ttu-id="a77f7-152">这可能是照相机、 免提电话、 麦克风或前端聊天室显示</span><span class="sxs-lookup"><span data-stu-id="a77f7-152">This could be the camera, speakerphone, microphone, or Front Room Display</span></span>
    2.  <span data-ttu-id="a77f7-153">等待事件日志操作管理套件中填充的 10 分钟。</span><span class="sxs-lookup"><span data-stu-id="a77f7-153">Wait 10 minutes for the event log to be populated in Operations Management Suite.</span></span>
    3.  <span data-ttu-id="a77f7-154">使用列表硬件错误事件查询：`Event | where EventID == 3001`</span><span class="sxs-lookup"><span data-stu-id="a77f7-154">Use a query to list hardware error events: `Event | where EventID == 3001`</span></span>

5.  <span data-ttu-id="a77f7-155">生成应用程序问题，并验证的记录所需的事件。</span><span class="sxs-lookup"><span data-stu-id="a77f7-155">Generate an application issue, and validate that the required events are logged.</span></span>
    1.  <span data-ttu-id="a77f7-156">修改 Skype 会议室系统应用程序配置，并键入正确的会话初始协议 (SIP) 地址中的密码对。</span><span class="sxs-lookup"><span data-stu-id="a77f7-156">Modify Skype Room Systems application configuration, and type an incorrect Session Initiation Protocol (SIP) address/password pair.</span></span>
    2.  <span data-ttu-id="a77f7-157">等待事件日志操作管理套件中填充的 10 分钟。</span><span class="sxs-lookup"><span data-stu-id="a77f7-157">Wait 10 minutes for the event log to be populated in Operations Management Suite.</span></span>
    3.  <span data-ttu-id="a77f7-158">使用查询的列表应用程序错误事件：`Event | where EventID == 2001`</span><span class="sxs-lookup"><span data-stu-id="a77f7-158">Use a query to list application error events: `Event | where EventID == 2001`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a77f7-159">这些示例事件日志是必需的然后才能配置自定义字段。</span><span class="sxs-lookup"><span data-stu-id="a77f7-159">These sample event logs are required before custom fields can be configured.</span></span> <span data-ttu-id="a77f7-160">不继续下一步，直到您已收集所需的事件日志。</span><span class="sxs-lookup"><span data-stu-id="a77f7-160">Don’t proceed to the next step until you have collected the required event logs.</span></span>

## <a name="map-custom-fields"></a><span data-ttu-id="a77f7-161">映射自定义字段</span><span class="sxs-lookup"><span data-stu-id="a77f7-161">Map custom fields</span></span>
<span data-ttu-id="a77f7-162"><a name="Custom_fields"> </a></span><span class="sxs-lookup"><span data-stu-id="a77f7-162"></span></span>

<span data-ttu-id="a77f7-163">使用自定义域从事件日志中提取特定的数据。</span><span class="sxs-lookup"><span data-stu-id="a77f7-163">You use custom fields to extract specific data from the event logs.</span></span> <span data-ttu-id="a77f7-164">您需要定义将与您的图块数为单位、 仪表板视图和通知更高版本使用的自定义字段。</span><span class="sxs-lookup"><span data-stu-id="a77f7-164">You need to define custom fields that will be used later with your tiles, dashboard views, and alerts.</span></span> <span data-ttu-id="a77f7-165">请参阅[日志分析中的自定义域](https://docs.microsoft.com/azure/log-analytics/log-analytics-custom-fields)和熟悉概念开始创建自定义域之前。</span><span class="sxs-lookup"><span data-stu-id="a77f7-165">See [Custom fields in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-custom-fields) and become familiar with the concepts before you start creating your custom fields.</span></span>

<span data-ttu-id="a77f7-166">提取自定义域超出捕获的事件日志，请按照下列步骤：</span><span class="sxs-lookup"><span data-stu-id="a77f7-166">To extract your custom fields out of the captured event logs, follow these steps:</span></span>

1.  <span data-ttu-id="a77f7-167">登录到[Microsoft 操作管理套件门户](http://aka.ms/omsportal)。</span><span class="sxs-lookup"><span data-stu-id="a77f7-167">Sign in to the [Microsoft Operations Management Suite portal](http://aka.ms/omsportal).</span></span>

2.  <span data-ttu-id="a77f7-168">列出由 Skype 会议室系统设备生成的事件：</span><span class="sxs-lookup"><span data-stu-id="a77f7-168">List the events generated by a Skype Room Systems device:</span></span>
    1.  <span data-ttu-id="a77f7-169">转到**日志搜索**并使用查询来检索将具有自定义字段的记录。</span><span class="sxs-lookup"><span data-stu-id="a77f7-169">Go to **Log Search** and use a query to retrieve the records that will have the custom field.</span></span>
    2.  <span data-ttu-id="a77f7-170">示例查询：`Event | where Source == "SRS-App"`</span><span class="sxs-lookup"><span data-stu-id="a77f7-170">Sample query: `Event | where Source == "SRS-App"`</span></span>

3.  <span data-ttu-id="a77f7-171">选择记录之一，选择向左，按钮并启动字段提取向导。</span><span class="sxs-lookup"><span data-stu-id="a77f7-171">Select one of the records, select the button to the left, and start the field extraction wizard.</span></span>

<span data-ttu-id="a77f7-172">![字段提取向导](../../media/Deploy_OMS_3.png "字段提取向导")</span><span class="sxs-lookup"><span data-stu-id="a77f7-172">![Field extraction wizard](../../media/Deploy_OMS_3.png "Field extraction wizard")</span></span>

4.  <span data-ttu-id="a77f7-173">突出显示您希望从 RenderedDescription 提取并提供字段标题的数据。</span><span class="sxs-lookup"><span data-stu-id="a77f7-173">Highlight the data you’d like to extract from the RenderedDescription and provide a Field Title.</span></span> <span data-ttu-id="a77f7-174">表 1 中提供了应使用的字段名称。</span><span class="sxs-lookup"><span data-stu-id="a77f7-174">The field names that you should use are provided in Table 1.</span></span>

<span data-ttu-id="a77f7-175">![自定义字段定义](../../media/Deploy_OMS_4.png "自定义字段定义")</span><span class="sxs-lookup"><span data-stu-id="a77f7-175">![Custom field definition](../../media/Deploy_OMS_4.png "Custom field definition")</span></span>

5.  <span data-ttu-id="a77f7-176">使用表 1 中显示的映射。</span><span class="sxs-lookup"><span data-stu-id="a77f7-176">Use the mappings shown in Table 1.</span></span> <span data-ttu-id="a77f7-177">将自动添加操作管理套件**\_CF**时定义的新字段的字符串。</span><span class="sxs-lookup"><span data-stu-id="a77f7-177">Operations Management Suite will automatically add the **\_CF** string when you define the new field.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a77f7-178">请记住 JSON 和操作管理套件的所有字段，都都区分大小写。</span><span class="sxs-lookup"><span data-stu-id="a77f7-178">Remember that all JSON and Operations Management Suite fields are case-sensitive.</span></span>

> <span data-ttu-id="a77f7-179">下表列出了特别注意 EventID 复选框的状态。</span><span class="sxs-lookup"><span data-stu-id="a77f7-179">Pay attention to the state of the EventID check box in the table below.</span></span> <span data-ttu-id="a77f7-180">确保您确认此复选框的操作管理套件成功提取自定义域值的状态。</span><span class="sxs-lookup"><span data-stu-id="a77f7-180">Be sure you confirm the state of this check box for Operations Management Suite to successfully extract custom field values.</span></span>
> <span data-ttu-id="a77f7-181">![自定义字段定义](../../media/Deploy_OMS_5.png "自定义字段定义")</span><span class="sxs-lookup"><span data-stu-id="a77f7-181">![Custom field definition](../../media/Deploy_OMS_5.png "Custom field definition")</span></span> 

<span data-ttu-id="a77f7-182">**表 1**</span><span class="sxs-lookup"><span data-stu-id="a77f7-182">**Table 1**</span></span>

| <span data-ttu-id="a77f7-183">**JSON 字段**</span><span class="sxs-lookup"><span data-stu-id="a77f7-183">**JSON field**</span></span>               | <span data-ttu-id="a77f7-184">**OMS 自定义字段**</span><span class="sxs-lookup"><span data-stu-id="a77f7-184">**OMS custom field**</span></span>       | <span data-ttu-id="a77f7-185">**事件 ID**</span><span class="sxs-lookup"><span data-stu-id="a77f7-185">**Event ID**</span></span> |
|------------------------------|----------------------------|-----------------|
| <span data-ttu-id="a77f7-186">说明</span><span class="sxs-lookup"><span data-stu-id="a77f7-186">Description</span></span>                  | <span data-ttu-id="a77f7-187">SRSEventDescription_CF</span><span class="sxs-lookup"><span data-stu-id="a77f7-187">SRSEventDescription_CF</span></span>     | <span data-ttu-id="a77f7-188">未选定</span><span class="sxs-lookup"><span data-stu-id="a77f7-188">Not selected</span></span>    |
| <span data-ttu-id="a77f7-189">ResourceState</span><span class="sxs-lookup"><span data-stu-id="a77f7-189">ResourceState</span></span>                | <span data-ttu-id="a77f7-190">SRSResourceState_CF</span><span class="sxs-lookup"><span data-stu-id="a77f7-190">SRSResourceState_CF</span></span>        | <span data-ttu-id="a77f7-191">未选定</span><span class="sxs-lookup"><span data-stu-id="a77f7-191">Not selected</span></span>    |
| <span data-ttu-id="a77f7-192">操作名称</span><span class="sxs-lookup"><span data-stu-id="a77f7-192">OperationName</span></span>                | <span data-ttu-id="a77f7-193">SRSOperationName_CF</span><span class="sxs-lookup"><span data-stu-id="a77f7-193">SRSOperationName_CF</span></span>        | <span data-ttu-id="a77f7-194">未选定</span><span class="sxs-lookup"><span data-stu-id="a77f7-194">Not selected</span></span>    |
| <span data-ttu-id="a77f7-195">OperationResult</span><span class="sxs-lookup"><span data-stu-id="a77f7-195">OperationResult</span></span>              | <span data-ttu-id="a77f7-196">SRSOperationResult_CF</span><span class="sxs-lookup"><span data-stu-id="a77f7-196">SRSOperationResult_CF</span></span>      | <span data-ttu-id="a77f7-197">未选定</span><span class="sxs-lookup"><span data-stu-id="a77f7-197">Not selected</span></span>    |
| <span data-ttu-id="a77f7-198">OS</span><span class="sxs-lookup"><span data-stu-id="a77f7-198">OS</span></span>                           | <span data-ttu-id="a77f7-199">SRSOSVersion_CF</span><span class="sxs-lookup"><span data-stu-id="a77f7-199">SRSOSVersion_CF</span></span>            | <span data-ttu-id="a77f7-200">未选定</span><span class="sxs-lookup"><span data-stu-id="a77f7-200">Not selected</span></span>    |
| <span data-ttu-id="a77f7-201">OSVersion</span><span class="sxs-lookup"><span data-stu-id="a77f7-201">OSVersion</span></span>                    | <span data-ttu-id="a77f7-202">SRSOSLongVersion_CF</span><span class="sxs-lookup"><span data-stu-id="a77f7-202">SRSOSLongVersion_CF</span></span>        | <span data-ttu-id="a77f7-203">未选定</span><span class="sxs-lookup"><span data-stu-id="a77f7-203">Not selected</span></span>    |
| <span data-ttu-id="a77f7-204">别名</span><span class="sxs-lookup"><span data-stu-id="a77f7-204">Alias</span></span>                        | <span data-ttu-id="a77f7-205">SRSAlias_CF</span><span class="sxs-lookup"><span data-stu-id="a77f7-205">SRSAlias_CF</span></span>                | <span data-ttu-id="a77f7-206">未选定</span><span class="sxs-lookup"><span data-stu-id="a77f7-206">Not selected</span></span>    |
| <span data-ttu-id="a77f7-207">DisplayName</span><span class="sxs-lookup"><span data-stu-id="a77f7-207">DisplayName</span></span>                  | <span data-ttu-id="a77f7-208">SRSDisplayName_CF</span><span class="sxs-lookup"><span data-stu-id="a77f7-208">SRSDisplayName_CF</span></span>          | <span data-ttu-id="a77f7-209">未选定</span><span class="sxs-lookup"><span data-stu-id="a77f7-209">Not selected</span></span>    |
| <span data-ttu-id="a77f7-210">AppVersion</span><span class="sxs-lookup"><span data-stu-id="a77f7-210">AppVersion</span></span>                   | <span data-ttu-id="a77f7-211">SRSAppVersion_CF</span><span class="sxs-lookup"><span data-stu-id="a77f7-211">SRSAppVersion_CF</span></span>           | <span data-ttu-id="a77f7-212">未选定</span><span class="sxs-lookup"><span data-stu-id="a77f7-212">Not selected</span></span>    |
| <span data-ttu-id="a77f7-213">IPv4Address</span><span class="sxs-lookup"><span data-stu-id="a77f7-213">IPv4Address</span></span>                  | <span data-ttu-id="a77f7-214">SRSIPv4Address_CF</span><span class="sxs-lookup"><span data-stu-id="a77f7-214">SRSIPv4Address_CF</span></span>          | <span data-ttu-id="a77f7-215">未选定</span><span class="sxs-lookup"><span data-stu-id="a77f7-215">Not selected</span></span>    |
| <span data-ttu-id="a77f7-216">IPv6Address</span><span class="sxs-lookup"><span data-stu-id="a77f7-216">IPv6Address</span></span>                  | <span data-ttu-id="a77f7-217">SRSIPv6Address_CF</span><span class="sxs-lookup"><span data-stu-id="a77f7-217">SRSIPv6Address_CF</span></span>          | <span data-ttu-id="a77f7-218">未选定</span><span class="sxs-lookup"><span data-stu-id="a77f7-218">Not selected</span></span>    |
| <span data-ttu-id="a77f7-219">前面的聊天室显示状态</span><span class="sxs-lookup"><span data-stu-id="a77f7-219">Front of Room Display status</span></span> | <span data-ttu-id="a77f7-220">SRSFORDStatus_CF</span><span class="sxs-lookup"><span data-stu-id="a77f7-220">SRSFORDStatus_CF</span></span>           | <span data-ttu-id="a77f7-221">3001</span><span class="sxs-lookup"><span data-stu-id="a77f7-221">3001</span></span>            |
| <span data-ttu-id="a77f7-222">摄像机状态</span><span class="sxs-lookup"><span data-stu-id="a77f7-222">Camera status</span></span>                | <span data-ttu-id="a77f7-223">SRSCameraStatus_CF</span><span class="sxs-lookup"><span data-stu-id="a77f7-223">SRSCameraStatus_CF</span></span>         | <span data-ttu-id="a77f7-224">3001</span><span class="sxs-lookup"><span data-stu-id="a77f7-224">3001</span></span>            |
| <span data-ttu-id="a77f7-225">会议麦克风状态</span><span class="sxs-lookup"><span data-stu-id="a77f7-225">Conference Microphone status</span></span> | <span data-ttu-id="a77f7-226">SRSConfMicrophoneStatus_CF</span><span class="sxs-lookup"><span data-stu-id="a77f7-226">SRSConfMicrophoneStatus_CF</span></span> | <span data-ttu-id="a77f7-227">3001</span><span class="sxs-lookup"><span data-stu-id="a77f7-227">3001</span></span>            |
| <span data-ttu-id="a77f7-228">会议扬声器状态</span><span class="sxs-lookup"><span data-stu-id="a77f7-228">Conference Speaker status</span></span>    | <span data-ttu-id="a77f7-229">SRSConfSpeakerStatus_CF</span><span class="sxs-lookup"><span data-stu-id="a77f7-229">SRSConfSpeakerStatus_CF</span></span>    | <span data-ttu-id="a77f7-230">3001</span><span class="sxs-lookup"><span data-stu-id="a77f7-230">3001</span></span>            |
| <span data-ttu-id="a77f7-231">默认扬声器状态</span><span class="sxs-lookup"><span data-stu-id="a77f7-231">Default Speaker status</span></span>       | <span data-ttu-id="a77f7-232">SRSDefaultSpeakerStatus_CF</span><span class="sxs-lookup"><span data-stu-id="a77f7-232">SRSDefaultSpeakerStatus_CF</span></span> | <span data-ttu-id="a77f7-233">3001</span><span class="sxs-lookup"><span data-stu-id="a77f7-233">3001</span></span>            |
| <span data-ttu-id="a77f7-234">运动传感器状态</span><span class="sxs-lookup"><span data-stu-id="a77f7-234">Motion Sensor status</span></span>         | <span data-ttu-id="a77f7-235">SRSMotionSensorStatus_CF</span><span class="sxs-lookup"><span data-stu-id="a77f7-235">SRSMotionSensorStatus_CF</span></span>   | <span data-ttu-id="a77f7-236">3001</span><span class="sxs-lookup"><span data-stu-id="a77f7-236">3001</span></span>            |
| <span data-ttu-id="a77f7-237">HDMI 引入状态</span><span class="sxs-lookup"><span data-stu-id="a77f7-237">HDMI Ingest status</span></span>           | <span data-ttu-id="a77f7-238">SRSHDMIIngestStatus_CF</span><span class="sxs-lookup"><span data-stu-id="a77f7-238">SRSHDMIIngestStatus_CF</span></span>     | <span data-ttu-id="a77f7-239">3001</span><span class="sxs-lookup"><span data-stu-id="a77f7-239">3001</span></span>            |


## <a name="define-the-skype-room-systems-v2-views-in-operations-management-suite"></a><span data-ttu-id="a77f7-240">操作管理套件中定义的 Skype 会议室系统 v2 视图</span><span class="sxs-lookup"><span data-stu-id="a77f7-240">Define the Skype Room Systems v2 views in Operations Management Suite</span></span>
<span data-ttu-id="a77f7-241"><a name="Define_Views"> </a></span><span class="sxs-lookup"><span data-stu-id="a77f7-241"></span></span>

<span data-ttu-id="a77f7-242">收集数据并自定义字段映射后，您可以使用操作管理套件视图设计器开发包含各种平铺监视 Skype 会议室系统 v2 事件仪表板。</span><span class="sxs-lookup"><span data-stu-id="a77f7-242">After data is collected and custom fields are mapped, you can use Operations Management Suite View Designer to develop a dashboard containing various tiles to monitor Skype Room Systems v2 events.</span></span> <span data-ttu-id="a77f7-243">使用视图设计器创建以下图块。</span><span class="sxs-lookup"><span data-stu-id="a77f7-243">Use View Designer to create the following tiles.</span></span> <span data-ttu-id="a77f7-244">有关详细信息，请参阅[使用视图设计器创建日志分析中的自定义视图](https://docs.microsoft.com/azure/log-analytics/log-analytics-view-designer)</span><span class="sxs-lookup"><span data-stu-id="a77f7-244">For more information, see [Use View Designer to create custom views in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-view-designer)</span></span>

> [!NOTE]
> <span data-ttu-id="a77f7-245">应可以正常运行仪表板图块完成本指南中前面的步骤。</span><span class="sxs-lookup"><span data-stu-id="a77f7-245">Earlier steps in this guide should have been completed for the dashboard tiles to work properly.</span></span>


### <a name="create-a-skype-room-systems-v2-dashboard-by-using-the-import-method"></a><span data-ttu-id="a77f7-246">使用的导入方法创建 Skype 会议室系统 v2 仪表板</span><span class="sxs-lookup"><span data-stu-id="a77f7-246">Create a Skype Room Systems v2 dashboard by using the import method</span></span>

<span data-ttu-id="a77f7-247">可以导入的操作管理套件仪表板并启动立即监控您的设备。</span><span class="sxs-lookup"><span data-stu-id="a77f7-247">You can import an Operations Management Suite dashboard and start monitoring your devices immediately.</span></span> <span data-ttu-id="a77f7-248">执行以下步骤以导入仪表板：</span><span class="sxs-lookup"><span data-stu-id="a77f7-248">Take the following steps to import the dashboard:</span></span>

1.  <span data-ttu-id="a77f7-249">获取[SkypeRoomSystems_v2.omsview](http://download.microsoft.com/download/9/0/D/90D4826A-9FD2-47D2-B911-97BF1737F4F7/SkypeRoomSystems_v2.omsview)仪表板文件。</span><span class="sxs-lookup"><span data-stu-id="a77f7-249">Get the [SkypeRoomSystems_v2.omsview](http://download.microsoft.com/download/9/0/D/90D4826A-9FD2-47D2-B911-97BF1737F4F7/SkypeRoomSystems_v2.omsview) dashboard file.</span></span>
2.  <span data-ttu-id="a77f7-250">登录到[Microsoft 操作管理套件门户](http://aka.ms/omsportal)。</span><span class="sxs-lookup"><span data-stu-id="a77f7-250">Sign in to the [Microsoft Operations Management Suite portal](http://aka.ms/omsportal).</span></span>
3.  <span data-ttu-id="a77f7-251">打开**视图设计器**。</span><span class="sxs-lookup"><span data-stu-id="a77f7-251">Open **View Designer**.</span></span>
4.  <span data-ttu-id="a77f7-252">选择**导入**，，然后选择**SkypeRoomSystems_v2.omsview**文件。</span><span class="sxs-lookup"><span data-stu-id="a77f7-252">Select **Import**, and then select the **SkypeRoomSystems_v2.omsview** file.</span></span>
5.  <span data-ttu-id="a77f7-253">选择**保存**。</span><span class="sxs-lookup"><span data-stu-id="a77f7-253">Select **Save**.</span></span>

### <a name="create-a-skype-room-systems-v2-dashboard-manually"></a><span data-ttu-id="a77f7-254">手动创建 Skype 会议室系统 v2 仪表板</span><span class="sxs-lookup"><span data-stu-id="a77f7-254">Create a Skype Room Systems v2 dashboard manually</span></span>

<span data-ttu-id="a77f7-255">此外，您可以创建自己的仪表板并添加您想要监视的图块。</span><span class="sxs-lookup"><span data-stu-id="a77f7-255">Alternatively, you can create your own dashboard and add only the tiles that you wish to monitor.</span></span>

#### <a name="configure-the-overview-tile"></a><span data-ttu-id="a77f7-256">配置概述图块</span><span class="sxs-lookup"><span data-stu-id="a77f7-256">Configure the Overview Tile</span></span>
1.  <span data-ttu-id="a77f7-257">打开**视图设计器**。</span><span class="sxs-lookup"><span data-stu-id="a77f7-257">Open **View Designer**.</span></span>
2.  <span data-ttu-id="a77f7-258">选择**概述图块**，并从库选择**两个数字**。</span><span class="sxs-lookup"><span data-stu-id="a77f7-258">Select **Overview Tile**, and then select **Two numbers** from the gallery.</span></span>
3.  <span data-ttu-id="a77f7-259">名称平铺**Skype 会议室系统**。</span><span class="sxs-lookup"><span data-stu-id="a77f7-259">Name the tile **Skype Room Systems**.</span></span>
4.  <span data-ttu-id="a77f7-260">定义**第一个图块**：</span><span class="sxs-lookup"><span data-stu-id="a77f7-260">Define the **First Tile**:</span></span><br>
    <span data-ttu-id="a77f7-261">**图例：** 至少执行一次在上个月内发送检测信号的设备</span><span class="sxs-lookup"><span data-stu-id="a77f7-261">**Legend:** Devices that sent a heartbeat at least once within the last month</span></span><br>
    <span data-ttu-id="a77f7-262">**查询：**```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```</span><span class="sxs-lookup"><span data-stu-id="a77f7-262">**Query:** ```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```</span></span>
5.  <span data-ttu-id="a77f7-263">定义**第二个图块**：</span><span class="sxs-lookup"><span data-stu-id="a77f7-263">Define the **Second Tile**:</span></span><br>
    <span data-ttu-id="a77f7-264">**图例：** 发送检测信号的最后一个小时内的活动设备</span><span class="sxs-lookup"><span data-stu-id="a77f7-264">**Legend:** Active devices that sent a heartbeat within the last hour</span></span><br>
    <span data-ttu-id="a77f7-265">**查询：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```</span><span class="sxs-lookup"><span data-stu-id="a77f7-265">**Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```</span></span>
6.  <span data-ttu-id="a77f7-266">选择**应用**。</span><span class="sxs-lookup"><span data-stu-id="a77f7-266">Select **Apply**.</span></span>

### <a name="create-a-tile-that-displays-active-devices"></a><span data-ttu-id="a77f7-267">创建活动设备将显示一个图块</span><span class="sxs-lookup"><span data-stu-id="a77f7-267">Create a tile that displays active devices</span></span>
1.  <span data-ttu-id="a77f7-268">选择**视图仪表板**开始添加您的图块数为单位。</span><span class="sxs-lookup"><span data-stu-id="a77f7-268">Select **View Dashboard** to start adding your tiles.</span></span>
2.  <span data-ttu-id="a77f7-269">从库中选择**号码和列表**</span><span class="sxs-lookup"><span data-stu-id="a77f7-269">Select **Number & list** from the gallery</span></span>
3.  <span data-ttu-id="a77f7-270">定义**常规**属性：</span><span class="sxs-lookup"><span data-stu-id="a77f7-270">Define the **General** properties:</span></span><br>
    <span data-ttu-id="a77f7-271">**组标题：** 检测信号状态</span><span class="sxs-lookup"><span data-stu-id="a77f7-271">**Group Title:** Heartbeat Status</span></span><br>
    <span data-ttu-id="a77f7-272">**新组：** 选择</span><span class="sxs-lookup"><span data-stu-id="a77f7-272">**New Group:** Selected</span></span>
4.  <span data-ttu-id="a77f7-273">定义**平铺**属性：</span><span class="sxs-lookup"><span data-stu-id="a77f7-273">Define the **Tile** properties:</span></span><br>
    <span data-ttu-id="a77f7-274">**图例：** 活动设备 （检测信号发送前 20 分钟内）</span><span class="sxs-lookup"><span data-stu-id="a77f7-274">**Legend:** Active devices (heartbeat sent in the last 20 minutes)</span></span><br>
    <span data-ttu-id="a77f7-275">**平铺查询：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```</span><span class="sxs-lookup"><span data-stu-id="a77f7-275">**Tile Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```</span></span>
5.  <span data-ttu-id="a77f7-276">定义**列表**的属性：</span><span class="sxs-lookup"><span data-stu-id="a77f7-276">Define the **List** properties:</span></span><br>
    <span data-ttu-id="a77f7-277">**列表查询：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span><span class="sxs-lookup"><span data-stu-id="a77f7-277">**List Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span></span>
6.  <span data-ttu-id="a77f7-278">定义**列标题**：</span><span class="sxs-lookup"><span data-stu-id="a77f7-278">Define **Column Titles**:</span></span><br>
    <span data-ttu-id="a77f7-279">**名称：** 显示名称</span><span class="sxs-lookup"><span data-stu-id="a77f7-279">**Name:** Display Name</span></span><br>
    <span data-ttu-id="a77f7-280">**值：** 最后一个检测信号</span><span class="sxs-lookup"><span data-stu-id="a77f7-280">**Value:** Last Heartbeat</span></span>
7.  <span data-ttu-id="a77f7-281">定义**导航查询**。</span><span class="sxs-lookup"><span data-stu-id="a77f7-281">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  <span data-ttu-id="a77f7-282">选择**应用**，然后**关闭**。</span><span class="sxs-lookup"><span data-stu-id="a77f7-282">Select **Apply**, and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-devices-that-have-connectivity-issues"></a><span data-ttu-id="a77f7-283">创建具有连接问题的设备将显示一个图块</span><span class="sxs-lookup"><span data-stu-id="a77f7-283">Create a tile that displays devices that have connectivity issues</span></span>
1.  <span data-ttu-id="a77f7-284">从库中，选择**号码和列表**，然后添加新的平铺。</span><span class="sxs-lookup"><span data-stu-id="a77f7-284">Select **Number & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="a77f7-285">定义**常规**属性：</span><span class="sxs-lookup"><span data-stu-id="a77f7-285">Define the **General** properties:</span></span><br>
    <span data-ttu-id="a77f7-286">**组标题：** 将保留为空</span><span class="sxs-lookup"><span data-stu-id="a77f7-286">**Group Title:** Leave empty</span></span><br>
    <span data-ttu-id="a77f7-287">**新组：** 未选定</span><span class="sxs-lookup"><span data-stu-id="a77f7-287">**New Group:** Not Selected</span></span>
3.  <span data-ttu-id="a77f7-288">定义**平铺**属性：</span><span class="sxs-lookup"><span data-stu-id="a77f7-288">Define the **Tile** properties:</span></span><br>
    <span data-ttu-id="a77f7-289">**图例：** 非活动设备 （发送前 20 分钟内无检测信号消息）</span><span class="sxs-lookup"><span data-stu-id="a77f7-289">**Legend:** Inactive Devices (no heartbeat message sent in the last 20 minutes)</span></span><br>
    <span data-ttu-id="a77f7-290">**平铺查询：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```</span><span class="sxs-lookup"><span data-stu-id="a77f7-290">**Tile Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```</span></span>
4.  <span data-ttu-id="a77f7-291">定义**列表**的属性：</span><span class="sxs-lookup"><span data-stu-id="a77f7-291">Define the **List** properties:</span></span><br>
    <span data-ttu-id="a77f7-292">**列表查询：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```</span><span class="sxs-lookup"><span data-stu-id="a77f7-292">**List Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```</span></span>
5.  <span data-ttu-id="a77f7-293">定义**列标题**：</span><span class="sxs-lookup"><span data-stu-id="a77f7-293">Define **Column Titles**:</span></span><br>
    <span data-ttu-id="a77f7-294">**名称：** 显示名称</span><span class="sxs-lookup"><span data-stu-id="a77f7-294">**Name:** Display Name</span></span><br>
    <span data-ttu-id="a77f7-295">**值：** 最后一个检测信号</span><span class="sxs-lookup"><span data-stu-id="a77f7-295">**Value:** Last Heartbeat</span></span>
6.  <span data-ttu-id="a77f7-296">定义**导航查询**：</span><span class="sxs-lookup"><span data-stu-id="a77f7-296">Define **Navigation Query**:</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  <span data-ttu-id="a77f7-297">选择**应用**，然后**关闭**。</span><span class="sxs-lookup"><span data-stu-id="a77f7-297">Select **Apply**, and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-devices-that-have-a-hardware-error"></a><span data-ttu-id="a77f7-298">创建具有硬件错误的设备将显示一个图块</span><span class="sxs-lookup"><span data-stu-id="a77f7-298">Create a tile that displays devices that have a hardware error</span></span>

1.  <span data-ttu-id="a77f7-299">从库中，选择**号码和列表**，然后添加新的平铺。</span><span class="sxs-lookup"><span data-stu-id="a77f7-299">Select **Number & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="a77f7-300">定义**常规**属性：</span><span class="sxs-lookup"><span data-stu-id="a77f7-300">Define the **General** properties:</span></span><br>
    <span data-ttu-id="a77f7-301">**组标题：** 硬件</span><span class="sxs-lookup"><span data-stu-id="a77f7-301">**Group Title:** Hardware</span></span><br>
    <span data-ttu-id="a77f7-302">**新组：** 选择</span><span class="sxs-lookup"><span data-stu-id="a77f7-302">**New Group:** Selected</span></span>
3.  <span data-ttu-id="a77f7-303">定义**平铺**属性：</span><span class="sxs-lookup"><span data-stu-id="a77f7-303">Define the **Tile** properties:</span></span><br>
    <span data-ttu-id="a77f7-304">**图例：** 最后一个小时内遇到硬件错误的设备</span><span class="sxs-lookup"><span data-stu-id="a77f7-304">**Legend:** Devices that experienced a hardware error in the last hour</span></span> <br>
    <span data-ttu-id="a77f7-305">**平铺查询：**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```</span><span class="sxs-lookup"><span data-stu-id="a77f7-305">**Tile Query:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```</span></span>
4.  <span data-ttu-id="a77f7-306">定义**列表**的属性：</span><span class="sxs-lookup"><span data-stu-id="a77f7-306">Define the **List** properties:</span></span><br>
    <span data-ttu-id="a77f7-307">**列表查询：**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer```</span><span class="sxs-lookup"><span data-stu-id="a77f7-307">**List Query:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer```</span></span>
5.  <span data-ttu-id="a77f7-308">定义**列标题**：</span><span class="sxs-lookup"><span data-stu-id="a77f7-308">Define **Column Titles**:</span></span><br>
    <span data-ttu-id="a77f7-309">**名称：** 显示名称</span><span class="sxs-lookup"><span data-stu-id="a77f7-309">**Name:** Display Name</span></span><br>
    <span data-ttu-id="a77f7-310">**值：** 最后一个错误</span><span class="sxs-lookup"><span data-stu-id="a77f7-310">**Value:** Last Error</span></span>
6.  <span data-ttu-id="a77f7-311">定义**导航查询**：</span><span class="sxs-lookup"><span data-stu-id="a77f7-311">Define **Navigation Query**:</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 3001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  <span data-ttu-id="a77f7-312">选择**应用**，然后**关闭**。</span><span class="sxs-lookup"><span data-stu-id="a77f7-312">Select **Apply**, and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-skype-room-systems-application-versions"></a><span data-ttu-id="a77f7-313">创建显示 Skype 会议室系统应用程序版本拼贴</span><span class="sxs-lookup"><span data-stu-id="a77f7-313">Create a tile that displays Skype Room Systems application versions</span></span>

1.  <span data-ttu-id="a77f7-314">从库中，选择**圆环和列表**，然后添加新的平铺。</span><span class="sxs-lookup"><span data-stu-id="a77f7-314">Select **Donut & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="a77f7-315">定义**常规**属性：</span><span class="sxs-lookup"><span data-stu-id="a77f7-315">Define the **General** properties:</span></span><br>
    <span data-ttu-id="a77f7-316">**组标题：** Skype 会议室系统 v2 应用程序的详细信息</span><span class="sxs-lookup"><span data-stu-id="a77f7-316">**Group Title:** Skype Room Systems v2 application details</span></span> <br>
    <span data-ttu-id="a77f7-317">**新组：** 选择</span><span class="sxs-lookup"><span data-stu-id="a77f7-317">**New Group:** Selected</span></span>
3.  <span data-ttu-id="a77f7-318">定义**标头**属性：</span><span class="sxs-lookup"><span data-stu-id="a77f7-318">Define the **Header** properties:</span></span><br>
    <span data-ttu-id="a77f7-319">**标题：** 应用程序版本</span><span class="sxs-lookup"><span data-stu-id="a77f7-319">**Title:** Application versions</span></span><br>
    <span data-ttu-id="a77f7-320">**副标题：** 设备运行特定应用程序版本</span><span class="sxs-lookup"><span data-stu-id="a77f7-320">**Subtitle:** Devices running specific application versions</span></span>
4.  <span data-ttu-id="a77f7-321">定义**圆环**属性：</span><span class="sxs-lookup"><span data-stu-id="a77f7-321">Define the **Donut** properties:</span></span><br>
    <span data-ttu-id="a77f7-322">**查询：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```</span><span class="sxs-lookup"><span data-stu-id="a77f7-322">**Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```</span></span><br>
    <span data-ttu-id="a77f7-323">**使文本居中：** 设备</span><span class="sxs-lookup"><span data-stu-id="a77f7-323">**Center Text:** Devices</span></span><br>
    <span data-ttu-id="a77f7-324">**操作：** Sum</span><span class="sxs-lookup"><span data-stu-id="a77f7-324">**Operation:** Sum</span></span>
5.  <span data-ttu-id="a77f7-325">定义**列表**的属性。</span><span class="sxs-lookup"><span data-stu-id="a77f7-325">Define the **List** properties.</span></span><br>
    <span data-ttu-id="a77f7-326">**列表查询：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```</span><span class="sxs-lookup"><span data-stu-id="a77f7-326">**List Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```</span></span><br>
    <span data-ttu-id="a77f7-327">**隐藏图：** 选择</span><span class="sxs-lookup"><span data-stu-id="a77f7-327">**Hide Graph:** Selected</span></span><br>
    <span data-ttu-id="a77f7-328">**启用迷你图：** 未选定</span><span class="sxs-lookup"><span data-stu-id="a77f7-328">**Enable Sparklines:** Not selected</span></span>
6.  <span data-ttu-id="a77f7-329">定义**列标题**。</span><span class="sxs-lookup"><span data-stu-id="a77f7-329">Define **Column Titles**.</span></span><br>
    <span data-ttu-id="a77f7-330">**名称：** 显示名称</span><span class="sxs-lookup"><span data-stu-id="a77f7-330">**Name:** Display Name</span></span><br>
    <span data-ttu-id="a77f7-331">**值：** 将保留为空</span><span class="sxs-lookup"><span data-stu-id="a77f7-331">**Value:** Leave Empty</span></span>
7.  <span data-ttu-id="a77f7-332">定义**导航查询**。</span><span class="sxs-lookup"><span data-stu-id="a77f7-332">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  <span data-ttu-id="a77f7-333">选择**应用**，然后**关闭**。</span><span class="sxs-lookup"><span data-stu-id="a77f7-333">Select **Apply** and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-devices-that-have-an-application-error"></a><span data-ttu-id="a77f7-334">创建具有应用程序错误的设备将显示一个图块</span><span class="sxs-lookup"><span data-stu-id="a77f7-334">Create a tile that displays devices that have an application error</span></span>

1.  <span data-ttu-id="a77f7-335">从库中，选择**号码和列表**，然后添加新的平铺。</span><span class="sxs-lookup"><span data-stu-id="a77f7-335">Select **Number & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="a77f7-336">定义**常规**属性。</span><span class="sxs-lookup"><span data-stu-id="a77f7-336">Define the **General** properties.</span></span><br>
    <span data-ttu-id="a77f7-337">**组标题：** 将保留为空</span><span class="sxs-lookup"><span data-stu-id="a77f7-337">**Group Title:** Leave empty</span></span><br>
    <span data-ttu-id="a77f7-338">**新组：** 未选定</span><span class="sxs-lookup"><span data-stu-id="a77f7-338">**New Group:** Not Selected</span></span>
3.  <span data-ttu-id="a77f7-339">定义**平铺**属性。</span><span class="sxs-lookup"><span data-stu-id="a77f7-339">Define the **Tile** properties.</span></span><br>
    <span data-ttu-id="a77f7-340">**图例：** 设备所遇最后一个小时内的应用程序错误</span><span class="sxs-lookup"><span data-stu-id="a77f7-340">**Legend:** Devices that experienced an application error in the last hour</span></span><br>
    <span data-ttu-id="a77f7-341">**平铺查询：**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```</span><span class="sxs-lookup"><span data-stu-id="a77f7-341">**Tile Query:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```</span></span>
4.  <span data-ttu-id="a77f7-342">定义**列表**的属性。</span><span class="sxs-lookup"><span data-stu-id="a77f7-342">Define the **List** properties.</span></span><br>
    <span data-ttu-id="a77f7-343">**列表查询：**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span><span class="sxs-lookup"><span data-stu-id="a77f7-343">**List Query:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span></span>
5.  <span data-ttu-id="a77f7-344">定义**列标题**。</span><span class="sxs-lookup"><span data-stu-id="a77f7-344">Define **Column Titles**.</span></span><br>
    <span data-ttu-id="a77f7-345">**名称：** 显示名称</span><span class="sxs-lookup"><span data-stu-id="a77f7-345">**Name:** Display Name</span></span><br>
    <span data-ttu-id="a77f7-346">**值：** 最后一个错误</span><span class="sxs-lookup"><span data-stu-id="a77f7-346">**Value:** Last Error</span></span>
6.  <span data-ttu-id="a77f7-347">定义**导航查询**。</span><span class="sxs-lookup"><span data-stu-id="a77f7-347">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 2001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  <span data-ttu-id="a77f7-348">选择**应用**，然后**关闭**。</span><span class="sxs-lookup"><span data-stu-id="a77f7-348">Select **Apply** and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-devices-that-have-been-restarted"></a><span data-ttu-id="a77f7-349">创建显示已重新启动设备拼贴</span><span class="sxs-lookup"><span data-stu-id="a77f7-349">Create a tile that displays devices that have been restarted</span></span>

1.  <span data-ttu-id="a77f7-350">从库中，选择**号码和列表**，然后添加新的平铺。</span><span class="sxs-lookup"><span data-stu-id="a77f7-350">Select **Number & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="a77f7-351">定义**常规**属性。</span><span class="sxs-lookup"><span data-stu-id="a77f7-351">Define the **General** properties.</span></span><br>
    <span data-ttu-id="a77f7-352">**组标题：** 将保留为空</span><span class="sxs-lookup"><span data-stu-id="a77f7-352">**Group Title:** Leave empty</span></span><br>
    <span data-ttu-id="a77f7-353">**新组：** 未选定</span><span class="sxs-lookup"><span data-stu-id="a77f7-353">**New Group:** Not Selected</span></span>
3.  <span data-ttu-id="a77f7-354">定义**平铺**属性。</span><span class="sxs-lookup"><span data-stu-id="a77f7-354">Define the **Tile** properties.</span></span><br>
    <span data-ttu-id="a77f7-355">**图例：** 其中已重新启动应用程序中的最后一个 24 小时和重新启动次数的设备</span><span class="sxs-lookup"><span data-stu-id="a77f7-355">**Legend:** Devices where the application was restarted in the last 24 hours, and number of restarts</span></span><br>
    <span data-ttu-id="a77f7-356">**平铺查询：**```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```</span><span class="sxs-lookup"><span data-stu-id="a77f7-356">**Tile Query:** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```</span></span>
4.  <span data-ttu-id="a77f7-357">定义**列表**的属性。</span><span class="sxs-lookup"><span data-stu-id="a77f7-357">Define the **List** properties.</span></span><br>
    <span data-ttu-id="a77f7-358">**列表查询：**```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```</span><span class="sxs-lookup"><span data-stu-id="a77f7-358">**List Query:** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```</span></span>
5.  <span data-ttu-id="a77f7-359">定义**列标题**。</span><span class="sxs-lookup"><span data-stu-id="a77f7-359">Define **Column Titles**.</span></span><br>
    <span data-ttu-id="a77f7-360">**名称：** 显示名称</span><span class="sxs-lookup"><span data-stu-id="a77f7-360">**Name:** Display Name</span></span><br>
    <span data-ttu-id="a77f7-361">**值：** 重新启动次数</span><span class="sxs-lookup"><span data-stu-id="a77f7-361">**Value:** Number of Restarts</span></span>
6.  <span data-ttu-id="a77f7-362">定义**导航查询**。</span><span class="sxs-lookup"><span data-stu-id="a77f7-362">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  <span data-ttu-id="a77f7-363">选择**应用**，然后**关闭**。</span><span class="sxs-lookup"><span data-stu-id="a77f7-363">Select **Apply** and then **Close**.</span></span>
8.  <span data-ttu-id="a77f7-364">选择**保存**以保存您的仪表板。</span><span class="sxs-lookup"><span data-stu-id="a77f7-364">Select **Save** to save your dashboard.</span></span>

<span data-ttu-id="a77f7-365">现在您已完成创建您的视图。</span><span class="sxs-lookup"><span data-stu-id="a77f7-365">Now you’ve completed creating your views.</span></span>

<span data-ttu-id="a77f7-366">您可以使用 Microsoft 操作管理套件门户或[Windows Phone](https://www.microsoft.com/en-us/store/p/microsoft-operations-management-suite/9wzdncrfjz2r)、 [iOS](https://itunes.apple.com/us/app/microsoft-operations-management-suite/id1042424859)或[Android](https://play.google.com/store/apps/details?id=com.microsoft.operations.AndroidPhone)的操作管理套件移动客户端访问您的视图。</span><span class="sxs-lookup"><span data-stu-id="a77f7-366">You can use the Microsoft Operations Management Suite portal or Operations Management Suite mobile clients for [Windows Phone](https://www.microsoft.com/en-us/store/p/microsoft-operations-management-suite/9wzdncrfjz2r), [iOS](https://itunes.apple.com/us/app/microsoft-operations-management-suite/id1042424859), or [Android](https://play.google.com/store/apps/details?id=com.microsoft.operations.AndroidPhone) to access your views.</span></span>

## <a name="configure-alerts-in-operations-management-suite"></a><span data-ttu-id="a77f7-367">在操作管理套件中配置警报</span><span class="sxs-lookup"><span data-stu-id="a77f7-367">Configure Alerts in Operations Management Suite</span></span>
<span data-ttu-id="a77f7-368"><a name="Alerts"></a>时 Skype 会议室系统设备遇到的问题、 Microsoft 操作管理套件可以提升警报通知问题的详细信息的管理员。</span><span class="sxs-lookup"><span data-stu-id="a77f7-368"><a name="Alerts"> </a> When a Skype Room Systems device encounters an issue, Microsoft Operations Management Suite can raise alerts to notify the administrators with the details of the issue.</span></span>

<span data-ttu-id="a77f7-369">操作管理套件包括通过计划的日志搜索定期运行的内置警报机制。</span><span class="sxs-lookup"><span data-stu-id="a77f7-369">Operations Management Suite includes a built-in alerting mechanism that runs through scheduled log searches at regular intervals.</span></span> <span data-ttu-id="a77f7-370">如果日志搜索的结果与某个特定条件匹配，则创建警报的记录。</span><span class="sxs-lookup"><span data-stu-id="a77f7-370">If the results of the log search match some particular criteria, an alert record is created.</span></span>

<span data-ttu-id="a77f7-371">![OMS 通知机制](../../media/Deploy_OMS_6.png "OMS 通知机制")</span><span class="sxs-lookup"><span data-stu-id="a77f7-371">![OMS alert mechanism](../../media/Deploy_OMS_6.png "OMS alert mechanism")</span></span>

<span data-ttu-id="a77f7-372">规则可以自动运行主动通知您通知或调用其他进程的一个或多个操作。</span><span class="sxs-lookup"><span data-stu-id="a77f7-372">The rule can then automatically run one or more actions to proactively notify you of the alert or invoke another process.</span></span> <span data-ttu-id="a77f7-373">操作管理套件通知可能的选项包括：</span><span class="sxs-lookup"><span data-stu-id="a77f7-373">The possible options with Operations Management Suite alerts are:</span></span>
-   <span data-ttu-id="a77f7-374">发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="a77f7-374">Sending an email</span></span>
-   <span data-ttu-id="a77f7-375">调用外部进程通过 HTTP POST 请求</span><span class="sxs-lookup"><span data-stu-id="a77f7-375">Invoking an external process through an HTTP POST request</span></span>
-   <span data-ttu-id="a77f7-376">Azure 自动化服务中启动 runbook</span><span class="sxs-lookup"><span data-stu-id="a77f7-376">Starting a runbook in Azure Automation service</span></span>

<span data-ttu-id="a77f7-377">请参阅[了解日志分析中的通知](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts)，以详细了解如何操作管理套件中的通知。</span><span class="sxs-lookup"><span data-stu-id="a77f7-377">See [Understanding alerts in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts) to learn more about the alerts in Operations Management Suite.</span></span>

> [!NOTE]
> <span data-ttu-id="a77f7-378">Skype 会议室系统设备生成硬件或应用程序错误时，以下示例将发送电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="a77f7-378">The following examples send email alerts when a Skype Room Systems device generates a hardware or an application error.</span></span> 


### <a name="configure-an-email-alert-for-skype-room-systems-hardware-issues"></a><span data-ttu-id="a77f7-379">配置电子邮件通知 Skype 会议室系统硬件问题</span><span class="sxs-lookup"><span data-stu-id="a77f7-379">Configure an email alert for Skype Room Systems hardware issues</span></span>

<span data-ttu-id="a77f7-380">配置检查的最后一个小时内过硬件问题的 Skype 会议室系统设备通知规则。</span><span class="sxs-lookup"><span data-stu-id="a77f7-380">Configure an alert rule that checks for Skype Room Systems devices that have had hardware issues within the last hour.</span></span>
1.  <span data-ttu-id="a77f7-381">登录到[Microsoft 操作管理套件门户](http://aka.ms/omsportal)。</span><span class="sxs-lookup"><span data-stu-id="a77f7-381">Sign in to the [Microsoft Operations Management Suite portal](http://aka.ms/omsportal).</span></span>

2.  <span data-ttu-id="a77f7-382">选择**日志搜索**。</span><span class="sxs-lookup"><span data-stu-id="a77f7-382">Select **Log Search**.</span></span>

3.  <span data-ttu-id="a77f7-383">输入以下查询，，，然后选择**运行**。</span><span class="sxs-lookup"><span data-stu-id="a77f7-383">Enter the following query, and then select **Run**.</span></span><br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF 
    |sort by TimeGenerated desc
    ```

4.  <span data-ttu-id="a77f7-384">执行查询后，选择**通知**。</span><span class="sxs-lookup"><span data-stu-id="a77f7-384">After the query is executed, select **Alert**.</span></span> <span data-ttu-id="a77f7-385">这将打开**添加通知规则**页。</span><span class="sxs-lookup"><span data-stu-id="a77f7-385">This will open the **Add Alert Rule** page.</span></span>

5.  <span data-ttu-id="a77f7-386">使用下面的信息配置通知设置：</span><span class="sxs-lookup"><span data-stu-id="a77f7-386">Configure alert settings by using the information below:</span></span><br>
    <span data-ttu-id="a77f7-387">**规则名称：** Skype 会议室系统硬件故障警报</span><span class="sxs-lookup"><span data-stu-id="a77f7-387">**Rule Name:** Skype Room Systems Hardware Failure Alert</span></span><br>
    <span data-ttu-id="a77f7-388">**说明：** 遇到硬件问题的最后一个小时内的设备的列表</span><span class="sxs-lookup"><span data-stu-id="a77f7-388">**Description:** List of devices that encountered a hardware issue within the last hour</span></span><br>
    <span data-ttu-id="a77f7-389">**严重性：** 关键</span><span class="sxs-lookup"><span data-stu-id="a77f7-389">**Severity:** Critical</span></span><br>
    <span data-ttu-id="a77f7-390">**查询：** 使用预填充的搜索查询</span><span class="sxs-lookup"><span data-stu-id="a77f7-390">**Query:** Use the prepopulated search query</span></span><br>
    <span data-ttu-id="a77f7-391">**时间段：** 1 小时</span><span class="sxs-lookup"><span data-stu-id="a77f7-391">**Time Window:** 1 hour</span></span><br>
    <span data-ttu-id="a77f7-392">**通知的频率：** 1 小时</span><span class="sxs-lookup"><span data-stu-id="a77f7-392">**Alert Frequency:** 1 hour</span></span><br>
    <span data-ttu-id="a77f7-393">**的结果数：** 大于 0</span><span class="sxs-lookup"><span data-stu-id="a77f7-393">**Number of results:** Greater than 0</span></span><br>
    <span data-ttu-id="a77f7-394">**电子邮件主题：** Skype 会议室系统硬件故障警报</span><span class="sxs-lookup"><span data-stu-id="a77f7-394">**Email Subject:** Skype Room Systems Hardware Failure Alert</span></span><br>
    <span data-ttu-id="a77f7-395">**收件人：** 包括使用分号作为分隔符的电子邮件地址</span><span class="sxs-lookup"><span data-stu-id="a77f7-395">**Recipients:** Include the email addresses, using semicolons as separators</span></span><br>

6.  <span data-ttu-id="a77f7-396">选择**保存**。</span><span class="sxs-lookup"><span data-stu-id="a77f7-396">Select **Save**.</span></span>

### <a name="configure-an-email-alert-for-skype-room-systems-application-issues"></a><span data-ttu-id="a77f7-397">配置电子邮件通知 Skype 会议室系统应用程序问题</span><span class="sxs-lookup"><span data-stu-id="a77f7-397">Configure an email alert for Skype Room Systems application issues</span></span>

<span data-ttu-id="a77f7-398">配置通知的规则，来检查 Skype 会议室系统设备的最后一个小时内已应用程序问题。</span><span class="sxs-lookup"><span data-stu-id="a77f7-398">Configure an alert rule, that checks for Skype Room Systems devices that have had application issues within the last hour.</span></span>
1.  <span data-ttu-id="a77f7-399">选择**日志搜索**。</span><span class="sxs-lookup"><span data-stu-id="a77f7-399">Select **Log Search**.</span></span>

2.  <span data-ttu-id="a77f7-400">输入以下查询，，，然后选择**运行**。</span><span class="sxs-lookup"><span data-stu-id="a77f7-400">Enter the following query, and then select **Run**.</span></span><br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(10h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF
    | sort by TimeGenerated desc
    ```

3.  <span data-ttu-id="a77f7-401">执行查询后，选择**通知**。</span><span class="sxs-lookup"><span data-stu-id="a77f7-401">After the query is executed, select **Alert**.</span></span> <span data-ttu-id="a77f7-402">这将打开**添加通知规则**页。</span><span class="sxs-lookup"><span data-stu-id="a77f7-402">This will open the **Add Alert Rule** page.</span></span>

4.  <span data-ttu-id="a77f7-403">使用下面的信息配置通知设置：</span><span class="sxs-lookup"><span data-stu-id="a77f7-403">Configure alert settings by using the information below:</span></span><br>
    <span data-ttu-id="a77f7-404">**规则名称：** Skype 会议室系统应用程序失败通知</span><span class="sxs-lookup"><span data-stu-id="a77f7-404">**Rule Name:** Skype Room Systems Application Failure Alert</span></span><br>
    <span data-ttu-id="a77f7-405">**说明：** 遇到的应用程序问题的最后一个小时内的设备的列表</span><span class="sxs-lookup"><span data-stu-id="a77f7-405">**Description:** List of devices that encountered an application issue within the last hour</span></span><br>
    <span data-ttu-id="a77f7-406">**严重性：** 关键</span><span class="sxs-lookup"><span data-stu-id="a77f7-406">**Severity:** Critical</span></span><br>
    <span data-ttu-id="a77f7-407">**查询：** 使用预填充的搜索查询</span><span class="sxs-lookup"><span data-stu-id="a77f7-407">**Query:** Use the prepopulated search query</span></span><br>
    <span data-ttu-id="a77f7-408">**时间段：** 1 小时</span><span class="sxs-lookup"><span data-stu-id="a77f7-408">**Time Window:** 1 hour</span></span><br>
    <span data-ttu-id="a77f7-409">**通知的频率：** 1 小时</span><span class="sxs-lookup"><span data-stu-id="a77f7-409">**Alert Frequency:** 1 hour</span></span><br>
    <span data-ttu-id="a77f7-410">**的结果数：** 大于 0</span><span class="sxs-lookup"><span data-stu-id="a77f7-410">**Number of results:** Greater than 0</span></span><br>
    <span data-ttu-id="a77f7-411">**电子邮件主题：** Skype 会议室系统应用程序失败通知</span><span class="sxs-lookup"><span data-stu-id="a77f7-411">**Email Subject:** Skype Room Systems Application Failure Alert</span></span><br>
    <span data-ttu-id="a77f7-412">**收件人：** 包括使用分号作为分隔符的电子邮件地址</span><span class="sxs-lookup"><span data-stu-id="a77f7-412">**Recipients:** Include the email addresses, using semicolons as separators</span></span>

5.  <span data-ttu-id="a77f7-413">选择**保存**。</span><span class="sxs-lookup"><span data-stu-id="a77f7-413">Select **Save**.</span></span>

<span data-ttu-id="a77f7-414">现在您已完成定义通知。</span><span class="sxs-lookup"><span data-stu-id="a77f7-414">Now you’ve completed defining alerts.</span></span> <span data-ttu-id="a77f7-415">您可以使用上面的示例定义其他通知。</span><span class="sxs-lookup"><span data-stu-id="a77f7-415">You can define additional alerts by using the examples above.</span></span>

<span data-ttu-id="a77f7-416">生成警报时，您将获取电子邮件，其中列出遇到问题的最后一个小时内的设备。</span><span class="sxs-lookup"><span data-stu-id="a77f7-416">When an alert is generated, you’ll get an email that lists the devices that encountered an issue within the last hour.</span></span>

<span data-ttu-id="a77f7-417">![示例 OMS 通知电子邮件](../../media/Deploy_OMS_7.png "示例 OMS 通知电子邮件")</span><span class="sxs-lookup"><span data-stu-id="a77f7-417">![Sample OMS alert email](../../media/Deploy_OMS_7.png "Sample OMS alert email")</span></span>

<span data-ttu-id="a77f7-418">使用通知设置页面以修改现有警报配置，或要禁用或删除一条通知。</span><span class="sxs-lookup"><span data-stu-id="a77f7-418">You use an alert settings page to modify an existing alert configuration, or to disable or remove an alert.</span></span>

<span data-ttu-id="a77f7-419">![OMS 警报设置](../../media/Deploy_OMS_8.png "OMS 警报设置")</span><span class="sxs-lookup"><span data-stu-id="a77f7-419">![OMS alert settings](../../media/Deploy_OMS_8.png "OMS alert settings")</span></span>

> [!NOTE]
> <span data-ttu-id="a77f7-420">您可能需要使用 Azure 门户网站添加或修改操作管理套件通知，如果您的操作管理套件工作区配置到 Azure 扩展操作管理套件通知。</span><span class="sxs-lookup"><span data-stu-id="a77f7-420">You might need to use the Azure portal to add or modify Operations Management Suite alerts if your Operations Management Suite workspace is configured to extend the Operations Management Suite alerts into Azure.</span></span> <span data-ttu-id="a77f7-421">有关详细信息，请参阅[从 OMS 门户到 Azure 扩展通知](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-alerts-extend)。</span><span class="sxs-lookup"><span data-stu-id="a77f7-421">For more details, see [Extend alerts from OMS portal into Azure](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-alerts-extend).</span></span>

## <a name="configure-all-devices-for-operations-management-suite"></a><span data-ttu-id="a77f7-422">配置所有设备的操作管理套件</span><span class="sxs-lookup"><span data-stu-id="a77f7-422">Configure all devices for Operations Management Suite</span></span>
<span data-ttu-id="a77f7-423"><a name="configure_all_devices"></a>配置仪表板和通知后，您可以设置和配置所有 Skype 会议室系统设备，以完成监控部署上的操作管理套件代理。</span><span class="sxs-lookup"><span data-stu-id="a77f7-423"><a name="configure_all_devices"> </a> After the dashboards and alerts are configured, you can set up and configure Operations Management Suite agents on all Skype Room Systems devices to complete your monitoring deployment.</span></span>

<span data-ttu-id="a77f7-424">尽管您可以安装，并在每个设备上手动配置操作管理套件代理，但强烈建议您利用现有软件部署工具和方法。</span><span class="sxs-lookup"><span data-stu-id="a77f7-424">Although you can install and configure the Operations Management Suite agents manually on each device, we highly recommend you leverage existing software deployment tools and methods.</span></span>

<span data-ttu-id="a77f7-425">如果您首次构建 Skype 会议室系统的设备，您可能想要包括的生成过程一部分的操作管理套件代理安装和配置步骤。</span><span class="sxs-lookup"><span data-stu-id="a77f7-425">If you’re building your Skype Room Systems devices for the first time, you might want to include the Operations Management Suite agent setup and configuration steps as part of your build process.</span></span> <span data-ttu-id="a77f7-426">有关详细信息，请参阅[安装使用命令行的代理](https://docs.microsoft.com/azure/log-analytics/log-analytics-agent-windows#install-the-agent-using-the-command-line)。</span><span class="sxs-lookup"><span data-stu-id="a77f7-426">For more information, see [Install the agent using the command line](https://docs.microsoft.com/azure/log-analytics/log-analytics-agent-windows#install-the-agent-using-the-command-line).</span></span>

### <a name="deploying-operations-management-suite-agents-by-using-a-group-policy-object"></a><span data-ttu-id="a77f7-427">使用组策略对象部署操作管理套件代理</span><span class="sxs-lookup"><span data-stu-id="a77f7-427">Deploying Operations Management Suite agents by using a Group Policy Object</span></span>

<span data-ttu-id="a77f7-428">如果在执行操作管理套件之前，已部署 Skype 会议室系统的设备，您可以使用提供的脚本设置和使用 Active Directory 组策略配置代理。</span><span class="sxs-lookup"><span data-stu-id="a77f7-428">If you already deployed your Skype Room Systems devices before you implement Operations Management Suite, you can use the provided script to set up and configure the agents by using Active Directory group policies.</span></span>

1.  <span data-ttu-id="a77f7-429">创建共享的网络路径，并向**域计算机**组授予读取访问权限。</span><span class="sxs-lookup"><span data-stu-id="a77f7-429">Create a shared network path and grant read access to **Domain Computers** group.</span></span>

2.  <span data-ttu-id="a77f7-430">下载 64 位版本的操作管理套件代理用于 Windows 的从<http://go.microsoft.com/fwlink/?LinkID=517476></span><span class="sxs-lookup"><span data-stu-id="a77f7-430">Download the 64-bit version of the Operations Management Suite Agent for Windows from <http://go.microsoft.com/fwlink/?LinkID=517476></span></span>

3.  <span data-ttu-id="a77f7-431">安装程序包的内容解压到网络共享。</span><span class="sxs-lookup"><span data-stu-id="a77f7-431">Extract the contents of the setup package into the network share.</span></span>
    1.  <span data-ttu-id="a77f7-432">打开命令提示符窗口，并执行**MMASetup AMD64.exe /c**</span><span class="sxs-lookup"><span data-stu-id="a77f7-432">Open a Command Prompt window, and then execute **MMASetup-AMD64.exe /c**</span></span>
    2.  <span data-ttu-id="a77f7-433">指定您刚创建的共享和提取内容。</span><span class="sxs-lookup"><span data-stu-id="a77f7-433">Specify the share you just created, and extract the content.</span></span>

4.  <span data-ttu-id="a77f7-434">创建新的组策略对象，并将其分配给组织单位 Skype 会议室系统计算机帐户的位置。</span><span class="sxs-lookup"><span data-stu-id="a77f7-434">Create a new Group Policy Object and assign it to the organizational unit where Skype Room Systems machine accounts are located.</span></span>

5.  <span data-ttu-id="a77f7-435">配置 PowerShell 执行策略：</span><span class="sxs-lookup"><span data-stu-id="a77f7-435">Configure PowerShell execution policy:</span></span>
    1.  <span data-ttu-id="a77f7-436">编辑新创建的组策略对象，并导航到计算机配置\\策略\\管理模板\\Windows 组件\\Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a77f7-436">Edit the newly created Group Policy Object and navigate to Computer Configuration \\ Policies \\ Administrative Templates \\ Windows Components \\ Windows PowerShell</span></span>
    2.  <span data-ttu-id="a77f7-437">启用**脚本执行打开**并**允许本地**脚本设置**执行策略**。</span><span class="sxs-lookup"><span data-stu-id="a77f7-437">Enable the **Turn on Script Execution** and set **Execution Policy** to **Allow Local Scripts**.</span></span>

6.  <span data-ttu-id="a77f7-438">配置启动脚本：</span><span class="sxs-lookup"><span data-stu-id="a77f7-438">Configure the startup script:</span></span>
    1.  <span data-ttu-id="a77f7-439">复制以下脚本并将其保存为安装 OMSAgent.ps1。</span><span class="sxs-lookup"><span data-stu-id="a77f7-439">Copy the following script and save it as Install-OMSAgent.ps1.</span></span>
    2.  <span data-ttu-id="a77f7-440">修改 WorkspaceId、 WorkspaceKey 和 SetupPath 参数，以匹配您的配置。</span><span class="sxs-lookup"><span data-stu-id="a77f7-440">Modify WorkspaceId, WorkspaceKey, and SetupPath parameters to match your configuration.</span></span>
    3.  <span data-ttu-id="a77f7-441">编辑相同的组策略对象，并导航到计算机配置\\策略\\Windows 设置\\脚本 （启动/关机）</span><span class="sxs-lookup"><span data-stu-id="a77f7-441">Edit the same Group Policy Object and navigate to Computer Configuration \\ Policies \\ Windows Settings \\ Scripts (Startup/Shutdown)</span></span>
    4.  <span data-ttu-id="a77f7-442">双击可选择**启动**中，，然后选择**PowerShell 脚本**。</span><span class="sxs-lookup"><span data-stu-id="a77f7-442">Double-click to select **Startup**, and then select **PowerShell Scripts**.</span></span>
    5.  <span data-ttu-id="a77f7-443">选择**显示文件**，然后将**安装 OMSAgent.ps1**文件复制到该文件夹。</span><span class="sxs-lookup"><span data-stu-id="a77f7-443">Select **Show Files**, and then copy the **Install-OMSAgent.ps1** file to that folder.</span></span>
    6.  <span data-ttu-id="a77f7-444">选择**添加**，然后**浏览**。</span><span class="sxs-lookup"><span data-stu-id="a77f7-444">Select **Add**, and then **Browse**.</span></span>
    7.  <span data-ttu-id="a77f7-445">选择您刚复制的 ps1 脚本。</span><span class="sxs-lookup"><span data-stu-id="a77f7-445">Select the ps1 script you just copied.</span></span>

7.  <span data-ttu-id="a77f7-446">Skype 会议室系统设备应安装和配置第二个重新启动 Microsoft 监控代理。</span><span class="sxs-lookup"><span data-stu-id="a77f7-446">Skype Room Systems devices should install and configure the Microsoft Monitoring agent with the second reboot.</span></span>


    ```
    # Install-OMSAgent.ps1
    <# 
    Date:        04/20/2018 
    Script:      Install-OMSAgent.ps1 
    Version:     1.0
    #> 
    
    # Set the parameters
    $WorkspaceId = "<your workspace id>"
    $WorkspaceKey = "<your workspace key>"
    $SetupPath = "\\Server\Share"
    
    $SetupParameters = "/qn NOAPM=1 ADD_OPINSIGHTS_WORKSPACE=1 OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE=0 OPINSIGHTS_WORKSPACE_ID=$WorkspaceId OPINSIGHTS_WORKSPACE_KEY=$WorkspaceKey AcceptEndUserLicenseAgreement=1"
    
    # $SetupParameters = $SetupParameters + " OPINSIGHTS_PROXY_URL=<Proxy server URL> OPINSIGHTS_PROXY_USERNAME=<Proxy server username> OPINSIGHTS_PROXY_PASSWORD=<Proxy server password>"
    
    # Start PowerShell logging
    Start-Transcript -Path C:\OMSAgentInstall.Log  
    
    # Check if the Microsoft Monitoring Agent is installed
    $mma = New-Object -ComObject 'AgentConfigManager.MgmtSvcCfg'
    
    # Check if the Microsoft Monitoring agent is installed 
    if (!$mma)
    {
        #Install agent
        Start-Process -FilePath "$SetupPath\Setup.exe" -ArgumentList $SetupParameters -ErrorAction Stop -Wait
    }
    
    # Check if the agent has a valid configuration
    $CheckOMS = $mma.GetCloudWorkspace($WorkspaceId).AgentId
    if (!$CheckOMS)
    {
        # Apply new configuration
        $mma.AddCloudWorkspace($WorkspaceId, $WorkspaceKey)
        $mma.ReloadConfiguration()
    } 
    
    Stop-Transcript 
    
    ```
    
> [!NOTE]
> <span data-ttu-id="a77f7-447">当您需要重新配置代理、 将其移至不同的工作区中，或在初始安装后修改代理设置时，您可以参考文章[管理和维护日志分析代理](https://docs.microsoft.com/azure/log-analytics/log-analytics-agent-manage)。</span><span class="sxs-lookup"><span data-stu-id="a77f7-447">You can refer to the article [Managing and maintaining the Log Analytics agent](https://docs.microsoft.com/azure/log-analytics/log-analytics-agent-manage) when you need to reconfigure an agent, move it to a different workspace, or modify proxy settings after the initial installation.</span></span>

## <a name="additional-solutions"></a><span data-ttu-id="a77f7-448">其他解决方案</span><span class="sxs-lookup"><span data-stu-id="a77f7-448">Additional Solutions</span></span>
<span data-ttu-id="a77f7-449"><a name="Solutions"> </a></span><span class="sxs-lookup"><span data-stu-id="a77f7-449"></span></span>

<span data-ttu-id="a77f7-450">操作管理套件提供了内置解决方案通过其[解决方案库](https://docs.microsoft.com/azure/log-analytics/log-analytics-add-solutions)来进一步帮助监视您的环境。</span><span class="sxs-lookup"><span data-stu-id="a77f7-450">Operations Management Suite provides built-in solutions through its [solution gallery](https://docs.microsoft.com/azure/log-analytics/log-analytics-add-solutions) to further help you monitor your environment.</span></span> <span data-ttu-id="a77f7-451">我们强烈建议将[警报管理](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management)和[代理运行状况](https://docs.microsoft.com/azure/operations-management-suite/oms-solution-agenthealth)解决方案添加到您的操作管理套件工作区。</span><span class="sxs-lookup"><span data-stu-id="a77f7-451">We highly recommend that you add [Alert Management](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management) and [Agent Health](https://docs.microsoft.com/azure/operations-management-suite/oms-solution-agenthealth) solutions to your Operations Management Suite workspace as well.</span></span>

<span data-ttu-id="a77f7-452">![OMS 视图](../../media/Deploy_OMS_9.png "OMS 视图")</span><span class="sxs-lookup"><span data-stu-id="a77f7-452">![OMS views](../../media/Deploy_OMS_9.png "OMS views")</span></span>

> [!NOTE]
> <span data-ttu-id="a77f7-453">代理运行状况解决方案可帮助您确定您的环境中已过时或断开操作管理套件代理和警报管理解决方案提供了有关已引发的给定期间内的警报的详细信息。</span><span class="sxs-lookup"><span data-stu-id="a77f7-453">The Agent Health solution can help you identify outdated or broken Operations Management Suite agents within your environment, and the Alert Management solution provides details about the alerts that have been raised within a given period.</span></span>

## <a name="see-also"></a><span data-ttu-id="a77f7-454">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a77f7-454">See also</span></span>

#### 
[<span data-ttu-id="a77f7-455">规划使用 OMS 的 Skype 会议室系统 v2 管理</span><span class="sxs-lookup"><span data-stu-id="a77f7-455">Plan Skype Room Systems v2 management with OMS</span></span>](../../plan-your-deployment/clients-and-devices/oms-management.md)
  
[<span data-ttu-id="a77f7-456">管理与 OMS 的 Skype 会议室系统 v2 设备</span><span class="sxs-lookup"><span data-stu-id="a77f7-456">Manage Skype Room Systems v2 devices with OMS</span></span>](../../manage/skype-room-systems-v2/oms.md)