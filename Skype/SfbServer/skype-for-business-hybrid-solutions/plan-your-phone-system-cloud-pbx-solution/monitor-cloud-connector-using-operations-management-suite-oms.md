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
description: 阅读本主题，了解如何使用 Microsoft Operations Management Suite (OMS) 监视你的云连接器版本2.1 及更高版本的部署。
ms.openlocfilehash: eca2f56bf564e376717a42bd8d297710905f8dc6
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359088"
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a><span data-ttu-id="df16c-103">使用 Operations Management Suite (OMS) 监视云连接器</span><span class="sxs-lookup"><span data-stu-id="df16c-103">Monitor Cloud Connector using Operations Management Suite (OMS)</span></span>

> [!Important]
> <span data-ttu-id="df16c-104">云连接器版本将在2021年7月31日和 Skype for Business Online 之间终止。</span><span class="sxs-lookup"><span data-stu-id="df16c-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="df16c-105">组织升级到团队后，了解如何使用 [直接路由](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)将本地电话网络连接到团队。</span><span class="sxs-lookup"><span data-stu-id="df16c-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="df16c-106">阅读本主题，了解如何使用 Microsoft Operations Management Suite (OMS) 监视你的云连接器版本2.1 及更高版本的部署。</span><span class="sxs-lookup"><span data-stu-id="df16c-106">Read this topic to learn how to monitor your Cloud Connector version 2.1 and later deployment by using Microsoft Operations Management Suite (OMS).</span></span>

<span data-ttu-id="df16c-107">现在，您可以使用 Operations Management Suite (OMS) Microsoft 云 IT 管理解决方案来监视云连接器版本2.1 及更高版本的部署。</span><span class="sxs-lookup"><span data-stu-id="df16c-107">You can now monitor your Cloud Connector version 2.1 and later deployment by using Operations Management Suite (OMS), a Microsoft cloud IT management solution.</span></span> <span data-ttu-id="df16c-108">OMS 日志分析使您能够监视和分析资源（包括物理和虚拟机）的可用性和性能。</span><span class="sxs-lookup"><span data-stu-id="df16c-108">OMS Log Analytics enables you to monitor and analyze the availability and performance of resources including physical and virtual machines.</span></span> <span data-ttu-id="df16c-109">有关 OMS 和 Log Analytics 的详细信息，请参阅 [什么是 Operations Management Suite (OMS) ？](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview)</span><span class="sxs-lookup"><span data-stu-id="df16c-109">For more information about OMS and Log Analytics, see [What is Operations Management Suite (OMS)?](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview)</span></span>

<span data-ttu-id="df16c-110">本主题包含以下各部分：</span><span class="sxs-lookup"><span data-stu-id="df16c-110">This topic contains the following sections:</span></span>

- <span data-ttu-id="df16c-111">先决条件</span><span class="sxs-lookup"><span data-stu-id="df16c-111">Prerequisites</span></span>

- <span data-ttu-id="df16c-112">将云连接器配置为使用 OMS</span><span class="sxs-lookup"><span data-stu-id="df16c-112">Configure Cloud Connector to use OMS</span></span>

- <span data-ttu-id="df16c-113">配置 OMS</span><span class="sxs-lookup"><span data-stu-id="df16c-113">Configure OMS</span></span>

- <span data-ttu-id="df16c-114">分析 Log Analytics 存储库中的警报</span><span class="sxs-lookup"><span data-stu-id="df16c-114">Analyze the alerts in your Log Analytics repository</span></span>

- <span data-ttu-id="df16c-115">推荐的监视集</span><span class="sxs-lookup"><span data-stu-id="df16c-115">Recommended monitoring set</span></span>

## <a name="prerequisites"></a><span data-ttu-id="df16c-116">先决条件</span><span class="sxs-lookup"><span data-stu-id="df16c-116">Prerequisites</span></span>

<span data-ttu-id="df16c-117">在可以使用 OMS 监视云连接器部署之前，您需要以下各项：</span><span class="sxs-lookup"><span data-stu-id="df16c-117">Before you can use OMS to monitor your Cloud Connector deployment, you will need the following:</span></span>

- <span data-ttu-id="df16c-118">**Azure 帐户和 OMS 工作区。**</span><span class="sxs-lookup"><span data-stu-id="df16c-118">**An Azure account and an OMS workspace.**</span></span> <span data-ttu-id="df16c-119">如果你还没有 Azure 帐户，你将需要创建一个，才能使用 OMS 日志分析。</span><span class="sxs-lookup"><span data-stu-id="df16c-119">If you don't already have an Azure account, you will need to create one to use OMS Log Analytics.</span></span> <span data-ttu-id="df16c-120">有关如何创建 Azure 帐户和设置 OMS 工作区的信息，请参阅 [Log Analytics workspace 入门](https://docs.microsoft.com/azure/log-analytics/log-analytics-get-started)。</span><span class="sxs-lookup"><span data-stu-id="df16c-120">For information about how to create an Azure account and set up an OMS workspace, see [Get started with a Log Analytics workspace](https://docs.microsoft.com/azure/log-analytics/log-analytics-get-started).</span></span>

- <span data-ttu-id="df16c-121">**云连接器版本2.1 或更高版本**</span><span class="sxs-lookup"><span data-stu-id="df16c-121">**Cloud Connector version 2.1 or later**</span></span>

- <span data-ttu-id="df16c-122">需要进行日志分析：云连接器监控需要**新的日志搜索**。</span><span class="sxs-lookup"><span data-stu-id="df16c-122">**Log Analytics new log search** is required for Cloud Connector monitoring.</span></span> <span data-ttu-id="df16c-123">有关详细信息，请参阅 [将 Azure Log Analytics 工作区升级到新的日志搜索](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-search-upgrade)。</span><span class="sxs-lookup"><span data-stu-id="df16c-123">For more information, see [Upgrade your Azure Log Analytics workspace to new log search](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-search-upgrade).</span></span>

## <a name="configure-cloud-connector-to-use-oms"></a><span data-ttu-id="df16c-124">将云连接器配置为使用 OMS</span><span class="sxs-lookup"><span data-stu-id="df16c-124">Configure Cloud Connector to use OMS</span></span>

<span data-ttu-id="df16c-125">你需要将云连接器本地环境配置为使用 OMS。</span><span class="sxs-lookup"><span data-stu-id="df16c-125">You'll need to configure your Cloud Connector on-premises environment to use OMS.</span></span> <span data-ttu-id="df16c-126">若要执行此操作，您将需要您的 OMS 工作区 ID 和密钥，可通过以下方式使用 OMS 门户来查找：设置-- \> 连接的源-- \> Windows server：</span><span class="sxs-lookup"><span data-stu-id="df16c-126">To do this, you will need your OMS workspace ID and key, which you can find by using the OMS portal as follows: Settings --\>Connected Sources --\> Windows Servers:</span></span>

![云连接器 OMS 的屏幕截图](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)

<span data-ttu-id="df16c-128">如何配置云连接器以使用 OMS 取决于您的方案：</span><span class="sxs-lookup"><span data-stu-id="df16c-128">How you configure Cloud Connector to use OMS depends on your scenario:</span></span>

- <span data-ttu-id="df16c-129">**如果要安装新的云连接器设备或想要重新部署设备**，请在运行 register-ccappliance 之前执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="df16c-129">**If you are installing a new Cloud Connector appliance or you want to re-deploy an appliance**, follow these steps before you run Install-CcAppliance:</span></span>

    1. <span data-ttu-id="df16c-130">在 "CloudConnector.ini 文件 [Common]" 部分，将 OMSEnabled 参数设置为 True。</span><span class="sxs-lookup"><span data-stu-id="df16c-130">In the CloudConnector.ini file [Common] section, set the OMSEnabled parameter to True.</span></span>

        <span data-ttu-id="df16c-131">每次部署或升级云连接器时，都会尝试将 OMS 代理自动安装到 Vm 上。</span><span class="sxs-lookup"><span data-stu-id="df16c-131">Each time Cloud Connector is deployed or upgraded, it will try to install the OMS agent automatically onto the VMs.</span></span> <span data-ttu-id="df16c-132">启用此功能，以便 OMS 代理可经受云连接器自动更新。</span><span class="sxs-lookup"><span data-stu-id="df16c-132">Enable this feature so the OMS agent can survive the Cloud Connector automatic update.</span></span>

    2. <span data-ttu-id="df16c-133">若要配置 OMS ID 和密钥，请运行 Set-cccredential-AccountType OMSWorkspace。</span><span class="sxs-lookup"><span data-stu-id="df16c-133">To configure the OMS ID and key, run Set-CcCredential -AccountType OMSWorkspace.</span></span> 

- <span data-ttu-id="df16c-134">**如果要将 OMS 代理安装到现有云连接器设备上**，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="df16c-134">**If you are installing an OMS agent onto an existing Cloud Connector appliance**, follow these steps:</span></span>

    1. <span data-ttu-id="df16c-135">在 "CloudConnector.ini 文件 [Common]" 部分，设置 OMSEnabled = true。</span><span class="sxs-lookup"><span data-stu-id="df16c-135">In the CloudConnector.ini file [Common] section, set OMSEnabled=true.</span></span> 

    2. <span data-ttu-id="df16c-136">运行导入-Export-ccconfiguration。</span><span class="sxs-lookup"><span data-stu-id="df16c-136">Run Import-CcConfiguration.</span></span> 

    3. <span data-ttu-id="df16c-137">运行安装-CcOMSAgent。</span><span class="sxs-lookup"><span data-stu-id="df16c-137">Run Install-CcOMSAgent.</span></span> 

        > [!NOTE]
        > <span data-ttu-id="df16c-138">如果从未设置 OMSWorkspace 凭据，则当您运行 CcOMSAgent 时，系统会提示您提供凭据。</span><span class="sxs-lookup"><span data-stu-id="df16c-138">If the OMSWorkspace credential has never been set, you are prompted for the credential when you run install-CcOMSAgent.</span></span> 

- <span data-ttu-id="df16c-139">**如果要更新已安装 OMS 代理的云连接器设备中的 OMS 工作区 ID 或密钥，请执行以下操作：**</span><span class="sxs-lookup"><span data-stu-id="df16c-139">**If you want to update the OMS workspace ID or key in a Cloud Connector appliance that has already installed an OMS agent:**</span></span>

    1. <span data-ttu-id="df16c-140">若要配置 OMS ID 和密钥，请运行 Set-cccredential-AccountType OMSWorkspace。</span><span class="sxs-lookup"><span data-stu-id="df16c-140">To configure the OMS ID and key, run Set-CcCredential -AccountType OMSWorkspace.</span></span> 

    2. <span data-ttu-id="df16c-141">若要应用更新，请运行安装-CcOMSAgent。</span><span class="sxs-lookup"><span data-stu-id="df16c-141">To apply the updates, run Install-CcOMSAgent.</span></span> 

- <span data-ttu-id="df16c-142">**对于所有方案，请验证代理是否已连接，如下所示：**</span><span class="sxs-lookup"><span data-stu-id="df16c-142">**For all scenarios, verify that the agents are connected as follows:**</span></span>

    <span data-ttu-id="df16c-143">在 OMS 门户中，转到 "设置- \> 连接的源- \> Windows 服务器"。</span><span class="sxs-lookup"><span data-stu-id="df16c-143">In the OMS portal, go to Settings -\> Connected Sources -\> Windows Servers.</span></span> <span data-ttu-id="df16c-144">你将看到已连接的计算机的列表。</span><span class="sxs-lookup"><span data-stu-id="df16c-144">You will see a list of connected machines.</span></span> 

## <a name="configure-oms"></a><span data-ttu-id="df16c-145">配置 OMS</span><span class="sxs-lookup"><span data-stu-id="df16c-145">Configure OMS</span></span>

<span data-ttu-id="df16c-146">接下来，你将需要使用 OMS 门户指定 OMS 配置。</span><span class="sxs-lookup"><span data-stu-id="df16c-146">Next, you will need to specify your OMS configuration by using the OMS portal.</span></span> <span data-ttu-id="df16c-147">具体来说，您将需要：</span><span class="sxs-lookup"><span data-stu-id="df16c-147">Specifically, you will need to:</span></span>

- <span data-ttu-id="df16c-148">指定有关事件日志和性能计数器的信息。</span><span class="sxs-lookup"><span data-stu-id="df16c-148">Specify information about event logs and performance counters.</span></span>

- <span data-ttu-id="df16c-149">创建通知。</span><span class="sxs-lookup"><span data-stu-id="df16c-149">Create alerts.</span></span> 

### <a name="specify-information-about-event-logs-and-performance-counters"></a><span data-ttu-id="df16c-150">指定有关事件日志和性能计数器的信息</span><span class="sxs-lookup"><span data-stu-id="df16c-150">Specify information about event logs and performance counters</span></span>

<span data-ttu-id="df16c-151">在 OMS 门户中，您必须指定有关事件日志和性能计数器的信息，如下所示：</span><span class="sxs-lookup"><span data-stu-id="df16c-151">In the OMS portal, you must specify information about the event logs and performance counters as follows:</span></span>

1. <span data-ttu-id="df16c-152">转到 "设置 \> "-"Data- \> Windows 事件日志"，并为以下项添加事件日志：</span><span class="sxs-lookup"><span data-stu-id="df16c-152">Go to Settings-\>Data-\>Windows Event logs, and add event logs for:</span></span> 

   - <span data-ttu-id="df16c-153">Lync Server</span><span class="sxs-lookup"><span data-stu-id="df16c-153">Lync Server</span></span>

   - <span data-ttu-id="df16c-154">Application</span><span class="sxs-lookup"><span data-stu-id="df16c-154">Application</span></span>

     > [!NOTE]
     > <span data-ttu-id="df16c-155">您必须在文本框中手动输入 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="df16c-155">You must manually enter Lync Server in the text box.</span></span> <span data-ttu-id="df16c-156">它不会作为选项显示在下拉列表中。</span><span class="sxs-lookup"><span data-stu-id="df16c-156">It does not appear as an option in the drop-down list.</span></span> 

     <span data-ttu-id="df16c-157">有关详细信息，请参阅 [Log Analytics 中的 Windows 事件日志数据源](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events)</span><span class="sxs-lookup"><span data-stu-id="df16c-157">For more information, see [Windows event log data sources in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events)</span></span>

2. <span data-ttu-id="df16c-158">转到 "设置 \> "-"Data- \> Windows 性能计数器"，并为以下项添加性能计数器：</span><span class="sxs-lookup"><span data-stu-id="df16c-158">Go to Settings-\>Data-\> Windows Performance Counters, and add performance counters for:</span></span> 

   - <span data-ttu-id="df16c-159">**OS 级别计数器**。</span><span class="sxs-lookup"><span data-stu-id="df16c-159">**OS level counters**.</span></span> <span data-ttu-id="df16c-160">您可以添加 OS 级别的计数器，如处理器使用情况、内存使用率、网络使用情况，或者您可以使用现有的解决方案（如容量和性能）、网络性能监视器而无需显式添加计数器。</span><span class="sxs-lookup"><span data-stu-id="df16c-160">You can add OS level counters, such as processor usage, memory usage, network usage, or you can use existing solutions such as Capacity and Performance, Network Performance Monitor without adding counters explicitly.</span></span> <span data-ttu-id="df16c-161">无论您决定如何监视它们，Microsoft 建议您监视这些 OS 计数器。</span><span class="sxs-lookup"><span data-stu-id="df16c-161">No matter how you decide to monitor them, Microsoft recommends that you monitor these OS counters.</span></span>

   - <span data-ttu-id="df16c-162">**Skype For business 计数器**。</span><span class="sxs-lookup"><span data-stu-id="df16c-162">**Skype for Business counters**.</span></span> <span data-ttu-id="df16c-163">Skype for Business 提供了许多计数器。</span><span class="sxs-lookup"><span data-stu-id="df16c-163">There are numerous counters provided by Skype for Business.</span></span> <span data-ttu-id="df16c-164">您可以通过登录到任何中介服务器并打开性能监视器来查找这些计数器。</span><span class="sxs-lookup"><span data-stu-id="df16c-164">You can find these counters by logging on to any Mediation Server and opening the Performance Monitor.</span></span> <span data-ttu-id="df16c-165">这些计数器以 "LS：" 开头。</span><span class="sxs-lookup"><span data-stu-id="df16c-165">These counters start with "LS:".</span></span> <span data-ttu-id="df16c-166">Microsoft 建议您至少从以下容量计数器开始，添加其他感兴趣的计数器：</span><span class="sxs-lookup"><span data-stu-id="df16c-166">Microsoft recommends that you start with the following capacity counters at a minimum, and add others that are of interest:</span></span>

     <span data-ttu-id="df16c-167">活动呼叫总数：</span><span class="sxs-lookup"><span data-stu-id="df16c-167">Total active calls:</span></span>

       - <span data-ttu-id="df16c-168">LS： MediationServer) Current (_Total 的入站呼叫 \-</span><span class="sxs-lookup"><span data-stu-id="df16c-168">LS:MediationServer - Inbound Calls(_Total)\- Current</span></span> 

       - <span data-ttu-id="df16c-169">LS： MediationServer- (_Total) Current 的出站呼叫 \-</span><span class="sxs-lookup"><span data-stu-id="df16c-169">LS:MediationServer - Outbound Calls(_Total)\- Current</span></span> 

     <span data-ttu-id="df16c-170">活动媒体旁路呼叫总数：</span><span class="sxs-lookup"><span data-stu-id="df16c-170">Total active media bypass calls:</span></span>

       - <span data-ttu-id="df16c-171">LS： MediationServer) \- Active media 旁路呼叫 (_Total 的入站呼叫</span><span class="sxs-lookup"><span data-stu-id="df16c-171">LS:MediationServer - Inbound Calls(_Total)\- Active media bypass calls</span></span> 

       - <span data-ttu-id="df16c-172">LS： MediationServer) \- Active media 旁路呼叫 (_Total 的出站呼叫</span><span class="sxs-lookup"><span data-stu-id="df16c-172">LS:MediationServer - Outbound Calls(_Total)\- Active media bypass calls</span></span> 

     > [!NOTE]
     > <span data-ttu-id="df16c-173">您必须在文本框中手动输入性能计数器。</span><span class="sxs-lookup"><span data-stu-id="df16c-173">You must manually enter the performance counters in the text box.</span></span> <span data-ttu-id="df16c-174">它们不会作为选项显示在下拉列表中。</span><span class="sxs-lookup"><span data-stu-id="df16c-174">They do not appear as options in the drop-down list.</span></span> 

     <span data-ttu-id="df16c-175">有关详细信息，请参阅 [Log Analytics 中的 Windows 和 Linux 性能数据源](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-performance-counters)</span><span class="sxs-lookup"><span data-stu-id="df16c-175">For more information, see [Windows and Linux performance data sources in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-performance-counters)</span></span>

### <a name="create-alerts"></a><span data-ttu-id="df16c-176">创建通知</span><span class="sxs-lookup"><span data-stu-id="df16c-176">Create alerts</span></span>

<span data-ttu-id="df16c-177">OMS 中有两种类型的警报：结果警报和指标测量警报的数量。</span><span class="sxs-lookup"><span data-stu-id="df16c-177">There are two types of alerts in OMS: Number of results alerts and Metric measurement alerts.</span></span> <span data-ttu-id="df16c-178">有关创建通知的详细信息，请参阅 [在日志分析中使用警报规则](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts-creating)。</span><span class="sxs-lookup"><span data-stu-id="df16c-178">For more information about creating alerts, see [Working with alert rules in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts-creating).</span></span>

<span data-ttu-id="df16c-179">创建警报时，应考虑以下事项：</span><span class="sxs-lookup"><span data-stu-id="df16c-179">You should consider the following when creating alerts:</span></span>

- <span data-ttu-id="df16c-180">确保通知为 "结果数" 警报，这是默认选择。</span><span class="sxs-lookup"><span data-stu-id="df16c-180">Make sure the alert is a Number-of-results alert, which is the default selection.</span></span> 

- <span data-ttu-id="df16c-181">演示查询要求 "结果数" 设置为 "大于 0"。</span><span class="sxs-lookup"><span data-stu-id="df16c-181">The demo queries require that "Number of results" is set to "Greater than 0".</span></span> 

- <span data-ttu-id="df16c-182">建议将 "时间" 窗口和 "警报频率" 设置为5分钟。</span><span class="sxs-lookup"><span data-stu-id="df16c-182">It is recommended that you set both Time window and Alert frequency to 5 minutes.</span></span> 

- <span data-ttu-id="df16c-183">建议您不要为演示通知启用 "抑制通知"。</span><span class="sxs-lookup"><span data-stu-id="df16c-183">It is recommended that you do not enable "Suppress alerts" for demo alerts.</span></span> 

- <span data-ttu-id="df16c-184">对于典型的通知方案，Microsoft 建议创建一对警报：一个错误警报和一个重置警报。</span><span class="sxs-lookup"><span data-stu-id="df16c-184">For typical alert scenarios, Microsoft recommends creating a pair of alerts: one error alert and one reset alert.</span></span> <span data-ttu-id="df16c-185">对于错误警报，请选择严重级别严重级别;对于 "重置警报"，选择 "严重级别信息"。</span><span class="sxs-lookup"><span data-stu-id="df16c-185">For the error alert, select severity level Critical; for the reset alert, select severity level Informational .</span></span>

<span data-ttu-id="df16c-186">以下各节介绍如何创建示例警报。</span><span class="sxs-lookup"><span data-stu-id="df16c-186">The following sections describe how to create sample alerts.</span></span>

 <span data-ttu-id="df16c-187">**创建警报对： "RTCMEDSRV 未在中介服务器中运行" 和 "RTCMEDSRV 已重新在中介服务器中运行"**</span><span class="sxs-lookup"><span data-stu-id="df16c-187">**Create an alert pair: "RTCMEDSRV is NOT running in Mediation Servers" and "RTCMEDSRV is back in running in Mediation Servers"**</span></span>

<span data-ttu-id="df16c-188">若要创建此通知对：</span><span class="sxs-lookup"><span data-stu-id="df16c-188">To create this alert pair:</span></span>

- <span data-ttu-id="df16c-189">针对错误警报的查询是：</span><span class="sxs-lookup"><span data-stu-id="df16c-189">The query for the error alert is:</span></span>

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)  | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    <span data-ttu-id="df16c-190">查询使用计算机  *包含 "MediationServer"*  的计算机筛选器。</span><span class="sxs-lookup"><span data-stu-id="df16c-190">The query uses the computer filter  *where Computer contains "MediationServer"*  .</span></span> <span data-ttu-id="df16c-191">筛选器仅选择其名称中包含字符串 "MediationServer" 的计算机。</span><span class="sxs-lookup"><span data-stu-id="df16c-191">The filter selects only the computer whose name contains the string "MediationServer".</span></span>

     <span data-ttu-id="df16c-192">您需要将筛选器替换为自己的计算机筛选器，或者只是将其删除。</span><span class="sxs-lookup"><span data-stu-id="df16c-192">You would replace the filter with your own computer filter or simply remove it.</span></span> <span data-ttu-id="df16c-193">您可以创建不带正则表达式的复杂字符串筛选器。</span><span class="sxs-lookup"><span data-stu-id="df16c-193">You can create complex string filters without regular expressions.</span></span> <span data-ttu-id="df16c-194">有关详细信息，请参阅 [String operators](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators)。</span><span class="sxs-lookup"><span data-stu-id="df16c-194">For more information, see [String operators](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators).</span></span> <span data-ttu-id="df16c-195">您还可以选择使用正则表达式。</span><span class="sxs-lookup"><span data-stu-id="df16c-195">You can also choose to use regular expressions.</span></span> <span data-ttu-id="df16c-196">此外，您还可以通过保存搜索查询并将该组用作警报查询中的计算机筛选器来创建计算机组。</span><span class="sxs-lookup"><span data-stu-id="df16c-196">Moreover, you can create a computer group by saving a search query and using that group as your computer filter in your alert query.</span></span> <span data-ttu-id="df16c-197">有关详细信息，请参阅 [Log Analytics log 搜索中的计算机组](https://docs.microsoft.com/azure/log-analytics/log-analytics-computer-groups)。</span><span class="sxs-lookup"><span data-stu-id="df16c-197">For more information, see [Computer groups in Log Analytics log searches](https://docs.microsoft.com/azure/log-analytics/log-analytics-computer-groups).</span></span>

    <span data-ttu-id="df16c-198">对于每台计算机，错误查询将获取 RTCMEDSRV 服务启动和服务停止的最后一个事件日志。</span><span class="sxs-lookup"><span data-stu-id="df16c-198">For each computer, the error query will get the last event log for both the RTCMEDSRV service start and service stop.</span></span> <span data-ttu-id="df16c-199">如果最后一个事件是服务停止事件，它将返回一个日志; 否则，将返回一个日志。如果最后一个事件是服务启动事件，它将返回 nothing。</span><span class="sxs-lookup"><span data-stu-id="df16c-199">It will return one log if the last event is the service stop event; it will return nothing if the last event is the service start event.</span></span> <span data-ttu-id="df16c-200">简言之，该查询将返回在时间窗口中停止的 RTCMEDSRV 的服务器的列表。</span><span class="sxs-lookup"><span data-stu-id="df16c-200">In short, the query would return a list of servers whose RTCMEDSRV is stopped in the time window.</span></span> 

- <span data-ttu-id="df16c-201">对重置警报的查询为：</span><span class="sxs-lookup"><span data-stu-id="df16c-201">The query for the reset alert is:</span></span>

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003) | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    <span data-ttu-id="df16c-202">重置查询与错误查询完全相反。</span><span class="sxs-lookup"><span data-stu-id="df16c-202">The reset query does exactly the opposite thing of the error query.</span></span> <span data-ttu-id="df16c-203">对于每台计算机，如果最后一个事件是服务启动事件，它将返回一个，否则将返回一个。如果最后一个事件是服务停止事件，它将返回 nothing。</span><span class="sxs-lookup"><span data-stu-id="df16c-203">For each computer, it will return one if the last event is the service start event; it will return nothing if the last event is the service stop event.</span></span>

<span data-ttu-id="df16c-204">**创建警报对： "中介服务器中的并发呼叫过多" 和 "并发呼叫回退到正常负载"**</span><span class="sxs-lookup"><span data-stu-id="df16c-204">**Create an alert pair: " Too many concurrent calls in Mediation Servers" and "Concurrent calls fall back to normal load"**</span></span>

<span data-ttu-id="df16c-205">若要创建此警报：</span><span class="sxs-lookup"><span data-stu-id="df16c-205">To create this alert:</span></span>

- <span data-ttu-id="df16c-206">针对错误警报的查询是：</span><span class="sxs-lookup"><span data-stu-id="df16c-206">The query for the error alert is:</span></span>

  ```Kusto
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName == "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    <span data-ttu-id="df16c-207">对于每台计算机，查询将获取入站呼叫和出站呼叫的最后一个计数器，并对这两个值求和。</span><span class="sxs-lookup"><span data-stu-id="df16c-207">For each computer, the query will get the last counters for inbound call and outbound call and sum those two values.</span></span> <span data-ttu-id="df16c-208">如果总和值超过500，它将返回一个日志; 否则，将返回一个日志。如果不是，它将返回 nothing。</span><span class="sxs-lookup"><span data-stu-id="df16c-208">It will return one log if the sum value exceeds 500; it will return nothing if it doesn't.</span></span> <span data-ttu-id="df16c-209">简言之，该查询将返回时间窗口中其并发呼叫过多的服务器的列表。</span><span class="sxs-lookup"><span data-stu-id="df16c-209">In short, the query would return a list of servers whose concurrent calls are too many in the time window.</span></span>

- <span data-ttu-id="df16c-210">对重置警报的查询为：</span><span class="sxs-lookup"><span data-stu-id="df16c-210">The query for the reset alert is:</span></span>

  ```Kusto
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==  "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500
  ```

    <span data-ttu-id="df16c-211">重置查询与错误查询完全相反。</span><span class="sxs-lookup"><span data-stu-id="df16c-211">The reset query does exactly the opposite thing of the error query.</span></span> <span data-ttu-id="df16c-212">对于每台计算机，查询将获取入站呼叫和出站呼叫的最后一个计数器，并对这两个值求和。</span><span class="sxs-lookup"><span data-stu-id="df16c-212">For each computer, the query will get the last counters for inbound call and outbound call and sum those two values.</span></span> <span data-ttu-id="df16c-213">如果 sum 值小于500，它将返回一个日志; 否则，将返回一个日志。否则，它将返回 nothing。</span><span class="sxs-lookup"><span data-stu-id="df16c-213">It will return one log if the sum value is less than 500; it will return nothing otherwise.</span></span>

<span data-ttu-id="df16c-214">**创建警报： "服务器上的 CPU 使用率 \> 90 或 RTCMEDIARELAY 已停止" 警报**</span><span class="sxs-lookup"><span data-stu-id="df16c-214">**Create an alert: "CPU usage \> 90 or RTCMEDIARELAY stopped in Servers" alert**</span></span>

<span data-ttu-id="df16c-215">若要创建此警报，查询为：</span><span class="sxs-lookup"><span data-stu-id="df16c-215">To create this alert, the query is:</span></span>

```Kusto
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==  "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

<span data-ttu-id="df16c-216">如果处理器使用率超过90% 或服务被停止，则查询将从所有计算机获取所有处理器使用率计数器和服务停止事件，并返回一个日志。</span><span class="sxs-lookup"><span data-stu-id="df16c-216">The query will get all processor usage counter and service stop event from all computers and return one log if either processor usage exceeds 90% or service is ever stopped.</span></span> 

## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a><span data-ttu-id="df16c-217">分析 Log Analytics 存储库中的警报</span><span class="sxs-lookup"><span data-stu-id="df16c-217">Analyze the alerts in your Log Analytics repository</span></span>

<span data-ttu-id="df16c-218">若要分析存储库中的警报，请使用警报管理解决方案。</span><span class="sxs-lookup"><span data-stu-id="df16c-218">To analyze the alerts in your repository, use the Alert Management solution.</span></span> <span data-ttu-id="df16c-219">有关详细信息，请参阅 [Operations Management Suite 中的警报管理解决方案 (OMS) ](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management)</span><span class="sxs-lookup"><span data-stu-id="df16c-219">For more information, see [Alert Management solution in Operations Management Suite (OMS)](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management)</span></span>

## <a name="recommended-minimal-monitoring-set"></a><span data-ttu-id="df16c-220">建议的最小监控集</span><span class="sxs-lookup"><span data-stu-id="df16c-220">Recommended minimal monitoring set</span></span>

<span data-ttu-id="df16c-221">若要确定事件日志和性能计数器的问题，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="df16c-221">To identify issues with event logs and performance counters:</span></span> 

- <span data-ttu-id="df16c-222">**事件日志。**</span><span class="sxs-lookup"><span data-stu-id="df16c-222">**Event logs.**</span></span> <span data-ttu-id="df16c-223">对于任何问题，应有一个事件对，其中有一组事件指示存在错误，另一个事件指示一切正常。</span><span class="sxs-lookup"><span data-stu-id="df16c-223">For any issue, there should be an events pair, with one set of events to indicate something is wrong, while the other indicates that everything is well.</span></span> <span data-ttu-id="df16c-224">对于任何给定的时间段，它是最后记录的事件，用于指示是否某个时间段的 amiss。</span><span class="sxs-lookup"><span data-stu-id="df16c-224">For any given time period, it is the last event recorded that will indicate whether something is amiss for that time period.</span></span>

- <span data-ttu-id="df16c-225">**性能计数器。**</span><span class="sxs-lookup"><span data-stu-id="df16c-225">**Performance Counters.**</span></span> <span data-ttu-id="df16c-226">监视的计数器应有一个阈值。</span><span class="sxs-lookup"><span data-stu-id="df16c-226">There should be a threshold for the monitored counters.</span></span>

<span data-ttu-id="df16c-227">下表列出了 Microsoft 建议的用于通过列出停止和启动事件 Id 进行监视的服务：</span><span class="sxs-lookup"><span data-stu-id="df16c-227">The following table lists the services that Microsoft recommends monitoring by listing the stop and start event IDs:</span></span>

|<span data-ttu-id="df16c-228">服务名称</span><span class="sxs-lookup"><span data-stu-id="df16c-228">Service Name</span></span>  <br/> |<span data-ttu-id="df16c-229">目标服务器角色</span><span class="sxs-lookup"><span data-stu-id="df16c-229">Target Server Role</span></span>  <br/> |<span data-ttu-id="df16c-230">停止事件 ID</span><span class="sxs-lookup"><span data-stu-id="df16c-230">Stop Event ID</span></span>  <br/> |<span data-ttu-id="df16c-231">启动事件 ID</span><span class="sxs-lookup"><span data-stu-id="df16c-231">Start Event ID</span></span>  <br/> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="df16c-232">RTCMEDSRV</span><span class="sxs-lookup"><span data-stu-id="df16c-232">RTCMEDSRV</span></span>  <br/> |<span data-ttu-id="df16c-233">中介服务器</span><span class="sxs-lookup"><span data-stu-id="df16c-233">Mediation Server</span></span>  <br/> |<span data-ttu-id="df16c-234">25003</span><span class="sxs-lookup"><span data-stu-id="df16c-234">25003</span></span>  <br/> |<span data-ttu-id="df16c-235">25002</span><span class="sxs-lookup"><span data-stu-id="df16c-235">25002</span></span>  <br/> |
|<span data-ttu-id="df16c-236">RTCSRV</span><span class="sxs-lookup"><span data-stu-id="df16c-236">RTCSRV</span></span>  <br/> |<span data-ttu-id="df16c-237">边缘服务器</span><span class="sxs-lookup"><span data-stu-id="df16c-237">Edge Server</span></span>  <br/> |<span data-ttu-id="df16c-238">12289</span><span class="sxs-lookup"><span data-stu-id="df16c-238">12289</span></span>  <br/> |<span data-ttu-id="df16c-239">12288</span><span class="sxs-lookup"><span data-stu-id="df16c-239">12288</span></span>  <br/> |
|<span data-ttu-id="df16c-240">RTCMRAUTH</span><span class="sxs-lookup"><span data-stu-id="df16c-240">RTCMRAUTH</span></span>  <br/> |<span data-ttu-id="df16c-241">边缘服务器</span><span class="sxs-lookup"><span data-stu-id="df16c-241">Edge Server</span></span>  <br/> |<span data-ttu-id="df16c-242">19003</span><span class="sxs-lookup"><span data-stu-id="df16c-242">19003</span></span>  <br/> |<span data-ttu-id="df16c-243">19002</span><span class="sxs-lookup"><span data-stu-id="df16c-243">19002</span></span>  <br/> |
|<span data-ttu-id="df16c-244">RTCMEDIARELAY</span><span class="sxs-lookup"><span data-stu-id="df16c-244">RTCMEDIARELAY</span></span>  <br/> |<span data-ttu-id="df16c-245">边缘服务器</span><span class="sxs-lookup"><span data-stu-id="df16c-245">Edge Server</span></span>  <br/> |<span data-ttu-id="df16c-246">22003</span><span class="sxs-lookup"><span data-stu-id="df16c-246">22003</span></span>  <br/> |<span data-ttu-id="df16c-247">22002</span><span class="sxs-lookup"><span data-stu-id="df16c-247">22002</span></span>  <br/> |

<span data-ttu-id="df16c-248">下表列出了 Microsoft 建议监视的网络问题：</span><span class="sxs-lookup"><span data-stu-id="df16c-248">The following table lists the network issues that Microsoft recommends monitoring:</span></span>


| <span data-ttu-id="df16c-249">监视器名称</span><span class="sxs-lookup"><span data-stu-id="df16c-249">Monitor Name</span></span>  <br/>                                        | <span data-ttu-id="df16c-250">目标服务器角色</span><span class="sxs-lookup"><span data-stu-id="df16c-250">Target Server Role</span></span>  <br/> | <span data-ttu-id="df16c-251">成功事件 ID 表达式</span><span class="sxs-lookup"><span data-stu-id="df16c-251">Success Event ID expression</span></span>  <br/> | <span data-ttu-id="df16c-252">错误事件 ID 表达式</span><span class="sxs-lookup"><span data-stu-id="df16c-252">Error Event ID expression</span></span>  <br/> | <span data-ttu-id="df16c-253">故障示例</span><span class="sxs-lookup"><span data-stu-id="df16c-253">Failure example</span></span>  <br/> |
|:-----------------------------------------------------------|:--------------------------|:-----------------------------------|:---------------------------------|:-----------------------|
| <span data-ttu-id="df16c-254">中介服务器到网关连接失败</span><span class="sxs-lookup"><span data-stu-id="df16c-254">Mediation Server to gateway connectivity failure</span></span>  <br/>    | <span data-ttu-id="df16c-255">中介服务器</span><span class="sxs-lookup"><span data-stu-id="df16c-255">Mediation Server</span></span>  <br/>   | <span data-ttu-id="df16c-256">25062</span><span class="sxs-lookup"><span data-stu-id="df16c-256">25062</span></span>                              |                                  | <span data-ttu-id="df16c-257">25002</span><span class="sxs-lookup"><span data-stu-id="df16c-257">25002</span></span>  <br/>           |
| <span data-ttu-id="df16c-258">中介服务器到网关呼叫完成失败</span><span class="sxs-lookup"><span data-stu-id="df16c-258">Mediation Server to gateway call completion failure</span></span>  <br/> | <span data-ttu-id="df16c-259">中介服务器</span><span class="sxs-lookup"><span data-stu-id="df16c-259">Mediation Server</span></span>  <br/>   | <span data-ttu-id="df16c-260">25064</span><span class="sxs-lookup"><span data-stu-id="df16c-260">25064</span></span>                              |                                  | <span data-ttu-id="df16c-261">25002</span><span class="sxs-lookup"><span data-stu-id="df16c-261">25002</span></span>  <br/>           |
| <span data-ttu-id="df16c-262">关键网络问题</span><span class="sxs-lookup"><span data-stu-id="df16c-262">Critical network problems</span></span>  <br/>                           | <span data-ttu-id="df16c-263">边缘服务器</span><span class="sxs-lookup"><span data-stu-id="df16c-263">Edge Server</span></span>  <br/>        | <span data-ttu-id="df16c-264">14353</span><span class="sxs-lookup"><span data-stu-id="df16c-264">14353</span></span>                              |                                  | <span data-ttu-id="df16c-265">12288</span><span class="sxs-lookup"><span data-stu-id="df16c-265">12288</span></span>  <br/>           |

<span data-ttu-id="df16c-266">下面列出了应监视的呼叫容量计数器。</span><span class="sxs-lookup"><span data-stu-id="df16c-266">The following lists the call capacity counters that should be monitored.</span></span> <span data-ttu-id="df16c-267">对于云连接器标准版，这些号码应小于500。小于50的云连接器最低版本。</span><span class="sxs-lookup"><span data-stu-id="df16c-267">These numbers should be less that 500 for Cloud Connector standard edition; less than 50 for Cloud Connector minimum edition.</span></span>

- <span data-ttu-id="df16c-268">LS： MediationServer) Current (_Total 的入站呼叫 \-</span><span class="sxs-lookup"><span data-stu-id="df16c-268">LS:MediationServer - Inbound Calls(_Total)\- Current</span></span> 

- <span data-ttu-id="df16c-269">LS： MediationServer- (_Total) Current 的出站呼叫 \-</span><span class="sxs-lookup"><span data-stu-id="df16c-269">LS:MediationServer - Outbound Calls(_Total)\- Current</span></span> 

- <span data-ttu-id="df16c-270">LS： MediationServer) \- Active media 旁路呼叫 (_Total 的入站呼叫</span><span class="sxs-lookup"><span data-stu-id="df16c-270">LS:MediationServer - Inbound Calls(_Total)\- Active media bypass calls</span></span>

- <span data-ttu-id="df16c-271">LS： MediationServer) \- Active media 旁路呼叫 (_Total 的出站呼叫</span><span class="sxs-lookup"><span data-stu-id="df16c-271">LS:MediationServer - Outbound Calls(_Total)\- Active media bypass calls</span></span>

## <a name="see-also"></a><span data-ttu-id="df16c-272">另请参阅</span><span class="sxs-lookup"><span data-stu-id="df16c-272">See also</span></span>

<span data-ttu-id="df16c-273">有关使用 OMS 的详细信息，请参阅以下内容：</span><span class="sxs-lookup"><span data-stu-id="df16c-273">For more information about working with OMS, see the following:</span></span>

- [<span data-ttu-id="df16c-274">在日志分析中使用日志搜索查找数据</span><span class="sxs-lookup"><span data-stu-id="df16c-274">Find data using log searches in Log Analytics</span></span>](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-searches)

- [<span data-ttu-id="df16c-275">Azure 日志分析语言参考</span><span class="sxs-lookup"><span data-stu-id="df16c-275">Azure Log Analytics Language Reference</span></span>](https://docs.loganalytics.io/docs/Language-Reference)

- [<span data-ttu-id="df16c-276">了解日志分析中的警报</span><span class="sxs-lookup"><span data-stu-id="df16c-276">Understanding alerts in Log Analytics</span></span>](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts)

- [<span data-ttu-id="df16c-277">将 Windows 计算机连接到 Azure 中的 Log Analytics 服务</span><span class="sxs-lookup"><span data-stu-id="df16c-277">Connect Windows computers to the Log Analytics service in Azure</span></span>](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents)


