---
title: 部署 Skype 会议室系统 v2 管理使用 Azure 监视器
ms.author: jambirk
author: jambirk
ms.reviewer: Turgayo
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d86ff657-ee92-4b06-aee3-d4c43090bdcb
description: 本文讨论如何部署 Skype 会议室系统 v2 设备的管理方式集成的端到端使用 Azure 监视器。
ms.openlocfilehash: 6a90f5b1dcbbdbab9c4149717e16a01c3a5f5ba1
ms.sourcegitcommit: 09fcd68e30e7f83110f98172382c74f970b339a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2019
ms.locfileid: "29448446"
---
# <a name="deploy-skype-room-systems-v2-management-with-azure-monitor"></a><span data-ttu-id="a68b2-103">部署 Skype 会议室系统 v2 管理使用 Azure 监视器</span><span class="sxs-lookup"><span data-stu-id="a68b2-103">Deploy Skype Room Systems v2 management with Azure Monitor</span></span>

<span data-ttu-id="a68b2-104">本文讨论如何设置和部署的 Skype 会议室系统 v2 设备集成的端到端管理使用 Azure 监视器。</span><span class="sxs-lookup"><span data-stu-id="a68b2-104">This article discusses how to set up and deploy integrated, end-to-end management of Skype Room Systems v2 devices by using Azure Monitor.</span></span>

<span data-ttu-id="a68b2-105">您可以配置内 Azure 监视器提供基本遥测日志分析和通知将帮助您管理 Skype 会议室内设备。</span><span class="sxs-lookup"><span data-stu-id="a68b2-105">You can configure Log Analytics within Azure Monitor to provide basic telemetry and alerts that will help you manage Skype meeting room devices.</span></span> <span data-ttu-id="a68b2-106">随着您管理解决方案逐渐成熟，您可能决定部署其他数据和管理功能，以创建设备的可用性和性能的详细的视图。</span><span class="sxs-lookup"><span data-stu-id="a68b2-106">As your management solution matures, you might decide to deploy additional data and management capabilities to create a more detailed view of device availability and performance.</span></span>

<span data-ttu-id="a68b2-107">按照本指南，您可以使用类似下面的示例仪表板获取设备可用性、 应用程序和硬件运行状况和 Skype 会议室系统 v2 应用程序和操作系统版本分发报告的详细的状态。</span><span class="sxs-lookup"><span data-stu-id="a68b2-107">By following this guide, you can use a dashboard like the following example to get detailed status reporting for device availability, application and hardware health, and Skype Room Systems v2 application and operating system version distribution.</span></span>

<span data-ttu-id="a68b2-108">![SR v2 示例日志分析视图](../../media/Deploy-Azure-Monitor-1.png "SR v2 示例日志分析视图")</span><span class="sxs-lookup"><span data-stu-id="a68b2-108">![Sample Log Analytics view for SRS v2](../../media/Deploy-Azure-Monitor-1.png "Sample Log Analytics view for SRS v2")</span></span>

<span data-ttu-id="a68b2-109">你需要在高级别执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="a68b2-109">At a high level, you need to perform the following tasks:</span></span>


1.  [<span data-ttu-id="a68b2-110">验证日志分析配置</span><span class="sxs-lookup"><span data-stu-id="a68b2-110">Validate Log Analytics configuration</span></span>](azure-monitor.md#validate_LogAnalytics)
2.  [<span data-ttu-id="a68b2-111">配置日志分析管理安装程序测试设备</span><span class="sxs-lookup"><span data-stu-id="a68b2-111">Configure test devices for Log Analytics management setup</span></span>](azure-monitor.md#configure_test_devices)
3.  [<span data-ttu-id="a68b2-112">映射自定义字段</span><span class="sxs-lookup"><span data-stu-id="a68b2-112">Map custom fields</span></span>](azure-monitor.md#Custom_fields)
4.  [<span data-ttu-id="a68b2-113">日志分析中定义的 Skype 会议室系统 v2 视图</span><span class="sxs-lookup"><span data-stu-id="a68b2-113">Define the Skype Room Systems v2 views in Log Analytics</span></span>](azure-monitor.md#Define_Views)
5.  [<span data-ttu-id="a68b2-114">定义通知</span><span class="sxs-lookup"><span data-stu-id="a68b2-114">Define alerts</span></span>](azure-monitor.md#Alerts)
6.  [<span data-ttu-id="a68b2-115">将所有设备都配置为监控</span><span class="sxs-lookup"><span data-stu-id="a68b2-115">Configure all devices for Monitoring</span></span>](azure-monitor.md#configure_all_devices)
7.  [<span data-ttu-id="a68b2-116">配置其他 Azure 监视解决方案</span><span class="sxs-lookup"><span data-stu-id="a68b2-116">Configure additional Azure Monitor solutions</span></span>](azure-monitor.md#Solutions)

> [!IMPORTANT]
> <span data-ttu-id="a68b2-117">使用最少的配置，Azure 监视器日志分析可以监视运行 Windows 操作系统的计算机，但仍有一些需要在开始部署到所有 Skype 会议室系统的代理之前的 Skype 会议室系统 v2 特定步骤设备。</span><span class="sxs-lookup"><span data-stu-id="a68b2-117">Although with minimal configuration, Azure Monitor Log Analytics can monitor a computer running a Windows operating system, there are still some Skype Room Systems v2–specific steps that you need to take before you start deploying agents to all Skype Room Systems devices.</span></span>
> <span data-ttu-id="a68b2-118">因此，我们强烈建议您受控的安装和配置正确的顺序执行所有配置步骤。</span><span class="sxs-lookup"><span data-stu-id="a68b2-118">Therefore, we highly recommend you perform all configuration steps in the right order for a controlled setup and configuration.</span></span> <span data-ttu-id="a68b2-119">最终结果的质量很大程度取决于的初始配置的质量。</span><span class="sxs-lookup"><span data-stu-id="a68b2-119">The quality of the end result very much depends on the quality of the initial configuration.</span></span>

## <a name="validate-log-analytics-configuration"></a><span data-ttu-id="a68b2-120">验证日志分析配置</span><span class="sxs-lookup"><span data-stu-id="a68b2-120">Validate Log Analytics configuration</span></span>
<span data-ttu-id="a68b2-121"><a name="validate_LogAnalytics"> </a></span><span class="sxs-lookup"><span data-stu-id="a68b2-121"></span></span>

<span data-ttu-id="a68b2-122">您需要具有要开始从 Skype 会议室系统 v2 设备收集日志的日志分析工作区。</span><span class="sxs-lookup"><span data-stu-id="a68b2-122">You need to have a Log Analytics workspace to start collecting logs from Skype Room Systems v2 devices.</span></span> <span data-ttu-id="a68b2-123">工作区是使用其自己的数据存储库、 数据源和解决方案的唯一日志分析环境。</span><span class="sxs-lookup"><span data-stu-id="a68b2-123">A workspace is a unique Log Analytics environment with its own data repository, data sources, and solutions.</span></span> <span data-ttu-id="a68b2-124">如果您已有现有日志分析工作区，您可能使用它来监视 Skype 会议室系统 v2 部署或或者，您可以创建一个专用的日志分析工作区特定到 Skype 会议室系统 v2 监控需求。</span><span class="sxs-lookup"><span data-stu-id="a68b2-124">If you already have an existing Log Analytics workspace, you might use it to monitor your Skype Room Systems v2 deployment or alternatively, you can create a dedicated Log Analytics workspace specific to your Skype Room Systems v2 monitoring needs.</span></span>

<span data-ttu-id="a68b2-125">如果您需要创建新的日志分析工作区，请按照[创建 Azure 门户中的日志分析工作区](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace)一文中的说明</span><span class="sxs-lookup"><span data-stu-id="a68b2-125">If you need to create a new Log Analytics workspace, follow the instructions in the article [Create a Log Analytics workspace in the Azure portal](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace)</span></span>

> [!NOTE]
> <span data-ttu-id="a68b2-126">若要使用日志分析与 Azure 监视器，您需要具有活动的 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="a68b2-126">To use Log Analytics with Azure Monitor, you need to have an active Azure subscription.</span></span> <span data-ttu-id="a68b2-127">如果您没有 Azure 订阅，您可以创建[免费的试用订阅](https://azure.microsoft.com/free)作为起点。</span><span class="sxs-lookup"><span data-stu-id="a68b2-127">If you don’t have an Azure subscription, you can create [a free trial subscription](https://azure.microsoft.com/free) as a starting point.</span></span>

### <a name="configure-log-analytics-to-collect-skype-room-systems-v2-event-logs"></a><span data-ttu-id="a68b2-128">配置日志分析收集 Skype 会议室系统 v2 事件日志</span><span class="sxs-lookup"><span data-stu-id="a68b2-128">Configure Log Analytics to collect Skype Room Systems v2 event logs</span></span>

<span data-ttu-id="a68b2-129">日志分析仅收集在设置中指定的 Windows 事件日志中的事件。</span><span class="sxs-lookup"><span data-stu-id="a68b2-129">Log Analytics only collects events from the Windows event logs that are specified in the settings.</span></span> <span data-ttu-id="a68b2-130">为每个日志中，会收集仅将所选的严重级别的事件。</span><span class="sxs-lookup"><span data-stu-id="a68b2-130">For each log, only the events with the selected severities are collected.</span></span>

<span data-ttu-id="a68b2-131">您需要配置日志分析收集监视 Skype 会议室系统 v2 设备和应用程序状态所需的日志。</span><span class="sxs-lookup"><span data-stu-id="a68b2-131">You need to configure Log Analytics to collect the logs required to monitor Skype Room Systems v2 device and application status.</span></span> <span data-ttu-id="a68b2-132">Skype 会议室系统 v2 设备使用**Skype 会议室系统**事件日志。</span><span class="sxs-lookup"><span data-stu-id="a68b2-132">Skype Room Systems v2 devices use the **Skype Room System** event log.</span></span>

<span data-ttu-id="a68b2-133">若要配置日志分析，以收集 Skype 会议室系统 v2 事件，请参阅[在 Azure 监视器中的 Windows 事件日志数据源](https://docs.microsoft.com/azure/azure-monitor/platform/data-sources-windows-events)</span><span class="sxs-lookup"><span data-stu-id="a68b2-133">To configure Log Analytics to collect the Skype Room Systems v2 events, see [Windows event log data sources in Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/platform/data-sources-windows-events)</span></span>

<span data-ttu-id="a68b2-134">![事件日志设置](../../media/Deploy-Azure-Monitor-2.png "事件日志设置")</span><span class="sxs-lookup"><span data-stu-id="a68b2-134">![Event log settings](../../media/Deploy-Azure-Monitor-2.png "Event log settings")</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a68b2-135">配置 Windows 事件日志设置并输入**Skype 会议室系统**作为事件日志名称，然后选中的**错误**、**警告**和**信息**复选框。</span><span class="sxs-lookup"><span data-stu-id="a68b2-135">Configure Windows Event Log settings and enter **Skype Room System** as event log name, and then select the **Error**, **Warning**, and **Information** check boxes.</span></span>

## <a name="configure-test-devices-for-azure-monitoring"></a><span data-ttu-id="a68b2-136">为 Azure 监控配置测试设备</span><span class="sxs-lookup"><span data-stu-id="a68b2-136">Configure test devices for Azure Monitoring</span></span>
<span data-ttu-id="a68b2-137"><a name="configure_test_devices"> </a></span><span class="sxs-lookup"><span data-stu-id="a68b2-137"></span></span>

<span data-ttu-id="a68b2-138">您需要准备日志分析能够监视 Skype 会议室系统 v2 相关的事件。</span><span class="sxs-lookup"><span data-stu-id="a68b2-138">You need to prepare Log Analytics to be able to monitor Skype Room Systems v2–related events.</span></span> <span data-ttu-id="a68b2-139">启动时，您需要将 Microsoft 监控代理部署到您可以物理访问的只是一个或两个 Skype 会议室系统 v2 设备并实现这些测试设备生成一些数据，并将其推送到日志分析工作区。</span><span class="sxs-lookup"><span data-stu-id="a68b2-139">To start with, you need to deploy Microsoft Monitoring agents to just one or two Skype Room Systems v2 devices that you have physical access to, and get those test devices generate some data and push it to the Log Analytics workspace.</span></span>

### <a name="install-microsoft-monitoring-agents-to-test-devices"></a><span data-ttu-id="a68b2-140">安装 Microsoft 监控代理到测试设备</span><span class="sxs-lookup"><span data-stu-id="a68b2-140">Install Microsoft Monitoring agents to test devices</span></span>

<span data-ttu-id="a68b2-141">使用[到 Azure 中的日志分析服务的连接的 Windows 计算机](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows)中提供的说明，将 Microsoft 监控代理部署到测试设备上。</span><span class="sxs-lookup"><span data-stu-id="a68b2-141">Deploy the Microsoft Monitoring agent to the test devices by using the instructions provided in [Connect Windows computers to the Log Analytics service in Azure](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows).</span></span> <span data-ttu-id="a68b2-142">本文提供有关部署监控代理的 Windows 的步骤的详细的信息，获取日志分析***工作区 ID***和***主关键字***的说明，以获取 Skype 会议室系统 v2 设备连接到您的 Azure 监视部署和步骤验证代理连接到日志分析实例。</span><span class="sxs-lookup"><span data-stu-id="a68b2-142">This article provides detailed information about the steps for deploying Microsoft Monitoring Agent for Windows, instructions for obtaining the Log Analytics ***Workspace ID*** and the ***primary key*** to get Skype Room Systems v2 devices connected to your Azure Monitor deployment, and steps to verify agent connectivity to Log Analytics instance.</span></span>

### <a name="generate-sample-skype-room-systems-events"></a><span data-ttu-id="a68b2-143">生成示例 Skype 会议室系统事件</span><span class="sxs-lookup"><span data-stu-id="a68b2-143">Generate sample Skype Room Systems events</span></span>

<span data-ttu-id="a68b2-144">Microsoft 监控代理部署到测试设备后，验证 Azure 监视器，收集所需的事件日志数据。</span><span class="sxs-lookup"><span data-stu-id="a68b2-144">After the Microsoft Monitoring agent is deployed onto the test devices, verify that the required event log data is collected by Azure Monitor.</span></span>

> [!NOTE]
> <span data-ttu-id="a68b2-145">Microsoft 监控代理，在安装后重新启动设备，并确保该 Skype 会议室系统 v2 会议应用程序已启动，以便它可以到事件日志中生成的新事件。</span><span class="sxs-lookup"><span data-stu-id="a68b2-145">Reboot the device after the installation of the Microsoft Monitoring agent, and make sure that Skype Room Systems v2 Meeting app is started, so that it can generate new events into the Event Log.</span></span>

1.  <span data-ttu-id="a68b2-146">登录到[Microsoft Azure 门户](https://portal.azure.com)，转到日志分析，并选择您的工作区。</span><span class="sxs-lookup"><span data-stu-id="a68b2-146">Sign in to the [Microsoft Azure portal](https://portal.azure.com) and go to Log Analytics and select your workspace.</span></span>

2.  <span data-ttu-id="a68b2-147">列出检测信号事件生成的 Skype 会议室系统 v2 设备：</span><span class="sxs-lookup"><span data-stu-id="a68b2-147">List the heartbeat events generated by a Skype Room Systems v2 device:</span></span>
    1.  <span data-ttu-id="a68b2-148">选择您的工作区并转到**日志**使用查询来检索检测信号记录将具有 SR v2 的自定义字段。</span><span class="sxs-lookup"><span data-stu-id="a68b2-148">Select your workspace and go to **Logs** and use a query to retrieve the heartbeat records that will have the custom fields for SRS v2.</span></span>
    2.  <span data-ttu-id="a68b2-149">示例查询：`Event | where Source == "SRS-App" and EventID == 2000`</span><span class="sxs-lookup"><span data-stu-id="a68b2-149">Sample query: `Event | where Source == "SRS-App" and EventID == 2000`</span></span>

3.  <span data-ttu-id="a68b2-150">确保查询返回包含生成的 Skype 会议室系统 v2 会议应用程序事件日志记录。</span><span class="sxs-lookup"><span data-stu-id="a68b2-150">Make sure that the query returns log records that include events generated by the Skype Room Systems v2 meetings app.</span></span>

4.  <span data-ttu-id="a68b2-151">生成硬件问题，并验证 Azure 日志分析中的记录所需的事件。</span><span class="sxs-lookup"><span data-stu-id="a68b2-151">Generate a hardware issue, and validate that the required events are logged in Azure Log Analytics.</span></span>
    1.  <span data-ttu-id="a68b2-152">拔下测试 Skype 会议室系统 v2 系统上的外围设备之一。</span><span class="sxs-lookup"><span data-stu-id="a68b2-152">Unplug one of the peripheral devices on the test Skype Room Systems v2 system.</span></span> <span data-ttu-id="a68b2-153">这可能是照相机、 免提电话、 麦克风或前端聊天室显示</span><span class="sxs-lookup"><span data-stu-id="a68b2-153">This could be the camera, speakerphone, microphone, or Front Room Display</span></span>
    2.  <span data-ttu-id="a68b2-154">等待事件日志中 Azure 日志分析填充 10 分钟。</span><span class="sxs-lookup"><span data-stu-id="a68b2-154">Wait 10 minutes for the event log to be populated in Azure Log Analytics.</span></span>
    3.  <span data-ttu-id="a68b2-155">使用列表硬件错误事件查询：`Event | where Source == "SRS-App" and EventID == 3001`</span><span class="sxs-lookup"><span data-stu-id="a68b2-155">Use a query to list hardware error events: `Event | where Source == "SRS-App" and EventID == 3001`</span></span>

5.  <span data-ttu-id="a68b2-156">生成应用程序问题，并验证的记录所需的事件。</span><span class="sxs-lookup"><span data-stu-id="a68b2-156">Generate an application issue, and validate that the required events are logged.</span></span>
    1.  <span data-ttu-id="a68b2-157">修改 Skype 会议室系统 v2 应用程序配置，并键入正确的会话初始协议 (SIP) 地址中的密码对。</span><span class="sxs-lookup"><span data-stu-id="a68b2-157">Modify Skype Room Systems v2 application configuration, and type an incorrect Session Initiation Protocol (SIP) address/password pair.</span></span>
    2.  <span data-ttu-id="a68b2-158">等待事件日志中 Azure 日志分析填充 10 分钟。</span><span class="sxs-lookup"><span data-stu-id="a68b2-158">Wait 10 minutes for the event log to be populated in Azure Log Analytics.</span></span>
    3.  <span data-ttu-id="a68b2-159">使用查询的列表应用程序错误事件：`Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`</span><span class="sxs-lookup"><span data-stu-id="a68b2-159">Use a query to list application error events: `Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a68b2-160">这些示例事件日志是必需的然后才能配置自定义字段。</span><span class="sxs-lookup"><span data-stu-id="a68b2-160">These sample event logs are required before custom fields can be configured.</span></span> <span data-ttu-id="a68b2-161">不继续下一步，直到您已收集所需的事件日志。</span><span class="sxs-lookup"><span data-stu-id="a68b2-161">Don’t proceed to the next step until you have collected the required event logs.</span></span>

## <a name="map-custom-fields"></a><span data-ttu-id="a68b2-162">映射自定义字段</span><span class="sxs-lookup"><span data-stu-id="a68b2-162">Map custom fields</span></span>
<span data-ttu-id="a68b2-163"><a name="Custom_fields"> </a></span><span class="sxs-lookup"><span data-stu-id="a68b2-163"></span></span>

<span data-ttu-id="a68b2-164">使用自定义域从事件日志中提取特定的数据。</span><span class="sxs-lookup"><span data-stu-id="a68b2-164">You use custom fields to extract specific data from the event logs.</span></span> <span data-ttu-id="a68b2-165">您需要定义将与您的图块数为单位、 仪表板视图和通知更高版本使用的自定义字段。</span><span class="sxs-lookup"><span data-stu-id="a68b2-165">You need to define custom fields that will be used later with your tiles, dashboard views, and alerts.</span></span> <span data-ttu-id="a68b2-166">请参阅[日志分析中的自定义域](https://docs.microsoft.com/azure/azure-monitor/platform/custom-fields)和熟悉概念开始创建自定义域之前。</span><span class="sxs-lookup"><span data-stu-id="a68b2-166">See [Custom fields in Log Analytics](https://docs.microsoft.com/azure/azure-monitor/platform/custom-fields) and become familiar with the concepts before you start creating your custom fields.</span></span>

<span data-ttu-id="a68b2-167">提取自定义域超出捕获的事件日志，请按照下列步骤：</span><span class="sxs-lookup"><span data-stu-id="a68b2-167">To extract your custom fields out of the captured event logs, follow these steps:</span></span>

1.  <span data-ttu-id="a68b2-168">登录到[Microsoft Azure 门户](https://portal.azure.com)，转到日志分析，并选择您的工作区。</span><span class="sxs-lookup"><span data-stu-id="a68b2-168">Sign in to the [Microsoft Azure portal](https://portal.azure.com) and go to Log Analytics and select your workspace.</span></span>

2. <span data-ttu-id="a68b2-169">列出由 Skype 会议室系统 v2 设备生成的事件：</span><span class="sxs-lookup"><span data-stu-id="a68b2-169">List the events generated by a Skype Room Systems v2 device:</span></span>
   1.  <span data-ttu-id="a68b2-170">转到**日志 （经典）** ，并使用查询来检索将具有自定义字段的记录。</span><span class="sxs-lookup"><span data-stu-id="a68b2-170">Go to **Logs (classic)** and use a query to retrieve the records that will have the custom field.</span></span>
   2.  <span data-ttu-id="a68b2-171">示例查询：`Event | where Source == "SRS-App" and EventID == 2000`</span><span class="sxs-lookup"><span data-stu-id="a68b2-171">Sample query: `Event | where Source == "SRS-App" and EventID == 2000`</span></span>

3. <span data-ttu-id="a68b2-172">选择记录之一，选择向左，按钮并启动字段提取向导。</span><span class="sxs-lookup"><span data-stu-id="a68b2-172">Select one of the records, select the button to the left, and start the field extraction wizard.</span></span>

   <span data-ttu-id="a68b2-173">![字段提取向导](../../media/Deploy-Azure-Monitor-3.png "字段提取向导")</span><span class="sxs-lookup"><span data-stu-id="a68b2-173">![Field extraction wizard](../../media/Deploy-Azure-Monitor-3.png "Field extraction wizard")</span></span>

4. <span data-ttu-id="a68b2-174">突出显示您希望从 RenderedDescription 提取并提供字段标题的数据。</span><span class="sxs-lookup"><span data-stu-id="a68b2-174">Highlight the data you’d like to extract from the RenderedDescription and provide a Field Title.</span></span> <span data-ttu-id="a68b2-175">表 1 中提供了应使用的字段名称。</span><span class="sxs-lookup"><span data-stu-id="a68b2-175">The field names that you should use are provided in Table 1.</span></span>

   <span data-ttu-id="a68b2-176">![自定义字段定义](../../media/Deploy-Azure-Monitor-4.png "自定义字段定义")</span><span class="sxs-lookup"><span data-stu-id="a68b2-176">![Custom field definition](../../media/Deploy-Azure-Monitor-4.png "Custom field definition")</span></span>

5. <span data-ttu-id="a68b2-177">使用*表 1*中显示的映射。</span><span class="sxs-lookup"><span data-stu-id="a68b2-177">Use the mappings shown in *Table 1*.</span></span> <span data-ttu-id="a68b2-178">将自动追加日志分析**\_CF**时定义的新字段的字符串。</span><span class="sxs-lookup"><span data-stu-id="a68b2-178">Log Analytics will automatically append the **\_CF** string when you define the new field.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a68b2-179">请记住 JSON 和日志分析的所有字段，都都区分大小写。</span><span class="sxs-lookup"><span data-stu-id="a68b2-179">Remember that all JSON and Log Analytics fields are case-sensitive.</span></span>
> 
> <span data-ttu-id="a68b2-180">请注意下表列出了每个自定义字段所需的查询。</span><span class="sxs-lookup"><span data-stu-id="a68b2-180">Pay attention to the queries required for each custom field in the table below.</span></span> <span data-ttu-id="a68b2-181">您需要使用日志分析的正确的查询成功提取自定义字段值。</span><span class="sxs-lookup"><span data-stu-id="a68b2-181">You need to use the correct queries for Log Analytics to successfully extract custom field values.</span></span>
> 
 <span data-ttu-id="a68b2-182">![自定义字段定义](../../media/Deploy-Azure-Monitor-5.png "自定义字段定义")</span><span class="sxs-lookup"><span data-stu-id="a68b2-182">![Custom field definition](../../media/Deploy-Azure-Monitor-5.png "Custom field definition")</span></span>

<span data-ttu-id="a68b2-183">表 1.</span><span class="sxs-lookup"><span data-stu-id="a68b2-183">**Table 1**</span></span>

| <span data-ttu-id="a68b2-184">JSON 字段</span><span class="sxs-lookup"><span data-stu-id="a68b2-184">**JSON field**</span></span>                   | <span data-ttu-id="a68b2-185">**日志分析自定义字段**</span><span class="sxs-lookup"><span data-stu-id="a68b2-185">**Log Analytics custom field**</span></span> | <span data-ttu-id="a68b2-186">事件 ID</span><span class="sxs-lookup"><span data-stu-id="a68b2-186">**Event ID**</span></span> | <span data-ttu-id="a68b2-187">**用于提取的查询**</span><span class="sxs-lookup"><span data-stu-id="a68b2-187">**Query to use with the extraction**</span></span>                   |
|:---------------------------------|:-------------------------------|:-------------|:-------------------------------------------------------|
| <span data-ttu-id="a68b2-188">说明</span><span class="sxs-lookup"><span data-stu-id="a68b2-188">Description</span></span>                      | <span data-ttu-id="a68b2-189">SRSEventDescription</span><span class="sxs-lookup"><span data-stu-id="a68b2-189">SRSEventDescription</span></span>         | <span data-ttu-id="a68b2-190">$2,000</span><span class="sxs-lookup"><span data-stu-id="a68b2-190">**2000**</span></span>     | <span data-ttu-id="a68b2-191">事件\|其中源 = ="SR 应用程序"和 EventID = = 2000年</span><span class="sxs-lookup"><span data-stu-id="a68b2-191">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="a68b2-192">ResourceState</span><span class="sxs-lookup"><span data-stu-id="a68b2-192">ResourceState</span></span>                    | <span data-ttu-id="a68b2-193">SRSResourceState</span><span class="sxs-lookup"><span data-stu-id="a68b2-193">SRSResourceState</span></span>            | <span data-ttu-id="a68b2-194">$2,000</span><span class="sxs-lookup"><span data-stu-id="a68b2-194">**2000**</span></span>     | <span data-ttu-id="a68b2-195">事件\|其中源 = ="SR 应用程序"和 EventID = = 2000年</span><span class="sxs-lookup"><span data-stu-id="a68b2-195">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="a68b2-196">OperationName</span><span class="sxs-lookup"><span data-stu-id="a68b2-196">OperationName</span></span>                    | <span data-ttu-id="a68b2-197">SRSOperationName</span><span class="sxs-lookup"><span data-stu-id="a68b2-197">SRSOperationName</span></span>            | <span data-ttu-id="a68b2-198">$2,000</span><span class="sxs-lookup"><span data-stu-id="a68b2-198">**2000**</span></span>     | <span data-ttu-id="a68b2-199">事件\|其中源 = ="SR 应用程序"和 EventID = = 2000年</span><span class="sxs-lookup"><span data-stu-id="a68b2-199">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="a68b2-200">OperationResult</span><span class="sxs-lookup"><span data-stu-id="a68b2-200">OperationResult</span></span>                  | <span data-ttu-id="a68b2-201">SRSOperationResult</span><span class="sxs-lookup"><span data-stu-id="a68b2-201">SRSOperationResult</span></span>          | <span data-ttu-id="a68b2-202">$2,000</span><span class="sxs-lookup"><span data-stu-id="a68b2-202">**2000**</span></span>     | <span data-ttu-id="a68b2-203">事件\|其中源 = ="SR 应用程序"和 EventID = = 2000年</span><span class="sxs-lookup"><span data-stu-id="a68b2-203">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="a68b2-204">OS</span><span class="sxs-lookup"><span data-stu-id="a68b2-204">OS</span></span>                               | <span data-ttu-id="a68b2-205">SRSOSVersion</span><span class="sxs-lookup"><span data-stu-id="a68b2-205">SRSOSVersion</span></span>                | <span data-ttu-id="a68b2-206">$2,000</span><span class="sxs-lookup"><span data-stu-id="a68b2-206">**2000**</span></span>     | <span data-ttu-id="a68b2-207">事件\|其中源 = ="SR 应用程序"和 EventID = = 2000年</span><span class="sxs-lookup"><span data-stu-id="a68b2-207">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="a68b2-208">OSVersion</span><span class="sxs-lookup"><span data-stu-id="a68b2-208">OSVersion</span></span>                        | <span data-ttu-id="a68b2-209">SRSOSLongVersion</span><span class="sxs-lookup"><span data-stu-id="a68b2-209">SRSOSLongVersion</span></span>            | <span data-ttu-id="a68b2-210">$2,000</span><span class="sxs-lookup"><span data-stu-id="a68b2-210">**2000**</span></span>     | <span data-ttu-id="a68b2-211">事件\|其中源 = ="SR 应用程序"和 EventID = = 2000年</span><span class="sxs-lookup"><span data-stu-id="a68b2-211">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="a68b2-212">别名</span><span class="sxs-lookup"><span data-stu-id="a68b2-212">Alias</span></span>                            | <span data-ttu-id="a68b2-213">SRSAlias</span><span class="sxs-lookup"><span data-stu-id="a68b2-213">SRSAlias</span></span>                    | <span data-ttu-id="a68b2-214">$2,000</span><span class="sxs-lookup"><span data-stu-id="a68b2-214">**2000**</span></span>     | <span data-ttu-id="a68b2-215">事件\|其中源 = ="SR 应用程序"和 EventID = = 2000年</span><span class="sxs-lookup"><span data-stu-id="a68b2-215">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="a68b2-216">DisplayName</span><span class="sxs-lookup"><span data-stu-id="a68b2-216">DisplayName</span></span>                      | <span data-ttu-id="a68b2-217">SRSDisplayName</span><span class="sxs-lookup"><span data-stu-id="a68b2-217">SRSDisplayName</span></span>              | <span data-ttu-id="a68b2-218">$2,000</span><span class="sxs-lookup"><span data-stu-id="a68b2-218">**2000**</span></span>     | <span data-ttu-id="a68b2-219">事件\|其中源 = ="SR 应用程序"和 EventID = = 2000年</span><span class="sxs-lookup"><span data-stu-id="a68b2-219">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="a68b2-220">AppVersion</span><span class="sxs-lookup"><span data-stu-id="a68b2-220">AppVersion</span></span>                       | <span data-ttu-id="a68b2-221">SRSAppVersion</span><span class="sxs-lookup"><span data-stu-id="a68b2-221">SRSAppVersion</span></span>               | <span data-ttu-id="a68b2-222">$2,000</span><span class="sxs-lookup"><span data-stu-id="a68b2-222">**2000**</span></span>     | <span data-ttu-id="a68b2-223">事件\|其中源 = ="SR 应用程序"和 EventID = = 2000年</span><span class="sxs-lookup"><span data-stu-id="a68b2-223">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="a68b2-224">IPv4Address</span><span class="sxs-lookup"><span data-stu-id="a68b2-224">IPv4Address</span></span>                      | <span data-ttu-id="a68b2-225">SRSIPv4Address</span><span class="sxs-lookup"><span data-stu-id="a68b2-225">SRSIPv4Address</span></span>              | <span data-ttu-id="a68b2-226">$2,000</span><span class="sxs-lookup"><span data-stu-id="a68b2-226">**2000**</span></span>     | <span data-ttu-id="a68b2-227">事件\|其中源 = ="SR 应用程序"和 EventID = = 2000年</span><span class="sxs-lookup"><span data-stu-id="a68b2-227">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="a68b2-228">IPv6Address</span><span class="sxs-lookup"><span data-stu-id="a68b2-228">IPv6Address</span></span>                      | <span data-ttu-id="a68b2-229">SRSIPv6Address</span><span class="sxs-lookup"><span data-stu-id="a68b2-229">SRSIPv6Address</span></span>              | <span data-ttu-id="a68b2-230">$2,000</span><span class="sxs-lookup"><span data-stu-id="a68b2-230">**2000**</span></span>     | <span data-ttu-id="a68b2-231">事件\|其中源 = ="SR 应用程序"和 EventID = = 2000年</span><span class="sxs-lookup"><span data-stu-id="a68b2-231">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="a68b2-232">会议麦克风状态</span><span class="sxs-lookup"><span data-stu-id="a68b2-232">Conference Microphone status</span></span>     | <span data-ttu-id="a68b2-233">SRSConfMicrophoneStatus</span><span class="sxs-lookup"><span data-stu-id="a68b2-233">SRSConfMicrophoneStatus</span></span>     | <span data-ttu-id="a68b2-234">**3001**</span><span class="sxs-lookup"><span data-stu-id="a68b2-234">**3001**</span></span>     | <span data-ttu-id="a68b2-235">事件\|其中源 = ="SR 应用程序"和 EventID = = 3001</span><span class="sxs-lookup"><span data-stu-id="a68b2-235">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="a68b2-236">会议扬声器状态</span><span class="sxs-lookup"><span data-stu-id="a68b2-236">Conference Speaker status</span></span>        | <span data-ttu-id="a68b2-237">SRSConfSpeakerStatus</span><span class="sxs-lookup"><span data-stu-id="a68b2-237">SRSConfSpeakerStatus</span></span>        | <span data-ttu-id="a68b2-238">**3001**</span><span class="sxs-lookup"><span data-stu-id="a68b2-238">**3001**</span></span>     | <span data-ttu-id="a68b2-239">事件\|其中源 = ="SR 应用程序"和 EventID = = 3001</span><span class="sxs-lookup"><span data-stu-id="a68b2-239">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="a68b2-240">默认扬声器状态</span><span class="sxs-lookup"><span data-stu-id="a68b2-240">Default Speaker status</span></span>           | <span data-ttu-id="a68b2-241">SRSDefaultSpeakerStatus</span><span class="sxs-lookup"><span data-stu-id="a68b2-241">SRSDefaultSpeakerStatus</span></span>     | <span data-ttu-id="a68b2-242">**3001**</span><span class="sxs-lookup"><span data-stu-id="a68b2-242">**3001**</span></span>     | <span data-ttu-id="a68b2-243">事件\|其中源 = ="SR 应用程序"和 EventID = = 3001</span><span class="sxs-lookup"><span data-stu-id="a68b2-243">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="a68b2-244">摄像机状态</span><span class="sxs-lookup"><span data-stu-id="a68b2-244">Camera status</span></span>                    | <span data-ttu-id="a68b2-245">SRSCameraStatus</span><span class="sxs-lookup"><span data-stu-id="a68b2-245">SRSCameraStatus</span></span>             | <span data-ttu-id="a68b2-246">**3001**</span><span class="sxs-lookup"><span data-stu-id="a68b2-246">**3001**</span></span>     | <span data-ttu-id="a68b2-247">事件\|其中源 = ="SR 应用程序"和 EventID = = 3001</span><span class="sxs-lookup"><span data-stu-id="a68b2-247">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="a68b2-248">前面的聊天室显示状态</span><span class="sxs-lookup"><span data-stu-id="a68b2-248">Front of Room Display status</span></span>     | <span data-ttu-id="a68b2-249">SRSFORDStatus</span><span class="sxs-lookup"><span data-stu-id="a68b2-249">SRSFORDStatus</span></span>               | <span data-ttu-id="a68b2-250">**3001**</span><span class="sxs-lookup"><span data-stu-id="a68b2-250">**3001**</span></span>     | <span data-ttu-id="a68b2-251">事件\|其中源 = ="SR 应用程序"和 EventID = = 3001</span><span class="sxs-lookup"><span data-stu-id="a68b2-251">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="a68b2-252">运动传感器状态</span><span class="sxs-lookup"><span data-stu-id="a68b2-252">Motion Sensor status</span></span>             | <span data-ttu-id="a68b2-253">SRSMotionSensorStatus</span><span class="sxs-lookup"><span data-stu-id="a68b2-253">SRSMotionSensorStatus</span></span>       | <span data-ttu-id="a68b2-254">**3001**</span><span class="sxs-lookup"><span data-stu-id="a68b2-254">**3001**</span></span>     | <span data-ttu-id="a68b2-255">事件\|其中源 = ="SR 应用程序"和 EventID = = 3001</span><span class="sxs-lookup"><span data-stu-id="a68b2-255">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="a68b2-256">HDMI 引入状态</span><span class="sxs-lookup"><span data-stu-id="a68b2-256">HDMI Ingest status</span></span>               | <span data-ttu-id="a68b2-257">SRSHDMIIngestStatus</span><span class="sxs-lookup"><span data-stu-id="a68b2-257">SRSHDMIIngestStatus</span></span>         | <span data-ttu-id="a68b2-258">**3001**</span><span class="sxs-lookup"><span data-stu-id="a68b2-258">**3001**</span></span>     | <span data-ttu-id="a68b2-259">事件\|其中源 = ="SR 应用程序"和 EventID = = 3001</span><span class="sxs-lookup"><span data-stu-id="a68b2-259">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |


## <a name="define-the-skype-room-systems-v2-views-in-log-analytics"></a><span data-ttu-id="a68b2-260">日志分析中定义的 Skype 会议室系统 v2 视图</span><span class="sxs-lookup"><span data-stu-id="a68b2-260">Define the Skype Room Systems v2 views in Log Analytics</span></span>
<span data-ttu-id="a68b2-261"><a name="Define_Views"> </a></span><span class="sxs-lookup"><span data-stu-id="a68b2-261"></span></span>

<span data-ttu-id="a68b2-262">收集数据并自定义字段映射后，您可以使用视图设计器开发包含各种平铺监视 Skype 会议室系统 v2 事件仪表板。</span><span class="sxs-lookup"><span data-stu-id="a68b2-262">After data is collected and custom fields are mapped, you can use View Designer to develop a dashboard containing various tiles to monitor Skype Room Systems v2 events.</span></span> <span data-ttu-id="a68b2-263">使用视图设计器创建以下图块。</span><span class="sxs-lookup"><span data-stu-id="a68b2-263">Use View Designer to create the following tiles.</span></span> <span data-ttu-id="a68b2-264">有关详细信息，请参阅[创建使用日志分析中的视图设计器的自定义视图](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer)</span><span class="sxs-lookup"><span data-stu-id="a68b2-264">For more information, see [Create custom views by using View Designer in Log Analytics](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer)</span></span>

> [!NOTE]
> <span data-ttu-id="a68b2-265">应可以正常运行仪表板图块完成本指南中的上一步骤。</span><span class="sxs-lookup"><span data-stu-id="a68b2-265">Previous steps in this guide should have been completed for the dashboard tiles to work properly.</span></span>

### <a name="create-a-skype-room-systems-v2-dashboard-by-using-the-import-method"></a><span data-ttu-id="a68b2-266">使用的导入方法创建 Skype 会议室系统 v2 仪表板</span><span class="sxs-lookup"><span data-stu-id="a68b2-266">Create a Skype Room Systems v2 dashboard by using the import method</span></span>

<span data-ttu-id="a68b2-267">可以导入的 Skype 会议室系统 v2 仪表板并开始快速监视您的设备。</span><span class="sxs-lookup"><span data-stu-id="a68b2-267">You can import an Skype Room Systems v2 dashboard and start monitoring your devices quickly.</span></span> <span data-ttu-id="a68b2-268">执行以下步骤以导入仪表板：</span><span class="sxs-lookup"><span data-stu-id="a68b2-268">Take the following steps to import the dashboard:</span></span>

1.  <span data-ttu-id="a68b2-269">获取[SkypeRoomSystems_v2.omsview](https://go.microsoft.com/fwlink/?linkid=835675)仪表板文件。</span><span class="sxs-lookup"><span data-stu-id="a68b2-269">Get the [SkypeRoomSystems_v2.omsview](https://go.microsoft.com/fwlink/?linkid=835675) dashboard file.</span></span>
2.  <span data-ttu-id="a68b2-270">登录到[Microsoft Azure 门户](https://portal.azure.com)，转到日志分析，并选择您的工作区。</span><span class="sxs-lookup"><span data-stu-id="a68b2-270">Sign in to the [Microsoft Azure portal](https://portal.azure.com) and go to Log Analytics and select your workspace.</span></span>
3.  <span data-ttu-id="a68b2-271">打开**视图设计器**。</span><span class="sxs-lookup"><span data-stu-id="a68b2-271">Open **View Designer**.</span></span>
4.  <span data-ttu-id="a68b2-272">选择**导入**，，然后选择**SkypeRoomSystems_v2.omsview**文件。</span><span class="sxs-lookup"><span data-stu-id="a68b2-272">Select **Import**, and then select the **SkypeRoomSystems_v2.omsview** file.</span></span>
5.  <span data-ttu-id="a68b2-273">选择**保存**。</span><span class="sxs-lookup"><span data-stu-id="a68b2-273">Select **Save**.</span></span>

### <a name="create-a-skype-room-systems-v2-dashboard-manually"></a><span data-ttu-id="a68b2-274">手动创建 Skype 会议室系统 v2 仪表板</span><span class="sxs-lookup"><span data-stu-id="a68b2-274">Create a Skype Room Systems v2 dashboard manually</span></span>

<span data-ttu-id="a68b2-275">此外，您可以创建自己的仪表板并添加您想要监视的图块。</span><span class="sxs-lookup"><span data-stu-id="a68b2-275">Alternatively, you can create your own dashboard and add only the tiles that you wish to monitor.</span></span>

#### <a name="configure-the-overview-tile"></a><span data-ttu-id="a68b2-276">配置概述图块</span><span class="sxs-lookup"><span data-stu-id="a68b2-276">Configure the Overview Tile</span></span>

1.  <span data-ttu-id="a68b2-277">打开**视图设计器**。</span><span class="sxs-lookup"><span data-stu-id="a68b2-277">Open **View Designer**.</span></span>
2.  <span data-ttu-id="a68b2-278">选择**概述图块**，并从库选择**两个数字**。</span><span class="sxs-lookup"><span data-stu-id="a68b2-278">Select **Overview Tile**, and then select **Two numbers** from the gallery.</span></span>
3.  <span data-ttu-id="a68b2-279">名称平铺**Skype 会议室系统 v2**。</span><span class="sxs-lookup"><span data-stu-id="a68b2-279">Name the tile **Skype Room Systems v2**.</span></span>
4.  <span data-ttu-id="a68b2-280">定义**第一个图块**：</span><span class="sxs-lookup"><span data-stu-id="a68b2-280">Define the **First Tile**:</span></span><br>
    <span data-ttu-id="a68b2-281">**图例：** 至少执行一次在上个月内发送检测信号的设备</span><span class="sxs-lookup"><span data-stu-id="a68b2-281">**Legend:** Devices that sent a heartbeat at least once within the last month</span></span><br>
    <span data-ttu-id="a68b2-282">**查询：**```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```</span><span class="sxs-lookup"><span data-stu-id="a68b2-282">**Query:** ```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```</span></span>
5.  <span data-ttu-id="a68b2-283">定义**第二个图块**：</span><span class="sxs-lookup"><span data-stu-id="a68b2-283">Define the **Second Tile**:</span></span><br>
    <span data-ttu-id="a68b2-284">**图例：** 发送检测信号的最后一个小时内的活动设备</span><span class="sxs-lookup"><span data-stu-id="a68b2-284">**Legend:** Active devices that sent a heartbeat within the last hour</span></span><br>
    <span data-ttu-id="a68b2-285">**查询：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```</span><span class="sxs-lookup"><span data-stu-id="a68b2-285">**Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```</span></span>
6.  <span data-ttu-id="a68b2-286">选择**应用**。</span><span class="sxs-lookup"><span data-stu-id="a68b2-286">Select **Apply**.</span></span>

### <a name="create-a-tile-that-displays-active-devices"></a><span data-ttu-id="a68b2-287">创建活动设备将显示一个图块</span><span class="sxs-lookup"><span data-stu-id="a68b2-287">Create a tile that displays active devices</span></span>

1.  <span data-ttu-id="a68b2-288">选择**视图仪表板**开始添加您的图块数为单位。</span><span class="sxs-lookup"><span data-stu-id="a68b2-288">Select **View Dashboard** to start adding your tiles.</span></span>
2.  <span data-ttu-id="a68b2-289">从库中选择**数字 & 列表**</span><span class="sxs-lookup"><span data-stu-id="a68b2-289">Select **Number & list** from the gallery</span></span>
3.  <span data-ttu-id="a68b2-290">定义**常规**属性：</span><span class="sxs-lookup"><span data-stu-id="a68b2-290">Define the **General** properties:</span></span><br>
    <span data-ttu-id="a68b2-291">**组标题：** 检测信号状态</span><span class="sxs-lookup"><span data-stu-id="a68b2-291">**Group Title:** Heartbeat Status</span></span><br>
    <span data-ttu-id="a68b2-292">**新组：** 选择</span><span class="sxs-lookup"><span data-stu-id="a68b2-292">**New Group:** Selected</span></span>
4.  <span data-ttu-id="a68b2-293">定义**平铺**属性：</span><span class="sxs-lookup"><span data-stu-id="a68b2-293">Define the **Tile** properties:</span></span><br>
    <span data-ttu-id="a68b2-294">**图例：** 活动设备 （检测信号发送前 20 分钟内）</span><span class="sxs-lookup"><span data-stu-id="a68b2-294">**Legend:** Active devices (heartbeat sent in the last 20 minutes)</span></span><br>
    <span data-ttu-id="a68b2-295">图块查询：</span><span class="sxs-lookup"><span data-stu-id="a68b2-295">**Tile Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```</span></span>
5.  <span data-ttu-id="a68b2-296">定义**列表**的属性：</span><span class="sxs-lookup"><span data-stu-id="a68b2-296">Define the **List** properties:</span></span><br>
    <span data-ttu-id="a68b2-297">列表查询：</span><span class="sxs-lookup"><span data-stu-id="a68b2-297">**List Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span></span>
6.  <span data-ttu-id="a68b2-298">定义**列标题**：</span><span class="sxs-lookup"><span data-stu-id="a68b2-298">Define **Column Titles**:</span></span><br>
    <span data-ttu-id="a68b2-299">**名称：** 计算机名称</span><span class="sxs-lookup"><span data-stu-id="a68b2-299">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="a68b2-300">**值：** 最后一个检测信号</span><span class="sxs-lookup"><span data-stu-id="a68b2-300">**Value:** Last Heartbeat</span></span>
7.  <span data-ttu-id="a68b2-301">定义**导航查询**。</span><span class="sxs-lookup"><span data-stu-id="a68b2-301">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  <span data-ttu-id="a68b2-302">选择**应用**，然后**关闭**。</span><span class="sxs-lookup"><span data-stu-id="a68b2-302">Select **Apply**, and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-devices-that-have-connectivity-issues"></a><span data-ttu-id="a68b2-303">创建具有连接问题的设备将显示一个图块</span><span class="sxs-lookup"><span data-stu-id="a68b2-303">Create a tile that displays devices that have connectivity issues</span></span>

1.  <span data-ttu-id="a68b2-304">从库中，选择**号码 & 列表**，然后添加新的平铺。</span><span class="sxs-lookup"><span data-stu-id="a68b2-304">Select **Number & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="a68b2-305">定义**常规**属性：</span><span class="sxs-lookup"><span data-stu-id="a68b2-305">Define the **General** properties:</span></span><br>
    <span data-ttu-id="a68b2-306">**组标题：** 将保留为空</span><span class="sxs-lookup"><span data-stu-id="a68b2-306">**Group Title:** Leave empty</span></span><br>
    <span data-ttu-id="a68b2-307">**新组：** 未选定</span><span class="sxs-lookup"><span data-stu-id="a68b2-307">**New Group:** Not Selected</span></span>
3.  <span data-ttu-id="a68b2-308">定义**平铺**属性：</span><span class="sxs-lookup"><span data-stu-id="a68b2-308">Define the **Tile** properties:</span></span><br>
    <span data-ttu-id="a68b2-309">**图例：** 非活动设备 （发送前 20 分钟内无检测信号消息）</span><span class="sxs-lookup"><span data-stu-id="a68b2-309">**Legend:** Inactive Devices (no heartbeat message sent in the last 20 minutes)</span></span><br>
    <span data-ttu-id="a68b2-310">图块查询：</span><span class="sxs-lookup"><span data-stu-id="a68b2-310">**Tile Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```</span></span>
4.  <span data-ttu-id="a68b2-311">定义**列表**的属性：</span><span class="sxs-lookup"><span data-stu-id="a68b2-311">Define the **List** properties:</span></span><br>
    <span data-ttu-id="a68b2-312">列表查询：</span><span class="sxs-lookup"><span data-stu-id="a68b2-312">**List Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```</span></span>
5.  <span data-ttu-id="a68b2-313">定义**列标题**：</span><span class="sxs-lookup"><span data-stu-id="a68b2-313">Define **Column Titles**:</span></span><br>
    <span data-ttu-id="a68b2-314">**名称：** 计算机名称</span><span class="sxs-lookup"><span data-stu-id="a68b2-314">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="a68b2-315">**值：** 最后一个检测信号</span><span class="sxs-lookup"><span data-stu-id="a68b2-315">**Value:** Last Heartbeat</span></span>
6.  <span data-ttu-id="a68b2-316">定义**导航查询**：</span><span class="sxs-lookup"><span data-stu-id="a68b2-316">Define **Navigation Query**:</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  <span data-ttu-id="a68b2-317">选择**应用**，然后**关闭**。</span><span class="sxs-lookup"><span data-stu-id="a68b2-317">Select **Apply**, and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-devices-that-have-a-hardware-error"></a><span data-ttu-id="a68b2-318">创建具有硬件错误的设备将显示一个图块</span><span class="sxs-lookup"><span data-stu-id="a68b2-318">Create a tile that displays devices that have a hardware error</span></span>

1.  <span data-ttu-id="a68b2-319">从库中，选择**号码 & 列表**，然后添加新的平铺。</span><span class="sxs-lookup"><span data-stu-id="a68b2-319">Select **Number & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="a68b2-320">定义**常规**属性：</span><span class="sxs-lookup"><span data-stu-id="a68b2-320">Define the **General** properties:</span></span><br>
    <span data-ttu-id="a68b2-321">**组标题：** 硬件状态</span><span class="sxs-lookup"><span data-stu-id="a68b2-321">**Group Title:** Hardware Status</span></span><br>
    <span data-ttu-id="a68b2-322">**新组：** 选择</span><span class="sxs-lookup"><span data-stu-id="a68b2-322">**New Group:** Selected</span></span>
3.  <span data-ttu-id="a68b2-323">定义**平铺**属性：</span><span class="sxs-lookup"><span data-stu-id="a68b2-323">Define the **Tile** properties:</span></span><br>
    <span data-ttu-id="a68b2-324">**图例：** 最后一个小时内遇到硬件错误的设备</span><span class="sxs-lookup"><span data-stu-id="a68b2-324">**Legend:** Devices that experienced a hardware error in the last hour</span></span><br>
    <span data-ttu-id="a68b2-325">图块查询：</span><span class="sxs-lookup"><span data-stu-id="a68b2-325">**Tile Query:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```</span></span>
4.  <span data-ttu-id="a68b2-326">定义**列表**的属性：</span><span class="sxs-lookup"><span data-stu-id="a68b2-326">Define the **List** properties:</span></span><br>
    <span data-ttu-id="a68b2-327">列表查询：</span><span class="sxs-lookup"><span data-stu-id="a68b2-327">**List Query:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span></span>
5.  <span data-ttu-id="a68b2-328">定义**列标题**：</span><span class="sxs-lookup"><span data-stu-id="a68b2-328">Define **Column Titles**:</span></span><br>
    <span data-ttu-id="a68b2-329">**名称：** 计算机名称</span><span class="sxs-lookup"><span data-stu-id="a68b2-329">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="a68b2-330">**值：** 最后一个错误</span><span class="sxs-lookup"><span data-stu-id="a68b2-330">**Value:** Last Error</span></span>
6.  <span data-ttu-id="a68b2-331">定义**导航查询**：</span><span class="sxs-lookup"><span data-stu-id="a68b2-331">Define **Navigation Query**:</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 3001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  <span data-ttu-id="a68b2-332">选择**应用**，然后**关闭**。</span><span class="sxs-lookup"><span data-stu-id="a68b2-332">Select **Apply**, and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-skype-room-systems-v2-operating-system-versions"></a><span data-ttu-id="a68b2-333">创建显示 Skype 会议室系统 v2 操作系统版本拼贴</span><span class="sxs-lookup"><span data-stu-id="a68b2-333">Create a tile that displays Skype Room Systems v2 Operating System versions</span></span>

1.  <span data-ttu-id="a68b2-334">从库中选择**圆环 & 列表**，然后添加新的平铺。</span><span class="sxs-lookup"><span data-stu-id="a68b2-334">Select **Donut & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="a68b2-335">定义**常规**属性：</span><span class="sxs-lookup"><span data-stu-id="a68b2-335">Define the **General** properties:</span></span><br>
    <span data-ttu-id="a68b2-336">**组标题：** 操作系统详细信息</span><span class="sxs-lookup"><span data-stu-id="a68b2-336">**Group Title:** Operating System details</span></span><br>
    <span data-ttu-id="a68b2-337">**新组：** 选择</span><span class="sxs-lookup"><span data-stu-id="a68b2-337">**New Group:** Selected</span></span>
3.  <span data-ttu-id="a68b2-338">定义**标头**属性：</span><span class="sxs-lookup"><span data-stu-id="a68b2-338">Define the **Header** properties:</span></span><br>
    <span data-ttu-id="a68b2-339">**标题：** 操作系统版本</span><span class="sxs-lookup"><span data-stu-id="a68b2-339">**Title:** Operating System versions</span></span><br>
    <span data-ttu-id="a68b2-340">**副标题：** 运行特定操作系统版本的设备</span><span class="sxs-lookup"><span data-stu-id="a68b2-340">**Subtitle:** Devices running specific OS versions</span></span>
4.  <span data-ttu-id="a68b2-341">定义**圆环**属性：</span><span class="sxs-lookup"><span data-stu-id="a68b2-341">Define the **Donut** properties:</span></span><br>
    <span data-ttu-id="a68b2-342">**查询：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize OS_Version = max(SRSOSLongVersion_CF) by Computer | summarize AggregatedValue = count() by OS_Version | sort by OS_Version asc```</span><span class="sxs-lookup"><span data-stu-id="a68b2-342">**Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize OS_Version = max(SRSOSLongVersion_CF) by Computer | summarize AggregatedValue = count() by OS_Version | sort by OS_Version asc```</span></span><br>
    <span data-ttu-id="a68b2-343">**使文本居中：** 设备</span><span class="sxs-lookup"><span data-stu-id="a68b2-343">**Center Text:** Devices</span></span><br>
    <span data-ttu-id="a68b2-344">**操作：** Sum</span><span class="sxs-lookup"><span data-stu-id="a68b2-344">**Operation:** Sum</span></span>
5.  <span data-ttu-id="a68b2-345">定义**列表**的属性。</span><span class="sxs-lookup"><span data-stu-id="a68b2-345">Define the **List** properties.</span></span><br>
    <span data-ttu-id="a68b2-346">列表查询：</span><span class="sxs-lookup"><span data-stu-id="a68b2-346">**List Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSOSLongVersion_CF = max(SRSOSLongVersion_CF) by Computer | sort by Computer asc```</span></span><br>
    <span data-ttu-id="a68b2-347">**隐藏图：** 选择</span><span class="sxs-lookup"><span data-stu-id="a68b2-347">**Hide Graph:** Selected</span></span><br>
    <span data-ttu-id="a68b2-348">**启用迷你图：** 未选定</span><span class="sxs-lookup"><span data-stu-id="a68b2-348">**Enable Sparklines:** Not selected</span></span>
6.  <span data-ttu-id="a68b2-349">定义**列标题**。</span><span class="sxs-lookup"><span data-stu-id="a68b2-349">Define **Column Titles**.</span></span><br>
    <span data-ttu-id="a68b2-350">**名称：** 计算机名称</span><span class="sxs-lookup"><span data-stu-id="a68b2-350">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="a68b2-351">**值：** 将保留为空</span><span class="sxs-lookup"><span data-stu-id="a68b2-351">**Value:** Leave Empty</span></span>
7.  <span data-ttu-id="a68b2-352">定义**导航查询**。</span><span class="sxs-lookup"><span data-stu-id="a68b2-352">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  <span data-ttu-id="a68b2-353">选择**应用**，然后**关闭**。</span><span class="sxs-lookup"><span data-stu-id="a68b2-353">Select **Apply** and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-skype-room-systems-v2-application-versions"></a><span data-ttu-id="a68b2-354">创建显示 Skype 会议室系统 v2 应用程序版本拼贴</span><span class="sxs-lookup"><span data-stu-id="a68b2-354">Create a tile that displays Skype Room Systems v2 application versions</span></span>

1.  <span data-ttu-id="a68b2-355">从库中选择**圆环 & 列表**，然后添加新的平铺。</span><span class="sxs-lookup"><span data-stu-id="a68b2-355">Select **Donut & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="a68b2-356">定义**常规**属性：</span><span class="sxs-lookup"><span data-stu-id="a68b2-356">Define the **General** properties:</span></span><br>
    <span data-ttu-id="a68b2-357">**组标题：** Skype 会议室系统 v2 应用程序的详细信息</span><span class="sxs-lookup"><span data-stu-id="a68b2-357">**Group Title:** Skype Room Systems v2 application details</span></span><br>
    <span data-ttu-id="a68b2-358">**新组：** 选择</span><span class="sxs-lookup"><span data-stu-id="a68b2-358">**New Group:** Selected</span></span>
3.  <span data-ttu-id="a68b2-359">定义**标头**属性：</span><span class="sxs-lookup"><span data-stu-id="a68b2-359">Define the **Header** properties:</span></span><br>
    <span data-ttu-id="a68b2-360">**标题：** 应用程序版本</span><span class="sxs-lookup"><span data-stu-id="a68b2-360">**Title:** Application versions</span></span><br>
    <span data-ttu-id="a68b2-361">**副标题：** 设备运行特定应用程序版本</span><span class="sxs-lookup"><span data-stu-id="a68b2-361">**Subtitle:** Devices running specific application versions</span></span>
4.  <span data-ttu-id="a68b2-362">定义**圆环**属性：</span><span class="sxs-lookup"><span data-stu-id="a68b2-362">Define the **Donut** properties:</span></span><br>
    <span data-ttu-id="a68b2-363">**查询：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```</span><span class="sxs-lookup"><span data-stu-id="a68b2-363">**Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```</span></span><br>
    <span data-ttu-id="a68b2-364">**使文本居中：** 设备</span><span class="sxs-lookup"><span data-stu-id="a68b2-364">**Center Text:** Devices</span></span><br>
    <span data-ttu-id="a68b2-365">**操作：** Sum</span><span class="sxs-lookup"><span data-stu-id="a68b2-365">**Operation:** Sum</span></span>
5.  <span data-ttu-id="a68b2-366">定义**列表**的属性。</span><span class="sxs-lookup"><span data-stu-id="a68b2-366">Define the **List** properties.</span></span><br>
    <span data-ttu-id="a68b2-367">列表查询：</span><span class="sxs-lookup"><span data-stu-id="a68b2-367">**List Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```</span></span><br>
    <span data-ttu-id="a68b2-368">**隐藏图：** 选择</span><span class="sxs-lookup"><span data-stu-id="a68b2-368">**Hide Graph:** Selected</span></span><br>
    <span data-ttu-id="a68b2-369">**启用迷你图：** 未选定</span><span class="sxs-lookup"><span data-stu-id="a68b2-369">**Enable Sparklines:** Not selected</span></span>
6.  <span data-ttu-id="a68b2-370">定义**列标题**。</span><span class="sxs-lookup"><span data-stu-id="a68b2-370">Define **Column Titles**.</span></span><br>
    <span data-ttu-id="a68b2-371">**名称：** 计算机名称</span><span class="sxs-lookup"><span data-stu-id="a68b2-371">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="a68b2-372">**值：** 将保留为空</span><span class="sxs-lookup"><span data-stu-id="a68b2-372">**Value:** Leave Empty</span></span>
7.  <span data-ttu-id="a68b2-373">定义**导航查询**。</span><span class="sxs-lookup"><span data-stu-id="a68b2-373">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  <span data-ttu-id="a68b2-374">选择**应用**，然后**关闭**。</span><span class="sxs-lookup"><span data-stu-id="a68b2-374">Select **Apply** and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-devices-that-have-an-application-error"></a><span data-ttu-id="a68b2-375">创建具有应用程序错误的设备将显示一个图块</span><span class="sxs-lookup"><span data-stu-id="a68b2-375">Create a tile that displays devices that have an application error</span></span>

1.  <span data-ttu-id="a68b2-376">从库中，选择**号码 & 列表**，然后添加新的平铺。</span><span class="sxs-lookup"><span data-stu-id="a68b2-376">Select **Number & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="a68b2-377">定义**常规**属性。</span><span class="sxs-lookup"><span data-stu-id="a68b2-377">Define the **General** properties.</span></span><br>
    <span data-ttu-id="a68b2-378">**组标题：** 将保留为空</span><span class="sxs-lookup"><span data-stu-id="a68b2-378">**Group Title:** Leave empty</span></span><br>
    <span data-ttu-id="a68b2-379">**新组：** 未选定</span><span class="sxs-lookup"><span data-stu-id="a68b2-379">**New Group:** Not Selected</span></span>
3.  <span data-ttu-id="a68b2-380">定义**平铺**属性。</span><span class="sxs-lookup"><span data-stu-id="a68b2-380">Define the **Tile** properties.</span></span><br>
    <span data-ttu-id="a68b2-381">**图例：** 设备所遇最后一个小时内的应用程序错误</span><span class="sxs-lookup"><span data-stu-id="a68b2-381">**Legend:** Devices that experienced an application error in the last hour</span></span><br>
    <span data-ttu-id="a68b2-382">图块查询：</span><span class="sxs-lookup"><span data-stu-id="a68b2-382">**Tile Query:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```</span></span>
4.  <span data-ttu-id="a68b2-383">定义**列表**的属性。</span><span class="sxs-lookup"><span data-stu-id="a68b2-383">Define the **List** properties.</span></span><br>
    <span data-ttu-id="a68b2-384">列表查询：</span><span class="sxs-lookup"><span data-stu-id="a68b2-384">**List Query:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span></span>
5.  <span data-ttu-id="a68b2-385">定义**列标题**。</span><span class="sxs-lookup"><span data-stu-id="a68b2-385">Define **Column Titles**.</span></span><br>
    <span data-ttu-id="a68b2-386">**名称：** 计算机名称</span><span class="sxs-lookup"><span data-stu-id="a68b2-386">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="a68b2-387">**值：** 最后一个错误</span><span class="sxs-lookup"><span data-stu-id="a68b2-387">**Value:** Last Error</span></span>
6.  <span data-ttu-id="a68b2-388">定义**导航查询**。</span><span class="sxs-lookup"><span data-stu-id="a68b2-388">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 2001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  <span data-ttu-id="a68b2-389">选择**应用**，然后**关闭**。</span><span class="sxs-lookup"><span data-stu-id="a68b2-389">Select **Apply** and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-devices-that-have-been-restarted"></a><span data-ttu-id="a68b2-390">创建显示已重新启动设备拼贴</span><span class="sxs-lookup"><span data-stu-id="a68b2-390">Create a tile that displays devices that have been restarted</span></span>

1.  <span data-ttu-id="a68b2-391">从库中，选择**号码 & 列表**，然后添加新的平铺。</span><span class="sxs-lookup"><span data-stu-id="a68b2-391">Select **Number & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="a68b2-392">定义**常规**属性。</span><span class="sxs-lookup"><span data-stu-id="a68b2-392">Define the **General** properties.</span></span><br>
    <span data-ttu-id="a68b2-393">**组标题：** 将保留为空</span><span class="sxs-lookup"><span data-stu-id="a68b2-393">**Group Title:** Leave empty</span></span><br>
    <span data-ttu-id="a68b2-394">**新组：** 未选定</span><span class="sxs-lookup"><span data-stu-id="a68b2-394">**New Group:** Not Selected</span></span>
3.  <span data-ttu-id="a68b2-395">定义**平铺**属性。</span><span class="sxs-lookup"><span data-stu-id="a68b2-395">Define the **Tile** properties.</span></span><br>
    <span data-ttu-id="a68b2-396">**图例：** 其中已重新启动应用程序中的最后一个 24 小时和重新启动次数的设备</span><span class="sxs-lookup"><span data-stu-id="a68b2-396">**Legend:** Devices where the application was restarted in the last 24 hours, and number of restarts</span></span><br>
    <span data-ttu-id="a68b2-397">图块查询：</span><span class="sxs-lookup"><span data-stu-id="a68b2-397">**Tile Query:** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```</span></span>
4.  <span data-ttu-id="a68b2-398">定义**列表**的属性。</span><span class="sxs-lookup"><span data-stu-id="a68b2-398">Define the **List** properties.</span></span><br>
    <span data-ttu-id="a68b2-399">列表查询：</span><span class="sxs-lookup"><span data-stu-id="a68b2-399">**List Query:** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```</span></span>
5.  <span data-ttu-id="a68b2-400">定义**列标题**。</span><span class="sxs-lookup"><span data-stu-id="a68b2-400">Define **Column Titles**.</span></span><br>
    <span data-ttu-id="a68b2-401">**名称：** 计算机名称</span><span class="sxs-lookup"><span data-stu-id="a68b2-401">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="a68b2-402">**值：** 重新启动次数</span><span class="sxs-lookup"><span data-stu-id="a68b2-402">**Value:** Number of Restarts</span></span>
6.  <span data-ttu-id="a68b2-403">定义**导航查询**。</span><span class="sxs-lookup"><span data-stu-id="a68b2-403">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  <span data-ttu-id="a68b2-404">选择**应用**，然后**关闭**。</span><span class="sxs-lookup"><span data-stu-id="a68b2-404">Select **Apply** and then **Close**.</span></span>
8.  <span data-ttu-id="a68b2-405">选择**保存**以保存您的仪表板。</span><span class="sxs-lookup"><span data-stu-id="a68b2-405">Select **Save** to save your dashboard.</span></span>

<span data-ttu-id="a68b2-406">现在您已完成创建您的视图。</span><span class="sxs-lookup"><span data-stu-id="a68b2-406">Now you’ve completed creating your views.</span></span>

## <a name="configure-alerts-in-azure-monitor"></a><span data-ttu-id="a68b2-407">在 Azure 监视器中配置警报</span><span class="sxs-lookup"><span data-stu-id="a68b2-407">Configure Alerts in Azure Monitor</span></span>
<span data-ttu-id="a68b2-408"><a name="Alerts"> </a></span><span class="sxs-lookup"><span data-stu-id="a68b2-408"></span></span>

<span data-ttu-id="a68b2-409">Azure 监视器可引发警报 Skype 会议室系统 v2 控制台遇到问题时通知管理员。</span><span class="sxs-lookup"><span data-stu-id="a68b2-409">Azure Monitor can raise alerts to notify the administrators, when a Skype Room Systems v2 console encounters an issue.</span></span>

<span data-ttu-id="a68b2-410">Azure 监视器包括通过计划的日志搜索定期运行的内置警报机制。</span><span class="sxs-lookup"><span data-stu-id="a68b2-410">Azure Monitor includes a built-in alerting mechanism that runs through scheduled log searches at regular intervals.</span></span> <span data-ttu-id="a68b2-411">如果日志搜索的结果与某个特定条件匹配，则创建警报的记录。</span><span class="sxs-lookup"><span data-stu-id="a68b2-411">If the results of the log search match some particular criteria, an alert record is created.</span></span>

<span data-ttu-id="a68b2-412">规则可以自动运行主动通知您通知或调用其他进程的一个或多个操作。</span><span class="sxs-lookup"><span data-stu-id="a68b2-412">The rule can then automatically run one or more actions to proactively notify you of the alert or invoke another process.</span></span> <span data-ttu-id="a68b2-413">通知可能的选项包括：</span><span class="sxs-lookup"><span data-stu-id="a68b2-413">The possible options with alerts are:</span></span>
-   <span data-ttu-id="a68b2-414">发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="a68b2-414">Sending an email</span></span>
-   <span data-ttu-id="a68b2-415">调用外部进程通过 HTTP POST 请求</span><span class="sxs-lookup"><span data-stu-id="a68b2-415">Invoking an external process through an HTTP POST request</span></span>
-   <span data-ttu-id="a68b2-416">Azure 自动化服务中启动 runbook</span><span class="sxs-lookup"><span data-stu-id="a68b2-416">Starting a runbook in Azure Automation service</span></span>

<span data-ttu-id="a68b2-417">请参阅[日志 Azure 监视器中的通知](https://docs.microsoft.com/azure/azure-monitor/platform/alerts-unified-log)以详细了解如何在 Azure 监视器的警报。</span><span class="sxs-lookup"><span data-stu-id="a68b2-417">See [Log alerts in Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/platform/alerts-unified-log) to learn more about the alerts in Azure Monitor.</span></span>

> [!NOTE]
> <span data-ttu-id="a68b2-418">Skype 会议室系统 v2 设备生成硬件或应用程序错误时，以下示例将发送电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="a68b2-418">The following examples send email alerts when a Skype Room Systems v2 device generates a hardware or an application error.</span></span>

### <a name="configure-an-email-alert-for-skype-room-systems-v2-hardware-issues"></a><span data-ttu-id="a68b2-419">配置电子邮件通知 Skype 会议室系统 v2 硬件问题</span><span class="sxs-lookup"><span data-stu-id="a68b2-419">Configure an email alert for Skype Room Systems v2 hardware issues</span></span>

<span data-ttu-id="a68b2-420">配置通知的规则，检查 Skype 会议室系统 v2 设备的最后一个小时内已遇到硬件问题。</span><span class="sxs-lookup"><span data-stu-id="a68b2-420">Configure an alert rule that checks for Skype Room Systems v2 devices that have encountered hardware issues within the last hour.</span></span>
1.  <span data-ttu-id="a68b2-421">登录到[Microsoft Azure 门户](https://portal.azure.com)，转到日志分析，并选择您的工作区。</span><span class="sxs-lookup"><span data-stu-id="a68b2-421">Sign in to the [Microsoft Azure portal](https://portal.azure.com) and go to Log Analytics and select your workspace.</span></span>

2. <span data-ttu-id="a68b2-422">导航到您的日志分析工作区并选中**通知**，然后选择**新的通知规则**</span><span class="sxs-lookup"><span data-stu-id="a68b2-422">Navigate to your Log Analytics workspace and select **Alerts** and then select **New alert rule**</span></span>

3. <span data-ttu-id="a68b2-423">选择**添加条件**和**自定义日志搜索**</span><span class="sxs-lookup"><span data-stu-id="a68b2-423">Select **Add condition** and then **Custom log search**</span></span>

4.  <span data-ttu-id="a68b2-424">搜索查询文本框中输入以下查询。</span><span class="sxs-lookup"><span data-stu-id="a68b2-424">Enter the following query to the Search query text box.</span></span><br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF
    |sort by TimeGenerated desc
    ```

5.  <span data-ttu-id="a68b2-425">配置通知的逻辑设置：</span><span class="sxs-lookup"><span data-stu-id="a68b2-425">Configure the Alert logic settings:</span></span><br>
    <span data-ttu-id="a68b2-426">**基于：** 结果数</span><span class="sxs-lookup"><span data-stu-id="a68b2-426">**Based on:** Number of results</span></span><br>
    <span data-ttu-id="a68b2-427">**条件：** 更高版本然后</span><span class="sxs-lookup"><span data-stu-id="a68b2-427">**Condition:** Greater then</span></span><br>
    <span data-ttu-id="a68b2-428">**Treshold:** 0</span><span class="sxs-lookup"><span data-stu-id="a68b2-428">**Treshold:** 0</span></span><br>

6. <span data-ttu-id="a68b2-429">配置评估设置并选择**完成**:</span><span class="sxs-lookup"><span data-stu-id="a68b2-429">Configure Evaluation settings and select **Done**:</span></span> <br>
    <span data-ttu-id="a68b2-430">**时间段 （以分钟为单位）：** 60</span><span class="sxs-lookup"><span data-stu-id="a68b2-430">**Period (in minutes):** 60</span></span><br>
    <span data-ttu-id="a68b2-431">**频率 （以分钟为单位）：** 60</span><span class="sxs-lookup"><span data-stu-id="a68b2-431">**Frequency (in minutes):** 60</span></span><br>

7. <span data-ttu-id="a68b2-432">配置操作组：</span><span class="sxs-lookup"><span data-stu-id="a68b2-432">Configure action groups:</span></span>
    1.  <span data-ttu-id="a68b2-433">选择**创建新**</span><span class="sxs-lookup"><span data-stu-id="a68b2-433">Select **Create New**</span></span>
    2.  <span data-ttu-id="a68b2-434">提供适当的*操作组名*和*短名称*字段的名称。</span><span class="sxs-lookup"><span data-stu-id="a68b2-434">Provide suitable names for the *Action group name* and *Short Name* fields.</span></span>
    3.  <span data-ttu-id="a68b2-435">指定一个唯一的*操作名称*并选择**电子邮件/SMS/推送/语音**，然后选择**编辑详细信息**。</span><span class="sxs-lookup"><span data-stu-id="a68b2-435">Specify a unique *Action Name* and select **Email/SMS/Push/Voice**, and then select **Edit details**.</span></span>
    4.  <span data-ttu-id="a68b2-436">选择电子邮件复选框并提供个人或组将接收通知的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="a68b2-436">Select the Email checkbox and provide the email address of the person or group that will recieve the alerts.</span></span>
    5.  <span data-ttu-id="a68b2-437">您还可以提供您的电话号码，以获得通知使用 SMS，和 / 或语音呼叫。</span><span class="sxs-lookup"><span data-stu-id="a68b2-437">You may also provide your phone number to get notified with SMS, a voice call or both.</span></span>
    6. <span data-ttu-id="a68b2-438">选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="a68b2-438">Select **OK**.</span></span>

8. <span data-ttu-id="a68b2-439">**自定义操作**如果您要重写通知电子邮件的主题行。</span><span class="sxs-lookup"><span data-stu-id="a68b2-439">**Customize Actions** if you like to override the subject line of the alert emails.</span></span>

9. <span data-ttu-id="a68b2-440">指定规则名称和说明。</span><span class="sxs-lookup"><span data-stu-id="a68b2-440">Specify a rule name and description.</span></span><br>
    <span data-ttu-id="a68b2-441">**规则名称：** Skype 会议室系统 v2 硬件故障警报</span><span class="sxs-lookup"><span data-stu-id="a68b2-441">**Rule Name:** Skype Room Systems v2 Hardware Failure Alert</span></span><br>
    <span data-ttu-id="a68b2-442">**说明：** 遇到硬件问题的最后一个小时内的设备的列表</span><span class="sxs-lookup"><span data-stu-id="a68b2-442">**Description:** List of devices that encountered a hardware issue within the last hour</span></span><br>

10. <span data-ttu-id="a68b2-443">选择的预期的严重性并确保启用规则。</span><span class="sxs-lookup"><span data-stu-id="a68b2-443">Select the intended severity and make sure the rule is enabled.</span></span>

11. <span data-ttu-id="a68b2-444">选择**创建通知规则**。</span><span class="sxs-lookup"><span data-stu-id="a68b2-444">Select **Create alert rule**.</span></span>

### <a name="configure-an-email-alert-for-skype-room-systems-v2-application-issues"></a><span data-ttu-id="a68b2-445">配置电子邮件通知 Skype 会议室系统 v2 应用程序问题</span><span class="sxs-lookup"><span data-stu-id="a68b2-445">Configure an email alert for Skype Room Systems v2 application issues</span></span>

<span data-ttu-id="a68b2-446">重复同一过程，但使用应用程序问题遇到的最后一个小时内的列表设备将以下查询。</span><span class="sxs-lookup"><span data-stu-id="a68b2-446">Repeat the same procedure but use the following query to list devices that have encountered application issues within the last hour.</span></span>

    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF
    | sort by TimeGenerated desc
    ```

<span data-ttu-id="a68b2-447">现在您已完成定义通知。</span><span class="sxs-lookup"><span data-stu-id="a68b2-447">Now you’ve completed defining alerts.</span></span> <span data-ttu-id="a68b2-448">您可以使用上面的示例定义其他通知。</span><span class="sxs-lookup"><span data-stu-id="a68b2-448">You can define additional alerts by using the examples above.</span></span>

<span data-ttu-id="a68b2-449">生成警报时，您将获取电子邮件，其中列出遇到问题的最后一个小时内的设备。</span><span class="sxs-lookup"><span data-stu-id="a68b2-449">When an alert is generated, you’ll get an email that lists the devices that encountered an issue within the last hour.</span></span>

<span data-ttu-id="a68b2-450">![示例 Azure 监视器通知电子邮件](../../media/Deploy-Azure-Monitor-6.png "示例 Azure 监视器通知电子邮件")</span><span class="sxs-lookup"><span data-stu-id="a68b2-450">![Sample Azure Monitor alert email](../../media/Deploy-Azure-Monitor-6.png "Sample Azure Monitor alert email")</span></span>

## <a name="configure-all-devices-for-azure-monitoring"></a><span data-ttu-id="a68b2-451">为 Azure 监控配置的所有设备</span><span class="sxs-lookup"><span data-stu-id="a68b2-451">Configure all devices for Azure Monitoring</span></span>
<span data-ttu-id="a68b2-452"><a name="configure_all_devices"></a>配置仪表板和通知后，您可以设置和配置上所有的 Skype 会议室系统 v2 设备，以完成监控部署 Microsoft 监控代理。</span><span class="sxs-lookup"><span data-stu-id="a68b2-452"><a name="configure_all_devices"> </a> After the dashboards and alerts are configured, you can set up and configure Microsoft Monitoring agent on all Skype Room Systems v2 devices to complete your monitoring deployment.</span></span>

<span data-ttu-id="a68b2-453">尽管您可以安装，并在每个设备上手动配置 Microsoft 监控代理，但强烈建议您利用现有软件部署工具和方法。</span><span class="sxs-lookup"><span data-stu-id="a68b2-453">Although you can install and configure the Microsoft Monitoring agent manually on each device, we highly recommend you leverage existing software deployment tools and methods.</span></span>

<span data-ttu-id="a68b2-454">如果您首次构建 Skype 会议室系统 v2 设备，您可能想要包括 Microsoft 监控代理安装和配置步骤生成过程的一部分。</span><span class="sxs-lookup"><span data-stu-id="a68b2-454">If you’re building your Skype Room Systems v2 devices for the first time, you might want to include the Microsoft Monitoring agent setup and configuration steps as part of your build process.</span></span> <span data-ttu-id="a68b2-455">有关详细信息，请参阅[安装使用命令行的代理](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line)。</span><span class="sxs-lookup"><span data-stu-id="a68b2-455">For more information, see [Install the agent using the command line](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line).</span></span>

### <a name="deploying-microsoft-monitoring-agent-by-using-a-group-policy-object-gpo"></a><span data-ttu-id="a68b2-456">使用组策略对象 (GPO) 部署 Microsoft 监控代理</span><span class="sxs-lookup"><span data-stu-id="a68b2-456">Deploying Microsoft Monitoring agent by using a Group Policy Object (GPO)</span></span>

<span data-ttu-id="a68b2-457">如果您已部署 Skype 会议室系统 v2 设备实现 Azure 监控之前，您可以使用提供的脚本设置和使用 Active Directory 组策略对象配置代理。</span><span class="sxs-lookup"><span data-stu-id="a68b2-457">If you already deployed your Skype Room Systems v2 devices before you implement Azure Monitoring, you can use the provided script to set up and configure the agents by using Active Directory group policy objects.</span></span>

1.  <span data-ttu-id="a68b2-458">创建共享的网络路径，并向**域计算机**组授予读取访问权限。</span><span class="sxs-lookup"><span data-stu-id="a68b2-458">Create a shared network path and grant read access to **Domain Computers** group.</span></span>

2.  <span data-ttu-id="a68b2-459">下载 Microsoft 监控代理用于 Windows 的从 64 位版本<https://go.microsoft.com/fwlink/?LinkID=517476></span><span class="sxs-lookup"><span data-stu-id="a68b2-459">Download the 64-bit version of the Microsoft Monitoring Agent for Windows from <https://go.microsoft.com/fwlink/?LinkID=517476></span></span>

3.  <span data-ttu-id="a68b2-460">安装程序包的内容解压到网络共享。</span><span class="sxs-lookup"><span data-stu-id="a68b2-460">Extract the contents of the setup package into the network share.</span></span>
    1.  <span data-ttu-id="a68b2-461">打开命令提示符窗口，并执行**MMASetup AMD64.exe /c**</span><span class="sxs-lookup"><span data-stu-id="a68b2-461">Open a Command Prompt window, and then execute **MMASetup-AMD64.exe /c**</span></span>
    2.  <span data-ttu-id="a68b2-462">指定您刚创建的共享和提取内容。</span><span class="sxs-lookup"><span data-stu-id="a68b2-462">Specify the share you just created, and extract the content.</span></span>

4.  <span data-ttu-id="a68b2-463">创建新的组策略对象，并将其分配给组织单位 Skype 会议室系统 v2 计算机帐户的位置。</span><span class="sxs-lookup"><span data-stu-id="a68b2-463">Create a new Group Policy Object and assign it to the organizational unit where Skype Room Systems v2 machine accounts are located.</span></span>

5.  <span data-ttu-id="a68b2-464">配置 PowerShell 执行策略：</span><span class="sxs-lookup"><span data-stu-id="a68b2-464">Configure PowerShell execution policy:</span></span>
    1.  <span data-ttu-id="a68b2-465">编辑新创建的组策略对象，并导航到计算机配置\\策略\\管理模板\\Windows 组件\\Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a68b2-465">Edit the newly created Group Policy Object and navigate to Computer Configuration \\ Policies \\ Administrative Templates \\ Windows Components \\ Windows PowerShell</span></span>
    2.  <span data-ttu-id="a68b2-466">启用**脚本执行打开**并**允许本地**脚本设置**执行策略**。</span><span class="sxs-lookup"><span data-stu-id="a68b2-466">Enable the **Turn on Script Execution** and set **Execution Policy** to **Allow Local Scripts**.</span></span>

6.  <span data-ttu-id="a68b2-467">配置启动脚本：</span><span class="sxs-lookup"><span data-stu-id="a68b2-467">Configure the startup script:</span></span>
    1.  <span data-ttu-id="a68b2-468">复制以下脚本并将其保存为安装 MMAgent.ps1。</span><span class="sxs-lookup"><span data-stu-id="a68b2-468">Copy the following script and save it as Install-MMAgent.ps1.</span></span>
    2.  <span data-ttu-id="a68b2-469">修改 WorkspaceId、 WorkspaceKey 和 SetupPath 参数，以匹配您的配置。</span><span class="sxs-lookup"><span data-stu-id="a68b2-469">Modify WorkspaceId, WorkspaceKey, and SetupPath parameters to match your configuration.</span></span>
    3.  <span data-ttu-id="a68b2-470">编辑相同的组策略对象，并导航到计算机配置\\策略\\Windows 设置\\脚本 （启动/关机）</span><span class="sxs-lookup"><span data-stu-id="a68b2-470">Edit the same Group Policy Object and navigate to Computer Configuration \\ Policies \\ Windows Settings \\ Scripts (Startup/Shutdown)</span></span>
    4.  <span data-ttu-id="a68b2-471">双击可选择**启动**中，，然后选择**PowerShell 脚本**。</span><span class="sxs-lookup"><span data-stu-id="a68b2-471">Double-click to select **Startup**, and then select **PowerShell Scripts**.</span></span>
    5.  <span data-ttu-id="a68b2-472">选择**显示文件**，然后将**安装 MMAgent.ps1**文件复制到该文件夹。</span><span class="sxs-lookup"><span data-stu-id="a68b2-472">Select **Show Files**, and then copy the **Install-MMAgent.ps1** file to that folder.</span></span>
    6.  <span data-ttu-id="a68b2-473">选择**添加**，然后**浏览**。</span><span class="sxs-lookup"><span data-stu-id="a68b2-473">Select **Add**, and then **Browse**.</span></span>
    7.  <span data-ttu-id="a68b2-474">选择您刚复制的 ps1 脚本。</span><span class="sxs-lookup"><span data-stu-id="a68b2-474">Select the ps1 script you just copied.</span></span>

7.  <span data-ttu-id="a68b2-475">Skype 会议室系统 v2 设备应安装和配置第二个重新启动 Microsoft 监控代理。</span><span class="sxs-lookup"><span data-stu-id="a68b2-475">Skype Room Systems v2 devices should install and configure the Microsoft Monitoring agent with the second reboot.</span></span>

```
# Install-MMAgent.ps1
<#
Date:        04/20/2018
Script:      Install-MMAgent.ps1
Version:     1.0
#>

# Set the parameters
$WorkspaceId = "<your workspace id>"
$WorkspaceKey = "<your workspace key>"
$SetupPath = "\\Server\Share"

$SetupParameters = "/qn NOAPM=1 ADD_OPINSIGHTS_WORKSPACE=1 OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE=0 OPINSIGHTS_WORKSPACE_ID=$WorkspaceId OPINSIGHTS_WORKSPACE_KEY=$WorkspaceKey AcceptEndUserLicenseAgreement=1"

# $SetupParameters = $SetupParameters + " OPINSIGHTS_PROXY_URL=<Proxy server URL> OPINSIGHTS_PROXY_USERNAME=<Proxy server username> OPINSIGHTS_PROXY_PASSWORD=<Proxy server password>"

# Start PowerShell logging
Start-Transcript -Path C:\Temp\MMA-Install.Log

# Check if the Microsoft Monitoring Agent is installed
$mma = New-Object -ComObject 'AgentConfigManager.MgmtSvcCfg'

# Check if the Microsoft Monitoring agent is installed
if (!$mma)
{
    #Install agent
    Start-Process -FilePath "$SetupPath\Setup.exe" -ArgumentList $SetupParameters -ErrorAction Stop -Wait
}

# Check if the agent has a valid configuration
$CheckMMA = $mma.GetCloudWorkspace($WorkspaceId).AgentId
if (!$CheckMMA)
{
    # Apply new configuration
    $mma.AddCloudWorkspace($WorkspaceId, $WorkspaceKey)
    $mma.ReloadConfiguration()
}

Stop-Transcript
```

> [!NOTE]
> <span data-ttu-id="a68b2-476">当您需要重新配置代理、 将其移至不同的工作区中，或在初始安装后修改代理设置时，您可以参考文章[管理和维护日志分析代理](https://docs.microsoft.com/azure/azure-monitor/platform/agent-manage)。</span><span class="sxs-lookup"><span data-stu-id="a68b2-476">You can refer to the article [Managing and maintaining the Log Analytics agent](https://docs.microsoft.com/azure/azure-monitor/platform/agent-manage) when you need to reconfigure an agent, move it to a different workspace, or modify proxy settings after the initial installation.</span></span>

## <a name="additional-solutions"></a><span data-ttu-id="a68b2-477">其他解决方案</span><span class="sxs-lookup"><span data-stu-id="a68b2-477">Additional Solutions</span></span>
<span data-ttu-id="a68b2-478"><a name="Solutions"> </a></span><span class="sxs-lookup"><span data-stu-id="a68b2-478"></span></span>

<span data-ttu-id="a68b2-479">Azure 监视器提供通过其[解决方案库](https://docs.microsoft.com/azure/azure-monitor/insights/solutions)来进一步帮助监视您的环境的内置管理解决方案。</span><span class="sxs-lookup"><span data-stu-id="a68b2-479">Azure Monitor provides built-in management solutions through its [solution gallery](https://docs.microsoft.com/azure/azure-monitor/insights/solutions) to further help you monitor your environment.</span></span> <span data-ttu-id="a68b2-480">我们强烈建议将[警报管理](https://docs.microsoft.com/azure/azure-monitor/platform/alert-management-solution)和[Azure 日志分析代理运行状况](https://docs.microsoft.com/azure/azure-monitor/insights/solution-agenthealth)解决方案添加到您的工作区。</span><span class="sxs-lookup"><span data-stu-id="a68b2-480">We highly recommend that you add [Alert Management](https://docs.microsoft.com/azure/azure-monitor/platform/alert-management-solution) and [Azure Log Analytics Agent Health](https://docs.microsoft.com/azure/azure-monitor/insights/solution-agenthealth) solutions to your workspace as well.</span></span>

> [!NOTE]
> <span data-ttu-id="a68b2-481">代理运行状况解决方案可帮助您确定您的环境中已过时或断开 Microsoft 监控代理和警报管理解决方案提供了有关已引发的给定期间内的警报的详细信息。</span><span class="sxs-lookup"><span data-stu-id="a68b2-481">The Agent Health solution can help you identify outdated or broken Microsoft Monitoring agents within your environment, and the Alert Management solution provides details about the alerts that have been raised within a given period.</span></span>

## <a name="see-also"></a><span data-ttu-id="a68b2-482">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a68b2-482">See also</span></span>

[<span data-ttu-id="a68b2-483">规划 Skype 会议室系统 v2 管理使用 Azure 监视器</span><span class="sxs-lookup"><span data-stu-id="a68b2-483">Plan Skype Room Systems v2 management with Azure Monitor</span></span>](../../plan-your-deployment/clients-and-devices/azure-monitor.md)

[<span data-ttu-id="a68b2-484">管理使用 Azure 监视器的 Skype 会议室系统 v2 设备</span><span class="sxs-lookup"><span data-stu-id="a68b2-484">Manage Skype Room Systems v2 devices with Azure Monitor</span></span>](../../manage/skype-room-systems-v2/azure-monitor.md)