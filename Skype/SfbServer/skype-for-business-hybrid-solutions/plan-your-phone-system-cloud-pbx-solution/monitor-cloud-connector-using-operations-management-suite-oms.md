---
title: 监视云连接器使用操作管理套件 (OMS)
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: edf4a04c-d4c9-4c05-aacc-9e084618bb55
description: 阅读本主题可了解如何使用 Microsoft 操作管理套件 (OMS) 监视您的云连接器版本 2.1 和更高版本的部署。
ms.openlocfilehash: 19946c0d7701d2fd31c1b41cae58e08cfdf4c52d
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2018
ms.locfileid: "26295069"
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a><span data-ttu-id="0cee1-103">监视云连接器使用操作管理套件 (OMS)</span><span class="sxs-lookup"><span data-stu-id="0cee1-103">Monitor Cloud Connector using Operations Management Suite (OMS)</span></span>

<span data-ttu-id="0cee1-104">阅读本主题可了解如何使用 Microsoft 操作管理套件 (OMS) 监视您的云连接器版本 2.1 和更高版本的部署。</span><span class="sxs-lookup"><span data-stu-id="0cee1-104">Read this topic to learn how to monitor your Cloud Connector version 2.1 and later deployment by using Microsoft Operations Management Suite (OMS).</span></span>

<span data-ttu-id="0cee1-105">您现在可以通过使用操作管理套件 (OMS) Microsoft 云 IT 管理解决方案监视您的云连接器版本 2.1 和更高版本的部署。</span><span class="sxs-lookup"><span data-stu-id="0cee1-105">You can now monitor your Cloud Connector version 2.1 and later deployment by using Operations Management Suite (OMS), a Microsoft cloud IT management solution.</span></span> <span data-ttu-id="0cee1-106">OMS 日志分析，可以监视和分析的可用性和性能的资源，包括物理和虚拟机。</span><span class="sxs-lookup"><span data-stu-id="0cee1-106">OMS Log Analytics enables you to monitor and analyze the availability and performance of resources including physical and virtual machines.</span></span> <span data-ttu-id="0cee1-107">有关 OMS 和日志分析的详细信息，请参阅[操作管理套件 (OMS) 是什么？](https://docs.microsoft.com/en-us/azure/operations-management-suite/operations-management-suite-overview)。</span><span class="sxs-lookup"><span data-stu-id="0cee1-107">For more information about OMS and Log Analytics, see [What is Operations Management Suite (OMS)?](https://docs.microsoft.com/en-us/azure/operations-management-suite/operations-management-suite-overview).</span></span>

<span data-ttu-id="0cee1-108">本主题包括以下部分：</span><span class="sxs-lookup"><span data-stu-id="0cee1-108">This topic contains the following sections:</span></span>

- <span data-ttu-id="0cee1-109">先决条件</span><span class="sxs-lookup"><span data-stu-id="0cee1-109">Prerequisites</span></span>

- <span data-ttu-id="0cee1-110">配置要使用 OMS 的云连接器</span><span class="sxs-lookup"><span data-stu-id="0cee1-110">Configure Cloud Connector to use OMS</span></span>

- <span data-ttu-id="0cee1-111">配置 OMS</span><span class="sxs-lookup"><span data-stu-id="0cee1-111">Configure OMS</span></span>

- <span data-ttu-id="0cee1-112">分析日志分析资料库中的通知</span><span class="sxs-lookup"><span data-stu-id="0cee1-112">Analyze the alerts in your Log Analytics repository</span></span>

- <span data-ttu-id="0cee1-113">建议的监视设置</span><span class="sxs-lookup"><span data-stu-id="0cee1-113">Recommended monitoring set</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0cee1-114">先决条件</span><span class="sxs-lookup"><span data-stu-id="0cee1-114">Prerequisites</span></span>

<span data-ttu-id="0cee1-115">您可以使用 OMS 监视云连接器部署之前，您将需要以下各项：</span><span class="sxs-lookup"><span data-stu-id="0cee1-115">Before you can use OMS to monitor your Cloud Connector deployment, you will need the following:</span></span>

- <span data-ttu-id="0cee1-116">**Azure 帐户和 OMS 工作区。**</span><span class="sxs-lookup"><span data-stu-id="0cee1-116">**An Azure account and an OMS workspace.**</span></span> <span data-ttu-id="0cee1-117">如果您没有 Azure 帐户，您需要创建一个使用 OMS 日志分析。</span><span class="sxs-lookup"><span data-stu-id="0cee1-117">If you don't already have an Azure account, you will need to create one to use OMS Log Analytics.</span></span> <span data-ttu-id="0cee1-118">有关如何创建 Azure 帐户和设置 OMS 工作区的信息，请参阅[开始使用日志分析工作区](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-get-started)。</span><span class="sxs-lookup"><span data-stu-id="0cee1-118">For information about how to create an Azure account and set up an OMS workspace, see [Get started with a Log Analytics workspace](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-get-started).</span></span>

- <span data-ttu-id="0cee1-119">**云连接器 2.1 或更高版本**</span><span class="sxs-lookup"><span data-stu-id="0cee1-119">**Cloud Connector version 2.1 or later**</span></span>

- <span data-ttu-id="0cee1-120">需要云连接器监视**日志分析新的日志搜索**。</span><span class="sxs-lookup"><span data-stu-id="0cee1-120">**Log Analytics new log search** is required for Cloud Connector monitoring.</span></span> <span data-ttu-id="0cee1-121">有关详细信息，请参阅[升级到新的日志搜索您 Azure 日志分析工作区](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-log-search-upgrade)。</span><span class="sxs-lookup"><span data-stu-id="0cee1-121">For more information, see [Upgrade your Azure Log Analytics workspace to new log search](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-log-search-upgrade).</span></span>

## <a name="configure-cloud-connector-to-use-oms"></a><span data-ttu-id="0cee1-122">配置要使用 OMS 的云连接器</span><span class="sxs-lookup"><span data-stu-id="0cee1-122">Configure Cloud Connector to use OMS</span></span>

<span data-ttu-id="0cee1-123">您需要配置云连接器在本地环境若要使用 OMS。</span><span class="sxs-lookup"><span data-stu-id="0cee1-123">You'll need to configure your Cloud Connector on-premises environment to use OMS.</span></span> <span data-ttu-id="0cee1-124">若要执行此操作，您需要您 OMS 工作区 ID 和密钥，您可以找到使用 OMS 门户，如下所示： 设置--\>连接源--\> Windows 服务器：</span><span class="sxs-lookup"><span data-stu-id="0cee1-124">To do this, you will need your OMS workspace ID and key, which you can find by using the OMS portal as follows: Settings --\>Connected Sources --\> Windows Servers:</span></span>

![云连接器 OMS 屏幕截图](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)

<span data-ttu-id="0cee1-126">要使用 OMS 的云连接器的配置方式取决于您的方案：</span><span class="sxs-lookup"><span data-stu-id="0cee1-126">How you configure Cloud Connector to use OMS depends on your scenario:</span></span>

- <span data-ttu-id="0cee1-127">**如果您正在安装新的云连接器装置或想要重新部署设备**，请按照下列步骤在运行安装 CcAppliance 之前：</span><span class="sxs-lookup"><span data-stu-id="0cee1-127">**If you are installing a new Cloud Connector appliance or you want to re-deploy an appliance**, follow these steps before you run Install-CcAppliance:</span></span>

1. <span data-ttu-id="0cee1-128">在 CloudConnector.ini 文件 [常见] 部分中，将 OMSEnabled 参数设置为 True。</span><span class="sxs-lookup"><span data-stu-id="0cee1-128">In the CloudConnector.ini file [Common] section, set the OMSEnabled parameter to True.</span></span>

    <span data-ttu-id="0cee1-129">每次云连接器部署或升级，则将尝试安装自动到虚拟机 OMS 代理。</span><span class="sxs-lookup"><span data-stu-id="0cee1-129">Each time Cloud Connector is deployed or upgraded, it will try to install the OMS agent automatically onto the VMs.</span></span> <span data-ttu-id="0cee1-130">启用此功能，以便 OMS 代理可以排除云连接器的自动更新。</span><span class="sxs-lookup"><span data-stu-id="0cee1-130">Enable this feature so the OMS agent can survive the Cloud Connector automatic update.</span></span>

2. <span data-ttu-id="0cee1-131">若要配置的 OMS ID 和密钥，请运行设置 CcCredential AccountType OMSWorkspace。</span><span class="sxs-lookup"><span data-stu-id="0cee1-131">To configure the OMS ID and key, run Set-CcCredential -AccountType OMSWorkspace.</span></span> 

- <span data-ttu-id="0cee1-132">**如果要安装到现有云连接器设备 OMS 代理**，请按照下列步骤：</span><span class="sxs-lookup"><span data-stu-id="0cee1-132">**If you are installing an OMS agent onto an existing Cloud Connector appliance**, follow these steps:</span></span>

1. <span data-ttu-id="0cee1-133">在 CloudConnector.ini 文件 [常见] 部分中，设置 OMSEnabled = true。</span><span class="sxs-lookup"><span data-stu-id="0cee1-133">In the CloudConnector.ini file [Common] section, set OMSEnabled=true.</span></span> 

2. <span data-ttu-id="0cee1-134">运行导入 CcConfiguration。</span><span class="sxs-lookup"><span data-stu-id="0cee1-134">Run Import-CcConfiguration.</span></span> 

3. <span data-ttu-id="0cee1-135">运行安装 CcOMSAgent。</span><span class="sxs-lookup"><span data-stu-id="0cee1-135">Run Install-CcOMSAgent.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="0cee1-136">如果从未设置 OMSWorkspace 凭据，则系统会提示凭据运行安装 CcOMSAgent 时。</span><span class="sxs-lookup"><span data-stu-id="0cee1-136">If the OMSWorkspace credential has never been set, you are prompted for the credential when you run install-CcOMSAgent.</span></span> 

- <span data-ttu-id="0cee1-137">**如果您想要更新的 OMS 工作区 ID 或云连接器装置中的项的已安装 OMS 代理：**</span><span class="sxs-lookup"><span data-stu-id="0cee1-137">**If you want to update the OMS workspace ID or key in a Cloud Connector appliance that has already installed an OMS agent:**</span></span>

1. <span data-ttu-id="0cee1-138">若要配置的 OMS ID 和密钥，请运行设置 CcCredential AccountType OMSWorkspace。</span><span class="sxs-lookup"><span data-stu-id="0cee1-138">To configure the OMS ID and key, run Set-CcCredential -AccountType OMSWorkspace.</span></span> 

2. <span data-ttu-id="0cee1-139">若要应用更新，请运行安装 CcOMSAgent。</span><span class="sxs-lookup"><span data-stu-id="0cee1-139">To apply the updates, run Install-CcOMSAgent.</span></span> 

- <span data-ttu-id="0cee1-140">**对于所有方案，确认代理相连，如下所示：**</span><span class="sxs-lookup"><span data-stu-id="0cee1-140">**For all scenarios, verify that the agents are connected as follows:**</span></span>

    <span data-ttu-id="0cee1-141">在 OMS 门户中，转到设置-\>连接源-\> Windows 服务器。</span><span class="sxs-lookup"><span data-stu-id="0cee1-141">In the OMS portal, go to Settings -\> Connected Sources -\> Windows Servers.</span></span> <span data-ttu-id="0cee1-142">您将看到已连接的计算机列表。</span><span class="sxs-lookup"><span data-stu-id="0cee1-142">You will see a list of connected machines.</span></span> 

## <a name="configure-oms"></a><span data-ttu-id="0cee1-143">配置 OMS</span><span class="sxs-lookup"><span data-stu-id="0cee1-143">Configure OMS</span></span>

<span data-ttu-id="0cee1-144">接下来，您需要使用 OMS 门户指定您 OMS 的配置。</span><span class="sxs-lookup"><span data-stu-id="0cee1-144">Next, you will need to specify your OMS configuration by using the OMS portal.</span></span> <span data-ttu-id="0cee1-145">具体而言，您将需要：</span><span class="sxs-lookup"><span data-stu-id="0cee1-145">Specifically, you will need to:</span></span>

- <span data-ttu-id="0cee1-146">指定的事件日志和性能计数器信息。</span><span class="sxs-lookup"><span data-stu-id="0cee1-146">Specify information about event logs and performance counters.</span></span>

- <span data-ttu-id="0cee1-147">创建通知。</span><span class="sxs-lookup"><span data-stu-id="0cee1-147">Create alerts.</span></span> 

### <a name="specify-information-about-event-logs-and-performance-counters"></a><span data-ttu-id="0cee1-148">指定有关的事件日志和性能计数器信息</span><span class="sxs-lookup"><span data-stu-id="0cee1-148">Specify information about event logs and performance counters</span></span>

<span data-ttu-id="0cee1-149">在 OMS 门户中，您必须指定的事件日志和性能计数器的信息，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0cee1-149">In the OMS portal, you must specify information about the event logs and performance counters as follows:</span></span>

1. <span data-ttu-id="0cee1-150">转到设置-\>数据-\>Windows 事件日志，并将其添加的事件日志：</span><span class="sxs-lookup"><span data-stu-id="0cee1-150">Go to Settings-\>Data-\>Windows Event logs, and add event logs for:</span></span> 

   - <span data-ttu-id="0cee1-151">Lync Server</span><span class="sxs-lookup"><span data-stu-id="0cee1-151">Lync Server</span></span>

   - <span data-ttu-id="0cee1-152">应用程序</span><span class="sxs-lookup"><span data-stu-id="0cee1-152">Application</span></span>

     > [!NOTE]
     > <span data-ttu-id="0cee1-153">您必须手动在文本框中输入 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="0cee1-153">You must manually enter Lync Server in the text box.</span></span> <span data-ttu-id="0cee1-154">它不显示为下拉列表中的选项。</span><span class="sxs-lookup"><span data-stu-id="0cee1-154">It does not appear as an option in the drop-down list.</span></span> 

     <span data-ttu-id="0cee1-155">有关详细信息，请参阅[日志分析中的 Windows 事件日志数据源](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-data-sources-windows-events)</span><span class="sxs-lookup"><span data-stu-id="0cee1-155">For more information, see [Windows event log data sources in Log Analytics](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-data-sources-windows-events)</span></span>

2. <span data-ttu-id="0cee1-156">转到设置-\>数据-\> Windows 性能计数器，并将其添加性能计数器：</span><span class="sxs-lookup"><span data-stu-id="0cee1-156">Go to Settings-\>Data-\> Windows Performance Counters, and add performance counters for:</span></span> 

   - <span data-ttu-id="0cee1-157">**操作系统级别计数器**。</span><span class="sxs-lookup"><span data-stu-id="0cee1-157">**OS level counters**.</span></span> <span data-ttu-id="0cee1-158">您可以添加 OS 级别计数器，如处理器使用率、 内存使用率、 网络使用情况，或者您可以使用现有的解决方案，例如容量和性能、 网络性能监视器不明确添加计数器。</span><span class="sxs-lookup"><span data-stu-id="0cee1-158">You can add OS level counters, such as processor usage, memory usage, network usage, or you can use existing solutions such as Capacity and Performance, Network Performance Monitor without adding counters explicitly.</span></span> <span data-ttu-id="0cee1-159">无论您决定如何监视其，Microsoft 建议您监视这些 OS 计数器。</span><span class="sxs-lookup"><span data-stu-id="0cee1-159">No matter how you decide to monitor them, Microsoft recommends that you monitor these OS counters.</span></span>

   - <span data-ttu-id="0cee1-160">**Skype 的业务计数器**。</span><span class="sxs-lookup"><span data-stu-id="0cee1-160">**Skype for Business counters**.</span></span> <span data-ttu-id="0cee1-161">有许多 for Business 的 Skype 提供的计数器。</span><span class="sxs-lookup"><span data-stu-id="0cee1-161">There are numerous counters provided by Skype for Business.</span></span> <span data-ttu-id="0cee1-162">您可以通过在登录到的任何中介服务器并打开性能监视器中找到这些计数器。</span><span class="sxs-lookup"><span data-stu-id="0cee1-162">You can find these counters by logging on to any Mediation Server and opening the Performance Monitor.</span></span> <span data-ttu-id="0cee1-163">这些计数器开头"LS:"。</span><span class="sxs-lookup"><span data-stu-id="0cee1-163">These counters start with "LS:".</span></span> <span data-ttu-id="0cee1-164">Microsoft 建议您启动与至少以下容量计数器，然后添加感兴趣的其他人：</span><span class="sxs-lookup"><span data-stu-id="0cee1-164">Microsoft recommends that you start with the following capacity counters at a minimum, and add others that are of interest:</span></span>

     <span data-ttu-id="0cee1-165">总活动呼叫：</span><span class="sxs-lookup"><span data-stu-id="0cee1-165">Total active calls:</span></span>

   - <span data-ttu-id="0cee1-166">LS:MediationServer-入站 Calls(_Total)\-当前</span><span class="sxs-lookup"><span data-stu-id="0cee1-166">LS:MediationServer - Inbound Calls(_Total)\- Current</span></span> 

   - <span data-ttu-id="0cee1-167">LS:MediationServer-出站 Calls(_Total)\-当前</span><span class="sxs-lookup"><span data-stu-id="0cee1-167">LS:MediationServer - Outbound Calls(_Total)\- Current</span></span> 

     <span data-ttu-id="0cee1-168">总活动的媒体绕过呼叫：</span><span class="sxs-lookup"><span data-stu-id="0cee1-168">Total active media bypass calls:</span></span>

   - <span data-ttu-id="0cee1-169">LS:MediationServer-入站 Calls(_Total)\-活动的媒体绕过呼叫</span><span class="sxs-lookup"><span data-stu-id="0cee1-169">LS:MediationServer - Inbound Calls(_Total)\- Active media bypass calls</span></span> 

   - <span data-ttu-id="0cee1-170">LS:MediationServer-出站 Calls(_Total)\-活动的媒体绕过呼叫</span><span class="sxs-lookup"><span data-stu-id="0cee1-170">LS:MediationServer - Outbound Calls(_Total)\- Active media bypass calls</span></span> 

     > [!NOTE]
     > <span data-ttu-id="0cee1-171">您必须手动在文本框中输入的性能计数器。</span><span class="sxs-lookup"><span data-stu-id="0cee1-171">You must manually enter the performance counters in the text box.</span></span> <span data-ttu-id="0cee1-172">它们不显示为下拉列表中的选项。</span><span class="sxs-lookup"><span data-stu-id="0cee1-172">They do not appear as options in the drop-down list.</span></span> 

     <span data-ttu-id="0cee1-173">有关详细信息，请参阅[日志分析中的 Windows 和 Linux 性能数据源](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-data-sources-performance-counters)</span><span class="sxs-lookup"><span data-stu-id="0cee1-173">For more information, see [Windows and Linux performance data sources in Log Analytics](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-data-sources-performance-counters)</span></span>

### <a name="create-alerts"></a><span data-ttu-id="0cee1-174">创建通知</span><span class="sxs-lookup"><span data-stu-id="0cee1-174">Create alerts</span></span>

<span data-ttu-id="0cee1-175">有两种类型的通知中 OMS： 结果通知和公制度量通知的数目。</span><span class="sxs-lookup"><span data-stu-id="0cee1-175">There are two types of alerts in OMS: Number of results alerts and Metric measurement alerts.</span></span> <span data-ttu-id="0cee1-176">有关创建通知的详细信息，请参阅[使用日志分析中的通知规则](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-alerts-creating)。</span><span class="sxs-lookup"><span data-stu-id="0cee1-176">For more information about creating alerts, see [Working with alert rules in Log Analytics](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-alerts-creating).</span></span>

<span data-ttu-id="0cee1-177">创建通知时，您应考虑以下：</span><span class="sxs-lookup"><span data-stu-id="0cee1-177">You should consider the following when creating alerts:</span></span>

- <span data-ttu-id="0cee1-178">请确保警报结果号码的通知中，这是默认选项。</span><span class="sxs-lookup"><span data-stu-id="0cee1-178">Make sure the alert is a Number-of-results alert, which is the default selection.</span></span> 

- <span data-ttu-id="0cee1-179">演示查询都需要"的结果数"设置为"大于 0"。</span><span class="sxs-lookup"><span data-stu-id="0cee1-179">The demo queries require that "Number of results" is set to "Greater than 0".</span></span> 

- <span data-ttu-id="0cee1-180">建议您设置时间窗口和通知的频率为 5 分钟。</span><span class="sxs-lookup"><span data-stu-id="0cee1-180">It is recommended that you set both Time window and Alert frequency to 5 minutes.</span></span> 

- <span data-ttu-id="0cee1-181">建议您未启用"抑制通知"演示通知。</span><span class="sxs-lookup"><span data-stu-id="0cee1-181">It is recommended that you do not enable "Suppress alerts" for demo alerts.</span></span> 

- <span data-ttu-id="0cee1-182">典型的警报方案，Microsoft 建议创建一对通知： 一个错误通知和一个重置通知。</span><span class="sxs-lookup"><span data-stu-id="0cee1-182">For typical alert scenarios, Microsoft recommends creating a pair of alerts: one error alert and one reset alert.</span></span> <span data-ttu-id="0cee1-183">对于错误通知中，选择严重级别关键;对于重置通知中，选择严重级别信息。</span><span class="sxs-lookup"><span data-stu-id="0cee1-183">For the error alert, select severity level Critical; for the reset alert, select severity level Informational .</span></span>

<span data-ttu-id="0cee1-184">以下各节介绍如何创建示例通知。</span><span class="sxs-lookup"><span data-stu-id="0cee1-184">The following sections describe how to create sample alerts.</span></span>

 <span data-ttu-id="0cee1-185">**创建通知对:"RTCMEDSRV 未运行在中介服务器"和"RTCMEDSRV is 后中在中介服务器上运行"**</span><span class="sxs-lookup"><span data-stu-id="0cee1-185">**Create an alert pair: "RTCMEDSRV is NOT running in Mediation Servers" and "RTCMEDSRV is back in running in Mediation Servers"**</span></span>

<span data-ttu-id="0cee1-186">若要创建此通知对：</span><span class="sxs-lookup"><span data-stu-id="0cee1-186">To create this alert pair:</span></span>

- <span data-ttu-id="0cee1-187">错误警告的查询为：</span><span class="sxs-lookup"><span data-stu-id="0cee1-187">The query for the error alert is:</span></span>

  ```
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)  | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    <span data-ttu-id="0cee1-188">查询使用计算机筛选器，*其中计算机包含"MediationServer"* 。</span><span class="sxs-lookup"><span data-stu-id="0cee1-188">The query uses the computer filter  *where Computer contains "MediationServer"*  .</span></span> <span data-ttu-id="0cee1-189">筛选器选择仅名称中包含字符串"MediationServer"的计算机。</span><span class="sxs-lookup"><span data-stu-id="0cee1-189">The filter selects only the computer whose name contains the string "MediationServer".</span></span>

     <span data-ttu-id="0cee1-190">将替换计算机筛选器的筛选器，也可以只需将其删除。</span><span class="sxs-lookup"><span data-stu-id="0cee1-190">You would replace the filter with your own computer filter or simply remove it.</span></span> <span data-ttu-id="0cee1-191">您可以创建复杂的字符串不正则表达式的筛选器。</span><span class="sxs-lookup"><span data-stu-id="0cee1-191">You can create complex string filters without regular expressions.</span></span> <span data-ttu-id="0cee1-192">有关详细信息，请参阅[字符串运算符](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators)。</span><span class="sxs-lookup"><span data-stu-id="0cee1-192">For more information, see [String operators](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators).</span></span> <span data-ttu-id="0cee1-193">您还可以选择使用正则表达式。</span><span class="sxs-lookup"><span data-stu-id="0cee1-193">You can also choose to use regular expressions.</span></span> <span data-ttu-id="0cee1-194">此外，您可以创建计算机组保存搜索查询并为您计算机的筛选器警报查询中使用的组。</span><span class="sxs-lookup"><span data-stu-id="0cee1-194">Moreover, you can create a computer group by saving a search query and using that group as your computer filter in your alert query.</span></span> <span data-ttu-id="0cee1-195">有关详细信息，请参阅[计算机组日志分析中的日志搜索](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-computer-groups)。</span><span class="sxs-lookup"><span data-stu-id="0cee1-195">For more information, see [Computer groups in Log Analytics log searches](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-computer-groups).</span></span>

    <span data-ttu-id="0cee1-196">为每台计算机，错误查询将获取 RTCMEDSRV 服务启动最后的事件日志和服务停止。</span><span class="sxs-lookup"><span data-stu-id="0cee1-196">For each computer, the error query will get the last event log for both the RTCMEDSRV service start and service stop.</span></span> <span data-ttu-id="0cee1-197">它将返回一个日志的最后一个事件是否服务停止事件;它将返回 nothing 的最后一个事件是否服务开始事件。</span><span class="sxs-lookup"><span data-stu-id="0cee1-197">It will return one log if the last event is the service stop event; it will return nothing if the last event is the service start event.</span></span> <span data-ttu-id="0cee1-198">简而言之，查询将返回其 RTCMEDSRV 已停止的时间窗口中的服务器的列表。</span><span class="sxs-lookup"><span data-stu-id="0cee1-198">In short, the query would return a list of servers whose RTCMEDSRV is stopped in the time window.</span></span> 

- <span data-ttu-id="0cee1-199">重置通知的查询为：</span><span class="sxs-lookup"><span data-stu-id="0cee1-199">The query for the reset alert is:</span></span>

  ```
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003) | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    <span data-ttu-id="0cee1-200">重置查询执行的任务的错误查询完全相反。</span><span class="sxs-lookup"><span data-stu-id="0cee1-200">The reset query does exactly the opposite thing of the error query.</span></span> <span data-ttu-id="0cee1-201">对于每台计算机，它将返回一个的最后一个事件是该服务启动事件; 如果它将返回 nothing 的最后一个事件是否服务停止事件。</span><span class="sxs-lookup"><span data-stu-id="0cee1-201">For each computer, it will return one if the last event is the service start event; it will return nothing if the last event is the service stop event.</span></span>

  <span data-ttu-id="0cee1-202">**创建通知对:"太多个并发呼叫在中介服务器"和"并发呼叫回退到正常负载"**</span><span class="sxs-lookup"><span data-stu-id="0cee1-202">**Create an alert pair: " Too many concurrent calls in Mediation Servers" and "Concurrent calls fall back to normal load"**</span></span>

<span data-ttu-id="0cee1-203">若要创建此通知：</span><span class="sxs-lookup"><span data-stu-id="0cee1-203">To create this alert:</span></span>

- <span data-ttu-id="0cee1-204">错误警告的查询为：</span><span class="sxs-lookup"><span data-stu-id="0cee1-204">The query for the error alert is:</span></span>

  ```
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName == "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    <span data-ttu-id="0cee1-205">对于每台计算机，查询将获取入站的呼叫和之和出站呼叫的最后一个计数器这两个值。</span><span class="sxs-lookup"><span data-stu-id="0cee1-205">For each computer, the query will get the last counters for inbound call and outbound call and sum those two values.</span></span> <span data-ttu-id="0cee1-206">它将返回一个日志的总和值超过 500; 如果它将返回 nothing 如果它不存在。</span><span class="sxs-lookup"><span data-stu-id="0cee1-206">It will return one log if the sum value exceeds 500; it will return nothing if it doesn't.</span></span> <span data-ttu-id="0cee1-207">简而言之，查询将返回其并发呼叫具有太多时间窗口中的服务器的列表。</span><span class="sxs-lookup"><span data-stu-id="0cee1-207">In short, the query would return a list of servers whose concurrent calls are too many in the time window.</span></span>

- <span data-ttu-id="0cee1-208">重置通知的查询为：</span><span class="sxs-lookup"><span data-stu-id="0cee1-208">The query for the reset alert is:</span></span>

  ```
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==  "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500
  ```

    <span data-ttu-id="0cee1-209">重置查询执行的任务的错误查询完全相反。</span><span class="sxs-lookup"><span data-stu-id="0cee1-209">The reset query does exactly the opposite thing of the error query.</span></span> <span data-ttu-id="0cee1-210">对于每台计算机，查询将获取入站的呼叫和之和出站呼叫的最后一个计数器这两个值。</span><span class="sxs-lookup"><span data-stu-id="0cee1-210">For each computer, the query will get the last counters for inbound call and outbound call and sum those two values.</span></span> <span data-ttu-id="0cee1-211">它将返回一个日志的总和的值是否不超过 500;它将否则返回 nothing。</span><span class="sxs-lookup"><span data-stu-id="0cee1-211">It will return one log if the sum value is less than 500; it will return nothing otherwise.</span></span>

  <span data-ttu-id="0cee1-212">**创建通知:"CPU 使用率\>90 或 RTCMEDIARELAY 服务器中停止"警报**</span><span class="sxs-lookup"><span data-stu-id="0cee1-212">**Create an alert: "CPU usage \> 90 or RTCMEDIARELAY stopped in Servers" alert**</span></span>

<span data-ttu-id="0cee1-213">若要创建此通知，该查询在：</span><span class="sxs-lookup"><span data-stu-id="0cee1-213">To create this alert, the query is:</span></span>

```
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==  "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

<span data-ttu-id="0cee1-214">查询将从所有计算机并返回以往停止一个日志如果任一处理器使用率超过 90%或服务来获取所有处理器使用率计数器和服务停止事件。</span><span class="sxs-lookup"><span data-stu-id="0cee1-214">The query will get all processor usage counter and service stop event from all computers and return one log if either processor usage exceeds 90% or service is ever stopped.</span></span> 

## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a><span data-ttu-id="0cee1-215">分析日志分析资料库中的通知</span><span class="sxs-lookup"><span data-stu-id="0cee1-215">Analyze the alerts in your Log Analytics repository</span></span>

<span data-ttu-id="0cee1-216">若要分析您的库中的通知，请使用警报管理解决方案。</span><span class="sxs-lookup"><span data-stu-id="0cee1-216">To analyze the alerts in your repository, use the Alert Management solution.</span></span> <span data-ttu-id="0cee1-217">有关详细信息，请参阅[警报管理解决方案中操作管理套件 (OMS)](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-solution-alert-management)</span><span class="sxs-lookup"><span data-stu-id="0cee1-217">For more information, see [Alert Management solution in Operations Management Suite (OMS)](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-solution-alert-management)</span></span>

## <a name="recommended-minimal-monitoring-set"></a><span data-ttu-id="0cee1-218">建议的最小监控集</span><span class="sxs-lookup"><span data-stu-id="0cee1-218">Recommended minimal monitoring set</span></span>

<span data-ttu-id="0cee1-219">若要确定与事件日志和性能计数器的问题：</span><span class="sxs-lookup"><span data-stu-id="0cee1-219">To identify issues with event logs and performance counters:</span></span> 

- <span data-ttu-id="0cee1-220">**事件日志。**</span><span class="sxs-lookup"><span data-stu-id="0cee1-220">**Event logs.**</span></span> <span data-ttu-id="0cee1-221">以解决任何问题，应该有一组事件，以指示有问题，而另表明一切以及带有事件对。</span><span class="sxs-lookup"><span data-stu-id="0cee1-221">For any issue, there should be an events pair, with one set of events to indicate something is wrong, while the other indicates that everything is well.</span></span> <span data-ttu-id="0cee1-222">任何给定的时间段，它是最后一个记录的事件，指示是否异常情况的时间段内使用的内容。</span><span class="sxs-lookup"><span data-stu-id="0cee1-222">For any given time period, it is the last event recorded that will indicate whether something is amiss for that time period.</span></span>

- <span data-ttu-id="0cee1-223">**性能计数器。**</span><span class="sxs-lookup"><span data-stu-id="0cee1-223">**Performance Counters.**</span></span> <span data-ttu-id="0cee1-224">应受监视的计数器的阈值。</span><span class="sxs-lookup"><span data-stu-id="0cee1-224">There should be a threshold for the monitored counters.</span></span>

<span data-ttu-id="0cee1-225">下表列出了 Microsoft 建议通过列出停止和启动事件 Id 监控服务：</span><span class="sxs-lookup"><span data-stu-id="0cee1-225">The following table lists the services that Microsoft recommends monitoring by listing the stop and start event IDs:</span></span>

|<span data-ttu-id="0cee1-226">服务名称</span><span class="sxs-lookup"><span data-stu-id="0cee1-226">Service Name</span></span>  <br/> |<span data-ttu-id="0cee1-227">目标服务器角色</span><span class="sxs-lookup"><span data-stu-id="0cee1-227">Target Server Role</span></span>  <br/> |<span data-ttu-id="0cee1-228">停止事件 ID</span><span class="sxs-lookup"><span data-stu-id="0cee1-228">Stop Event ID</span></span>  <br/> |<span data-ttu-id="0cee1-229">启动事件 ID</span><span class="sxs-lookup"><span data-stu-id="0cee1-229">Start Event ID</span></span>  <br/> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0cee1-230">RTCMEDSRV</span><span class="sxs-lookup"><span data-stu-id="0cee1-230">RTCMEDSRV</span></span>  <br/> |<span data-ttu-id="0cee1-231">中介服务器</span><span class="sxs-lookup"><span data-stu-id="0cee1-231">Mediation Server</span></span>  <br/> |<span data-ttu-id="0cee1-232">25003</span><span class="sxs-lookup"><span data-stu-id="0cee1-232">25003</span></span>  <br/> |<span data-ttu-id="0cee1-233">25002</span><span class="sxs-lookup"><span data-stu-id="0cee1-233">25002</span></span>  <br/> |
|<span data-ttu-id="0cee1-234">RTCSRV</span><span class="sxs-lookup"><span data-stu-id="0cee1-234">RTCSRV</span></span>  <br/> |<span data-ttu-id="0cee1-235">边缘服务器</span><span class="sxs-lookup"><span data-stu-id="0cee1-235">Edge Server</span></span>  <br/> |<span data-ttu-id="0cee1-236">12289</span><span class="sxs-lookup"><span data-stu-id="0cee1-236">12289</span></span>  <br/> |<span data-ttu-id="0cee1-237">12288</span><span class="sxs-lookup"><span data-stu-id="0cee1-237">12288</span></span>  <br/> |
|<span data-ttu-id="0cee1-238">RTCMRAUTH</span><span class="sxs-lookup"><span data-stu-id="0cee1-238">RTCMRAUTH</span></span>  <br/> |<span data-ttu-id="0cee1-239">边缘服务器</span><span class="sxs-lookup"><span data-stu-id="0cee1-239">Edge Server</span></span>  <br/> |<span data-ttu-id="0cee1-240">19003</span><span class="sxs-lookup"><span data-stu-id="0cee1-240">19003</span></span>  <br/> |<span data-ttu-id="0cee1-241">19002</span><span class="sxs-lookup"><span data-stu-id="0cee1-241">19002</span></span>  <br/> |
|<span data-ttu-id="0cee1-242">RTCMEDIARELAY</span><span class="sxs-lookup"><span data-stu-id="0cee1-242">RTCMEDIARELAY</span></span>  <br/> |<span data-ttu-id="0cee1-243">边缘服务器</span><span class="sxs-lookup"><span data-stu-id="0cee1-243">Edge Server</span></span>  <br/> |<span data-ttu-id="0cee1-244">22003</span><span class="sxs-lookup"><span data-stu-id="0cee1-244">22003</span></span>  <br/> |<span data-ttu-id="0cee1-245">22002</span><span class="sxs-lookup"><span data-stu-id="0cee1-245">22002</span></span>  <br/> |

<span data-ttu-id="0cee1-246">下表列出了 Microsoft 建议监控网络问题：</span><span class="sxs-lookup"><span data-stu-id="0cee1-246">The following table lists the network issues that Microsoft recommends monitoring:</span></span>


| <span data-ttu-id="0cee1-247">监视器名称</span><span class="sxs-lookup"><span data-stu-id="0cee1-247">Monitor Name</span></span>  <br/>                                        | <span data-ttu-id="0cee1-248">目标服务器角色</span><span class="sxs-lookup"><span data-stu-id="0cee1-248">Target Server Role</span></span>  <br/> | <span data-ttu-id="0cee1-249">成功事件 ID 表达式</span><span class="sxs-lookup"><span data-stu-id="0cee1-249">Success Event ID expression</span></span>  <br/> | <span data-ttu-id="0cee1-250">错误事件 ID 表达式</span><span class="sxs-lookup"><span data-stu-id="0cee1-250">Error Event ID expression</span></span>  <br/> | <span data-ttu-id="0cee1-251">故障示例</span><span class="sxs-lookup"><span data-stu-id="0cee1-251">Failure example</span></span>  <br/> |
|:-----------------------------------------------------------|:--------------------------|:-----------------------------------|:---------------------------------|:-----------------------|
| <span data-ttu-id="0cee1-252">中介服务器与网关连接失败</span><span class="sxs-lookup"><span data-stu-id="0cee1-252">Mediation Server to gateway connectivity failure</span></span>  <br/>    | <span data-ttu-id="0cee1-253">中介服务器</span><span class="sxs-lookup"><span data-stu-id="0cee1-253">Mediation Server</span></span>  <br/>   | <span data-ttu-id="0cee1-254">25062</span><span class="sxs-lookup"><span data-stu-id="0cee1-254">25062</span></span>                              |                                  | <span data-ttu-id="0cee1-255">25002</span><span class="sxs-lookup"><span data-stu-id="0cee1-255">25002</span></span>  <br/>           |
| <span data-ttu-id="0cee1-256">中介服务器到网关呼叫完成故障</span><span class="sxs-lookup"><span data-stu-id="0cee1-256">Mediation Server to gateway call completion failure</span></span>  <br/> | <span data-ttu-id="0cee1-257">中介服务器</span><span class="sxs-lookup"><span data-stu-id="0cee1-257">Mediation Server</span></span>  <br/>   | <span data-ttu-id="0cee1-258">25064</span><span class="sxs-lookup"><span data-stu-id="0cee1-258">25064</span></span>                              |                                  | <span data-ttu-id="0cee1-259">25002</span><span class="sxs-lookup"><span data-stu-id="0cee1-259">25002</span></span>  <br/>           |
| <span data-ttu-id="0cee1-260">关键网络问题</span><span class="sxs-lookup"><span data-stu-id="0cee1-260">Critical network problems</span></span>  <br/>                           | <span data-ttu-id="0cee1-261">边缘服务器</span><span class="sxs-lookup"><span data-stu-id="0cee1-261">Edge Server</span></span>  <br/>        | <span data-ttu-id="0cee1-262">14353</span><span class="sxs-lookup"><span data-stu-id="0cee1-262">14353</span></span>                              |                                  | <span data-ttu-id="0cee1-263">12288</span><span class="sxs-lookup"><span data-stu-id="0cee1-263">12288</span></span>  <br/>           |

<span data-ttu-id="0cee1-264">下面列出了应受到监视的呼叫容量计数器。</span><span class="sxs-lookup"><span data-stu-id="0cee1-264">The following lists the call capacity counters that should be monitored.</span></span> <span data-ttu-id="0cee1-265">这些号码应，小于 500，对于云连接器 standard edition;小于 50 云连接器的最小 edition。</span><span class="sxs-lookup"><span data-stu-id="0cee1-265">These numbers should be less that 500 for Cloud Connector standard edition; less than 50 for Cloud Connector minimum edition.</span></span>

- <span data-ttu-id="0cee1-266">LS:MediationServer-入站 Calls(_Total)\-当前</span><span class="sxs-lookup"><span data-stu-id="0cee1-266">LS:MediationServer - Inbound Calls(_Total)\- Current</span></span> 

- <span data-ttu-id="0cee1-267">LS:MediationServer-出站 Calls(_Total)\-当前</span><span class="sxs-lookup"><span data-stu-id="0cee1-267">LS:MediationServer - Outbound Calls(_Total)\- Current</span></span> 

- <span data-ttu-id="0cee1-268">LS:MediationServer-入站 Calls(_Total)\-活动的媒体绕过呼叫</span><span class="sxs-lookup"><span data-stu-id="0cee1-268">LS:MediationServer - Inbound Calls(_Total)\- Active media bypass calls</span></span>

- <span data-ttu-id="0cee1-269">LS:MediationServer-出站 Calls(_Total)\-活动的媒体绕过呼叫</span><span class="sxs-lookup"><span data-stu-id="0cee1-269">LS:MediationServer - Outbound Calls(_Total)\- Active media bypass calls</span></span>

## <a name="see-also"></a><span data-ttu-id="0cee1-270">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0cee1-270">See also</span></span>

<span data-ttu-id="0cee1-271">有关使用 OMS 的详细信息，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="0cee1-271">For more information about working with OMS, see the following:</span></span>

- [<span data-ttu-id="0cee1-272">查找使用日志分析中的日志搜索的数据</span><span class="sxs-lookup"><span data-stu-id="0cee1-272">Find data using log searches in Log Analytics</span></span>](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-log-searches)

- [<span data-ttu-id="0cee1-273">Azure 日志分析语言参考</span><span class="sxs-lookup"><span data-stu-id="0cee1-273">Azure Log Analytics Language Reference</span></span>](https://docs.loganalytics.io/docs/Language-Reference)

- [<span data-ttu-id="0cee1-274">了解日志分析中的通知</span><span class="sxs-lookup"><span data-stu-id="0cee1-274">Understanding alerts in Log Analytics</span></span>](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-alerts)

- [<span data-ttu-id="0cee1-275">连接到 Azure 中的日志 Analytics service 的 Windows 计算机</span><span class="sxs-lookup"><span data-stu-id="0cee1-275">Connect Windows computers to the Log Analytics service in Azure</span></span>](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-windows-agents)


