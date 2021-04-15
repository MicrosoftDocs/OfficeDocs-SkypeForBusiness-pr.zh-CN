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
ms.openlocfilehash: c3b2c37f7f3731b34abb5337bf954250e0c3564d
ms.sourcegitcommit: 046b020cee8af00a1d0e5f5866f847d42e8ad9a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "51712764"
---
# <a name="azure-sentinel-and-microsoft-teams"></a><span data-ttu-id="47a7c-103">Azure Sentinel 和 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="47a7c-103">Azure Sentinel and Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="47a7c-104">Azure Sentinel 现具有集成连接器。</span><span class="sxs-lookup"><span data-stu-id="47a7c-104">Azure Sentinel now has an integrated connector.</span></span> <span data-ttu-id="47a7c-105">有关详细信息，请参阅 [将 Office 365 日志连接到 Azure Sentinel](/azure/sentinel/connect-office-365)。</span><span class="sxs-lookup"><span data-stu-id="47a7c-105">For more information, see [Connect Office 365 Logs to Azure Sentinel](/azure/sentinel/connect-office-365).</span></span> <span data-ttu-id="47a7c-106">这是收集这些日志的建议途径，并取代下文所述的收集方法。</span><span class="sxs-lookup"><span data-stu-id="47a7c-106">This is the recommended route for collecting these logs and supersedes the collection methods described below.</span></span>

<span data-ttu-id="47a7c-107">Teams 在 Microsoft 365 云中的通信和数据共享中发挥核心作用。</span><span class="sxs-lookup"><span data-stu-id="47a7c-107">Teams serves a central role in communication and data-sharing in the Microsoft 365 Cloud.</span></span> <span data-ttu-id="47a7c-108">由于 Teams 涉及云中的多种技术，因此它可以从人机和自动化分析受益。</span><span class="sxs-lookup"><span data-stu-id="47a7c-108">Since Teams touches on so many technologies in the Cloud, it can benefit from human and automated analysis.</span></span> <span data-ttu-id="47a7c-109">这适用于 *日志搜索* 和 *对会议进行实时*。</span><span class="sxs-lookup"><span data-stu-id="47a7c-109">This applies to both *hunting in logs*, and *real-time monitoring of meetings*.</span></span> <span data-ttu-id="47a7c-110">Azure Sentinel 可为管理员提供这些解决方案。</span><span class="sxs-lookup"><span data-stu-id="47a7c-110">Azure Sentinel offers admins these solutions.</span></span>

> [!NOTE]
> <span data-ttu-id="47a7c-111">需要复习有关 Azure Sentinel 的知识？</span><span class="sxs-lookup"><span data-stu-id="47a7c-111">Need a refresher on Azure Sentinel?</span></span> <span data-ttu-id="47a7c-112">[本文](/azure/sentinel/overview)正好满足你的需求。</span><span class="sxs-lookup"><span data-stu-id="47a7c-112">[This article](/azure/sentinel/overview) is just the thing.</span></span>

## <a name="sentinel-and-microsoft-teams-activity-logs"></a><span data-ttu-id="47a7c-113">Sentinel 和 Microsoft Teams 活动日志</span><span class="sxs-lookup"><span data-stu-id="47a7c-113">Sentinel and Microsoft Teams Activity Logs</span></span>

<span data-ttu-id="47a7c-114">本文重点介绍如何在 Azure Sentinel 中收集 Teams 活动日志。</span><span class="sxs-lookup"><span data-stu-id="47a7c-114">This article focuses on collecting Teams activity logs in Azure Sentinel.</span></span>

<span data-ttu-id="47a7c-115">已发送的信息允许管理员在一个位置执行安全管理。</span><span class="sxs-lookup"><span data-stu-id="47a7c-115">Sentinel lets administrators do security management in one location.</span></span> <span data-ttu-id="47a7c-116">其中包括管理：</span><span class="sxs-lookup"><span data-stu-id="47a7c-116">This includes managing:</span></span>

- <span data-ttu-id="47a7c-117">第三方设备</span><span class="sxs-lookup"><span data-stu-id="47a7c-117">Third-party devices</span></span>
- <span data-ttu-id="47a7c-118">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="47a7c-118">Microsoft Threat Protection</span></span>
- <span data-ttu-id="47a7c-119">Microsoft 365 工作负载</span><span class="sxs-lookup"><span data-stu-id="47a7c-119">Microsoft 365 Workloads</span></span>

<span data-ttu-id="47a7c-120">发送的工作簿和运行簿可以使系统 *监视*。</span><span class="sxs-lookup"><span data-stu-id="47a7c-120">Sentinel workbooks and runbooks can make security monitoring *systematic*.</span></span> <span data-ttu-id="47a7c-121">该过程的第一步是收集需要分析的日志。</span><span class="sxs-lookup"><span data-stu-id="47a7c-121">A good first step in this process is collecting the logs needed analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="47a7c-122">可以在同一个 Azure Sentinel 实例中呈现多个 Microsoft 365 订阅。</span><span class="sxs-lookup"><span data-stu-id="47a7c-122">More than one Microsoft 365 subscription can be surfaced in the same instance of Azure Sentinel.</span></span> <span data-ttu-id="47a7c-123">这将允许[实时监控](/azure/sentinel/livestream)以及在历史日志文件中搜寻威胁。</span><span class="sxs-lookup"><span data-stu-id="47a7c-123">This will allow for [realtime monitoring](/azure/sentinel/livestream) and hunting for threats in historical log files.</span></span> <span data-ttu-id="47a7c-124">管理员可以使用[跨资源查询](/azure/azure-monitor/log-query/cross-workspace-query)在单个资源组内、跨资源组或在另一个订阅中进行搜寻。</span><span class="sxs-lookup"><span data-stu-id="47a7c-124">Administrators will be able to hunt using [cross-resource queries](/azure/azure-monitor/log-query/cross-workspace-query), that is within a single resource group, across resource groups, or in another subscription.</span></span>

## <a name="step-1-collect-teams-logs-enable-audit-logs-in-microsoft-365"></a><span data-ttu-id="47a7c-125">步骤 1：收集团队日志：在 Microsoft 365 中启用审核日志</span><span class="sxs-lookup"><span data-stu-id="47a7c-125">Step 1: Collect Teams logs: Enable Audit logs in Microsoft 365</span></span>

<span data-ttu-id="47a7c-126">由于 Teams 通过 Microsoft 365 记录活动，因此默认情况下不会收集审核日志。</span><span class="sxs-lookup"><span data-stu-id="47a7c-126">Because Teams logs activity through Microsoft 365, audit logs aren't collected by default.</span></span> <span data-ttu-id="47a7c-127">通过[以下步骤](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off)启用此功能。</span><span class="sxs-lookup"><span data-stu-id="47a7c-127">Turn on this feature with [these steps](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off).</span></span> <span data-ttu-id="47a7c-128">Teams 数据在 Microsoft 365 审核中根据 *Audit.General* 进行收集。</span><span class="sxs-lookup"><span data-stu-id="47a7c-128">Teams data is collected in the Microsoft 365 audit under *Audit.General*.</span></span>

## <a name="step-2-connect-office-365-logs-to-azure-sentinel"></a><span data-ttu-id="47a7c-129">步骤 2：将 Office 365 日志连接到 Azure Sentinel</span><span class="sxs-lookup"><span data-stu-id="47a7c-129">Step 2: Connect Office 365 logs to Azure Sentinel</span></span>

<span data-ttu-id="47a7c-130">Azure Sentinel 提供 Office 365 日志的内置连接器，可用于将 Teams 数据和其他 Office 365 数据一起输入 Azure Sentinel。</span><span class="sxs-lookup"><span data-stu-id="47a7c-130">Azure Sentinel provides a built-in connector for Office 365 logs, which enables you to ingest Teams data into Azure Sentinel together with other Office 365 data.</span></span>
 
<span data-ttu-id="47a7c-131">在 Azure Sentinel 中，启用 Office 365 数据连接器。</span><span class="sxs-lookup"><span data-stu-id="47a7c-131">In Azure Sentinel, enable the Office 365 data connector.</span></span> <span data-ttu-id="47a7c-132">有关详细信息，请参阅 [Azure Sentinel 文档](/azure/sentinel/connect-office-365)。</span><span class="sxs-lookup"><span data-stu-id="47a7c-132">For more information, see the [Azure Sentinel documentation](/azure/sentinel/connect-office-365).</span></span>

## <a name="helpful-hunting-kql-queries"></a><span data-ttu-id="47a7c-133">有用的搜寻 KQL 查询</span><span class="sxs-lookup"><span data-stu-id="47a7c-133">Helpful hunting KQL queries</span></span>

<span data-ttu-id="47a7c-134">可以使用这些查询来让自己熟悉 Teams 数据和 Teams 环境。</span><span class="sxs-lookup"><span data-stu-id="47a7c-134">Use these queries to familiarize yourself with your Teams data and Teams environment.</span></span> <span data-ttu-id="47a7c-135">要识别可疑活动，最好先了解环境的外观和行为。</span><span class="sxs-lookup"><span data-stu-id="47a7c-135">Knowing how the environment should look and behave is a good first step in recognizing suspicious activity.</span></span> <span data-ttu-id="47a7c-136">从那里，你可以分支到威胁搜寻。</span><span class="sxs-lookup"><span data-stu-id="47a7c-136">From there, you can branch out into threat hunting.</span></span>

### <a name="federated-external-users-query"></a><span data-ttu-id="47a7c-137">联合外部用户查询</span><span class="sxs-lookup"><span data-stu-id="47a7c-137">Federated external users query</span></span>

<span data-ttu-id="47a7c-138">获取具有联合外部用户的 Teams 网站的列表。</span><span class="sxs-lookup"><span data-stu-id="47a7c-138">Get the list of Teams sites that have federated external users.</span></span> <span data-ttu-id="47a7c-139">这些用户具有域名和/或未由你的组织拥有的 UPN 后缀。</span><span class="sxs-lookup"><span data-stu-id="47a7c-139">These users have a domain name and/or a UPN suffix that isn't owned by your organization.</span></span>

<span data-ttu-id="47a7c-140">在此示例查询中，组织拥有 contoso.com。</span><span class="sxs-lookup"><span data-stu-id="47a7c-140">In this example query, the organization owns contoso.com.</span></span>

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
> <span data-ttu-id="47a7c-141">若要深入了解 Teams 中的外部和来宾访问类型，请参阅 [与其他组织](communicate-with-users-from-other-organizations.md)的用户沟通"，或"Teams 安全指南"中的 [参与者](teams-security-guide.md#participant-types) 部分。</span><span class="sxs-lookup"><span data-stu-id="47a7c-141">To learn more about External and Guest access types in Teams see [Communicate with users from other organizations](communicate-with-users-from-other-organizations.md), or the [Participant Types](teams-security-guide.md#participant-types) section in the Teams Security Guide.</span></span>

### <a name="who-recently-joined--whose-role-changed"></a><span data-ttu-id="47a7c-142">最近加入/角色已更改的人员</span><span class="sxs-lookup"><span data-stu-id="47a7c-142">Who recently joined / Whose role changed</span></span>

<span data-ttu-id="47a7c-143">查询特定用户以了解他们是否是在最近 7 天或一周内添加到 Teams 频道的：</span><span class="sxs-lookup"><span data-stu-id="47a7c-143">Query a specific user to check if they were added to a Teams channel in the last seven days, or within a week:</span></span>

```Kusto
OfficeActivity
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberAdded"
| where Members has "<DisplayName>" or Members has "<UserPrincipalName>"
| project TeamName, Operation, UserId, Members
```

<span data-ttu-id="47a7c-144">查询用户的角色是否过去七天内为团队发生更改：</span><span class="sxs-lookup"><span data-stu-id="47a7c-144">Query whether a user's role changed for a Team in the last seven days:</span></span>

```Kusto
OfficeActivity
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberRoleChanged"
| project TeamName, Operation, UserId, Members
| mv-expand bagexpansion=array Members
| evaluate bag_unpack(Members)
| where Role == '1'
``` 

### <a name="external-users-from-unknown-or-new-organizations"></a><span data-ttu-id="47a7c-145">来自未知组织或新组织的外部用户</span><span class="sxs-lookup"><span data-stu-id="47a7c-145">External users from unknown or new organizations</span></span>

<span data-ttu-id="47a7c-146">在 Teams 中，可将外部用户添加到你的环境或频道。</span><span class="sxs-lookup"><span data-stu-id="47a7c-146">In Teams, you can add external users to your environment or channels.</span></span> <span data-ttu-id="47a7c-147">组织通常具有数量有限的关键合作伙伴关系，并从这些合作伙伴中添加用户。</span><span class="sxs-lookup"><span data-stu-id="47a7c-147">Organizations often have a limited number of key partnerships and add users from among these partners.</span></span> <span data-ttu-id="47a7c-148">此 KQL 会查看添加到团队的外部用户，这些用户来自之前没有见过或添加过的组织。</span><span class="sxs-lookup"><span data-stu-id="47a7c-148">This KQL looks at external users added to teams who come from organizations that haven't been seen or added before.</span></span>

<span data-ttu-id="47a7c-149">有关详细信息，请参阅 Azure Sentinel 社区 [git 中心网站中的查询](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/ExternalUserFromNewOrgAddedToTeams.yaml)。</span><span class="sxs-lookup"><span data-stu-id="47a7c-149">For more information, see the query in the [Azure Sentinel community git hub](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/ExternalUserFromNewOrgAddedToTeams.yaml).</span></span>

### <a name="external-users-who-were-added-and-then-removed"></a><span data-ttu-id="47a7c-150">添加后又删除的外部用户</span><span class="sxs-lookup"><span data-stu-id="47a7c-150">External users who were added and then removed</span></span>

<span data-ttu-id="47a7c-151">具有一定程度的现有访问权限的攻击者可能会向 Teams 添加一个新的外部帐户，以便访问和窃取数据。</span><span class="sxs-lookup"><span data-stu-id="47a7c-151">Attackers with some level of existing access may add a new external account to Teams to access and exfiltrate data.</span></span> <span data-ttu-id="47a7c-152">他们还可能会快速删除该用户，以隐藏他们进行了访问的事实。</span><span class="sxs-lookup"><span data-stu-id="47a7c-152">They may also quickly remove that user to hide that they made access.</span></span> <span data-ttu-id="47a7c-153">此查询将搜寻添加到 Teams 中后迅速删除的外部帐户，以帮助识别可疑行为。</span><span class="sxs-lookup"><span data-stu-id="47a7c-153">This query hunts for external accounts that are added to Teams and swiftly removed to help identify suspicious behavior.</span></span>

<span data-ttu-id="47a7c-154">有关详细信息，请参阅 Azure Sentinel 社区 [git 中心网站中的查询](https://github.com/Azure/Azure-Sentinel/blob/master/Detections/OfficeActivity/ExternalUserAddedRemovedInTeams.yaml)。</span><span class="sxs-lookup"><span data-stu-id="47a7c-154">For more information, see the query in the [Azure Sentinel community git hub](https://github.com/Azure/Azure-Sentinel/blob/master/Detections/OfficeActivity/ExternalUserAddedRemovedInTeams.yaml).</span></span>

### <a name="new-bot-or-application-added"></a><span data-ttu-id="47a7c-155">添加了新的机器人或应用程序</span><span class="sxs-lookup"><span data-stu-id="47a7c-155">New bot or application added</span></span>

<span data-ttu-id="47a7c-156">团队可在团队中包括应用或机器人以扩展功能集（包括自定义应用和自动程序）。</span><span class="sxs-lookup"><span data-stu-id="47a7c-156">Teams can include apps or bots in a Team to extend the feature set (including custom apps and bots).</span></span> <span data-ttu-id="47a7c-157">在某些情况下，应用或自动程序可用于在 Teams *暂留* ，而无需用户帐户，并且可以访问文件和其他数据。</span><span class="sxs-lookup"><span data-stu-id="47a7c-157">In some cases, an app or bot can be used for *persistence* in Teams without needing a user account, and can access files and other data.</span></span> <span data-ttu-id="47a7c-158">此查询会搜寻 Teams 中新增的应用或机器人。</span><span class="sxs-lookup"><span data-stu-id="47a7c-158">This query hunts for apps or bots that are new to Teams.</span></span>

<span data-ttu-id="47a7c-159">有关详细信息，请参阅 Azure Sentinel 社区 [git 中心网站中的查询](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/NewBotAddedToTeams.yaml)。</span><span class="sxs-lookup"><span data-stu-id="47a7c-159">For more information, see the query in the [Azure Sentinel community git hub](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/NewBotAddedToTeams.yaml).</span></span>

### <a name="user-accounts-who-are-owners-of-large-numbers-of-teams"></a><span data-ttu-id="47a7c-160">拥有大量 Teams 的用户帐户</span><span class="sxs-lookup"><span data-stu-id="47a7c-160">User accounts who are Owners of large numbers of Teams</span></span>

<span data-ttu-id="47a7c-161">想要提升特权的攻击者可能会为大量不同团队分配所有者权限。</span><span class="sxs-lookup"><span data-stu-id="47a7c-161">Attackers looking to elevate their privileges may assign themselves Owner privileges of a large number of diverse teams.</span></span> <span data-ttu-id="47a7c-162">*通常*，用户围绕特定主题创建并拥有一些团队。</span><span class="sxs-lookup"><span data-stu-id="47a7c-162">*Usually*, users create and own a few teams around specific topics.</span></span> <span data-ttu-id="47a7c-163">此 KQL 查询可查找可疑行为。</span><span class="sxs-lookup"><span data-stu-id="47a7c-163">This KQL query looks for suspicious behavior.</span></span>

<span data-ttu-id="47a7c-164">有关详细信息，请参阅 Azure Sentinel 社区 [git 中心网站中的查询](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/MultiTeamOwner.yaml)。</span><span class="sxs-lookup"><span data-stu-id="47a7c-164">For more information, see the query in the [Azure Sentinel community git hub](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/MultiTeamOwner.yaml).</span></span>

### <a name="many-team-deletions-by-a-single-user"></a><span data-ttu-id="47a7c-165">单个用户删除多个团队</span><span class="sxs-lookup"><span data-stu-id="47a7c-165">Many Team deletions by a single user</span></span>

<span data-ttu-id="47a7c-166">攻击者可以通过删除多个团队来造成中断并危及项目和数据。</span><span class="sxs-lookup"><span data-stu-id="47a7c-166">Attackers can cause disruptions and jeopardize projects and data by deleting multiple teams.</span></span> <span data-ttu-id="47a7c-167">由于团队通常由单个所有者删除，因此集中删除许多团队可能是问题之一。</span><span class="sxs-lookup"><span data-stu-id="47a7c-167">Since teams are usually deleted by individual Owners, central deletion of many teams can be a sign of trouble.</span></span> <span data-ttu-id="47a7c-168">此 KQL 可查找删除了多个团队的单个用户。</span><span class="sxs-lookup"><span data-stu-id="47a7c-168">This KQL looks for single users who delete multiple teams.</span></span>

<span data-ttu-id="47a7c-169">有关详细信息，请参阅 Azure Sentinel 社区 [git 中心网站中的查询](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/MultipleTeamsDeletes.yaml)。</span><span class="sxs-lookup"><span data-stu-id="47a7c-169">For more information, see the query in the [Azure Sentinel community git hub](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/MultipleTeamsDeletes.yaml).</span></span>

### <a name="expanding-your-threat-hunting-opportunities"></a><span data-ttu-id="47a7c-170">扩大你的线程搜寻机会</span><span class="sxs-lookup"><span data-stu-id="47a7c-170">Expanding your threat hunting opportunities</span></span>

<span data-ttu-id="47a7c-171">组合来自 Azure Active Directory （Azure AD） 或其他 Office 365 工作负荷等资源查询可以与 Teams 查询一起使用。</span><span class="sxs-lookup"><span data-stu-id="47a7c-171">Combining queries from resources like Azure Active Directory (Azure AD), or other Office 365 workloads can be used with Teams queries.</span></span> <span data-ttu-id="47a7c-172">例如，组合检测 Azure AD SigninLogs 中的可疑模式，并使用该输出，同时搜索团队所有者。</span><span class="sxs-lookup"><span data-stu-id="47a7c-172">For example, combine the detection of suspicious patterns in Azure AD SigninLogs, and use that output while hunting for Team Owners.</span></span>

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

<span data-ttu-id="47a7c-173">此外，你还可以使用以下方法为仅基于 Teams 的登录添加筛选器，将 SigninLogs 检测设置为特定于 Teams：</span><span class="sxs-lookup"><span data-stu-id="47a7c-173">Also, you can make the SigninLogs detections specific to Teams by adding a filter for only Teams-based logons by using:</span></span>

```Kusto
| where AppDisplayName has 'Teams'
```

<span data-ttu-id="47a7c-174">为了帮助说明 *AppDisplayName在哪里进一步使用Teams*，您在下面看到的KQL演示了从一个IP地址成功登录，而从另一个IP地址失败，但 *仅* 限于Teams登录的情况：</span><span class="sxs-lookup"><span data-stu-id="47a7c-174">To help explain using *where AppDisplayName has Teams* further, the KQL you see below demonstrates a successful logon from one IP address with failure from a different IP address, but scoped to *only* Teams sign-ins:</span></span>

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

## <a name="important-information-and-updates"></a><span data-ttu-id="47a7c-175">重要信息和更新</span><span class="sxs-lookup"><span data-stu-id="47a7c-175">Important information and updates</span></span>

<span data-ttu-id="47a7c-176">**感谢你们的内容协作，Pete Bryan、Nicholas DiCola 和 Matthew Lowe。**</span><span class="sxs-lookup"><span data-stu-id="47a7c-176">**Thank you for content collaboration, Pete Bryan, Nicholas DiCola, and Matthew Lowe.**</span></span> <span data-ttu-id="47a7c-177">牛娇和合作人员继续为 Teams 开发检测和查询查询。</span><span class="sxs-lookup"><span data-stu-id="47a7c-177">Pete Bryan, and people he collaborates with, continue to develop detection and hunting queries for Teams.</span></span>

<span data-ttu-id="47a7c-178">使用 Git Hub [更新](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/TeamsLogs) 保持联络。</span><span class="sxs-lookup"><span data-stu-id="47a7c-178">Stay in touch with this [Git Hub](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/TeamsLogs) repository for updates.</span></span>

<span data-ttu-id="47a7c-179">监控本文中使用的[分析器](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt)和[逻辑应用](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data)的更新。</span><span class="sxs-lookup"><span data-stu-id="47a7c-179">Watch for updates to the [parser](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt) and [logic app](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) used in this article.</span></span>

<span data-ttu-id="47a7c-180">你也可以加入并参与 [Azure Sentinel 社区](https://github.com/Azure/Azure-Sentinel/wiki)。</span><span class="sxs-lookup"><span data-stu-id="47a7c-180">You should also join (and contribute to) the [Azure Sentinel community](https://github.com/Azure/Azure-Sentinel/wiki).</span></span> <span data-ttu-id="47a7c-181">我们正在积极寻找有关本文的反馈，因此请使用下面的反馈选项。</span><span class="sxs-lookup"><span data-stu-id="47a7c-181">We are actively looking for feedback on this article, so please use the feedback option below.</span></span> <span data-ttu-id="47a7c-182">谢谢，快乐你。</span><span class="sxs-lookup"><span data-stu-id="47a7c-182">Thank you & Happy hunting.</span></span>

[<span data-ttu-id="47a7c-183">在 Azure AD 中注册应用程序</span><span class="sxs-lookup"><span data-stu-id="47a7c-183">Registering your application in Azure AD</span></span>](/skype-sdk/ucwa/registeringyourapplicationinazuread%C2%A0%20%20%C2%A0)

[<span data-ttu-id="47a7c-184">启用或禁用审核日志搜索</span><span class="sxs-lookup"><span data-stu-id="47a7c-184">Turn audit log search on or off</span></span>](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off)

[<span data-ttu-id="47a7c-185">什么是 Azure Sentinel?</span><span class="sxs-lookup"><span data-stu-id="47a7c-185">What is Azure Sentinel?</span></span>](/azure/sentinel/overview)
