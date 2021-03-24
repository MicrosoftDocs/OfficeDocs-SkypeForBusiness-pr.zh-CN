---
title: 使用 Operations Management Suite (OMS) 监视云连接器
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: edf4a04c-d4c9-4c05-aacc-9e084618bb55
description: 阅读本主题，了解如何使用 Microsoft Operations Management Suite (OMS) 云连接器版本 2.1 和更高版本) 。
ms.openlocfilehash: 55685aae01bdcc3c7c979627dbba910bb33203fa
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098538"
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a><span data-ttu-id="5af04-103">使用 Operations Management Suite (OMS) 监视云连接器</span><span class="sxs-lookup"><span data-stu-id="5af04-103">Monitor Cloud Connector using Operations Management Suite (OMS)</span></span>

> [!Important]
> <span data-ttu-id="5af04-104">云连接器版本将于 2021 年 7 月 31 日与 Skype for Business Online 一起停用。</span><span class="sxs-lookup"><span data-stu-id="5af04-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="5af04-105">组织升级到 Teams 后，了解如何使用直接路由将本地电话网络连接到[Teams。](/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="5af04-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="5af04-106">阅读本主题，了解如何使用 Microsoft Operations Management Suite (OMS) 云连接器版本 2.1 和更高版本) 。</span><span class="sxs-lookup"><span data-stu-id="5af04-106">Read this topic to learn how to monitor your Cloud Connector version 2.1 and later deployment by using Microsoft Operations Management Suite (OMS).</span></span>

<span data-ttu-id="5af04-107">现在，可以使用 Operations Management Suite (OMS) （Microsoft 云 IT 管理解决方案）监控云连接器 2.1 版和更高版本的部署。</span><span class="sxs-lookup"><span data-stu-id="5af04-107">You can now monitor your Cloud Connector version 2.1 and later deployment by using Operations Management Suite (OMS), a Microsoft cloud IT management solution.</span></span> <span data-ttu-id="5af04-108">利用 OMS Log Analytics，可以监视和分析资源（包括物理和虚拟机）的可用性和性能。</span><span class="sxs-lookup"><span data-stu-id="5af04-108">OMS Log Analytics enables you to monitor and analyze the availability and performance of resources including physical and virtual machines.</span></span> <span data-ttu-id="5af04-109">有关 OMS 和 Log Analytics 详细信息，请参阅 [什么是 Operations Management Suite (OMS) ？](/azure/operations-management-suite/operations-management-suite-overview)</span><span class="sxs-lookup"><span data-stu-id="5af04-109">For more information about OMS and Log Analytics, see [What is Operations Management Suite (OMS)?](/azure/operations-management-suite/operations-management-suite-overview)</span></span>

<span data-ttu-id="5af04-110">本主题包含以下各部分：</span><span class="sxs-lookup"><span data-stu-id="5af04-110">This topic contains the following sections:</span></span>

- <span data-ttu-id="5af04-111">先决条件</span><span class="sxs-lookup"><span data-stu-id="5af04-111">Prerequisites</span></span>

- <span data-ttu-id="5af04-112">配置云连接器以使用 OMS</span><span class="sxs-lookup"><span data-stu-id="5af04-112">Configure Cloud Connector to use OMS</span></span>

- <span data-ttu-id="5af04-113">配置 OMS</span><span class="sxs-lookup"><span data-stu-id="5af04-113">Configure OMS</span></span>

- <span data-ttu-id="5af04-114">分析 Log Analytics 存储库中的警报</span><span class="sxs-lookup"><span data-stu-id="5af04-114">Analyze the alerts in your Log Analytics repository</span></span>

- <span data-ttu-id="5af04-115">建议的监视集</span><span class="sxs-lookup"><span data-stu-id="5af04-115">Recommended monitoring set</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5af04-116">先决条件</span><span class="sxs-lookup"><span data-stu-id="5af04-116">Prerequisites</span></span>

<span data-ttu-id="5af04-117">在可以使用 OMS 监视云连接器部署之前，你将需要以下各项：</span><span class="sxs-lookup"><span data-stu-id="5af04-117">Before you can use OMS to monitor your Cloud Connector deployment, you will need the following:</span></span>

- <span data-ttu-id="5af04-118">**Azure 帐户和 OMS 工作区。**</span><span class="sxs-lookup"><span data-stu-id="5af04-118">**An Azure account and an OMS workspace.**</span></span> <span data-ttu-id="5af04-119">如果还没有 Azure 帐户，则需要创建一个帐户才能使用 OMS Log Analytics。</span><span class="sxs-lookup"><span data-stu-id="5af04-119">If you don't already have an Azure account, you will need to create one to use OMS Log Analytics.</span></span> <span data-ttu-id="5af04-120">若要了解如何创建 Azure 帐户和设置 OMS 工作区，请参阅 Log [Analytics 工作区入门](/azure/log-analytics/log-analytics-get-started)。</span><span class="sxs-lookup"><span data-stu-id="5af04-120">For information about how to create an Azure account and set up an OMS workspace, see [Get started with a Log Analytics workspace](/azure/log-analytics/log-analytics-get-started).</span></span>

- <span data-ttu-id="5af04-121">**云连接器版本 2.1 或更高版本**</span><span class="sxs-lookup"><span data-stu-id="5af04-121">**Cloud Connector version 2.1 or later**</span></span>

- <span data-ttu-id="5af04-122">**Log Analytics 云连接器监控** 需要新的日志搜索。</span><span class="sxs-lookup"><span data-stu-id="5af04-122">**Log Analytics new log search** is required for Cloud Connector monitoring.</span></span> <span data-ttu-id="5af04-123">有关详细信息，请参阅将 [Azure Log Analytics 工作区升级到新的日志搜索](/azure/log-analytics/log-analytics-log-search-upgrade)。</span><span class="sxs-lookup"><span data-stu-id="5af04-123">For more information, see [Upgrade your Azure Log Analytics workspace to new log search](/azure/log-analytics/log-analytics-log-search-upgrade).</span></span>

## <a name="configure-cloud-connector-to-use-oms"></a><span data-ttu-id="5af04-124">配置云连接器以使用 OMS</span><span class="sxs-lookup"><span data-stu-id="5af04-124">Configure Cloud Connector to use OMS</span></span>

<span data-ttu-id="5af04-125">你需要将云连接器本地环境配置为使用 OMS。</span><span class="sxs-lookup"><span data-stu-id="5af04-125">You'll need to configure your Cloud Connector on-premises environment to use OMS.</span></span> <span data-ttu-id="5af04-126">为此，您需要 OMS 工作区 ID 和密钥，可通过使用 OMS 门户找到，如下所示：设置 -- 连接源 \> -- \> Windows 服务器：</span><span class="sxs-lookup"><span data-stu-id="5af04-126">To do this, you will need your OMS workspace ID and key, which you can find by using the OMS portal as follows: Settings --\>Connected Sources --\> Windows Servers:</span></span>

![云连接器 OMS 的屏幕截图](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)

<span data-ttu-id="5af04-128">配置云连接器以使用 OMS 的方式取决于你的方案：</span><span class="sxs-lookup"><span data-stu-id="5af04-128">How you configure Cloud Connector to use OMS depends on your scenario:</span></span>

- <span data-ttu-id="5af04-129">**如果要安装新的** 云连接器设备或要重新部署设备，请按照以下步骤操作，然后再运行 Install-CcAppliance：</span><span class="sxs-lookup"><span data-stu-id="5af04-129">**If you are installing a new Cloud Connector appliance or you want to re-deploy an appliance**, follow these steps before you run Install-CcAppliance:</span></span>

    1. <span data-ttu-id="5af04-130">在CloudConnector.ini文件 [Common] 部分中，将 OMSEnabled 参数设置为 True。</span><span class="sxs-lookup"><span data-stu-id="5af04-130">In the CloudConnector.ini file [Common] section, set the OMSEnabled parameter to True.</span></span>

        <span data-ttu-id="5af04-131">每次部署或升级云连接器时，它都会尝试将 OMS 代理自动安装到 VM 上。</span><span class="sxs-lookup"><span data-stu-id="5af04-131">Each time Cloud Connector is deployed or upgraded, it will try to install the OMS agent automatically onto the VMs.</span></span> <span data-ttu-id="5af04-132">启用此功能，以便 OMS 代理可以保存云连接器自动更新。</span><span class="sxs-lookup"><span data-stu-id="5af04-132">Enable this feature so the OMS agent can survive the Cloud Connector automatic update.</span></span>

    2. <span data-ttu-id="5af04-133">若要配置 OMS ID 和密钥，请运行 Set-CcCredential -AccountType OMSWorkspace。</span><span class="sxs-lookup"><span data-stu-id="5af04-133">To configure the OMS ID and key, run Set-CcCredential -AccountType OMSWorkspace.</span></span> 

- <span data-ttu-id="5af04-134">**如果要将 OMS 代理安装到现有云连接器设备**，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="5af04-134">**If you are installing an OMS agent onto an existing Cloud Connector appliance**, follow these steps:</span></span>

    1. <span data-ttu-id="5af04-135">在CloudConnector.ini文件 [Common] 部分中，设置 OMSEnabled=true。</span><span class="sxs-lookup"><span data-stu-id="5af04-135">In the CloudConnector.ini file [Common] section, set OMSEnabled=true.</span></span> 

    2. <span data-ttu-id="5af04-136">运行 Import-CcConfiguration。</span><span class="sxs-lookup"><span data-stu-id="5af04-136">Run Import-CcConfiguration.</span></span> 

    3. <span data-ttu-id="5af04-137">运行 Install-CcOMSAgent。</span><span class="sxs-lookup"><span data-stu-id="5af04-137">Run Install-CcOMSAgent.</span></span> 

        > [!NOTE]
        > <span data-ttu-id="5af04-138">如果从未设置 OMSWorkspace 凭据，则当您运行 install-CcOMSAgent 时，系统会提示您输入凭据。</span><span class="sxs-lookup"><span data-stu-id="5af04-138">If the OMSWorkspace credential has never been set, you are prompted for the credential when you run install-CcOMSAgent.</span></span> 

- <span data-ttu-id="5af04-139">**如果要更新已安装 OMS 代理的云连接器设备中的 OMS 工作区 ID 或密钥：**</span><span class="sxs-lookup"><span data-stu-id="5af04-139">**If you want to update the OMS workspace ID or key in a Cloud Connector appliance that has already installed an OMS agent:**</span></span>

    1. <span data-ttu-id="5af04-140">若要配置 OMS ID 和密钥，请运行 Set-CcCredential -AccountType OMSWorkspace。</span><span class="sxs-lookup"><span data-stu-id="5af04-140">To configure the OMS ID and key, run Set-CcCredential -AccountType OMSWorkspace.</span></span> 

    2. <span data-ttu-id="5af04-141">若要应用更新，请运行 Install-CcOMSAgent。</span><span class="sxs-lookup"><span data-stu-id="5af04-141">To apply the updates, run Install-CcOMSAgent.</span></span> 

- <span data-ttu-id="5af04-142">**对于所有方案，验证代理是否按如下方式连接：**</span><span class="sxs-lookup"><span data-stu-id="5af04-142">**For all scenarios, verify that the agents are connected as follows:**</span></span>

    <span data-ttu-id="5af04-143">在 OMS 门户中，转到设置 - \> 连接源 - \> Windows 服务器。</span><span class="sxs-lookup"><span data-stu-id="5af04-143">In the OMS portal, go to Settings -\> Connected Sources -\> Windows Servers.</span></span> <span data-ttu-id="5af04-144">你将看到已连接计算机的列表。</span><span class="sxs-lookup"><span data-stu-id="5af04-144">You will see a list of connected machines.</span></span> 

## <a name="configure-oms"></a><span data-ttu-id="5af04-145">配置 OMS</span><span class="sxs-lookup"><span data-stu-id="5af04-145">Configure OMS</span></span>

<span data-ttu-id="5af04-146">接下来，您需要使用 OMS 门户指定 OMS 配置。</span><span class="sxs-lookup"><span data-stu-id="5af04-146">Next, you will need to specify your OMS configuration by using the OMS portal.</span></span> <span data-ttu-id="5af04-147">具体而言，你将需要：</span><span class="sxs-lookup"><span data-stu-id="5af04-147">Specifically, you will need to:</span></span>

- <span data-ttu-id="5af04-148">指定有关事件日志和性能计数器的信息。</span><span class="sxs-lookup"><span data-stu-id="5af04-148">Specify information about event logs and performance counters.</span></span>

- <span data-ttu-id="5af04-149">创建通知。</span><span class="sxs-lookup"><span data-stu-id="5af04-149">Create alerts.</span></span> 

### <a name="specify-information-about-event-logs-and-performance-counters"></a><span data-ttu-id="5af04-150">指定有关事件日志和性能计数器的信息</span><span class="sxs-lookup"><span data-stu-id="5af04-150">Specify information about event logs and performance counters</span></span>

<span data-ttu-id="5af04-151">在 OMS 门户中，必须指定有关事件日志和性能计数器的信息，如下所示：</span><span class="sxs-lookup"><span data-stu-id="5af04-151">In the OMS portal, you must specify information about the event logs and performance counters as follows:</span></span>

1. <span data-ttu-id="5af04-152">转到设置 - \> 数据 - Windows \> 事件日志，并添加事件日志：</span><span class="sxs-lookup"><span data-stu-id="5af04-152">Go to Settings-\>Data-\>Windows Event logs, and add event logs for:</span></span> 

   - <span data-ttu-id="5af04-153">Lync Server</span><span class="sxs-lookup"><span data-stu-id="5af04-153">Lync Server</span></span>

   - <span data-ttu-id="5af04-154">应用程序</span><span class="sxs-lookup"><span data-stu-id="5af04-154">Application</span></span>

     > [!NOTE]
     > <span data-ttu-id="5af04-155">您必须在文本框中手动输入 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="5af04-155">You must manually enter Lync Server in the text box.</span></span> <span data-ttu-id="5af04-156">它不会显示为下拉列表中的选项。</span><span class="sxs-lookup"><span data-stu-id="5af04-156">It does not appear as an option in the drop-down list.</span></span> 

     <span data-ttu-id="5af04-157">有关详细信息，请参阅 Log [Analytics 中的 Windows 事件日志数据源](/azure/log-analytics/log-analytics-data-sources-windows-events)</span><span class="sxs-lookup"><span data-stu-id="5af04-157">For more information, see [Windows event log data sources in Log Analytics](/azure/log-analytics/log-analytics-data-sources-windows-events)</span></span>

2. <span data-ttu-id="5af04-158">转到设置 - \> 数据 - Windows 性能计数器，并 \> 添加性能计数器：</span><span class="sxs-lookup"><span data-stu-id="5af04-158">Go to Settings-\>Data-\> Windows Performance Counters, and add performance counters for:</span></span> 

   - <span data-ttu-id="5af04-159">**操作系统级别计数器**。</span><span class="sxs-lookup"><span data-stu-id="5af04-159">**OS level counters**.</span></span> <span data-ttu-id="5af04-160">可以添加操作系统级别计数器（如处理器使用率、内存使用率、网络使用情况）或使用现有解决方案（如容量和性能、网络性能监视器）而无需显式添加计数器。</span><span class="sxs-lookup"><span data-stu-id="5af04-160">You can add OS level counters, such as processor usage, memory usage, network usage, or you can use existing solutions such as Capacity and Performance, Network Performance Monitor without adding counters explicitly.</span></span> <span data-ttu-id="5af04-161">无论你决定如何监视它们，Microsoft 都建议您监视这些操作系统计数器。</span><span class="sxs-lookup"><span data-stu-id="5af04-161">No matter how you decide to monitor them, Microsoft recommends that you monitor these OS counters.</span></span>

   - <span data-ttu-id="5af04-162">**Skype for Business 计数器**。</span><span class="sxs-lookup"><span data-stu-id="5af04-162">**Skype for Business counters**.</span></span> <span data-ttu-id="5af04-163">Skype for Business 提供了许多计数器。</span><span class="sxs-lookup"><span data-stu-id="5af04-163">There are numerous counters provided by Skype for Business.</span></span> <span data-ttu-id="5af04-164">通过登录到任何中介服务器并打开性能监视器，可以找到这些计数器。</span><span class="sxs-lookup"><span data-stu-id="5af04-164">You can find these counters by logging on to any Mediation Server and opening the Performance Monitor.</span></span> <span data-ttu-id="5af04-165">这些计数器以"LS："开始。</span><span class="sxs-lookup"><span data-stu-id="5af04-165">These counters start with "LS:".</span></span> <span data-ttu-id="5af04-166">Microsoft 建议你至少从以下容量计数器开始，并添加感兴趣的其他计数器：</span><span class="sxs-lookup"><span data-stu-id="5af04-166">Microsoft recommends that you start with the following capacity counters at a minimum, and add others that are of interest:</span></span>

     <span data-ttu-id="5af04-167">总活动呼叫：</span><span class="sxs-lookup"><span data-stu-id="5af04-167">Total active calls:</span></span>

       - <span data-ttu-id="5af04-168">LS：MediationServer - (_Total) \- 呼叫</span><span class="sxs-lookup"><span data-stu-id="5af04-168">LS:MediationServer - Inbound Calls(_Total)\- Current</span></span> 

       - <span data-ttu-id="5af04-169">LS：MediationServer - 当前 (_Total) \- 呼叫</span><span class="sxs-lookup"><span data-stu-id="5af04-169">LS:MediationServer - Outbound Calls(_Total)\- Current</span></span> 

     <span data-ttu-id="5af04-170">活动媒体旁路呼叫总数：</span><span class="sxs-lookup"><span data-stu-id="5af04-170">Total active media bypass calls:</span></span>

       - <span data-ttu-id="5af04-171">LS：MediationServer - (_Total) \- 媒体旁路呼叫的入站呼叫</span><span class="sxs-lookup"><span data-stu-id="5af04-171">LS:MediationServer - Inbound Calls(_Total)\- Active media bypass calls</span></span> 

       - <span data-ttu-id="5af04-172">LS：MediationServer - (_Total) \- 媒体旁路呼叫的出站呼叫</span><span class="sxs-lookup"><span data-stu-id="5af04-172">LS:MediationServer - Outbound Calls(_Total)\- Active media bypass calls</span></span> 

     > [!NOTE]
     > <span data-ttu-id="5af04-173">您必须手动在文本框中输入性能计数器。</span><span class="sxs-lookup"><span data-stu-id="5af04-173">You must manually enter the performance counters in the text box.</span></span> <span data-ttu-id="5af04-174">它们不会显示为下拉列表中的选项。</span><span class="sxs-lookup"><span data-stu-id="5af04-174">They do not appear as options in the drop-down list.</span></span> 

     <span data-ttu-id="5af04-175">有关详细信息，请参阅 Log Analytics 中的 [Windows 和 Linux 性能数据源](/azure/log-analytics/log-analytics-data-sources-performance-counters)</span><span class="sxs-lookup"><span data-stu-id="5af04-175">For more information, see [Windows and Linux performance data sources in Log Analytics](/azure/log-analytics/log-analytics-data-sources-performance-counters)</span></span>

### <a name="create-alerts"></a><span data-ttu-id="5af04-176">创建警报</span><span class="sxs-lookup"><span data-stu-id="5af04-176">Create alerts</span></span>

<span data-ttu-id="5af04-177">OMS 中有两种类型的警报：结果警报数和指标度量警报。</span><span class="sxs-lookup"><span data-stu-id="5af04-177">There are two types of alerts in OMS: Number of results alerts and Metric measurement alerts.</span></span> <span data-ttu-id="5af04-178">有关创建警报的信息，请参阅在 [Log Analytics 中处理警报规则](/azure/log-analytics/log-analytics-alerts-creating)。</span><span class="sxs-lookup"><span data-stu-id="5af04-178">For more information about creating alerts, see [Working with alert rules in Log Analytics](/azure/log-analytics/log-analytics-alerts-creating).</span></span>

<span data-ttu-id="5af04-179">在创建警报时，应考虑以下事项：</span><span class="sxs-lookup"><span data-stu-id="5af04-179">You should consider the following when creating alerts:</span></span>

- <span data-ttu-id="5af04-180">确保警报是结果数警报，这是默认选择。</span><span class="sxs-lookup"><span data-stu-id="5af04-180">Make sure the alert is a Number-of-results alert, which is the default selection.</span></span> 

- <span data-ttu-id="5af04-181">演示查询要求将"结果数"设置为"大于 0"。</span><span class="sxs-lookup"><span data-stu-id="5af04-181">The demo queries require that "Number of results" is set to "Greater than 0".</span></span> 

- <span data-ttu-id="5af04-182">建议将时间窗口和警报频率都设置为 5 分钟。</span><span class="sxs-lookup"><span data-stu-id="5af04-182">It is recommended that you set both Time window and Alert frequency to 5 minutes.</span></span> 

- <span data-ttu-id="5af04-183">建议不要对演示警报启用"抑制警报"。</span><span class="sxs-lookup"><span data-stu-id="5af04-183">It is recommended that you do not enable "Suppress alerts" for demo alerts.</span></span> 

- <span data-ttu-id="5af04-184">对于典型的警报方案，Microsoft 建议创建一对警报：一个错误警报和一个重置警报。</span><span class="sxs-lookup"><span data-stu-id="5af04-184">For typical alert scenarios, Microsoft recommends creating a pair of alerts: one error alert and one reset alert.</span></span> <span data-ttu-id="5af04-185">对于错误警报，选择严重性级别"严重";对于重置警报，选择严重性级别"信息"。</span><span class="sxs-lookup"><span data-stu-id="5af04-185">For the error alert, select severity level Critical; for the reset alert, select severity level Informational .</span></span>

<span data-ttu-id="5af04-186">以下各节介绍如何创建示例警报。</span><span class="sxs-lookup"><span data-stu-id="5af04-186">The following sections describe how to create sample alerts.</span></span>

 <span data-ttu-id="5af04-187">**创建警报对："RTCMEDSRV 未在中介服务器中运行"和"RTCMEDSRV 正在中介服务器中重新运行"**</span><span class="sxs-lookup"><span data-stu-id="5af04-187">**Create an alert pair: "RTCMEDSRV is NOT running in Mediation Servers" and "RTCMEDSRV is back in running in Mediation Servers"**</span></span>

<span data-ttu-id="5af04-188">若要创建此警报对：</span><span class="sxs-lookup"><span data-stu-id="5af04-188">To create this alert pair:</span></span>

- <span data-ttu-id="5af04-189">对错误警报的查询为：</span><span class="sxs-lookup"><span data-stu-id="5af04-189">The query for the error alert is:</span></span>

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)  | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    <span data-ttu-id="5af04-190">查询使用计算机筛选器，*其中 Computer 包含"MediationServer"。*</span><span class="sxs-lookup"><span data-stu-id="5af04-190">The query uses the computer filter  *where Computer contains "MediationServer"*  .</span></span> <span data-ttu-id="5af04-191">筛选器仅选择其名称包含字符串"MediationServer"的计算机。</span><span class="sxs-lookup"><span data-stu-id="5af04-191">The filter selects only the computer whose name contains the string "MediationServer".</span></span>

     <span data-ttu-id="5af04-192">可以使用自己的计算机筛选器替换筛选器，或者直接将其删除。</span><span class="sxs-lookup"><span data-stu-id="5af04-192">You would replace the filter with your own computer filter or simply remove it.</span></span> <span data-ttu-id="5af04-193">可以创建不带正则表达式的复杂字符串筛选器。</span><span class="sxs-lookup"><span data-stu-id="5af04-193">You can create complex string filters without regular expressions.</span></span> <span data-ttu-id="5af04-194">有关详细信息，请参阅字符串 [运算符](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators)。</span><span class="sxs-lookup"><span data-stu-id="5af04-194">For more information, see [String operators](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators).</span></span> <span data-ttu-id="5af04-195">您还可以选择使用正则表达式。</span><span class="sxs-lookup"><span data-stu-id="5af04-195">You can also choose to use regular expressions.</span></span> <span data-ttu-id="5af04-196">此外，您可以通过保存搜索查询，以及将该组用作警报查询中的计算机筛选器来创建计算机组。</span><span class="sxs-lookup"><span data-stu-id="5af04-196">Moreover, you can create a computer group by saving a search query and using that group as your computer filter in your alert query.</span></span> <span data-ttu-id="5af04-197">有关详细信息，请参阅 Log [Analytics 日志搜索中的计算机组](/azure/log-analytics/log-analytics-computer-groups)。</span><span class="sxs-lookup"><span data-stu-id="5af04-197">For more information, see [Computer groups in Log Analytics log searches](/azure/log-analytics/log-analytics-computer-groups).</span></span>

    <span data-ttu-id="5af04-198">对于每个计算机，错误查询将获取 RTCMEDSRV 服务启动和服务停止的最后一个事件日志。</span><span class="sxs-lookup"><span data-stu-id="5af04-198">For each computer, the error query will get the last event log for both the RTCMEDSRV service start and service stop.</span></span> <span data-ttu-id="5af04-199">如果最后一个事件是服务停止事件，它将返回一个日志;如果最后一个事件是服务启动事件，它将不返回任何值。</span><span class="sxs-lookup"><span data-stu-id="5af04-199">It will return one log if the last event is the service stop event; it will return nothing if the last event is the service start event.</span></span> <span data-ttu-id="5af04-200">简而言之，查询将返回其 RTCMEDSRV 在时间窗口中停止的服务器的列表。</span><span class="sxs-lookup"><span data-stu-id="5af04-200">In short, the query would return a list of servers whose RTCMEDSRV is stopped in the time window.</span></span> 

- <span data-ttu-id="5af04-201">重置警报的查询为：</span><span class="sxs-lookup"><span data-stu-id="5af04-201">The query for the reset alert is:</span></span>

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003) | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    <span data-ttu-id="5af04-202">重置查询与错误查询完全相反。</span><span class="sxs-lookup"><span data-stu-id="5af04-202">The reset query does exactly the opposite thing of the error query.</span></span> <span data-ttu-id="5af04-203">对于每个计算机，如果最后一个事件是服务启动事件，它将返回一个;如果最后一个事件是服务停止事件，它将不返回任何值。</span><span class="sxs-lookup"><span data-stu-id="5af04-203">For each computer, it will return one if the last event is the service start event; it will return nothing if the last event is the service stop event.</span></span>

<span data-ttu-id="5af04-204">**创建警报对："中介服务器中的并发呼叫过多"和"并发呼叫回退到正常负载"**</span><span class="sxs-lookup"><span data-stu-id="5af04-204">**Create an alert pair: " Too many concurrent calls in Mediation Servers" and "Concurrent calls fall back to normal load"**</span></span>

<span data-ttu-id="5af04-205">若要创建此警报：</span><span class="sxs-lookup"><span data-stu-id="5af04-205">To create this alert:</span></span>

- <span data-ttu-id="5af04-206">对错误警报的查询为：</span><span class="sxs-lookup"><span data-stu-id="5af04-206">The query for the error alert is:</span></span>

  ```Kusto
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName == "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    <span data-ttu-id="5af04-207">对于每个计算机，查询将获取入站呼叫和出站呼叫的最后一个计数器，并计算这两个值的总和。</span><span class="sxs-lookup"><span data-stu-id="5af04-207">For each computer, the query will get the last counters for inbound call and outbound call and sum those two values.</span></span> <span data-ttu-id="5af04-208">如果总和值超过 500，它将返回一个日志;如果未返回任何值，则不返回任何值。</span><span class="sxs-lookup"><span data-stu-id="5af04-208">It will return one log if the sum value exceeds 500; it will return nothing if it doesn't.</span></span> <span data-ttu-id="5af04-209">简而言之，查询将返回一个服务器列表，这些服务器的并发调用在时间窗口中太多。</span><span class="sxs-lookup"><span data-stu-id="5af04-209">In short, the query would return a list of servers whose concurrent calls are too many in the time window.</span></span>

- <span data-ttu-id="5af04-210">重置警报的查询为：</span><span class="sxs-lookup"><span data-stu-id="5af04-210">The query for the reset alert is:</span></span>

  ```Kusto
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==  "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500
  ```

    <span data-ttu-id="5af04-211">重置查询与错误查询完全相反。</span><span class="sxs-lookup"><span data-stu-id="5af04-211">The reset query does exactly the opposite thing of the error query.</span></span> <span data-ttu-id="5af04-212">对于每个计算机，查询将获取入站呼叫和出站呼叫的最后一个计数器，并计算这两个值的总和。</span><span class="sxs-lookup"><span data-stu-id="5af04-212">For each computer, the query will get the last counters for inbound call and outbound call and sum those two values.</span></span> <span data-ttu-id="5af04-213">如果总和值小于 500，它将返回一个日志;否则，它将不返回任何值。</span><span class="sxs-lookup"><span data-stu-id="5af04-213">It will return one log if the sum value is less than 500; it will return nothing otherwise.</span></span>

<span data-ttu-id="5af04-214">**创建警报："CPU 使用率 \> 90 或 RTCMEDIARELAY 在服务器中已停止"警报**</span><span class="sxs-lookup"><span data-stu-id="5af04-214">**Create an alert: "CPU usage \> 90 or RTCMEDIARELAY stopped in Servers" alert**</span></span>

<span data-ttu-id="5af04-215">若要创建此警报，查询为：</span><span class="sxs-lookup"><span data-stu-id="5af04-215">To create this alert, the query is:</span></span>

```Kusto
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==  "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

<span data-ttu-id="5af04-216">查询将获取所有计算机的所有处理器使用率计数器和服务停止事件，如果任一处理器使用率超过 90% 或者服务停止，则返回一个日志。</span><span class="sxs-lookup"><span data-stu-id="5af04-216">The query will get all processor usage counter and service stop event from all computers and return one log if either processor usage exceeds 90% or service is ever stopped.</span></span> 

## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a><span data-ttu-id="5af04-217">分析 Log Analytics 存储库中的警报</span><span class="sxs-lookup"><span data-stu-id="5af04-217">Analyze the alerts in your Log Analytics repository</span></span>

<span data-ttu-id="5af04-218">若要分析存储库中的警报，请使用警报管理解决方案。</span><span class="sxs-lookup"><span data-stu-id="5af04-218">To analyze the alerts in your repository, use the Alert Management solution.</span></span> <span data-ttu-id="5af04-219">有关详细信息，请参阅 [Operations Management Suite (OMS) ](/azure/log-analytics/log-analytics-solution-alert-management)</span><span class="sxs-lookup"><span data-stu-id="5af04-219">For more information, see [Alert Management solution in Operations Management Suite (OMS)](/azure/log-analytics/log-analytics-solution-alert-management)</span></span>

## <a name="recommended-minimal-monitoring-set"></a><span data-ttu-id="5af04-220">建议最小监视集</span><span class="sxs-lookup"><span data-stu-id="5af04-220">Recommended minimal monitoring set</span></span>

<span data-ttu-id="5af04-221">标识事件日志和性能计数器的问题：</span><span class="sxs-lookup"><span data-stu-id="5af04-221">To identify issues with event logs and performance counters:</span></span> 

- <span data-ttu-id="5af04-222">**事件日志。**</span><span class="sxs-lookup"><span data-stu-id="5af04-222">**Event logs.**</span></span> <span data-ttu-id="5af04-223">对于任何问题，都应该有一个事件对，其中一组事件指示出错，而另一个表示一切良好。</span><span class="sxs-lookup"><span data-stu-id="5af04-223">For any issue, there should be an events pair, with one set of events to indicate something is wrong, while the other indicates that everything is well.</span></span> <span data-ttu-id="5af04-224">对于任何给定的时间段，记录的最后一个事件将指示该时间段是否有内容。</span><span class="sxs-lookup"><span data-stu-id="5af04-224">For any given time period, it is the last event recorded that will indicate whether something is amiss for that time period.</span></span>

- <span data-ttu-id="5af04-225">**性能计数器。**</span><span class="sxs-lookup"><span data-stu-id="5af04-225">**Performance Counters.**</span></span> <span data-ttu-id="5af04-226">应存在受监视计数器的阈值。</span><span class="sxs-lookup"><span data-stu-id="5af04-226">There should be a threshold for the monitored counters.</span></span>

<span data-ttu-id="5af04-227">下表列出了 Microsoft 建议通过列出停止和启动事件 ID 监视的服务：</span><span class="sxs-lookup"><span data-stu-id="5af04-227">The following table lists the services that Microsoft recommends monitoring by listing the stop and start event IDs:</span></span>

|<span data-ttu-id="5af04-228">服务名称</span><span class="sxs-lookup"><span data-stu-id="5af04-228">Service Name</span></span>  <br/> |<span data-ttu-id="5af04-229">目标服务器角色</span><span class="sxs-lookup"><span data-stu-id="5af04-229">Target Server Role</span></span>  <br/> |<span data-ttu-id="5af04-230">停止事件 ID</span><span class="sxs-lookup"><span data-stu-id="5af04-230">Stop Event ID</span></span>  <br/> |<span data-ttu-id="5af04-231">开始事件 ID</span><span class="sxs-lookup"><span data-stu-id="5af04-231">Start Event ID</span></span>  <br/> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5af04-232">RTCMEDSRV</span><span class="sxs-lookup"><span data-stu-id="5af04-232">RTCMEDSRV</span></span>  <br/> |<span data-ttu-id="5af04-233">中介服务器</span><span class="sxs-lookup"><span data-stu-id="5af04-233">Mediation Server</span></span>  <br/> |<span data-ttu-id="5af04-234">25003</span><span class="sxs-lookup"><span data-stu-id="5af04-234">25003</span></span>  <br/> |<span data-ttu-id="5af04-235">25002</span><span class="sxs-lookup"><span data-stu-id="5af04-235">25002</span></span>  <br/> |
|<span data-ttu-id="5af04-236">RTCSRV</span><span class="sxs-lookup"><span data-stu-id="5af04-236">RTCSRV</span></span>  <br/> |<span data-ttu-id="5af04-237">边缘服务器</span><span class="sxs-lookup"><span data-stu-id="5af04-237">Edge Server</span></span>  <br/> |<span data-ttu-id="5af04-238">12289</span><span class="sxs-lookup"><span data-stu-id="5af04-238">12289</span></span>  <br/> |<span data-ttu-id="5af04-239">12288</span><span class="sxs-lookup"><span data-stu-id="5af04-239">12288</span></span>  <br/> |
|<span data-ttu-id="5af04-240">RTCMRAUTH</span><span class="sxs-lookup"><span data-stu-id="5af04-240">RTCMRAUTH</span></span>  <br/> |<span data-ttu-id="5af04-241">边缘服务器</span><span class="sxs-lookup"><span data-stu-id="5af04-241">Edge Server</span></span>  <br/> |<span data-ttu-id="5af04-242">19003</span><span class="sxs-lookup"><span data-stu-id="5af04-242">19003</span></span>  <br/> |<span data-ttu-id="5af04-243">19002</span><span class="sxs-lookup"><span data-stu-id="5af04-243">19002</span></span>  <br/> |
|<span data-ttu-id="5af04-244">RTCMEDIARELAY</span><span class="sxs-lookup"><span data-stu-id="5af04-244">RTCMEDIARELAY</span></span>  <br/> |<span data-ttu-id="5af04-245">边缘服务器</span><span class="sxs-lookup"><span data-stu-id="5af04-245">Edge Server</span></span>  <br/> |<span data-ttu-id="5af04-246">22003</span><span class="sxs-lookup"><span data-stu-id="5af04-246">22003</span></span>  <br/> |<span data-ttu-id="5af04-247">22002</span><span class="sxs-lookup"><span data-stu-id="5af04-247">22002</span></span>  <br/> |

<span data-ttu-id="5af04-248">下表列出了 Microsoft 建议监视的网络问题：</span><span class="sxs-lookup"><span data-stu-id="5af04-248">The following table lists the network issues that Microsoft recommends monitoring:</span></span>


| <span data-ttu-id="5af04-249">监视器名称</span><span class="sxs-lookup"><span data-stu-id="5af04-249">Monitor Name</span></span>  <br/>                                        | <span data-ttu-id="5af04-250">目标服务器角色</span><span class="sxs-lookup"><span data-stu-id="5af04-250">Target Server Role</span></span>  <br/> | <span data-ttu-id="5af04-251">成功事件 ID 表达式</span><span class="sxs-lookup"><span data-stu-id="5af04-251">Success Event ID expression</span></span>  <br/> | <span data-ttu-id="5af04-252">错误事件 ID 表达式</span><span class="sxs-lookup"><span data-stu-id="5af04-252">Error Event ID expression</span></span>  <br/> | <span data-ttu-id="5af04-253">失败示例</span><span class="sxs-lookup"><span data-stu-id="5af04-253">Failure example</span></span>  <br/> |
|:-----------------------------------------------------------|:--------------------------|:-----------------------------------|:---------------------------------|:-----------------------|
| <span data-ttu-id="5af04-254">中介服务器到网关的连接失败</span><span class="sxs-lookup"><span data-stu-id="5af04-254">Mediation Server to gateway connectivity failure</span></span>  <br/>    | <span data-ttu-id="5af04-255">中介服务器</span><span class="sxs-lookup"><span data-stu-id="5af04-255">Mediation Server</span></span>  <br/>   | <span data-ttu-id="5af04-256">25062</span><span class="sxs-lookup"><span data-stu-id="5af04-256">25062</span></span>                              |                                  | <span data-ttu-id="5af04-257">25002</span><span class="sxs-lookup"><span data-stu-id="5af04-257">25002</span></span>  <br/>           |
| <span data-ttu-id="5af04-258">中介服务器到网关的呼叫完成失败</span><span class="sxs-lookup"><span data-stu-id="5af04-258">Mediation Server to gateway call completion failure</span></span>  <br/> | <span data-ttu-id="5af04-259">中介服务器</span><span class="sxs-lookup"><span data-stu-id="5af04-259">Mediation Server</span></span>  <br/>   | <span data-ttu-id="5af04-260">25064</span><span class="sxs-lookup"><span data-stu-id="5af04-260">25064</span></span>                              |                                  | <span data-ttu-id="5af04-261">25002</span><span class="sxs-lookup"><span data-stu-id="5af04-261">25002</span></span>  <br/>           |
| <span data-ttu-id="5af04-262">关键网络问题</span><span class="sxs-lookup"><span data-stu-id="5af04-262">Critical network problems</span></span>  <br/>                           | <span data-ttu-id="5af04-263">边缘服务器</span><span class="sxs-lookup"><span data-stu-id="5af04-263">Edge Server</span></span>  <br/>        | <span data-ttu-id="5af04-264">14353</span><span class="sxs-lookup"><span data-stu-id="5af04-264">14353</span></span>                              |                                  | <span data-ttu-id="5af04-265">12288</span><span class="sxs-lookup"><span data-stu-id="5af04-265">12288</span></span>  <br/>           |

<span data-ttu-id="5af04-266">下面列出了应监视的呼叫容量计数器。</span><span class="sxs-lookup"><span data-stu-id="5af04-266">The following lists the call capacity counters that should be monitored.</span></span> <span data-ttu-id="5af04-267">对于云连接器标准版，这些数字应小于 500;云连接器最低版本低于 50。</span><span class="sxs-lookup"><span data-stu-id="5af04-267">These numbers should be less that 500 for Cloud Connector standard edition; less than 50 for Cloud Connector minimum edition.</span></span>

- <span data-ttu-id="5af04-268">LS：MediationServer - (_Total) \- 呼叫</span><span class="sxs-lookup"><span data-stu-id="5af04-268">LS:MediationServer - Inbound Calls(_Total)\- Current</span></span> 

- <span data-ttu-id="5af04-269">LS：MediationServer - 当前 (_Total) \- 呼叫</span><span class="sxs-lookup"><span data-stu-id="5af04-269">LS:MediationServer - Outbound Calls(_Total)\- Current</span></span> 

- <span data-ttu-id="5af04-270">LS：MediationServer - (_Total) \- 媒体旁路呼叫的入站呼叫</span><span class="sxs-lookup"><span data-stu-id="5af04-270">LS:MediationServer - Inbound Calls(_Total)\- Active media bypass calls</span></span>

- <span data-ttu-id="5af04-271">LS：MediationServer - (_Total) \- 媒体旁路呼叫的出站呼叫</span><span class="sxs-lookup"><span data-stu-id="5af04-271">LS:MediationServer - Outbound Calls(_Total)\- Active media bypass calls</span></span>

## <a name="see-also"></a><span data-ttu-id="5af04-272">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5af04-272">See also</span></span>

<span data-ttu-id="5af04-273">有关使用 OMS 的信息，请参阅以下内容：</span><span class="sxs-lookup"><span data-stu-id="5af04-273">For more information about working with OMS, see the following:</span></span>

- [<span data-ttu-id="5af04-274">使用日志搜索在 Log Analytics 中查找数据</span><span class="sxs-lookup"><span data-stu-id="5af04-274">Find data using log searches in Log Analytics</span></span>](/azure/log-analytics/log-analytics-log-searches)

- [<span data-ttu-id="5af04-275">Azure Log Analytics 语言参考</span><span class="sxs-lookup"><span data-stu-id="5af04-275">Azure Log Analytics Language Reference</span></span>](https://docs.loganalytics.io/docs/Language-Reference)

- [<span data-ttu-id="5af04-276">了解 Log Analytics 中的警报</span><span class="sxs-lookup"><span data-stu-id="5af04-276">Understanding alerts in Log Analytics</span></span>](/azure/log-analytics/log-analytics-alerts)

- [<span data-ttu-id="5af04-277">将 Windows 计算机连接到 Azure 中的 Log Analytics 服务</span><span class="sxs-lookup"><span data-stu-id="5af04-277">Connect Windows computers to the Log Analytics service in Azure</span></span>](/azure/log-analytics/log-analytics-windows-agents)