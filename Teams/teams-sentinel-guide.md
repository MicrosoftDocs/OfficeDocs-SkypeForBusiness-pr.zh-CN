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
ms.openlocfilehash: 55307637e18f81775229bb46db51a6f5738cce7c
ms.sourcegitcommit: b387296c043fcf10fba7b9ef416328383e54a565
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/26/2021
ms.locfileid: "53587041"
---
# <a name="azure-sentinel-and-microsoft-teams"></a>Azure Sentinel 和 Microsoft Teams

> [!IMPORTANT]
> Azure Sentinel 现具有集成连接器。 有关详细信息，请参阅 [将 Office 365 日志连接到 Azure Sentinel](/azure/sentinel/connect-office-365)。 这是收集这些日志的建议途径，并取代下文所述的收集方法。

Teams 在 Microsoft 365 云中的通信和数据共享中发挥核心作用。 由于 Teams 涉及云中的多种技术，因此它可以从人机和自动化分析受益。 这适用于 *日志搜索* 和 *对会议进行实时*。 Azure Sentinel 可为管理员提供这些解决方案。

> [!NOTE]
> 需要复习有关 Azure Sentinel 的知识？ [本文](/azure/sentinel/overview)正好满足你的需求。

## <a name="sentinel-and-microsoft-teams-activity-logs"></a>Sentinel 和 Microsoft Teams 活动日志

本文重点介绍如何在 Azure Sentinel 中收集 Teams 活动日志。

Sentinel 允许管理员在一个位置进行安全管理。这包括管理以下内容：

- 第三方设备
- Microsoft 威胁防护
- Microsoft 365 工作负载

发送的工作簿和运行簿可以使系统 *监视*。 该过程的第一步是收集需要分析的日志。

> [!NOTE]
> 可以在同一个 Azure Sentinel 实例中呈现多个 Microsoft 365 订阅。 这将允许[实时监控](/azure/sentinel/livestream)以及在历史日志文件中搜寻威胁。 管理员可以使用[跨资源查询](/azure/azure-monitor/log-query/cross-workspace-query)在单个资源组内、跨资源组或在另一个订阅中进行搜寻。

## <a name="step-1-collect-teams-logs-enable-audit-logs-in-microsoft-365"></a>步骤 1：收集团队日志：在 Microsoft 365 中启用审核日志

由于 Teams 通过 Microsoft 365 记录活动，因此默认情况下不会收集审核日志。 通过[以下步骤](/microsoft-365/compliance/turn-audit-log-search-on-or-off)启用此功能。 Teams 数据在 Microsoft 365 审核中根据 *Audit.General* 进行收集。

## <a name="step-2-connect-office-365-logs-to-azure-sentinel"></a>步骤 2：将 Office 365 日志连接到 Azure Sentinel

Azure Sentinel 提供 Office 365 日志的内置连接器，可用于将 Teams 数据和其他 Office 365 数据一起输入 Azure Sentinel。
 
在 Azure Sentinel 中，启用 Office 365 数据连接器。 有关详细信息，请参阅 [Azure Sentinel 文档](/azure/sentinel/connect-office-365)。

## <a name="helpful-hunting-kql-queries"></a>有用的搜寻 KQL 查询

可以使用这些查询来让自己熟悉 Teams 数据和 Teams 环境。 要识别可疑活动，最好先了解环境的外观和行为。 从那里，你可以分支到威胁搜寻。

### <a name="federated-external-users-query"></a>联合外部用户查询

获取具有联合外部用户的 Teams 网站的列表。 这些用户具有域名和/或未由你的组织拥有的 UPN 后缀。

在此示例查询中，组织拥有 contoso.com。

```Kusto
OfficeActivity
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberAdded"
| where parse_json(Members)[0].Role == 3
| project TeamName, Operation, UserId, Members
| mv-expand bagexpansion=array Members
| evaluate bag_unpack(Members)
```

> [!TIP]
> 若要深入了解 Teams 中的外部和来宾访问类型，请参阅 [与其他组织](communicate-with-users-from-other-organizations.md)的用户沟通"，或"Teams 安全指南"中的 [参与者](teams-security-guide.md#participant-types) 部分。

### <a name="who-recently-joined--whose-role-changed"></a>最近加入/角色已更改的人员

查询特定用户以了解他们是否是在最近 7 天或一周内添加到 Teams 频道的：

```Kusto
OfficeActivity
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberAdded"
| where Members has "<DisplayName>" or Members has "<UserPrincipalName>"
| project TeamName, Operation, UserId, Members
```

查询用户的角色是否过去七天内为团队发生更改：

```Kusto
OfficeActivity
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberRoleChanged"
| project TeamName, Operation, UserId, Members
| mv-expand bagexpansion=array Members
| evaluate bag_unpack(Members)
| where Role == '1'
``` 

### <a name="external-users-from-unknown-or-new-organizations"></a>来自未知组织或新组织的外部用户

在 Teams 中，可将外部用户添加到你的环境或频道。 组织通常具有数量有限的关键合作伙伴关系，并从这些合作伙伴中添加用户。 此 KQL 会查看添加到团队的外部用户，这些用户来自之前没有见过或添加过的组织。

有关详细信息，请参阅 Azure Sentinel 社区 [git 中心网站中的查询](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/ExternalUserFromNewOrgAddedToTeams.yaml)。

### <a name="external-users-who-were-added-and-then-removed"></a>添加后又删除的外部用户

具有一定程度的现有访问权限的攻击者可能会向 Teams 添加一个新的外部帐户，以便访问和窃取数据。 他们还可能会快速删除该用户，以隐藏他们进行了访问的事实。 此查询将搜寻添加到 Teams 中后迅速删除的外部帐户，以帮助识别可疑行为。

有关详细信息，请参阅 Azure Sentinel 社区 [git 中心网站中的查询](https://github.com/Azure/Azure-Sentinel/blob/master/Detections/OfficeActivity/ExternalUserAddedRemovedInTeams.yaml)。

### <a name="new-bot-or-application-added"></a>添加了新的机器人或应用程序

团队可在团队中包括应用或机器人以扩展功能集（包括自定义应用和自动程序）。 在某些情况下，应用或自动程序可用于在 Teams *暂留* ，而无需用户帐户，并且可以访问文件和其他数据。 此查询会搜寻 Teams 中新增的应用或机器人。

有关详细信息，请参阅 Azure Sentinel 社区 [git 中心网站中的查询](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/NewBotAddedToTeams.yaml)。

### <a name="user-accounts-who-are-owners-of-large-numbers-of-teams"></a>拥有大量 Teams 的用户帐户

想要提升特权的攻击者可能会为大量不同团队分配所有者权限。 *通常*，用户围绕特定主题创建并拥有一些团队。 此 KQL 查询可查找可疑行为。

有关详细信息，请参阅 Azure Sentinel 社区 [git 中心网站中的查询](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/MultiTeamOwner.yaml)。

### <a name="many-team-deletions-by-a-single-user"></a>单个用户删除多个团队

攻击者可以通过删除多个团队来造成中断并危及项目和数据。 由于团队通常由单个所有者删除，因此集中删除许多团队可能是问题之一。 此 KQL 可查找删除了多个团队的单个用户。

有关详细信息，请参阅 Azure Sentinel 社区 [git 中心网站中的查询](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/MultipleTeamsDeletes.yaml)。

### <a name="expanding-your-threat-hunting-opportunities"></a>扩大你的线程搜寻机会

组合来自 Azure Active Directory （Azure AD） 或其他 Office 365 工作负荷等资源查询可以与 Teams 查询一起使用。 例如，组合检测 Azure AD SigninLogs 中的可疑模式，并使用该输出，同时搜索团队所有者。

```Kusto
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
OfficeActivity
| where TimeGenerated > ago(time_window)
| where Operation =~ "MemberRoleChanged"
| mv-expand bagexpansion=array Members
| evaluate bag_unpack(Members)
| where Role == '2'
| where Members in (failed_signins)
```

此外，你还可以使用以下方法为仅基于 Teams 的登录添加筛选器，将 SigninLogs 检测设置为特定于 Teams：

```Kusto
| where AppDisplayName has 'Teams'
```

为了帮助说明 *AppDisplayName在哪里进一步使用Teams*，您在下面看到的KQL演示了从一个IP地址成功登录，而从另一个IP地址失败，但 *仅* 限于Teams登录的情况：

```Kusto
let timeFrame = 1d;
let logonDiff = 10m;
SigninLogs 
  | where TimeGenerated >= ago(timeFrame) 
  | where ResultType == "0" 
  | where AppDisplayName has "Teams"
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

**感谢你们的内容协作，Pete Bryan、Nicholas DiCola 和 Matthew Lowe。** 牛娇和合作人员继续为 Teams 开发检测和查询查询。

使用 Git Hub [更新](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/TeamsLogs) 保持联络。

监控本文中使用的[分析器](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt)和[逻辑应用](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data)的更新。

你也可以加入并参与 [Azure Sentinel 社区](https://github.com/Azure/Azure-Sentinel/wiki)。 我们正在积极寻找有关本文的反馈，因此请使用下面的反馈选项。 谢谢，快乐你。

[在 Azure AD 中注册应用程序](/skype-sdk/ucwa/registeringyourapplicationinazuread%C2%A0%20%20%C2%A0)

[启用或禁用审核日志搜索](/microsoft-365/compliance/turn-audit-log-search-on-or-off)

[什么是 Azure Sentinel?](/azure/sentinel/overview)
