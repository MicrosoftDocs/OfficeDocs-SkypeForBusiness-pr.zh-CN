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
ms.custom: ''
ms.assetid: d86ff657-ee92-4b06-aee3-d4c43090bdcb
description: 本文介绍如何使用 Azure 监视器以集成的端到端方式部署 Microsoft 团队聊天室设备的管理。
ms.openlocfilehash: 54268676eadab25599d4f8b6e415ff373717943f
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41826260"
---
# <a name="deploy-no-loc-textmicrosoft-teams-rooms-management-with-no-loc-textazure-monitor"></a><span data-ttu-id="705a0-103">部署:::no-loc text="Microsoft Teams Rooms":::管理:::no-loc text="Azure Monitor":::</span><span class="sxs-lookup"><span data-stu-id="705a0-103">Deploy :::no-loc text="Microsoft Teams Rooms"::: management with :::no-loc text="Azure Monitor":::</span></span>

<span data-ttu-id="705a0-104">本文介绍如何通过使用:::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Azure Monitor":::设置和部署设备的集成端到端管理。</span><span class="sxs-lookup"><span data-stu-id="705a0-104">This article discusses how to set up and deploy integrated, end-to-end management of :::no-loc text="Microsoft Teams Rooms"::: devices by using :::no-loc text="Azure Monitor":::.</span></span>

<span data-ttu-id="705a0-105">你可以在:::no-loc text="Log Analytics":::内部:::no-loc text="Azure Monitor":::进行配置，以提供可帮助你管理:::no-loc text="Microsoft Teams Rooms":::会议室设备的基本遥测和警报。</span><span class="sxs-lookup"><span data-stu-id="705a0-105">You can configure :::no-loc text="Log Analytics"::: within :::no-loc text="Azure Monitor"::: to provide basic telemetry and alerts that will help you manage :::no-loc text="Microsoft Teams Rooms"::: meeting room devices.</span></span> <span data-ttu-id="705a0-106">随着管理解决方案的成熟，你可能会决定部署其他数据和管理功能来创建更详细的设备可用性和性能视图。</span><span class="sxs-lookup"><span data-stu-id="705a0-106">As your management solution matures, you might decide to deploy additional data and management capabilities to create a more detailed view of device availability and performance.</span></span>

<span data-ttu-id="705a0-107">通过遵循本指南，你可以使用仪表板（如以下示例）获取有关设备可用性、应用程序和硬件运行状况以及:::no-loc text="Microsoft Teams Rooms":::应用程序和操作系统版本分发的详细状态报告。</span><span class="sxs-lookup"><span data-stu-id="705a0-107">By following this guide, you can use a dashboard like the following example to get detailed status reporting for device availability, application and hardware health, and :::no-loc text="Microsoft Teams Rooms"::: application and operating system version distribution.</span></span>

<span data-ttu-id="705a0-108">![示例:::no-loc text="Log Analytics":::视图的屏幕截图:::no-loc text="Microsoft Teams Rooms":::](../media/Deploy-Azure-Monitor-1.png "示例:::no-loc text="Log Analytics":::视图:::no-loc text="Microsoft Teams Rooms":::"）</span><span class="sxs-lookup"><span data-stu-id="705a0-108">![Screen shot of sample :::no-loc text="Log Analytics"::: view for :::no-loc text="Microsoft Teams Rooms":::](../media/Deploy-Azure-Monitor-1.png "Sample :::no-loc text="Log Analytics"::: view for :::no-loc text="Microsoft Teams Rooms":::")</span></span>

<span data-ttu-id="705a0-109">你需要在高级别执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="705a0-109">At a high level, you need to perform the following tasks:</span></span>


1. [<span data-ttu-id="705a0-110">验证:::no-loc text="Log Analytics":::配置</span><span class="sxs-lookup"><span data-stu-id="705a0-110">Validate :::no-loc text="Log Analytics"::: configuration</span></span>](azure-monitor-deploy.md#validate_LogAnalytics)
2. [<span data-ttu-id="705a0-111">配置管理设置的:::no-loc text="Log Analytics":::测试设备</span><span class="sxs-lookup"><span data-stu-id="705a0-111">Configure test devices for :::no-loc text="Log Analytics"::: management setup</span></span>](azure-monitor-deploy.md#configure_test_devices)
3. [<span data-ttu-id="705a0-112">映射自定义字段</span><span class="sxs-lookup"><span data-stu-id="705a0-112">Map custom fields</span></span>](azure-monitor-deploy.md#Custom_fields)
4. [<span data-ttu-id="705a0-113">定义:::no-loc text="Microsoft Teams Rooms":::视图:::no-loc text="Log Analytics":::</span><span class="sxs-lookup"><span data-stu-id="705a0-113">Define the :::no-loc text="Microsoft Teams Rooms"::: views in :::no-loc text="Log Analytics":::</span></span>](azure-monitor-deploy.md#Define_Views)
5. [<span data-ttu-id="705a0-114">定义警报</span><span class="sxs-lookup"><span data-stu-id="705a0-114">Define alerts</span></span>](azure-monitor-deploy.md#Alerts)
6. [<span data-ttu-id="705a0-115">配置用于监视的所有设备</span><span class="sxs-lookup"><span data-stu-id="705a0-115">Configure all devices for Monitoring</span></span>](azure-monitor-deploy.md#configure_all_devices)
7. [<span data-ttu-id="705a0-116">配置其他:::no-loc text="Azure Monitor":::解决方案</span><span class="sxs-lookup"><span data-stu-id="705a0-116">Configure additional :::no-loc text="Azure Monitor"::: solutions</span></span>](azure-monitor-deploy.md#Solutions)

> [!IMPORTANT]
> <span data-ttu-id="705a0-117">虽然使用最少的:::no-loc text="Azure Monitor"::: :::no-loc text="Log Analytics":::配置可以监视运行:::no-loc text="Windows":::操作系统的计算机，但在开始将代理:::no-loc text="Microsoft Teams Rooms":::部署到所有:::no-loc text="Microsoft Teams Rooms":::设备之前，仍需要执行一些特定步骤。</span><span class="sxs-lookup"><span data-stu-id="705a0-117">Although with minimal configuration, :::no-loc text="Azure Monitor"::: :::no-loc text="Log Analytics"::: can monitor a computer running a :::no-loc text="Windows"::: operating system, there are still some :::no-loc text="Microsoft Teams Rooms":::–specific steps that you need to take before you start deploying agents to all :::no-loc text="Microsoft Teams Rooms"::: devices.</span></span>
> <span data-ttu-id="705a0-118">因此，我们强烈建议你按照正确的顺序执行所有配置步骤，以进行受控设置和配置。</span><span class="sxs-lookup"><span data-stu-id="705a0-118">Therefore, we highly recommend you perform all configuration steps in the right order for a controlled setup and configuration.</span></span> <span data-ttu-id="705a0-119">最终结果的质量非常多取决于初始配置的质量。</span><span class="sxs-lookup"><span data-stu-id="705a0-119">The quality of the end result very much depends on the quality of the initial configuration.</span></span>

## <a name="validate-no-loc-textlog-analytics-configuration"></a><span data-ttu-id="705a0-120">验证:::no-loc text="Log Analytics":::配置</span><span class="sxs-lookup"><span data-stu-id="705a0-120">Validate :::no-loc text="Log Analytics"::: configuration</span></span>
<span data-ttu-id="705a0-121"><a name="validate_LogAnalytics"> </a></span><span class="sxs-lookup"><span data-stu-id="705a0-121"><a name="validate_LogAnalytics"> </a></span></span>

<span data-ttu-id="705a0-122">需要具有:::no-loc text="Log Analytics":::工作区才能开始从:::no-loc text="Microsoft Teams Rooms":::设备收集日志。</span><span class="sxs-lookup"><span data-stu-id="705a0-122">You need to have a :::no-loc text="Log Analytics"::: workspace to start collecting logs from :::no-loc text="Microsoft Teams Rooms"::: devices.</span></span> <span data-ttu-id="705a0-123">工作区是具有自己:::no-loc text="Log Analytics":::的数据存储库、数据源和解决方案的独特环境。</span><span class="sxs-lookup"><span data-stu-id="705a0-123">A workspace is a unique :::no-loc text="Log Analytics"::: environment with its own data repository, data sources, and solutions.</span></span> <span data-ttu-id="705a0-124">如果你已有一个现有:::no-loc text="Log Analytics":::工作区，则可以使用它监视你:::no-loc text="Microsoft Teams Rooms":::的部署，或者你可以创建特定于:::no-loc text="Log Analytics":::你:::no-loc text="Microsoft Teams Rooms":::的监视需求的专用工作区。</span><span class="sxs-lookup"><span data-stu-id="705a0-124">If you already have an existing :::no-loc text="Log Analytics"::: workspace, you might use it to monitor your :::no-loc text="Microsoft Teams Rooms"::: deployment or alternatively, you can create a dedicated :::no-loc text="Log Analytics"::: workspace specific to your :::no-loc text="Microsoft Teams Rooms"::: monitoring needs.</span></span>

<span data-ttu-id="705a0-125">如果需要创建新:::no-loc text="Log Analytics":::的工作区，请按照文章在[ :::no-loc text="Log Analytics"::: :::no-loc text="Azure":::门户中创建工作区](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace)中的说明进行操作</span><span class="sxs-lookup"><span data-stu-id="705a0-125">If you need to create a new :::no-loc text="Log Analytics"::: workspace, follow the instructions in the article [Create a :::no-loc text="Log Analytics"::: workspace in the :::no-loc text="Azure"::: portal](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace)</span></span>

> [!NOTE]
> <span data-ttu-id="705a0-126">若要:::no-loc text="Log Analytics":::使用:::no-loc text="Azure Monitor":::，您需要有有效:::no-loc text="Azure":::的订阅。</span><span class="sxs-lookup"><span data-stu-id="705a0-126">To use :::no-loc text="Log Analytics"::: with :::no-loc text="Azure Monitor":::, you need to have an active :::no-loc text="Azure"::: subscription.</span></span> <span data-ttu-id="705a0-127">如果您没有:::no-loc text="Azure":::套餐，您可以创建[一个免费试用订阅](https://azure.microsoft.com/free)作为起点。</span><span class="sxs-lookup"><span data-stu-id="705a0-127">If you don’t have an :::no-loc text="Azure"::: subscription, you can create [a free trial subscription](https://azure.microsoft.com/free) as a starting point.</span></span>

### <a name="configure-no-loc-textlog-analytics-to-collect-no-loc-textmicrosoft-teams-rooms-event-logs"></a><span data-ttu-id="705a0-128">配置:::no-loc text="Log Analytics":::以收集:::no-loc text="Microsoft Teams Rooms":::事件日志</span><span class="sxs-lookup"><span data-stu-id="705a0-128">Configure :::no-loc text="Log Analytics"::: to collect :::no-loc text="Microsoft Teams Rooms"::: event logs</span></span>

<span data-ttu-id="705a0-129">:::no-loc text="Log Analytics":::仅收集在 "设置:::no-loc text="Windows"::: " 中指定的事件日志中的事件。</span><span class="sxs-lookup"><span data-stu-id="705a0-129">:::no-loc text="Log Analytics"::: only collects events from the :::no-loc text="Windows"::: event logs that are specified in the settings.</span></span> <span data-ttu-id="705a0-130">对于每个日志，仅收集具有选定严重性的事件。</span><span class="sxs-lookup"><span data-stu-id="705a0-130">For each log, only the events with the selected severities are collected.</span></span>

<span data-ttu-id="705a0-131">你需要配置:::no-loc text="Log Analytics":::以收集监视:::no-loc text="Microsoft Teams Rooms":::设备和应用程序状态所需的日志。</span><span class="sxs-lookup"><span data-stu-id="705a0-131">You need to configure :::no-loc text="Log Analytics"::: to collect the logs required to monitor :::no-loc text="Microsoft Teams Rooms"::: device and application status.</span></span> <span data-ttu-id="705a0-132">:::no-loc text="Microsoft Teams Rooms":::设备使用**:::no-loc text="Skype Room System":::** 事件日志。</span><span class="sxs-lookup"><span data-stu-id="705a0-132">:::no-loc text="Microsoft Teams Rooms"::: devices use the **:::no-loc text="Skype Room System":::** event log.</span></span>

<span data-ttu-id="705a0-133">若要:::no-loc text="Log Analytics":::配置以收集:::no-loc text="Microsoft Teams Rooms":::事件，请参阅[ :::no-loc text="Windows":::事件日志中的:::no-loc text="Azure Monitor"::: "数据源](https://docs.microsoft.com/azure/azure-monitor/platform/data-sources-windows-events)"</span><span class="sxs-lookup"><span data-stu-id="705a0-133">To configure :::no-loc text="Log Analytics"::: to collect the :::no-loc text="Microsoft Teams Rooms"::: events, see [:::no-loc text="Windows"::: event log data sources in :::no-loc text="Azure Monitor":::](https://docs.microsoft.com/azure/azure-monitor/platform/data-sources-windows-events)</span></span>

<span data-ttu-id="705a0-134">![事件日志设置的屏幕截图](../media/Deploy-Azure-Monitor-2.png "事件日志设置")</span><span class="sxs-lookup"><span data-stu-id="705a0-134">![Screen shot of event log settings](../media/Deploy-Azure-Monitor-2.png "Event log settings")</span></span>

> [!IMPORTANT]
> <span data-ttu-id="705a0-135">配置:::no-loc text="Windows":::事件日志设置并输入**:::no-loc text="Skype Room System":::** "事件日志名称"，然后选择 "**错误**"、"**警告**" 和 "**信息**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="705a0-135">Configure :::no-loc text="Windows"::: Event Log settings and enter **:::no-loc text="Skype Room System":::** as event log name, and then select the **Error**, **Warning**, and **Information** check boxes.</span></span>

## <a name="configure-test-devices-for-azure-monitoring"></a><span data-ttu-id="705a0-136">配置用于 Azure 监视的测试设备</span><span class="sxs-lookup"><span data-stu-id="705a0-136">Configure test devices for Azure Monitoring</span></span>
<span data-ttu-id="705a0-137"><a name="configure_test_devices"> </a></span><span class="sxs-lookup"><span data-stu-id="705a0-137"><a name="configure_test_devices"> </a></span></span>

<span data-ttu-id="705a0-138">您需要准备:::no-loc text="Log Analytics":::能够监视:::no-loc text="Microsoft Teams Rooms":::相关事件。</span><span class="sxs-lookup"><span data-stu-id="705a0-138">You need to prepare :::no-loc text="Log Analytics"::: to be able to monitor :::no-loc text="Microsoft Teams Rooms":::–related events.</span></span> <span data-ttu-id="705a0-139">首先，你需要将代理部署:::no-loc text="Microsoft Monitoring":::到你具有物理访问权限的:::no-loc text="Microsoft Teams Rooms":::一个或两个设备，并且让这些测试设备生成一些数据并将其推送到:::no-loc text="Log Analytics":::工作区。</span><span class="sxs-lookup"><span data-stu-id="705a0-139">To start with, you need to deploy :::no-loc text="Microsoft Monitoring"::: agents to just one or two :::no-loc text="Microsoft Teams Rooms"::: devices that you have physical access to, and get those test devices generate some data and push it to the :::no-loc text="Log Analytics"::: workspace.</span></span>

### <a name="install-no-loc-textmicrosoft-monitoring-agents-to-test-devices"></a><span data-ttu-id="705a0-140">安装:::no-loc text="Microsoft Monitoring":::代理以测试设备</span><span class="sxs-lookup"><span data-stu-id="705a0-140">Install :::no-loc text="Microsoft Monitoring"::: agents to test devices</span></span>

<span data-ttu-id="705a0-141">使用 " :::no-loc text="Microsoft Monitoring"::: [将计算机连接:::no-loc text="Windows"::: :::no-loc text="Log Analytics":::到" 服务:::no-loc text="Azure":::](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows)中提供的说明将代理部署到测试设备。</span><span class="sxs-lookup"><span data-stu-id="705a0-141">Deploy the :::no-loc text="Microsoft Monitoring"::: agent to the test devices by using the instructions provided in [Connect :::no-loc text="Windows"::: computers to the :::no-loc text="Log Analytics"::: service in :::no-loc text="Azure":::](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows).</span></span> <span data-ttu-id="705a0-142">:::no-loc text="Microsoft Monitoring":::本文提供有关部署代理的:::no-loc text="Windows":::步骤的详细信息、获取:::no-loc text="Log Analytics"::: ***工作区 ID***的说明和用于获取:::no-loc text="Microsoft Teams Rooms":::连接到:::no-loc text="Azure Monitor":::部署的设备的:::no-loc text="Log Analytics"::: ***主键***，以及用于验证代理连接实例的步骤。</span><span class="sxs-lookup"><span data-stu-id="705a0-142">This article provides detailed information about the steps for deploying :::no-loc text="Microsoft Monitoring"::: Agent for :::no-loc text="Windows":::, instructions for obtaining the :::no-loc text="Log Analytics"::: ***Workspace ID*** and the ***primary key*** to get :::no-loc text="Microsoft Teams Rooms"::: devices connected to your :::no-loc text="Azure Monitor"::: deployment, and steps to verify agent connectivity to :::no-loc text="Log Analytics"::: instance.</span></span>

### <a name="generate-sample-no-loc-textmicrosoft-teams-rooms-events"></a><span data-ttu-id="705a0-143">生成示例:::no-loc text="Microsoft Teams Rooms":::事件</span><span class="sxs-lookup"><span data-stu-id="705a0-143">Generate sample :::no-loc text="Microsoft Teams Rooms"::: events</span></span>

<span data-ttu-id="705a0-144">将:::no-loc text="Microsoft Monitoring":::代理部署到测试设备后，验证所需的事件日志数据是否由:::no-loc text="Azure Monitor":::收集。</span><span class="sxs-lookup"><span data-stu-id="705a0-144">After the :::no-loc text="Microsoft Monitoring"::: agent is deployed onto the test devices, verify that the required event log data is collected by :::no-loc text="Azure Monitor":::.</span></span>

> [!NOTE]
> <span data-ttu-id="705a0-145">安装:::no-loc text="Microsoft Monitoring":::代理后重新启动设备，并确保启动:::no-loc text="Microsoft Teams Rooms":::会议应用，以便它可以在事件日志中生成新事件。</span><span class="sxs-lookup"><span data-stu-id="705a0-145">Reboot the device after the installation of the :::no-loc text="Microsoft Monitoring"::: agent, and make sure that :::no-loc text="Microsoft Teams Rooms"::: Meeting app is started, so that it can generate new events into the Event Log.</span></span>

1.  <span data-ttu-id="705a0-146">登录[ :::no-loc text="Microsoft Azure":::门户](https://portal.azure.com)并转到:::no-loc text="Log Analytics":::并选择您的工作区。</span><span class="sxs-lookup"><span data-stu-id="705a0-146">Sign in to the [:::no-loc text="Microsoft Azure"::: portal](https://portal.azure.com) and go to :::no-loc text="Log Analytics"::: and select your workspace.</span></span>

2.  <span data-ttu-id="705a0-147">列出:::no-loc text="Microsoft Teams Rooms":::设备生成的检测信号事件：</span><span class="sxs-lookup"><span data-stu-id="705a0-147">List the heartbeat events generated by a :::no-loc text="Microsoft Teams Rooms"::: device:</span></span>
    1.  <span data-ttu-id="705a0-148">选择您的工作区并转到 "**日志**" 并使用查询来检索包含自定义字段的检测信号:::no-loc text="Microsoft Teams Rooms":::记录。</span><span class="sxs-lookup"><span data-stu-id="705a0-148">Select your workspace and go to **Logs** and use a query to retrieve the heartbeat records that will have the custom fields for :::no-loc text="Microsoft Teams Rooms":::.</span></span>
    2.  <span data-ttu-id="705a0-149">示例查询：`Event | where Source == "SRS-App" and EventID == 2000`</span><span class="sxs-lookup"><span data-stu-id="705a0-149">Sample query: `Event | where Source == "SRS-App" and EventID == 2000`</span></span>

3.  <span data-ttu-id="705a0-150">请确保查询返回包含:::no-loc text="Microsoft Teams Rooms":::会议应用生成的事件的日志记录。</span><span class="sxs-lookup"><span data-stu-id="705a0-150">Make sure that the query returns log records that include events generated by the :::no-loc text="Microsoft Teams Rooms"::: meetings app.</span></span>

4.  <span data-ttu-id="705a0-151">生成硬件问题，并验证是否已登录所需的事件:::no-loc text="Azure Log Analytics":::。</span><span class="sxs-lookup"><span data-stu-id="705a0-151">Generate a hardware issue, and validate that the required events are logged in :::no-loc text="Azure Log Analytics":::.</span></span>
    1.  <span data-ttu-id="705a0-152">拔下测试:::no-loc text="Microsoft Teams Rooms":::系统上的其中一个外围设备。</span><span class="sxs-lookup"><span data-stu-id="705a0-152">Unplug one of the peripheral devices on the test :::no-loc text="Microsoft Teams Rooms"::: system.</span></span> <span data-ttu-id="705a0-153">这可能是相机、话筒、麦克风或前置房间显示</span><span class="sxs-lookup"><span data-stu-id="705a0-153">This could be the camera, speakerphone, microphone, or Front Room Display</span></span>
    2.  <span data-ttu-id="705a0-154">等待10分钟，以便填充事件日志:::no-loc text="Azure Log Analytics":::。</span><span class="sxs-lookup"><span data-stu-id="705a0-154">Wait 10 minutes for the event log to be populated in :::no-loc text="Azure Log Analytics":::.</span></span>
    3.  <span data-ttu-id="705a0-155">使用查询列出硬件错误事件：`Event | where Source == "SRS-App" and EventID == 3001`</span><span class="sxs-lookup"><span data-stu-id="705a0-155">Use a query to list hardware error events: `Event | where Source == "SRS-App" and EventID == 3001`</span></span>

5.  <span data-ttu-id="705a0-156">生成应用程序问题，并验证是否已记录所需的事件。</span><span class="sxs-lookup"><span data-stu-id="705a0-156">Generate an application issue, and validate that the required events are logged.</span></span>
    1.  <span data-ttu-id="705a0-157">修改:::no-loc text="Microsoft Teams Rooms":::应用程序配置，并键入不正确的会话启动协议（SIP）地址/密码对。</span><span class="sxs-lookup"><span data-stu-id="705a0-157">Modify :::no-loc text="Microsoft Teams Rooms"::: application configuration, and type an incorrect Session Initiation Protocol (SIP) address/password pair.</span></span>
    2.  <span data-ttu-id="705a0-158">等待10分钟，以便填充事件日志:::no-loc text="Azure Log Analytics":::。</span><span class="sxs-lookup"><span data-stu-id="705a0-158">Wait 10 minutes for the event log to be populated in :::no-loc text="Azure Log Analytics":::.</span></span>
    3.  <span data-ttu-id="705a0-159">使用查询列出应用程序错误事件：`Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`</span><span class="sxs-lookup"><span data-stu-id="705a0-159">Use a query to list application error events: `Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="705a0-160">在可以配置自定义字段之前，需要这些示例事件日志。</span><span class="sxs-lookup"><span data-stu-id="705a0-160">These sample event logs are required before custom fields can be configured.</span></span> <span data-ttu-id="705a0-161">不要继续执行下一步操作，直到收集了所需的事件日志。</span><span class="sxs-lookup"><span data-stu-id="705a0-161">Don’t proceed to the next step until you have collected the required event logs.</span></span>

## <a name="map-custom-fields"></a><span data-ttu-id="705a0-162">映射自定义字段</span><span class="sxs-lookup"><span data-stu-id="705a0-162">Map custom fields</span></span>
<span data-ttu-id="705a0-163"><a name="Custom_fields"> </a></span><span class="sxs-lookup"><span data-stu-id="705a0-163"><a name="Custom_fields"> </a></span></span>

<span data-ttu-id="705a0-164">使用自定义域从事件日志中提取特定数据。</span><span class="sxs-lookup"><span data-stu-id="705a0-164">You use custom fields to extract specific data from the event logs.</span></span> <span data-ttu-id="705a0-165">你需要定义稍后将用于你的磁贴、仪表板视图和通知的自定义字段。</span><span class="sxs-lookup"><span data-stu-id="705a0-165">You need to define custom fields that will be used later with your tiles, dashboard views, and alerts.</span></span> <span data-ttu-id="705a0-166">在开始创建自定义字段之前，请参阅[中:::no-loc text="Log Analytics":::的自定义字段](https://docs.microsoft.com/azure/azure-monitor/platform/custom-fields)并熟悉概念。</span><span class="sxs-lookup"><span data-stu-id="705a0-166">See [Custom fields in :::no-loc text="Log Analytics":::](https://docs.microsoft.com/azure/azure-monitor/platform/custom-fields) and become familiar with the concepts before you start creating your custom fields.</span></span>

<span data-ttu-id="705a0-167">若要从捕获的事件日志中提取自定义域，请按照下列步骤操作：</span><span class="sxs-lookup"><span data-stu-id="705a0-167">To extract your custom fields out of the captured event logs, follow these steps:</span></span>

1.  <span data-ttu-id="705a0-168">登录[ :::no-loc text="Microsoft Azure":::门户](https://portal.azure.com)并转到:::no-loc text="Log Analytics":::并选择您的工作区。</span><span class="sxs-lookup"><span data-stu-id="705a0-168">Sign in to the [:::no-loc text="Microsoft Azure"::: portal](https://portal.azure.com) and go to :::no-loc text="Log Analytics"::: and select your workspace.</span></span>

2. <span data-ttu-id="705a0-169">列出:::no-loc text="Microsoft Teams Rooms":::设备生成的事件：</span><span class="sxs-lookup"><span data-stu-id="705a0-169">List the events generated by a :::no-loc text="Microsoft Teams Rooms"::: device:</span></span>
   1.  <span data-ttu-id="705a0-170">转到 "**日志**" 并使用查询检索将具有自定义字段的记录。</span><span class="sxs-lookup"><span data-stu-id="705a0-170">Go to **Logs** and use a query to retrieve the records that will have the custom field.</span></span>
   2.  <span data-ttu-id="705a0-171">示例查询：`Event | where Source == "SRS-App" and EventID == 2000`</span><span class="sxs-lookup"><span data-stu-id="705a0-171">Sample query: `Event | where Source == "SRS-App" and EventID == 2000`</span></span>

3. <span data-ttu-id="705a0-172">选择其中一个记录，选择左侧的按钮，然后启动 "字段提取向导"。</span><span class="sxs-lookup"><span data-stu-id="705a0-172">Select one of the records, select the button to the left, and start the field extraction wizard.</span></span>
4. <span data-ttu-id="705a0-173">突出显示要从 RenderedDescription 中提取的数据，并提供字段标题。</span><span class="sxs-lookup"><span data-stu-id="705a0-173">Highlight the data you’d like to extract from the RenderedDescription and provide a Field Title.</span></span> <span data-ttu-id="705a0-174">表1中提供了应使用的字段名称。</span><span class="sxs-lookup"><span data-stu-id="705a0-174">The field names that you should use are provided in Table 1.</span></span>

   <span data-ttu-id="705a0-175">![自定义字段定义](../media/Deploy-Azure-Monitor-4.png "自定义字段定义")</span><span class="sxs-lookup"><span data-stu-id="705a0-175">![Custom field definition](../media/Deploy-Azure-Monitor-4.png "Custom field definition")</span></span>

5. <span data-ttu-id="705a0-176">使用*表 1*中所示的映射。</span><span class="sxs-lookup"><span data-stu-id="705a0-176">Use the mappings shown in *Table 1*.</span></span> <span data-ttu-id="705a0-177">:::no-loc text="Log Analytics":::定义新字段时，将自动追加\*\* \_CF\*\*字符串。</span><span class="sxs-lookup"><span data-stu-id="705a0-177">:::no-loc text="Log Analytics"::: will automatically append the **\_CF** string when you define the new field.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="705a0-178">请记住，所有 JSON :::no-loc text="Log Analytics":::和字段都区分大小写。</span><span class="sxs-lookup"><span data-stu-id="705a0-178">Remember that all JSON and :::no-loc text="Log Analytics"::: fields are case-sensitive.</span></span>
> 
> <span data-ttu-id="705a0-179">请注意下表中每个自定义域所需的查询。</span><span class="sxs-lookup"><span data-stu-id="705a0-179">Pay attention to the queries required for each custom field in the table below.</span></span> <span data-ttu-id="705a0-180">您需要使用正确的:::no-loc text="Log Analytics":::查询来成功提取自定义域值。</span><span class="sxs-lookup"><span data-stu-id="705a0-180">You need to use the correct queries for :::no-loc text="Log Analytics"::: to successfully extract custom field values.</span></span>
> 
 <span data-ttu-id="705a0-181">![自定义字段定义](../media/Deploy-Azure-Monitor-5.png "自定义字段定义")</span><span class="sxs-lookup"><span data-stu-id="705a0-181">![Custom field definition](../media/Deploy-Azure-Monitor-5.png "Custom field definition")</span></span>

<span data-ttu-id="705a0-182">**表1**</span><span class="sxs-lookup"><span data-stu-id="705a0-182">**Table 1**</span></span>

| <span data-ttu-id="705a0-183">**JSON 字段**</span><span class="sxs-lookup"><span data-stu-id="705a0-183">**JSON field**</span></span>                   | <span data-ttu-id="705a0-184">**:::no-loc text="Log Analytics":::自定义域**</span><span class="sxs-lookup"><span data-stu-id="705a0-184">**:::no-loc text="Log Analytics"::: custom field**</span></span> | <span data-ttu-id="705a0-185">**事件 ID**</span><span class="sxs-lookup"><span data-stu-id="705a0-185">**Event ID**</span></span> | <span data-ttu-id="705a0-186">**要与提取一起使用的查询**</span><span class="sxs-lookup"><span data-stu-id="705a0-186">**Query to use with the extraction**</span></span>                   |
|:---------------------------------|:-------------------------------|:-------------|:-------------------------------------------------------|
| <span data-ttu-id="705a0-187">说明</span><span class="sxs-lookup"><span data-stu-id="705a0-187">Description</span></span>                      | <span data-ttu-id="705a0-188">SRSEventDescription</span><span class="sxs-lookup"><span data-stu-id="705a0-188">SRSEventDescription</span></span>         | <span data-ttu-id="705a0-189">**2000**</span><span class="sxs-lookup"><span data-stu-id="705a0-189">**2000**</span></span>     | <span data-ttu-id="705a0-190">源\| = = "SRS-App" 和 EventID = = 2000 的事件</span><span class="sxs-lookup"><span data-stu-id="705a0-190">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="705a0-191">ResourceState</span><span class="sxs-lookup"><span data-stu-id="705a0-191">ResourceState</span></span>                    | <span data-ttu-id="705a0-192">SRSResourceState</span><span class="sxs-lookup"><span data-stu-id="705a0-192">SRSResourceState</span></span>            | <span data-ttu-id="705a0-193">**2000**</span><span class="sxs-lookup"><span data-stu-id="705a0-193">**2000**</span></span>     | <span data-ttu-id="705a0-194">源\| = = "SRS-App" 和 EventID = = 2000 的事件</span><span class="sxs-lookup"><span data-stu-id="705a0-194">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="705a0-195">OperationName</span><span class="sxs-lookup"><span data-stu-id="705a0-195">OperationName</span></span>                    | <span data-ttu-id="705a0-196">SRSOperationName</span><span class="sxs-lookup"><span data-stu-id="705a0-196">SRSOperationName</span></span>            | <span data-ttu-id="705a0-197">**2000**</span><span class="sxs-lookup"><span data-stu-id="705a0-197">**2000**</span></span>     | <span data-ttu-id="705a0-198">源\| = = "SRS-App" 和 EventID = = 2000 的事件</span><span class="sxs-lookup"><span data-stu-id="705a0-198">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="705a0-199">OperationResult</span><span class="sxs-lookup"><span data-stu-id="705a0-199">OperationResult</span></span>                  | <span data-ttu-id="705a0-200">SRSOperationResult</span><span class="sxs-lookup"><span data-stu-id="705a0-200">SRSOperationResult</span></span>          | <span data-ttu-id="705a0-201">**2000**</span><span class="sxs-lookup"><span data-stu-id="705a0-201">**2000**</span></span>     | <span data-ttu-id="705a0-202">源\| = = "SRS-App" 和 EventID = = 2000 的事件</span><span class="sxs-lookup"><span data-stu-id="705a0-202">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="705a0-203">OS</span><span class="sxs-lookup"><span data-stu-id="705a0-203">OS</span></span>                               | <span data-ttu-id="705a0-204">SRSOSVersion</span><span class="sxs-lookup"><span data-stu-id="705a0-204">SRSOSVersion</span></span>                | <span data-ttu-id="705a0-205">**2000**</span><span class="sxs-lookup"><span data-stu-id="705a0-205">**2000**</span></span>     | <span data-ttu-id="705a0-206">源\| = = "SRS-App" 和 EventID = = 2000 的事件</span><span class="sxs-lookup"><span data-stu-id="705a0-206">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="705a0-207">OSVersion</span><span class="sxs-lookup"><span data-stu-id="705a0-207">OSVersion</span></span>                        | <span data-ttu-id="705a0-208">SRSOSLongVersion</span><span class="sxs-lookup"><span data-stu-id="705a0-208">SRSOSLongVersion</span></span>            | <span data-ttu-id="705a0-209">**2000**</span><span class="sxs-lookup"><span data-stu-id="705a0-209">**2000**</span></span>     | <span data-ttu-id="705a0-210">源\| = = "SRS-App" 和 EventID = = 2000 的事件</span><span class="sxs-lookup"><span data-stu-id="705a0-210">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="705a0-211">别名</span><span class="sxs-lookup"><span data-stu-id="705a0-211">Alias</span></span>                            | <span data-ttu-id="705a0-212">SRSAlias</span><span class="sxs-lookup"><span data-stu-id="705a0-212">SRSAlias</span></span>                    | <span data-ttu-id="705a0-213">**2000**</span><span class="sxs-lookup"><span data-stu-id="705a0-213">**2000**</span></span>     | <span data-ttu-id="705a0-214">源\| = = "SRS-App" 和 EventID = = 2000 的事件</span><span class="sxs-lookup"><span data-stu-id="705a0-214">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="705a0-215">DisplayName</span><span class="sxs-lookup"><span data-stu-id="705a0-215">DisplayName</span></span>                      | <span data-ttu-id="705a0-216">SRSDisplayName</span><span class="sxs-lookup"><span data-stu-id="705a0-216">SRSDisplayName</span></span>              | <span data-ttu-id="705a0-217">**2000**</span><span class="sxs-lookup"><span data-stu-id="705a0-217">**2000**</span></span>     | <span data-ttu-id="705a0-218">源\| = = "SRS-App" 和 EventID = = 2000 的事件</span><span class="sxs-lookup"><span data-stu-id="705a0-218">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="705a0-219">AppVersion</span><span class="sxs-lookup"><span data-stu-id="705a0-219">AppVersion</span></span>                       | <span data-ttu-id="705a0-220">SRSAppVersion</span><span class="sxs-lookup"><span data-stu-id="705a0-220">SRSAppVersion</span></span>               | <span data-ttu-id="705a0-221">**2000**</span><span class="sxs-lookup"><span data-stu-id="705a0-221">**2000**</span></span>     | <span data-ttu-id="705a0-222">源\| = = "SRS-App" 和 EventID = = 2000 的事件</span><span class="sxs-lookup"><span data-stu-id="705a0-222">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="705a0-223">IPv4Address</span><span class="sxs-lookup"><span data-stu-id="705a0-223">IPv4Address</span></span>                      | <span data-ttu-id="705a0-224">SRSIPv4Address</span><span class="sxs-lookup"><span data-stu-id="705a0-224">SRSIPv4Address</span></span>              | <span data-ttu-id="705a0-225">**2000**</span><span class="sxs-lookup"><span data-stu-id="705a0-225">**2000**</span></span>     | <span data-ttu-id="705a0-226">源\| = = "SRS-App" 和 EventID = = 2000 的事件</span><span class="sxs-lookup"><span data-stu-id="705a0-226">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="705a0-227">IPv6Address</span><span class="sxs-lookup"><span data-stu-id="705a0-227">IPv6Address</span></span>                      | <span data-ttu-id="705a0-228">SRSIPv6Address</span><span class="sxs-lookup"><span data-stu-id="705a0-228">SRSIPv6Address</span></span>              | <span data-ttu-id="705a0-229">**2000**</span><span class="sxs-lookup"><span data-stu-id="705a0-229">**2000**</span></span>     | <span data-ttu-id="705a0-230">源\| = = "SRS-App" 和 EventID = = 2000 的事件</span><span class="sxs-lookup"><span data-stu-id="705a0-230">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="705a0-231">会议麦克风状态</span><span class="sxs-lookup"><span data-stu-id="705a0-231">Conference Microphone status</span></span>     | <span data-ttu-id="705a0-232">SRSConfMicrophoneStatus</span><span class="sxs-lookup"><span data-stu-id="705a0-232">SRSConfMicrophoneStatus</span></span>     | <span data-ttu-id="705a0-233">**3001**</span><span class="sxs-lookup"><span data-stu-id="705a0-233">**3001**</span></span>     | <span data-ttu-id="705a0-234">源\| = = "SRS-App" 和 EventID = = 3001 的事件</span><span class="sxs-lookup"><span data-stu-id="705a0-234">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="705a0-235">会议演讲者状态</span><span class="sxs-lookup"><span data-stu-id="705a0-235">Conference Speaker status</span></span>        | <span data-ttu-id="705a0-236">SRSConfSpeakerStatus</span><span class="sxs-lookup"><span data-stu-id="705a0-236">SRSConfSpeakerStatus</span></span>        | <span data-ttu-id="705a0-237">**3001**</span><span class="sxs-lookup"><span data-stu-id="705a0-237">**3001**</span></span>     | <span data-ttu-id="705a0-238">源\| = = "SRS-App" 和 EventID = = 3001 的事件</span><span class="sxs-lookup"><span data-stu-id="705a0-238">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="705a0-239">默认扬声器状态</span><span class="sxs-lookup"><span data-stu-id="705a0-239">Default Speaker status</span></span>           | <span data-ttu-id="705a0-240">SRSDefaultSpeakerStatus</span><span class="sxs-lookup"><span data-stu-id="705a0-240">SRSDefaultSpeakerStatus</span></span>     | <span data-ttu-id="705a0-241">**3001**</span><span class="sxs-lookup"><span data-stu-id="705a0-241">**3001**</span></span>     | <span data-ttu-id="705a0-242">源\| = = "SRS-App" 和 EventID = = 3001 的事件</span><span class="sxs-lookup"><span data-stu-id="705a0-242">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="705a0-243">相机状态</span><span class="sxs-lookup"><span data-stu-id="705a0-243">Camera status</span></span>                    | <span data-ttu-id="705a0-244">SRSCameraStatus</span><span class="sxs-lookup"><span data-stu-id="705a0-244">SRSCameraStatus</span></span>             | <span data-ttu-id="705a0-245">**3001**</span><span class="sxs-lookup"><span data-stu-id="705a0-245">**3001**</span></span>     | <span data-ttu-id="705a0-246">源\| = = "SRS-App" 和 EventID = = 3001 的事件</span><span class="sxs-lookup"><span data-stu-id="705a0-246">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="705a0-247">房间前显示状态</span><span class="sxs-lookup"><span data-stu-id="705a0-247">Front of Room Display status</span></span>     | <span data-ttu-id="705a0-248">SRSFORDStatus</span><span class="sxs-lookup"><span data-stu-id="705a0-248">SRSFORDStatus</span></span>               | <span data-ttu-id="705a0-249">**3001**</span><span class="sxs-lookup"><span data-stu-id="705a0-249">**3001**</span></span>     | <span data-ttu-id="705a0-250">源\| = = "SRS-App" 和 EventID = = 3001 的事件</span><span class="sxs-lookup"><span data-stu-id="705a0-250">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="705a0-251">运动传感器状态</span><span class="sxs-lookup"><span data-stu-id="705a0-251">Motion Sensor status</span></span>             | <span data-ttu-id="705a0-252">SRSMotionSensorStatus</span><span class="sxs-lookup"><span data-stu-id="705a0-252">SRSMotionSensorStatus</span></span>       | <span data-ttu-id="705a0-253">**3001**</span><span class="sxs-lookup"><span data-stu-id="705a0-253">**3001**</span></span>     | <span data-ttu-id="705a0-254">源\| = = "SRS-App" 和 EventID = = 3001 的事件</span><span class="sxs-lookup"><span data-stu-id="705a0-254">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="705a0-255">HDMI 接收状态</span><span class="sxs-lookup"><span data-stu-id="705a0-255">HDMI Ingest status</span></span>               | <span data-ttu-id="705a0-256">SRSHDMIIngestStatus</span><span class="sxs-lookup"><span data-stu-id="705a0-256">SRSHDMIIngestStatus</span></span>         | <span data-ttu-id="705a0-257">**3001**</span><span class="sxs-lookup"><span data-stu-id="705a0-257">**3001**</span></span>     | <span data-ttu-id="705a0-258">源\| = = "SRS-App" 和 EventID = = 3001 的事件</span><span class="sxs-lookup"><span data-stu-id="705a0-258">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |


## <a name="define-the-no-loc-textmicrosoft-teams-rooms-views-in-no-loc-textlog-analytics"></a><span data-ttu-id="705a0-259">定义:::no-loc text="Microsoft Teams Rooms":::视图:::no-loc text="Log Analytics":::</span><span class="sxs-lookup"><span data-stu-id="705a0-259">Define the :::no-loc text="Microsoft Teams Rooms"::: views in :::no-loc text="Log Analytics":::</span></span>
<span data-ttu-id="705a0-260"><a name="Define_Views"> </a></span><span class="sxs-lookup"><span data-stu-id="705a0-260"><a name="Define_Views"> </a></span></span>

<span data-ttu-id="705a0-261">收集数据并映射自定义字段后，可以使用 "视图设计器" 开发一个仪表板，其中包含用于:::no-loc text="Microsoft Teams Rooms":::监视事件的各种磁贴。</span><span class="sxs-lookup"><span data-stu-id="705a0-261">After data is collected and custom fields are mapped, you can use View Designer to develop a dashboard containing various tiles to monitor :::no-loc text="Microsoft Teams Rooms"::: events.</span></span> <span data-ttu-id="705a0-262">使用 "视图设计器" 创建以下图块。</span><span class="sxs-lookup"><span data-stu-id="705a0-262">Use View Designer to create the following tiles.</span></span> <span data-ttu-id="705a0-263">有关详细信息，请参阅[使用视图设计器:::no-loc text="Log Analytics":::创建自定义视图](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer)</span><span class="sxs-lookup"><span data-stu-id="705a0-263">For more information, see [Create custom views by using View Designer in :::no-loc text="Log Analytics":::](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer)</span></span>

> [!NOTE]
> <span data-ttu-id="705a0-264">应完成本指南前面的步骤，仪表板图块才能正常工作。</span><span class="sxs-lookup"><span data-stu-id="705a0-264">Previous steps in this guide should have been completed for the dashboard tiles to work properly.</span></span>

### <a name="create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method"></a><span data-ttu-id="705a0-265">使用 import 方法创建 Microsoft 团队聊天室仪表板</span><span class="sxs-lookup"><span data-stu-id="705a0-265">Create a Microsoft Teams Rooms dashboard by using the import method</span></span>

<span data-ttu-id="705a0-266">您可以导入:::no-loc text="Microsoft Teams Rooms":::仪表板并快速开始监视设备。</span><span class="sxs-lookup"><span data-stu-id="705a0-266">You can import an :::no-loc text="Microsoft Teams Rooms"::: dashboard and start monitoring your devices quickly.</span></span> <span data-ttu-id="705a0-267">执行以下步骤导入仪表板：</span><span class="sxs-lookup"><span data-stu-id="705a0-267">Take the following steps to import the dashboard:</span></span>

1.  <span data-ttu-id="705a0-268">获取[SkypeRoomSystems_v2 的 omsview](https://go.microsoft.com/fwlink/?linkid=835675)仪表板文件。</span><span class="sxs-lookup"><span data-stu-id="705a0-268">Get the [SkypeRoomSystems_v2.omsview](https://go.microsoft.com/fwlink/?linkid=835675) dashboard file.</span></span>
2.  <span data-ttu-id="705a0-269">登录[ :::no-loc text="Microsoft Azure":::门户](https://portal.azure.com)并转到:::no-loc text="Log Analytics":::并选择您的工作区。</span><span class="sxs-lookup"><span data-stu-id="705a0-269">Sign in to the [:::no-loc text="Microsoft Azure"::: portal](https://portal.azure.com) and go to :::no-loc text="Log Analytics"::: and select your workspace.</span></span>
3.  <span data-ttu-id="705a0-270">打开**视图设计器**。</span><span class="sxs-lookup"><span data-stu-id="705a0-270">Open **View Designer**.</span></span>
4.  <span data-ttu-id="705a0-271">选择 "**导入**"，然后选择 " **SkypeRoomSystems_v2 的 omsview**文件。</span><span class="sxs-lookup"><span data-stu-id="705a0-271">Select **Import**, and then select the **SkypeRoomSystems_v2.omsview** file.</span></span>
5.  <span data-ttu-id="705a0-272">选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="705a0-272">Select **Save**.</span></span>

### <a name="create-a-microsoft-teams-rooms-dashboard-manually"></a><span data-ttu-id="705a0-273">手动创建 Microsoft 团队聊天室仪表板</span><span class="sxs-lookup"><span data-stu-id="705a0-273">Create a Microsoft Teams Rooms dashboard manually</span></span>

<span data-ttu-id="705a0-274">或者，你可以创建自己的仪表板并仅添加你希望监视的磁贴。</span><span class="sxs-lookup"><span data-stu-id="705a0-274">Alternatively, you can create your own dashboard and add only the tiles that you wish to monitor.</span></span>

#### <a name="configure-the-overview-tile"></a><span data-ttu-id="705a0-275">配置概述图块</span><span class="sxs-lookup"><span data-stu-id="705a0-275">Configure the Overview Tile</span></span>

1.  <span data-ttu-id="705a0-276">打开**视图设计器**。</span><span class="sxs-lookup"><span data-stu-id="705a0-276">Open **View Designer**.</span></span>
2.  <span data-ttu-id="705a0-277">选择 "**概述图块**"，然后从库中选择**两个数字**。</span><span class="sxs-lookup"><span data-stu-id="705a0-277">Select **Overview Tile**, and then select **Two numbers** from the gallery.</span></span>
3.  <span data-ttu-id="705a0-278">命名磁贴**:::no-loc text="Microsoft Teams Rooms":::**。</span><span class="sxs-lookup"><span data-stu-id="705a0-278">Name the tile **:::no-loc text="Microsoft Teams Rooms":::**.</span></span>
4.  <span data-ttu-id="705a0-279">定义**第一个图块**：</span><span class="sxs-lookup"><span data-stu-id="705a0-279">Define the **First Tile**:</span></span><br>
    <span data-ttu-id="705a0-280">**图例：** 在上个月内至少发送过一次检测信号的设备</span><span class="sxs-lookup"><span data-stu-id="705a0-280">**Legend:** Devices that sent a heartbeat at least once within the last month</span></span><br>
    <span data-ttu-id="705a0-281">**查询：**```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```</span><span class="sxs-lookup"><span data-stu-id="705a0-281">**Query:** ```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```</span></span>
5.  <span data-ttu-id="705a0-282">定义**第二个图块**：</span><span class="sxs-lookup"><span data-stu-id="705a0-282">Define the **Second Tile**:</span></span><br>
    <span data-ttu-id="705a0-283">**图例：** 在过去一小时内发送检测信号的活动设备</span><span class="sxs-lookup"><span data-stu-id="705a0-283">**Legend:** Active devices that sent a heartbeat within the last hour</span></span><br>
    <span data-ttu-id="705a0-284">**查询：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```</span><span class="sxs-lookup"><span data-stu-id="705a0-284">**Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```</span></span>
6.  <span data-ttu-id="705a0-285">选择 "**应用**"。</span><span class="sxs-lookup"><span data-stu-id="705a0-285">Select **Apply**.</span></span>

### <a name="create-a-tile-that-displays-active-devices"></a><span data-ttu-id="705a0-286">创建显示活动设备的磁贴</span><span class="sxs-lookup"><span data-stu-id="705a0-286">Create a tile that displays active devices</span></span>

1.  <span data-ttu-id="705a0-287">选择 "**查看仪表板**" 以开始添加磁贴。</span><span class="sxs-lookup"><span data-stu-id="705a0-287">Select **View Dashboard** to start adding your tiles.</span></span>
2.  <span data-ttu-id="705a0-288">从库中选择 "**编号" & 列表**</span><span class="sxs-lookup"><span data-stu-id="705a0-288">Select **Number & list** from the gallery</span></span>
3.  <span data-ttu-id="705a0-289">定义**常规**属性：</span><span class="sxs-lookup"><span data-stu-id="705a0-289">Define the **General** properties:</span></span><br>
    <span data-ttu-id="705a0-290">**组标题：** 检测信号状态</span><span class="sxs-lookup"><span data-stu-id="705a0-290">**Group Title:** Heartbeat Status</span></span><br>
    <span data-ttu-id="705a0-291">**新组：** 处于</span><span class="sxs-lookup"><span data-stu-id="705a0-291">**New Group:** Selected</span></span>
4.  <span data-ttu-id="705a0-292">定义**图块**属性：</span><span class="sxs-lookup"><span data-stu-id="705a0-292">Define the **Tile** properties:</span></span><br>
    <span data-ttu-id="705a0-293">**图例：** 活动设备（最近20分钟内发送的检测信号）</span><span class="sxs-lookup"><span data-stu-id="705a0-293">**Legend:** Active devices (heartbeat sent in the last 20 minutes)</span></span><br>
    <span data-ttu-id="705a0-294">**图块查询：** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```</span><span class="sxs-lookup"><span data-stu-id="705a0-294">**Tile Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```</span></span>
5.  <span data-ttu-id="705a0-295">定义**列表**属性：</span><span class="sxs-lookup"><span data-stu-id="705a0-295">Define the **List** properties:</span></span><br>
    <span data-ttu-id="705a0-296">**列表查询：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span><span class="sxs-lookup"><span data-stu-id="705a0-296">**List Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span></span>
6.  <span data-ttu-id="705a0-297">定义**列标题**：</span><span class="sxs-lookup"><span data-stu-id="705a0-297">Define **Column Titles**:</span></span><br>
    <span data-ttu-id="705a0-298">**名称：** 计算机名</span><span class="sxs-lookup"><span data-stu-id="705a0-298">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="705a0-299">**值：** 上次检测信号</span><span class="sxs-lookup"><span data-stu-id="705a0-299">**Value:** Last Heartbeat</span></span>
7.  <span data-ttu-id="705a0-300">定义**导航查询**。</span><span class="sxs-lookup"><span data-stu-id="705a0-300">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  <span data-ttu-id="705a0-301">选择 "**应用**"，然后单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="705a0-301">Select **Apply**, and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-devices-that-have-connectivity-issues"></a><span data-ttu-id="705a0-302">创建显示有连接问题的设备的磁贴</span><span class="sxs-lookup"><span data-stu-id="705a0-302">Create a tile that displays devices that have connectivity issues</span></span>

1.  <span data-ttu-id="705a0-303">从库中选择 "**编号" & 列表**，然后添加新磁贴。</span><span class="sxs-lookup"><span data-stu-id="705a0-303">Select **Number & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="705a0-304">定义**常规**属性：</span><span class="sxs-lookup"><span data-stu-id="705a0-304">Define the **General** properties:</span></span><br>
    <span data-ttu-id="705a0-305">**组标题：** 留空</span><span class="sxs-lookup"><span data-stu-id="705a0-305">**Group Title:** Leave empty</span></span><br>
    <span data-ttu-id="705a0-306">**新组：** 未选中</span><span class="sxs-lookup"><span data-stu-id="705a0-306">**New Group:** Not Selected</span></span>
3.  <span data-ttu-id="705a0-307">定义**图块**属性：</span><span class="sxs-lookup"><span data-stu-id="705a0-307">Define the **Tile** properties:</span></span><br>
    <span data-ttu-id="705a0-308">**图例：** 非活动设备（最近20分钟内未发送检测信号消息）</span><span class="sxs-lookup"><span data-stu-id="705a0-308">**Legend:** Inactive Devices (no heartbeat message sent in the last 20 minutes)</span></span><br>
    <span data-ttu-id="705a0-309">**图块查询：** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```</span><span class="sxs-lookup"><span data-stu-id="705a0-309">**Tile Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```</span></span>
4.  <span data-ttu-id="705a0-310">定义**列表**属性：</span><span class="sxs-lookup"><span data-stu-id="705a0-310">Define the **List** properties:</span></span><br>
    <span data-ttu-id="705a0-311">**列表查询：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```</span><span class="sxs-lookup"><span data-stu-id="705a0-311">**List Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```</span></span>
5.  <span data-ttu-id="705a0-312">定义**列标题**：</span><span class="sxs-lookup"><span data-stu-id="705a0-312">Define **Column Titles**:</span></span><br>
    <span data-ttu-id="705a0-313">**名称：** 计算机名</span><span class="sxs-lookup"><span data-stu-id="705a0-313">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="705a0-314">**值：** 上次检测信号</span><span class="sxs-lookup"><span data-stu-id="705a0-314">**Value:** Last Heartbeat</span></span>
6.  <span data-ttu-id="705a0-315">定义**导航查询**：</span><span class="sxs-lookup"><span data-stu-id="705a0-315">Define **Navigation Query**:</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  <span data-ttu-id="705a0-316">选择 "**应用**"，然后单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="705a0-316">Select **Apply**, and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-devices-that-have-a-hardware-error"></a><span data-ttu-id="705a0-317">创建显示硬件出现错误的设备的磁贴</span><span class="sxs-lookup"><span data-stu-id="705a0-317">Create a tile that displays devices that have a hardware error</span></span>

1.  <span data-ttu-id="705a0-318">从库中选择 "**编号" & 列表**，然后添加新磁贴。</span><span class="sxs-lookup"><span data-stu-id="705a0-318">Select **Number & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="705a0-319">定义**常规**属性：</span><span class="sxs-lookup"><span data-stu-id="705a0-319">Define the **General** properties:</span></span><br>
    <span data-ttu-id="705a0-320">**组标题：** 硬件状态</span><span class="sxs-lookup"><span data-stu-id="705a0-320">**Group Title:** Hardware Status</span></span><br>
    <span data-ttu-id="705a0-321">**新组：** 处于</span><span class="sxs-lookup"><span data-stu-id="705a0-321">**New Group:** Selected</span></span>
3.  <span data-ttu-id="705a0-322">定义**图块**属性：</span><span class="sxs-lookup"><span data-stu-id="705a0-322">Define the **Tile** properties:</span></span><br>
    <span data-ttu-id="705a0-323">**图例：** 过去一小时内遇到硬件错误的设备</span><span class="sxs-lookup"><span data-stu-id="705a0-323">**Legend:** Devices that experienced a hardware error in the last hour</span></span><br>
    <span data-ttu-id="705a0-324">**图块查询：** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```</span><span class="sxs-lookup"><span data-stu-id="705a0-324">**Tile Query:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```</span></span>
4.  <span data-ttu-id="705a0-325">定义**列表**属性：</span><span class="sxs-lookup"><span data-stu-id="705a0-325">Define the **List** properties:</span></span><br>
    <span data-ttu-id="705a0-326">**列表查询：**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span><span class="sxs-lookup"><span data-stu-id="705a0-326">**List Query:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span></span>
5.  <span data-ttu-id="705a0-327">定义**列标题**：</span><span class="sxs-lookup"><span data-stu-id="705a0-327">Define **Column Titles**:</span></span><br>
    <span data-ttu-id="705a0-328">**名称：** 计算机名</span><span class="sxs-lookup"><span data-stu-id="705a0-328">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="705a0-329">**值：** 上一个错误</span><span class="sxs-lookup"><span data-stu-id="705a0-329">**Value:** Last Error</span></span>
6.  <span data-ttu-id="705a0-330">定义**导航查询**：</span><span class="sxs-lookup"><span data-stu-id="705a0-330">Define **Navigation Query**:</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 3001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  <span data-ttu-id="705a0-331">选择 "**应用**"，然后单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="705a0-331">Select **Apply**, and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-operating-system-versions"></a><span data-ttu-id="705a0-332">创建显示:::no-loc text="Microsoft Teams Rooms":::操作系统版本的磁贴</span><span class="sxs-lookup"><span data-stu-id="705a0-332">Create a tile that displays :::no-loc text="Microsoft Teams Rooms"::: Operating System versions</span></span>

1.  <span data-ttu-id="705a0-333">从库中选择 "**同心圆 & 列表**"，然后添加新磁贴。</span><span class="sxs-lookup"><span data-stu-id="705a0-333">Select **Donut & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="705a0-334">定义**常规**属性：</span><span class="sxs-lookup"><span data-stu-id="705a0-334">Define the **General** properties:</span></span><br>
    <span data-ttu-id="705a0-335">**组标题：** 操作系统详细信息</span><span class="sxs-lookup"><span data-stu-id="705a0-335">**Group Title:** Operating System details</span></span><br>
    <span data-ttu-id="705a0-336">**新组：** 处于</span><span class="sxs-lookup"><span data-stu-id="705a0-336">**New Group:** Selected</span></span>
3.  <span data-ttu-id="705a0-337">定义**页眉**属性：</span><span class="sxs-lookup"><span data-stu-id="705a0-337">Define the **Header** properties:</span></span><br>
    <span data-ttu-id="705a0-338">**标题：** 操作系统版本</span><span class="sxs-lookup"><span data-stu-id="705a0-338">**Title:** Operating System versions</span></span><br>
    <span data-ttu-id="705a0-339">**副标题：** 运行特定操作系统版本的设备</span><span class="sxs-lookup"><span data-stu-id="705a0-339">**Subtitle:** Devices running specific OS versions</span></span>
4.  <span data-ttu-id="705a0-340">定义**同心圆**属性：</span><span class="sxs-lookup"><span data-stu-id="705a0-340">Define the **Donut** properties:</span></span><br>
    <span data-ttu-id="705a0-341">**查询：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize OS_Version = max(SRSOSLongVersion_CF) by Computer | summarize AggregatedValue = count() by OS_Version | sort by OS_Version asc```</span><span class="sxs-lookup"><span data-stu-id="705a0-341">**Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize OS_Version = max(SRSOSLongVersion_CF) by Computer | summarize AggregatedValue = count() by OS_Version | sort by OS_Version asc```</span></span><br>
    <span data-ttu-id="705a0-342">**文本居中：** 台</span><span class="sxs-lookup"><span data-stu-id="705a0-342">**Center Text:** Devices</span></span><br>
    <span data-ttu-id="705a0-343">**操作：** 量</span><span class="sxs-lookup"><span data-stu-id="705a0-343">**Operation:** Sum</span></span>
5.  <span data-ttu-id="705a0-344">定义**列表**属性。</span><span class="sxs-lookup"><span data-stu-id="705a0-344">Define the **List** properties.</span></span><br>
    <span data-ttu-id="705a0-345">**列表查询：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSOSLongVersion_CF = max(SRSOSLongVersion_CF) by Computer | sort by Computer asc```</span><span class="sxs-lookup"><span data-stu-id="705a0-345">**List Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSOSLongVersion_CF = max(SRSOSLongVersion_CF) by Computer | sort by Computer asc```</span></span><br>
    <span data-ttu-id="705a0-346">**隐藏图形：** 处于</span><span class="sxs-lookup"><span data-stu-id="705a0-346">**Hide Graph:** Selected</span></span><br>
    <span data-ttu-id="705a0-347">**启用迷你图：** 未选中</span><span class="sxs-lookup"><span data-stu-id="705a0-347">**Enable Sparklines:** Not selected</span></span>
6.  <span data-ttu-id="705a0-348">定义**列标题**。</span><span class="sxs-lookup"><span data-stu-id="705a0-348">Define **Column Titles**.</span></span><br>
    <span data-ttu-id="705a0-349">**名称：** 计算机名</span><span class="sxs-lookup"><span data-stu-id="705a0-349">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="705a0-350">**值：** 留空</span><span class="sxs-lookup"><span data-stu-id="705a0-350">**Value:** Leave Empty</span></span>
7.  <span data-ttu-id="705a0-351">定义**导航查询**。</span><span class="sxs-lookup"><span data-stu-id="705a0-351">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  <span data-ttu-id="705a0-352">选择 "**应用**"，然后选择 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="705a0-352">Select **Apply** and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-application-versions"></a><span data-ttu-id="705a0-353">创建显示:::no-loc text="Microsoft Teams Rooms":::应用程序版本的磁贴</span><span class="sxs-lookup"><span data-stu-id="705a0-353">Create a tile that displays :::no-loc text="Microsoft Teams Rooms"::: application versions</span></span>

1.  <span data-ttu-id="705a0-354">从库中选择 "**同心圆 & 列表**"，然后添加新磁贴。</span><span class="sxs-lookup"><span data-stu-id="705a0-354">Select **Donut & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="705a0-355">定义**常规**属性：</span><span class="sxs-lookup"><span data-stu-id="705a0-355">Define the **General** properties:</span></span><br>
    <span data-ttu-id="705a0-356">**组标题：** :::no-loc text="Microsoft Teams Rooms":::应用程序详细信息</span><span class="sxs-lookup"><span data-stu-id="705a0-356">**Group Title:** :::no-loc text="Microsoft Teams Rooms"::: application details</span></span><br>
    <span data-ttu-id="705a0-357">**新组：** 处于</span><span class="sxs-lookup"><span data-stu-id="705a0-357">**New Group:** Selected</span></span>
3.  <span data-ttu-id="705a0-358">定义**页眉**属性：</span><span class="sxs-lookup"><span data-stu-id="705a0-358">Define the **Header** properties:</span></span><br>
    <span data-ttu-id="705a0-359">**标题：** 应用程序版本</span><span class="sxs-lookup"><span data-stu-id="705a0-359">**Title:** Application versions</span></span><br>
    <span data-ttu-id="705a0-360">**副标题：** 运行特定应用程序版本的设备</span><span class="sxs-lookup"><span data-stu-id="705a0-360">**Subtitle:** Devices running specific application versions</span></span>
4.  <span data-ttu-id="705a0-361">定义**同心圆**属性：</span><span class="sxs-lookup"><span data-stu-id="705a0-361">Define the **Donut** properties:</span></span><br>
    <span data-ttu-id="705a0-362">**查询：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```</span><span class="sxs-lookup"><span data-stu-id="705a0-362">**Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```</span></span><br>
    <span data-ttu-id="705a0-363">**文本居中：** 台</span><span class="sxs-lookup"><span data-stu-id="705a0-363">**Center Text:** Devices</span></span><br>
    <span data-ttu-id="705a0-364">**操作：** 量</span><span class="sxs-lookup"><span data-stu-id="705a0-364">**Operation:** Sum</span></span>
5.  <span data-ttu-id="705a0-365">定义**列表**属性。</span><span class="sxs-lookup"><span data-stu-id="705a0-365">Define the **List** properties.</span></span><br>
    <span data-ttu-id="705a0-366">**列表查询：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```</span><span class="sxs-lookup"><span data-stu-id="705a0-366">**List Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```</span></span><br>
    <span data-ttu-id="705a0-367">**隐藏图形：** 处于</span><span class="sxs-lookup"><span data-stu-id="705a0-367">**Hide Graph:** Selected</span></span><br>
    <span data-ttu-id="705a0-368">**启用迷你图：** 未选中</span><span class="sxs-lookup"><span data-stu-id="705a0-368">**Enable Sparklines:** Not selected</span></span>
6.  <span data-ttu-id="705a0-369">定义**列标题**。</span><span class="sxs-lookup"><span data-stu-id="705a0-369">Define **Column Titles**.</span></span><br>
    <span data-ttu-id="705a0-370">**名称：** 计算机名</span><span class="sxs-lookup"><span data-stu-id="705a0-370">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="705a0-371">**值：** 留空</span><span class="sxs-lookup"><span data-stu-id="705a0-371">**Value:** Leave Empty</span></span>
7.  <span data-ttu-id="705a0-372">定义**导航查询**。</span><span class="sxs-lookup"><span data-stu-id="705a0-372">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  <span data-ttu-id="705a0-373">选择 "**应用**"，然后选择 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="705a0-373">Select **Apply** and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-devices-that-have-an-application-error"></a><span data-ttu-id="705a0-374">创建显示有应用程序错误的设备的磁贴</span><span class="sxs-lookup"><span data-stu-id="705a0-374">Create a tile that displays devices that have an application error</span></span>

1.  <span data-ttu-id="705a0-375">从库中选择 "**编号" & 列表**，然后添加新磁贴。</span><span class="sxs-lookup"><span data-stu-id="705a0-375">Select **Number & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="705a0-376">定义**常规**属性。</span><span class="sxs-lookup"><span data-stu-id="705a0-376">Define the **General** properties.</span></span><br>
    <span data-ttu-id="705a0-377">**组标题：** 留空</span><span class="sxs-lookup"><span data-stu-id="705a0-377">**Group Title:** Leave empty</span></span><br>
    <span data-ttu-id="705a0-378">**新组：** 未选中</span><span class="sxs-lookup"><span data-stu-id="705a0-378">**New Group:** Not Selected</span></span>
3.  <span data-ttu-id="705a0-379">定义**图块**属性。</span><span class="sxs-lookup"><span data-stu-id="705a0-379">Define the **Tile** properties.</span></span><br>
    <span data-ttu-id="705a0-380">**图例：** 过去一小时遇到应用程序错误的设备</span><span class="sxs-lookup"><span data-stu-id="705a0-380">**Legend:** Devices that experienced an application error in the last hour</span></span><br>
    <span data-ttu-id="705a0-381">**图块查询：** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```</span><span class="sxs-lookup"><span data-stu-id="705a0-381">**Tile Query:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```</span></span>
4.  <span data-ttu-id="705a0-382">定义**列表**属性。</span><span class="sxs-lookup"><span data-stu-id="705a0-382">Define the **List** properties.</span></span><br>
    <span data-ttu-id="705a0-383">**列表查询：**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span><span class="sxs-lookup"><span data-stu-id="705a0-383">**List Query:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span></span>
5.  <span data-ttu-id="705a0-384">定义**列标题**。</span><span class="sxs-lookup"><span data-stu-id="705a0-384">Define **Column Titles**.</span></span><br>
    <span data-ttu-id="705a0-385">**名称：** 计算机名</span><span class="sxs-lookup"><span data-stu-id="705a0-385">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="705a0-386">**值：** 上一个错误</span><span class="sxs-lookup"><span data-stu-id="705a0-386">**Value:** Last Error</span></span>
6.  <span data-ttu-id="705a0-387">定义**导航查询**。</span><span class="sxs-lookup"><span data-stu-id="705a0-387">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 2001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  <span data-ttu-id="705a0-388">选择 "**应用**"，然后选择 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="705a0-388">Select **Apply** and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-devices-that-have-been-restarted"></a><span data-ttu-id="705a0-389">创建显示已重新启动的设备的磁贴</span><span class="sxs-lookup"><span data-stu-id="705a0-389">Create a tile that displays devices that have been restarted</span></span>

1.  <span data-ttu-id="705a0-390">从库中选择 "**编号" & 列表**，然后添加新磁贴。</span><span class="sxs-lookup"><span data-stu-id="705a0-390">Select **Number & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="705a0-391">定义**常规**属性。</span><span class="sxs-lookup"><span data-stu-id="705a0-391">Define the **General** properties.</span></span><br>
    <span data-ttu-id="705a0-392">**组标题：** 留空</span><span class="sxs-lookup"><span data-stu-id="705a0-392">**Group Title:** Leave empty</span></span><br>
    <span data-ttu-id="705a0-393">**新组：** 未选中</span><span class="sxs-lookup"><span data-stu-id="705a0-393">**New Group:** Not Selected</span></span>
3.  <span data-ttu-id="705a0-394">定义**图块**属性。</span><span class="sxs-lookup"><span data-stu-id="705a0-394">Define the **Tile** properties.</span></span><br>
    <span data-ttu-id="705a0-395">**图例：** 在过去24小时内重新启动应用程序的设备以及重启次数</span><span class="sxs-lookup"><span data-stu-id="705a0-395">**Legend:** Devices where the application was restarted in the last 24 hours, and number of restarts</span></span><br>
    <span data-ttu-id="705a0-396">**图块查询：** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```</span><span class="sxs-lookup"><span data-stu-id="705a0-396">**Tile Query:** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```</span></span>
4.  <span data-ttu-id="705a0-397">定义**列表**属性。</span><span class="sxs-lookup"><span data-stu-id="705a0-397">Define the **List** properties.</span></span><br>
    <span data-ttu-id="705a0-398">**列表查询：**```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```</span><span class="sxs-lookup"><span data-stu-id="705a0-398">**List Query:** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```</span></span>
5.  <span data-ttu-id="705a0-399">定义**列标题**。</span><span class="sxs-lookup"><span data-stu-id="705a0-399">Define **Column Titles**.</span></span><br>
    <span data-ttu-id="705a0-400">**名称：** 计算机名</span><span class="sxs-lookup"><span data-stu-id="705a0-400">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="705a0-401">**值：** 重启次数</span><span class="sxs-lookup"><span data-stu-id="705a0-401">**Value:** Number of Restarts</span></span>
6.  <span data-ttu-id="705a0-402">定义**导航查询**。</span><span class="sxs-lookup"><span data-stu-id="705a0-402">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  <span data-ttu-id="705a0-403">选择 "**应用**"，然后选择 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="705a0-403">Select **Apply** and then **Close**.</span></span>
8.  <span data-ttu-id="705a0-404">选择 "**保存**" 以保存仪表板。</span><span class="sxs-lookup"><span data-stu-id="705a0-404">Select **Save** to save your dashboard.</span></span>

<span data-ttu-id="705a0-405">现在，你已完成创建视图。</span><span class="sxs-lookup"><span data-stu-id="705a0-405">Now you’ve completed creating your views.</span></span>

## <a name="configure-alerts-in-no-loc-textazure-monitor"></a><span data-ttu-id="705a0-406">在中配置警报:::no-loc text="Azure Monitor":::</span><span class="sxs-lookup"><span data-stu-id="705a0-406">Configure Alerts in :::no-loc text="Azure Monitor":::</span></span>
<span data-ttu-id="705a0-407"><a name="Alerts"> </a></span><span class="sxs-lookup"><span data-stu-id="705a0-407"><a name="Alerts"> </a></span></span>

<span data-ttu-id="705a0-408">:::no-loc text="Azure Monitor":::当:::no-loc text="Microsoft Teams Rooms":::控制台遇到问题时，可以引发通知以通知管理员。</span><span class="sxs-lookup"><span data-stu-id="705a0-408">:::no-loc text="Azure Monitor"::: can raise alerts to notify the administrators, when a :::no-loc text="Microsoft Teams Rooms"::: console encounters an issue.</span></span>

<span data-ttu-id="705a0-409">:::no-loc text="Azure Monitor":::包括一种内置的警报机制，可按固定时间间隔通过计划的日志搜索进行运行。</span><span class="sxs-lookup"><span data-stu-id="705a0-409">:::no-loc text="Azure Monitor"::: includes a built-in alerting mechanism that runs through scheduled log searches at regular intervals.</span></span> <span data-ttu-id="705a0-410">如果日志搜索的结果符合某些特定条件，则会创建一条警告记录。</span><span class="sxs-lookup"><span data-stu-id="705a0-410">If the results of the log search match some particular criteria, an alert record is created.</span></span>

<span data-ttu-id="705a0-411">然后，该规则可以自动运行一个或多个操作，主动通知你警报或调用另一个进程。</span><span class="sxs-lookup"><span data-stu-id="705a0-411">The rule can then automatically run one or more actions to proactively notify you of the alert or invoke another process.</span></span> <span data-ttu-id="705a0-412">警报的可能选项如下：</span><span class="sxs-lookup"><span data-stu-id="705a0-412">The possible options with alerts are:</span></span>
-   <span data-ttu-id="705a0-413">发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="705a0-413">Sending an email</span></span>
-   <span data-ttu-id="705a0-414">通过 HTTP POST 请求调用外部进程</span><span class="sxs-lookup"><span data-stu-id="705a0-414">Invoking an external process through an HTTP POST request</span></span>
-   <span data-ttu-id="705a0-415">在服务中:::no-loc text="Azure Automation":::启动 runbook</span><span class="sxs-lookup"><span data-stu-id="705a0-415">Starting a runbook in :::no-loc text="Azure Automation"::: service</span></span>

<span data-ttu-id="705a0-416">有关中:::no-loc text="Azure Monitor":::的警报的详细信息，请参阅[在中:::no-loc text="Azure Monitor":::记录警报](https://docs.microsoft.com/azure/azure-monitor/platform/alerts-unified-log)。</span><span class="sxs-lookup"><span data-stu-id="705a0-416">See [Log alerts in :::no-loc text="Azure Monitor":::](https://docs.microsoft.com/azure/azure-monitor/platform/alerts-unified-log) to learn more about the alerts in :::no-loc text="Azure Monitor":::.</span></span>

> [!NOTE]
> <span data-ttu-id="705a0-417">以下示例将在:::no-loc text="Microsoft Teams Rooms":::设备生成硬件或应用程序错误时发送电子邮件警报。</span><span class="sxs-lookup"><span data-stu-id="705a0-417">The following examples send email alerts when a :::no-loc text="Microsoft Teams Rooms"::: device generates a hardware or an application error.</span></span>

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-hardware-issues"></a><span data-ttu-id="705a0-418">配置针对硬件问题的:::no-loc text="Microsoft Teams Rooms":::电子邮件警报</span><span class="sxs-lookup"><span data-stu-id="705a0-418">Configure an email alert for :::no-loc text="Microsoft Teams Rooms"::: hardware issues</span></span>

<span data-ttu-id="705a0-419">配置检查在过去一小时内:::no-loc text="Microsoft Teams Rooms":::遇到硬件问题的设备的警报规则。</span><span class="sxs-lookup"><span data-stu-id="705a0-419">Configure an alert rule that checks for :::no-loc text="Microsoft Teams Rooms"::: devices that have encountered hardware issues within the last hour.</span></span>
1.  <span data-ttu-id="705a0-420">登录[ :::no-loc text="Microsoft Azure":::门户](https://portal.azure.com)并转到:::no-loc text="Log Analytics":::并选择您的工作区。</span><span class="sxs-lookup"><span data-stu-id="705a0-420">Sign in to the [:::no-loc text="Microsoft Azure"::: portal](https://portal.azure.com) and go to :::no-loc text="Log Analytics"::: and select your workspace.</span></span>

2. <span data-ttu-id="705a0-421">导航到您:::no-loc text="Log Analytics":::的工作区并选择 "**通知**"，然后选择 "**新建通知规则**"</span><span class="sxs-lookup"><span data-stu-id="705a0-421">Navigate to your :::no-loc text="Log Analytics"::: workspace and select **Alerts** and then select **New alert rule**</span></span>

3. <span data-ttu-id="705a0-422">选择 "**添加条件**"，然后选择 "**自定义日志搜索**"</span><span class="sxs-lookup"><span data-stu-id="705a0-422">Select **Add condition** and then **Custom log search**</span></span>

4.  <span data-ttu-id="705a0-423">在 "搜索查询" 文本框中输入以下查询。</span><span class="sxs-lookup"><span data-stu-id="705a0-423">Enter the following query to the Search query text box.</span></span><br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF
    |sort by TimeGenerated desc
    ```

5.  <span data-ttu-id="705a0-424">配置警报逻辑设置：</span><span class="sxs-lookup"><span data-stu-id="705a0-424">Configure the Alert logic settings:</span></span><br>
    <span data-ttu-id="705a0-425">**基于：** 结果数</span><span class="sxs-lookup"><span data-stu-id="705a0-425">**Based on:** Number of results</span></span><br>
    <span data-ttu-id="705a0-426">**条件：** 大于</span><span class="sxs-lookup"><span data-stu-id="705a0-426">**Condition:** Greater then</span></span><br>
    <span data-ttu-id="705a0-427">**Treshold：** 0</span><span class="sxs-lookup"><span data-stu-id="705a0-427">**Treshold:** 0</span></span><br>

6. <span data-ttu-id="705a0-428">配置评估设置，然后选择 "**完成**"：</span><span class="sxs-lookup"><span data-stu-id="705a0-428">Configure Evaluation settings and select **Done**:</span></span> <br>
    <span data-ttu-id="705a0-429">**周期（分钟）：** 60</span><span class="sxs-lookup"><span data-stu-id="705a0-429">**Period (in minutes):** 60</span></span><br>
    <span data-ttu-id="705a0-430">**频率（分钟）：** 60</span><span class="sxs-lookup"><span data-stu-id="705a0-430">**Frequency (in minutes):** 60</span></span><br>

7. <span data-ttu-id="705a0-431">配置操作组：</span><span class="sxs-lookup"><span data-stu-id="705a0-431">Configure action groups:</span></span>
    1.  <span data-ttu-id="705a0-432">选择 "**新建**"</span><span class="sxs-lookup"><span data-stu-id="705a0-432">Select **Create New**</span></span>
    2.  <span data-ttu-id="705a0-433">为 "*操作组名称*" 和 "*短名称*" 字段提供合适的名称。</span><span class="sxs-lookup"><span data-stu-id="705a0-433">Provide suitable names for the *Action group name* and *Short Name* fields.</span></span>
    3.  <span data-ttu-id="705a0-434">指定唯一的*操作名称*，选择 "**电子邮件/短信/短信/推/语音**"，然后选择 "**编辑详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="705a0-434">Specify a unique *Action Name* and select **Email/SMS/Push/Voice**, and then select **Edit details**.</span></span>
    4.  <span data-ttu-id="705a0-435">选择 "电子邮件" 复选框，并提供将接收通知的人员或组的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="705a0-435">Select the Email checkbox and provide the email address of the person or group that will recieve the alerts.</span></span>
    5.  <span data-ttu-id="705a0-436">您还可以提供您的电话号码以接收短信通知、语音通话或同时获得这两者。</span><span class="sxs-lookup"><span data-stu-id="705a0-436">You may also provide your phone number to get notified with SMS, a voice call or both.</span></span>
    6. <span data-ttu-id="705a0-437">选择 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="705a0-437">Select **OK**.</span></span>

8. <span data-ttu-id="705a0-438">如果想要替代预警电子邮件的主题行，请**自定义操作**。</span><span class="sxs-lookup"><span data-stu-id="705a0-438">**Customize Actions** if you like to override the subject line of the alert emails.</span></span>

9. <span data-ttu-id="705a0-439">指定规则名称和说明。</span><span class="sxs-lookup"><span data-stu-id="705a0-439">Specify a rule name and description.</span></span><br>
    <span data-ttu-id="705a0-440">**规则名称：** :::no-loc text="Microsoft Teams Rooms":::硬件故障警报</span><span class="sxs-lookup"><span data-stu-id="705a0-440">**Rule Name:** :::no-loc text="Microsoft Teams Rooms"::: Hardware Failure Alert</span></span><br>
    <span data-ttu-id="705a0-441">**说明：** 过去一小时内遇到硬件问题的设备的列表</span><span class="sxs-lookup"><span data-stu-id="705a0-441">**Description:** List of devices that encountered a hardware issue within the last hour</span></span><br>

10. <span data-ttu-id="705a0-442">选择预期的严重性，并确保规则已启用。</span><span class="sxs-lookup"><span data-stu-id="705a0-442">Select the intended severity and make sure the rule is enabled.</span></span>

11. <span data-ttu-id="705a0-443">选择 "**创建通知规则**"。</span><span class="sxs-lookup"><span data-stu-id="705a0-443">Select **Create alert rule**.</span></span>

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-application-issues"></a><span data-ttu-id="705a0-444">为:::no-loc text="Microsoft Teams Rooms":::应用程序问题配置电子邮件警报</span><span class="sxs-lookup"><span data-stu-id="705a0-444">Configure an email alert for :::no-loc text="Microsoft Teams Rooms"::: application issues</span></span>

<span data-ttu-id="705a0-445">重复相同的过程，但使用以下查询列出过去一小时内遇到的应用程序问题的设备。</span><span class="sxs-lookup"><span data-stu-id="705a0-445">Repeat the same procedure but use the following query to list devices that have encountered application issues within the last hour.</span></span>

    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF
    | sort by TimeGenerated desc
    ```

<span data-ttu-id="705a0-446">现在，你已完成定义通知。</span><span class="sxs-lookup"><span data-stu-id="705a0-446">Now you’ve completed defining alerts.</span></span> <span data-ttu-id="705a0-447">你可以使用上述示例定义其他警报。</span><span class="sxs-lookup"><span data-stu-id="705a0-447">You can define additional alerts by using the examples above.</span></span>

<span data-ttu-id="705a0-448">生成警报时，你将收到一封电子邮件，其中列出了在过去一小时内遇到问题的设备。</span><span class="sxs-lookup"><span data-stu-id="705a0-448">When an alert is generated, you’ll get an email that lists the devices that encountered an issue within the last hour.</span></span>

<span data-ttu-id="705a0-449">![通知:::no-loc text="Azure Monitor":::电子邮件示例](../media/Deploy-Azure-Monitor-6.png "通知:::no-loc text="Azure Monitor":::电子邮件示例"）</span><span class="sxs-lookup"><span data-stu-id="705a0-449">![Sample :::no-loc text="Azure Monitor"::: alert email](../media/Deploy-Azure-Monitor-6.png "Sample :::no-loc text="Azure Monitor"::: alert email")</span></span>

## <a name="configure-all-devices-for-no-loc-textazure-monitoring"></a><span data-ttu-id="705a0-450">配置所有设备:::no-loc text="Azure Monitoring":::</span><span class="sxs-lookup"><span data-stu-id="705a0-450">Configure all devices for :::no-loc text="Azure Monitoring":::</span></span>
<span data-ttu-id="705a0-451"><a name="configure_all_devices"></a>配置仪表板和警报后，您可以在所有:::no-loc text="Microsoft Monitoring"::: :::no-loc text="Microsoft Teams Rooms":::设备上设置和配置代理以完成监视部署。</span><span class="sxs-lookup"><span data-stu-id="705a0-451"><a name="configure_all_devices"> </a> After the dashboards and alerts are configured, you can set up and configure :::no-loc text="Microsoft Monitoring"::: agent on all :::no-loc text="Microsoft Teams Rooms"::: devices to complete your monitoring deployment.</span></span>

<span data-ttu-id="705a0-452">虽然你可以在每台设备:::no-loc text="Microsoft Monitoring":::上手动安装和配置代理，但我们强烈建议你充分利用现有软件部署工具和方法。</span><span class="sxs-lookup"><span data-stu-id="705a0-452">Although you can install and configure the :::no-loc text="Microsoft Monitoring"::: agent manually on each device, we highly recommend you leverage existing software deployment tools and methods.</span></span>

<span data-ttu-id="705a0-453">如果你是首次:::no-loc text="Microsoft Teams Rooms":::生成设备，你可能希望将:::no-loc text="Microsoft Monitoring":::代理设置和配置步骤包含在你的生成过程中。</span><span class="sxs-lookup"><span data-stu-id="705a0-453">If you’re building your :::no-loc text="Microsoft Teams Rooms"::: devices for the first time, you might want to include the :::no-loc text="Microsoft Monitoring"::: agent setup and configuration steps as part of your build process.</span></span> <span data-ttu-id="705a0-454">有关详细信息，请参阅[使用命令行安装代理](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line)。</span><span class="sxs-lookup"><span data-stu-id="705a0-454">For more information, see [Install the agent using the command line](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line).</span></span>

### <a name="deploying-no-loc-textmicrosoft-monitoring-agent-by-using-a-group-policy-object-gpo"></a><span data-ttu-id="705a0-455">使用:::no-loc text="Microsoft Monitoring":::组策略对象（GPO）部署代理</span><span class="sxs-lookup"><span data-stu-id="705a0-455">Deploying :::no-loc text="Microsoft Monitoring"::: agent by using a Group Policy Object (GPO)</span></span>

<span data-ttu-id="705a0-456">如果在实现:::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Azure Monitoring":::之前已部署了设备，则可以使用提供的脚本通过 " :::no-loc text="Active Directory":::组策略" 对象设置和配置代理。</span><span class="sxs-lookup"><span data-stu-id="705a0-456">If you already deployed your :::no-loc text="Microsoft Teams Rooms"::: devices before you implement :::no-loc text="Azure Monitoring":::, you can use the provided script to set up and configure the agents by using :::no-loc text="Active Directory"::: group policy objects.</span></span>

1.  <span data-ttu-id="705a0-457">创建共享网络路径并向 "**域计算机**" 组授予 "读取" 访问权限。</span><span class="sxs-lookup"><span data-stu-id="705a0-457">Create a shared network path and grant read access to **Domain Computers** group.</span></span>

2.  <span data-ttu-id="705a0-458">从下载64位版本的:::no-loc text="Microsoft Monitoring"::: :::no-loc text="Windows":::<https://go.microsoft.com/fwlink/?LinkID=517476></span><span class="sxs-lookup"><span data-stu-id="705a0-458">Download the 64-bit version of the :::no-loc text="Microsoft Monitoring"::: Agent for :::no-loc text="Windows"::: from <https://go.microsoft.com/fwlink/?LinkID=517476></span></span>

3.  <span data-ttu-id="705a0-459">将安装程序包的内容提取到网络共享中。</span><span class="sxs-lookup"><span data-stu-id="705a0-459">Extract the contents of the setup package into the network share.</span></span>
    1.  <span data-ttu-id="705a0-460">打开命令提示符窗口，然后执行**MMASetup-AMD64/c**</span><span class="sxs-lookup"><span data-stu-id="705a0-460">Open a Command Prompt window, and then execute **MMASetup-AMD64.exe /c**</span></span>
    2.  <span data-ttu-id="705a0-461">指定刚刚创建的共享，然后提取内容。</span><span class="sxs-lookup"><span data-stu-id="705a0-461">Specify the share you just created, and extract the content.</span></span>

4.  <span data-ttu-id="705a0-462">创建新的组策略对象，并将其分配给:::no-loc text="Microsoft Teams Rooms":::计算机帐户所在的组织单位。</span><span class="sxs-lookup"><span data-stu-id="705a0-462">Create a new Group Policy Object and assign it to the organizational unit where :::no-loc text="Microsoft Teams Rooms"::: machine accounts are located.</span></span>

5.  <span data-ttu-id="705a0-463">配置 PowerShell 执行策略：</span><span class="sxs-lookup"><span data-stu-id="705a0-463">Configure PowerShell execution policy:</span></span>
    1.  <span data-ttu-id="705a0-464">编辑新创建的组策略对象，并导航到 " \\计算机\\配置策略\\ :::no-loc text="Windows"::: " \\管理模板组件:::no-loc text="Windows PowerShell":::</span><span class="sxs-lookup"><span data-stu-id="705a0-464">Edit the newly created Group Policy Object and navigate to Computer Configuration \\ Policies \\ Administrative Templates \\ :::no-loc text="Windows"::: Components \\ :::no-loc text="Windows PowerShell":::</span></span>
    2.  <span data-ttu-id="705a0-465">启用 "**打开脚本执行**" 和 "设置**执行策略**" 以**允许本地脚本**。</span><span class="sxs-lookup"><span data-stu-id="705a0-465">Enable the **Turn on Script Execution** and set **Execution Policy** to **Allow Local Scripts**.</span></span>

6.  <span data-ttu-id="705a0-466">配置启动脚本：</span><span class="sxs-lookup"><span data-stu-id="705a0-466">Configure the startup script:</span></span>
    1.  <span data-ttu-id="705a0-467">复制以下脚本并将其另存为 Install-MMAgent。</span><span class="sxs-lookup"><span data-stu-id="705a0-467">Copy the following script and save it as Install-MMAgent.ps1.</span></span>
    2.  <span data-ttu-id="705a0-468">修改 WorkspaceId、WorkspaceKey 和 SetupPath 参数以匹配您的配置。</span><span class="sxs-lookup"><span data-stu-id="705a0-468">Modify WorkspaceId, WorkspaceKey, and SetupPath parameters to match your configuration.</span></span>
    3.  <span data-ttu-id="705a0-469">编辑相同的组策略对象并导航到 "计算机\\配置\\ :::no-loc text="Windows":::策略\\ " 设置脚本（启动/关闭）</span><span class="sxs-lookup"><span data-stu-id="705a0-469">Edit the same Group Policy Object and navigate to Computer Configuration \\ Policies \\ :::no-loc text="Windows"::: Settings \\ Scripts (Startup/Shutdown)</span></span>
    4.  <span data-ttu-id="705a0-470">双击以选择 "**启动**"，然后选择 " **PowerShell 脚本**"。</span><span class="sxs-lookup"><span data-stu-id="705a0-470">Double-click to select **Startup**, and then select **PowerShell Scripts**.</span></span>
    5.  <span data-ttu-id="705a0-471">选择 "**显示文件**"，然后将**Install-MMAgent**文件复制到该文件夹。</span><span class="sxs-lookup"><span data-stu-id="705a0-471">Select **Show Files**, and then copy the **Install-MMAgent.ps1** file to that folder.</span></span>
    6.  <span data-ttu-id="705a0-472">选择 "**添加**"，然后单击 "**浏览**"。</span><span class="sxs-lookup"><span data-stu-id="705a0-472">Select **Add**, and then **Browse**.</span></span>
    7.  <span data-ttu-id="705a0-473">选择您刚刚复制的 ps1 脚本。</span><span class="sxs-lookup"><span data-stu-id="705a0-473">Select the ps1 script you just copied.</span></span>

7.  <span data-ttu-id="705a0-474">:::no-loc text="Microsoft Teams Rooms":::设备应在第二次:::no-loc text="Microsoft Monitoring":::重启时安装和配置代理。</span><span class="sxs-lookup"><span data-stu-id="705a0-474">:::no-loc text="Microsoft Teams Rooms"::: devices should install and configure the :::no-loc text="Microsoft Monitoring"::: agent with the second reboot.</span></span>

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
> <span data-ttu-id="705a0-475">如果需要重新配置代理、将代理移到其他工作区或在初始安装后修改代理服务器设置，可以参阅[管理和维护:::no-loc text="Log Analytics":::代理](https://docs.microsoft.com/azure/azure-monitor/platform/agent-manage)的文章。</span><span class="sxs-lookup"><span data-stu-id="705a0-475">You can refer to the article [Managing and maintaining the :::no-loc text="Log Analytics"::: agent](https://docs.microsoft.com/azure/azure-monitor/platform/agent-manage) when you need to reconfigure an agent, move it to a different workspace, or modify proxy settings after the initial installation.</span></span>

## <a name="additional-solutions"></a><span data-ttu-id="705a0-476">其他解决方案</span><span class="sxs-lookup"><span data-stu-id="705a0-476">Additional Solutions</span></span>
<span data-ttu-id="705a0-477"><a name="Solutions"> </a></span><span class="sxs-lookup"><span data-stu-id="705a0-477"><a name="Solutions"> </a></span></span>

<span data-ttu-id="705a0-478">:::no-loc text="Azure Monitor":::通过其[解决方案库](https://docs.microsoft.com/azure/azure-monitor/insights/solutions)提供内置管理解决方案，进一步帮助你监视你的环境。</span><span class="sxs-lookup"><span data-stu-id="705a0-478">:::no-loc text="Azure Monitor"::: provides built-in management solutions through its [solution gallery](https://docs.microsoft.com/azure/azure-monitor/insights/solutions) to further help you monitor your environment.</span></span> <span data-ttu-id="705a0-479">我们强烈建议你将[警报管理](https://docs.microsoft.com/azure/azure-monitor/platform/alert-management-solution)和[ :::no-loc text="Azure Log Analytics":::代理运行状况](https://docs.microsoft.com/azure/azure-monitor/insights/solution-agenthealth)解决方案添加到你的工作区。</span><span class="sxs-lookup"><span data-stu-id="705a0-479">We highly recommend that you add [Alert Management](https://docs.microsoft.com/azure/azure-monitor/platform/alert-management-solution) and [:::no-loc text="Azure Log Analytics"::: Agent Health](https://docs.microsoft.com/azure/azure-monitor/insights/solution-agenthealth) solutions to your workspace as well.</span></span>

> [!NOTE]
> <span data-ttu-id="705a0-480">代理运行状况解决方案可帮助你在你的环境:::no-loc text="Microsoft Monitoring":::内识别过时或损坏的代理，并且警报管理解决方案提供有关在给定期间内引发的警报的详细信息。</span><span class="sxs-lookup"><span data-stu-id="705a0-480">The Agent Health solution can help you identify outdated or broken :::no-loc text="Microsoft Monitoring"::: agents within your environment, and the Alert Management solution provides details about the alerts that have been raised within a given period.</span></span>

## <a name="see-also"></a><span data-ttu-id="705a0-481">另请参阅</span><span class="sxs-lookup"><span data-stu-id="705a0-481">See also</span></span>

[<span data-ttu-id="705a0-482">计划:::no-loc text="Microsoft Teams Rooms":::管理与:::no-loc text="Azure Monitor":::</span><span class="sxs-lookup"><span data-stu-id="705a0-482">Plan :::no-loc text="Microsoft Teams Rooms"::: management with :::no-loc text="Azure Monitor":::</span></span>](azure-monitor-plan.md)

[<span data-ttu-id="705a0-483">管理:::no-loc text="Microsoft Teams Rooms":::设备:::no-loc text="Azure Monitor":::</span><span class="sxs-lookup"><span data-stu-id="705a0-483">Manage :::no-loc text="Microsoft Teams Rooms"::: devices with :::no-loc text="Azure Monitor":::</span></span>](azure-monitor-manage.md)
