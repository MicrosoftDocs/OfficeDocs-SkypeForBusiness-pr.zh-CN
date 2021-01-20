---
title: 推出 Microsoft Teams First
author: LaszloSomi
ms.author: lsomi
manager: swerth
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: lsomi
localization_priority: Normal
search.appverid: MET150
description: 使用本指南将 Microsoft Teams 作为第一个 Microsoft 365 或 Office 365 工作负荷推出。
ROBOTS: NOINDEX, NOFOLLOW
appliesto:
- Microsoft Teams
ms.openlocfilehash: a30d5bed9443df3077ab7384cd8266d2f049148d
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909476"
---
# <a name="roll-out-microsoft-teams-first"></a>推出 Microsoft Teams First

Microsoft Teams 可帮助你的员工保持联系并相互协作，尤其是在当前前所未有的时间，远程工作是世界各地的员工现实。 能够在 Teams 中聊天、召开视频会议和协作处理 Office 文档可帮助公司保持高效。 无论是小型企业、非营利组织还是大型组织，都可以在部署任何其他 Office 应用或服务之前，先将 Teams 用作 Microsoft 365 或 Office 365 套件中的第一个工作负荷。

本文详细介绍了使用"Teams First"方法必须考虑的注意事项。

> [!IMPORTANT]
> 虽然 Teams 可以是组织的第一个云部署工作负荷，但部署 Teams 应该是总体云部署策略的一部分。

如果已推出其他 Microsoft 365 或 Office 365 服务，而 Teams 是下一个要推出 (而不是第一个) 的工作负荷，请从"如何推出 [Teams"](How-to-roll-out-teams.md)开始。

## <a name="start-here"></a>从这里开始

若要开始使用 Teams First 部署，至少需要满足一些先决条件。 以下列表将显示在启用 Teams 之前，组织必须拥有哪些功能：

1.  使用域名配置的 Microsoft 365 或 Office 365 组织

2.  Azure Active Directory 连接 (AAD) 或类似云标识同步解决方案 - 所有必需属性与租户同步  
    若要了解与 AAD 同步同步的属性，请阅读 [Azure AD Connect 同步：同步到 Azure Active Directory 的属性](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)

3.  为 Teams 分配相应的用户许可证  
    若要了解 Teams 许可，请阅读 [Microsoft Teams 服务说明](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)。

4.  为 Teams 准备的组织网络  
    若要了解网络准备，请阅读["为 Teams 准备组织的网络"。](prepare-network.md)

5.  允许网络访问 Microsoft 365 或 Office 365 中的 Exchange、Sharepoint 和 OneDrive for [Business：Office 365 URL](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)和 IP 地址范围。

> [!NOTE]
> 在 2019 年 9 月 1 日之后创建的租户在"仅 Teams"模式下预配。
> 
> [!IMPORTANT]
> 如果你部署了 Skype for Business Server，并且你的租户是在 2019 年 9 月 1 日之后预配的，请联系支持人员为 Teams 启用共存功能。 在将任何 Teams 许可证分配给用户之前，请确保将"组织范围的<span class="underline"></span>升级策略"设置为"岛模式"。

## <a name="migration-starting-points"></a>迁移起点

你到 Microsoft 365 或 Office 365 之旅以及 Teams 中可用的功能，具体取决于起点以及本地 Skype for Business 或 Lync 服务器的存在。 除了上述先决条件外，以下部分还将详细介绍基本功能和配置选项。 我们已将起点方案细分为以下主题：

**租户团队配置**：租户和用户模式用于控制收件人的行为。 这些设置可以在组织的租户级别或用户级别分配。 若要了解有关详细信息，请阅读[与 Skype for Business 共存。](coexistence-chat-calls-presence.md)

**Teams 中的聊天/** 外部通信：聊天服务是指组织内部或组织外部的对等或群组聊天对话。 外部通信在 Skype for Business 中也称为联合。

**在 Teams 中** 创建和查看会议：用户始终可以通过 Outlook Teams 加载项创建联机会议，在用户获得许可后，PSTN 拨入功能在所有方案中均可用。 Teams 和 Skype for Business 将日历信息存储在用户的 Exchange 邮箱中。 本地 Exchange 服务器必须Exchange Server 2016 CU3 或更高层，Teams 客户端才能与用户的邮箱进行交互。 如果没有 Exchange 邮箱访问权限，Teams 中的日历图标将不会显示，并且用户将无法在 Teams 客户端中查看、创建或修改会议。

**Teams 中的呼叫功能 VoIP/PSTN：** 呼叫可以是通过 IP (VoIP) 语音呼叫或 PSTN (公用电话) 。 VoIP 连接在 Teams 客户端之间本机发生，而 PSTN 连接发生在用户拨打外部电话号码时。  

Teams 支持两种类型的 PSTN 连接。 Microsoft 呼叫计划，当 Microsoft 提供电话基础结构（包括用户的电话号码）或直接路由配置时，客户通过会话边界控制器 (SBC) 为 Teams 用户提供电话连接。  
若要了解有关详细信息，请阅读 [哪种呼叫计划适合你？](calling-plan-landing-page.md) 以及 [电话系统直接路由](direct-routing-landing-page.md)。

**Teams 中的团队和** 频道协作：在 Teams 中，团队是一组为了工作、项目或共同兴趣而聚在一起的人。 团队由频道决定。 每个频道围绕主题构建，例如"团队活动"、部门名称或只是为了娱乐。 频道是召开会议、进行对话以及一起处理文件的地方。 协作期间

Teams 中的 **OneDrive for Business (P2P** 文件共享) ：在 Teams 和频道之外，Teams 用户可以使用 OneDrive for Business 或其他 P2P 共享文件程序（如 Citrix 文件、DropBox、Box 和 Google Drive）进行文件对等共享。 对于 OneDrive for Business，用户必须分配有 SharePoint Online 许可证。

**应用程序** 平台：应用为组织提供可进一步利用 Teams 的开箱即用工具。 这些应用结合了由 Microsoft 提供、由第三方或组织中的开发人员提供的选项卡、消息传递扩展、连接器和机器人的功能。

**安全性和符合性功能：** Teams 提供大量信息来帮助你实现合规性，包括保留策略、数据丢失保护 (DLP) 、电子数据展示和通道、聊天和文件法定保留、审核日志搜索。 若要了解有关详细信息，请阅读 [Microsoft Teams 中的安全性和符合性](security-compliance-overview.md)。  

> [!NOTE]
> 高级电子数据展示功能需要 E5 许可。

[比较许可选项](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)。

阅读 [Exchange 和 Microsoft Teams 如何交互](exchange-teams-interact.md) ，了解在你的方案中可用的合规性功能。

## <a name="organizations-span-classunderlinewithoutspan-skype-for-business-or-lync-server"></a>没有 **<span class="underline"></span>** Skype for Business 或 Lync Server 的组织

此起点假定你的组织当前未使用 Skype for Business 或 Lync Server，而 Teams 将是 Microsoft 365 或 Office 365 中的第一个应用程序。 下表详细介绍了 Teams 的核心服务的高级别配置和最终用户功能。

<table>
<thead>
<tr class="header">
<th>项目</th>
<th>注释</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>租户团队配置</td>
<td>仅 Teams 模式，所有聊天和通话功能均在 Teams 中提供。</td>
</tr>
<tr class="even">
<td>Teams 中的聊天/外部通信</td>
<td><p>Microsoft (365 或 Office 365 组织内部的) 和来自 Teams 的外部聊天通信。</p>
<p><em>注意：必须为外部访问配置 DNS 条目。 即使你在本地或 Microsoft 365 或 Office 365 中没有 Skype for Business，也需要 Skype for Business DNS 记录，以允许与 Lync 和 Skype for Business 环境联合：<br />
<a href="https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records">外部域名系统记录</a></em></p></td>
</tr>
<tr class="odd">
<td>在 Teams 创建和查看会议</td>
<td><p>能够通过 Outlook 加载项创建内部和外部会议。</p>
<p>PSTN 拨入和拨出功能可用于音频会议许可证。</p>
<p>Teams 日历访问需要使用已建立 Exchange 混合部署的 Exchange 2016 CU3+ 本地：使用混合配置向导创建 <a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">混合部署。</a> </p>
<p>除了 Exchange 混合配置，还建立 Exchange OAuth 身份验证：在 Exchange 和 Exchange Online 组织之间 <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help"> 配置 OAuth 身份验证"。</p>

</p></td>
</tr>
<tr class="even">
<td>呼叫功能<br />
Teams 中的 VoIP/PSTN</td>
<td><p>可在租户内部和外部使用 VoIP。</p>
<p>PSTN 服务可以通过 Microsoft Phone 系统进行配置，还可以添加 Microsoft 呼叫计划或直接路由。</p></td>
</tr>
<tr class="odd">
<td>Teams 中的团队和频道协作</td>
<td><p>若要获得完整体验，包括合规性功能，需要将 SharePoint Online 许可证分配给用户。</p>
<p>不需要迁移现有的本地 SharePoint 网站。</p></td>
</tr>
<tr class="even">
<td>OneDrive for Business (P2P 文件共享) </td>
<td>OneDrive for Business 要求用户分配有 SharePoint Online 许可证。 如果没有此许可证，将不可能进行对等文件共享。</td>
</tr>
<tr class="odd">
<td>应用程序平台</td>
<td>用户将能够使用根据公司策略为用户指定的应用。<br />
在此处了解更多信息 <a href="https://docs.microsoft.com/microsoftteams/admin-settings">：Teams 中应用的管理员设置</a></td>
</tr>
<tr class="even">
<td>安全性和符合性功能</td>
<td><ul>
<li><p>保留策略可用。</p></li>
<li><p>支持电子数据展示和法定保留，以确保通道消息的符合性。</p></li>
<li><p>DLP (数据丢失防护) 可用。</p></li>
</ul>
<p>Exchange Online 提供的完整功能集;本地 Exchange 支持大多数这些功能。 有关完整列表，请参阅 <a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">Exchange 和 Teams 如何交互</a>。</p></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-without-skype-for-business-or-lync-server"></a>为没有 Skype for Business 或 Lync Server 的组织启用步骤

1.  满足上述"此处开始"部分中详述的先决条件

2.  将租户切换到仅针对现有租户 (Teams 模式) ： [设置共存和升级设置](setting-your-coexistence-and-upgrade-settings.md)。

3.  根据公司的业务/公司策略配置租户：管理组织的 Microsoft Teams [设置](enable-features-office-365.md)。

4.  将 Teams 客户端部署到用户： [获取 Teams 的客户端](get-clients.md)

5.  推动采用计划  
    [采用 Microsoft Teams](adopt-microsoft-teams-landing-page.md)
    
    [Microsoft Teams 采用快速入门清单](teams-adoption-quick-start-checklist.md)

6.  开始计划将其他工作负荷移动到 Microsoft 365 或 Office 365

## <a name="organizations-span-classunderlinewithspan-skype-for-business-or-lync-server"></a>使用 **<span class="underline"></span>** Skype for Business 或 Lync 服务器的组织

此起点假定你的组织使用本地 Skype for Business 2019、2015+ 或 Lync 2013+ 服务器。 我们已针对组织从本地服务器迁移到 Teams 提供了广泛的指导，这些方案应该遵循这些指南。 本指南特定于 Teams 是 Microsoft 365 或 Office 365 中利用的第一个应用程序的方案。 下表详细介绍了 Teams 的核心服务的高级别配置和最终用户功能。

<table>
<thead>
<tr class="header">
<th>项目</th>
<th>注释</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>租户团队配置</td>
<td>岛屿模式。</td>
</tr>
<tr class="even">
<td>Teams 中的聊天/外部通信</td>
<td>仅在你自己的租户内部，外部通信 (联合) 通过 Skype for Business 或 Lync 服务器部署进行。</td>
</tr>
<tr class="odd">
<td>在 Teams 创建和查看会议</td>
<td><p>能够通过 Outlook 加载项创建内部和外部会议。</p>
<p>PSTN 拨入和拨出功能可用于音频会议许可证。</p>
<p>Teams 日历访问要求使用 Exchange 混合部署 Exchange 2016 CU3+ 本地：<br />
<a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">使用混合配置向导创建混合部署。</a></p>
<p>管理员可以通过 Teams 会议策略的 PreferredMeetingProviderForIslandsMode 属性<a href="https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps"> set-csteamsmeetingpolicy</a>控制 Skype for Business Outlook 加载项。</p> 
</td>
</tr>
<tr class="even">
<td>呼叫功能<br />
Teams 中的 VoIP/PSTN</td>
<td><p>可在租户内部使用 VoIP。</p>
<p>PSTN 或呼叫计划服务在用户移动到"仅 Teams"体验之前不可用。</p></td>
</tr>
<tr class="odd">
<td>Teams 中的团队和频道协作</td>
<td><p>若要获得完整体验，包括合规性功能，需要将 SharePoint Online 许可证分配给用户。</p>
<p>不需要迁移现有的本地 SharePoint 网站。</p></td>
</tr>
<tr class="even">
<td>OneDrive for Business (P2P 文件共享) </td>
<td>OneDrive for Business 要求用户分配有 SharePoint Online 许可证。 如果没有此许可证，将不可能进行按对等文件共享。</td>
</tr>
<tr class="odd">
<td>应用程序平台</td>
<td>用户将能够使用根据公司策略为用户指定的应用。<br />
在此处了解更多信息 <a href="https://docs.microsoft.com/microsoftteams/admin-settings">：Teams 中应用的管理员设置</a></td>
</tr>
<tr class="even">
<td>安全性和符合性功能</td>
<td><ul>
<li><p>保留策略可用。</p></li>
<li><p>支持电子数据展示和法定保留，以确保通道消息的符合性。</p></li>
<li><p>DLP (数据丢失防护) 可用。</p></li>
</ul>
<p>Exchange Online 提供的完整功能集;本地 Exchange 支持大多数这些功能。 有关完整列表，请参阅 <a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">Exchange 和 Teams 如何交互。</a></p>
<ul>
</ul></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-with-skype-for-business-server"></a>为使用 Skype for Business Server 的组织启用步骤  

1.  满足上述"此处开始"部分中详述的先决条件。

2.  对于 2019 年 9 月 1 日 (预配的租户，请将租户切换到群岛模式模式，请联系支持部门，)   
    [设置共存和升级设置](setting-your-coexistence-and-upgrade-settings.md)

3.  根据公司的业务/公司策略配置租户  
    [为你的组织管理 Microsoft Teams 设置](enable-features-office-365.md)

4.  部署 Teams 客户端  
    [获取 Teams 客户端](get-clients.md)

5.   推动采用计划  
    [采用 Microsoft Teams](adopt-microsoft-teams-landing-page.md)<br/>
    [Microsoft Teams 采用快速入门清单](teams-adoption-quick-start-checklist.md)

6.  开始计划将其他工作负荷移动到 Microsoft 365 或 Office 365

7.  建立 Skype for Business 混合并遵循 Skype for Business 和 Lync 服务器的建议升级路径  
    [从本地 Skype for Business 升级到 Teams](upgrade-to-teams-execute-skypeforbusinesshybridonprem.md)

## <a name="closing-statement"></a>结束语句

Microsoft Teams 可以是组织在单个平台上将所有员工、信息工作者和一线工作者汇集在一起的一个促成工具。 你可以 [从今天开始](https://products.office.com/microsoft-teams/group-chat-software) 。 你可以在此处随时了解我们的最新公告和每月产品 [更新](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog)。

此外，由于世界各地的公司正在管理当前的 COVID-19 情况，我们创建了一系列内容，可帮助你利用 Teams 在组织中实现最大影响。

  - 我们在[COVID-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)期间为客户提供的承诺

  - [2 周后：我们已了解远程工作](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/18/making-the-switch-to-remote-work-5-things-weve-learned/)

  - [传送联机会议和事件](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/delivering-online-meetings-events/)

  - [协助中小型企业使用 Teams 远程工作](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/helping-smb-customers-work-remotely-microsoft-teams/)

  - [实时事件的数字化转换：Bob Be在一线观察结果](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/13/digital-transformation-live-events-bob-bejans-observations-frontline/)

  - [Microsoft IT 便于员工远程工作的 9 大方式](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/top-9-ways-microsoft-it-enabling-remote-work-employees/)

  - [远程工作，保持安全 — CISOS 提示](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/work-remotely-stay-secure-ciso-tips/)

  - [帮助教师和学生转换到远程学习](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/11/helping-teachers-students-switch-remote-learning/)

  - [在远程使用 Microsoft Teams 时保持高效](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/)

## <a name="support-services-reference"></a>支持服务参考

Teams 依赖 Exchange Online、SharePoint Online、OneDrive for Business 和 Microsoft 365 组为用户提供完全集成的 Microsoft 365 或 Office 365 体验。 如上所述，Teams 在未完全部署这些服务的情况下工作 - 功能有限。 可在此处阅读有关 Teams 及其先决条件的更多信息：[欢迎使用 Teams。](teams-overview.md)

有关上面列出的每个服务的详细信息，请访问以下链接：

  - Exchange Online 用于在 Teams 中存储日历功能和存储对等消息。 若要了解更多信息，请阅读 [Exchange 和 Teams 如何交互](exchange-teams-interact.md)

> [!IMPORTANT]
> 对于 Teams 与 Exchange 本地的互操作，必须配置新的 Exchange OAuth 身份验证协议，如在 Exchange 和 Exchange Online 组织之间配置 [OAuth 身份验证中所述](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)。

  - SharePoint 用于频道中的文件共享，而 /OneDrive for Business 用于在 1：1 或群组聊天中共享文件。 若要了解有关详细信息，请阅读 [SharePoint Online 和 OneDrive for Business 如何与 Microsoft Teams 交互](sharepoint-onedrive-interact.md)。

  - [Microsoft 365 组](office-365-groups.md) 用于团队和频道创建/管理。


## <a name="related-topics"></a>相关主题

[Microsoft Teams IT 体系结构和电话解决方案海报](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)

[规划 Skype for Business Server 与 Office 365 之间的混合连接](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity)

[使用 Teams 支持远程工作者](support-remote-work-with-teams.md)

[使用 Microsoft 365 远程工作](https://aka.ms/remote-work)
