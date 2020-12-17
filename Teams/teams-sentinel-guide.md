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
# <a name="azure-sentinel-and-microsoft-teams"></a>Azure Sentinel 和 Microsoft Teams

Teams 在 Microsoft 365 云中的通信和数据共享中发挥核心作用。 由于 Teams 服务涉及云中的许多基础技术，因此它不仅可以在 *搜寻日志* 时从人工和自动化分析中受益，还可以 *实时监控会议*。 Azure Sentinel 可为管理员提供这些解决方案。

> [!NOTE]
> 需要复习有关 Azure Sentinel 的知识？ [本文](https://docs.microsoft.com/azure/sentinel/overview)正好满足你的需求。

## <a name="sentinel-and-microsoft-teams-activity-logs"></a>Sentinel 和 Microsoft Teams 活动日志

本文重点介绍如何在 Azure Sentinel 中收集 Teams 活动日志。 除了允许管理员将安全管理放在一个窗格（包括任何选定的第三方设备、Microsoft 威胁防护和其他 Microsoft 365 工作负载）下，Sentinel 工作簿和运行手册还可以使安全监控系统化。 在此流程中，最好先收集所需的日志进行分析。

> [!NOTE]
> 可以在同一个 Azure Sentinel 实例中呈现多个 Microsoft 365 订阅。 这将允许[实时监控](https://docs.microsoft.com/azure/sentinel/livestream)以及在历史日志文件中搜寻威胁。 管理员可以使用[跨资源查询](https://docs.microsoft.com/azure/azure-monitor/log-query/cross-workspace-query)在单个资源组内、跨资源组或在另一个订阅中进行搜寻。

## <a name="step-1-collect-teams-logs"></a>步骤 1：收集 Teams 日志

此分区具有三个部分：

1. 在 **Microsoft 365** (M365) 中启用审核日志。
2. 在 **Microsoft Azure** 中注册应用，以允许对日志收集进行身份验证和授权。
3. 注册 API 订阅，允许在 M365 API 中通过 **PowerShell** 进行日志收集。

### <a name="enable-audit-logs-in-m365"></a>在 M365 中启用审核日志

由于 Teams 通过 M365 记录活动，因此默认情况下不会收集审核日志。 通过[以下步骤](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide&viewFallbackFrom=o365-worldwide%C2%A0)启用此功能。 Teams 数据在 M365 审核中根据 *Audit.General* 进行收集。

### <a name="register-an-app-in-microsoft-azure-for-log-collection"></a>在 Microsoft Azure 中注册应用以进行日志收集

> [!TIP]
> 开始之前，需要记录 **应用程序ID/客户端 ID** 以及 **租户 ID**，以便以后使用。 在执行以下应用程序注册步骤时，务必捕获这些信息。 你将看到这两个 ID。
>- 创建应用后，单击快速启动侧栏上的“应用注册”> 查找新应用程序的显示名称 > 复制应用程序（客户端）ID。
>- 单击快速启动侧栏上的“概述”> 复制目录（租户）ID。

对 Azure Active Directory (Azure AD) 应用进行身份验证和授权，以从 API 收集日志数据。

1. 在 Azure 门户中导航到 *Azure AD* 边栏选项卡。
2. 单击快速启动侧栏中的“*应用注册*”。
3. 选择“*新注册*”。
4. 为你的 Teams 日志收集应用命名，然后单击“*注册*”。
5. 沿以下路径依次单击：“*API权限*” > “*添加权限*” > “*Office 365 管理 API*” > “*应用程序权限*”。
6. 展开活动源，然后勾选 *ActivityFeed.Read*。
7. 在此处选择“*获得管理员同意*”。 当系统提示询问这是否是你的本意时，单击“是”。
8. 单击侧栏的“*证书和密码*”>“*新客户端密码*”。
9. 在“新客户端密码”窗口上，输入对新客户端密码的描述，确保为“过期”选择“永不”，然后单击“*添加*”。

> [!IMPORTANT]
> 将新的客户端密码复制到新创建的应用名称下的密码管理器条目中，这一点很 **重要**。 关闭 Azure 边栏选项卡（*边栏选项卡* 是 Azure 窗口术语）后，将无法返回查看此密码。

### <a name="register-the-api-with-powershell-to-collect-teams-logs"></a>在 PowerShell 中注册 API 以收集 Teams 日志

设置的最后一步是收集并注册 API 订阅，以便你能收集日志数据。 此操作通过对 M365 管理活动 API 的 PowerShell REST 调用来完成。

准备好在下面的 PowerShell cmdlet 中提供 **应用程序（客户端）ID**、新的 **客户端密码**、**M365 的 URL 域** 和 **目录（租户）ID** 值。

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

## <a name="step-2-deploy-a-sentinel-playbook-to-ingest-the-teams-logs"></a>步骤 2：部署 Sentinel Playbook 以获取 Teams 日志

Azure Sentinel Playbook（也称为逻辑应用）将允许 Azure 获取你收集的 Teams 数据。 逻辑应用将查询 Office 365 以查找其写入 Azure Sentinel 工作区的审核数据。

使用[此](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) ARM 模板部署你的 Sentinel Playbook。

注意事项：

1. 你将需要遍历 ARM 模板并将某些值替换为适合自身环境的值。
2. 你将需要在获取日志和查看 Azure Sentinel 中的结果之间留出时间。

   等待 5 到 10 分钟，明白一点，如果过去 5 分钟内没有数据，你将看到一条错误消息。 检查审核日志，请记住，由于 Teams 信息位于 Audit.General 事件中（该事件比 Teams 日志收集的信息更多），因此结果应在使用中的系统上显示 5 到 10 分钟。 如果使用文本环境，请确保使用 Teams 来生成日志记录。

![显示逻辑应用类的图形。](media/tracyp-teams-sentinel-logic-app.png#thumbnail)

 <p><details><summary> 图形操作说明： 
  </summary>

  •“定期”是一种逻辑应用触发器，它指示工作流每小时运行一次。
  <p>
•“当前时间”操作是一种非常基本的操作，仅获取当前时间。
  <p>
•“初始化变量”将创建名为 NextPage 的变量，并将其设置为 1。 稍后将使用它来处理 O365 API 中的分页。
  <p>
•“初始化变量 2”会创建一个名为“开始时间”的空变量。
  <p>
• 运行查询和列表结果是一个 Azure Monitor 操作，它将查询从逻辑应用中输入的最后一个 O365 日志的工作区。
  <p>
•“条件 4”用于检查运行查询和列表结果查询是否返回了任何数据。 执行此操作可检查这是否是首次使用逻辑应用。 如果未返回任何数据，StartTime 变量将设置为“现在 – 24 小时”。 如果返回了数据，StartTime 将设置为最后一条记录 TimeGenerated。 这样做是为了使查询可以获取针对 O365 API 的轮询中从最后一个条目到现在的数据；或者如果是第一次运行，则可以获取最近 24 小时内的数据。
  <p>
•“初始化变量 3”会创建一个名为 AvailableUri 的变量。 这是一个字符串，使用 StartTime 和 CurrentTime 分别作为开始时间和结束时间来构建 URL。
  <p>
• Until 条件是一个循环，允许逻辑应用保持轮询 API 以查看是否还有更多数据（分页）。 只要 NextPage 变量为 1，循环就将继续。 之后如果没有更多页面可供检索，此变量将更新。
  <p>
• 在 Until 循环中，第一个 HTTP 步骤连接到 AvailableURI。 此 URI 将返回可用内容和每个内容 URI 的列表。 有关其工作原理的更多信息，请访问此 URL：https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#list-available-content。
  <p>
• 接下来，运行检查以确保返回数据。 该条件将检查正文的长度是否为 0。 如果是，则表示没有数据可写入日志分析。 如果值大于 0，则表示有要处理的数据。
  <p>
• 如果检测到数据，必须随后对其进行处理。 分析 JSON 定义返回数据的架构。 这使逻辑应用能够在后续步骤中将分析数据用作动态内容。
  <p>
• 由于返回的可用数据列表是一个数组，因此，“全部应用”操作用于循环读取可用内容列表。
  <p>
• 下一步是抓取内容。  再次使用 HTTP 获取 contentUri（从分析 JSON 创建的动态属性），即要检索的数据的 URL。
  <p>
• 分析 JSON 还用于分析返回的数据。 可在此 URL 中找到一些示例内容：https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#list-available-content。
  <p>
• 返回的数据也是一个数组。 也可在此处使用“全部应用”循环。 在此循环中，工作流将提取当前数据项，并使用“发送数据”操作将数据写入日志分析。
  <p>
• 由于可能存在多个页面的可用内容，因此一个条件将检查 NextPageUri 是否不为 NULL。 如果为 NULL 或为空，NextPage 将设置为 0，这将结束 Until 循环。 如果它包含 URL，AvaibleUri 变量将更新为该 URL。 这样，下次运行 Until 循环时将使用下个可用的 URL，而不是起始 URL。

  </details>

> [!TIP]
> 你可以选择改用 *Azure 函数* 来获取这些日志，如果执行此操作，有关如何部署的信息将显示在 [此处](https://github.com/Azure/Azure-Sentinel/tree/master/DataConnectors/O365%20Data)或 [此处](https://github.com/Azure/Azure-Sentinel/tree/master/DataConnectors/O365%20DataCSharp)，具体取决于你的偏好。

在连接器（选择上述任一选项）运行时，应该会在 Azure Sentinel 工作区中看到一个名为 O365API_CL 的自定义表。 其中将包括你的 Teams 日志。

## <a name="step-3-use-sentinel-to-monitor-microsoft-teams"></a>步骤 3：使用 Sentinel 监控 Microsoft Teams

身份是要在 Microsoft Teams 中监控的重要攻击媒介。 由于 Azure Active Directory (Azure AD) 是 Microsoft 365 目录（包括 Teams）的基础，因此收集和搜寻有关身份验证的 Azure AD 日志中的威胁将有助于捕获关于身份的可疑行为。 你可以使用内置连接器将 Azure AD 数据拉入 Azure Sentinel，并使用这些[检测](https://github.com/Azure/Azure-Sentinel/tree/master/Detections/SigninLogs)和[搜寻](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/SigninLogs)查询来查找问题。

对于特定于 Microsoft Teams 的攻击，例如对数据的威胁，Azure Sentinel 还有监控和追查数据的手段。

### <a name="create-a-parser-for-your-data"></a>为数据创建分析器

为了理解收集的大量数据，首先要通过分析使其具有意义。 此操作可以通过 Kusto 查询语言 (KQL) 函数完成，该函数使数据更易于使用。

> [!NOTE]
> KQL 函数是保存为名为“函数”的数据类型的 KQL 查询。 KQL 函数有一个别名，可在 Sentinel 的查询框中输入别名来快速重新运行查询。 有关 KQL 函数以及如何构建解析器函数的更多信息，请阅读[本技术社区文章](https://techcommunity.microsoft.com/t5/azure-sentinel/using-kql-functions-to-speed-up-analysis-in-azure-sentinel/ba-p/712381)。
 
 下面的解析器是一个可自定义的示例，旨在选择与 *Teams* 相关的 Office 365 管理 API 字段的子集。 此外还有一个建议的分析器 [GitHub ](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt)，但可以下面的解析器可以针对不同的需求和偏好进行修改。

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
 将分析器另存为别名为 TeamsData 的 KQL 函数。 它将用于后续查询。 可在此[技术社区文章](https://techcommunity.microsoft.com/t5/azure-sentinel/using-kql-functions-to-speed-up-analysis-in-azure-sentinel/ba-p/712381)中找到有关配置和使用 KQL 函数作为分析器的详细信息。

## <a name="helpful-hunting-kql-queries"></a>有用的搜寻 KQL 查询

可以使用这些查询来让自己熟悉 Teams 数据和 Teams 环境。 要识别可疑活动，最好先了解环境的外观和行为。 从那里，你可以分支到威胁搜寻。

#### <a name="federated-external-users-query"></a>联合外部用户查询

获取具有联合外部用户的 Teams 网站的列表。 这些用户将具有 *不* 归你的组织拥有的域名/UPN 后缀。 在此示例查询中，组织拥有 contoso.com。

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
> 若要了解有关 Teams 中外部和来宾访问类型的更多信息，请参阅 [本文](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations)或 [Teams 安全指南](https://docs.microsoft.com/microsoftteams/teams-security-guide)中的 *参与者类型* 部分。

#### <a name="who-recently-joined--whose-role-changed"></a>最近加入/角色已更改的人员

查询特定用户以了解他们是否是在最近 7 天或一周内添加到 Teams 频道的：

```kusto
TeamsData
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberAdded"
| where Members contains "UserName"
```

用户针对某个团队的角色是否在最近 7 天内进行了更改：

```kusto
TeamsData
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberRoleChanged"
| where Members contains "Role" and Members contains "1"
```

#### <a name="external-users-from-unknown-or-new-organizations"></a>来自未知组织或新组织的外部用户

在 Teams 中，可将外部用户添加到你的环境或频道。 组织通常具有数量有限的关键合作伙伴关系，并从这些合作伙伴中添加用户。 此 KQL 会查看添加到团队的外部用户，这些用户来自之前没有见过或添加过的组织。

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

#### <a name="external-users-who-were-added-and-then-removed"></a>添加后又删除的外部用户

具有一定程度的现有访问权限的攻击者可能会向 Teams 添加一个新的外部帐户，以便访问和窃取数据。 他们还可能会快速删除该用户，以隐藏他们进行了访问的事实。 此查询将搜寻添加到 Teams 中后迅速删除的外部帐户，以帮助识别可疑行为。

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

#### <a name="new-bot-or-application-added"></a>添加了新的机器人或应用程序

Teams 可以在团队中包含应用或机器人，以扩展功能集。 其中包括自定义应用和机器人。 在某些情况下，可以使用应用或机器人在 Teams 中建立持久性，无需用户帐户，也可以访问文件和其他数据。 此查询会搜寻 Teams 中新增的应用或机器人。

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

#### <a name="user-accounts-who-are-owners-of-large-numbers-of-teams"></a>拥有大量 Teams 的用户帐户

希望提升其特权的攻击者可能会为自己分配大量不同 Teams 的所有者特权，而通常情况下，用户会创建和拥有少量围绕特定主题的 Teams。 此 KQL 查询可查找可疑行为。

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

#### <a name="many-team-deletions-by-a-single-user"></a>单个用户删除多个团队

攻击者可以通过删除多个团队来造成中断并危及项目和数据。 由于团队通常由个人所有者删除，因此将多个团队集中删除可能是出现问题的迹象。 此 KQL 可查找删除了多个团队的单个用户。

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

#### <a name="expanding-your-thread-hunting-opportunities"></a>扩大你的线程搜寻机会

你可以通过将来自 Azure Active Directory (Azure AD) 或其他 Office 365 工作负载等资源的查询与 Teams 查询相结合来扩大搜寻范围。 一个示例是结合对 Azure AD SigninLogs 中可疑模式的检测，并使用该信息来搜寻团队所有者。

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

此外，你还可以使用以下方法为仅基于 Teams 的登录添加筛选器，将 SigninLogs 检测设置为特定于 Teams：

```kusto
| where AppDisplayName startswith "Microsoft Teams"
```

为了帮助进一步说明如何使用 `where AppDisplayName starts with "Microsoft Teams"`，下面的 KQL 演示了从一个 IP 地址成功登录而从另一个 IP 地址失败的情况，但仅限于 Teams 登录：

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

## <a name="important-information-and-updates"></a>重要信息和更新

**感谢你们的内容协作，Pete Bryan、Nicholas DiCola 和 Matthew Lowe。** Pete Bryan 和他的同事将继续为 Teams 开发检测和搜寻查询，因此请时常访问该 [GitHub](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/TeamsLogs) 存储库以获取更新。  监控本文中使用的[分析器](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt)和[逻辑应用](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data)的更新。 你也可以加入并参与 [Azure Sentinel 社区](https://github.com/Azure/Azure-Sentinel/wiki)。 谢谢！ 祝你搜寻愉快。

[在 Azure AD 中注册应用程序](https://docs.microsoft.com/skype-sdk/ucwa/registeringyourapplicationinazuread%C2%A0%20%20%C2%A0)

[启用或禁用审核日志搜索](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide&viewFallbackFrom=o365-worldwide%C2%A0)

[什么是 Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)
