---
title: 通过 Azure 监视器部署 Microsoft 团队聊天室管理
ms.author: v-lanac
author: lanachin
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
description: 本文介绍如何使用 Azure 监视器以集成的端到端方式部署 Microsoft 团队聊天室设备的管理。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 3c1ecb3906eec551ddaed9a2c748a66c9da7ac9a
ms.sourcegitcommit: 67c686810d37bffda72a6e92155d9c8ec86bfae6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2020
ms.locfileid: "47766876"
---
# <a name="deploy-no-loc-textmicrosoft-teams-rooms-management-with-no-loc-textazure-monitor"></a><span data-ttu-id="b3e57-103">部署 :::no-loc text="Microsoft Teams Rooms"::: 管理 :::no-loc text="Azure Monitor":::</span><span class="sxs-lookup"><span data-stu-id="b3e57-103">Deploy :::no-loc text="Microsoft Teams Rooms"::: management with :::no-loc text="Azure Monitor":::</span></span>

<span data-ttu-id="b3e57-104">本文介绍如何通过使用设置和部署设备的集成端到端管理 :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Azure Monitor"::: 。</span><span class="sxs-lookup"><span data-stu-id="b3e57-104">This article discusses how to set up and deploy integrated, end-to-end management of :::no-loc text="Microsoft Teams Rooms"::: devices by using :::no-loc text="Azure Monitor":::.</span></span>

<span data-ttu-id="b3e57-105">你可以 :::no-loc text="Log Analytics"::: 在内部 :::no-loc text="Azure Monitor"::: 进行配置，以提供可帮助你管理会议室设备的基本遥测和警报 :::no-loc text="Microsoft Teams Rooms"::: 。</span><span class="sxs-lookup"><span data-stu-id="b3e57-105">You can configure :::no-loc text="Log Analytics"::: within :::no-loc text="Azure Monitor"::: to provide basic telemetry and alerts that will help you manage :::no-loc text="Microsoft Teams Rooms"::: meeting room devices.</span></span> <span data-ttu-id="b3e57-106">随着管理解决方案的成熟，你可能会决定部署其他数据和管理功能来创建更详细的设备可用性和性能视图。</span><span class="sxs-lookup"><span data-stu-id="b3e57-106">As your management solution matures, you might decide to deploy additional data and management capabilities to create a more detailed view of device availability and performance.</span></span>

<span data-ttu-id="b3e57-107">通过遵循本指南，你可以使用仪表板（如以下示例）获取有关设备可用性、应用程序和硬件运行状况以及 :::no-loc text="Microsoft Teams Rooms"::: 应用程序和操作系统版本分发的详细状态报告。</span><span class="sxs-lookup"><span data-stu-id="b3e57-107">By following this guide, you can use a dashboard like the following example to get detailed status reporting for device availability, application and hardware health, and :::no-loc text="Microsoft Teams Rooms"::: application and operating system version distribution.</span></span>

<span data-ttu-id="b3e57-108">![Microsoft 团队聊天室示例 Log Analytics 视图的屏幕截图](../media/Deploy-Azure-Monitor-1.png "Microsoft 团队聊天室的日志分析视图示例")</span><span class="sxs-lookup"><span data-stu-id="b3e57-108">![Screenshot of sample Log Analytics view for Microsoft Teams Rooms](../media/Deploy-Azure-Monitor-1.png "Sample Log Analytics view for Microsoft Teams Rooms")</span></span>

<span data-ttu-id="b3e57-109">你需要在高级别执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="b3e57-109">At a high level, you need to perform the following tasks:</span></span>


1. [<span data-ttu-id="b3e57-110">验证 :::no-loc text="Log Analytics"::: 配置</span><span class="sxs-lookup"><span data-stu-id="b3e57-110">Validate :::no-loc text="Log Analytics"::: configuration</span></span>](azure-monitor-deploy.md#validate_LogAnalytics)
2. [<span data-ttu-id="b3e57-111">配置管理设置的测试设备 :::no-loc text="Log Analytics":::</span><span class="sxs-lookup"><span data-stu-id="b3e57-111">Configure test devices for :::no-loc text="Log Analytics"::: management setup</span></span>](azure-monitor-deploy.md#configure_test_devices)
3. [<span data-ttu-id="b3e57-112">映射自定义字段</span><span class="sxs-lookup"><span data-stu-id="b3e57-112">Map custom fields</span></span>](azure-monitor-deploy.md#Custom_fields)
4. [<span data-ttu-id="b3e57-113">定义 :::no-loc text="Microsoft Teams Rooms"::: 视图 :::no-loc text="Log Analytics":::</span><span class="sxs-lookup"><span data-stu-id="b3e57-113">Define the :::no-loc text="Microsoft Teams Rooms"::: views in :::no-loc text="Log Analytics":::</span></span>](azure-monitor-deploy.md#Define_Views)
5. [<span data-ttu-id="b3e57-114">定义警报</span><span class="sxs-lookup"><span data-stu-id="b3e57-114">Define alerts</span></span>](azure-monitor-deploy.md#Alerts)
6. [<span data-ttu-id="b3e57-115">配置用于监视的所有设备</span><span class="sxs-lookup"><span data-stu-id="b3e57-115">Configure all devices for Monitoring</span></span>](azure-monitor-deploy.md#configure_all_devices)
7. [<span data-ttu-id="b3e57-116">配置其他 :::no-loc text="Azure Monitor"::: 解决方案</span><span class="sxs-lookup"><span data-stu-id="b3e57-116">Configure additional :::no-loc text="Azure Monitor"::: solutions</span></span>](azure-monitor-deploy.md#Solutions)

> [!IMPORTANT]
> <span data-ttu-id="b3e57-117">虽然使用最少的配置 :::no-loc text="Azure Monitor"::: :::no-loc text="Log Analytics"::: 可以监视运行操作系统的计算机，但在 :::no-loc text="Windows"::: :::no-loc text="Microsoft Teams Rooms"::: 开始将代理部署到所有设备之前，仍需要执行一些特定步骤 :::no-loc text="Microsoft Teams Rooms"::: 。</span><span class="sxs-lookup"><span data-stu-id="b3e57-117">Although with minimal configuration, :::no-loc text="Azure Monitor"::: :::no-loc text="Log Analytics"::: can monitor a computer running a :::no-loc text="Windows"::: operating system, there are still some :::no-loc text="Microsoft Teams Rooms":::–specific steps that you need to take before you start deploying agents to all :::no-loc text="Microsoft Teams Rooms"::: devices.</span></span>
> <span data-ttu-id="b3e57-118">因此，我们强烈建议你按照正确的顺序执行所有配置步骤，以进行受控设置和配置。</span><span class="sxs-lookup"><span data-stu-id="b3e57-118">Therefore, we highly recommend you perform all configuration steps in the right order for a controlled setup and configuration.</span></span> <span data-ttu-id="b3e57-119">最终结果的质量非常多取决于初始配置的质量。</span><span class="sxs-lookup"><span data-stu-id="b3e57-119">The quality of the end result very much depends on the quality of the initial configuration.</span></span>

## <a name="validate-no-loc-textlog-analytics-configuration"></a><span data-ttu-id="b3e57-120">验证 :::no-loc text="Log Analytics"::: 配置</span><span class="sxs-lookup"><span data-stu-id="b3e57-120">Validate :::no-loc text="Log Analytics"::: configuration</span></span>
<span data-ttu-id="b3e57-121"><a name="validate_LogAnalytics"> </a></span><span class="sxs-lookup"><span data-stu-id="b3e57-121"><a name="validate_LogAnalytics"> </a></span></span>

<span data-ttu-id="b3e57-122">需要具有 :::no-loc text="Log Analytics"::: 工作区才能开始从设备收集日志 :::no-loc text="Microsoft Teams Rooms"::: 。</span><span class="sxs-lookup"><span data-stu-id="b3e57-122">You need to have a :::no-loc text="Log Analytics"::: workspace to start collecting logs from :::no-loc text="Microsoft Teams Rooms"::: devices.</span></span> <span data-ttu-id="b3e57-123">工作区是 :::no-loc text="Log Analytics"::: 具有自己的数据存储库、数据源和解决方案的独特环境。</span><span class="sxs-lookup"><span data-stu-id="b3e57-123">A workspace is a unique :::no-loc text="Log Analytics"::: environment with its own data repository, data sources, and solutions.</span></span> <span data-ttu-id="b3e57-124">如果你已有一个现有 :::no-loc text="Log Analytics"::: 工作区，则可以使用它监视你的部署，或者 :::no-loc text="Microsoft Teams Rooms"::: 你可以创建 :::no-loc text="Log Analytics"::: 特定于你的监视需求的专用工作区 :::no-loc text="Microsoft Teams Rooms"::: 。</span><span class="sxs-lookup"><span data-stu-id="b3e57-124">If you already have an existing :::no-loc text="Log Analytics"::: workspace, you might use it to monitor your :::no-loc text="Microsoft Teams Rooms"::: deployment or alternatively, you can create a dedicated :::no-loc text="Log Analytics"::: workspace specific to your :::no-loc text="Microsoft Teams Rooms"::: monitoring needs.</span></span>

<span data-ttu-id="b3e57-125">如果需要创建新的 :::no-loc text="Log Analytics"::: 工作区，请按照文章在[ :::no-loc text="Log Analytics"::: :::no-loc text="Azure"::: 门户中创建工作区](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace)中的说明进行操作</span><span class="sxs-lookup"><span data-stu-id="b3e57-125">If you need to create a new :::no-loc text="Log Analytics"::: workspace, follow the instructions in the article [Create a :::no-loc text="Log Analytics"::: workspace in the :::no-loc text="Azure"::: portal](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace)</span></span>

> [!NOTE]
> <span data-ttu-id="b3e57-126">若要 :::no-loc text="Log Analytics"::: 使用 :::no-loc text="Azure Monitor"::: ，您需要有有效的 :::no-loc text="Azure"::: 订阅。</span><span class="sxs-lookup"><span data-stu-id="b3e57-126">To use :::no-loc text="Log Analytics"::: with :::no-loc text="Azure Monitor":::, you need to have an active :::no-loc text="Azure"::: subscription.</span></span> <span data-ttu-id="b3e57-127">如果您没有套餐 :::no-loc text="Azure"::: ，您可以创建 [一个免费试用订阅](https://azure.microsoft.com/free) 作为起点。</span><span class="sxs-lookup"><span data-stu-id="b3e57-127">If you don't have an :::no-loc text="Azure"::: subscription, you can create [a free trial subscription](https://azure.microsoft.com/free) as a starting point.</span></span>

### <a name="configure-no-loc-textlog-analytics-to-collect-no-loc-textmicrosoft-teams-rooms-event-logs"></a><span data-ttu-id="b3e57-128">配置 :::no-loc text="Log Analytics"::: 以收集 :::no-loc text="Microsoft Teams Rooms"::: 事件日志</span><span class="sxs-lookup"><span data-stu-id="b3e57-128">Configure :::no-loc text="Log Analytics"::: to collect :::no-loc text="Microsoft Teams Rooms"::: event logs</span></span>

<span data-ttu-id="b3e57-129">:::no-loc text="Log Analytics"::: 仅收集 :::no-loc text="Windows"::: 在 "设置" 中指定的事件日志中的事件。</span><span class="sxs-lookup"><span data-stu-id="b3e57-129">:::no-loc text="Log Analytics"::: only collects events from the :::no-loc text="Windows"::: event logs that are specified in the settings.</span></span> <span data-ttu-id="b3e57-130">对于每个日志，仅收集具有选定严重性的事件。</span><span class="sxs-lookup"><span data-stu-id="b3e57-130">For each log, only the events with the selected severities are collected.</span></span>

<span data-ttu-id="b3e57-131">你需要配置 :::no-loc text="Log Analytics"::: 以收集监视 :::no-loc text="Microsoft Teams Rooms"::: 设备和应用程序状态所需的日志。</span><span class="sxs-lookup"><span data-stu-id="b3e57-131">You need to configure :::no-loc text="Log Analytics"::: to collect the logs required to monitor :::no-loc text="Microsoft Teams Rooms"::: device and application status.</span></span> <span data-ttu-id="b3e57-132">:::no-loc text="Microsoft Teams Rooms"::: 设备使用 **:::no-loc text="Skype Room System":::** 事件日志。</span><span class="sxs-lookup"><span data-stu-id="b3e57-132">:::no-loc text="Microsoft Teams Rooms"::: devices use the **:::no-loc text="Skype Room System":::** event log.</span></span>

<span data-ttu-id="b3e57-133">若要配置 :::no-loc text="Log Analytics"::: 以收集 :::no-loc text="Microsoft Teams Rooms"::: 事件，请参阅[ :::no-loc text="Windows"::: 事件日志中的 :::no-loc text="Azure Monitor"::: "数据源](https://docs.microsoft.com/azure/azure-monitor/platform/data-sources-windows-events)"</span><span class="sxs-lookup"><span data-stu-id="b3e57-133">To configure :::no-loc text="Log Analytics"::: to collect the :::no-loc text="Microsoft Teams Rooms"::: events, see [:::no-loc text="Windows"::: event log data sources in :::no-loc text="Azure Monitor":::](https://docs.microsoft.com/azure/azure-monitor/platform/data-sources-windows-events)</span></span>

<span data-ttu-id="b3e57-134">![事件日志设置的屏幕截图](../media/Deploy-Azure-Monitor-2.png "事件日志设置")</span><span class="sxs-lookup"><span data-stu-id="b3e57-134">![Screenshot of event log settings](../media/Deploy-Azure-Monitor-2.png "Event log settings")</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b3e57-135">配置 :::no-loc text="Windows"::: 事件日志设置并输入 **:::no-loc text="Skype Room System":::** "事件日志名称"，然后选择 " **错误**"、" **警告**" 和 " **信息** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="b3e57-135">Configure :::no-loc text="Windows"::: Event Log settings and enter **:::no-loc text="Skype Room System":::** as event log name, and then select the **Error**, **Warning**, and **Information** check boxes.</span></span>

## <a name="configure-test-devices-for-azure-monitoring"></a><span data-ttu-id="b3e57-136">配置用于 Azure 监视的测试设备</span><span class="sxs-lookup"><span data-stu-id="b3e57-136">Configure test devices for Azure Monitoring</span></span>
<span data-ttu-id="b3e57-137"><a name="configure_test_devices"> </a></span><span class="sxs-lookup"><span data-stu-id="b3e57-137"><a name="configure_test_devices"> </a></span></span>

<span data-ttu-id="b3e57-138">您需要准备 :::no-loc text="Log Analytics"::: 能够监视 :::no-loc text="Microsoft Teams Rooms"::: 相关事件。</span><span class="sxs-lookup"><span data-stu-id="b3e57-138">You need to prepare :::no-loc text="Log Analytics"::: to be able to monitor :::no-loc text="Microsoft Teams Rooms":::–related events.</span></span> <span data-ttu-id="b3e57-139">首先，你需要将 :::no-loc text="Microsoft Monitoring"::: 代理部署到 :::no-loc text="Microsoft Teams Rooms"::: 你具有物理访问权限的一个或两个设备，并且让这些测试设备生成一些数据并将其推送到 :::no-loc text="Log Analytics"::: 工作区。</span><span class="sxs-lookup"><span data-stu-id="b3e57-139">To start with, you need to deploy :::no-loc text="Microsoft Monitoring"::: agents to just one or two :::no-loc text="Microsoft Teams Rooms"::: devices that you have physical access to, and get those test devices generate some data and push it to the :::no-loc text="Log Analytics"::: workspace.</span></span>

### <a name="install-no-loc-textmicrosoft-monitoring-agents-to-test-devices"></a><span data-ttu-id="b3e57-140">安装 :::no-loc text="Microsoft Monitoring"::: 代理以测试设备</span><span class="sxs-lookup"><span data-stu-id="b3e57-140">Install :::no-loc text="Microsoft Monitoring"::: agents to test devices</span></span>

<span data-ttu-id="b3e57-141">:::no-loc text="Microsoft Monitoring":::使用 "[将 :::no-loc text="Windows"::: 计算机连接到" :::no-loc text="Log Analytics"::: 服务 :::no-loc text="Azure"::: ](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows)中提供的说明将代理部署到测试设备。</span><span class="sxs-lookup"><span data-stu-id="b3e57-141">Deploy the :::no-loc text="Microsoft Monitoring"::: agent to the test devices by using the instructions provided in [Connect :::no-loc text="Windows"::: computers to the :::no-loc text="Log Analytics"::: service in :::no-loc text="Azure":::](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows).</span></span> <span data-ttu-id="b3e57-142">本文提供有关部署代理的步骤的详细信息 :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Windows"::: 、获取 :::no-loc text="Log Analytics"::: ***工作区 ID*** 的说明和用于获取连接到部署的设备的 ***主键*** ， :::no-loc text="Microsoft Teams Rooms"::: 以及用于 :::no-loc text="Azure Monitor"::: 验证代理连接实例的步骤 :::no-loc text="Log Analytics"::: 。</span><span class="sxs-lookup"><span data-stu-id="b3e57-142">This article provides detailed information about the steps for deploying :::no-loc text="Microsoft Monitoring"::: Agent for :::no-loc text="Windows":::, instructions for obtaining the :::no-loc text="Log Analytics"::: ***Workspace ID*** and the ***primary key*** to get :::no-loc text="Microsoft Teams Rooms"::: devices connected to your :::no-loc text="Azure Monitor"::: deployment, and steps to verify agent connectivity to :::no-loc text="Log Analytics"::: instance.</span></span>

### <a name="generate-sample-no-loc-textmicrosoft-teams-rooms-events"></a><span data-ttu-id="b3e57-143">生成示例 :::no-loc text="Microsoft Teams Rooms"::: 事件</span><span class="sxs-lookup"><span data-stu-id="b3e57-143">Generate sample :::no-loc text="Microsoft Teams Rooms"::: events</span></span>

<span data-ttu-id="b3e57-144">将 :::no-loc text="Microsoft Monitoring"::: 代理部署到测试设备后，验证所需的事件日志数据是否由收集 :::no-loc text="Azure Monitor"::: 。</span><span class="sxs-lookup"><span data-stu-id="b3e57-144">After the :::no-loc text="Microsoft Monitoring"::: agent is deployed onto the test devices, verify that the required event log data is collected by :::no-loc text="Azure Monitor":::.</span></span>

> [!NOTE]
> <span data-ttu-id="b3e57-145">安装代理后重新启动设备 :::no-loc text="Microsoft Monitoring"::: ，并确保 :::no-loc text="Microsoft Teams Rooms"::: 启动会议应用，以便它可以在事件日志中生成新事件。</span><span class="sxs-lookup"><span data-stu-id="b3e57-145">Reboot the device after the installation of the :::no-loc text="Microsoft Monitoring"::: agent, and make sure that :::no-loc text="Microsoft Teams Rooms"::: Meeting app is started, so that it can generate new events into the Event Log.</span></span>

1.  <span data-ttu-id="b3e57-146">登录[ :::no-loc text="Microsoft Azure"::: 门户](https://portal.azure.com)并转到 :::no-loc text="Log Analytics"::: 并选择您的工作区。</span><span class="sxs-lookup"><span data-stu-id="b3e57-146">Sign in to the [:::no-loc text="Microsoft Azure"::: portal](https://portal.azure.com) and go to :::no-loc text="Log Analytics"::: and select your workspace.</span></span>

2.  <span data-ttu-id="b3e57-147">列出设备生成的检测信号事件 :::no-loc text="Microsoft Teams Rooms"::: ：</span><span class="sxs-lookup"><span data-stu-id="b3e57-147">List the heartbeat events generated by a :::no-loc text="Microsoft Teams Rooms"::: device:</span></span>
    1.  <span data-ttu-id="b3e57-148">选择您的工作区并转到 " **日志** " 并使用查询来检索包含自定义字段的检测信号记录 :::no-loc text="Microsoft Teams Rooms"::: 。</span><span class="sxs-lookup"><span data-stu-id="b3e57-148">Select your workspace and go to **Logs** and use a query to retrieve the heartbeat records that will have the custom fields for :::no-loc text="Microsoft Teams Rooms":::.</span></span>
    2.  <span data-ttu-id="b3e57-149">示例查询： `Event | where Source == "SRS-App" and EventID == 2000`</span><span class="sxs-lookup"><span data-stu-id="b3e57-149">Sample query: `Event | where Source == "SRS-App" and EventID == 2000`</span></span>

3.  <span data-ttu-id="b3e57-150">请确保查询返回包含会议应用生成的事件的日志记录 :::no-loc text="Microsoft Teams Rooms"::: 。</span><span class="sxs-lookup"><span data-stu-id="b3e57-150">Make sure that the query returns log records that include events generated by the :::no-loc text="Microsoft Teams Rooms"::: meetings app.</span></span>

4.  <span data-ttu-id="b3e57-151">生成硬件问题，并验证是否已登录所需的事件 :::no-loc text="Azure Log Analytics"::: 。</span><span class="sxs-lookup"><span data-stu-id="b3e57-151">Generate a hardware issue, and validate that the required events are logged in :::no-loc text="Azure Log Analytics":::.</span></span>
    1.  <span data-ttu-id="b3e57-152">拔下测试系统上的其中一个外围设备 :::no-loc text="Microsoft Teams Rooms"::: 。</span><span class="sxs-lookup"><span data-stu-id="b3e57-152">Unplug one of the peripheral devices on the test :::no-loc text="Microsoft Teams Rooms"::: system.</span></span> <span data-ttu-id="b3e57-153">这可能是相机、话筒、麦克风或前置房间显示</span><span class="sxs-lookup"><span data-stu-id="b3e57-153">This could be the camera, speakerphone, microphone, or Front Room Display</span></span>
    2.  <span data-ttu-id="b3e57-154">等待10分钟，以便填充事件日志 :::no-loc text="Azure Log Analytics"::: 。</span><span class="sxs-lookup"><span data-stu-id="b3e57-154">Wait 10 minutes for the event log to be populated in :::no-loc text="Azure Log Analytics":::.</span></span>
    3.  <span data-ttu-id="b3e57-155">使用查询列出硬件错误事件： `Event | where Source == "SRS-App" and EventID == 3001`</span><span class="sxs-lookup"><span data-stu-id="b3e57-155">Use a query to list hardware error events: `Event | where Source == "SRS-App" and EventID == 3001`</span></span>

5.  <span data-ttu-id="b3e57-156">生成应用程序问题，并验证是否已记录所需的事件。</span><span class="sxs-lookup"><span data-stu-id="b3e57-156">Generate an application issue, and validate that the required events are logged.</span></span>
    1.  <span data-ttu-id="b3e57-157">修改 :::no-loc text="Microsoft Teams Rooms"::: 应用程序配置，并键入不正确的会话初始协议 (SIP) 地址/密码对。</span><span class="sxs-lookup"><span data-stu-id="b3e57-157">Modify :::no-loc text="Microsoft Teams Rooms"::: application configuration, and type an incorrect Session Initiation Protocol (SIP) address/password pair.</span></span>
    2.  <span data-ttu-id="b3e57-158">等待10分钟，以便填充事件日志 :::no-loc text="Azure Log Analytics"::: 。</span><span class="sxs-lookup"><span data-stu-id="b3e57-158">Wait 10 minutes for the event log to be populated in :::no-loc text="Azure Log Analytics":::.</span></span>
    3.  <span data-ttu-id="b3e57-159">使用查询列出应用程序错误事件： `Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`</span><span class="sxs-lookup"><span data-stu-id="b3e57-159">Use a query to list application error events: `Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b3e57-160">在可以配置自定义字段之前，需要这些示例事件日志。</span><span class="sxs-lookup"><span data-stu-id="b3e57-160">These sample event logs are required before custom fields can be configured.</span></span> <span data-ttu-id="b3e57-161">不要继续执行下一步操作，直到收集了所需的事件日志。</span><span class="sxs-lookup"><span data-stu-id="b3e57-161">Don't proceed to the next step until you have collected the required event logs.</span></span>

## <a name="map-custom-fields"></a><span data-ttu-id="b3e57-162">映射自定义字段</span><span class="sxs-lookup"><span data-stu-id="b3e57-162">Map custom fields</span></span>
<span data-ttu-id="b3e57-163"><a name="Custom_fields"> </a></span><span class="sxs-lookup"><span data-stu-id="b3e57-163"><a name="Custom_fields"> </a></span></span>

<span data-ttu-id="b3e57-164">使用自定义域从事件日志中提取特定数据。</span><span class="sxs-lookup"><span data-stu-id="b3e57-164">You use custom fields to extract specific data from the event logs.</span></span> <span data-ttu-id="b3e57-165">你需要定义稍后将用于你的磁贴、仪表板视图和通知的自定义字段。</span><span class="sxs-lookup"><span data-stu-id="b3e57-165">You need to define custom fields that will be used later with your tiles, dashboard views, and alerts.</span></span> <span data-ttu-id="b3e57-166">在开始创建自定义字段之前，请参阅[中 :::no-loc text="Log Analytics"::: 的自定义字段](https://docs.microsoft.com/azure/azure-monitor/platform/custom-fields)并熟悉概念。</span><span class="sxs-lookup"><span data-stu-id="b3e57-166">See [Custom fields in :::no-loc text="Log Analytics":::](https://docs.microsoft.com/azure/azure-monitor/platform/custom-fields) and become familiar with the concepts before you start creating your custom fields.</span></span>

<span data-ttu-id="b3e57-167">若要从捕获的事件日志中提取自定义域，请按照下列步骤操作：</span><span class="sxs-lookup"><span data-stu-id="b3e57-167">To extract your custom fields out of the captured event logs, follow these steps:</span></span>

1.  <span data-ttu-id="b3e57-168">登录[ :::no-loc text="Microsoft Azure"::: 门户](https://portal.azure.com)并转到 :::no-loc text="Log Analytics"::: 并选择您的工作区。</span><span class="sxs-lookup"><span data-stu-id="b3e57-168">Sign in to the [:::no-loc text="Microsoft Azure"::: portal](https://portal.azure.com) and go to :::no-loc text="Log Analytics"::: and select your workspace.</span></span>

2. <span data-ttu-id="b3e57-169">列出设备生成的事件 :::no-loc text="Microsoft Teams Rooms"::: ：</span><span class="sxs-lookup"><span data-stu-id="b3e57-169">List the events generated by a :::no-loc text="Microsoft Teams Rooms"::: device:</span></span>
   1.  <span data-ttu-id="b3e57-170">转到 " **日志** " 并使用查询检索将具有自定义字段的记录。</span><span class="sxs-lookup"><span data-stu-id="b3e57-170">Go to **Logs** and use a query to retrieve the records that will have the custom field.</span></span>
   2.  <span data-ttu-id="b3e57-171">示例查询： `Event | where Source == "SRS-App" and EventID == 2000`</span><span class="sxs-lookup"><span data-stu-id="b3e57-171">Sample query: `Event | where Source == "SRS-App" and EventID == 2000`</span></span>

3. <span data-ttu-id="b3e57-172">选择其中一个记录，选择左侧的按钮，然后启动 "字段提取向导"。</span><span class="sxs-lookup"><span data-stu-id="b3e57-172">Select one of the records, select the button to the left, and start the field extraction wizard.</span></span>
4. <span data-ttu-id="b3e57-173">突出显示要从 RenderedDescription 中提取的数据，并提供字段标题。</span><span class="sxs-lookup"><span data-stu-id="b3e57-173">Highlight the data you'd like to extract from the RenderedDescription and provide a Field Title.</span></span> <span data-ttu-id="b3e57-174">表1中提供了应使用的字段名称。</span><span class="sxs-lookup"><span data-stu-id="b3e57-174">The field names that you should use are provided in Table 1.</span></span>
5. <span data-ttu-id="b3e57-175">使用 *表 1*中所示的映射。</span><span class="sxs-lookup"><span data-stu-id="b3e57-175">Use the mappings shown in *Table 1*.</span></span> <span data-ttu-id="b3e57-176">:::no-loc text="Log Analytics":::定义新字段时，将自动追加\*\* \_ CF\*\*字符串。</span><span class="sxs-lookup"><span data-stu-id="b3e57-176">:::no-loc text="Log Analytics"::: will automatically append the **\_CF** string when you define the new field.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b3e57-177">请记住，所有 JSON 和 :::no-loc text="Log Analytics"::: 字段都区分大小写。</span><span class="sxs-lookup"><span data-stu-id="b3e57-177">Remember that all JSON and :::no-loc text="Log Analytics"::: fields are case-sensitive.</span></span>
> 
> <span data-ttu-id="b3e57-178">请注意下表中每个自定义域所需的查询。</span><span class="sxs-lookup"><span data-stu-id="b3e57-178">Pay attention to the queries required for each custom field in the table below.</span></span> <span data-ttu-id="b3e57-179">您需要使用正确的查询 :::no-loc text="Log Analytics"::: 来成功提取自定义域值。</span><span class="sxs-lookup"><span data-stu-id="b3e57-179">You need to use the correct queries for :::no-loc text="Log Analytics"::: to successfully extract custom field values.</span></span>
> 
<span data-ttu-id="b3e57-180">**表1**</span><span class="sxs-lookup"><span data-stu-id="b3e57-180">**Table 1**</span></span>

| <span data-ttu-id="b3e57-181">**JSON 字段**</span><span class="sxs-lookup"><span data-stu-id="b3e57-181">**JSON field**</span></span>                   | <span data-ttu-id="b3e57-182">**:::no-loc text="Log Analytics"::: 自定义域**</span><span class="sxs-lookup"><span data-stu-id="b3e57-182">**:::no-loc text="Log Analytics"::: custom field**</span></span> | <span data-ttu-id="b3e57-183">**事件 ID**</span><span class="sxs-lookup"><span data-stu-id="b3e57-183">**Event ID**</span></span> | <span data-ttu-id="b3e57-184">**要与提取一起使用的查询**</span><span class="sxs-lookup"><span data-stu-id="b3e57-184">**Query to use with the extraction**</span></span>                   |
|:---------------------------------|:-------------------------------|:-------------|:-------------------------------------------------------|
| <span data-ttu-id="b3e57-185">说明</span><span class="sxs-lookup"><span data-stu-id="b3e57-185">Description</span></span>                      | <span data-ttu-id="b3e57-186">SRSEventDescription</span><span class="sxs-lookup"><span data-stu-id="b3e57-186">SRSEventDescription</span></span>         | <span data-ttu-id="b3e57-187">**2000**</span><span class="sxs-lookup"><span data-stu-id="b3e57-187">**2000**</span></span>     | <span data-ttu-id="b3e57-188">\|源 = = "SRS-App" 和 EventID = = 2000 的事件</span><span class="sxs-lookup"><span data-stu-id="b3e57-188">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="b3e57-189">ResourceState</span><span class="sxs-lookup"><span data-stu-id="b3e57-189">ResourceState</span></span>                    | <span data-ttu-id="b3e57-190">SRSResourceState</span><span class="sxs-lookup"><span data-stu-id="b3e57-190">SRSResourceState</span></span>            | <span data-ttu-id="b3e57-191">**2000**</span><span class="sxs-lookup"><span data-stu-id="b3e57-191">**2000**</span></span>     | <span data-ttu-id="b3e57-192">\|源 = = "SRS-App" 和 EventID = = 2000 的事件</span><span class="sxs-lookup"><span data-stu-id="b3e57-192">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="b3e57-193">OperationName</span><span class="sxs-lookup"><span data-stu-id="b3e57-193">OperationName</span></span>                    | <span data-ttu-id="b3e57-194">SRSOperationName</span><span class="sxs-lookup"><span data-stu-id="b3e57-194">SRSOperationName</span></span>            | <span data-ttu-id="b3e57-195">**2000**</span><span class="sxs-lookup"><span data-stu-id="b3e57-195">**2000**</span></span>     | <span data-ttu-id="b3e57-196">\|源 = = "SRS-App" 和 EventID = = 2000 的事件</span><span class="sxs-lookup"><span data-stu-id="b3e57-196">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="b3e57-197">OperationResult</span><span class="sxs-lookup"><span data-stu-id="b3e57-197">OperationResult</span></span>                  | <span data-ttu-id="b3e57-198">SRSOperationResult</span><span class="sxs-lookup"><span data-stu-id="b3e57-198">SRSOperationResult</span></span>          | <span data-ttu-id="b3e57-199">**2000**</span><span class="sxs-lookup"><span data-stu-id="b3e57-199">**2000**</span></span>     | <span data-ttu-id="b3e57-200">\|源 = = "SRS-App" 和 EventID = = 2000 的事件</span><span class="sxs-lookup"><span data-stu-id="b3e57-200">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="b3e57-201">OS</span><span class="sxs-lookup"><span data-stu-id="b3e57-201">OS</span></span>                               | <span data-ttu-id="b3e57-202">SRSOSVersion</span><span class="sxs-lookup"><span data-stu-id="b3e57-202">SRSOSVersion</span></span>                | <span data-ttu-id="b3e57-203">**2000**</span><span class="sxs-lookup"><span data-stu-id="b3e57-203">**2000**</span></span>     | <span data-ttu-id="b3e57-204">\|源 = = "SRS-App" 和 EventID = = 2000 的事件</span><span class="sxs-lookup"><span data-stu-id="b3e57-204">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="b3e57-205">OSVersion</span><span class="sxs-lookup"><span data-stu-id="b3e57-205">OSVersion</span></span>                        | <span data-ttu-id="b3e57-206">SRSOSLongVersion</span><span class="sxs-lookup"><span data-stu-id="b3e57-206">SRSOSLongVersion</span></span>            | <span data-ttu-id="b3e57-207">**2000**</span><span class="sxs-lookup"><span data-stu-id="b3e57-207">**2000**</span></span>     | <span data-ttu-id="b3e57-208">\|源 = = "SRS-App" 和 EventID = = 2000 的事件</span><span class="sxs-lookup"><span data-stu-id="b3e57-208">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="b3e57-209">别名</span><span class="sxs-lookup"><span data-stu-id="b3e57-209">Alias</span></span>                            | <span data-ttu-id="b3e57-210">SRSAlias</span><span class="sxs-lookup"><span data-stu-id="b3e57-210">SRSAlias</span></span>                    | <span data-ttu-id="b3e57-211">**2000**</span><span class="sxs-lookup"><span data-stu-id="b3e57-211">**2000**</span></span>     | <span data-ttu-id="b3e57-212">\|源 = = "SRS-App" 和 EventID = = 2000 的事件</span><span class="sxs-lookup"><span data-stu-id="b3e57-212">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="b3e57-213">DisplayName</span><span class="sxs-lookup"><span data-stu-id="b3e57-213">DisplayName</span></span>                      | <span data-ttu-id="b3e57-214">SRSDisplayName</span><span class="sxs-lookup"><span data-stu-id="b3e57-214">SRSDisplayName</span></span>              | <span data-ttu-id="b3e57-215">**2000**</span><span class="sxs-lookup"><span data-stu-id="b3e57-215">**2000**</span></span>     | <span data-ttu-id="b3e57-216">\|源 = = "SRS-App" 和 EventID = = 2000 的事件</span><span class="sxs-lookup"><span data-stu-id="b3e57-216">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="b3e57-217">AppVersion</span><span class="sxs-lookup"><span data-stu-id="b3e57-217">AppVersion</span></span>                       | <span data-ttu-id="b3e57-218">SRSAppVersion</span><span class="sxs-lookup"><span data-stu-id="b3e57-218">SRSAppVersion</span></span>               | <span data-ttu-id="b3e57-219">**2000**</span><span class="sxs-lookup"><span data-stu-id="b3e57-219">**2000**</span></span>     | <span data-ttu-id="b3e57-220">\|源 = = "SRS-App" 和 EventID = = 2000 的事件</span><span class="sxs-lookup"><span data-stu-id="b3e57-220">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="b3e57-221">IPv4Address</span><span class="sxs-lookup"><span data-stu-id="b3e57-221">IPv4Address</span></span>                      | <span data-ttu-id="b3e57-222">SRSIPv4Address</span><span class="sxs-lookup"><span data-stu-id="b3e57-222">SRSIPv4Address</span></span>              | <span data-ttu-id="b3e57-223">**2000**</span><span class="sxs-lookup"><span data-stu-id="b3e57-223">**2000**</span></span>     | <span data-ttu-id="b3e57-224">\|源 = = "SRS-App" 和 EventID = = 2000 的事件</span><span class="sxs-lookup"><span data-stu-id="b3e57-224">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="b3e57-225">IPv6Address</span><span class="sxs-lookup"><span data-stu-id="b3e57-225">IPv6Address</span></span>                      | <span data-ttu-id="b3e57-226">SRSIPv6Address</span><span class="sxs-lookup"><span data-stu-id="b3e57-226">SRSIPv6Address</span></span>              | <span data-ttu-id="b3e57-227">**2000**</span><span class="sxs-lookup"><span data-stu-id="b3e57-227">**2000**</span></span>     | <span data-ttu-id="b3e57-228">\|源 = = "SRS-App" 和 EventID = = 2000 的事件</span><span class="sxs-lookup"><span data-stu-id="b3e57-228">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="b3e57-229">会议麦克风状态</span><span class="sxs-lookup"><span data-stu-id="b3e57-229">Conference Microphone status</span></span>     | <span data-ttu-id="b3e57-230">SRSConfMicrophoneStatus</span><span class="sxs-lookup"><span data-stu-id="b3e57-230">SRSConfMicrophoneStatus</span></span>     | <span data-ttu-id="b3e57-231">**3001**</span><span class="sxs-lookup"><span data-stu-id="b3e57-231">**3001**</span></span>     | <span data-ttu-id="b3e57-232">\|源 = = "SRS-App" 和 EventID = = 3001 的事件</span><span class="sxs-lookup"><span data-stu-id="b3e57-232">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="b3e57-233">会议演讲者状态</span><span class="sxs-lookup"><span data-stu-id="b3e57-233">Conference Speaker status</span></span>        | <span data-ttu-id="b3e57-234">SRSConfSpeakerStatus</span><span class="sxs-lookup"><span data-stu-id="b3e57-234">SRSConfSpeakerStatus</span></span>        | <span data-ttu-id="b3e57-235">**3001**</span><span class="sxs-lookup"><span data-stu-id="b3e57-235">**3001**</span></span>     | <span data-ttu-id="b3e57-236">\|源 = = "SRS-App" 和 EventID = = 3001 的事件</span><span class="sxs-lookup"><span data-stu-id="b3e57-236">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="b3e57-237">默认扬声器状态</span><span class="sxs-lookup"><span data-stu-id="b3e57-237">Default Speaker status</span></span>           | <span data-ttu-id="b3e57-238">SRSDefaultSpeakerStatus</span><span class="sxs-lookup"><span data-stu-id="b3e57-238">SRSDefaultSpeakerStatus</span></span>     | <span data-ttu-id="b3e57-239">**3001**</span><span class="sxs-lookup"><span data-stu-id="b3e57-239">**3001**</span></span>     | <span data-ttu-id="b3e57-240">\|源 = = "SRS-App" 和 EventID = = 3001 的事件</span><span class="sxs-lookup"><span data-stu-id="b3e57-240">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="b3e57-241">相机状态</span><span class="sxs-lookup"><span data-stu-id="b3e57-241">Camera status</span></span>                    | <span data-ttu-id="b3e57-242">SRSCameraStatus</span><span class="sxs-lookup"><span data-stu-id="b3e57-242">SRSCameraStatus</span></span>             | <span data-ttu-id="b3e57-243">**3001**</span><span class="sxs-lookup"><span data-stu-id="b3e57-243">**3001**</span></span>     | <span data-ttu-id="b3e57-244">\|源 = = "SRS-App" 和 EventID = = 3001 的事件</span><span class="sxs-lookup"><span data-stu-id="b3e57-244">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="b3e57-245">房间前显示状态</span><span class="sxs-lookup"><span data-stu-id="b3e57-245">Front of Room Display status</span></span>     | <span data-ttu-id="b3e57-246">SRSFORDStatus</span><span class="sxs-lookup"><span data-stu-id="b3e57-246">SRSFORDStatus</span></span>               | <span data-ttu-id="b3e57-247">**3001**</span><span class="sxs-lookup"><span data-stu-id="b3e57-247">**3001**</span></span>     | <span data-ttu-id="b3e57-248">\|源 = = "SRS-App" 和 EventID = = 3001 的事件</span><span class="sxs-lookup"><span data-stu-id="b3e57-248">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="b3e57-249">运动传感器状态</span><span class="sxs-lookup"><span data-stu-id="b3e57-249">Motion Sensor status</span></span>             | <span data-ttu-id="b3e57-250">SRSMotionSensorStatus</span><span class="sxs-lookup"><span data-stu-id="b3e57-250">SRSMotionSensorStatus</span></span>       | <span data-ttu-id="b3e57-251">**3001**</span><span class="sxs-lookup"><span data-stu-id="b3e57-251">**3001**</span></span>     | <span data-ttu-id="b3e57-252">\|源 = = "SRS-App" 和 EventID = = 3001 的事件</span><span class="sxs-lookup"><span data-stu-id="b3e57-252">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="b3e57-253">HDMI 接收状态</span><span class="sxs-lookup"><span data-stu-id="b3e57-253">HDMI Ingest status</span></span>               | <span data-ttu-id="b3e57-254">SRSHDMIIngestStatus</span><span class="sxs-lookup"><span data-stu-id="b3e57-254">SRSHDMIIngestStatus</span></span>         | <span data-ttu-id="b3e57-255">**3001**</span><span class="sxs-lookup"><span data-stu-id="b3e57-255">**3001**</span></span>     | <span data-ttu-id="b3e57-256">\|源 = = "SRS-App" 和 EventID = = 3001 的事件</span><span class="sxs-lookup"><span data-stu-id="b3e57-256">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |


## <a name="define-the-no-loc-textmicrosoft-teams-rooms-views-in-no-loc-textlog-analytics"></a><span data-ttu-id="b3e57-257">定义 :::no-loc text="Microsoft Teams Rooms"::: 视图 :::no-loc text="Log Analytics":::</span><span class="sxs-lookup"><span data-stu-id="b3e57-257">Define the :::no-loc text="Microsoft Teams Rooms"::: views in :::no-loc text="Log Analytics":::</span></span>
<span data-ttu-id="b3e57-258"><a name="Define_Views"> </a></span><span class="sxs-lookup"><span data-stu-id="b3e57-258"><a name="Define_Views"> </a></span></span>

<span data-ttu-id="b3e57-259">收集数据并映射自定义字段后，可以使用 "视图设计器" 开发一个仪表板，其中包含用于监视事件的各种磁贴 :::no-loc text="Microsoft Teams Rooms"::: 。</span><span class="sxs-lookup"><span data-stu-id="b3e57-259">After data is collected and custom fields are mapped, you can use View Designer to develop a dashboard containing various tiles to monitor :::no-loc text="Microsoft Teams Rooms"::: events.</span></span> <span data-ttu-id="b3e57-260">使用 "视图设计器" 创建以下图块。</span><span class="sxs-lookup"><span data-stu-id="b3e57-260">Use View Designer to create the following tiles.</span></span> <span data-ttu-id="b3e57-261">有关详细信息，请参阅[使用视图设计器 :::no-loc text="Log Analytics"::: 创建自定义视图](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer)</span><span class="sxs-lookup"><span data-stu-id="b3e57-261">For more information, see [Create custom views by using View Designer in :::no-loc text="Log Analytics":::](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer)</span></span>

> [!NOTE]
> <span data-ttu-id="b3e57-262">应完成本指南前面的步骤，仪表板图块才能正常工作。</span><span class="sxs-lookup"><span data-stu-id="b3e57-262">Previous steps in this guide should have been completed for the dashboard tiles to work properly.</span></span>

### <a name="create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method"></a><span data-ttu-id="b3e57-263">使用 import 方法创建 Microsoft 团队聊天室仪表板</span><span class="sxs-lookup"><span data-stu-id="b3e57-263">Create a Microsoft Teams Rooms dashboard by using the import method</span></span>

<span data-ttu-id="b3e57-264">您可以导入 :::no-loc text="Microsoft Teams Rooms"::: 仪表板并快速开始监视设备。</span><span class="sxs-lookup"><span data-stu-id="b3e57-264">You can import an :::no-loc text="Microsoft Teams Rooms"::: dashboard and start monitoring your devices quickly.</span></span> <span data-ttu-id="b3e57-265">执行以下步骤导入仪表板：</span><span class="sxs-lookup"><span data-stu-id="b3e57-265">Take the following steps to import the dashboard:</span></span>

1.  <span data-ttu-id="b3e57-266">获取 [SkypeRoomSystems_v2 的 omsview](https://go.microsoft.com/fwlink/?linkid=835675) 仪表板文件。</span><span class="sxs-lookup"><span data-stu-id="b3e57-266">Get the [SkypeRoomSystems_v2.omsview](https://go.microsoft.com/fwlink/?linkid=835675) dashboard file.</span></span>
2.  <span data-ttu-id="b3e57-267">登录[ :::no-loc text="Microsoft Azure"::: 门户](https://portal.azure.com)并转到 :::no-loc text="Log Analytics"::: 并选择您的工作区。</span><span class="sxs-lookup"><span data-stu-id="b3e57-267">Sign in to the [:::no-loc text="Microsoft Azure"::: portal](https://portal.azure.com) and go to :::no-loc text="Log Analytics"::: and select your workspace.</span></span>
3.  <span data-ttu-id="b3e57-268">打开 **视图设计器**。</span><span class="sxs-lookup"><span data-stu-id="b3e57-268">Open **View Designer**.</span></span>
4.  <span data-ttu-id="b3e57-269">选择 " **导入**"，然后选择 " **SkypeRoomSystems_v2 的 omsview** 文件。</span><span class="sxs-lookup"><span data-stu-id="b3e57-269">Select **Import**, and then select the **SkypeRoomSystems_v2.omsview** file.</span></span>
5.  <span data-ttu-id="b3e57-270">选择 " **保存**"。</span><span class="sxs-lookup"><span data-stu-id="b3e57-270">Select **Save**.</span></span>

### <a name="create-a-microsoft-teams-rooms-dashboard-manually"></a><span data-ttu-id="b3e57-271">手动创建 Microsoft 团队聊天室仪表板</span><span class="sxs-lookup"><span data-stu-id="b3e57-271">Create a Microsoft Teams Rooms dashboard manually</span></span>

<span data-ttu-id="b3e57-272">或者，你可以创建自己的仪表板并仅添加你希望监视的磁贴。</span><span class="sxs-lookup"><span data-stu-id="b3e57-272">Alternatively, you can create your own dashboard and add only the tiles that you wish to monitor.</span></span>

#### <a name="configure-the-overview-tile"></a><span data-ttu-id="b3e57-273">配置概述图块</span><span class="sxs-lookup"><span data-stu-id="b3e57-273">Configure the Overview Tile</span></span>

1.  <span data-ttu-id="b3e57-274">打开 **视图设计器**。</span><span class="sxs-lookup"><span data-stu-id="b3e57-274">Open **View Designer**.</span></span>
2.  <span data-ttu-id="b3e57-275">选择 " **概述图块**"，然后从库中选择 **两个数字** 。</span><span class="sxs-lookup"><span data-stu-id="b3e57-275">Select **Overview Tile**, and then select **Two numbers** from the gallery.</span></span>
3.  <span data-ttu-id="b3e57-276">命名磁贴 **:::no-loc text="Microsoft Teams Rooms":::** 。</span><span class="sxs-lookup"><span data-stu-id="b3e57-276">Name the tile **:::no-loc text="Microsoft Teams Rooms":::**.</span></span>
4.  <span data-ttu-id="b3e57-277">定义 **第一个图块**：</span><span class="sxs-lookup"><span data-stu-id="b3e57-277">Define the **First Tile**:</span></span><br>
    <span data-ttu-id="b3e57-278">**图例：** 在上个月内至少发送过一次检测信号的设备</span><span class="sxs-lookup"><span data-stu-id="b3e57-278">**Legend:** Devices that sent a heartbeat at least once within the last month</span></span><br>
    <span data-ttu-id="b3e57-279">**查询：**```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```</span><span class="sxs-lookup"><span data-stu-id="b3e57-279">**Query:** ```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```</span></span>
5.  <span data-ttu-id="b3e57-280">定义 **第二个图块**：</span><span class="sxs-lookup"><span data-stu-id="b3e57-280">Define the **Second Tile**:</span></span><br>
    <span data-ttu-id="b3e57-281">**图例：** 在过去一小时内发送检测信号的活动设备</span><span class="sxs-lookup"><span data-stu-id="b3e57-281">**Legend:** Active devices that sent a heartbeat within the last hour</span></span><br>
    <span data-ttu-id="b3e57-282">**查询：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```</span><span class="sxs-lookup"><span data-stu-id="b3e57-282">**Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```</span></span>
6.  <span data-ttu-id="b3e57-283">选择 " **应用**"。</span><span class="sxs-lookup"><span data-stu-id="b3e57-283">Select **Apply**.</span></span>

### <a name="create-a-tile-that-displays-active-devices"></a><span data-ttu-id="b3e57-284">创建显示活动设备的磁贴</span><span class="sxs-lookup"><span data-stu-id="b3e57-284">Create a tile that displays active devices</span></span>

1.  <span data-ttu-id="b3e57-285">选择 " **查看仪表板** " 以开始添加磁贴。</span><span class="sxs-lookup"><span data-stu-id="b3e57-285">Select **View Dashboard** to start adding your tiles.</span></span>
2.  <span data-ttu-id="b3e57-286">从库中选择 "**编号" & 列表**</span><span class="sxs-lookup"><span data-stu-id="b3e57-286">Select **Number & list** from the gallery</span></span>
3.  <span data-ttu-id="b3e57-287">定义 **常规** 属性：</span><span class="sxs-lookup"><span data-stu-id="b3e57-287">Define the **General** properties:</span></span><br>
    <span data-ttu-id="b3e57-288">**组标题：** 检测信号状态</span><span class="sxs-lookup"><span data-stu-id="b3e57-288">**Group Title:** Heartbeat Status</span></span><br>
    <span data-ttu-id="b3e57-289">**新组：** 处于</span><span class="sxs-lookup"><span data-stu-id="b3e57-289">**New Group:** Selected</span></span>
4.  <span data-ttu-id="b3e57-290">定义 **图块** 属性：</span><span class="sxs-lookup"><span data-stu-id="b3e57-290">Define the **Tile** properties:</span></span><br>
    <span data-ttu-id="b3e57-291">**图例：** 最近20分钟内发送 (检测信号的活动设备) </span><span class="sxs-lookup"><span data-stu-id="b3e57-291">**Legend:** Active devices (heartbeat sent in the last 20 minutes)</span></span><br>
    <span data-ttu-id="b3e57-292">**图块查询：** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```</span><span class="sxs-lookup"><span data-stu-id="b3e57-292">**Tile Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```</span></span>
5.  <span data-ttu-id="b3e57-293">定义 **列表** 属性：</span><span class="sxs-lookup"><span data-stu-id="b3e57-293">Define the **List** properties:</span></span><br>
    <span data-ttu-id="b3e57-294">**列表查询：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span><span class="sxs-lookup"><span data-stu-id="b3e57-294">**List Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span></span>
6.  <span data-ttu-id="b3e57-295">定义 **列标题**：</span><span class="sxs-lookup"><span data-stu-id="b3e57-295">Define **Column Titles**:</span></span><br>
    <span data-ttu-id="b3e57-296">**名称：** 计算机名</span><span class="sxs-lookup"><span data-stu-id="b3e57-296">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="b3e57-297">**值：** 上次检测信号</span><span class="sxs-lookup"><span data-stu-id="b3e57-297">**Value:** Last Heartbeat</span></span>
7.  <span data-ttu-id="b3e57-298">定义 **导航查询**。</span><span class="sxs-lookup"><span data-stu-id="b3e57-298">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  <span data-ttu-id="b3e57-299">选择 " **应用**"，然后单击 " **关闭**"。</span><span class="sxs-lookup"><span data-stu-id="b3e57-299">Select **Apply**, and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-devices-that-have-connectivity-issues"></a><span data-ttu-id="b3e57-300">创建显示有连接问题的设备的磁贴</span><span class="sxs-lookup"><span data-stu-id="b3e57-300">Create a tile that displays devices that have connectivity issues</span></span>

1.  <span data-ttu-id="b3e57-301">从库中选择 " **编号" & 列表** ，然后添加新磁贴。</span><span class="sxs-lookup"><span data-stu-id="b3e57-301">Select **Number & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="b3e57-302">定义 **常规** 属性：</span><span class="sxs-lookup"><span data-stu-id="b3e57-302">Define the **General** properties:</span></span><br>
    <span data-ttu-id="b3e57-303">**组标题：** 留空</span><span class="sxs-lookup"><span data-stu-id="b3e57-303">**Group Title:** Leave empty</span></span><br>
    <span data-ttu-id="b3e57-304">**新组：** 未选中</span><span class="sxs-lookup"><span data-stu-id="b3e57-304">**New Group:** Not Selected</span></span>
3.  <span data-ttu-id="b3e57-305">定义 **图块** 属性：</span><span class="sxs-lookup"><span data-stu-id="b3e57-305">Define the **Tile** properties:</span></span><br>
    <span data-ttu-id="b3e57-306">**图例：** 非活动设备 (最近20分钟内发送的心跳消息) </span><span class="sxs-lookup"><span data-stu-id="b3e57-306">**Legend:** Inactive Devices (no heartbeat message sent in the last 20 minutes)</span></span><br>
    <span data-ttu-id="b3e57-307">**图块查询：** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```</span><span class="sxs-lookup"><span data-stu-id="b3e57-307">**Tile Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```</span></span>
4.  <span data-ttu-id="b3e57-308">定义 **列表** 属性：</span><span class="sxs-lookup"><span data-stu-id="b3e57-308">Define the **List** properties:</span></span><br>
    <span data-ttu-id="b3e57-309">**列表查询：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```</span><span class="sxs-lookup"><span data-stu-id="b3e57-309">**List Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```</span></span>
5.  <span data-ttu-id="b3e57-310">定义 **列标题**：</span><span class="sxs-lookup"><span data-stu-id="b3e57-310">Define **Column Titles**:</span></span><br>
    <span data-ttu-id="b3e57-311">**名称：** 计算机名</span><span class="sxs-lookup"><span data-stu-id="b3e57-311">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="b3e57-312">**值：** 上次检测信号</span><span class="sxs-lookup"><span data-stu-id="b3e57-312">**Value:** Last Heartbeat</span></span>
6.  <span data-ttu-id="b3e57-313">定义 **导航查询**：</span><span class="sxs-lookup"><span data-stu-id="b3e57-313">Define **Navigation Query**:</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  <span data-ttu-id="b3e57-314">选择 " **应用**"，然后单击 " **关闭**"。</span><span class="sxs-lookup"><span data-stu-id="b3e57-314">Select **Apply**, and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-devices-that-have-a-hardware-error"></a><span data-ttu-id="b3e57-315">创建显示硬件出现错误的设备的磁贴</span><span class="sxs-lookup"><span data-stu-id="b3e57-315">Create a tile that displays devices that have a hardware error</span></span>

1.  <span data-ttu-id="b3e57-316">从库中选择 " **编号" & 列表** ，然后添加新磁贴。</span><span class="sxs-lookup"><span data-stu-id="b3e57-316">Select **Number & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="b3e57-317">定义 **常规** 属性：</span><span class="sxs-lookup"><span data-stu-id="b3e57-317">Define the **General** properties:</span></span><br>
    <span data-ttu-id="b3e57-318">**组标题：** 硬件状态</span><span class="sxs-lookup"><span data-stu-id="b3e57-318">**Group Title:** Hardware Status</span></span><br>
    <span data-ttu-id="b3e57-319">**新组：** 处于</span><span class="sxs-lookup"><span data-stu-id="b3e57-319">**New Group:** Selected</span></span>
3.  <span data-ttu-id="b3e57-320">定义 **图块** 属性：</span><span class="sxs-lookup"><span data-stu-id="b3e57-320">Define the **Tile** properties:</span></span><br>
    <span data-ttu-id="b3e57-321">**图例：** 过去一小时内遇到硬件错误的设备</span><span class="sxs-lookup"><span data-stu-id="b3e57-321">**Legend:** Devices that experienced a hardware error in the last hour</span></span><br>
    <span data-ttu-id="b3e57-322">**图块查询：** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```</span><span class="sxs-lookup"><span data-stu-id="b3e57-322">**Tile Query:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```</span></span>
4.  <span data-ttu-id="b3e57-323">定义 **列表** 属性：</span><span class="sxs-lookup"><span data-stu-id="b3e57-323">Define the **List** properties:</span></span><br>
    <span data-ttu-id="b3e57-324">**列表查询：**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span><span class="sxs-lookup"><span data-stu-id="b3e57-324">**List Query:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span></span>
5.  <span data-ttu-id="b3e57-325">定义 **列标题**：</span><span class="sxs-lookup"><span data-stu-id="b3e57-325">Define **Column Titles**:</span></span><br>
    <span data-ttu-id="b3e57-326">**名称：** 计算机名</span><span class="sxs-lookup"><span data-stu-id="b3e57-326">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="b3e57-327">**值：** 上一个错误</span><span class="sxs-lookup"><span data-stu-id="b3e57-327">**Value:** Last Error</span></span>
6.  <span data-ttu-id="b3e57-328">定义 **导航查询**：</span><span class="sxs-lookup"><span data-stu-id="b3e57-328">Define **Navigation Query**:</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 3001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  <span data-ttu-id="b3e57-329">选择 " **应用**"，然后单击 " **关闭**"。</span><span class="sxs-lookup"><span data-stu-id="b3e57-329">Select **Apply**, and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-operating-system-versions"></a><span data-ttu-id="b3e57-330">创建显示操作系统版本的磁贴 :::no-loc text="Microsoft Teams Rooms":::</span><span class="sxs-lookup"><span data-stu-id="b3e57-330">Create a tile that displays :::no-loc text="Microsoft Teams Rooms"::: Operating System versions</span></span>

1.  <span data-ttu-id="b3e57-331">从库中选择 " **同心圆 & 列表** "，然后添加新磁贴。</span><span class="sxs-lookup"><span data-stu-id="b3e57-331">Select **Donut & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="b3e57-332">定义 **常规** 属性：</span><span class="sxs-lookup"><span data-stu-id="b3e57-332">Define the **General** properties:</span></span><br>
    <span data-ttu-id="b3e57-333">**组标题：** 操作系统详细信息</span><span class="sxs-lookup"><span data-stu-id="b3e57-333">**Group Title:** Operating System details</span></span><br>
    <span data-ttu-id="b3e57-334">**新组：** 处于</span><span class="sxs-lookup"><span data-stu-id="b3e57-334">**New Group:** Selected</span></span>
3.  <span data-ttu-id="b3e57-335">定义 **页眉** 属性：</span><span class="sxs-lookup"><span data-stu-id="b3e57-335">Define the **Header** properties:</span></span><br>
    <span data-ttu-id="b3e57-336">**标题：** 操作系统版本</span><span class="sxs-lookup"><span data-stu-id="b3e57-336">**Title:** Operating System versions</span></span><br>
    <span data-ttu-id="b3e57-337">**副标题：** 运行特定操作系统版本的设备</span><span class="sxs-lookup"><span data-stu-id="b3e57-337">**Subtitle:** Devices running specific OS versions</span></span>
4.  <span data-ttu-id="b3e57-338">定义 **同心圆** 属性：</span><span class="sxs-lookup"><span data-stu-id="b3e57-338">Define the **Donut** properties:</span></span><br>
    <span data-ttu-id="b3e57-339">**查询：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize OS_Version = max(SRSOSLongVersion_CF) by Computer | summarize AggregatedValue = count() by OS_Version | sort by OS_Version asc```</span><span class="sxs-lookup"><span data-stu-id="b3e57-339">**Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize OS_Version = max(SRSOSLongVersion_CF) by Computer | summarize AggregatedValue = count() by OS_Version | sort by OS_Version asc```</span></span><br>
    <span data-ttu-id="b3e57-340">**文本居中：** 台</span><span class="sxs-lookup"><span data-stu-id="b3e57-340">**Center Text:** Devices</span></span><br>
    <span data-ttu-id="b3e57-341">**操作：** 量</span><span class="sxs-lookup"><span data-stu-id="b3e57-341">**Operation:** Sum</span></span>
5.  <span data-ttu-id="b3e57-342">定义 **列表** 属性。</span><span class="sxs-lookup"><span data-stu-id="b3e57-342">Define the **List** properties.</span></span><br>
    <span data-ttu-id="b3e57-343">**列表查询：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSOSLongVersion_CF = max(SRSOSLongVersion_CF) by Computer | sort by Computer asc```</span><span class="sxs-lookup"><span data-stu-id="b3e57-343">**List Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSOSLongVersion_CF = max(SRSOSLongVersion_CF) by Computer | sort by Computer asc```</span></span><br>
    <span data-ttu-id="b3e57-344">**隐藏图形：** 处于</span><span class="sxs-lookup"><span data-stu-id="b3e57-344">**Hide Graph:** Selected</span></span><br>
    <span data-ttu-id="b3e57-345">**启用迷你图：** 未选中</span><span class="sxs-lookup"><span data-stu-id="b3e57-345">**Enable Sparklines:** Not selected</span></span>
6.  <span data-ttu-id="b3e57-346">定义 **列标题**。</span><span class="sxs-lookup"><span data-stu-id="b3e57-346">Define **Column Titles**.</span></span><br>
    <span data-ttu-id="b3e57-347">**名称：** 计算机名</span><span class="sxs-lookup"><span data-stu-id="b3e57-347">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="b3e57-348">**值：** 留空</span><span class="sxs-lookup"><span data-stu-id="b3e57-348">**Value:** Leave Empty</span></span>
7.  <span data-ttu-id="b3e57-349">定义 **导航查询**。</span><span class="sxs-lookup"><span data-stu-id="b3e57-349">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  <span data-ttu-id="b3e57-350">选择 " **应用** "，然后选择 " **关闭**"。</span><span class="sxs-lookup"><span data-stu-id="b3e57-350">Select **Apply** and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-application-versions"></a><span data-ttu-id="b3e57-351">创建显示 :::no-loc text="Microsoft Teams Rooms"::: 应用程序版本的磁贴</span><span class="sxs-lookup"><span data-stu-id="b3e57-351">Create a tile that displays :::no-loc text="Microsoft Teams Rooms"::: application versions</span></span>

1.  <span data-ttu-id="b3e57-352">从库中选择 " **同心圆 & 列表** "，然后添加新磁贴。</span><span class="sxs-lookup"><span data-stu-id="b3e57-352">Select **Donut & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="b3e57-353">定义 **常规** 属性：</span><span class="sxs-lookup"><span data-stu-id="b3e57-353">Define the **General** properties:</span></span><br>
    <span data-ttu-id="b3e57-354">**组标题：** :::no-loc text="Microsoft Teams Rooms"::: 应用程序详细信息</span><span class="sxs-lookup"><span data-stu-id="b3e57-354">**Group Title:** :::no-loc text="Microsoft Teams Rooms"::: application details</span></span><br>
    <span data-ttu-id="b3e57-355">**新组：** 处于</span><span class="sxs-lookup"><span data-stu-id="b3e57-355">**New Group:** Selected</span></span>
3.  <span data-ttu-id="b3e57-356">定义 **页眉** 属性：</span><span class="sxs-lookup"><span data-stu-id="b3e57-356">Define the **Header** properties:</span></span><br>
    <span data-ttu-id="b3e57-357">**标题：** 应用程序版本</span><span class="sxs-lookup"><span data-stu-id="b3e57-357">**Title:** Application versions</span></span><br>
    <span data-ttu-id="b3e57-358">**副标题：** 运行特定应用程序版本的设备</span><span class="sxs-lookup"><span data-stu-id="b3e57-358">**Subtitle:** Devices running specific application versions</span></span>
4.  <span data-ttu-id="b3e57-359">定义 **同心圆** 属性：</span><span class="sxs-lookup"><span data-stu-id="b3e57-359">Define the **Donut** properties:</span></span><br>
    <span data-ttu-id="b3e57-360">**查询：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```</span><span class="sxs-lookup"><span data-stu-id="b3e57-360">**Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```</span></span><br>
    <span data-ttu-id="b3e57-361">**文本居中：** 台</span><span class="sxs-lookup"><span data-stu-id="b3e57-361">**Center Text:** Devices</span></span><br>
    <span data-ttu-id="b3e57-362">**操作：** 量</span><span class="sxs-lookup"><span data-stu-id="b3e57-362">**Operation:** Sum</span></span>
5.  <span data-ttu-id="b3e57-363">定义 **列表** 属性。</span><span class="sxs-lookup"><span data-stu-id="b3e57-363">Define the **List** properties.</span></span><br>
    <span data-ttu-id="b3e57-364">**列表查询：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```</span><span class="sxs-lookup"><span data-stu-id="b3e57-364">**List Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```</span></span><br>
    <span data-ttu-id="b3e57-365">**隐藏图形：** 处于</span><span class="sxs-lookup"><span data-stu-id="b3e57-365">**Hide Graph:** Selected</span></span><br>
    <span data-ttu-id="b3e57-366">**启用迷你图：** 未选中</span><span class="sxs-lookup"><span data-stu-id="b3e57-366">**Enable Sparklines:** Not selected</span></span>
6.  <span data-ttu-id="b3e57-367">定义 **列标题**。</span><span class="sxs-lookup"><span data-stu-id="b3e57-367">Define **Column Titles**.</span></span><br>
    <span data-ttu-id="b3e57-368">**名称：** 计算机名</span><span class="sxs-lookup"><span data-stu-id="b3e57-368">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="b3e57-369">**值：** 留空</span><span class="sxs-lookup"><span data-stu-id="b3e57-369">**Value:** Leave Empty</span></span>
7.  <span data-ttu-id="b3e57-370">定义 **导航查询**。</span><span class="sxs-lookup"><span data-stu-id="b3e57-370">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  <span data-ttu-id="b3e57-371">选择 " **应用** "，然后选择 " **关闭**"。</span><span class="sxs-lookup"><span data-stu-id="b3e57-371">Select **Apply** and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-devices-that-have-an-application-error"></a><span data-ttu-id="b3e57-372">创建显示有应用程序错误的设备的磁贴</span><span class="sxs-lookup"><span data-stu-id="b3e57-372">Create a tile that displays devices that have an application error</span></span>

1.  <span data-ttu-id="b3e57-373">从库中选择 " **编号" & 列表** ，然后添加新磁贴。</span><span class="sxs-lookup"><span data-stu-id="b3e57-373">Select **Number & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="b3e57-374">定义 **常规** 属性。</span><span class="sxs-lookup"><span data-stu-id="b3e57-374">Define the **General** properties.</span></span><br>
    <span data-ttu-id="b3e57-375">**组标题：** 留空</span><span class="sxs-lookup"><span data-stu-id="b3e57-375">**Group Title:** Leave empty</span></span><br>
    <span data-ttu-id="b3e57-376">**新组：** 未选中</span><span class="sxs-lookup"><span data-stu-id="b3e57-376">**New Group:** Not Selected</span></span>
3.  <span data-ttu-id="b3e57-377">定义 **图块** 属性。</span><span class="sxs-lookup"><span data-stu-id="b3e57-377">Define the **Tile** properties.</span></span><br>
    <span data-ttu-id="b3e57-378">**图例：** 过去一小时遇到应用程序错误的设备</span><span class="sxs-lookup"><span data-stu-id="b3e57-378">**Legend:** Devices that experienced an application error in the last hour</span></span><br>
    <span data-ttu-id="b3e57-379">**图块查询：** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```</span><span class="sxs-lookup"><span data-stu-id="b3e57-379">**Tile Query:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```</span></span>
4.  <span data-ttu-id="b3e57-380">定义 **列表** 属性。</span><span class="sxs-lookup"><span data-stu-id="b3e57-380">Define the **List** properties.</span></span><br>
    <span data-ttu-id="b3e57-381">**列表查询：**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span><span class="sxs-lookup"><span data-stu-id="b3e57-381">**List Query:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span></span>
5.  <span data-ttu-id="b3e57-382">定义 **列标题**。</span><span class="sxs-lookup"><span data-stu-id="b3e57-382">Define **Column Titles**.</span></span><br>
    <span data-ttu-id="b3e57-383">**名称：** 计算机名</span><span class="sxs-lookup"><span data-stu-id="b3e57-383">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="b3e57-384">**值：** 上一个错误</span><span class="sxs-lookup"><span data-stu-id="b3e57-384">**Value:** Last Error</span></span>
6.  <span data-ttu-id="b3e57-385">定义 **导航查询**。</span><span class="sxs-lookup"><span data-stu-id="b3e57-385">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 2001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  <span data-ttu-id="b3e57-386">选择 " **应用** "，然后选择 " **关闭**"。</span><span class="sxs-lookup"><span data-stu-id="b3e57-386">Select **Apply** and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-devices-that-have-been-restarted"></a><span data-ttu-id="b3e57-387">创建显示已重新启动的设备的磁贴</span><span class="sxs-lookup"><span data-stu-id="b3e57-387">Create a tile that displays devices that have been restarted</span></span>

1.  <span data-ttu-id="b3e57-388">从库中选择 " **编号" & 列表** ，然后添加新磁贴。</span><span class="sxs-lookup"><span data-stu-id="b3e57-388">Select **Number & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="b3e57-389">定义 **常规** 属性。</span><span class="sxs-lookup"><span data-stu-id="b3e57-389">Define the **General** properties.</span></span><br>
    <span data-ttu-id="b3e57-390">**组标题：** 留空</span><span class="sxs-lookup"><span data-stu-id="b3e57-390">**Group Title:** Leave empty</span></span><br>
    <span data-ttu-id="b3e57-391">**新组：** 未选中</span><span class="sxs-lookup"><span data-stu-id="b3e57-391">**New Group:** Not Selected</span></span>
3.  <span data-ttu-id="b3e57-392">定义 **图块** 属性。</span><span class="sxs-lookup"><span data-stu-id="b3e57-392">Define the **Tile** properties.</span></span><br>
    <span data-ttu-id="b3e57-393">**图例：** 在过去24小时内重新启动应用程序的设备以及重启次数</span><span class="sxs-lookup"><span data-stu-id="b3e57-393">**Legend:** Devices where the application was restarted in the last 24 hours, and number of restarts</span></span><br>
    <span data-ttu-id="b3e57-394">**图块查询：** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```</span><span class="sxs-lookup"><span data-stu-id="b3e57-394">**Tile Query:** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```</span></span>
4.  <span data-ttu-id="b3e57-395">定义 **列表** 属性。</span><span class="sxs-lookup"><span data-stu-id="b3e57-395">Define the **List** properties.</span></span><br>
    <span data-ttu-id="b3e57-396">**列表查询：**```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```</span><span class="sxs-lookup"><span data-stu-id="b3e57-396">**List Query:** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```</span></span>
5.  <span data-ttu-id="b3e57-397">定义 **列标题**。</span><span class="sxs-lookup"><span data-stu-id="b3e57-397">Define **Column Titles**.</span></span><br>
    <span data-ttu-id="b3e57-398">**名称：** 计算机名</span><span class="sxs-lookup"><span data-stu-id="b3e57-398">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="b3e57-399">**值：** 重启次数</span><span class="sxs-lookup"><span data-stu-id="b3e57-399">**Value:** Number of Restarts</span></span>
6.  <span data-ttu-id="b3e57-400">定义 **导航查询**。</span><span class="sxs-lookup"><span data-stu-id="b3e57-400">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  <span data-ttu-id="b3e57-401">选择 " **应用** "，然后选择 " **关闭**"。</span><span class="sxs-lookup"><span data-stu-id="b3e57-401">Select **Apply** and then **Close**.</span></span>
8.  <span data-ttu-id="b3e57-402">选择 " **保存** " 以保存仪表板。</span><span class="sxs-lookup"><span data-stu-id="b3e57-402">Select **Save** to save your dashboard.</span></span>

<span data-ttu-id="b3e57-403">现在，你已完成创建视图。</span><span class="sxs-lookup"><span data-stu-id="b3e57-403">Now you've completed creating your views.</span></span>

## <a name="configure-alerts-in-no-loc-textazure-monitor"></a><span data-ttu-id="b3e57-404">在中配置警报 :::no-loc text="Azure Monitor":::</span><span class="sxs-lookup"><span data-stu-id="b3e57-404">Configure Alerts in :::no-loc text="Azure Monitor":::</span></span>
<span data-ttu-id="b3e57-405"><a name="Alerts"> </a></span><span class="sxs-lookup"><span data-stu-id="b3e57-405"><a name="Alerts"> </a></span></span>

<span data-ttu-id="b3e57-406">:::no-loc text="Azure Monitor"::: 当控制台遇到问题时，可以引发通知以通知管理员 :::no-loc text="Microsoft Teams Rooms"::: 。</span><span class="sxs-lookup"><span data-stu-id="b3e57-406">:::no-loc text="Azure Monitor"::: can raise alerts to notify the administrators, when a :::no-loc text="Microsoft Teams Rooms"::: console encounters an issue.</span></span>

<span data-ttu-id="b3e57-407">:::no-loc text="Azure Monitor"::: 包括一种内置的警报机制，可按固定时间间隔通过计划的日志搜索进行运行。</span><span class="sxs-lookup"><span data-stu-id="b3e57-407">:::no-loc text="Azure Monitor"::: includes a built-in alerting mechanism that runs through scheduled log searches at regular intervals.</span></span> <span data-ttu-id="b3e57-408">如果日志搜索的结果符合某些特定条件，则会创建一条警告记录。</span><span class="sxs-lookup"><span data-stu-id="b3e57-408">If the results of the log search match some particular criteria, an alert record is created.</span></span>

<span data-ttu-id="b3e57-409">然后，该规则可以自动运行一个或多个操作，主动通知你警报或调用另一个进程。</span><span class="sxs-lookup"><span data-stu-id="b3e57-409">The rule can then automatically run one or more actions to proactively notify you of the alert or invoke another process.</span></span> <span data-ttu-id="b3e57-410">警报的可能选项如下：</span><span class="sxs-lookup"><span data-stu-id="b3e57-410">The possible options with alerts are:</span></span>
-   <span data-ttu-id="b3e57-411">发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="b3e57-411">Sending an email</span></span>
-   <span data-ttu-id="b3e57-412">通过 HTTP POST 请求调用外部进程</span><span class="sxs-lookup"><span data-stu-id="b3e57-412">Invoking an external process through an HTTP POST request</span></span>
-   <span data-ttu-id="b3e57-413">在服务中启动 runbook :::no-loc text="Azure Automation":::</span><span class="sxs-lookup"><span data-stu-id="b3e57-413">Starting a runbook in :::no-loc text="Azure Automation"::: service</span></span>

<span data-ttu-id="b3e57-414">有关中的警报的详细信息，请参阅[在中 :::no-loc text="Azure Monitor"::: 记录警报](https://docs.microsoft.com/azure/azure-monitor/platform/alerts-unified-log) :::no-loc text="Azure Monitor"::: 。</span><span class="sxs-lookup"><span data-stu-id="b3e57-414">See [Log alerts in :::no-loc text="Azure Monitor":::](https://docs.microsoft.com/azure/azure-monitor/platform/alerts-unified-log) to learn more about the alerts in :::no-loc text="Azure Monitor":::.</span></span>

> [!NOTE]
> <span data-ttu-id="b3e57-415">以下示例将在 :::no-loc text="Microsoft Teams Rooms"::: 设备生成硬件或应用程序错误时发送电子邮件警报。</span><span class="sxs-lookup"><span data-stu-id="b3e57-415">The following examples send email alerts when a :::no-loc text="Microsoft Teams Rooms"::: device generates a hardware or an application error.</span></span>

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-hardware-issues"></a><span data-ttu-id="b3e57-416">配置针对硬件问题的电子邮件警报 :::no-loc text="Microsoft Teams Rooms":::</span><span class="sxs-lookup"><span data-stu-id="b3e57-416">Configure an email alert for :::no-loc text="Microsoft Teams Rooms"::: hardware issues</span></span>

<span data-ttu-id="b3e57-417">配置检查 :::no-loc text="Microsoft Teams Rooms"::: 在过去一小时内遇到硬件问题的设备的警报规则。</span><span class="sxs-lookup"><span data-stu-id="b3e57-417">Configure an alert rule that checks for :::no-loc text="Microsoft Teams Rooms"::: devices that have encountered hardware issues within the last hour.</span></span>
1.  <span data-ttu-id="b3e57-418">登录[ :::no-loc text="Microsoft Azure"::: 门户](https://portal.azure.com)并转到 :::no-loc text="Log Analytics"::: 并选择您的工作区。</span><span class="sxs-lookup"><span data-stu-id="b3e57-418">Sign in to the [:::no-loc text="Microsoft Azure"::: portal](https://portal.azure.com) and go to :::no-loc text="Log Analytics"::: and select your workspace.</span></span>

2. <span data-ttu-id="b3e57-419">导航到您的 :::no-loc text="Log Analytics"::: 工作区并选择 "**通知**"，然后选择 "**新建通知规则**"</span><span class="sxs-lookup"><span data-stu-id="b3e57-419">Navigate to your :::no-loc text="Log Analytics"::: workspace and select **Alerts** and then select **New alert rule**</span></span>

3. <span data-ttu-id="b3e57-420">选择 "**添加条件**"，然后选择 "**自定义日志搜索**"</span><span class="sxs-lookup"><span data-stu-id="b3e57-420">Select **Add condition** and then **Custom log search**</span></span>

4.  <span data-ttu-id="b3e57-421">在 "搜索查询" 文本框中输入以下查询。</span><span class="sxs-lookup"><span data-stu-id="b3e57-421">Enter the following query to the Search query text box.</span></span><br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF
    |sort by TimeGenerated desc
    ```

5.  <span data-ttu-id="b3e57-422">配置警报逻辑设置：</span><span class="sxs-lookup"><span data-stu-id="b3e57-422">Configure the Alert logic settings:</span></span><br>
    <span data-ttu-id="b3e57-423">**基于：** 结果数</span><span class="sxs-lookup"><span data-stu-id="b3e57-423">**Based on:** Number of results</span></span><br>
    <span data-ttu-id="b3e57-424">**条件：** 大于</span><span class="sxs-lookup"><span data-stu-id="b3e57-424">**Condition:** Greater then</span></span><br>
    <span data-ttu-id="b3e57-425">**阈值：** 0</span><span class="sxs-lookup"><span data-stu-id="b3e57-425">**Threshold:** 0</span></span><br>

6. <span data-ttu-id="b3e57-426">配置评估设置，然后选择 " **完成**"：</span><span class="sxs-lookup"><span data-stu-id="b3e57-426">Configure Evaluation settings and select **Done**:</span></span> <br>
    <span data-ttu-id="b3e57-427">**周期 (分钟) ：** 60</span><span class="sxs-lookup"><span data-stu-id="b3e57-427">**Period (in minutes):** 60</span></span><br>
    <span data-ttu-id="b3e57-428">\*\* (分钟) ：60中的频率\*\*</span><span class="sxs-lookup"><span data-stu-id="b3e57-428">**Frequency (in minutes):** 60</span></span><br>

7. <span data-ttu-id="b3e57-429">配置操作组：</span><span class="sxs-lookup"><span data-stu-id="b3e57-429">Configure action groups:</span></span>
    1.  <span data-ttu-id="b3e57-430">选择 "**新建**"</span><span class="sxs-lookup"><span data-stu-id="b3e57-430">Select **Create New**</span></span>
    2.  <span data-ttu-id="b3e57-431">为 " *操作组名称* " 和 " *短名称* " 字段提供合适的名称。</span><span class="sxs-lookup"><span data-stu-id="b3e57-431">Provide suitable names for the *Action group name* and *Short Name* fields.</span></span>
    3.  <span data-ttu-id="b3e57-432">指定唯一的 *操作名称* ，选择 " **电子邮件/短信/短信/推/语音**"，然后选择 " **编辑详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="b3e57-432">Specify a unique *Action Name* and select **Email/SMS/Push/Voice**, and then select **Edit details**.</span></span>
    4.  <span data-ttu-id="b3e57-433">选择 " **电子邮件** " 复选框，并提供将接收通知的人员或组的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="b3e57-433">Select the **Email** checkbox and provide the email address of the person or group that will receive the alerts.</span></span>
    5.  <span data-ttu-id="b3e57-434">您还可以提供您的电话号码以接收短信通知、语音通话或同时获得这两者。</span><span class="sxs-lookup"><span data-stu-id="b3e57-434">You may also provide your phone number to get notified with SMS, a voice call or both.</span></span>
    6. <span data-ttu-id="b3e57-435">选择 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="b3e57-435">Select **OK**.</span></span>

8. <span data-ttu-id="b3e57-436">如果想要替代预警电子邮件的主题行，请**自定义操作**。</span><span class="sxs-lookup"><span data-stu-id="b3e57-436">**Customize Actions** if you like to override the subject line of the alert emails.</span></span>

9. <span data-ttu-id="b3e57-437">指定规则名称和说明。</span><span class="sxs-lookup"><span data-stu-id="b3e57-437">Specify a rule name and description.</span></span><br>
    <span data-ttu-id="b3e57-438">**规则名称：** :::no-loc text="Microsoft Teams Rooms"::: 硬件故障警报</span><span class="sxs-lookup"><span data-stu-id="b3e57-438">**Rule Name:** :::no-loc text="Microsoft Teams Rooms"::: Hardware Failure Alert</span></span><br>
    <span data-ttu-id="b3e57-439">**说明：** 过去一小时内遇到硬件问题的设备的列表</span><span class="sxs-lookup"><span data-stu-id="b3e57-439">**Description:** List of devices that encountered a hardware issue within the last hour</span></span><br>

10. <span data-ttu-id="b3e57-440">选择预期的严重性，并确保规则已启用。</span><span class="sxs-lookup"><span data-stu-id="b3e57-440">Select the intended severity and make sure the rule is enabled.</span></span>

11. <span data-ttu-id="b3e57-441">选择 " **创建通知规则**"。</span><span class="sxs-lookup"><span data-stu-id="b3e57-441">Select **Create alert rule**.</span></span>

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-application-issues"></a><span data-ttu-id="b3e57-442">为应用程序问题配置电子邮件警报 :::no-loc text="Microsoft Teams Rooms":::</span><span class="sxs-lookup"><span data-stu-id="b3e57-442">Configure an email alert for :::no-loc text="Microsoft Teams Rooms"::: application issues</span></span>

<span data-ttu-id="b3e57-443">重复相同的过程，但使用以下查询列出过去一小时内遇到的应用程序问题的设备。</span><span class="sxs-lookup"><span data-stu-id="b3e57-443">Repeat the same procedure but use the following query to list devices that have encountered application issues within the last hour.</span></span>

    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF
    | sort by TimeGenerated desc
    ```

<span data-ttu-id="b3e57-444">现在，你已完成定义通知。</span><span class="sxs-lookup"><span data-stu-id="b3e57-444">Now you've completed defining alerts.</span></span> <span data-ttu-id="b3e57-445">你可以使用上述示例定义其他警报。</span><span class="sxs-lookup"><span data-stu-id="b3e57-445">You can define additional alerts by using the examples above.</span></span>

<span data-ttu-id="b3e57-446">生成警报时，你将收到一封电子邮件，其中列出了在过去一小时内遇到问题的设备。</span><span class="sxs-lookup"><span data-stu-id="b3e57-446">When an alert is generated, you'll get an email that lists the devices that encountered an issue within the last hour.</span></span>

<span data-ttu-id="b3e57-447">![示例 :::no-loc text="Azure Monitor"::: 通知电子邮件] ( .。。/media/Deploy-Azure-Monitor-6.png " :::no-loc text="Azure Monitor"::: 通知电子邮件示例" ) </span><span class="sxs-lookup"><span data-stu-id="b3e57-447">![Sample :::no-loc text="Azure Monitor"::: alert email](../media/Deploy-Azure-Monitor-6.png "Sample :::no-loc text="Azure Monitor"::: alert email")</span></span>

## <a name="configure-all-devices-for-no-loc-textazure-monitoring"></a><span data-ttu-id="b3e57-448">配置所有设备 :::no-loc text="Azure Monitoring":::</span><span class="sxs-lookup"><span data-stu-id="b3e57-448">Configure all devices for :::no-loc text="Azure Monitoring":::</span></span>
<span data-ttu-id="b3e57-449"><a name="configure_all_devices"> </a>配置仪表板和警报后，您可以 :::no-loc text="Microsoft Monitoring"::: 在所有设备上设置和配置代理 :::no-loc text="Microsoft Teams Rooms"::: 以完成监视部署。</span><span class="sxs-lookup"><span data-stu-id="b3e57-449"><a name="configure_all_devices"> </a> After the dashboards and alerts are configured, you can set up and configure :::no-loc text="Microsoft Monitoring"::: agent on all :::no-loc text="Microsoft Teams Rooms"::: devices to complete your monitoring deployment.</span></span>

<span data-ttu-id="b3e57-450">虽然你可以 :::no-loc text="Microsoft Monitoring"::: 在每台设备上手动安装和配置代理，但我们强烈建议你充分利用现有软件部署工具和方法。</span><span class="sxs-lookup"><span data-stu-id="b3e57-450">Although you can install and configure the :::no-loc text="Microsoft Monitoring"::: agent manually on each device, we highly recommend you leverage existing software deployment tools and methods.</span></span>

<span data-ttu-id="b3e57-451">如果你是 :::no-loc text="Microsoft Teams Rooms"::: 首次生成设备，你可能希望将 :::no-loc text="Microsoft Monitoring"::: 代理设置和配置步骤包含在你的生成过程中。</span><span class="sxs-lookup"><span data-stu-id="b3e57-451">If you're building your :::no-loc text="Microsoft Teams Rooms"::: devices for the first time, you might want to include the :::no-loc text="Microsoft Monitoring"::: agent setup and configuration steps as part of your build process.</span></span> <span data-ttu-id="b3e57-452">有关详细信息，请参阅 [使用命令行安装代理](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line)。</span><span class="sxs-lookup"><span data-stu-id="b3e57-452">For more information, see [Install the agent using the command line](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line).</span></span>

### <a name="deploying-no-loc-textmicrosoft-monitoring-agent-by-using-a-group-policy-object-gpo"></a><span data-ttu-id="b3e57-453">:::no-loc text="Microsoft Monitoring":::使用组策略对象 (GPO) 部署代理</span><span class="sxs-lookup"><span data-stu-id="b3e57-453">Deploying :::no-loc text="Microsoft Monitoring"::: agent by using a Group Policy Object (GPO)</span></span>

<span data-ttu-id="b3e57-454">如果在实现之前已部署了 :::no-loc text="Microsoft Teams Rooms"::: 设备 :::no-loc text="Azure Monitoring"::: ，则可以使用提供的脚本通过 "组策略" 对象设置和配置代理 :::no-loc text="Active Directory"::: 。</span><span class="sxs-lookup"><span data-stu-id="b3e57-454">If you already deployed your :::no-loc text="Microsoft Teams Rooms"::: devices before you implement :::no-loc text="Azure Monitoring":::, you can use the provided script to set up and configure the agents by using :::no-loc text="Active Directory"::: group policy objects.</span></span>

1.  <span data-ttu-id="b3e57-455">创建共享网络路径并向 " **域计算机** " 组授予 "读取" 访问权限。</span><span class="sxs-lookup"><span data-stu-id="b3e57-455">Create a shared network path and grant read access to **Domain Computers** group.</span></span>

2.  <span data-ttu-id="b3e57-456">从下载64位版本的 :::no-loc text="Microsoft Monitoring"::: 代理 :::no-loc text="Windows":::<https://go.microsoft.com/fwlink/?LinkID=517476></span><span class="sxs-lookup"><span data-stu-id="b3e57-456">Download the 64-bit version of the :::no-loc text="Microsoft Monitoring"::: Agent for :::no-loc text="Windows"::: from <https://go.microsoft.com/fwlink/?LinkID=517476></span></span>

3.  <span data-ttu-id="b3e57-457">将安装程序包的内容提取到网络共享中。</span><span class="sxs-lookup"><span data-stu-id="b3e57-457">Extract the contents of the setup package into the network share.</span></span>
    1.  <span data-ttu-id="b3e57-458">打开命令提示符窗口，然后执行 **MMASetup-AMD64.exe/c**</span><span class="sxs-lookup"><span data-stu-id="b3e57-458">Open a Command Prompt window, and then execute **MMASetup-AMD64.exe /c**</span></span>
    2.  <span data-ttu-id="b3e57-459">指定刚刚创建的共享，然后提取内容。</span><span class="sxs-lookup"><span data-stu-id="b3e57-459">Specify the share you just created, and extract the content.</span></span>

4.  <span data-ttu-id="b3e57-460">创建新的组策略对象，并将其分配给 :::no-loc text="Microsoft Teams Rooms"::: 计算机帐户所在的组织单位。</span><span class="sxs-lookup"><span data-stu-id="b3e57-460">Create a new Group Policy Object and assign it to the organizational unit where :::no-loc text="Microsoft Teams Rooms"::: machine accounts are located.</span></span>

5.  <span data-ttu-id="b3e57-461">配置 PowerShell 执行策略：</span><span class="sxs-lookup"><span data-stu-id="b3e57-461">Configure PowerShell execution policy:</span></span>
    1.  <span data-ttu-id="b3e57-462">编辑新创建的组策略对象，并导航到 "计算机配置 \\ 策略" \\ 管理模板 \\ :::no-loc text="Windows"::: 组件 \\:::no-loc text="Windows PowerShell":::</span><span class="sxs-lookup"><span data-stu-id="b3e57-462">Edit the newly created Group Policy Object and navigate to Computer Configuration \\ Policies \\ Administrative Templates \\ :::no-loc text="Windows"::: Components \\ :::no-loc text="Windows PowerShell":::</span></span>
    2.  <span data-ttu-id="b3e57-463">启用 " **打开脚本执行** " 和 "设置 **执行策略** " 以 **允许本地脚本**。</span><span class="sxs-lookup"><span data-stu-id="b3e57-463">Enable the **Turn on Script Execution** and set **Execution Policy** to **Allow Local Scripts**.</span></span>

6.  <span data-ttu-id="b3e57-464">配置启动脚本：</span><span class="sxs-lookup"><span data-stu-id="b3e57-464">Configure the startup script:</span></span>
    1.  <span data-ttu-id="b3e57-465">复制以下脚本并将其另存为 Install-MMAgent.ps1。</span><span class="sxs-lookup"><span data-stu-id="b3e57-465">Copy the following script and save it as Install-MMAgent.ps1.</span></span>
    2.  <span data-ttu-id="b3e57-466">修改 WorkspaceId、WorkspaceKey 和 SetupPath 参数以匹配您的配置。</span><span class="sxs-lookup"><span data-stu-id="b3e57-466">Modify WorkspaceId, WorkspaceKey, and SetupPath parameters to match your configuration.</span></span>
    3.  <span data-ttu-id="b3e57-467">编辑相同的组策略对象并导航到 "计算机配置 \\ 策略 \\ :::no-loc text="Windows"::: 设置" \\ 脚本 (启动/关闭) </span><span class="sxs-lookup"><span data-stu-id="b3e57-467">Edit the same Group Policy Object and navigate to Computer Configuration \\ Policies \\ :::no-loc text="Windows"::: Settings \\ Scripts (Startup/Shutdown)</span></span>
    4.  <span data-ttu-id="b3e57-468">双击以选择 " **启动**"，然后选择 " **PowerShell 脚本**"。</span><span class="sxs-lookup"><span data-stu-id="b3e57-468">Double-click to select **Startup**, and then select **PowerShell Scripts**.</span></span>
    5.  <span data-ttu-id="b3e57-469">选择 " **显示文件**"，然后将 **Install-MMAgent.ps1** 文件复制到该文件夹。</span><span class="sxs-lookup"><span data-stu-id="b3e57-469">Select **Show Files**, and then copy the **Install-MMAgent.ps1** file to that folder.</span></span>
    6.  <span data-ttu-id="b3e57-470">选择 " **添加**"，然后单击 " **浏览**"。</span><span class="sxs-lookup"><span data-stu-id="b3e57-470">Select **Add**, and then **Browse**.</span></span>
    7.  <span data-ttu-id="b3e57-471">选择您刚刚复制的 ps1 脚本。</span><span class="sxs-lookup"><span data-stu-id="b3e57-471">Select the ps1 script you just copied.</span></span>

7.  <span data-ttu-id="b3e57-472">:::no-loc text="Microsoft Teams Rooms"::: 设备应 :::no-loc text="Microsoft Monitoring"::: 在第二次重启时安装和配置代理。</span><span class="sxs-lookup"><span data-stu-id="b3e57-472">:::no-loc text="Microsoft Teams Rooms"::: devices should install and configure the :::no-loc text="Microsoft Monitoring"::: agent with the second reboot.</span></span>

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
> <span data-ttu-id="b3e57-473">如果需要重新配置代理、将代理移到其他工作区或在初始安装后修改代理服务器设置，可以参阅 [管理和维护 :::no-loc text="Log Analytics"::: 代理](https://docs.microsoft.com/azure/azure-monitor/platform/agent-manage) 的文章。</span><span class="sxs-lookup"><span data-stu-id="b3e57-473">You can refer to the article [Managing and maintaining the :::no-loc text="Log Analytics"::: agent](https://docs.microsoft.com/azure/azure-monitor/platform/agent-manage) when you need to reconfigure an agent, move it to a different workspace, or modify proxy settings after the initial installation.</span></span>

## <a name="additional-solutions"></a><span data-ttu-id="b3e57-474">其他解决方案</span><span class="sxs-lookup"><span data-stu-id="b3e57-474">Additional Solutions</span></span>
<span data-ttu-id="b3e57-475"><a name="Solutions"> </a></span><span class="sxs-lookup"><span data-stu-id="b3e57-475"><a name="Solutions"> </a></span></span>

<span data-ttu-id="b3e57-476">:::no-loc text="Azure Monitor"::: 通过其 [解决方案库](https://docs.microsoft.com/azure/azure-monitor/insights/solutions) 提供内置管理解决方案，进一步帮助你监视你的环境。</span><span class="sxs-lookup"><span data-stu-id="b3e57-476">:::no-loc text="Azure Monitor"::: provides built-in management solutions through its [solution gallery](https://docs.microsoft.com/azure/azure-monitor/insights/solutions) to further help you monitor your environment.</span></span> <span data-ttu-id="b3e57-477">我们强烈建议你将[警报管理](https://docs.microsoft.com/azure/azure-monitor/platform/alert-management-solution)和[ :::no-loc text="Azure Log Analytics"::: 代理运行状况](https://docs.microsoft.com/azure/azure-monitor/insights/solution-agenthealth)解决方案添加到你的工作区。</span><span class="sxs-lookup"><span data-stu-id="b3e57-477">We highly recommend that you add [Alert Management](https://docs.microsoft.com/azure/azure-monitor/platform/alert-management-solution) and [:::no-loc text="Azure Log Analytics"::: Agent Health](https://docs.microsoft.com/azure/azure-monitor/insights/solution-agenthealth) solutions to your workspace as well.</span></span>

> [!NOTE]
> <span data-ttu-id="b3e57-478">代理运行状况解决方案可帮助你在你的环境内识别过时或损坏的 :::no-loc text="Microsoft Monitoring"::: 代理，并且警报管理解决方案提供有关在给定期间内引发的警报的详细信息。</span><span class="sxs-lookup"><span data-stu-id="b3e57-478">The Agent Health solution can help you identify outdated or broken :::no-loc text="Microsoft Monitoring"::: agents within your environment, and the Alert Management solution provides details about the alerts that have been raised within a given period.</span></span>

## <a name="see-also"></a><span data-ttu-id="b3e57-479">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b3e57-479">See also</span></span>

[<span data-ttu-id="b3e57-480">计划 :::no-loc text="Microsoft Teams Rooms"::: 管理与 :::no-loc text="Azure Monitor":::</span><span class="sxs-lookup"><span data-stu-id="b3e57-480">Plan :::no-loc text="Microsoft Teams Rooms"::: management with :::no-loc text="Azure Monitor":::</span></span>](azure-monitor-plan.md)

[<span data-ttu-id="b3e57-481">管理 :::no-loc text="Microsoft Teams Rooms"::: 设备 :::no-loc text="Azure Monitor":::</span><span class="sxs-lookup"><span data-stu-id="b3e57-481">Manage :::no-loc text="Microsoft Teams Rooms"::: devices with :::no-loc text="Azure Monitor":::</span></span>](azure-monitor-manage.md)
