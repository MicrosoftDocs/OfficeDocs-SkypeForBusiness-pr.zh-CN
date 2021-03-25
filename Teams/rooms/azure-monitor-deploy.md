---
title: 使用 Azure Monitor 部署 Microsoft Teams 会议室管理
ms.author: dstrome
author: dstrome
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.assetid: d86ff657-ee92-4b06-aee3-d4c43090bdcb
description: 本文讨论如何使用 Azure Monitor 以集成式的端到端方式部署 Microsoft Teams 会议室设备的管理。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7046fc0010a4337ea14854e356600ccf3428f9d0
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117590"
---
# <a name="deploy-no-loc-textmicrosoft-teams-rooms-management-with-no-loc-textazure-monitor"></a><span data-ttu-id="e9e27-103">使用 :::no-loc text="Microsoft Teams Rooms"::: 部署管理 :::no-loc text="Azure Monitor":::</span><span class="sxs-lookup"><span data-stu-id="e9e27-103">Deploy :::no-loc text="Microsoft Teams Rooms"::: management with :::no-loc text="Azure Monitor":::</span></span>

<span data-ttu-id="e9e27-104">本文讨论如何使用 设置和部署集成的端到端 :::no-loc text="Microsoft Teams Rooms"::: 设备管理 :::no-loc text="Azure Monitor"::: 。</span><span class="sxs-lookup"><span data-stu-id="e9e27-104">This article discusses how to set up and deploy integrated, end-to-end management of :::no-loc text="Microsoft Teams Rooms"::: devices by using :::no-loc text="Azure Monitor":::.</span></span>

<span data-ttu-id="e9e27-105">可在 内 :::no-loc text="Log Analytics"::: :::no-loc text="Azure Monitor"::: 进行配置，提供有助于管理会议室设备的基本遥测和 :::no-loc text="Microsoft Teams Rooms"::: 警报。</span><span class="sxs-lookup"><span data-stu-id="e9e27-105">You can configure :::no-loc text="Log Analytics"::: within :::no-loc text="Azure Monitor"::: to provide basic telemetry and alerts that will help you manage :::no-loc text="Microsoft Teams Rooms"::: meeting room devices.</span></span> <span data-ttu-id="e9e27-106">随着管理解决方案的成熟，可以决定部署其他数据和管理功能，以创建设备可用性和性能的更详细视图。</span><span class="sxs-lookup"><span data-stu-id="e9e27-106">As your management solution matures, you might decide to deploy additional data and management capabilities to create a more detailed view of device availability and performance.</span></span>

<span data-ttu-id="e9e27-107">遵循本指南，可以使用如以下示例所示的仪表板获取有关设备可用性、应用程序和硬件运行状况以及应用程序和操作系统版本分发 :::no-loc text="Microsoft Teams Rooms"::: 的详细状态报告。</span><span class="sxs-lookup"><span data-stu-id="e9e27-107">By following this guide, you can use a dashboard like the following example to get detailed status reporting for device availability, application and hardware health, and :::no-loc text="Microsoft Teams Rooms"::: application and operating system version distribution.</span></span>

<span data-ttu-id="e9e27-108">![Microsoft Teams 会议室的示例 Log Analytics 视图的屏幕截图](../media/Deploy-Azure-Monitor-1.png "Microsoft Teams 会议室的示例 Log Analytics 视图")</span><span class="sxs-lookup"><span data-stu-id="e9e27-108">![Screenshot of sample Log Analytics view for Microsoft Teams Rooms](../media/Deploy-Azure-Monitor-1.png "Sample Log Analytics view for Microsoft Teams Rooms")</span></span>

<span data-ttu-id="e9e27-109">你需要在高级别执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="e9e27-109">At a high level, you need to perform the following tasks:</span></span>


1. [<span data-ttu-id="e9e27-110">验证 :::no-loc text="Log Analytics"::: 配置</span><span class="sxs-lookup"><span data-stu-id="e9e27-110">Validate :::no-loc text="Log Analytics"::: configuration</span></span>](azure-monitor-deploy.md#validate_LogAnalytics)
2. [<span data-ttu-id="e9e27-111">配置用于管理设置 :::no-loc text="Log Analytics"::: 的测试设备</span><span class="sxs-lookup"><span data-stu-id="e9e27-111">Configure test devices for :::no-loc text="Log Analytics"::: management setup</span></span>](azure-monitor-deploy.md#configure_test_devices)
3. [<span data-ttu-id="e9e27-112">映射自定义字段</span><span class="sxs-lookup"><span data-stu-id="e9e27-112">Map custom fields</span></span>](azure-monitor-deploy.md#Custom_fields)
4. [<span data-ttu-id="e9e27-113">在 :::no-loc text="Microsoft Teams Rooms"::: 中定义视图 :::no-loc text="Log Analytics":::</span><span class="sxs-lookup"><span data-stu-id="e9e27-113">Define the :::no-loc text="Microsoft Teams Rooms"::: views in :::no-loc text="Log Analytics":::</span></span>](azure-monitor-deploy.md#Define_Views)
5. [<span data-ttu-id="e9e27-114">定义警报</span><span class="sxs-lookup"><span data-stu-id="e9e27-114">Define alerts</span></span>](azure-monitor-deploy.md#Alerts)
6. [<span data-ttu-id="e9e27-115">配置用于监视的所有设备</span><span class="sxs-lookup"><span data-stu-id="e9e27-115">Configure all devices for Monitoring</span></span>](azure-monitor-deploy.md#configure_all_devices)
7. [<span data-ttu-id="e9e27-116">配置其他 :::no-loc text="Azure Monitor"::: 解决方案</span><span class="sxs-lookup"><span data-stu-id="e9e27-116">Configure additional :::no-loc text="Azure Monitor"::: solutions</span></span>](azure-monitor-deploy.md#Solutions)

> [!IMPORTANT]
> <span data-ttu-id="e9e27-117">尽管只需最少的配置，就可以监视运行操作系统的计算机，但在开始将代理部署到所有设备之前，仍然需要执行一些特定于 :::no-loc text="Azure Monitor"::: :::no-loc text="Log Analytics"::: :::no-loc text="Windows"::: :::no-loc text="Microsoft Teams Rooms"::: 特定的 :::no-loc text="Microsoft Teams Rooms"::: 步骤。</span><span class="sxs-lookup"><span data-stu-id="e9e27-117">Although with minimal configuration, :::no-loc text="Azure Monitor"::: :::no-loc text="Log Analytics"::: can monitor a computer running a :::no-loc text="Windows"::: operating system, there are still some :::no-loc text="Microsoft Teams Rooms":::–specific steps that you need to take before you start deploying agents to all :::no-loc text="Microsoft Teams Rooms"::: devices.</span></span>
> <span data-ttu-id="e9e27-118">因此，强烈建议以正确的顺序执行所有配置步骤，以便进行受控的设置和配置。</span><span class="sxs-lookup"><span data-stu-id="e9e27-118">Therefore, we highly recommend you perform all configuration steps in the right order for a controlled setup and configuration.</span></span> <span data-ttu-id="e9e27-119">最终结果的质量在很大程度上取决于初始配置的质量。</span><span class="sxs-lookup"><span data-stu-id="e9e27-119">The quality of the end result very much depends on the quality of the initial configuration.</span></span>

## <a name="validate-no-loc-textlog-analytics-configuration"></a><span data-ttu-id="e9e27-120">验证 :::no-loc text="Log Analytics"::: 配置</span><span class="sxs-lookup"><span data-stu-id="e9e27-120">Validate :::no-loc text="Log Analytics"::: configuration</span></span>
<span data-ttu-id="e9e27-121"><a name="validate_LogAnalytics"> </a></span><span class="sxs-lookup"><span data-stu-id="e9e27-121"><a name="validate_LogAnalytics"> </a></span></span>

<span data-ttu-id="e9e27-122">需要一个 :::no-loc text="Log Analytics"::: 工作区，以开始从设备收集 :::no-loc text="Microsoft Teams Rooms"::: 日志。</span><span class="sxs-lookup"><span data-stu-id="e9e27-122">You need to have a :::no-loc text="Log Analytics"::: workspace to start collecting logs from :::no-loc text="Microsoft Teams Rooms"::: devices.</span></span> <span data-ttu-id="e9e27-123">工作区是具有其自己的数据存储库、数据源和解决方案的独特 :::no-loc text="Log Analytics"::: 环境。</span><span class="sxs-lookup"><span data-stu-id="e9e27-123">A workspace is a unique :::no-loc text="Log Analytics"::: environment with its own data repository, data sources, and solutions.</span></span> <span data-ttu-id="e9e27-124">如果已有一个工作区，可以使用它来监视部署，也可以创建特定于监视 :::no-loc text="Log Analytics"::: :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Log Analytics"::: 需求的专用 :::no-loc text="Microsoft Teams Rooms"::: 工作区。</span><span class="sxs-lookup"><span data-stu-id="e9e27-124">If you already have an existing :::no-loc text="Log Analytics"::: workspace, you might use it to monitor your :::no-loc text="Microsoft Teams Rooms"::: deployment or alternatively, you can create a dedicated :::no-loc text="Log Analytics"::: workspace specific to your :::no-loc text="Microsoft Teams Rooms"::: monitoring needs.</span></span>

<span data-ttu-id="e9e27-125">如果需要创建新工作区，请按照在门户中创建工作区 :::no-loc text="Log Analytics"::: [一文 :::no-loc text="Log Analytics"::: 的说明 :::no-loc text="Azure"::: 进行操作](/azure/azure-monitor/learn/quick-create-workspace)</span><span class="sxs-lookup"><span data-stu-id="e9e27-125">If you need to create a new :::no-loc text="Log Analytics"::: workspace, follow the instructions in the article [Create a :::no-loc text="Log Analytics"::: workspace in the :::no-loc text="Azure"::: portal](/azure/azure-monitor/learn/quick-create-workspace)</span></span>

> [!NOTE]
> <span data-ttu-id="e9e27-126">若要 :::no-loc text="Log Analytics"::: 与 :::no-loc text="Azure Monitor"::: 一同使用，需要具有活动 :::no-loc text="Azure"::: 订阅。</span><span class="sxs-lookup"><span data-stu-id="e9e27-126">To use :::no-loc text="Log Analytics"::: with :::no-loc text="Azure Monitor":::, you need to have an active :::no-loc text="Azure"::: subscription.</span></span> <span data-ttu-id="e9e27-127">如果没有订阅，可以创建免费 :::no-loc text="Azure"::: [试用版](https://azure.microsoft.com/free) 订阅作为起点。</span><span class="sxs-lookup"><span data-stu-id="e9e27-127">If you don't have an :::no-loc text="Azure"::: subscription, you can create [a free trial subscription](https://azure.microsoft.com/free) as a starting point.</span></span>

### <a name="configure-no-loc-textlog-analytics-to-collect-no-loc-textmicrosoft-teams-rooms-event-logs"></a><span data-ttu-id="e9e27-128">配置为 :::no-loc text="Log Analytics"::: 收集 :::no-loc text="Microsoft Teams Rooms"::: 事件日志</span><span class="sxs-lookup"><span data-stu-id="e9e27-128">Configure :::no-loc text="Log Analytics"::: to collect :::no-loc text="Microsoft Teams Rooms"::: event logs</span></span>

<span data-ttu-id="e9e27-129">:::no-loc text="Log Analytics"::: 仅从设置 :::no-loc text="Windows"::: 中指定的事件日志中收集事件。</span><span class="sxs-lookup"><span data-stu-id="e9e27-129">:::no-loc text="Log Analytics"::: only collects events from the :::no-loc text="Windows"::: event logs that are specified in the settings.</span></span> <span data-ttu-id="e9e27-130">对于每个日志，只会收集具有所选严重性的事件。</span><span class="sxs-lookup"><span data-stu-id="e9e27-130">For each log, only the events with the selected severities are collected.</span></span>

<span data-ttu-id="e9e27-131">需要配置为 :::no-loc text="Log Analytics"::: 收集监视设备和应用程序状态 :::no-loc text="Microsoft Teams Rooms"::: 所需的日志。</span><span class="sxs-lookup"><span data-stu-id="e9e27-131">You need to configure :::no-loc text="Log Analytics"::: to collect the logs required to monitor :::no-loc text="Microsoft Teams Rooms"::: device and application status.</span></span> <span data-ttu-id="e9e27-132">:::no-loc text="Microsoft Teams Rooms"::: 设备使用 **:::no-loc text="Skype Room System":::** 事件日志。</span><span class="sxs-lookup"><span data-stu-id="e9e27-132">:::no-loc text="Microsoft Teams Rooms"::: devices use the **:::no-loc text="Skype Room System":::** event log.</span></span>

<span data-ttu-id="e9e27-133">若要 :::no-loc text="Log Analytics"::: 配置为收集 :::no-loc text="Microsoft Teams Rooms"::: 事件，请参阅 中的[ :::no-loc text="Windows"::: 事件日志数据源 :::no-loc text="Azure Monitor"::: ](/azure/azure-monitor/platform/data-sources-windows-events)</span><span class="sxs-lookup"><span data-stu-id="e9e27-133">To configure :::no-loc text="Log Analytics"::: to collect the :::no-loc text="Microsoft Teams Rooms"::: events, see [:::no-loc text="Windows"::: event log data sources in :::no-loc text="Azure Monitor":::](/azure/azure-monitor/platform/data-sources-windows-events)</span></span>

<span data-ttu-id="e9e27-134">![事件日志设置的屏幕截图](../media/Deploy-Azure-Monitor-2.png "事件日志设置")</span><span class="sxs-lookup"><span data-stu-id="e9e27-134">![Screenshot of event log settings](../media/Deploy-Azure-Monitor-2.png "Event log settings")</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e9e27-135">配置 :::no-loc text="Windows"::: 事件日志设置，输入 **:::no-loc text="Skype Room System":::** 作为事件日志名称，然后选中"错误、**警告** 和 **信息**"复选框。</span><span class="sxs-lookup"><span data-stu-id="e9e27-135">Configure :::no-loc text="Windows"::: Event Log settings and enter **:::no-loc text="Skype Room System":::** as event log name, and then select the **Error**, **Warning**, and **Information** check boxes.</span></span>

## <a name="configure-test-devices-for-azure-monitoring"></a><span data-ttu-id="e9e27-136">为 Azure 监视配置测试设备</span><span class="sxs-lookup"><span data-stu-id="e9e27-136">Configure test devices for Azure Monitoring</span></span>
<span data-ttu-id="e9e27-137"><a name="configure_test_devices"> </a></span><span class="sxs-lookup"><span data-stu-id="e9e27-137"><a name="configure_test_devices"> </a></span></span>

<span data-ttu-id="e9e27-138">需要做好监视 :::no-loc text="Log Analytics"::: 相关 :::no-loc text="Microsoft Teams Rooms"::: 事件的准备。</span><span class="sxs-lookup"><span data-stu-id="e9e27-138">You need to prepare :::no-loc text="Log Analytics"::: to be able to monitor :::no-loc text="Microsoft Teams Rooms":::–related events.</span></span> <span data-ttu-id="e9e27-139">首先，只需将代理部署到具有物理访问权限的一个或两个设备，然后让这些测试设备生成一些数据，并 :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Microsoft Teams Rooms"::: 推送到 :::no-loc text="Log Analytics"::: 工作区。</span><span class="sxs-lookup"><span data-stu-id="e9e27-139">To start with, you need to deploy :::no-loc text="Microsoft Monitoring"::: agents to just one or two :::no-loc text="Microsoft Teams Rooms"::: devices that you have physical access to, and get those test devices generate some data and push it to the :::no-loc text="Log Analytics"::: workspace.</span></span>

### <a name="install-no-loc-textmicrosoft-monitoring-agents-to-test-devices"></a><span data-ttu-id="e9e27-140">安装 :::no-loc text="Microsoft Monitoring"::: 代理以测试设备</span><span class="sxs-lookup"><span data-stu-id="e9e27-140">Install :::no-loc text="Microsoft Monitoring"::: agents to test devices</span></span>

<span data-ttu-id="e9e27-141">按照将计算机连接到 中的服务中提供的说明，将代理 :::no-loc text="Microsoft Monitoring"::: [ :::no-loc text="Windows"::: :::no-loc text="Log Analytics"::: 部署到测试设备 :::no-loc text="Azure"::: ](/azure/azure-monitor/platform/agent-windows)。</span><span class="sxs-lookup"><span data-stu-id="e9e27-141">Deploy the :::no-loc text="Microsoft Monitoring"::: agent to the test devices by using the instructions provided in [Connect :::no-loc text="Windows"::: computers to the :::no-loc text="Log Analytics"::: service in :::no-loc text="Azure":::](/azure/azure-monitor/platform/agent-windows).</span></span> <span data-ttu-id="e9e27-142">本文详细介绍了部署代理的步骤、获取工作区 ID _ 和 _ 主密钥 \* 以将设备连接到部署的说明，以及验证代理与实例的连接 :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Windows"::: :::no-loc text="Log Analytics":::  \* \*\* :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Azure Monitor"::: :::no-loc text="Log Analytics"::: 的步骤。</span><span class="sxs-lookup"><span data-stu-id="e9e27-142">This article provides detailed information about the steps for deploying :::no-loc text="Microsoft Monitoring"::: Agent for :::no-loc text="Windows":::, instructions for obtaining the :::no-loc text="Log Analytics"::: ***Workspace ID** _ and the _ *_primary key_** to get :::no-loc text="Microsoft Teams Rooms"::: devices connected to your :::no-loc text="Azure Monitor"::: deployment, and steps to verify agent connectivity to :::no-loc text="Log Analytics"::: instance.</span></span>

### <a name="generate-sample-no-loc-textmicrosoft-teams-rooms-events"></a><span data-ttu-id="e9e27-143">生成 :::no-loc text="Microsoft Teams Rooms"::: 示例事件</span><span class="sxs-lookup"><span data-stu-id="e9e27-143">Generate sample :::no-loc text="Microsoft Teams Rooms"::: events</span></span>

<span data-ttu-id="e9e27-144">将 :::no-loc text="Microsoft Monitoring"::: 代理部署到测试设备后，验证 所需的事件日志数据是否由 收集 :::no-loc text="Azure Monitor"::: 。</span><span class="sxs-lookup"><span data-stu-id="e9e27-144">After the :::no-loc text="Microsoft Monitoring"::: agent is deployed onto the test devices, verify that the required event log data is collected by :::no-loc text="Azure Monitor":::.</span></span>

> [!NOTE]
> <span data-ttu-id="e9e27-145">安装代理后重新启动设备，并确保会议应用已启动，以便它可以在事件日志中生成 :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Microsoft Teams Rooms"::: 新事件。</span><span class="sxs-lookup"><span data-stu-id="e9e27-145">Reboot the device after the installation of the :::no-loc text="Microsoft Monitoring"::: agent, and make sure that :::no-loc text="Microsoft Teams Rooms"::: Meeting app is started, so that it can generate new events into the Event Log.</span></span>

1.  <span data-ttu-id="e9e27-146">登录到门户[ :::no-loc text="Microsoft Azure"::: ，](https://portal.azure.com)转到并选择 :::no-loc text="Log Analytics"::: 工作区。</span><span class="sxs-lookup"><span data-stu-id="e9e27-146">Sign in to the [:::no-loc text="Microsoft Azure"::: portal](https://portal.azure.com) and go to :::no-loc text="Log Analytics"::: and select your workspace.</span></span>

2.  <span data-ttu-id="e9e27-147">列出设备生成的检测信号 :::no-loc text="Microsoft Teams Rooms"::: 事件：</span><span class="sxs-lookup"><span data-stu-id="e9e27-147">List the heartbeat events generated by a :::no-loc text="Microsoft Teams Rooms"::: device:</span></span>
    1.  <span data-ttu-id="e9e27-148">选择工作区，转到" **日志** "，然后使用查询检索将具有 的自定义字段的检测信号记录 :::no-loc text="Microsoft Teams Rooms"::: 。</span><span class="sxs-lookup"><span data-stu-id="e9e27-148">Select your workspace and go to **Logs** and use a query to retrieve the heartbeat records that will have the custom fields for :::no-loc text="Microsoft Teams Rooms":::.</span></span>
    2.  <span data-ttu-id="e9e27-149">示例查询： `Event | where Source == "SRS-App" and EventID == 2000`</span><span class="sxs-lookup"><span data-stu-id="e9e27-149">Sample query: `Event | where Source == "SRS-App" and EventID == 2000`</span></span>

3.  <span data-ttu-id="e9e27-150">确保查询返回包含会议应用生成的事件的 :::no-loc text="Microsoft Teams Rooms"::: 日志记录。</span><span class="sxs-lookup"><span data-stu-id="e9e27-150">Make sure that the query returns log records that include events generated by the :::no-loc text="Microsoft Teams Rooms"::: meetings app.</span></span>

4.  <span data-ttu-id="e9e27-151">生成硬件问题，并验证所需的事件是否记录在 中 :::no-loc text="Azure Log Analytics"::: 。</span><span class="sxs-lookup"><span data-stu-id="e9e27-151">Generate a hardware issue, and validate that the required events are logged in :::no-loc text="Azure Log Analytics":::.</span></span>
    1.  <span data-ttu-id="e9e27-152">拔下测试系统上的一个外围设备 :::no-loc text="Microsoft Teams Rooms"::: 。</span><span class="sxs-lookup"><span data-stu-id="e9e27-152">Unplug one of the peripheral devices on the test :::no-loc text="Microsoft Teams Rooms"::: system.</span></span> <span data-ttu-id="e9e27-153">这可以是相机、免提电话、麦克风或前会议室显示器</span><span class="sxs-lookup"><span data-stu-id="e9e27-153">This could be the camera, speakerphone, microphone, or Front Room Display</span></span>
    2.  <span data-ttu-id="e9e27-154">等待 10 分钟，以在 中填充事件日志 :::no-loc text="Azure Log Analytics"::: 。</span><span class="sxs-lookup"><span data-stu-id="e9e27-154">Wait 10 minutes for the event log to be populated in :::no-loc text="Azure Log Analytics":::.</span></span>
    3.  <span data-ttu-id="e9e27-155">使用查询列出硬件错误事件： `Event | where Source == "SRS-App" and EventID == 3001`</span><span class="sxs-lookup"><span data-stu-id="e9e27-155">Use a query to list hardware error events: `Event | where Source == "SRS-App" and EventID == 3001`</span></span>

5.  <span data-ttu-id="e9e27-156">生成应用程序问题，并验证是否记录了所需的事件。</span><span class="sxs-lookup"><span data-stu-id="e9e27-156">Generate an application issue, and validate that the required events are logged.</span></span>
    1.  <span data-ttu-id="e9e27-157">修改 :::no-loc text="Microsoft Teams Rooms"::: 应用程序配置，并键入错误的会话启动协议 (SIP) /密码对。</span><span class="sxs-lookup"><span data-stu-id="e9e27-157">Modify :::no-loc text="Microsoft Teams Rooms"::: application configuration, and type an incorrect Session Initiation Protocol (SIP) address/password pair.</span></span>
    2.  <span data-ttu-id="e9e27-158">等待 10 分钟，以在 中填充事件日志 :::no-loc text="Azure Log Analytics"::: 。</span><span class="sxs-lookup"><span data-stu-id="e9e27-158">Wait 10 minutes for the event log to be populated in :::no-loc text="Azure Log Analytics":::.</span></span>
    3.  <span data-ttu-id="e9e27-159">使用查询列出应用程序错误事件： `Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`</span><span class="sxs-lookup"><span data-stu-id="e9e27-159">Use a query to list application error events: `Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e9e27-160">在配置自定义字段之前，需要这些示例事件日志。</span><span class="sxs-lookup"><span data-stu-id="e9e27-160">These sample event logs are required before custom fields can be configured.</span></span> <span data-ttu-id="e9e27-161">收集所需的事件日志之前，不要继续执行下一步。</span><span class="sxs-lookup"><span data-stu-id="e9e27-161">Don't proceed to the next step until you have collected the required event logs.</span></span>

## <a name="map-custom-fields"></a><span data-ttu-id="e9e27-162">映射自定义字段</span><span class="sxs-lookup"><span data-stu-id="e9e27-162">Map custom fields</span></span>
<span data-ttu-id="e9e27-163"><a name="Custom_fields"> </a></span><span class="sxs-lookup"><span data-stu-id="e9e27-163"><a name="Custom_fields"> </a></span></span>

<span data-ttu-id="e9e27-164">使用自定义字段从事件日志中提取特定数据。</span><span class="sxs-lookup"><span data-stu-id="e9e27-164">You use custom fields to extract specific data from the event logs.</span></span> <span data-ttu-id="e9e27-165">需要定义稍后用于磁贴、仪表板视图和警报的自定义字段。</span><span class="sxs-lookup"><span data-stu-id="e9e27-165">You need to define custom fields that will be used later with your tiles, dashboard views, and alerts.</span></span> <span data-ttu-id="e9e27-166">在开始[创建自定义字段 :::no-loc text="Log Analytics"::: ](/azure/azure-monitor/platform/custom-fields)之前，请参阅 中的自定义字段并熟悉相关概念。</span><span class="sxs-lookup"><span data-stu-id="e9e27-166">See [Custom fields in :::no-loc text="Log Analytics":::](/azure/azure-monitor/platform/custom-fields) and become familiar with the concepts before you start creating your custom fields.</span></span>

<span data-ttu-id="e9e27-167">若要从捕获的事件日志中提取自定义字段，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="e9e27-167">To extract your custom fields out of the captured event logs, follow these steps:</span></span>

1.  <span data-ttu-id="e9e27-168">登录到门户[ :::no-loc text="Microsoft Azure"::: ，](https://portal.azure.com)转到并选择 :::no-loc text="Log Analytics"::: 工作区。</span><span class="sxs-lookup"><span data-stu-id="e9e27-168">Sign in to the [:::no-loc text="Microsoft Azure"::: portal](https://portal.azure.com) and go to :::no-loc text="Log Analytics"::: and select your workspace.</span></span>

2. <span data-ttu-id="e9e27-169">列出设备生成的 :::no-loc text="Microsoft Teams Rooms"::: 事件：</span><span class="sxs-lookup"><span data-stu-id="e9e27-169">List the events generated by a :::no-loc text="Microsoft Teams Rooms"::: device:</span></span>
   1.  <span data-ttu-id="e9e27-170">转到 **"** 日志"并使用查询检索具有自定义字段的记录。</span><span class="sxs-lookup"><span data-stu-id="e9e27-170">Go to **Logs** and use a query to retrieve the records that will have the custom field.</span></span>
   2.  <span data-ttu-id="e9e27-171">示例查询： `Event | where Source == "SRS-App" and EventID == 2000`</span><span class="sxs-lookup"><span data-stu-id="e9e27-171">Sample query: `Event | where Source == "SRS-App" and EventID == 2000`</span></span>

3. <span data-ttu-id="e9e27-172">选择一条记录，选择左侧的按钮，然后启动字段提取向导。</span><span class="sxs-lookup"><span data-stu-id="e9e27-172">Select one of the records, select the button to the left, and start the field extraction wizard.</span></span>
4. <span data-ttu-id="e9e27-173">突出显示要从 RenderedDescription 提取的数据，并提供字段标题。</span><span class="sxs-lookup"><span data-stu-id="e9e27-173">Highlight the data you'd like to extract from the RenderedDescription and provide a Field Title.</span></span> <span data-ttu-id="e9e27-174">表 1 中提供了应该使用的字段名称。</span><span class="sxs-lookup"><span data-stu-id="e9e27-174">The field names that you should use are provided in Table 1.</span></span>
5. <span data-ttu-id="e9e27-175">使用表 *1 中所示的映射*。</span><span class="sxs-lookup"><span data-stu-id="e9e27-175">Use the mappings shown in *Table 1*.</span></span> <span data-ttu-id="e9e27-176">:::no-loc text="Log Analytics":::定义新字段时，会自动追加 **\_ CF** 字符串。</span><span class="sxs-lookup"><span data-stu-id="e9e27-176">:::no-loc text="Log Analytics"::: will automatically append the **\_CF** string when you define the new field.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e9e27-177">请记住，所有 JSON :::no-loc text="Log Analytics"::: 和字段都区分大小写。</span><span class="sxs-lookup"><span data-stu-id="e9e27-177">Remember that all JSON and :::no-loc text="Log Analytics"::: fields are case-sensitive.</span></span>
> 
> <span data-ttu-id="e9e27-178">请注意下表中每个自定义字段所需的查询。</span><span class="sxs-lookup"><span data-stu-id="e9e27-178">Pay attention to the queries required for each custom field in the table below.</span></span> <span data-ttu-id="e9e27-179">需要针对 使用正确的查询来 :::no-loc text="Log Analytics"::: 成功提取自定义字段值。</span><span class="sxs-lookup"><span data-stu-id="e9e27-179">You need to use the correct queries for :::no-loc text="Log Analytics"::: to successfully extract custom field values.</span></span>
> 
<span data-ttu-id="e9e27-180">**表 1**</span><span class="sxs-lookup"><span data-stu-id="e9e27-180">**Table 1**</span></span>

| <span data-ttu-id="e9e27-181">**JSON 字段**</span><span class="sxs-lookup"><span data-stu-id="e9e27-181">**JSON field**</span></span>                   | <span data-ttu-id="e9e27-182">**:::no-loc text="Log Analytics"::: 自定义字段**</span><span class="sxs-lookup"><span data-stu-id="e9e27-182">**:::no-loc text="Log Analytics"::: custom field**</span></span> | <span data-ttu-id="e9e27-183">**事件 ID**</span><span class="sxs-lookup"><span data-stu-id="e9e27-183">**Event ID**</span></span> | <span data-ttu-id="e9e27-184">**要与提取一起使用的查询**</span><span class="sxs-lookup"><span data-stu-id="e9e27-184">**Query to use with the extraction**</span></span>                   |
|:---------------------------------|:-------------------------------|:-------------|:-------------------------------------------------------|
| <span data-ttu-id="e9e27-185">说明</span><span class="sxs-lookup"><span data-stu-id="e9e27-185">Description</span></span>                      | <span data-ttu-id="e9e27-186">SRSEventDescription</span><span class="sxs-lookup"><span data-stu-id="e9e27-186">SRSEventDescription</span></span>         | <span data-ttu-id="e9e27-187">**2000**</span><span class="sxs-lookup"><span data-stu-id="e9e27-187">**2000**</span></span>     | <span data-ttu-id="e9e27-188">Source \| == "SRS-App" 和 EventID == 2000 的事件</span><span class="sxs-lookup"><span data-stu-id="e9e27-188">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="e9e27-189">ResourceState</span><span class="sxs-lookup"><span data-stu-id="e9e27-189">ResourceState</span></span>                    | <span data-ttu-id="e9e27-190">SRSResourceState</span><span class="sxs-lookup"><span data-stu-id="e9e27-190">SRSResourceState</span></span>            | <span data-ttu-id="e9e27-191">**2000**</span><span class="sxs-lookup"><span data-stu-id="e9e27-191">**2000**</span></span>     | <span data-ttu-id="e9e27-192">Source \| == "SRS-App" 和 EventID == 2000 的事件</span><span class="sxs-lookup"><span data-stu-id="e9e27-192">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="e9e27-193">OperationName</span><span class="sxs-lookup"><span data-stu-id="e9e27-193">OperationName</span></span>                    | <span data-ttu-id="e9e27-194">SRSOperationName</span><span class="sxs-lookup"><span data-stu-id="e9e27-194">SRSOperationName</span></span>            | <span data-ttu-id="e9e27-195">**2000**</span><span class="sxs-lookup"><span data-stu-id="e9e27-195">**2000**</span></span>     | <span data-ttu-id="e9e27-196">Source \| == "SRS-App" 和 EventID == 2000 的事件</span><span class="sxs-lookup"><span data-stu-id="e9e27-196">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="e9e27-197">OperationResult</span><span class="sxs-lookup"><span data-stu-id="e9e27-197">OperationResult</span></span>                  | <span data-ttu-id="e9e27-198">SRSOperationResult</span><span class="sxs-lookup"><span data-stu-id="e9e27-198">SRSOperationResult</span></span>          | <span data-ttu-id="e9e27-199">**2000**</span><span class="sxs-lookup"><span data-stu-id="e9e27-199">**2000**</span></span>     | <span data-ttu-id="e9e27-200">Source \| == "SRS-App" 和 EventID == 2000 的事件</span><span class="sxs-lookup"><span data-stu-id="e9e27-200">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="e9e27-201">OS</span><span class="sxs-lookup"><span data-stu-id="e9e27-201">OS</span></span>                               | <span data-ttu-id="e9e27-202">SRSOSVersion</span><span class="sxs-lookup"><span data-stu-id="e9e27-202">SRSOSVersion</span></span>                | <span data-ttu-id="e9e27-203">**2000**</span><span class="sxs-lookup"><span data-stu-id="e9e27-203">**2000**</span></span>     | <span data-ttu-id="e9e27-204">Source \| == "SRS-App" 和 EventID == 2000 的事件</span><span class="sxs-lookup"><span data-stu-id="e9e27-204">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="e9e27-205">OSVersion</span><span class="sxs-lookup"><span data-stu-id="e9e27-205">OSVersion</span></span>                        | <span data-ttu-id="e9e27-206">SRSOSLongVersion</span><span class="sxs-lookup"><span data-stu-id="e9e27-206">SRSOSLongVersion</span></span>            | <span data-ttu-id="e9e27-207">**2000**</span><span class="sxs-lookup"><span data-stu-id="e9e27-207">**2000**</span></span>     | <span data-ttu-id="e9e27-208">Source \| == "SRS-App" 和 EventID == 2000 的事件</span><span class="sxs-lookup"><span data-stu-id="e9e27-208">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="e9e27-209">别名</span><span class="sxs-lookup"><span data-stu-id="e9e27-209">Alias</span></span>                            | <span data-ttu-id="e9e27-210">SRSAlias</span><span class="sxs-lookup"><span data-stu-id="e9e27-210">SRSAlias</span></span>                    | <span data-ttu-id="e9e27-211">**2000**</span><span class="sxs-lookup"><span data-stu-id="e9e27-211">**2000**</span></span>     | <span data-ttu-id="e9e27-212">Source \| == "SRS-App" 和 EventID == 2000 的事件</span><span class="sxs-lookup"><span data-stu-id="e9e27-212">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="e9e27-213">DisplayName</span><span class="sxs-lookup"><span data-stu-id="e9e27-213">DisplayName</span></span>                      | <span data-ttu-id="e9e27-214">SRSDisplayName</span><span class="sxs-lookup"><span data-stu-id="e9e27-214">SRSDisplayName</span></span>              | <span data-ttu-id="e9e27-215">**2000**</span><span class="sxs-lookup"><span data-stu-id="e9e27-215">**2000**</span></span>     | <span data-ttu-id="e9e27-216">Source \| == "SRS-App" 和 EventID == 2000 的事件</span><span class="sxs-lookup"><span data-stu-id="e9e27-216">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="e9e27-217">AppVersion</span><span class="sxs-lookup"><span data-stu-id="e9e27-217">AppVersion</span></span>                       | <span data-ttu-id="e9e27-218">SRSAppVersion</span><span class="sxs-lookup"><span data-stu-id="e9e27-218">SRSAppVersion</span></span>               | <span data-ttu-id="e9e27-219">**2000**</span><span class="sxs-lookup"><span data-stu-id="e9e27-219">**2000**</span></span>     | <span data-ttu-id="e9e27-220">Source \| == "SRS-App" 和 EventID == 2000 的事件</span><span class="sxs-lookup"><span data-stu-id="e9e27-220">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="e9e27-221">IPv4Address</span><span class="sxs-lookup"><span data-stu-id="e9e27-221">IPv4Address</span></span>                      | <span data-ttu-id="e9e27-222">SRSIPv4Address</span><span class="sxs-lookup"><span data-stu-id="e9e27-222">SRSIPv4Address</span></span>              | <span data-ttu-id="e9e27-223">**2000**</span><span class="sxs-lookup"><span data-stu-id="e9e27-223">**2000**</span></span>     | <span data-ttu-id="e9e27-224">Source \| == "SRS-App" 和 EventID == 2000 的事件</span><span class="sxs-lookup"><span data-stu-id="e9e27-224">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="e9e27-225">IPv6Address</span><span class="sxs-lookup"><span data-stu-id="e9e27-225">IPv6Address</span></span>                      | <span data-ttu-id="e9e27-226">SRSIPv6Address</span><span class="sxs-lookup"><span data-stu-id="e9e27-226">SRSIPv6Address</span></span>              | <span data-ttu-id="e9e27-227">**2000**</span><span class="sxs-lookup"><span data-stu-id="e9e27-227">**2000**</span></span>     | <span data-ttu-id="e9e27-228">Source \| == "SRS-App" 和 EventID == 2000 的事件</span><span class="sxs-lookup"><span data-stu-id="e9e27-228">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="e9e27-229">会议麦克风状态</span><span class="sxs-lookup"><span data-stu-id="e9e27-229">Conference Microphone status</span></span>     | <span data-ttu-id="e9e27-230">SRSConfMicrophoneStatus</span><span class="sxs-lookup"><span data-stu-id="e9e27-230">SRSConfMicrophoneStatus</span></span>     | <span data-ttu-id="e9e27-231">**3001**</span><span class="sxs-lookup"><span data-stu-id="e9e27-231">**3001**</span></span>     | <span data-ttu-id="e9e27-232">Source \| == "SRS-App" 和 EventID == 3001 的事件</span><span class="sxs-lookup"><span data-stu-id="e9e27-232">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="e9e27-233">会议发言人状态</span><span class="sxs-lookup"><span data-stu-id="e9e27-233">Conference Speaker status</span></span>        | <span data-ttu-id="e9e27-234">SRSConfSpeakerStatus</span><span class="sxs-lookup"><span data-stu-id="e9e27-234">SRSConfSpeakerStatus</span></span>        | <span data-ttu-id="e9e27-235">**3001**</span><span class="sxs-lookup"><span data-stu-id="e9e27-235">**3001**</span></span>     | <span data-ttu-id="e9e27-236">Source \| == "SRS-App" 和 EventID == 3001 的事件</span><span class="sxs-lookup"><span data-stu-id="e9e27-236">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="e9e27-237">默认发言人状态</span><span class="sxs-lookup"><span data-stu-id="e9e27-237">Default Speaker status</span></span>           | <span data-ttu-id="e9e27-238">SRSDefaultSpeakerStatus</span><span class="sxs-lookup"><span data-stu-id="e9e27-238">SRSDefaultSpeakerStatus</span></span>     | <span data-ttu-id="e9e27-239">**3001**</span><span class="sxs-lookup"><span data-stu-id="e9e27-239">**3001**</span></span>     | <span data-ttu-id="e9e27-240">Source \| == "SRS-App" 和 EventID == 3001 的事件</span><span class="sxs-lookup"><span data-stu-id="e9e27-240">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="e9e27-241">相机状态</span><span class="sxs-lookup"><span data-stu-id="e9e27-241">Camera status</span></span>                    | <span data-ttu-id="e9e27-242">SRSCameraStatus</span><span class="sxs-lookup"><span data-stu-id="e9e27-242">SRSCameraStatus</span></span>             | <span data-ttu-id="e9e27-243">**3001**</span><span class="sxs-lookup"><span data-stu-id="e9e27-243">**3001**</span></span>     | <span data-ttu-id="e9e27-244">Source \| == "SRS-App" 和 EventID == 3001 的事件</span><span class="sxs-lookup"><span data-stu-id="e9e27-244">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="e9e27-245">会议室显示状态前</span><span class="sxs-lookup"><span data-stu-id="e9e27-245">Front of Room Display status</span></span>     | <span data-ttu-id="e9e27-246">SRSFORDStatus</span><span class="sxs-lookup"><span data-stu-id="e9e27-246">SRSFORDStatus</span></span>               | <span data-ttu-id="e9e27-247">**3001**</span><span class="sxs-lookup"><span data-stu-id="e9e27-247">**3001**</span></span>     | <span data-ttu-id="e9e27-248">Source \| == "SRS-App" 和 EventID == 3001 的事件</span><span class="sxs-lookup"><span data-stu-id="e9e27-248">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="e9e27-249">运动传感器状态</span><span class="sxs-lookup"><span data-stu-id="e9e27-249">Motion Sensor status</span></span>             | <span data-ttu-id="e9e27-250">SRSMotionSensorStatus</span><span class="sxs-lookup"><span data-stu-id="e9e27-250">SRSMotionSensorStatus</span></span>       | <span data-ttu-id="e9e27-251">**3001**</span><span class="sxs-lookup"><span data-stu-id="e9e27-251">**3001**</span></span>     | <span data-ttu-id="e9e27-252">Source \| == "SRS-App" 和 EventID == 3001 的事件</span><span class="sxs-lookup"><span data-stu-id="e9e27-252">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="e9e27-253">HDMI Ingest 状态</span><span class="sxs-lookup"><span data-stu-id="e9e27-253">HDMI Ingest status</span></span>               | <span data-ttu-id="e9e27-254">SRSHDMIIngestStatus</span><span class="sxs-lookup"><span data-stu-id="e9e27-254">SRSHDMIIngestStatus</span></span>         | <span data-ttu-id="e9e27-255">**3001**</span><span class="sxs-lookup"><span data-stu-id="e9e27-255">**3001**</span></span>     | <span data-ttu-id="e9e27-256">Source \| == "SRS-App" 和 EventID == 3001 的事件</span><span class="sxs-lookup"><span data-stu-id="e9e27-256">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |


## <a name="define-the-no-loc-textmicrosoft-teams-rooms-views-in-no-loc-textlog-analytics"></a><span data-ttu-id="e9e27-257">在 :::no-loc text="Microsoft Teams Rooms"::: 中定义视图 :::no-loc text="Log Analytics":::</span><span class="sxs-lookup"><span data-stu-id="e9e27-257">Define the :::no-loc text="Microsoft Teams Rooms"::: views in :::no-loc text="Log Analytics":::</span></span>
<span data-ttu-id="e9e27-258"><a name="Define_Views"> </a></span><span class="sxs-lookup"><span data-stu-id="e9e27-258"><a name="Define_Views"> </a></span></span>

<span data-ttu-id="e9e27-259">收集数据并映射自定义字段后，可以使用视图设计器开发包含各种磁贴的仪表板来监视 :::no-loc text="Microsoft Teams Rooms"::: 事件。</span><span class="sxs-lookup"><span data-stu-id="e9e27-259">After data is collected and custom fields are mapped, you can use View Designer to develop a dashboard containing various tiles to monitor :::no-loc text="Microsoft Teams Rooms"::: events.</span></span> <span data-ttu-id="e9e27-260">使用视图设计器创建以下磁贴。</span><span class="sxs-lookup"><span data-stu-id="e9e27-260">Use View Designer to create the following tiles.</span></span> <span data-ttu-id="e9e27-261">有关详细信息，请参阅中的[使用视图设计器创建自定义视图 :::no-loc text="Log Analytics"::: ](/azure/azure-monitor/platform/view-designer)</span><span class="sxs-lookup"><span data-stu-id="e9e27-261">For more information, see [Create custom views by using View Designer in :::no-loc text="Log Analytics":::](/azure/azure-monitor/platform/view-designer)</span></span>

> [!NOTE]
> <span data-ttu-id="e9e27-262">本指南中的先前步骤应已完成，仪表板磁贴应能正常工作。</span><span class="sxs-lookup"><span data-stu-id="e9e27-262">Previous steps in this guide should have been completed for the dashboard tiles to work properly.</span></span>

### <a name="create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method"></a><span data-ttu-id="e9e27-263">使用导入方法创建 Microsoft Teams 会议室仪表板</span><span class="sxs-lookup"><span data-stu-id="e9e27-263">Create a Microsoft Teams Rooms dashboard by using the import method</span></span>

<span data-ttu-id="e9e27-264">可以导入 :::no-loc text="Microsoft Teams Rooms"::: 仪表板并开始快速监视设备。</span><span class="sxs-lookup"><span data-stu-id="e9e27-264">You can import an :::no-loc text="Microsoft Teams Rooms"::: dashboard and start monitoring your devices quickly.</span></span> <span data-ttu-id="e9e27-265">执行以下步骤导入仪表板：</span><span class="sxs-lookup"><span data-stu-id="e9e27-265">Take the following steps to import the dashboard:</span></span>

1.  <span data-ttu-id="e9e27-266">获取 [SkypeRoomSystems_v2.omsview](https://go.microsoft.com/fwlink/?linkid=835675) 仪表板文件。</span><span class="sxs-lookup"><span data-stu-id="e9e27-266">Get the [SkypeRoomSystems_v2.omsview](https://go.microsoft.com/fwlink/?linkid=835675) dashboard file.</span></span>
2.  <span data-ttu-id="e9e27-267">登录到门户[ :::no-loc text="Microsoft Azure"::: ，](https://portal.azure.com)转到并选择 :::no-loc text="Log Analytics"::: 工作区。</span><span class="sxs-lookup"><span data-stu-id="e9e27-267">Sign in to the [:::no-loc text="Microsoft Azure"::: portal](https://portal.azure.com) and go to :::no-loc text="Log Analytics"::: and select your workspace.</span></span>
3.  <span data-ttu-id="e9e27-268">打开 **"视图设计器"。**</span><span class="sxs-lookup"><span data-stu-id="e9e27-268">Open **View Designer**.</span></span>
4.  <span data-ttu-id="e9e27-269">选择 **"导入**"，然后选择 **SkypeRoomSystems_v2.omsview** 文件。</span><span class="sxs-lookup"><span data-stu-id="e9e27-269">Select **Import**, and then select the **SkypeRoomSystems_v2.omsview** file.</span></span>
5.  <span data-ttu-id="e9e27-270">选择"**保存"。**</span><span class="sxs-lookup"><span data-stu-id="e9e27-270">Select **Save**.</span></span>

### <a name="create-a-microsoft-teams-rooms-dashboard-manually"></a><span data-ttu-id="e9e27-271">手动创建 Microsoft Teams 会议室仪表板</span><span class="sxs-lookup"><span data-stu-id="e9e27-271">Create a Microsoft Teams Rooms dashboard manually</span></span>

<span data-ttu-id="e9e27-272">或者，你可以创建自己的仪表板并仅添加要监视的磁贴。</span><span class="sxs-lookup"><span data-stu-id="e9e27-272">Alternatively, you can create your own dashboard and add only the tiles that you wish to monitor.</span></span>

#### <a name="configure-the-overview-tile"></a><span data-ttu-id="e9e27-273">配置"概述"磁贴</span><span class="sxs-lookup"><span data-stu-id="e9e27-273">Configure the Overview Tile</span></span>

1.  <span data-ttu-id="e9e27-274">打开 **"视图设计器"。**</span><span class="sxs-lookup"><span data-stu-id="e9e27-274">Open **View Designer**.</span></span>
2.  <span data-ttu-id="e9e27-275">选择 **"概述磁贴**"，然后 **从库中选择** "两个数字"。</span><span class="sxs-lookup"><span data-stu-id="e9e27-275">Select **Overview Tile**, and then select **Two numbers** from the gallery.</span></span>
3.  <span data-ttu-id="e9e27-276">将磁贴命名 **:::no-loc text="Microsoft Teams Rooms":::** 。</span><span class="sxs-lookup"><span data-stu-id="e9e27-276">Name the tile **:::no-loc text="Microsoft Teams Rooms":::**.</span></span>
4.  <span data-ttu-id="e9e27-277">定义第 **一个磁贴**：</span><span class="sxs-lookup"><span data-stu-id="e9e27-277">Define the **First Tile**:</span></span><br>
    <span data-ttu-id="e9e27-278">**图例：** 在上个月至少发送了一次检测信号的设备</span><span class="sxs-lookup"><span data-stu-id="e9e27-278">**Legend:** Devices that sent a heartbeat at least once within the last month</span></span><br>
    <span data-ttu-id="e9e27-279">**查询：**```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```</span><span class="sxs-lookup"><span data-stu-id="e9e27-279">**Query:** ```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```</span></span>
5.  <span data-ttu-id="e9e27-280">定义第 **二个磁贴**：</span><span class="sxs-lookup"><span data-stu-id="e9e27-280">Define the **Second Tile**:</span></span><br>
    <span data-ttu-id="e9e27-281">**图例：** 过去一小时内发送检测信号的活动设备</span><span class="sxs-lookup"><span data-stu-id="e9e27-281">**Legend:** Active devices that sent a heartbeat within the last hour</span></span><br>
    <span data-ttu-id="e9e27-282">**查询：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```</span><span class="sxs-lookup"><span data-stu-id="e9e27-282">**Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```</span></span>
6.  <span data-ttu-id="e9e27-283">选择"**应用"。**</span><span class="sxs-lookup"><span data-stu-id="e9e27-283">Select **Apply**.</span></span>

### <a name="create-a-tile-that-displays-active-devices"></a><span data-ttu-id="e9e27-284">创建显示活动设备的磁贴</span><span class="sxs-lookup"><span data-stu-id="e9e27-284">Create a tile that displays active devices</span></span>

1.  <span data-ttu-id="e9e27-285">选择 **"查看仪表板** "开始添加磁贴。</span><span class="sxs-lookup"><span data-stu-id="e9e27-285">Select **View Dashboard** to start adding your tiles.</span></span>
2.  <span data-ttu-id="e9e27-286">从 **库中&** 数字"列表</span><span class="sxs-lookup"><span data-stu-id="e9e27-286">Select **Number & list** from the gallery</span></span>
3.  <span data-ttu-id="e9e27-287">定义 **"常规"** 属性：</span><span class="sxs-lookup"><span data-stu-id="e9e27-287">Define the **General** properties:</span></span><br>
    <span data-ttu-id="e9e27-288">**组标题：** 检测信号状态</span><span class="sxs-lookup"><span data-stu-id="e9e27-288">**Group Title:** Heartbeat Status</span></span><br>
    <span data-ttu-id="e9e27-289">**新建组：** 已选择</span><span class="sxs-lookup"><span data-stu-id="e9e27-289">**New Group:** Selected</span></span>
4.  <span data-ttu-id="e9e27-290">定义 **磁贴** 属性：</span><span class="sxs-lookup"><span data-stu-id="e9e27-290">Define the **Tile** properties:</span></span><br>
    <span data-ttu-id="e9e27-291">**图例：** 活动设备 (最近 20 分钟内发送的检测信号) </span><span class="sxs-lookup"><span data-stu-id="e9e27-291">**Legend:** Active devices (heartbeat sent in the last 20 minutes)</span></span><br>
    <span data-ttu-id="e9e27-292">**图块查询：** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```</span><span class="sxs-lookup"><span data-stu-id="e9e27-292">**Tile Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```</span></span>
5.  <span data-ttu-id="e9e27-293">定义 **列表** 属性：</span><span class="sxs-lookup"><span data-stu-id="e9e27-293">Define the **List** properties:</span></span><br>
    <span data-ttu-id="e9e27-294">**列表查询：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span><span class="sxs-lookup"><span data-stu-id="e9e27-294">**List Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span></span>
6.  <span data-ttu-id="e9e27-295">定义 **列标题**：</span><span class="sxs-lookup"><span data-stu-id="e9e27-295">Define **Column Titles**:</span></span><br>
    <span data-ttu-id="e9e27-296">**名称：** 计算机名称</span><span class="sxs-lookup"><span data-stu-id="e9e27-296">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="e9e27-297">**值：** 上次检测信号</span><span class="sxs-lookup"><span data-stu-id="e9e27-297">**Value:** Last Heartbeat</span></span>
7.  <span data-ttu-id="e9e27-298">定义 **导航查询**。</span><span class="sxs-lookup"><span data-stu-id="e9e27-298">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  <span data-ttu-id="e9e27-299">选择 **"应用"，** 然后选择"**关闭"。**</span><span class="sxs-lookup"><span data-stu-id="e9e27-299">Select **Apply**, and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-devices-that-have-connectivity-issues"></a><span data-ttu-id="e9e27-300">创建一个磁贴，用于显示有连接问题的设备</span><span class="sxs-lookup"><span data-stu-id="e9e27-300">Create a tile that displays devices that have connectivity issues</span></span>

1.  <span data-ttu-id="e9e27-301">从 **库中&"** 数字"列表，然后添加新磁贴。</span><span class="sxs-lookup"><span data-stu-id="e9e27-301">Select **Number & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="e9e27-302">定义 **"常规"** 属性：</span><span class="sxs-lookup"><span data-stu-id="e9e27-302">Define the **General** properties:</span></span><br>
    <span data-ttu-id="e9e27-303">**组标题：** 留空</span><span class="sxs-lookup"><span data-stu-id="e9e27-303">**Group Title:** Leave empty</span></span><br>
    <span data-ttu-id="e9e27-304">**新建组：** 未选中</span><span class="sxs-lookup"><span data-stu-id="e9e27-304">**New Group:** Not Selected</span></span>
3.  <span data-ttu-id="e9e27-305">定义 **磁贴** 属性：</span><span class="sxs-lookup"><span data-stu-id="e9e27-305">Define the **Tile** properties:</span></span><br>
    <span data-ttu-id="e9e27-306">**图例：** 非活动设备 (最近 20 分钟内未发送任何检测信号) </span><span class="sxs-lookup"><span data-stu-id="e9e27-306">**Legend:** Inactive Devices (no heartbeat message sent in the last 20 minutes)</span></span><br>
    <span data-ttu-id="e9e27-307">**图块查询：** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```</span><span class="sxs-lookup"><span data-stu-id="e9e27-307">**Tile Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```</span></span>
4.  <span data-ttu-id="e9e27-308">定义 **列表** 属性：</span><span class="sxs-lookup"><span data-stu-id="e9e27-308">Define the **List** properties:</span></span><br>
    <span data-ttu-id="e9e27-309">**列表查询：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```</span><span class="sxs-lookup"><span data-stu-id="e9e27-309">**List Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```</span></span>
5.  <span data-ttu-id="e9e27-310">定义 **列标题**：</span><span class="sxs-lookup"><span data-stu-id="e9e27-310">Define **Column Titles**:</span></span><br>
    <span data-ttu-id="e9e27-311">**名称：** 计算机名称</span><span class="sxs-lookup"><span data-stu-id="e9e27-311">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="e9e27-312">**值：** 上次检测信号</span><span class="sxs-lookup"><span data-stu-id="e9e27-312">**Value:** Last Heartbeat</span></span>
6.  <span data-ttu-id="e9e27-313">定义 **导航查询**：</span><span class="sxs-lookup"><span data-stu-id="e9e27-313">Define **Navigation Query**:</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  <span data-ttu-id="e9e27-314">选择 **"应用"，** 然后选择"**关闭"。**</span><span class="sxs-lookup"><span data-stu-id="e9e27-314">Select **Apply**, and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-devices-that-have-a-hardware-error"></a><span data-ttu-id="e9e27-315">创建一个磁贴，用于显示出现硬件错误的设备</span><span class="sxs-lookup"><span data-stu-id="e9e27-315">Create a tile that displays devices that have a hardware error</span></span>

1.  <span data-ttu-id="e9e27-316">从 **库中&"** 数字"列表，然后添加新磁贴。</span><span class="sxs-lookup"><span data-stu-id="e9e27-316">Select **Number & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="e9e27-317">定义 **"常规"** 属性：</span><span class="sxs-lookup"><span data-stu-id="e9e27-317">Define the **General** properties:</span></span><br>
    <span data-ttu-id="e9e27-318">**组标题：** 硬件状态</span><span class="sxs-lookup"><span data-stu-id="e9e27-318">**Group Title:** Hardware Status</span></span><br>
    <span data-ttu-id="e9e27-319">**新建组：** 已选择</span><span class="sxs-lookup"><span data-stu-id="e9e27-319">**New Group:** Selected</span></span>
3.  <span data-ttu-id="e9e27-320">定义 **磁贴** 属性：</span><span class="sxs-lookup"><span data-stu-id="e9e27-320">Define the **Tile** properties:</span></span><br>
    <span data-ttu-id="e9e27-321">**图例：** 过去一小时内遇到硬件错误的设备</span><span class="sxs-lookup"><span data-stu-id="e9e27-321">**Legend:** Devices that experienced a hardware error in the last hour</span></span><br>
    <span data-ttu-id="e9e27-322">**图块查询：** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```</span><span class="sxs-lookup"><span data-stu-id="e9e27-322">**Tile Query:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```</span></span>
4.  <span data-ttu-id="e9e27-323">定义 **列表** 属性：</span><span class="sxs-lookup"><span data-stu-id="e9e27-323">Define the **List** properties:</span></span><br>
    <span data-ttu-id="e9e27-324">**列表查询：**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span><span class="sxs-lookup"><span data-stu-id="e9e27-324">**List Query:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span></span>
5.  <span data-ttu-id="e9e27-325">定义 **列标题**：</span><span class="sxs-lookup"><span data-stu-id="e9e27-325">Define **Column Titles**:</span></span><br>
    <span data-ttu-id="e9e27-326">**名称：** 计算机名称</span><span class="sxs-lookup"><span data-stu-id="e9e27-326">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="e9e27-327">**值：** 上次错误</span><span class="sxs-lookup"><span data-stu-id="e9e27-327">**Value:** Last Error</span></span>
6.  <span data-ttu-id="e9e27-328">定义 **导航查询**：</span><span class="sxs-lookup"><span data-stu-id="e9e27-328">Define **Navigation Query**:</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 3001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  <span data-ttu-id="e9e27-329">选择 **"应用"，** 然后选择"**关闭"。**</span><span class="sxs-lookup"><span data-stu-id="e9e27-329">Select **Apply**, and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-operating-system-versions"></a><span data-ttu-id="e9e27-330">创建显示 :::no-loc text="Microsoft Teams Rooms"::: 操作系统版本的磁贴</span><span class="sxs-lookup"><span data-stu-id="e9e27-330">Create a tile that displays :::no-loc text="Microsoft Teams Rooms"::: Operating System versions</span></span>

1.  <span data-ttu-id="e9e27-331">从 **库中&"** 按钮"，然后添加新磁贴。</span><span class="sxs-lookup"><span data-stu-id="e9e27-331">Select **Donut & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="e9e27-332">定义 **"常规"** 属性：</span><span class="sxs-lookup"><span data-stu-id="e9e27-332">Define the **General** properties:</span></span><br>
    <span data-ttu-id="e9e27-333">**组标题：** 操作系统详细信息</span><span class="sxs-lookup"><span data-stu-id="e9e27-333">**Group Title:** Operating System details</span></span><br>
    <span data-ttu-id="e9e27-334">**新建组：** 已选择</span><span class="sxs-lookup"><span data-stu-id="e9e27-334">**New Group:** Selected</span></span>
3.  <span data-ttu-id="e9e27-335">定义 **标头** 属性：</span><span class="sxs-lookup"><span data-stu-id="e9e27-335">Define the **Header** properties:</span></span><br>
    <span data-ttu-id="e9e27-336">**标题：** 操作系统版本</span><span class="sxs-lookup"><span data-stu-id="e9e27-336">**Title:** Operating System versions</span></span><br>
    <span data-ttu-id="e9e27-337">**副标题：** 运行特定 OS 版本的设备</span><span class="sxs-lookup"><span data-stu-id="e9e27-337">**Subtitle:** Devices running specific OS versions</span></span>
4.  <span data-ttu-id="e9e27-338">定义 **Donut** 属性：</span><span class="sxs-lookup"><span data-stu-id="e9e27-338">Define the **Donut** properties:</span></span><br>
    <span data-ttu-id="e9e27-339">**查询：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize OS_Version = max(SRSOSLongVersion_CF) by Computer | summarize AggregatedValue = count() by OS_Version | sort by OS_Version asc```</span><span class="sxs-lookup"><span data-stu-id="e9e27-339">**Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize OS_Version = max(SRSOSLongVersion_CF) by Computer | summarize AggregatedValue = count() by OS_Version | sort by OS_Version asc```</span></span><br>
    <span data-ttu-id="e9e27-340">**居中文本：** 设备</span><span class="sxs-lookup"><span data-stu-id="e9e27-340">**Center Text:** Devices</span></span><br>
    <span data-ttu-id="e9e27-341">**操作：** 总和</span><span class="sxs-lookup"><span data-stu-id="e9e27-341">**Operation:** Sum</span></span>
5.  <span data-ttu-id="e9e27-342">定义 **列表** 属性。</span><span class="sxs-lookup"><span data-stu-id="e9e27-342">Define the **List** properties.</span></span><br>
    <span data-ttu-id="e9e27-343">**列表查询：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSOSLongVersion_CF = max(SRSOSLongVersion_CF) by Computer | sort by Computer asc```</span><span class="sxs-lookup"><span data-stu-id="e9e27-343">**List Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSOSLongVersion_CF = max(SRSOSLongVersion_CF) by Computer | sort by Computer asc```</span></span><br>
    <span data-ttu-id="e9e27-344">**隐藏图形：** 已选择</span><span class="sxs-lookup"><span data-stu-id="e9e27-344">**Hide Graph:** Selected</span></span><br>
    <span data-ttu-id="e9e27-345">**启用迷你图：** 未选中</span><span class="sxs-lookup"><span data-stu-id="e9e27-345">**Enable Sparklines:** Not selected</span></span>
6.  <span data-ttu-id="e9e27-346">定义 **列标题**。</span><span class="sxs-lookup"><span data-stu-id="e9e27-346">Define **Column Titles**.</span></span><br>
    <span data-ttu-id="e9e27-347">**名称：** 计算机名称</span><span class="sxs-lookup"><span data-stu-id="e9e27-347">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="e9e27-348">**值：** 留空</span><span class="sxs-lookup"><span data-stu-id="e9e27-348">**Value:** Leave Empty</span></span>
7.  <span data-ttu-id="e9e27-349">定义 **导航查询**。</span><span class="sxs-lookup"><span data-stu-id="e9e27-349">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  <span data-ttu-id="e9e27-350">选择 **"应用"，** 然后选择"**关闭"。**</span><span class="sxs-lookup"><span data-stu-id="e9e27-350">Select **Apply** and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-application-versions"></a><span data-ttu-id="e9e27-351">创建显示应用程序 :::no-loc text="Microsoft Teams Rooms"::: 版本的磁贴</span><span class="sxs-lookup"><span data-stu-id="e9e27-351">Create a tile that displays :::no-loc text="Microsoft Teams Rooms"::: application versions</span></span>

1.  <span data-ttu-id="e9e27-352">从 **库中&"** 按钮"，然后添加新磁贴。</span><span class="sxs-lookup"><span data-stu-id="e9e27-352">Select **Donut & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="e9e27-353">定义 **"常规"** 属性：</span><span class="sxs-lookup"><span data-stu-id="e9e27-353">Define the **General** properties:</span></span><br>
    <span data-ttu-id="e9e27-354">**组标题：** :::no-loc text="Microsoft Teams Rooms"::: 应用程序详细信息</span><span class="sxs-lookup"><span data-stu-id="e9e27-354">**Group Title:** :::no-loc text="Microsoft Teams Rooms"::: application details</span></span><br>
    <span data-ttu-id="e9e27-355">**新建组：** 已选择</span><span class="sxs-lookup"><span data-stu-id="e9e27-355">**New Group:** Selected</span></span>
3.  <span data-ttu-id="e9e27-356">定义 **标头** 属性：</span><span class="sxs-lookup"><span data-stu-id="e9e27-356">Define the **Header** properties:</span></span><br>
    <span data-ttu-id="e9e27-357">**标题：** 应用程序版本</span><span class="sxs-lookup"><span data-stu-id="e9e27-357">**Title:** Application versions</span></span><br>
    <span data-ttu-id="e9e27-358">**副标题：** 运行特定应用程序版本的设备</span><span class="sxs-lookup"><span data-stu-id="e9e27-358">**Subtitle:** Devices running specific application versions</span></span>
4.  <span data-ttu-id="e9e27-359">定义 **Donut** 属性：</span><span class="sxs-lookup"><span data-stu-id="e9e27-359">Define the **Donut** properties:</span></span><br>
    <span data-ttu-id="e9e27-360">**查询：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```</span><span class="sxs-lookup"><span data-stu-id="e9e27-360">**Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```</span></span><br>
    <span data-ttu-id="e9e27-361">**居中文本：** 设备</span><span class="sxs-lookup"><span data-stu-id="e9e27-361">**Center Text:** Devices</span></span><br>
    <span data-ttu-id="e9e27-362">**操作：** 总和</span><span class="sxs-lookup"><span data-stu-id="e9e27-362">**Operation:** Sum</span></span>
5.  <span data-ttu-id="e9e27-363">定义 **列表** 属性。</span><span class="sxs-lookup"><span data-stu-id="e9e27-363">Define the **List** properties.</span></span><br>
    <span data-ttu-id="e9e27-364">**列表查询：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```</span><span class="sxs-lookup"><span data-stu-id="e9e27-364">**List Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```</span></span><br>
    <span data-ttu-id="e9e27-365">**隐藏图形：** 已选择</span><span class="sxs-lookup"><span data-stu-id="e9e27-365">**Hide Graph:** Selected</span></span><br>
    <span data-ttu-id="e9e27-366">**启用迷你图：** 未选中</span><span class="sxs-lookup"><span data-stu-id="e9e27-366">**Enable Sparklines:** Not selected</span></span>
6.  <span data-ttu-id="e9e27-367">定义 **列标题**。</span><span class="sxs-lookup"><span data-stu-id="e9e27-367">Define **Column Titles**.</span></span><br>
    <span data-ttu-id="e9e27-368">**名称：** 计算机名称</span><span class="sxs-lookup"><span data-stu-id="e9e27-368">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="e9e27-369">**值：** 留空</span><span class="sxs-lookup"><span data-stu-id="e9e27-369">**Value:** Leave Empty</span></span>
7.  <span data-ttu-id="e9e27-370">定义 **导航查询**。</span><span class="sxs-lookup"><span data-stu-id="e9e27-370">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  <span data-ttu-id="e9e27-371">选择 **"应用"，** 然后选择"**关闭"。**</span><span class="sxs-lookup"><span data-stu-id="e9e27-371">Select **Apply** and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-devices-that-have-an-application-error"></a><span data-ttu-id="e9e27-372">创建一个磁贴，用于显示具有应用程序错误的设备</span><span class="sxs-lookup"><span data-stu-id="e9e27-372">Create a tile that displays devices that have an application error</span></span>

1.  <span data-ttu-id="e9e27-373">从 **库中&"** 数字"列表，然后添加新磁贴。</span><span class="sxs-lookup"><span data-stu-id="e9e27-373">Select **Number & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="e9e27-374">定义 **"常规"** 属性。</span><span class="sxs-lookup"><span data-stu-id="e9e27-374">Define the **General** properties.</span></span><br>
    <span data-ttu-id="e9e27-375">**组标题：** 留空</span><span class="sxs-lookup"><span data-stu-id="e9e27-375">**Group Title:** Leave empty</span></span><br>
    <span data-ttu-id="e9e27-376">**新建组：** 未选中</span><span class="sxs-lookup"><span data-stu-id="e9e27-376">**New Group:** Not Selected</span></span>
3.  <span data-ttu-id="e9e27-377">定义 **磁贴** 属性。</span><span class="sxs-lookup"><span data-stu-id="e9e27-377">Define the **Tile** properties.</span></span><br>
    <span data-ttu-id="e9e27-378">**图例：** 过去一小时内遇到应用程序错误的设备</span><span class="sxs-lookup"><span data-stu-id="e9e27-378">**Legend:** Devices that experienced an application error in the last hour</span></span><br>
    <span data-ttu-id="e9e27-379">**图块查询：** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```</span><span class="sxs-lookup"><span data-stu-id="e9e27-379">**Tile Query:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```</span></span>
4.  <span data-ttu-id="e9e27-380">定义 **列表** 属性。</span><span class="sxs-lookup"><span data-stu-id="e9e27-380">Define the **List** properties.</span></span><br>
    <span data-ttu-id="e9e27-381">**列表查询：**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span><span class="sxs-lookup"><span data-stu-id="e9e27-381">**List Query:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span></span>
5.  <span data-ttu-id="e9e27-382">定义 **列标题**。</span><span class="sxs-lookup"><span data-stu-id="e9e27-382">Define **Column Titles**.</span></span><br>
    <span data-ttu-id="e9e27-383">**名称：** 计算机名称</span><span class="sxs-lookup"><span data-stu-id="e9e27-383">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="e9e27-384">**值：** 上次错误</span><span class="sxs-lookup"><span data-stu-id="e9e27-384">**Value:** Last Error</span></span>
6.  <span data-ttu-id="e9e27-385">定义 **导航查询**。</span><span class="sxs-lookup"><span data-stu-id="e9e27-385">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 2001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  <span data-ttu-id="e9e27-386">选择 **"应用"，** 然后选择"**关闭"。**</span><span class="sxs-lookup"><span data-stu-id="e9e27-386">Select **Apply** and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-devices-that-have-been-restarted"></a><span data-ttu-id="e9e27-387">创建一个磁贴，用于显示已重启的设备</span><span class="sxs-lookup"><span data-stu-id="e9e27-387">Create a tile that displays devices that have been restarted</span></span>

1.  <span data-ttu-id="e9e27-388">从 **库中&"** 数字"列表，然后添加新磁贴。</span><span class="sxs-lookup"><span data-stu-id="e9e27-388">Select **Number & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="e9e27-389">定义 **"常规"** 属性。</span><span class="sxs-lookup"><span data-stu-id="e9e27-389">Define the **General** properties.</span></span><br>
    <span data-ttu-id="e9e27-390">**组标题：** 留空</span><span class="sxs-lookup"><span data-stu-id="e9e27-390">**Group Title:** Leave empty</span></span><br>
    <span data-ttu-id="e9e27-391">**新建组：** 未选中</span><span class="sxs-lookup"><span data-stu-id="e9e27-391">**New Group:** Not Selected</span></span>
3.  <span data-ttu-id="e9e27-392">定义 **磁贴** 属性。</span><span class="sxs-lookup"><span data-stu-id="e9e27-392">Define the **Tile** properties.</span></span><br>
    <span data-ttu-id="e9e27-393">**图例：** 过去 24 小时内重启应用程序的设备，以及重启次数</span><span class="sxs-lookup"><span data-stu-id="e9e27-393">**Legend:** Devices where the application was restarted in the last 24 hours, and number of restarts</span></span><br>
    <span data-ttu-id="e9e27-394">**图块查询：** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```</span><span class="sxs-lookup"><span data-stu-id="e9e27-394">**Tile Query:** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```</span></span>
4.  <span data-ttu-id="e9e27-395">定义 **列表** 属性。</span><span class="sxs-lookup"><span data-stu-id="e9e27-395">Define the **List** properties.</span></span><br>
    <span data-ttu-id="e9e27-396">**列表查询：**```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```</span><span class="sxs-lookup"><span data-stu-id="e9e27-396">**List Query:** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```</span></span>
5.  <span data-ttu-id="e9e27-397">定义 **列标题**。</span><span class="sxs-lookup"><span data-stu-id="e9e27-397">Define **Column Titles**.</span></span><br>
    <span data-ttu-id="e9e27-398">**名称：** 计算机名称</span><span class="sxs-lookup"><span data-stu-id="e9e27-398">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="e9e27-399">**值：** 重启次数</span><span class="sxs-lookup"><span data-stu-id="e9e27-399">**Value:** Number of Restarts</span></span>
6.  <span data-ttu-id="e9e27-400">定义 **导航查询**。</span><span class="sxs-lookup"><span data-stu-id="e9e27-400">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  <span data-ttu-id="e9e27-401">选择 **"应用"，** 然后选择"**关闭"。**</span><span class="sxs-lookup"><span data-stu-id="e9e27-401">Select **Apply** and then **Close**.</span></span>
8.  <span data-ttu-id="e9e27-402">选择 **"保存** "以保存仪表板。</span><span class="sxs-lookup"><span data-stu-id="e9e27-402">Select **Save** to save your dashboard.</span></span>

<span data-ttu-id="e9e27-403">现在，你已完成创建视图。</span><span class="sxs-lookup"><span data-stu-id="e9e27-403">Now you've completed creating your views.</span></span>

## <a name="configure-alerts-in-no-loc-textazure-monitor"></a><span data-ttu-id="e9e27-404">在 中配置警报 :::no-loc text="Azure Monitor":::</span><span class="sxs-lookup"><span data-stu-id="e9e27-404">Configure Alerts in :::no-loc text="Azure Monitor":::</span></span>
<span data-ttu-id="e9e27-405"><a name="Alerts"> </a></span><span class="sxs-lookup"><span data-stu-id="e9e27-405"><a name="Alerts"> </a></span></span>

<span data-ttu-id="e9e27-406">:::no-loc text="Azure Monitor"::: 当主机遇到问题时，可以 :::no-loc text="Microsoft Teams Rooms"::: 引发警报以通知管理员。</span><span class="sxs-lookup"><span data-stu-id="e9e27-406">:::no-loc text="Azure Monitor"::: can raise alerts to notify the administrators, when a :::no-loc text="Microsoft Teams Rooms"::: console encounters an issue.</span></span>

<span data-ttu-id="e9e27-407">:::no-loc text="Azure Monitor"::: 包括内置警报机制，该机制定期通过计划的日志搜索运行。</span><span class="sxs-lookup"><span data-stu-id="e9e27-407">:::no-loc text="Azure Monitor"::: includes a built-in alerting mechanism that runs through scheduled log searches at regular intervals.</span></span> <span data-ttu-id="e9e27-408">如果日志搜索结果与特定条件匹配，则创建警报记录。</span><span class="sxs-lookup"><span data-stu-id="e9e27-408">If the results of the log search match some particular criteria, an alert record is created.</span></span>

<span data-ttu-id="e9e27-409">然后，规则可以自动运行一个或多个操作，主动通知你警报或调用另一个进程。</span><span class="sxs-lookup"><span data-stu-id="e9e27-409">The rule can then automatically run one or more actions to proactively notify you of the alert or invoke another process.</span></span> <span data-ttu-id="e9e27-410">警报的可能选项包括：</span><span class="sxs-lookup"><span data-stu-id="e9e27-410">The possible options with alerts are:</span></span>
-   <span data-ttu-id="e9e27-411">发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="e9e27-411">Sending an email</span></span>
-   <span data-ttu-id="e9e27-412">通过 HTTP POST 请求调用外部进程</span><span class="sxs-lookup"><span data-stu-id="e9e27-412">Invoking an external process through an HTTP POST request</span></span>
-   <span data-ttu-id="e9e27-413">在服务中启动 Runbook :::no-loc text="Azure Automation":::</span><span class="sxs-lookup"><span data-stu-id="e9e27-413">Starting a runbook in :::no-loc text="Azure Automation"::: service</span></span>

<span data-ttu-id="e9e27-414">请参阅[中的日志警报 :::no-loc text="Azure Monitor"::: ](/azure/azure-monitor/platform/alerts-unified-log)，详细了解 中的警报 :::no-loc text="Azure Monitor"::: 。</span><span class="sxs-lookup"><span data-stu-id="e9e27-414">See [Log alerts in :::no-loc text="Azure Monitor":::](/azure/azure-monitor/platform/alerts-unified-log) to learn more about the alerts in :::no-loc text="Azure Monitor":::.</span></span>

> [!NOTE]
> <span data-ttu-id="e9e27-415">以下示例在设备生成硬件或应用程序错误时 :::no-loc text="Microsoft Teams Rooms"::: 发送电子邮件警报。</span><span class="sxs-lookup"><span data-stu-id="e9e27-415">The following examples send email alerts when a :::no-loc text="Microsoft Teams Rooms"::: device generates a hardware or an application error.</span></span>

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-hardware-issues"></a><span data-ttu-id="e9e27-416">配置针对硬件问题 :::no-loc text="Microsoft Teams Rooms"::: 的电子邮件警报</span><span class="sxs-lookup"><span data-stu-id="e9e27-416">Configure an email alert for :::no-loc text="Microsoft Teams Rooms"::: hardware issues</span></span>

<span data-ttu-id="e9e27-417">配置一个警报规则，用于检查过去一小时内遇到 :::no-loc text="Microsoft Teams Rooms"::: 硬件问题的设备。</span><span class="sxs-lookup"><span data-stu-id="e9e27-417">Configure an alert rule that checks for :::no-loc text="Microsoft Teams Rooms"::: devices that have encountered hardware issues within the last hour.</span></span>
1.  <span data-ttu-id="e9e27-418">登录到门户[ :::no-loc text="Microsoft Azure"::: ，](https://portal.azure.com)转到并选择 :::no-loc text="Log Analytics"::: 工作区。</span><span class="sxs-lookup"><span data-stu-id="e9e27-418">Sign in to the [:::no-loc text="Microsoft Azure"::: portal](https://portal.azure.com) and go to :::no-loc text="Log Analytics"::: and select your workspace.</span></span>

2. <span data-ttu-id="e9e27-419">导航到工作区 :::no-loc text="Log Analytics"::: ，选择 **"警报"，** 然后选择" **新建警报规则"**</span><span class="sxs-lookup"><span data-stu-id="e9e27-419">Navigate to your :::no-loc text="Log Analytics"::: workspace and select **Alerts** and then select **New alert rule**</span></span>

3. <span data-ttu-id="e9e27-420">选择 **"添加条件** "，然后选择" **自定义日志搜索"**</span><span class="sxs-lookup"><span data-stu-id="e9e27-420">Select **Add condition** and then **Custom log search**</span></span>

4.  <span data-ttu-id="e9e27-421">在"搜索查询"文本框中输入以下查询。</span><span class="sxs-lookup"><span data-stu-id="e9e27-421">Enter the following query to the Search query text box.</span></span><br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF
    |sort by TimeGenerated desc
    ```

5.  <span data-ttu-id="e9e27-422">配置警报逻辑设置：</span><span class="sxs-lookup"><span data-stu-id="e9e27-422">Configure the Alert logic settings:</span></span><br>
    <span data-ttu-id="e9e27-423">**基于：** 结果数</span><span class="sxs-lookup"><span data-stu-id="e9e27-423">**Based on:** Number of results</span></span><br>
    <span data-ttu-id="e9e27-424">**条件：** 大于，然后</span><span class="sxs-lookup"><span data-stu-id="e9e27-424">**Condition:** Greater then</span></span><br>
    <span data-ttu-id="e9e27-425">**阈值：0**</span><span class="sxs-lookup"><span data-stu-id="e9e27-425">**Threshold:** 0</span></span><br>

6. <span data-ttu-id="e9e27-426">配置评估设置，然后选择"完成 **"：**</span><span class="sxs-lookup"><span data-stu-id="e9e27-426">Configure Evaluation settings and select **Done**:</span></span> <br>
    <span data-ttu-id="e9e27-427">**时间段 (分钟) ：60**</span><span class="sxs-lookup"><span data-stu-id="e9e27-427">**Period (in minutes):** 60</span></span><br>
    <span data-ttu-id="e9e27-428">**频率 (分钟) ：60**</span><span class="sxs-lookup"><span data-stu-id="e9e27-428">**Frequency (in minutes):** 60</span></span><br>

7. <span data-ttu-id="e9e27-429">配置操作组：</span><span class="sxs-lookup"><span data-stu-id="e9e27-429">Configure action groups:</span></span>
    1.  <span data-ttu-id="e9e27-430">选择 **"新建"**</span><span class="sxs-lookup"><span data-stu-id="e9e27-430">Select **Create New**</span></span>
    2.  <span data-ttu-id="e9e27-431">为"操作组名称"*和"短名称"字段\*\*提供合适的* 名称。</span><span class="sxs-lookup"><span data-stu-id="e9e27-431">Provide suitable names for the *Action group name* and *Short Name* fields.</span></span>
    3.  <span data-ttu-id="e9e27-432">指定唯一 *的操作名称，* 选择"**电子邮件/短信/推送/语音**"，然后选择"**编辑详细信息"。**</span><span class="sxs-lookup"><span data-stu-id="e9e27-432">Specify a unique *Action Name* and select **Email/SMS/Push/Voice**, and then select **Edit details**.</span></span>
    4.  <span data-ttu-id="e9e27-433">选中 **"电子邮件** "复选框，并提供将接收警报的联系人或组的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="e9e27-433">Select the **Email** checkbox and provide the email address of the person or group that will receive the alerts.</span></span>
    5.  <span data-ttu-id="e9e27-434">您也可以提供电话号码，以便通过短信和/或语音呼叫获得通知。</span><span class="sxs-lookup"><span data-stu-id="e9e27-434">You may also provide your phone number to get notified with SMS, a voice call or both.</span></span>
    6. <span data-ttu-id="e9e27-435">选择"**确定"。**</span><span class="sxs-lookup"><span data-stu-id="e9e27-435">Select **OK**.</span></span>

8. <span data-ttu-id="e9e27-436">**如果要** 覆盖警报电子邮件的主题行，请自定义"操作"。</span><span class="sxs-lookup"><span data-stu-id="e9e27-436">**Customize Actions** if you like to override the subject line of the alert emails.</span></span>

9. <span data-ttu-id="e9e27-437">指定规则名称和说明。</span><span class="sxs-lookup"><span data-stu-id="e9e27-437">Specify a rule name and description.</span></span><br>
    <span data-ttu-id="e9e27-438">**规则名称：** :::no-loc text="Microsoft Teams Rooms"::: 硬件故障警报</span><span class="sxs-lookup"><span data-stu-id="e9e27-438">**Rule Name:** :::no-loc text="Microsoft Teams Rooms"::: Hardware Failure Alert</span></span><br>
    <span data-ttu-id="e9e27-439">**说明：** 过去一小时内遇到硬件问题的设备列表</span><span class="sxs-lookup"><span data-stu-id="e9e27-439">**Description:** List of devices that encountered a hardware issue within the last hour</span></span><br>

10. <span data-ttu-id="e9e27-440">选择预期的严重性，并确保已启用规则。</span><span class="sxs-lookup"><span data-stu-id="e9e27-440">Select the intended severity and make sure the rule is enabled.</span></span>

11. <span data-ttu-id="e9e27-441">选择 **"创建警报规则"。**</span><span class="sxs-lookup"><span data-stu-id="e9e27-441">Select **Create alert rule**.</span></span>

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-application-issues"></a><span data-ttu-id="e9e27-442">配置应用程序问题 :::no-loc text="Microsoft Teams Rooms"::: 的电子邮件警报</span><span class="sxs-lookup"><span data-stu-id="e9e27-442">Configure an email alert for :::no-loc text="Microsoft Teams Rooms"::: application issues</span></span>

<span data-ttu-id="e9e27-443">重复相同的过程，但使用以下查询列出过去一小时内遇到应用程序问题的设备。</span><span class="sxs-lookup"><span data-stu-id="e9e27-443">Repeat the same procedure but use the following query to list devices that have encountered application issues within the last hour.</span></span>

    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF
    | sort by TimeGenerated desc
    ```

<span data-ttu-id="e9e27-444">现已完成警报定义。</span><span class="sxs-lookup"><span data-stu-id="e9e27-444">Now you've completed defining alerts.</span></span> <span data-ttu-id="e9e27-445">可以使用上述示例定义其他警报。</span><span class="sxs-lookup"><span data-stu-id="e9e27-445">You can define additional alerts by using the examples above.</span></span>

<span data-ttu-id="e9e27-446">生成警报时，你收到一封电子邮件，其中列出了过去一小时内遇到问题的设备。</span><span class="sxs-lookup"><span data-stu-id="e9e27-446">When an alert is generated, you'll get an email that lists the devices that encountered an issue within the last hour.</span></span>

<span data-ttu-id="e9e27-447">![示例 :::no-loc text="Azure Monitor"::: 警报电子邮件] (./media/Deploy-Azure-Monitor-6.png" :::no-loc text="Azure Monitor"::: 示例警报电子邮件") </span><span class="sxs-lookup"><span data-stu-id="e9e27-447">![Sample :::no-loc text="Azure Monitor"::: alert email](../media/Deploy-Azure-Monitor-6.png "Sample :::no-loc text="Azure Monitor"::: alert email")</span></span>

## <a name="configure-all-devices-for-no-loc-textazure-monitoring"></a><span data-ttu-id="e9e27-448">为 配置所有设备 :::no-loc text="Azure Monitoring":::</span><span class="sxs-lookup"><span data-stu-id="e9e27-448">Configure all devices for :::no-loc text="Azure Monitoring":::</span></span>
<span data-ttu-id="e9e27-449"><a name="configure_all_devices"></a>配置仪表板和警报后，可以在所有设备上设置和配置代理， :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Microsoft Teams Rooms"::: 以完成监视部署。</span><span class="sxs-lookup"><span data-stu-id="e9e27-449"><a name="configure_all_devices"> </a> After the dashboards and alerts are configured, you can set up and configure :::no-loc text="Microsoft Monitoring"::: agent on all :::no-loc text="Microsoft Teams Rooms"::: devices to complete your monitoring deployment.</span></span>

<span data-ttu-id="e9e27-450">虽然可以在每台设备上手动安装和配置代理，但我们强烈建议利用现有 :::no-loc text="Microsoft Monitoring"::: 的软件部署工具和方法。</span><span class="sxs-lookup"><span data-stu-id="e9e27-450">Although you can install and configure the :::no-loc text="Microsoft Monitoring"::: agent manually on each device, we highly recommend you leverage existing software deployment tools and methods.</span></span>

<span data-ttu-id="e9e27-451">如果是首次生成设备，可能需要在生成过程中包括代理设置 :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Microsoft Monitoring"::: 和配置步骤。</span><span class="sxs-lookup"><span data-stu-id="e9e27-451">If you're building your :::no-loc text="Microsoft Teams Rooms"::: devices for the first time, you might want to include the :::no-loc text="Microsoft Monitoring"::: agent setup and configuration steps as part of your build process.</span></span> <span data-ttu-id="e9e27-452">有关详细信息，请参阅 [使用命令行安装代理](/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line)。</span><span class="sxs-lookup"><span data-stu-id="e9e27-452">For more information, see [Install the agent using the command line](/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line).</span></span>

### <a name="deploying-no-loc-textmicrosoft-monitoring-agent-by-using-a-group-policy-object-gpo"></a><span data-ttu-id="e9e27-453">使用 :::no-loc text="Microsoft Monitoring"::: 组策略对象和 GPO (部署) </span><span class="sxs-lookup"><span data-stu-id="e9e27-453">Deploying :::no-loc text="Microsoft Monitoring"::: agent by using a Group Policy Object (GPO)</span></span>

<span data-ttu-id="e9e27-454">如果在实现 之前已部署设备，可以使用提供的脚本通过组策略对象 :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Azure Monitoring"::: 来设置和配置 :::no-loc text="Active Directory"::: 代理。</span><span class="sxs-lookup"><span data-stu-id="e9e27-454">If you already deployed your :::no-loc text="Microsoft Teams Rooms"::: devices before you implement :::no-loc text="Azure Monitoring":::, you can use the provided script to set up and configure the agents by using :::no-loc text="Active Directory"::: group policy objects.</span></span>

1.  <span data-ttu-id="e9e27-455">创建共享网络路径，并授予对"域计算机 **"组的读取** 访问权限。</span><span class="sxs-lookup"><span data-stu-id="e9e27-455">Create a shared network path and grant read access to **Domain Computers** group.</span></span>

2.  <span data-ttu-id="e9e27-456">从 下载 64 位 :::no-loc text="Microsoft Monitoring"::: 版本的 :::no-loc text="Windows"::: 代理 <https://go.microsoft.com/fwlink/?LinkID=517476></span><span class="sxs-lookup"><span data-stu-id="e9e27-456">Download the 64-bit version of the :::no-loc text="Microsoft Monitoring"::: Agent for :::no-loc text="Windows"::: from <https://go.microsoft.com/fwlink/?LinkID=517476></span></span>

3.  <span data-ttu-id="e9e27-457">将安装包的内容提取到网络共享中。</span><span class="sxs-lookup"><span data-stu-id="e9e27-457">Extract the contents of the setup package into the network share.</span></span>
    1.  <span data-ttu-id="e9e27-458">打开命令提示符窗口，然后MMASetup-AMD64.exe **/c**</span><span class="sxs-lookup"><span data-stu-id="e9e27-458">Open a Command Prompt window, and then execute **MMASetup-AMD64.exe /c**</span></span>
    2.  <span data-ttu-id="e9e27-459">指定刚刚创建的共享，并提取内容。</span><span class="sxs-lookup"><span data-stu-id="e9e27-459">Specify the share you just created, and extract the content.</span></span>

4.  <span data-ttu-id="e9e27-460">创建新的组策略对象，并将其分配给计算机帐户 :::no-loc text="Microsoft Teams Rooms"::: 所在的组织单位。</span><span class="sxs-lookup"><span data-stu-id="e9e27-460">Create a new Group Policy Object and assign it to the organizational unit where :::no-loc text="Microsoft Teams Rooms"::: machine accounts are located.</span></span>

5.  <span data-ttu-id="e9e27-461">配置 PowerShell 执行策略：</span><span class="sxs-lookup"><span data-stu-id="e9e27-461">Configure PowerShell execution policy:</span></span>
    1.  <span data-ttu-id="e9e27-462">编辑新建的组策略对象并导航到"计算机配置 \\ 策略 \\ ""管理模板组件 \\ :::no-loc text="Windows"::: " \\:::no-loc text="Windows PowerShell":::</span><span class="sxs-lookup"><span data-stu-id="e9e27-462">Edit the newly created Group Policy Object and navigate to Computer Configuration \\ Policies \\ Administrative Templates \\ :::no-loc text="Windows"::: Components \\ :::no-loc text="Windows PowerShell":::</span></span>
    2.  <span data-ttu-id="e9e27-463">启用"**启用脚本执行"，将\*\*\*\*"执行策略"设置为\*\*\*\*"允许本地脚本"。**</span><span class="sxs-lookup"><span data-stu-id="e9e27-463">Enable the **Turn on Script Execution** and set **Execution Policy** to **Allow Local Scripts**.</span></span>

6.  <span data-ttu-id="e9e27-464">配置启动脚本：</span><span class="sxs-lookup"><span data-stu-id="e9e27-464">Configure the startup script:</span></span>
    1.  <span data-ttu-id="e9e27-465">复制以下脚本并将其另存为Install-MMAgent.ps1。</span><span class="sxs-lookup"><span data-stu-id="e9e27-465">Copy the following script and save it as Install-MMAgent.ps1.</span></span>
    2.  <span data-ttu-id="e9e27-466">修改 WorkspaceId、WorkspaceKey 和 SetupPath 参数，以匹配配置。</span><span class="sxs-lookup"><span data-stu-id="e9e27-466">Modify WorkspaceId, WorkspaceKey, and SetupPath parameters to match your configuration.</span></span>
    3.  <span data-ttu-id="e9e27-467">编辑同一组策略对象并导航到"计算机配置策略设置"脚本 \\ \\ :::no-loc text="Windows"::: \\ (启动/关闭) </span><span class="sxs-lookup"><span data-stu-id="e9e27-467">Edit the same Group Policy Object and navigate to Computer Configuration \\ Policies \\ :::no-loc text="Windows"::: Settings \\ Scripts (Startup/Shutdown)</span></span>
    4.  <span data-ttu-id="e9e27-468">双击选择"启动 **"，** 然后选择 **"PowerShell 脚本"。**</span><span class="sxs-lookup"><span data-stu-id="e9e27-468">Double-click to select **Startup**, and then select **PowerShell Scripts**.</span></span>
    5.  <span data-ttu-id="e9e27-469">选择 **"显示** 文件"， **然后将Install-MMAgent.ps1文件** 复制到该文件夹。</span><span class="sxs-lookup"><span data-stu-id="e9e27-469">Select **Show Files**, and then copy the **Install-MMAgent.ps1** file to that folder.</span></span>
    6.  <span data-ttu-id="e9e27-470">选择 **"添加"，** 然后选择"**浏览"。**</span><span class="sxs-lookup"><span data-stu-id="e9e27-470">Select **Add**, and then **Browse**.</span></span>
    7.  <span data-ttu-id="e9e27-471">选择刚刚复制的 ps1 脚本。</span><span class="sxs-lookup"><span data-stu-id="e9e27-471">Select the ps1 script you just copied.</span></span>

7.  <span data-ttu-id="e9e27-472">:::no-loc text="Microsoft Teams Rooms"::: 设备应在第二次 :::no-loc text="Microsoft Monitoring"::: 重新启动时安装和配置代理。</span><span class="sxs-lookup"><span data-stu-id="e9e27-472">:::no-loc text="Microsoft Teams Rooms"::: devices should install and configure the :::no-loc text="Microsoft Monitoring"::: agent with the second reboot.</span></span>

```PowerShell
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
> <span data-ttu-id="e9e27-473">可以在需要 [重新配置代理、 :::no-loc text="Log Analytics"::: ](/azure/azure-monitor/platform/agent-manage) 将其移到其他工作区或修改初始安装后修改代理设置时，参阅管理和维护代理一文。</span><span class="sxs-lookup"><span data-stu-id="e9e27-473">You can refer to the article [Managing and maintaining the :::no-loc text="Log Analytics"::: agent](/azure/azure-monitor/platform/agent-manage) when you need to reconfigure an agent, move it to a different workspace, or modify proxy settings after the initial installation.</span></span>

## <a name="additional-solutions"></a><span data-ttu-id="e9e27-474">其他解决方案</span><span class="sxs-lookup"><span data-stu-id="e9e27-474">Additional Solutions</span></span>
<span data-ttu-id="e9e27-475"><a name="Solutions"> </a></span><span class="sxs-lookup"><span data-stu-id="e9e27-475"><a name="Solutions"> </a></span></span>

<span data-ttu-id="e9e27-476">:::no-loc text="Azure Monitor"::: 通过其解决方案库提供内置管理解决方案 [，](/azure/azure-monitor/insights/solutions) 以进一步帮助监视环境。</span><span class="sxs-lookup"><span data-stu-id="e9e27-476">:::no-loc text="Azure Monitor"::: provides built-in management solutions through its [solution gallery](/azure/azure-monitor/insights/solutions) to further help you monitor your environment.</span></span> <span data-ttu-id="e9e27-477">我们强烈建议将[警报管理和](/azure/azure-monitor/platform/alert-management-solution)[ :::no-loc text="Azure Log Analytics"::: 代理运行状况](/azure/azure-monitor/insights/solution-agenthealth)解决方案添加到工作区。</span><span class="sxs-lookup"><span data-stu-id="e9e27-477">We highly recommend that you add [Alert Management](/azure/azure-monitor/platform/alert-management-solution) and [:::no-loc text="Azure Log Analytics"::: Agent Health](/azure/azure-monitor/insights/solution-agenthealth) solutions to your workspace as well.</span></span>

> [!NOTE]
> <span data-ttu-id="e9e27-478">代理运行状况解决方案可帮助识别环境中过期或损坏的代理，警报管理解决方案提供有关给定时段内已引发警报 :::no-loc text="Microsoft Monitoring"::: 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="e9e27-478">The Agent Health solution can help you identify outdated or broken :::no-loc text="Microsoft Monitoring"::: agents within your environment, and the Alert Management solution provides details about the alerts that have been raised within a given period.</span></span>

## <a name="see-also"></a><span data-ttu-id="e9e27-479">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e9e27-479">See also</span></span>

[<span data-ttu-id="e9e27-480">使用 :::no-loc text="Microsoft Teams Rooms"::: 进行计划管理 :::no-loc text="Azure Monitor":::</span><span class="sxs-lookup"><span data-stu-id="e9e27-480">Plan :::no-loc text="Microsoft Teams Rooms"::: management with :::no-loc text="Azure Monitor":::</span></span>](azure-monitor-plan.md)

[<span data-ttu-id="e9e27-481">使用 :::no-loc text="Microsoft Teams Rooms"::: 管理设备 :::no-loc text="Azure Monitor":::</span><span class="sxs-lookup"><span data-stu-id="e9e27-481">Manage :::no-loc text="Microsoft Teams Rooms"::: devices with :::no-loc text="Azure Monitor":::</span></span>](azure-monitor-manage.md)