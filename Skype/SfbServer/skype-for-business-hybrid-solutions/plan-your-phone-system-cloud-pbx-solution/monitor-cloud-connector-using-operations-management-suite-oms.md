---
title: 监视使用操作管理套件 (OMS) 的云连接器
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: edf4a04c-d4c9-4c05-aacc-9e084618bb55
description: 阅读本主题，以了解如何通过使用 Microsoft 操作管理套件 (OMS) 监视您的云连接器 2.1 版和更高版本的部署。
ms.openlocfilehash: 8cb454cfcb61bb11e0545ab5ff7dd45d1403ce55
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/05/2018
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a><span data-ttu-id="01197-103">监视使用操作管理套件 (OMS) 的云连接器</span><span class="sxs-lookup"><span data-stu-id="01197-103">Monitor Cloud Connector using Operations Management Suite (OMS)</span></span>
 
<span data-ttu-id="01197-104">阅读本主题，以了解如何通过使用 Microsoft 操作管理套件 (OMS) 监视您的云连接器 2.1 版和更高版本的部署。</span><span class="sxs-lookup"><span data-stu-id="01197-104">Read this topic to learn how to monitor your Cloud Connector version 2.1 and later deployment by using Microsoft Operations Management Suite (OMS).</span></span>
  
<span data-ttu-id="01197-105">现在可以通过使用操作管理套件 (OMS)，Microsoft IT 管理解决方案云监视您的云连接器 2.1 版和更高版本的部署。</span><span class="sxs-lookup"><span data-stu-id="01197-105">You can now monitor your Cloud Connector version 2.1 and later deployment by using Operations Management Suite (OMS), a Microsoft cloud IT management solution.</span></span> <span data-ttu-id="01197-106">OMS 日志分析功能使您能够监视和分析可用性和资源，包括物理和虚拟机的性能。</span><span class="sxs-lookup"><span data-stu-id="01197-106">OMS Log Analytics enables you to monitor and analyze the availability and performance of resources including physical and virtual machines.</span></span> <span data-ttu-id="01197-107">关于 OMS 和日志分析的详细信息，请参阅[操作管理套件 (OMS) 是什么？](https://docs.microsoft.com/en-us/azure/operations-management-suite/operations-management-suite-overview)。</span><span class="sxs-lookup"><span data-stu-id="01197-107">For more information about OMS and Log Analytics, see [What is Operations Management Suite (OMS)?](https://docs.microsoft.com/en-us/azure/operations-management-suite/operations-management-suite-overview).</span></span>
  
<span data-ttu-id="01197-108">本主题包括以下部分：</span><span class="sxs-lookup"><span data-stu-id="01197-108">This topic contains the following sections:</span></span>
  
- <span data-ttu-id="01197-109">先决条件</span><span class="sxs-lookup"><span data-stu-id="01197-109">Prerequisites</span></span>
    
- <span data-ttu-id="01197-110">云将连接器配置为使用 OMS</span><span class="sxs-lookup"><span data-stu-id="01197-110">Configure Cloud Connector to use OMS</span></span>
    
- <span data-ttu-id="01197-111">配置 OMS</span><span class="sxs-lookup"><span data-stu-id="01197-111">Configure OMS</span></span>
    
- <span data-ttu-id="01197-112">分析日志分析资料库中的警报</span><span class="sxs-lookup"><span data-stu-id="01197-112">Analyze the alerts in your Log Analytics repository</span></span>
    
- <span data-ttu-id="01197-113">建议使用的监控集</span><span class="sxs-lookup"><span data-stu-id="01197-113">Recommended monitoring set</span></span>
    
## <a name="prerequisites"></a><span data-ttu-id="01197-114">先决条件</span><span class="sxs-lookup"><span data-stu-id="01197-114">Prerequisites</span></span>

<span data-ttu-id="01197-115">您可以使用 OMS 监视云连接器部署之前，您需要以下：</span><span class="sxs-lookup"><span data-stu-id="01197-115">Before you can use OMS to monitor your Cloud Connector deployment, you will need the following:</span></span>
  
- <span data-ttu-id="01197-116">**Azure 帐户，OMS 区。**</span><span class="sxs-lookup"><span data-stu-id="01197-116">**An Azure account and an OMS workspace.**</span></span> <span data-ttu-id="01197-117">如果没有 Azure 帐户，您需要创建一个使用 OMS 日志分析。</span><span class="sxs-lookup"><span data-stu-id="01197-117">If you don't already have an Azure account, you will need to create one to use OMS Log Analytics.</span></span> <span data-ttu-id="01197-118">有关如何创建 Azure 帐户并设置 OMS 工作区的信息，请参阅[入门日志分析区](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-get-started)。</span><span class="sxs-lookup"><span data-stu-id="01197-118">For information about how to create an Azure account and set up an OMS workspace, see [Get started with a Log Analytics workspace](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-get-started).</span></span>
    
- <span data-ttu-id="01197-119">**云的连接器版本 2.1 或更高版本**</span><span class="sxs-lookup"><span data-stu-id="01197-119">**Cloud Connector version 2.1 or later**</span></span>
    
- <span data-ttu-id="01197-120">**新日志分析的日志搜索**时需要监控云连接器。</span><span class="sxs-lookup"><span data-stu-id="01197-120">**Log Analytics new log search** is required for Cloud Connector monitoring.</span></span> <span data-ttu-id="01197-121">有关详细信息，请参阅[升级到新的日志搜索您 Azure 日志分析的工作区](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-log-search-upgrade)。</span><span class="sxs-lookup"><span data-stu-id="01197-121">For more information, see [Upgrade your Azure Log Analytics workspace to new log search](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-log-search-upgrade).</span></span>
    
## <a name="configure-cloud-connector-to-use-oms"></a><span data-ttu-id="01197-122">云将连接器配置为使用 OMS</span><span class="sxs-lookup"><span data-stu-id="01197-122">Configure Cloud Connector to use OMS</span></span>

<span data-ttu-id="01197-123">您将需要配置使用 OMS 云接头内部环境。</span><span class="sxs-lookup"><span data-stu-id="01197-123">You'll need to configure your Cloud Connector on-premises environment to use OMS.</span></span> <span data-ttu-id="01197-124">要执行此操作，您将需要您的 OMS 区 ID 和密钥，您可以通过按如下方式使用 OMS 门户网站查找： 设置--\>连接源--\> Windows 服务器：</span><span class="sxs-lookup"><span data-stu-id="01197-124">To do this, you will need your OMS workspace ID and key, which you can find by using the OMS portal as follows: Settings --\>Connected Sources --\> Windows Servers:</span></span>
  
![云连接器 OMS 屏幕截图](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)
  
<span data-ttu-id="01197-126">配置云连接器使用 OMS 的方式取决于您的情况：</span><span class="sxs-lookup"><span data-stu-id="01197-126">How you configure Cloud Connector to use OMS depends on your scenario:</span></span>
  
- <span data-ttu-id="01197-127">**如果要安装新的云接头装置或要重新部署设备**，请按照下列步骤运行安装 CcAppliance 之前：</span><span class="sxs-lookup"><span data-stu-id="01197-127">**If you are installing a new Cloud Connector appliance or you want to re-deploy an appliance**, follow these steps before you run Install-CcAppliance:</span></span>
    
1. <span data-ttu-id="01197-128">在 CloudConnector.ini 文件 [公共] 部分中，将 OMSEnabled 参数设置为 True。</span><span class="sxs-lookup"><span data-stu-id="01197-128">In the CloudConnector.ini file [Common] section, set the OMSEnabled parameter to True.</span></span>
    
    <span data-ttu-id="01197-129">每次部署或升级，云连接器时它会尝试安装到虚拟机自动 OMS 代理。</span><span class="sxs-lookup"><span data-stu-id="01197-129">Each time Cloud Connector is deployed or upgraded, it will try to install the OMS agent automatically onto the VMs.</span></span> <span data-ttu-id="01197-130">因此 OMS 代理可以经受得住云接头自动更新，请启用此功能。</span><span class="sxs-lookup"><span data-stu-id="01197-130">Enable this feature so the OMS agent can survive the Cloud Connector automatic update.</span></span>
    
2. <span data-ttu-id="01197-131">若要配置的 OMS ID 和密钥，请运行组 CcCredential AccountType OMSWorkspace。</span><span class="sxs-lookup"><span data-stu-id="01197-131">To configure the OMS ID and key, run Set-CcCredential -AccountType OMSWorkspace.</span></span> 
    
- <span data-ttu-id="01197-132">**如果您正在安装到现有的云接头装置 OMS 代理**，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="01197-132">**If you are installing an OMS agent onto an existing Cloud Connector appliance**, follow these steps:</span></span>
    
1. <span data-ttu-id="01197-133">在 CloudConnector.ini 文件 [公共] 部分中，设置 OMSEnabled = true。</span><span class="sxs-lookup"><span data-stu-id="01197-133">In the CloudConnector.ini file [Common] section, set OMSEnabled=true.</span></span> 
    
2. <span data-ttu-id="01197-134">运行导入 CcConfiguration。</span><span class="sxs-lookup"><span data-stu-id="01197-134">Run Import-CcConfiguration.</span></span> 
    
3. <span data-ttu-id="01197-135">运行安装 CcOMSAgent。</span><span class="sxs-lookup"><span data-stu-id="01197-135">Run Install-CcOMSAgent.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="01197-136">如果从未设置 OMSWorkspace 凭据，您的凭据运行时安装 CcOMSAgent。</span><span class="sxs-lookup"><span data-stu-id="01197-136">If the OMSWorkspace credential has never been set, you are prompted for the credential when you run install-CcOMSAgent.</span></span> 
  
- <span data-ttu-id="01197-137">**如果您想要更新的 OMS 区 ID 或云接头装置中的密钥的已安装 OMS 代理：**</span><span class="sxs-lookup"><span data-stu-id="01197-137">**If you want to update the OMS workspace ID or key in a Cloud Connector appliance that has already installed an OMS agent:**</span></span>
    
1. <span data-ttu-id="01197-138">若要配置的 OMS ID 和密钥，请运行组 CcCredential AccountType OMSWorkspace。</span><span class="sxs-lookup"><span data-stu-id="01197-138">To configure the OMS ID and key, run Set-CcCredential -AccountType OMSWorkspace.</span></span> 
    
2. <span data-ttu-id="01197-139">若要应用这些更新，请运行安装 CcOMSAgent。</span><span class="sxs-lookup"><span data-stu-id="01197-139">To apply the updates, run Install-CcOMSAgent.</span></span> 
    
- <span data-ttu-id="01197-140">**对于所有方案，验证的代理连接，如下所示：**</span><span class="sxs-lookup"><span data-stu-id="01197-140">**For all scenarios, verify that the agents are connected as follows:**</span></span>
    
    <span data-ttu-id="01197-141">在 OMS 门户中，转到设置-\>连接源-\> Windows 服务器。</span><span class="sxs-lookup"><span data-stu-id="01197-141">In the OMS portal, go to Settings -\> Connected Sources -\> Windows Servers.</span></span> <span data-ttu-id="01197-142">您将看到已连接的计算机的列表。</span><span class="sxs-lookup"><span data-stu-id="01197-142">You will see a list of connected machines.</span></span> 
    
## <a name="configure-oms"></a><span data-ttu-id="01197-143">配置 OMS</span><span class="sxs-lookup"><span data-stu-id="01197-143">Configure OMS</span></span>

<span data-ttu-id="01197-144">接下来，需要指定使用 OMS 门户的 OMS 配置。</span><span class="sxs-lookup"><span data-stu-id="01197-144">Next, you will need to specify your OMS configuration by using the OMS portal.</span></span> <span data-ttu-id="01197-145">具体来说，您将需要：</span><span class="sxs-lookup"><span data-stu-id="01197-145">Specifically, you will need to:</span></span>
  
- <span data-ttu-id="01197-146">指定事件日志和性能计数器的信息。</span><span class="sxs-lookup"><span data-stu-id="01197-146">Specify information about event logs and performance counters.</span></span>
    
- <span data-ttu-id="01197-147">创建通知。</span><span class="sxs-lookup"><span data-stu-id="01197-147">Create alerts.</span></span> 
    
### <a name="specify-information-about-event-logs-and-performance-counters"></a><span data-ttu-id="01197-148">指定事件日志和性能计数器信息</span><span class="sxs-lookup"><span data-stu-id="01197-148">Specify information about event logs and performance counters</span></span>

<span data-ttu-id="01197-149">在 OMS 门户中，必须如下所示指定事件日志和性能计数器的信息：</span><span class="sxs-lookup"><span data-stu-id="01197-149">In the OMS portal, you must specify information about the event logs and performance counters as follows:</span></span>
  
1. <span data-ttu-id="01197-150">转到设置-\>数据-\>Windows 事件日志，并添加为事件日志：</span><span class="sxs-lookup"><span data-stu-id="01197-150">Go to Settings-\>Data-\>Windows Event logs, and add event logs for:</span></span> 
    
  - <span data-ttu-id="01197-151">Lync Server</span><span class="sxs-lookup"><span data-stu-id="01197-151">Lync Server</span></span>
    
  - <span data-ttu-id="01197-152">应用程序</span><span class="sxs-lookup"><span data-stu-id="01197-152">Application</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="01197-153">您必须在文本框中手动输入 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="01197-153">You must manually enter Lync Server in the text box.</span></span> <span data-ttu-id="01197-154">它不会不显示为下拉列表中的选项。</span><span class="sxs-lookup"><span data-stu-id="01197-154">It does not appear as an option in the drop-down list.</span></span> 
  
    <span data-ttu-id="01197-155">有关详细信息，请参阅[日志分析中的 Windows 事件日志数据源](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-data-sources-windows-events)</span><span class="sxs-lookup"><span data-stu-id="01197-155">For more information, see [Windows event log data sources in Log Analytics](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-data-sources-windows-events)</span></span>
    
2. <span data-ttu-id="01197-156">转到设置-\>数据-\> Windows 性能计数器，并将添加性能计数器：</span><span class="sxs-lookup"><span data-stu-id="01197-156">Go to Settings-\>Data-\> Windows Performance Counters, and add performance counters for:</span></span> 
    
  - <span data-ttu-id="01197-157">**操作系统级的计数器**。</span><span class="sxs-lookup"><span data-stu-id="01197-157">**OS level counters**.</span></span> <span data-ttu-id="01197-158">您可以添加 OS 级别的计数器，例如处理器使用率、 内存使用率、 网络使用情况，也可以使用现有的解决方案，如容量和性能，而无需显式添加计数器的网络性能监视器。</span><span class="sxs-lookup"><span data-stu-id="01197-158">You can add OS level counters, such as processor usage, memory usage, network usage, or you can use existing solutions such as Capacity and Performance, Network Performance Monitor without adding counters explicitly.</span></span> <span data-ttu-id="01197-159">无论您决定如何进行监视，Microsoft 建议您监视这些操作系统计数器。</span><span class="sxs-lookup"><span data-stu-id="01197-159">No matter how you decide to monitor them, Microsoft recommends that you monitor these OS counters.</span></span>
    
  - <span data-ttu-id="01197-160">**Skype 业务的计数器**。</span><span class="sxs-lookup"><span data-stu-id="01197-160">**Skype for Business counters**.</span></span> <span data-ttu-id="01197-161">有大量业务的 Skype 所提供的计数器。</span><span class="sxs-lookup"><span data-stu-id="01197-161">There are numerous counters provided by Skype for Business.</span></span> <span data-ttu-id="01197-162">通过登录到任何中介服务器并打开性能监视器，您可以找到这些计数器。</span><span class="sxs-lookup"><span data-stu-id="01197-162">You can find these counters by logging on to any Mediation Server and opening the Performance Monitor.</span></span> <span data-ttu-id="01197-163">这些计数器开始"LS:"。</span><span class="sxs-lookup"><span data-stu-id="01197-163">These counters start with "LS:".</span></span> <span data-ttu-id="01197-164">Microsoft 建议您开始至少下列容量计数器并添加其他感兴趣的人：</span><span class="sxs-lookup"><span data-stu-id="01197-164">Microsoft recommends that you start with the following capacity counters at a minimum, and add others that are of interest:</span></span>
    
    <span data-ttu-id="01197-165">总的活动联络：</span><span class="sxs-lookup"><span data-stu-id="01197-165">Total active calls:</span></span>
    
  - <span data-ttu-id="01197-166">LS:MediationServer-站 Calls(_Total)\-当前</span><span class="sxs-lookup"><span data-stu-id="01197-166">LS:MediationServer - Inbound Calls(_Total)\- Current</span></span> 
    
  - <span data-ttu-id="01197-167">LS:MediationServer-出站 Calls(_Total)\-当前</span><span class="sxs-lookup"><span data-stu-id="01197-167">LS:MediationServer - Outbound Calls(_Total)\- Current</span></span> 
    
    <span data-ttu-id="01197-168">总的活动媒体绕过调用：</span><span class="sxs-lookup"><span data-stu-id="01197-168">Total active media bypass calls:</span></span>
    
  - <span data-ttu-id="01197-169">LS:MediationServer-站 Calls(_Total)\-活动媒体绕过电话</span><span class="sxs-lookup"><span data-stu-id="01197-169">LS:MediationServer - Inbound Calls(_Total)\- Active media bypass calls</span></span> 
    
  - <span data-ttu-id="01197-170">LS:MediationServer-出站 Calls(_Total)\-活动媒体绕过电话</span><span class="sxs-lookup"><span data-stu-id="01197-170">LS:MediationServer - Outbound Calls(_Total)\- Active media bypass calls</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="01197-171">您必须在文本框中手动输入的性能计数器。</span><span class="sxs-lookup"><span data-stu-id="01197-171">You must manually enter the performance counters in the text box.</span></span> <span data-ttu-id="01197-172">它们不显示为下拉列表中的选项。</span><span class="sxs-lookup"><span data-stu-id="01197-172">They do not appear as options in the drop-down list.</span></span> 
  
    <span data-ttu-id="01197-173">有关详细信息，请参阅[Windows 和 Linux 日志分析中的性能数据源](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-data-sources-performance-counters)</span><span class="sxs-lookup"><span data-stu-id="01197-173">For more information, see [Windows and Linux performance data sources in Log Analytics](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-data-sources-performance-counters)</span></span>
    
### <a name="create-alerts"></a><span data-ttu-id="01197-174">创建通知</span><span class="sxs-lookup"><span data-stu-id="01197-174">Create alerts</span></span>

<span data-ttu-id="01197-175">有两种类型中 OMS 的警报： 结果通知和警报公制度量单位的数量。</span><span class="sxs-lookup"><span data-stu-id="01197-175">There are two types of alerts in OMS: Number of results alerts and Metric measurement alerts.</span></span> <span data-ttu-id="01197-176">有关创建通知的详细信息，请参阅[使用日志分析中的警报规则](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-alerts-creating)。</span><span class="sxs-lookup"><span data-stu-id="01197-176">For more information about creating alerts, see [Working with alert rules in Log Analytics](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-alerts-creating).</span></span>
  
<span data-ttu-id="01197-177">创建警报时，您应该考虑以下：</span><span class="sxs-lookup"><span data-stu-id="01197-177">You should consider the following when creating alerts:</span></span>
  
- <span data-ttu-id="01197-178">请确保通知结果数的警报，这是默认选择。</span><span class="sxs-lookup"><span data-stu-id="01197-178">Make sure the alert is a Number-of-results alert, which is the default selection.</span></span> 
    
- <span data-ttu-id="01197-179">演示的查询要求，"结果数"设置为"大于 0"。</span><span class="sxs-lookup"><span data-stu-id="01197-179">The demo queries require that "Number of results" is set to "Greater than 0".</span></span> 
    
- <span data-ttu-id="01197-180">建议您将设置时间窗口和警报的频率为 5 分钟。</span><span class="sxs-lookup"><span data-stu-id="01197-180">It is recommended that you set both Time window and Alert frequency to 5 minutes.</span></span> 
    
- <span data-ttu-id="01197-181">建议您不要启用"隐藏警报"演示通知。</span><span class="sxs-lookup"><span data-stu-id="01197-181">It is recommended that you do not enable "Suppress alerts" for demo alerts.</span></span> 
    
- <span data-ttu-id="01197-182">通常警告的情况下，Microsoft 建议创建警报一对： 一个错误警报和一个重置警报。</span><span class="sxs-lookup"><span data-stu-id="01197-182">For typical alert scenarios, Microsoft recommends creating a pair of alerts: one error alert and one reset alert.</span></span> <span data-ttu-id="01197-183">对于错误警报，选择严重性级别严重;重置警报，选择严重级别信息。</span><span class="sxs-lookup"><span data-stu-id="01197-183">For the error alert, select severity level Critical; for the reset alert, select severity level Informational .</span></span>
    
<span data-ttu-id="01197-184">以下各节介绍如何创建示例通知。</span><span class="sxs-lookup"><span data-stu-id="01197-184">The following sections describe how to create sample alerts.</span></span>
  
 <span data-ttu-id="01197-185">**创建警报对:"RTCMEDSRV 不在服务器上运行中介"和"RTCMEDSRV 是在中介服务器上运行"**</span><span class="sxs-lookup"><span data-stu-id="01197-185">**Create an alert pair: "RTCMEDSRV is NOT running in Mediation Servers" and "RTCMEDSRV is back in running in Mediation Servers"**</span></span>
  
<span data-ttu-id="01197-186">若要创建此警报对：</span><span class="sxs-lookup"><span data-stu-id="01197-186">To create this alert pair:</span></span>
  
- <span data-ttu-id="01197-187">是错误警报的查询：</span><span class="sxs-lookup"><span data-stu-id="01197-187">The query for the error alert is:</span></span>
    
  ```
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)
 | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    <span data-ttu-id="01197-188">该查询使用计算机筛选器*的计算机都包含"MediationServer"* 。</span><span class="sxs-lookup"><span data-stu-id="01197-188">The query uses the computer filter  *where Computer contains "MediationServer"*  .</span></span> <span data-ttu-id="01197-189">筛选器选择的计算机名称中包含字符串"MediationServer"。</span><span class="sxs-lookup"><span data-stu-id="01197-189">The filter selects only the computer whose name contains the string "MediationServer".</span></span>
    
     <span data-ttu-id="01197-190">将替换为计算机筛选器的筛选器，或只是将其删除。</span><span class="sxs-lookup"><span data-stu-id="01197-190">You would replace the filter with your own computer filter or simply remove it.</span></span> <span data-ttu-id="01197-191">您可以创建复杂的字符串没有正则表达式的筛选器。</span><span class="sxs-lookup"><span data-stu-id="01197-191">You can create complex string filters without regular expressions.</span></span> <span data-ttu-id="01197-192">有关详细信息，请参阅[字符串运算符](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators)。</span><span class="sxs-lookup"><span data-stu-id="01197-192">For more information, see [String operators](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators).</span></span> <span data-ttu-id="01197-193">您还可以使用正则表达式。</span><span class="sxs-lookup"><span data-stu-id="01197-193">You can also choose to use regular expressions.</span></span> <span data-ttu-id="01197-194">此外，您可以保存搜索查询，并为计算机筛选器警报查询中使用该组来创建计算机组。</span><span class="sxs-lookup"><span data-stu-id="01197-194">Moreover, you can create a computer group by saving a search query and using that group as your computer filter in your alert query.</span></span> <span data-ttu-id="01197-195">有关详细信息，请参阅[日志分析中的计算机组记录搜索](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-computer-groups)。</span><span class="sxs-lookup"><span data-stu-id="01197-195">For more information, see [Computer groups in Log Analytics log searches](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-computer-groups).</span></span>
    
    <span data-ttu-id="01197-196">为每台计算机，查询时发生错误将最后一个事件日志获取 RTCMEDSRV 服务启动和停止提供服务。</span><span class="sxs-lookup"><span data-stu-id="01197-196">For each computer, the error query will get the last event log for both the RTCMEDSRV service start and service stop.</span></span> <span data-ttu-id="01197-197">它会返回一个记录的最后一个事件是否服务停止事件;该属性将返回 nothing 的最后一个事件是否服务启动事件。</span><span class="sxs-lookup"><span data-stu-id="01197-197">It will return one log if the last event is the service stop event; it will return nothing if the last event is the service start event.</span></span> <span data-ttu-id="01197-198">简单地说，则查询将返回其 RTCMEDSRV 停止的时间窗口中的服务器的列表。</span><span class="sxs-lookup"><span data-stu-id="01197-198">In short, the query would return a list of servers whose RTCMEDSRV is stopped in the time window.</span></span> 
    
- <span data-ttu-id="01197-199">重置警报查询是：</span><span class="sxs-lookup"><span data-stu-id="01197-199">The query for the reset alert is:</span></span>
    
  ```
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)
 | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    <span data-ttu-id="01197-200">重置查询执行查询时发生错误的完全相反的事情。</span><span class="sxs-lookup"><span data-stu-id="01197-200">The reset query does exactly the opposite thing of the error query.</span></span> <span data-ttu-id="01197-201">对于每个计算机，它会返回一个如果最后一个事件是启动服务的事件;该属性将返回 nothing 的最后一个事件是否服务停止事件。</span><span class="sxs-lookup"><span data-stu-id="01197-201">For each computer, it will return one if the last event is the service start event; it will return nothing if the last event is the service stop event.</span></span>
    
 <span data-ttu-id="01197-202">**创建警报对:"太中介服务器中的多个并发调用"和"并行调用回退到正常负载"**</span><span class="sxs-lookup"><span data-stu-id="01197-202">**Create an alert pair: " Too many concurrent calls in Mediation Servers" and "Concurrent calls fall back to normal load"**</span></span>
  
<span data-ttu-id="01197-203">若要创建此警报：</span><span class="sxs-lookup"><span data-stu-id="01197-203">To create this alert:</span></span>
  
- <span data-ttu-id="01197-204">是错误警报的查询：</span><span class="sxs-lookup"><span data-stu-id="01197-204">The query for the error alert is:</span></span>
    
  ```
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName 
== "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize
 TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    <span data-ttu-id="01197-205">对于每个计算机，查询将得到的入站的调用和出站呼叫之和最后一个计数器这两个值。</span><span class="sxs-lookup"><span data-stu-id="01197-205">For each computer, the query will get the last counters for inbound call and outbound call and sum those two values.</span></span> <span data-ttu-id="01197-206">它会返回一个记录的总计值超过 500; 如果该属性将返回 nothing 如果它不存在。</span><span class="sxs-lookup"><span data-stu-id="01197-206">It will return one log if the sum value exceeds 500; it will return nothing if it doesn't.</span></span> <span data-ttu-id="01197-207">简单地说，则查询将返回其并发调用具有太多的时间窗口中的服务器的列表。</span><span class="sxs-lookup"><span data-stu-id="01197-207">In short, the query would return a list of servers whose concurrent calls are too many in the time window.</span></span>
    
- <span data-ttu-id="01197-208">重置警报查询是：</span><span class="sxs-lookup"><span data-stu-id="01197-208">The query for the reset alert is:</span></span>
    
  ```
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==
 "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize
 TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500

  ```

    <span data-ttu-id="01197-209">重置查询执行查询时发生错误的完全相反的事情。</span><span class="sxs-lookup"><span data-stu-id="01197-209">The reset query does exactly the opposite thing of the error query.</span></span> <span data-ttu-id="01197-210">对于每个计算机，查询将得到的入站的调用和出站呼叫之和最后一个计数器这两个值。</span><span class="sxs-lookup"><span data-stu-id="01197-210">For each computer, the query will get the last counters for inbound call and outbound call and sum those two values.</span></span> <span data-ttu-id="01197-211">它将返回一个日志的总和值是否小于 500;它将否则返回 nothing。</span><span class="sxs-lookup"><span data-stu-id="01197-211">It will return one log if the sum value is less than 500; it will return nothing otherwise.</span></span>
    
 <span data-ttu-id="01197-212">**创建一个通知:"CPU 使用率\>90 或 RTCMEDIARELAY 中的服务器停止"警报**</span><span class="sxs-lookup"><span data-stu-id="01197-212">**Create an alert: "CPU usage \> 90 or RTCMEDIARELAY stopped in Servers" alert**</span></span>
  
<span data-ttu-id="01197-213">若要创建此警报，该查询在：</span><span class="sxs-lookup"><span data-stu-id="01197-213">To create this alert, the query is:</span></span>
  
```
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==
 "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

<span data-ttu-id="01197-214">查询将从所有计算机并返回曾经停止一个日志，如果任一处理器使用率超过 90%或服务来获取所有的处理器使用情况计数器和服务停止事件。</span><span class="sxs-lookup"><span data-stu-id="01197-214">The query will get all processor usage counter and service stop event from all computers and return one log if either processor usage exceeds 90% or service is ever stopped.</span></span> 
  
## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a><span data-ttu-id="01197-215">分析日志分析资料库中的警报</span><span class="sxs-lookup"><span data-stu-id="01197-215">Analyze the alerts in your Log Analytics repository</span></span>

<span data-ttu-id="01197-216">要分析您的存储库中的警报，请使用警报管理解决方案。</span><span class="sxs-lookup"><span data-stu-id="01197-216">To analyze the alerts in your repository, use the Alert Management solution.</span></span> <span data-ttu-id="01197-217">有关详细信息，请参阅[警报管理解决方案中操作管理套件 (OMS)](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-solution-alert-management)</span><span class="sxs-lookup"><span data-stu-id="01197-217">For more information, see [Alert Management solution in Operations Management Suite (OMS)](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-solution-alert-management)</span></span>
  
## <a name="recommended-minimal-monitoring-set"></a><span data-ttu-id="01197-218">建议使用最小的监控集</span><span class="sxs-lookup"><span data-stu-id="01197-218">Recommended minimal monitoring set</span></span>

<span data-ttu-id="01197-219">确定问题与事件日志和性能计数器：</span><span class="sxs-lookup"><span data-stu-id="01197-219">To identify issues with event logs and performance counters:</span></span> 
  
- <span data-ttu-id="01197-220">**事件日志。**</span><span class="sxs-lookup"><span data-stu-id="01197-220">**Event logs.**</span></span> <span data-ttu-id="01197-221">对于任何问题，应为事件对，一套事件以指示有问题，而其他表示一切都好。</span><span class="sxs-lookup"><span data-stu-id="01197-221">For any issue, there should be an events pair, with one set of events to indicate something is wrong, while the other indicates that everything is well.</span></span> <span data-ttu-id="01197-222">对于任何给定的时间段，它是最后一个记录表明是否有异常情况该时间段的事件。</span><span class="sxs-lookup"><span data-stu-id="01197-222">For any given time period, it is the last event recorded that will indicate whether something is amiss for that time period.</span></span>
    
- <span data-ttu-id="01197-223">**性能计数器。**</span><span class="sxs-lookup"><span data-stu-id="01197-223">**Performance Counters.**</span></span> <span data-ttu-id="01197-224">应该有个受监视的计数器的阈值。</span><span class="sxs-lookup"><span data-stu-id="01197-224">There should be a threshold for the monitored counters.</span></span>
    
<span data-ttu-id="01197-225">下表列出了 Microsoft 建议监视通过停止和开始事件 Id 列出的服务：</span><span class="sxs-lookup"><span data-stu-id="01197-225">The following table lists the services that Microsoft recommends monitoring by listing the stop and start event IDs:</span></span>
  
|<span data-ttu-id="01197-226">服务名称</span><span class="sxs-lookup"><span data-stu-id="01197-226">Service Name</span></span>  <br/> |<span data-ttu-id="01197-227">目标服务器角色</span><span class="sxs-lookup"><span data-stu-id="01197-227">Target Server Role</span></span>  <br/> |<span data-ttu-id="01197-228">停止事件 ID</span><span class="sxs-lookup"><span data-stu-id="01197-228">Stop Event ID</span></span>  <br/> |<span data-ttu-id="01197-229">开始事件 ID</span><span class="sxs-lookup"><span data-stu-id="01197-229">Start Event ID</span></span>  <br/> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="01197-230">RTCMEDSRV</span><span class="sxs-lookup"><span data-stu-id="01197-230">RTCMEDSRV</span></span>  <br/> |<span data-ttu-id="01197-231">中介服务器</span><span class="sxs-lookup"><span data-stu-id="01197-231">Mediation Server</span></span>  <br/> |<span data-ttu-id="01197-232">25003</span><span class="sxs-lookup"><span data-stu-id="01197-232">25003</span></span>  <br/> |<span data-ttu-id="01197-233">25002</span><span class="sxs-lookup"><span data-stu-id="01197-233">25002</span></span>  <br/> |
|<span data-ttu-id="01197-234">RTCSRV</span><span class="sxs-lookup"><span data-stu-id="01197-234">RTCSRV</span></span>  <br/> |<span data-ttu-id="01197-235">边缘服务器</span><span class="sxs-lookup"><span data-stu-id="01197-235">Edge Server</span></span>  <br/> |<span data-ttu-id="01197-236">12289</span><span class="sxs-lookup"><span data-stu-id="01197-236">12289</span></span>  <br/> |<span data-ttu-id="01197-237">12288</span><span class="sxs-lookup"><span data-stu-id="01197-237">12288</span></span>  <br/> |
|<span data-ttu-id="01197-238">RTCMRAUTH</span><span class="sxs-lookup"><span data-stu-id="01197-238">RTCMRAUTH</span></span>  <br/> |<span data-ttu-id="01197-239">边缘服务器</span><span class="sxs-lookup"><span data-stu-id="01197-239">Edge Server</span></span>  <br/> |<span data-ttu-id="01197-240">19003</span><span class="sxs-lookup"><span data-stu-id="01197-240">19003</span></span>  <br/> |<span data-ttu-id="01197-241">19002</span><span class="sxs-lookup"><span data-stu-id="01197-241">19002</span></span>  <br/> |
|<span data-ttu-id="01197-242">RTCMEDIARELAY</span><span class="sxs-lookup"><span data-stu-id="01197-242">RTCMEDIARELAY</span></span>  <br/> |<span data-ttu-id="01197-243">边缘服务器</span><span class="sxs-lookup"><span data-stu-id="01197-243">Edge Server</span></span>  <br/> |<span data-ttu-id="01197-244">22003</span><span class="sxs-lookup"><span data-stu-id="01197-244">22003</span></span>  <br/> |<span data-ttu-id="01197-245">22002</span><span class="sxs-lookup"><span data-stu-id="01197-245">22002</span></span>  <br/> |
   
<span data-ttu-id="01197-246">下表列出了 Microsoft 建议监视的网络问题：</span><span class="sxs-lookup"><span data-stu-id="01197-246">The following table lists the network issues that Microsoft recommends monitoring:</span></span>
  
|<span data-ttu-id="01197-247">监视器名称</span><span class="sxs-lookup"><span data-stu-id="01197-247">Monitor Name</span></span>  <br/> |<span data-ttu-id="01197-248">目标服务器角色</span><span class="sxs-lookup"><span data-stu-id="01197-248">Target Server Role</span></span>  <br/> |<span data-ttu-id="01197-249">成功事件 ID 表达式</span><span class="sxs-lookup"><span data-stu-id="01197-249">Success Event ID expression</span></span>  <br/> |<span data-ttu-id="01197-250">错误事件 ID 表达式</span><span class="sxs-lookup"><span data-stu-id="01197-250">Error Event ID expression</span></span>  <br/> |<span data-ttu-id="01197-251">失败的示例</span><span class="sxs-lookup"><span data-stu-id="01197-251">Failure example</span></span>  <br/> |
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="01197-252">中介服务器到网关连接失败</span><span class="sxs-lookup"><span data-stu-id="01197-252">Mediation Server to gateway connectivity failure</span></span>  <br/> |<span data-ttu-id="01197-253">中介服务器</span><span class="sxs-lookup"><span data-stu-id="01197-253">Mediation Server</span></span>  <br/> |<span data-ttu-id="01197-254">25062</span><span class="sxs-lookup"><span data-stu-id="01197-254">25062</span></span> || <span data-ttu-id="01197-255">25002</span><span class="sxs-lookup"><span data-stu-id="01197-255">25002</span></span>  <br/> |<span data-ttu-id="01197-256">25061</span><span class="sxs-lookup"><span data-stu-id="01197-256">25061</span></span>  <br/> |<span data-ttu-id="01197-257">MS PING （选项） 网关失败</span><span class="sxs-lookup"><span data-stu-id="01197-257">MS PING (option) Gateway failed</span></span>  <br/> |
|<span data-ttu-id="01197-258">中介服务器到网关呼叫完成故障</span><span class="sxs-lookup"><span data-stu-id="01197-258">Mediation Server to gateway call completion failure</span></span>  <br/> |<span data-ttu-id="01197-259">中介服务器</span><span class="sxs-lookup"><span data-stu-id="01197-259">Mediation Server</span></span>  <br/> |<span data-ttu-id="01197-260">25064</span><span class="sxs-lookup"><span data-stu-id="01197-260">25064</span></span> || <span data-ttu-id="01197-261">25002</span><span class="sxs-lookup"><span data-stu-id="01197-261">25002</span></span>  <br/> |<span data-ttu-id="01197-262">25063</span><span class="sxs-lookup"><span data-stu-id="01197-262">25063</span></span>  <br/> |<span data-ttu-id="01197-263">MS 试图使到网关呼叫失败</span><span class="sxs-lookup"><span data-stu-id="01197-263">MS trying to make call to Gateway failed</span></span>  <br/> |
|<span data-ttu-id="01197-264">关键网络问题</span><span class="sxs-lookup"><span data-stu-id="01197-264">Critical network problems</span></span>  <br/> |<span data-ttu-id="01197-265">边缘服务器</span><span class="sxs-lookup"><span data-stu-id="01197-265">Edge Server</span></span>  <br/> |<span data-ttu-id="01197-266">14353</span><span class="sxs-lookup"><span data-stu-id="01197-266">14353</span></span> || <span data-ttu-id="01197-267">12288</span><span class="sxs-lookup"><span data-stu-id="01197-267">12288</span></span>  <br/> |<span data-ttu-id="01197-268">14624</span><span class="sxs-lookup"><span data-stu-id="01197-268">14624</span></span>  <br/> |<span data-ttu-id="01197-269">TLS 传输本地 IP 地址 192.168.231.14 在端口 5061 上启动失败</span><span class="sxs-lookup"><span data-stu-id="01197-269">Transport TLS has failed to start on local IP address 192.168.231.14 at port 5061</span></span>  <br/> |
   
<span data-ttu-id="01197-270">下面列出了您应该监视电话容量计数器。</span><span class="sxs-lookup"><span data-stu-id="01197-270">The following lists the call capacity counters that should be monitored.</span></span> <span data-ttu-id="01197-271">这些数字应该是，小于 500 的云接口标准版;低于 50 云连接器最小版。</span><span class="sxs-lookup"><span data-stu-id="01197-271">These numbers should be less that 500 for Cloud Connector standard edition; less than 50 for Cloud Connector minimum edition.</span></span>
  
- <span data-ttu-id="01197-272">LS:MediationServer-站 Calls(_Total)\-当前</span><span class="sxs-lookup"><span data-stu-id="01197-272">LS:MediationServer - Inbound Calls(_Total)\- Current</span></span> 
    
- <span data-ttu-id="01197-273">LS:MediationServer-出站 Calls(_Total)\-当前</span><span class="sxs-lookup"><span data-stu-id="01197-273">LS:MediationServer - Outbound Calls(_Total)\- Current</span></span> 
    
- <span data-ttu-id="01197-274">LS:MediationServer-站 Calls(_Total)\-活动媒体绕过电话</span><span class="sxs-lookup"><span data-stu-id="01197-274">LS:MediationServer - Inbound Calls(_Total)\- Active media bypass calls</span></span>
    
- <span data-ttu-id="01197-275">LS:MediationServer-出站 Calls(_Total)\-活动媒体绕过电话</span><span class="sxs-lookup"><span data-stu-id="01197-275">LS:MediationServer - Outbound Calls(_Total)\- Active media bypass calls</span></span>
    
## <a name="see-also"></a><span data-ttu-id="01197-276">另请参阅</span><span class="sxs-lookup"><span data-stu-id="01197-276">See also</span></span>

<span data-ttu-id="01197-277">有关使用 OMS 的详细信息，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="01197-277">For more information about working with OMS, see the following:</span></span>
  
- [<span data-ttu-id="01197-278">日志分析中使用日志搜索查找数据</span><span class="sxs-lookup"><span data-stu-id="01197-278">Find data using log searches in Log Analytics</span></span>](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-log-searches)
    
- [<span data-ttu-id="01197-279">Azure 日志分析语言参考</span><span class="sxs-lookup"><span data-stu-id="01197-279">Azure Log Analytics Language Reference</span></span>](https://docs.loganalytics.io/docs/Language-Reference)
    
- [<span data-ttu-id="01197-280">日志分析中了解警报</span><span class="sxs-lookup"><span data-stu-id="01197-280">Understanding alerts in Log Analytics</span></span>](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-alerts)
    
- [<span data-ttu-id="01197-281">连接到 Azure 中的日志分析服务的 Windows 的计算机</span><span class="sxs-lookup"><span data-stu-id="01197-281">Connect Windows computers to the Log Analytics service in Azure</span></span>](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-windows-agents)
    

