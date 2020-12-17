---
title: Azure Sentinel 和 Microsoft Teams
author: MicrosoftHeidi
ms.author: tracyp
manager: dansimp
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: 为 IT 管理员提供的有关使用 Sentinel 来监控和搜寻 Teams 中可能出现的威胁的安全建议和经验。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4f13cdd1d62a31178f7aed922b3bc55b87cd59db
ms.sourcegitcommit: 380a96f1ed2cefb429286854f06546bdb28d7d74
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701230"
---
# <a name="azure-sentinel-and-microsoft-teams"></a><span data-ttu-id="d369b-103">Azure Sentinel 和 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d369b-103">Azure Sentinel and Microsoft Teams</span></span>

<span data-ttu-id="d369b-104">Teams 在 Microsoft 365 云中的通信和数据共享中发挥核心作用。</span><span class="sxs-lookup"><span data-stu-id="d369b-104">Teams serves a central role in both communication and data sharing in the Microsoft 365 Cloud.</span></span> <span data-ttu-id="d369b-105">由于 Teams 服务涉及云中的许多基础技术，因此它不仅可以在 *搜寻日志* 时从人工和自动化分析中受益，还可以 *实时监控会议*。</span><span class="sxs-lookup"><span data-stu-id="d369b-105">Because the Teams service touches on so many underlying technologies in the Cloud, it can benefit from human and automated analysis not only when it comes to *hunting in logs*, but also in *real-time monitoring of meetings*.</span></span> <span data-ttu-id="d369b-106">Azure Sentinel 可为管理员提供这些解决方案。</span><span class="sxs-lookup"><span data-stu-id="d369b-106">Azure Sentinel offers admins these solutions.</span></span>

> [!NOTE]
> <span data-ttu-id="d369b-107">需要复习有关 Azure Sentinel 的知识？</span><span class="sxs-lookup"><span data-stu-id="d369b-107">Need a refresher on Azure Sentinel?</span></span> <span data-ttu-id="d369b-108">[本文](https://docs.microsoft.com/azure/sentinel/overview)正好满足你的需求。</span><span class="sxs-lookup"><span data-stu-id="d369b-108">[This article](https://docs.microsoft.com/azure/sentinel/overview) is just the thing.</span></span>

## <a name="sentinel-and-microsoft-teams-activity-logs"></a><span data-ttu-id="d369b-109">Sentinel 和 Microsoft Teams 活动日志</span><span class="sxs-lookup"><span data-stu-id="d369b-109">Sentinel and Microsoft Teams Activity Logs</span></span>

<span data-ttu-id="d369b-110">本文重点介绍如何在 Azure Sentinel 中收集 Teams 活动日志。</span><span class="sxs-lookup"><span data-stu-id="d369b-110">This article focuses on collecting Teams activity logs in Azure Sentinel.</span></span> <span data-ttu-id="d369b-111">除了允许管理员将安全管理放在一个窗格（包括任何选定的第三方设备、Microsoft 威胁防护和其他 Microsoft 365 工作负载）下，Sentinel 工作簿和运行手册还可以使安全监控系统化。</span><span class="sxs-lookup"><span data-stu-id="d369b-111">Aside from allowing administrators to put security management under one pane of glass (including any selected 3rd party devices, Microsoft Threat Protection, and other Microsoft 365 Workloads), Sentinel workbooks, and runbooks can make security monitoring systematic.</span></span> <span data-ttu-id="d369b-112">在此流程中，最好先收集所需的日志进行分析。</span><span class="sxs-lookup"><span data-stu-id="d369b-112">A good first step in this process is collecting the needed logs for analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="d369b-113">可以在同一个 Azure Sentinel 实例中呈现多个 Microsoft 365 订阅。</span><span class="sxs-lookup"><span data-stu-id="d369b-113">More than one Microsoft 365 subscription can be surfaced in the same instance of Azure Sentinel.</span></span> <span data-ttu-id="d369b-114">这将允许[实时监控](https://docs.microsoft.com/azure/sentinel/livestream)以及在历史日志文件中搜寻威胁。</span><span class="sxs-lookup"><span data-stu-id="d369b-114">This will allow for [realtime monitoring](https://docs.microsoft.com/azure/sentinel/livestream) and hunting for threats in historical log file s.</span></span> <span data-ttu-id="d369b-115">管理员可以使用[跨资源查询](https://docs.microsoft.com/azure/azure-monitor/log-query/cross-workspace-query)在单个资源组内、跨资源组或在另一个订阅中进行搜寻。</span><span class="sxs-lookup"><span data-stu-id="d369b-115">Administrators will be able to hunt using [cross-resource queries](https://docs.microsoft.com/azure/azure-monitor/log-query/cross-workspace-query), that is within a single resource group, across resource groups, or in another subscription.</span></span>

## <a name="step-1-collect-teams-logs"></a><span data-ttu-id="d369b-116">步骤 1：收集 Teams 日志</span><span class="sxs-lookup"><span data-stu-id="d369b-116">Step 1: Collect Teams logs</span></span>

<span data-ttu-id="d369b-117">此分区具有三个部分：</span><span class="sxs-lookup"><span data-stu-id="d369b-117">This section has three parts:</span></span>

1. <span data-ttu-id="d369b-118">在 **Microsoft 365** (M365) 中启用审核日志。</span><span class="sxs-lookup"><span data-stu-id="d369b-118">Enabling Audit Logs in **Microsoft 365** (M365).</span></span>
2. <span data-ttu-id="d369b-119">在 **Microsoft Azure** 中注册应用，以允许对日志收集进行身份验证和授权。</span><span class="sxs-lookup"><span data-stu-id="d369b-119">Registering an App in **Microsoft Azure** to permit authentication and authorization for log collection.</span></span>
3. <span data-ttu-id="d369b-120">注册 API 订阅，允许在 M365 API 中通过 **PowerShell** 进行日志收集。</span><span class="sxs-lookup"><span data-stu-id="d369b-120">Registering the API subscription that will allow log collection via M365 API via **PowerShell**.</span></span>

### <a name="enable-audit-logs-in-m365"></a><span data-ttu-id="d369b-121">在 M365 中启用审核日志</span><span class="sxs-lookup"><span data-stu-id="d369b-121">Enable Audit logs in M365</span></span>

<span data-ttu-id="d369b-122">由于 Teams 通过 M365 记录活动，因此默认情况下不会收集审核日志。</span><span class="sxs-lookup"><span data-stu-id="d369b-122">Because Teams logs activity through M365, audit logs aren't collected by default.</span></span> <span data-ttu-id="d369b-123">通过[以下步骤](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide&viewFallbackFrom=o365-worldwide%C2%A0)启用此功能。</span><span class="sxs-lookup"><span data-stu-id="d369b-123">Turn on this feature via [these steps](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide&viewFallbackFrom=o365-worldwide%C2%A0).</span></span> <span data-ttu-id="d369b-124">Teams 数据在 M365 审核中根据 *Audit.General* 进行收集。</span><span class="sxs-lookup"><span data-stu-id="d369b-124">Teams data is collected in the M365 audit under *Audit.General*.</span></span>

### <a name="register-an-app-in-microsoft-azure-for-log-collection"></a><span data-ttu-id="d369b-125">在 Microsoft Azure 中注册应用以进行日志收集</span><span class="sxs-lookup"><span data-stu-id="d369b-125">Register an App in Microsoft Azure for log collection</span></span>

> [!TIP]
> <span data-ttu-id="d369b-126">开始之前，需要记录 **应用程序ID/客户端 ID** 以及 **租户 ID**，以便以后使用。</span><span class="sxs-lookup"><span data-stu-id="d369b-126">Before you begin, you will need to record you **Application ID / Client ID**, and your **Tenant ID** for later use.</span></span> <span data-ttu-id="d369b-127">在执行以下应用程序注册步骤时，务必捕获这些信息。</span><span class="sxs-lookup"><span data-stu-id="d369b-127">Be sure to capture them as you walk through app registration steps below.</span></span> <span data-ttu-id="d369b-128">你将看到这两个 ID。</span><span class="sxs-lookup"><span data-stu-id="d369b-128">You will see both IDs.</span></span>
>- <span data-ttu-id="d369b-129">创建应用后，单击快速启动侧栏上的“应用注册”> 查找新应用程序的显示名称 > 复制应用程序（客户端）ID。</span><span class="sxs-lookup"><span data-stu-id="d369b-129">After your app is created, click App Registration on the quick launch side-bar > Find your new app's display name > copy the Application (client) ID.</span></span>
>- <span data-ttu-id="d369b-130">单击快速启动侧栏上的“概述”> 复制目录（租户）ID。</span><span class="sxs-lookup"><span data-stu-id="d369b-130">Click Overview on the quick launch side-bar > copy the Directory (tenant) ID.</span></span>

<span data-ttu-id="d369b-131">对 Azure Active Directory (Azure AD) 应用进行身份验证和授权，以从 API 收集日志数据。</span><span class="sxs-lookup"><span data-stu-id="d369b-131">Authenticate and authorize an Azure Active Directory (Azure AD) app to collect log data from the API.</span></span>

1. <span data-ttu-id="d369b-132">在 Azure 门户中导航到 *Azure AD* 边栏选项卡。</span><span class="sxs-lookup"><span data-stu-id="d369b-132">Navigate to your *Azure AD* blade in the Azure portal.</span></span>
2. <span data-ttu-id="d369b-133">单击快速启动侧栏中的“*应用注册*”。</span><span class="sxs-lookup"><span data-stu-id="d369b-133">Click on *App registrations* in the quick launch side-bar.</span></span>
3. <span data-ttu-id="d369b-134">选择“*新注册*”。</span><span class="sxs-lookup"><span data-stu-id="d369b-134">Select *New registration*.</span></span>
4. <span data-ttu-id="d369b-135">为你的 Teams 日志收集应用命名，然后单击“*注册*”。</span><span class="sxs-lookup"><span data-stu-id="d369b-135">Name your Teams log collecting app and click *Register*.</span></span>
5. <span data-ttu-id="d369b-136">沿以下路径依次单击：“*API权限*” > “*添加权限*” > “*Office 365 管理 API*” > “*应用程序权限*”。</span><span class="sxs-lookup"><span data-stu-id="d369b-136">Click along this path: *API Permissions* > *Add a permission* > *Office 365 Management APIs* > *Application permissions*.</span></span>
6. <span data-ttu-id="d369b-137">展开活动源，然后勾选 *ActivityFeed.Read*。</span><span class="sxs-lookup"><span data-stu-id="d369b-137">Expand Activity Feed and check *ActivityFeed.Read*.</span></span>
7. <span data-ttu-id="d369b-138">在此处选择“*获得管理员同意*”。</span><span class="sxs-lookup"><span data-stu-id="d369b-138">Choose *Grand admin consent* here.</span></span> <span data-ttu-id="d369b-139">当系统提示询问这是否是你的本意时，单击“是”。</span><span class="sxs-lookup"><span data-stu-id="d369b-139">Click Yes when prompted asking if you mean it.</span></span>
8. <span data-ttu-id="d369b-140">单击侧栏的“*证书和密码*”>“*新客户端密码*”。</span><span class="sxs-lookup"><span data-stu-id="d369b-140">Click *Certificates and Secrets* in the side-bar> *New client secret* button.</span></span>
9. <span data-ttu-id="d369b-141">在“新客户端密码”窗口上，输入对新客户端密码的描述，确保为“过期”选择“永不”，然后单击“*添加*”。</span><span class="sxs-lookup"><span data-stu-id="d369b-141">On the New client secret window, enter a description for the new Client Secret, make sure you choose 'Never' for Expiration, and click *Add*.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d369b-142">将新的客户端密码复制到新创建的应用名称下的密码管理器条目中，这一点很 **重要**。</span><span class="sxs-lookup"><span data-stu-id="d369b-142">It's **critical** to copy the new client secret into a password manager entry that goes under the name of the newly created app.</span></span> <span data-ttu-id="d369b-143">关闭 Azure 边栏选项卡（*边栏选项卡* 是 Azure 窗口术语）后，将无法返回查看此密码。</span><span class="sxs-lookup"><span data-stu-id="d369b-143">You won't be able to get back to look at this secret after the closing out of the Azure blade (*blade* being the Azure term for window).</span></span>

### <a name="register-the-api-with-powershell-to-collect-teams-logs"></a><span data-ttu-id="d369b-144">在 PowerShell 中注册 API 以收集 Teams 日志</span><span class="sxs-lookup"><span data-stu-id="d369b-144">Register the API with PowerShell to collect Teams logs</span></span>

<span data-ttu-id="d369b-145">设置的最后一步是收集并注册 API 订阅，以便你能收集日志数据。</span><span class="sxs-lookup"><span data-stu-id="d369b-145">The final step in setup is to collect and register the API subscription so that you can collect your log data.</span></span> <span data-ttu-id="d369b-146">此操作通过对 M365 管理活动 API 的 PowerShell REST 调用来完成。</span><span class="sxs-lookup"><span data-stu-id="d369b-146">This is done via PowerShell REST calls to the M365 Management Activity API.</span></span>

<span data-ttu-id="d369b-147">准备好在下面的 PowerShell cmdlet 中提供 **应用程序（客户端）ID**、新的 **客户端密码**、**M365 的 URL 域** 和 **目录（租户）ID** 值。</span><span class="sxs-lookup"><span data-stu-id="d369b-147">Be ready to supply **Application (client) ID**, the new **Client Secret**, your **URL domain for M365**, and **Directory (tenant) ID** values in the PowerShell cmdlet below.</span></span>

```PowerShell
$ClientID = "<Application (client) ID>"  
$ClientSecret = "<Client secret>"  
$loginURL = "https://login.microsoftonline.com/"  
$tenantdomain = "<domain>.onmicrosoft.com"  

$TenantGUID = "<Directory (tenant) ID>"  
$resource = "https://manage.office.com"  
$body = @{grant_type="client_credentials";resource=$resource;client_id=$ClientID;client_secret=$ClientSecret}
$oauth = Invoke-RestMethod -Method Post -Uri $loginURL/$tenantdomain/oauth2/token?api-version=1.0 -Body $body  
$headerParams = @{'Authorization'="$($oauth.token_type) $($oauth.access_token)"}
$publisher = New-Guid
Invoke-WebRequest -Method Post -Headers $headerParams -Uri "https://manage.office.com/api/v1.0/$tenantGuid/activity/feed/subscriptions/start?contentType=Audit.General&PublisherIdentifier=$Publisher"
```

## <a name="step-2-deploy-a-sentinel-playbook-to-ingest-the-teams-logs"></a><span data-ttu-id="d369b-148">步骤 2：部署 Sentinel Playbook 以获取 Teams 日志</span><span class="sxs-lookup"><span data-stu-id="d369b-148">Step 2: Deploy a Sentinel Playbook to ingest the Teams logs</span></span>

<span data-ttu-id="d369b-149">Azure Sentinel Playbook（也称为逻辑应用）将允许 Azure 获取你收集的 Teams 数据。</span><span class="sxs-lookup"><span data-stu-id="d369b-149">Azure Sentinel Playbooks (also called Logic Apps) will allow Azure to ingest your collected Teams data.</span></span> <span data-ttu-id="d369b-150">逻辑应用将查询 Office 365 以查找其写入 Azure Sentinel 工作区的审核数据。</span><span class="sxs-lookup"><span data-stu-id="d369b-150">The Logic App queries Office 365 to find the audit data it writes into the Azure Sentinel workspace.</span></span>

<span data-ttu-id="d369b-151">使用[此](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) ARM 模板部署你的 Sentinel Playbook。</span><span class="sxs-lookup"><span data-stu-id="d369b-151">Use [this](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) ARM template to deploy your Sentinel Playbook.</span></span>

<span data-ttu-id="d369b-152">注意事项：</span><span class="sxs-lookup"><span data-stu-id="d369b-152">Things to remember:</span></span>

1. <span data-ttu-id="d369b-153">你将需要遍历 ARM 模板并将某些值替换为适合自身环境的值。</span><span class="sxs-lookup"><span data-stu-id="d369b-153">You will need to walk through the ARM template and replace certain of the values with values appropriate for your own environment.</span></span>
2. <span data-ttu-id="d369b-154">你将需要在获取日志和查看 Azure Sentinel 中的结果之间留出时间。</span><span class="sxs-lookup"><span data-stu-id="d369b-154">You will need to allow time between the ingestion of logs and looking at the results in Azure Sentinel.</span></span>

   <span data-ttu-id="d369b-155">等待 5 到 10 分钟，明白一点，如果过去 5 分钟内没有数据，你将看到一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="d369b-155">Wait for 5 to 10 minutes, understanding that if there is no data within the past 5 minutes you will see an error message.</span></span> <span data-ttu-id="d369b-156">检查审核日志，请记住，由于 Teams 信息位于 Audit.General 事件中（该事件比 Teams 日志收集的信息更多），因此结果应在使用中的系统上显示 5 到 10 分钟。</span><span class="sxs-lookup"><span data-stu-id="d369b-156">Check Audit logs and keep in mind that because Teams information is in the Audit.General events, which collects more than Teams logs, results should appear within 5 to 10 minutes on systems that are in use.</span></span> <span data-ttu-id="d369b-157">如果使用文本环境，请确保使用 Teams 来生成日志记录。</span><span class="sxs-lookup"><span data-stu-id="d369b-157">If using a text environment, be certain to use Teams in order to generate logging.</span></span>

![显示逻辑应用类的图形。](media/tracyp-teams-sentinel-logic-app.png#thumbnail)

 <p><details><summary> <span data-ttu-id="d369b-159">图形操作说明：</span><span class="sxs-lookup"><span data-stu-id="d369b-159">Explanation of actions in the graphic:</span></span> 
  </summary>

  <span data-ttu-id="d369b-160">•“定期”是一种逻辑应用触发器，它指示工作流每小时运行一次。</span><span class="sxs-lookup"><span data-stu-id="d369b-160">• Recurrence is the Logic App Trigger that tells the workflow to run every hour.</span></span>
  <p>
<span data-ttu-id="d369b-161">•“当前时间”操作是一种非常基本的操作，仅获取当前时间。</span><span class="sxs-lookup"><span data-stu-id="d369b-161">• The Current Time action is very basic and just gets the current time.</span></span>
  <p>
<span data-ttu-id="d369b-162">•“初始化变量”将创建名为 NextPage 的变量，并将其设置为 1。</span><span class="sxs-lookup"><span data-stu-id="d369b-162">• Initialize Variable creates a variable called NextPage and sets it to 1.</span></span> <span data-ttu-id="d369b-163">稍后将使用它来处理 O365 API 中的分页。</span><span class="sxs-lookup"><span data-stu-id="d369b-163">This will be used later in order to handle pagination from the O365 API.</span></span>
  <p>
<span data-ttu-id="d369b-164">•“初始化变量 2”会创建一个名为“开始时间”的空变量。</span><span class="sxs-lookup"><span data-stu-id="d369b-164">• Initialize Variable 2 creates an empty variable called Start Time.</span></span>
  <p>
<span data-ttu-id="d369b-165">• 运行查询和列表结果是一个 Azure Monitor 操作，它将查询从逻辑应用中输入的最后一个 O365 日志的工作区。</span><span class="sxs-lookup"><span data-stu-id="d369b-165">• Run Query and list results is an Azure Monitor action that will query the workspace for the last O365 log that was entered from the Logic App.</span></span>
  <p>
<span data-ttu-id="d369b-166">•“条件 4”用于检查运行查询和列表结果查询是否返回了任何数据。</span><span class="sxs-lookup"><span data-stu-id="d369b-166">• Condition 4 is used to check whether the Run Query and list results query returned any data.</span></span> <span data-ttu-id="d369b-167">执行此操作可检查这是否是首次使用逻辑应用。</span><span class="sxs-lookup"><span data-stu-id="d369b-167">This is done to check if this is the very first time the Logic App has been used.</span></span> <span data-ttu-id="d369b-168">如果未返回任何数据，StartTime 变量将设置为“现在 – 24 小时”。</span><span class="sxs-lookup"><span data-stu-id="d369b-168">If no data is returned, StartTime variable is set to Now – 24 hours.</span></span> <span data-ttu-id="d369b-169">如果返回了数据，StartTime 将设置为最后一条记录 TimeGenerated。</span><span class="sxs-lookup"><span data-stu-id="d369b-169">If data is returned, StartTime is set to the last record TimeGenerated.</span></span> <span data-ttu-id="d369b-170">这样做是为了使查询可以获取针对 O365 API 的轮询中从最后一个条目到现在的数据；或者如果是第一次运行，则可以获取最近 24 小时内的数据。</span><span class="sxs-lookup"><span data-stu-id="d369b-170">This is done so that the query can get data from the last entry till now in the poll against the O365 API, or in the last 24 hours if this is the first run.</span></span>
  <p>
<span data-ttu-id="d369b-171">•“初始化变量 3”会创建一个名为 AvailableUri 的变量。</span><span class="sxs-lookup"><span data-stu-id="d369b-171">• Initialize Variable 3 creates a variable called AvailableUri.</span></span> <span data-ttu-id="d369b-172">这是一个字符串，使用 StartTime 和 CurrentTime 分别作为开始时间和结束时间来构建 URL。</span><span class="sxs-lookup"><span data-stu-id="d369b-172">This is a string with the URL built using the StartTime and CurrentTime as start and end times, respectively.</span></span>
  <p>
<span data-ttu-id="d369b-173">• Until 条件是一个循环，允许逻辑应用保持轮询 API 以查看是否还有更多数据（分页）。</span><span class="sxs-lookup"><span data-stu-id="d369b-173">• The Until condition is a loop that allows the logic app to keep polling the API to see if there is more data (pagination).</span></span> <span data-ttu-id="d369b-174">只要 NextPage 变量为 1，循环就将继续。</span><span class="sxs-lookup"><span data-stu-id="d369b-174">As long as NextPage variable is 1 the loop will continue.</span></span> <span data-ttu-id="d369b-175">之后如果没有更多页面可供检索，此变量将更新。</span><span class="sxs-lookup"><span data-stu-id="d369b-175">Later this variable will be updated if there are no more pages left to retrieve.</span></span>
  <p>
<span data-ttu-id="d369b-176">• 在 Until 循环中，第一个 HTTP 步骤连接到 AvailableURI。</span><span class="sxs-lookup"><span data-stu-id="d369b-176">• Inside the Until loop, the first HTTP step Connects to the AvailableURI.</span></span> <span data-ttu-id="d369b-177">此 URI 将返回可用内容和每个内容 URI 的列表。</span><span class="sxs-lookup"><span data-stu-id="d369b-177">This URI returns a list of available content and each contents URI.</span></span> <span data-ttu-id="d369b-178">有关其工作原理的更多信息，请访问此 URL：https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#list-available-content。</span><span class="sxs-lookup"><span data-stu-id="d369b-178">There's more on how this works at this URL: https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#list-available-content.</span></span>
  <p>
<span data-ttu-id="d369b-179">• 接下来，运行检查以确保返回数据。</span><span class="sxs-lookup"><span data-stu-id="d369b-179">• Next a check is run to make sure data is returned.</span></span> <span data-ttu-id="d369b-180">该条件将检查正文的长度是否为 0。</span><span class="sxs-lookup"><span data-stu-id="d369b-180">The Condition checks if the length of the body is 0.</span></span> <span data-ttu-id="d369b-181">如果是，则表示没有数据可写入日志分析。</span><span class="sxs-lookup"><span data-stu-id="d369b-181">If so there is no data to write to Log Analytics.</span></span> <span data-ttu-id="d369b-182">如果值大于 0，则表示有要处理的数据。</span><span class="sxs-lookup"><span data-stu-id="d369b-182">If the value is greater than 0, there is data to process.</span></span>
  <p>
<span data-ttu-id="d369b-183">• 如果检测到数据，必须随后对其进行处理。</span><span class="sxs-lookup"><span data-stu-id="d369b-183">• If data is detected, it must next be processed.</span></span> <span data-ttu-id="d369b-184">分析 JSON 定义返回数据的架构。</span><span class="sxs-lookup"><span data-stu-id="d369b-184">Parse JSON defines a schema of the returned data.</span></span> <span data-ttu-id="d369b-185">这使逻辑应用能够在后续步骤中将分析数据用作动态内容。</span><span class="sxs-lookup"><span data-stu-id="d369b-185">This allows logic apps to use the parsed data as Dynamic content in later steps.</span></span>
  <p>
<span data-ttu-id="d369b-186">• 由于返回的可用数据列表是一个数组，因此，“全部应用”操作用于循环读取可用内容列表。</span><span class="sxs-lookup"><span data-stu-id="d369b-186">• Since the returned list of available data is an Array, a For Each action is used to loop through the list of available content.</span></span>
  <p>
<span data-ttu-id="d369b-187">• 下一步是抓取内容。</span><span class="sxs-lookup"><span data-stu-id="d369b-187">• Next is grabbing the content.</span></span>  <span data-ttu-id="d369b-188">再次使用 HTTP 获取 contentUri（从分析 JSON 创建的动态属性），即要检索的数据的 URL。</span><span class="sxs-lookup"><span data-stu-id="d369b-188">HTTP is used again to get the contentUri (a dynamic property created from Parse JSON), which is the URL of the data to retrieve.</span></span>
  <p>
<span data-ttu-id="d369b-189">• 分析 JSON 还用于分析返回的数据。</span><span class="sxs-lookup"><span data-stu-id="d369b-189">• Parse JSON is also used to parse the returned data.</span></span> <span data-ttu-id="d369b-190">可在此 URL 中找到一些示例内容：https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#list-available-content。</span><span class="sxs-lookup"><span data-stu-id="d369b-190">You can find some sample content at this URL: https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#list-available-content.</span></span>
  <p>
<span data-ttu-id="d369b-191">• 返回的数据也是一个数组。</span><span class="sxs-lookup"><span data-stu-id="d369b-191">• The data returned is also an array.</span></span> <span data-ttu-id="d369b-192">也可在此处使用“全部应用”循环。</span><span class="sxs-lookup"><span data-stu-id="d369b-192">A For Each loop can be used here as well.</span></span> <span data-ttu-id="d369b-193">在此循环中，工作流将提取当前数据项，并使用“发送数据”操作将数据写入日志分析。</span><span class="sxs-lookup"><span data-stu-id="d369b-193">In this loop, the workflow takes the current item of data and uses the Send Data action to write the data to Log Analytics.</span></span>
  <p>
<span data-ttu-id="d369b-194">• 由于可能存在多个页面的可用内容，因此一个条件将检查 NextPageUri 是否不为 NULL。</span><span class="sxs-lookup"><span data-stu-id="d369b-194">• Since there may be multiple pages of available content, a condition checks if the NextPageUri is not NULL.</span></span> <span data-ttu-id="d369b-195">如果为 NULL 或为空，NextPage 将设置为 0，这将结束 Until 循环。</span><span class="sxs-lookup"><span data-stu-id="d369b-195">If it is NULL, or empty, NextPage is set to 0, which ends the Until loop.</span></span> <span data-ttu-id="d369b-196">如果它包含 URL，AvaibleUri 变量将更新为该 URL。</span><span class="sxs-lookup"><span data-stu-id="d369b-196">If it contains a URL, the AvaibleUri variable is updated to that URL.</span></span> <span data-ttu-id="d369b-197">这样，下次运行 Until 循环时将使用下个可用的 URL，而不是起始 URL。</span><span class="sxs-lookup"><span data-stu-id="d369b-197">This way, the next run of the Until loop uses a next available URL, and not the starting URL.</span></span>

  </details>

> [!TIP]
> <span data-ttu-id="d369b-198">你可以选择改用 *Azure 函数* 来获取这些日志，如果执行此操作，有关如何部署的信息将显示在 [此处](https://github.com/Azure/Azure-Sentinel/tree/master/DataConnectors/O365%20Data)或 [此处](https://github.com/Azure/Azure-Sentinel/tree/master/DataConnectors/O365%20DataCSharp)，具体取决于你的偏好。</span><span class="sxs-lookup"><span data-stu-id="d369b-198">You may choose to use an *Azure Function* to ingest those logs, instead, and if you do, the information on how to deploy is [here](https://github.com/Azure/Azure-Sentinel/tree/master/DataConnectors/O365%20Data), or [here](https://github.com/Azure/Azure-Sentinel/tree/master/DataConnectors/O365%20DataCSharp), depending on your preference.</span></span>

<span data-ttu-id="d369b-199">在连接器（选择上述任一选项）运行时，应该会在 Azure Sentinel 工作区中看到一个名为 O365API_CL 的自定义表。</span><span class="sxs-lookup"><span data-stu-id="d369b-199">With the connector (whichever of the options above you chose) running, you should see a custom table called O365API_CL in the Azure Sentinel workspace.</span></span> <span data-ttu-id="d369b-200">其中将包括你的 Teams 日志。</span><span class="sxs-lookup"><span data-stu-id="d369b-200">This will house your Teams logs.</span></span>

## <a name="step-3-use-sentinel-to-monitor-microsoft-teams"></a><span data-ttu-id="d369b-201">步骤 3：使用 Sentinel 监控 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d369b-201">Step 3: Use Sentinel to monitor Microsoft Teams</span></span>

<span data-ttu-id="d369b-202">身份是要在 Microsoft Teams 中监控的重要攻击媒介。</span><span class="sxs-lookup"><span data-stu-id="d369b-202">Identity is an important attack vector to monitor when it comes to Microsoft Teams.</span></span> <span data-ttu-id="d369b-203">由于 Azure Active Directory (Azure AD) 是 Microsoft 365 目录（包括 Teams）的基础，因此收集和搜寻有关身份验证的 Azure AD 日志中的威胁将有助于捕获关于身份的可疑行为。</span><span class="sxs-lookup"><span data-stu-id="d369b-203">Because Azure Active Directory (Azure AD) is the underpinning of Microsoft 365's directory, including Teams, collecting and hunting for threats in Azure AD logs around authentication will be useful in capturing suspicious behavior around identity.</span></span> <span data-ttu-id="d369b-204">你可以使用内置连接器将 Azure AD 数据拉入 Azure Sentinel，并使用这些[检测](https://github.com/Azure/Azure-Sentinel/tree/master/Detections/SigninLogs)和[搜寻](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/SigninLogs)查询来查找问题。</span><span class="sxs-lookup"><span data-stu-id="d369b-204">You can use the built-in connector to pull Azure AD data into Azure Sentinel, and use these [detection](https://github.com/Azure/Azure-Sentinel/tree/master/Detections/SigninLogs) and [hunting](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/SigninLogs) queries to look for problems.</span></span>

<span data-ttu-id="d369b-205">对于特定于 Microsoft Teams 的攻击，例如对数据的威胁，Azure Sentinel 还有监控和追查数据的手段。</span><span class="sxs-lookup"><span data-stu-id="d369b-205">Regarding attacks specific to Microsoft Teams, threats to data, for example, Azure Sentinel also has means to monitor for them and hunt them down.</span></span>

### <a name="create-a-parser-for-your-data"></a><span data-ttu-id="d369b-206">为数据创建分析器</span><span class="sxs-lookup"><span data-stu-id="d369b-206">Create a parser for your data</span></span>

<span data-ttu-id="d369b-207">为了理解收集的大量数据，首先要通过分析使其具有意义。</span><span class="sxs-lookup"><span data-stu-id="d369b-207">The first thing to do in order to make sense of the large set of collected data is to give it meaning by parsing it.</span></span> <span data-ttu-id="d369b-208">此操作可以通过 Kusto 查询语言 (KQL) 函数完成，该函数使数据更易于使用。</span><span class="sxs-lookup"><span data-stu-id="d369b-208">This is done with a Kusto Query Language (KQL) Function that makes the data easier to use.</span></span>

> [!NOTE]
> <span data-ttu-id="d369b-209">KQL 函数是保存为名为“函数”的数据类型的 KQL 查询。</span><span class="sxs-lookup"><span data-stu-id="d369b-209">KQL functions are KQL queries saved as a data-type called 'function'.</span></span> <span data-ttu-id="d369b-210">KQL 函数有一个别名，可在 Sentinel 的查询框中输入别名来快速重新运行查询。</span><span class="sxs-lookup"><span data-stu-id="d369b-210">KQL functions have an alias that can be entered into the query box in Sentinel to quickly run the query again.</span></span> <span data-ttu-id="d369b-211">有关 KQL 函数以及如何构建解析器函数的更多信息，请阅读[本技术社区文章](https://techcommunity.microsoft.com/t5/azure-sentinel/using-kql-functions-to-speed-up-analysis-in-azure-sentinel/ba-p/712381)。</span><span class="sxs-lookup"><span data-stu-id="d369b-211">For more about KQL functions and how to build a parser function, read [this Tech Community article](https://techcommunity.microsoft.com/t5/azure-sentinel/using-kql-functions-to-speed-up-analysis-in-azure-sentinel/ba-p/712381).</span></span>
 
 <span data-ttu-id="d369b-212">下面的解析器是一个可自定义的示例，旨在选择与 *Teams* 相关的 Office 365 管理 API 字段的子集。</span><span class="sxs-lookup"><span data-stu-id="d369b-212">The parser below is a customizable example aimed at selecting a subset of the Office 365 Management API fields relevant to *Teams*.</span></span> <span data-ttu-id="d369b-213">此外还有一个建议的分析器 [GitHub ](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt)，但可以下面的解析器可以针对不同的需求和偏好进行修改。</span><span class="sxs-lookup"><span data-stu-id="d369b-213">There is also a suggested parser [GitHub](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt), but the parser below can be modified to fit different needs and preferences.</span></span>

```kusto
O365API_CL
| where Workload_s =~ "MicrosoftTeams"
| project TimeGenerated,
          Workload=Workload_s,
          Operation=Operation_s,
          TeamName=columnifexists('TeamName_s', ""),
          UserId=columnifexists('UserId_s', ""),
          AddOnName=columnifexists('AddOnName_s', AddOnGuid_g),
          Members=columnifexists('Members_s', ""),
          Settings=iif(Operation_s contains "Setting", pack("Name", columnifexists('Name_s', ""), "Old Value", columnifexists('OldValue_s', ""), "New Value", columnifexists('NewValue_s', "")),""),
          Details=pack("Id", columnifexists('Id_g', ""),  "OrganizationId", columnifexists('OrganizationId_g', ""), "UserType", columnifexists('UserType_d', ""), "UserKey", columnifexists('UserKey_g', ""), "TeamGuid", columnifexists('TeamGuid_s', "")) 
```
 <span data-ttu-id="d369b-214">将分析器另存为别名为 TeamsData 的 KQL 函数。</span><span class="sxs-lookup"><span data-stu-id="d369b-214">Save the parser as a KQL function, with an alias of TeamsData.</span></span> <span data-ttu-id="d369b-215">它将用于后续查询。</span><span class="sxs-lookup"><span data-stu-id="d369b-215">It will be used for the queries to follow.</span></span> <span data-ttu-id="d369b-216">可在此[技术社区文章](https://techcommunity.microsoft.com/t5/azure-sentinel/using-kql-functions-to-speed-up-analysis-in-azure-sentinel/ba-p/712381)中找到有关配置和使用 KQL 函数作为分析器的详细信息。</span><span class="sxs-lookup"><span data-stu-id="d369b-216">Details on configuring and using a KQL function as a parser can be found in this [Tech Community article](https://techcommunity.microsoft.com/t5/azure-sentinel/using-kql-functions-to-speed-up-analysis-in-azure-sentinel/ba-p/712381).</span></span>

## <a name="helpful-hunting-kql-queries"></a><span data-ttu-id="d369b-217">有用的搜寻 KQL 查询</span><span class="sxs-lookup"><span data-stu-id="d369b-217">Helpful hunting KQL queries</span></span>

<span data-ttu-id="d369b-218">可以使用这些查询来让自己熟悉 Teams 数据和 Teams 环境。</span><span class="sxs-lookup"><span data-stu-id="d369b-218">Use these queries to familiarize yourself with your Teams data and Teams environment.</span></span> <span data-ttu-id="d369b-219">要识别可疑活动，最好先了解环境的外观和行为。</span><span class="sxs-lookup"><span data-stu-id="d369b-219">Knowing how the environment should look and behave is a good first step in recognizing suspicious activity.</span></span> <span data-ttu-id="d369b-220">从那里，你可以分支到威胁搜寻。</span><span class="sxs-lookup"><span data-stu-id="d369b-220">From there, you can branch out into threat hunting.</span></span>

#### <a name="federated-external-users-query"></a><span data-ttu-id="d369b-221">联合外部用户查询</span><span class="sxs-lookup"><span data-stu-id="d369b-221">Federated external users query</span></span>

<span data-ttu-id="d369b-222">获取具有联合外部用户的 Teams 网站的列表。</span><span class="sxs-lookup"><span data-stu-id="d369b-222">Get the list of Teams sites that have federated external users.</span></span> <span data-ttu-id="d369b-223">这些用户将具有 *不* 归你的组织拥有的域名/UPN 后缀。</span><span class="sxs-lookup"><span data-stu-id="d369b-223">These users will have a domain name / UPN suffix that *isn't* owned by your organization.</span></span> <span data-ttu-id="d369b-224">在此示例查询中，组织拥有 contoso.com。</span><span class="sxs-lookup"><span data-stu-id="d369b-224">In this example query, the organization owns contoso.com.</span></span>

```kusto
TeamsData
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberAdded"
| extend UPN = tostring(parse_json(Members)[0].Upn)
| where UPN !endswith "contoso.com"
| where parse_json(Members)[0].Role == 3
| project TeamName, Operation, UserId, Members, UPN
```

> [!TIP]
> <span data-ttu-id="d369b-225">若要了解有关 Teams 中外部和来宾访问类型的更多信息，请参阅 [本文](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations)或 [Teams 安全指南](https://docs.microsoft.com/microsoftteams/teams-security-guide)中的 *参与者类型* 部分。</span><span class="sxs-lookup"><span data-stu-id="d369b-225">To learn more about External and Guest access types in Teams see [this article](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations), or the *Participant Types* section in the [Teams Security Guide](https://docs.microsoft.com/microsoftteams/teams-security-guide).</span></span>

#### <a name="who-recently-joined--whose-role-changed"></a><span data-ttu-id="d369b-226">最近加入/角色已更改的人员</span><span class="sxs-lookup"><span data-stu-id="d369b-226">Who recently joined / Whose role changed</span></span>

<span data-ttu-id="d369b-227">查询特定用户以了解他们是否是在最近 7 天或一周内添加到 Teams 频道的：</span><span class="sxs-lookup"><span data-stu-id="d369b-227">Query a specific user to check if they were added to a Teams channel in the last 7 days, or within a week:</span></span>

```kusto
TeamsData
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberAdded"
| where Members contains "UserName"
```

<span data-ttu-id="d369b-228">用户针对某个团队的角色是否在最近 7 天内进行了更改：</span><span class="sxs-lookup"><span data-stu-id="d369b-228">Was a user's role changed for a Team in the last 7 days:</span></span>

```kusto
TeamsData
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberRoleChanged"
| where Members contains "Role" and Members contains "1"
```

#### <a name="external-users-from-unknown-or-new-organizations"></a><span data-ttu-id="d369b-229">来自未知组织或新组织的外部用户</span><span class="sxs-lookup"><span data-stu-id="d369b-229">External users from unknown or new organizations</span></span>

<span data-ttu-id="d369b-230">在 Teams 中，可将外部用户添加到你的环境或频道。</span><span class="sxs-lookup"><span data-stu-id="d369b-230">In Teams, you can add external users to your environment or channels.</span></span> <span data-ttu-id="d369b-231">组织通常具有数量有限的关键合作伙伴关系，并从这些合作伙伴中添加用户。</span><span class="sxs-lookup"><span data-stu-id="d369b-231">Organizations often have a limited number of key partnerships and add users from among these partners.</span></span> <span data-ttu-id="d369b-232">此 KQL 会查看添加到团队的外部用户，这些用户来自之前没有见过或添加过的组织。</span><span class="sxs-lookup"><span data-stu-id="d369b-232">This KQL looks at external users added to teams who come from organizations that haven't been seen or added before.</span></span>

```kusto
// If you have more than 14 days worth of Teams data change this value 
let data_date = 14d; 
// If you want to look at users further back than the last day change this value 
let lookback_data = 1d; 
let known_orgs = ( 
TeamsData  
| where TimeGenerated > ago(data_date) 
| where Operation =~ "MemberAdded" or Operation =~ "TeamsSessionStarted" 
// Extract the correct UPN and parse our external organization domain 
| extend UPN = iif(Operation == "MemberAdded", tostring(parse_json(Members)[0].UPN), UserId) 
| extend Organization = tostring(split(split(UPN, "_")[1], "#")[0]) 
| where isnotempty(Organization) 
| summarize by Organization); 
TeamsData  
| where TimeGenerated > ago(lookback_data) 
| where Operation =~ "MemberAdded" 
| extend UPN = tostring(parse_json(Members)[0].UPN) 
| extend Organization = tostring(split(split(UPN, "_")[1], "#")[0]) 
| where isnotempty(Organization) 
| where Organization !in (known_orgs) 
// Uncomment the following line to map query entities is you plan to use this as a detection query 
//| extend timestamp = TimeGenerated, AccountCustomEntity = UPN 
```

#### <a name="external-users-who-were-added-and-then-removed"></a><span data-ttu-id="d369b-233">添加后又删除的外部用户</span><span class="sxs-lookup"><span data-stu-id="d369b-233">External users who were added and then removed</span></span>

<span data-ttu-id="d369b-234">具有一定程度的现有访问权限的攻击者可能会向 Teams 添加一个新的外部帐户，以便访问和窃取数据。</span><span class="sxs-lookup"><span data-stu-id="d369b-234">Attackers with some level of existing access may add a new external account to Teams to access and exfiltrate data.</span></span> <span data-ttu-id="d369b-235">他们还可能会快速删除该用户，以隐藏他们进行了访问的事实。</span><span class="sxs-lookup"><span data-stu-id="d369b-235">They may also quickly remove that user to hide that they made access.</span></span> <span data-ttu-id="d369b-236">此查询将搜寻添加到 Teams 中后迅速删除的外部帐户，以帮助识别可疑行为。</span><span class="sxs-lookup"><span data-stu-id="d369b-236">This query hunts for external accounts that are added to Teams and swiftly removed to help identify suspicious behavior.</span></span>

```kusto
// If you want to look at user added further than 7 days ago adjust this value 
let time_ago = 7d; 
// If you want to change the timeframe of how quickly accounts need to be added and removed change this value 
let time_delta = 1h; 
TeamsData  
| where TimeGenerated > ago(time_ago) 
| where Operation =~ "MemberAdded" 
| extend UPN = tostring(parse_json(Members)[0].UPN) 
| project TimeAdded=TimeGenerated, Operation, UPN, UserWhoAdded = UserId, TeamName, TeamGuid = tostring(Details.TeamGuid) 
| join ( 
TeamsData  
| where TimeGenerated > ago(time_ago) 
| where Operation =~ "MemberRemoved" 
| extend UPN = tostring(parse_json(Members)[0].UPN) 
| project TimeDeleted=TimeGenerated, Operation, UPN, UserWhoDeleted = UserId, TeamName, TeamGuid = tostring(Details.TeamGuid)) on UPN, TeamGuid 
| where TimeDeleted < (TimeAdded + time_delta) 
| project TimeAdded, TimeDeleted, UPN, UserWhoAdded, UserWhoDeleted, TeamName, TeamGuid 
// Uncomment the following line to map query entities is you plan to use this as a detection query 
//| extend timestamp = TimeAdded, AccountCustomEntity = UPN 
```

#### <a name="new-bot-or-application-added"></a><span data-ttu-id="d369b-237">添加了新的机器人或应用程序</span><span class="sxs-lookup"><span data-stu-id="d369b-237">New bot or application added</span></span>

<span data-ttu-id="d369b-238">Teams 可以在团队中包含应用或机器人，以扩展功能集。</span><span class="sxs-lookup"><span data-stu-id="d369b-238">Teams has the ability to include apps or bots in a Team to extend the feature set.</span></span> <span data-ttu-id="d369b-239">其中包括自定义应用和机器人。</span><span class="sxs-lookup"><span data-stu-id="d369b-239">This includes custom apps and bots.</span></span> <span data-ttu-id="d369b-240">在某些情况下，可以使用应用或机器人在 Teams 中建立持久性，无需用户帐户，也可以访问文件和其他数据。</span><span class="sxs-lookup"><span data-stu-id="d369b-240">In some cases, an app or bot could be used to establish persistence in Teams without needing a user account, as well as access files and other data.</span></span> <span data-ttu-id="d369b-241">此查询会搜寻 Teams 中新增的应用或机器人。</span><span class="sxs-lookup"><span data-stu-id="d369b-241">This query hunts for apps or bots that are new to Teams.</span></span>

```kusto
// If you have more than 14 days worth of Teams data change this value 
let data_date = 14d; 
let historical_bots = ( 
TeamsData 
| where TimeGenerated > ago(data_date) 
| where isnotempty(AddOnName) 
| project AddOnName); 
TeamsData 
| where TimeGenerated > ago(1d) 
// Look for add-ins we have never seen before 
| where AddOnName in (historical_bots) 
// Uncomment the following line to map query entities is you plan to use this as a detection query 
//| extend timestamp = TimeGenerated, AccountCustomEntity = UserId 
```

#### <a name="user-accounts-who-are-owners-of-large-numbers-of-teams"></a><span data-ttu-id="d369b-242">拥有大量 Teams 的用户帐户</span><span class="sxs-lookup"><span data-stu-id="d369b-242">User accounts who are Owners of large numbers of Teams</span></span>

<span data-ttu-id="d369b-243">希望提升其特权的攻击者可能会为自己分配大量不同 Teams 的所有者特权，而通常情况下，用户会创建和拥有少量围绕特定主题的 Teams。</span><span class="sxs-lookup"><span data-stu-id="d369b-243">Attackers looking to elevate their privileges may assign themselves Owner privileges of a large number of diverse teams, when, usually, users create and own a small number of teams around specific topics.</span></span> <span data-ttu-id="d369b-244">此 KQL 查询可查找可疑行为。</span><span class="sxs-lookup"><span data-stu-id="d369b-244">This KQL query looks for suspicious behavior.</span></span>

```kusto
// Adjust this value to change how many teams a user is made owner of before detecting 
let max_owner_count = 3; 
// Change this value to adjust how larger timeframe the query is run over. 
let time_window = 1d; 
let high_owner_count = (TeamsData 
| where TimeGenerated > ago(time_window) 
| where Operation =~ "MemberRoleChanged" 
| extend Member = tostring(parse_json(Members)[0].UPN)  
| extend NewRole = toint(parse_json(Members)[0].Role)  
| where NewRole == 2 
| summarize dcount(TeamName) by Member 
| where dcount_TeamName > max_owner_count 
| project Member); 
TeamsData 
| where TimeGenerated > ago(time_window) 
| where Operation =~ "MemberRoleChanged" 
| extend Member = tostring(parse_json(Members)[0].UPN)  
| extend NewRole = toint(parse_json(Members)[0].Role)  
| where NewRole == 2 
| where Member in (high_owner_count) 
| extend TeamGuid = tostring(Details.TeamGuid) 
// Uncomment the following line to map query entities is you plan to use this as a detection query 
//| extend timestamp = TimeGenerated, AccountCustomEntity = Member 
```

#### <a name="many-team-deletions-by-a-single-user"></a><span data-ttu-id="d369b-245">单个用户删除多个团队</span><span class="sxs-lookup"><span data-stu-id="d369b-245">Many Team deletions by a single user</span></span>

<span data-ttu-id="d369b-246">攻击者可以通过删除多个团队来造成中断并危及项目和数据。</span><span class="sxs-lookup"><span data-stu-id="d369b-246">Attackers can cause disruptions and jeopardize projects and data by deleting multiple teams.</span></span> <span data-ttu-id="d369b-247">由于团队通常由个人所有者删除，因此将多个团队集中删除可能是出现问题的迹象。</span><span class="sxs-lookup"><span data-stu-id="d369b-247">Because teams are generally deleted by individual Owners, a central deletion of many teams can be a sign of trouble.</span></span> <span data-ttu-id="d369b-248">此 KQL 可查找删除了多个团队的单个用户。</span><span class="sxs-lookup"><span data-stu-id="d369b-248">This KQL looks for single users who delete multiple teams.</span></span>

```kusto
 // Adjust this value to change how many Teams should be deleted before including
 let max_delete = 3;
 // Adjust this value to change the timewindow the query runs over
 let time_window = 1d;
 let deleting_users = (
 TeamsData 
 | where TimeGenerated > ago(time_window)
 | where Operation =~ "TeamDeleted"
 | summarize count() by UserId
 | where count_ > max_delete
 | project UserId);
 TeamsData
 | where TimeGenerated > ago(time_window)
 | where Operation =~ "TeamDeleted"
 | where UserId in (deleting_users)
 | extend TeamGuid = tostring(Details.TeamGuid)
 | project-away AddOnName, Members, Settings
 // Uncomment the following line to map query entities is you plan to use this as a detection query
 //| extend timestamp = TimeGenerated, AccountCustomEntity = UserId
```

#### <a name="expanding-your-thread-hunting-opportunities"></a><span data-ttu-id="d369b-249">扩大你的线程搜寻机会</span><span class="sxs-lookup"><span data-stu-id="d369b-249">Expanding your thread hunting opportunities</span></span>

<span data-ttu-id="d369b-250">你可以通过将来自 Azure Active Directory (Azure AD) 或其他 Office 365 工作负载等资源的查询与 Teams 查询相结合来扩大搜寻范围。</span><span class="sxs-lookup"><span data-stu-id="d369b-250">You can expand your hunting by combining queries from resources like Azure Active Directory (Azure AD), or other Office 365 workloads with your Teams queries.</span></span> <span data-ttu-id="d369b-251">一个示例是结合对 Azure AD SigninLogs 中可疑模式的检测，并使用该信息来搜寻团队所有者。</span><span class="sxs-lookup"><span data-stu-id="d369b-251">One example is combining detection of suspicious patterns in Azure AD SigninLogs, and using that information while hunting for Team Owners.</span></span>

```kusto
let timeRange = 1d;
let lookBack = 7d;
let threshold_Failed = 5;
let threshold_FailedwithSingleIP = 20;
let threshold_IPAddressCount = 2;
let isGUID = "[0-9a-z]{8}-[0-9a-z]{4}-[0-9a-z]{4}-[0-9a-z]{4}-[0-9a-z]{12}";
let azPortalSignins = SigninLogs
| where TimeGenerated >= ago(timeRange)
// Azure Portal only and exclude non-failure Result Types
| where AppDisplayName has "Azure Portal" and ResultType !in ("0", "50125", "50140")
// Tagging identities not resolved to friendly names
| extend Unresolved = iff(Identity matches regex isGUID, true, false);
// Lookup up resolved identities from last 7 days
let identityLookup = SigninLogs
| where TimeGenerated >= ago(lookBack)
| where not(Identity matches regex isGUID)
| summarize by UserId, lu_UserDisplayName = UserDisplayName, lu_UserPrincipalName = UserPrincipalName;
// Join resolved names to unresolved list from portal signins
let unresolvedNames = azPortalSignins | where Unresolved == true | join kind= inner (
   identityLookup ) on UserId
| extend UserDisplayName = lu_UserDisplayName, UserPrincipalName = lu_UserPrincipalName
| project-away lu_UserDisplayName, lu_UserPrincipalName;
// Join Signins that had resolved names with list of unresolved that now have a resolved name
let u_azPortalSignins = azPortalSignins | where Unresolved == false | union unresolvedNames;
let failed_signins = (u_azPortalSignins
| extend Status = strcat(ResultType, ": ", ResultDescription), OS = tostring(DeviceDetail.operatingSystem), Browser = tostring(DeviceDetail.browser)
| extend FullLocation = strcat(Location,'|', LocationDetails.state, '|', LocationDetails.city)
| summarize TimeGenerated = makelist(TimeGenerated), Status = makelist(Status), IPAddresses = makelist(IPAddress), IPAddressCount = dcount(IPAddress), FailedLogonCount = count()
by UserPrincipalName, UserId, UserDisplayName, AppDisplayName, Browser, OS, FullLocation
| mvexpand TimeGenerated, IPAddresses, Status
| extend TimeGenerated = todatetime(tostring(TimeGenerated)), IPAddress = tostring(IPAddresses), Status = tostring(Status)
| project-away IPAddresses
| summarize StartTime = min(TimeGenerated), EndTime = max(TimeGenerated) by UserPrincipalName, UserId, UserDisplayName, Status, FailedLogonCount, IPAddress, IPAddressCount, AppDisplayName, Browser, OS, FullLocation
| where (IPAddressCount >= threshold_IPAddressCount and FailedLogonCount >= threshold_Failed) or FailedLogonCount >= threshold_FailedwithSingleIP
| project UserPrincipalName);
TeamsData
| where TimeGenerated > ago(time_window)
| where Operation =~ "MemberRoleChanged"
| extend Member = tostring(parse_json(Members)[0].UPN) 
| extend NewRole = toint(parse_json(Members)[0].Role) 
| where NewRole == 2
| where Member in (failed_signins)
| extend TeamGuid = tostring(Details.TeamGuid)
```

<span data-ttu-id="d369b-252">此外，你还可以使用以下方法为仅基于 Teams 的登录添加筛选器，将 SigninLogs 检测设置为特定于 Teams：</span><span class="sxs-lookup"><span data-stu-id="d369b-252">Also, you can make the SigninLogs detections specific to Teams by adding a filter for only Teams-based sign-ins by using:</span></span>

```kusto
| where AppDisplayName startswith "Microsoft Teams"
```

<span data-ttu-id="d369b-253">为了帮助进一步说明如何使用 `where AppDisplayName starts with "Microsoft Teams"`，下面的 KQL 演示了从一个 IP 地址成功登录而从另一个 IP 地址失败的情况，但仅限于 Teams 登录：</span><span class="sxs-lookup"><span data-stu-id="d369b-253">To help explain using `where AppDisplayName starts with "Microsoft Teams"` further, the KQL below demonstrates a successful logon from one IP address with failure from a different IP address, but scoped only to Teams sign-ins:</span></span>

```kusto
let timeFrame = 1d;
let logonDiff = 10m;
SigninLogs 
  | where TimeGenerated >= ago(timeFrame) 
  | where ResultType == "0" 
  | where AppDisplayName startswith "Microsoft Teams"
  | project SuccessLogonTime = TimeGenerated, UserPrincipalName, SuccessIPAddress = IPAddress, AppDisplayName, SuccessIPBlock = strcat(split(IPAddress, ".")[0], ".", split(IPAddress, ".")[1])
  | join kind= inner (
      SigninLogs 
      | where TimeGenerated >= ago(timeFrame) 
      | where ResultType !in ("0", "50140") 
      | where ResultDescription !~ "Other"  
      | where AppDisplayName startswith "Microsoft Teams"
      | project FailedLogonTime = TimeGenerated, UserPrincipalName, FailedIPAddress = IPAddress, AppDisplayName, ResultType, ResultDescription
  ) on UserPrincipalName, AppDisplayName 
  | where SuccessLogonTime < FailedLogonTime and FailedLogonTime - SuccessLogonTime <= logonDiff and FailedIPAddress !startswith SuccessIPBlock
  | summarize FailedLogonTime = max(FailedLogonTime), SuccessLogonTime = max(SuccessLogonTime) by UserPrincipalName, SuccessIPAddress, AppDisplayName, FailedIPAddress, ResultType, ResultDescription 
  | extend timestamp = SuccessLogonTime, AccountCustomEntity = UserPrincipalName, IPCustomEntity = SuccessIPAddress
```

## <a name="important-information-and-updates"></a><span data-ttu-id="d369b-254">重要信息和更新</span><span class="sxs-lookup"><span data-stu-id="d369b-254">Important information and updates</span></span>

<span data-ttu-id="d369b-255">**感谢你们的内容协作，Pete Bryan、Nicholas DiCola 和 Matthew Lowe。**</span><span class="sxs-lookup"><span data-stu-id="d369b-255">**Thank you for content collaboration, Pete Bryan, Nicholas DiCola, and Matthew Lowe.**</span></span> <span data-ttu-id="d369b-256">Pete Bryan 和他的同事将继续为 Teams 开发检测和搜寻查询，因此请时常访问该 [GitHub](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/TeamsLogs) 存储库以获取更新。</span><span class="sxs-lookup"><span data-stu-id="d369b-256">Pete Bryan and the people he collaborates with will continue to develop detection and hunting queries for Teams, so keep in touch with this [GitHub](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/TeamsLogs) repository for updates.</span></span>  <span data-ttu-id="d369b-257">监控本文中使用的[分析器](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt)和[逻辑应用](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data)的更新。</span><span class="sxs-lookup"><span data-stu-id="d369b-257">Monitor for updates to the [parser](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt) and [logic app](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) used in this article.</span></span> <span data-ttu-id="d369b-258">你也可以加入并参与 [Azure Sentinel 社区](https://github.com/Azure/Azure-Sentinel/wiki)。</span><span class="sxs-lookup"><span data-stu-id="d369b-258">You can also join and contribute to the [Azure Sentinel community](https://github.com/Azure/Azure-Sentinel/wiki).</span></span> <span data-ttu-id="d369b-259">谢谢！</span><span class="sxs-lookup"><span data-stu-id="d369b-259">Thank you!</span></span> <span data-ttu-id="d369b-260">祝你搜寻愉快。</span><span class="sxs-lookup"><span data-stu-id="d369b-260">Happy hunting.</span></span>

[<span data-ttu-id="d369b-261">在 Azure AD 中注册应用程序</span><span class="sxs-lookup"><span data-stu-id="d369b-261">Registering your application in Azure AD</span></span>](https://docs.microsoft.com/skype-sdk/ucwa/registeringyourapplicationinazuread%C2%A0%20%20%C2%A0)

[<span data-ttu-id="d369b-262">启用或禁用审核日志搜索</span><span class="sxs-lookup"><span data-stu-id="d369b-262">Turn audit log search on or off</span></span>](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide&viewFallbackFrom=o365-worldwide%C2%A0)

[<span data-ttu-id="d369b-263">什么是 Azure Sentinel</span><span class="sxs-lookup"><span data-stu-id="d369b-263">What is Azure Sentinel</span></span>](https://docs.microsoft.com/azure/sentinel/overview)
