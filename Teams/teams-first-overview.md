---
title: 首先Microsoft Teams
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
description: 使用本指南将 Microsoft Teams作为第一个Microsoft 365或Office 365工作负荷。
ROBOTS: NOINDEX, NOFOLLOW
appliesto:
- Microsoft Teams
ms.openlocfilehash: ddc107db668a582ad164e20f3b3ded169bd5d86125d949fe45d4d2f89090a8f7
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54312570"
---
# <a name="roll-out-microsoft-teams-first"></a>首先Microsoft Teams

Microsoft Teams可帮助员工保持联系和协作，尤其是在当前前所未有的时间，远程工作是世界各地员工的真实现实。 能够聊天、召开视频会议和协作处理Office文档Teams可帮助公司保持高效。 无论是小型企业、非营利组织还是大型组织，都可以先将 Teams 作为 Microsoft 365 或 Office 365 套件中的第一个工作负荷开始使用，然后再部署任何其他 Office 应用 或服务。

本文详细介绍了使用"第一步"方法Teams注意事项。

> [!IMPORTANT]
> 尽管Teams可能是组织的第一个云部署工作负荷，但部署Teams应是总体云部署策略的一部分。

如果已推出其他 Microsoft 365 或 Office 365 服务，Teams 是下一个要推出 (而不是第一个) 的工作负荷，请从如何推出 Teams[开始](./deploy-overview.md)。

## <a name="start-here"></a>从这里开始

若要开始使用 Teams第一个部署，至少需要满足一些先决条件。 以下列表将显示为组织设置的位置，才能启用Teams功能：

1.  已Microsoft 365域名Office 365组织或组织

2.  Azure Active Directory AAD (连接) 或类似云标识同步解决方案 - 所有必需属性与租户同步  
    若要了解与 AAD 同步同步的属性，请阅读[Azure AD 连接同步：同步](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)到 Azure Active Directory

3.  为用户分配了相应的用户Teams  
    若要了解Teams，请阅读Microsoft Teams[说明。](/office365/servicedescriptions/teams-service-description)

4.  组织的网络已准备好用于Teams  
    若要了解网络准备，请阅读[准备组织的网络以Teams。](prepare-network.md)

5.  允许网络访问 Exchange、Sharepoint 和 OneDrive for Business 或 Microsoft 365 Office 365：Office 365 URL 和 IP[地址范围](/office365/enterprise/urls-and-ip-address-ranges)。

> [!NOTE]
> 在 2019 年 9 月 1 日之后创建的租户在"仅Teams模式下预配。
> 
> [!IMPORTANT]
> 如果已Skype for Business Server，且租户是在 2019 年 9 月 1 日之后预配的，请联系支持人员以启用 Teams。 请确保将"组织范围的升级策略"设置为"岛模式"，然后再Teams<span class="underline"></span>许可证。

## <a name="migration-starting-points"></a>迁移起点

您到 Microsoft 365 Office 365 以及 Teams 中可用的功能之旅，具体取决于您的起点以及本地 Skype for Business 或 Lync 服务器的存在。 除了上述先决条件外，以下部分还将详细介绍基本功能和配置选项。 我们已将起点方案细分为以下主题：

**租户Teams配置**：租户和用户模式用于控制收件人的行为。 可以在租户级别或组织中用户级别分配这些设置。 若要了解有关详细信息，请阅读[与 Skype for Business](coexistence-chat-calls-presence.md)共存。

**聊天/外部** 通信Teams：聊天服务是指与组织内部或组织外部的对等或群组聊天对话。 外部通信也称为联合身份验证Skype for Business。

**在 Teams** 创建和查看会议：用户始终可以通过 Outlook Teams 加载项创建联机会议，在用户获得许可后，PSTN 拨入功能在所有方案中均可用。 Teams Skype for Business将日历信息存储在用户的邮箱中Exchange信息。 本地Exchange服务器必须Exchange Server 2016 CU3 或Teams客户端才能与用户的邮箱交互。 如果不Exchange邮箱访问，Teams日历图标将不会显示，并且用户将无法在 Teams 客户端中查看、创建或修改会议。

呼叫功能 Teams 中的 **VoIP/PSTN：** 呼叫可以是通过 IP (VoIP) 或 PSTN (电话) 。 VoIP 连接在客户端Teams本机发生，而 PSTN 连接发生在用户拨打外部电话号码时。  

Teams支持两种类型的 PSTN 连接。 Microsoft 呼叫计划：当 Microsoft 提供电话基础结构（包括用户的电话号码）或直接路由配置时，客户通过会话边界控制器 (SBC) 为 Teams 用户提供电话连接。  
若要了解有关详细信息，请阅读[哪种呼叫计划适合你？电话系统](calling-plan-landing-page.md)[直接路由"](direct-routing-landing-page.md)。

**Teams团队** 协作和频道Teams：在Teams，团队是一组为了工作、项目或共同兴趣而聚在一起的人。 Teams由通道决定。 每个频道围绕主题构建，例如"团队事件"、部门名称或只是为了娱乐。 频道是一起召开会议、进行对话以及处理文件的地方。 协作期间

OneDrive for Business (Teams 中的 **) P2P** 文件共享：在 Teams 和频道之外，Teams 用户可以使用 OneDrive for business 或其他 P2P 共享文件程序（如 Citrix 文件、DropBox、Box 和 Google 云端硬盘）对等共享文件。 对于OneDrive，用户必须分配有SharePoint Online 许可证。

**应用程序** 平台：应用为组织提供开箱即用的工具，以进一步Teams。 这些应用结合了由 Microsoft 提供的选项卡、消息传送扩展、连接器和机器人的功能，这些功能由第三方构建，或者由组织中的开发人员提供。

安全性和符合性 **功能：Teams** 提供广泛的信息来帮助你处理合规性领域，包括保留策略、数据丢失防护 (DLP) 、电子数据展示和通道、聊天和文件法定保留、审核日志 搜索。 若要了解有关详细信息，请阅读[中的安全性和](security-compliance-overview.md)Microsoft Teams。  

> [!NOTE]
> 高级电子数据展示功能需要 E5 许可。

[比较许可选项](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)。

阅读[Exchange Microsoft Teams](exchange-teams-interact.md)交互，了解方案中可用的符合性功能。

## <a name="organizations-span-classunderlinewithoutspan-skype-for-business-or-lync-server"></a>没有 **<span class="underline">Skype for Business</span>** Lync Server 的组织

此起点假定您的组织当前未使用 Skype for Business Lync Server，Teams将成为您的第一个应用程序，Microsoft 365或 Office 365。 下表详细介绍了核心服务高级配置和Teams功能。

<table>
<thead>
<tr class="header">
<th>项目</th>
<th>注释</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>租户Teams配置</td>
<td>Teams仅模式，所有聊天和通话功能都Teams模式。</td>
</tr>
<tr class="even">
<td>聊天/外部通信Teams</td>
<td><p>组织 (内部Microsoft 365 Office 365内部) 外部聊天通信可能来自Teams。</p>
<p><em>注意：必须为外部访问配置 DNS 条目。 Skype for Business即使你没有本地或 Skype for Business 或 Microsoft 365 或 Office 365，也需要 DNS 记录，以允许与 Lync 和 Skype for Business 环境联合：<br />
<a href="/office365/enterprise/external-domain-name-system-records">外部域名系统记录</a></em></p></td>
</tr>
<tr class="odd">
<td>在会议视图中创建和Teams</td>
<td><p>能够通过加载项创建内部和外部Outlook会议。</p>
<p>PSTN 拨入和拨出功能随音频会议许可证一起提供。</p>
<p>Teams日历访问Exchange 2016 CU3+ 本地部署并Exchange混合：使用混合配置向导创建<a href="/exchange/hybrid-deployment/deploy-hybrid">混合部署。</a> </p>

除了混合Exchange配置外，Exchange OAuth 身份验证：在组织与Exchange Exchange Online [OAuth 身份验证](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)。 

</p></td>
</tr>
<tr class="even">
<td>通话功能<br />
VoIP/PSTN Teams</td>
<td><p>可在租户内部和外部使用 VoIP。</p>
<p>PSTN 服务可以通过系统Microsoft 电话配置，还可以添加 Microsoft 呼叫计划或直接路由。</p></td>
</tr>
<tr class="odd">
<td>Teams和频道协作Teams</td>
<td><p>若要获得完整的体验（包括合规性功能SharePoint，需要向用户分配一个联机许可证。</p>
<p>无需迁移现有的本地SharePoint站点。</p></td>
</tr>
<tr class="even">
<td>OneDrive for Business (P2P 文件共享) </td>
<td>OneDrive for Business要求用户分配SharePoint Online 许可证。 如果没有此许可证，将不可能进行对等文件共享。</td>
</tr>
<tr class="odd">
<td>应用程序平台</td>
<td>用户将能够使用根据公司策略为用户指定的应用。<br />
在此处了解有关详细信息：<a href="/microsoftteams/admin-settings">应用中应用的管理员Teams</a></td>
</tr>
<tr class="even">
<td>安全性和符合性功能</td>
<td><ul>
<li><p>保留策略可用。</p></li>
<li><p>支持电子数据展示和法定保留，以确保通道消息的符合性。</p></li>
<li><p>DLP (的) 策略可用。</p></li>
</ul>
<p>完整功能集可用于Exchange Online;Exchange本地部署支持大多数这些功能。 有关完整列表，请参阅如何<a href="/MicrosoftTeams/exchange-teams-interact">Exchange Teams交互</a>。</p></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-without-skype-for-business-or-lync-server"></a>为没有 Skype for Business Lync Server 的组织启用步骤

1.  满足上述"从此处开始"部分中详述的先决条件

2.  将租户切换到Teams仅 (租户的模式) 设置[：设置共存和升级设置](setting-your-coexistence-and-upgrade-settings.md)。

3.  根据公司的业务/公司策略配置租户：管理Microsoft Teams[设置](enable-features-office-365.md)。

4.  将Teams客户端部署到用户：[获取客户端Teams](get-clients.md)

5.  推动采用计划  
    [采用 Microsoft Teams](adopt-microsoft-teams-landing-page.md)
    
    [Microsoft Teams 采用快速入门清单](teams-adoption-quick-start-checklist.md)

6.  开始计划将其他工作负荷移动到Microsoft 365或Office 365

## <a name="organizations-span-classunderlinewithspan-skype-for-business-or-lync-server"></a>使用 **<span class="underline">Skype for Business</span>** Lync 服务器的组织

此起点假定您的组织使用 Skype for Business 2019、2015+ 或 Lync 2013+ 本地服务器。 我们已经为组织从本地服务器迁移到 Teams提供了广泛的指导，这些方案应该遵循这些指南。 本指南特定于以下方案：Teams是首次在应用或Microsoft 365 Office 365。 下表详细介绍了核心服务高级配置和Teams功能。

<table>
<thead>
<tr class="header">
<th>项目</th>
<th>注释</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>租户Teams配置</td>
<td>岛屿模式。</td>
</tr>
<tr class="even">
<td>聊天/外部通信Teams</td>
<td>仅在您自己的租户内部，外部通信 (联合) 通过您的 Skype for Business Lync 服务器部署。</td>
</tr>
<tr class="odd">
<td>在会议视图中创建和Teams</td>
<td><p>能够通过加载项创建内部和外部Outlook会议。</p>
<p>PSTN 拨入和拨出功能随音频会议许可证一起提供。</p>
<p>Teams日历访问Exchange 2016 CU3+ 本地部署，并且Exchange混合：<br />
<a href="/exchange/hybrid-deployment/deploy-hybrid">使用混合配置向导创建混合部署。</a></p>
<p>管理员可以 Skype for Business Outlook通过 Teams 会议策略的 PreferredMeetingProviderForIslandsMode 属性<a href="/powershell/module/skype/set-csteamsmeetingpolicy">set-csteamsmeetingpolicy</a>控制该加载项。</p> 
</td>
</tr>
<tr class="even">
<td>通话功能<br />
VoIP/PSTN Teams</td>
<td><p>可在租户内部使用 VoIP。</p>
<p>PSTN 或呼叫计划服务在用户移动到仅Teams之前不可用。</p></td>
</tr>
<tr class="odd">
<td>Teams和频道协作Teams</td>
<td><p>若要获得完整的体验（包括合规性功能SharePoint，需要向用户分配一个联机许可证。</p>
<p>无需迁移现有的本地SharePoint站点。</p></td>
</tr>
<tr class="even">
<td>OneDrive for Business (P2P 文件共享) </td>
<td>OneDrive for Business要求用户分配SharePoint Online 许可证。 如果没有此许可证，将不可能进行每对等文件共享。</td>
</tr>
<tr class="odd">
<td>应用程序平台</td>
<td>用户将能够使用根据公司策略为用户指定的应用。<br />
在此处了解有关详细信息：<a href="/microsoftteams/admin-settings">应用中应用的管理员Teams</a></td>
</tr>
<tr class="even">
<td>安全性和符合性功能</td>
<td><ul>
<li><p>保留策略可用。</p></li>
<li><p>支持电子数据展示和法定保留，以确保通道消息的符合性。</p></li>
<li><p>DLP (的) 策略可用。</p></li>
</ul>
<p>完整功能集可用于Exchange Online;Exchange本地部署支持大多数这些功能。 有关完整列表，请参阅如何<a href="/MicrosoftTeams/exchange-teams-interact">Exchange Teams交互。</a></p>
<ul>
</ul></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-with-skype-for-business-server"></a>为具有以下功能的组织启用Skype for Business Server  

1.  满足上述"从此处开始"部分中详述的先决条件。

2.  对于在 2019 年 9 月 1 (预配的租户，请将租户切换为"群岛模式"模式，请联系支持人员)   
    [设置共存和升级设置](setting-your-coexistence-and-upgrade-settings.md)

3.  根据公司的业务/公司策略配置租户  
    [为你的组织管理 Microsoft Teams 设置](enable-features-office-365.md)

4.  部署 Teams 客户端  
    [获取 Teams 客户端](get-clients.md)

5.   推动采用计划  
    [采用 Microsoft Teams](adopt-microsoft-teams-landing-page.md)<br/>
    [Microsoft Teams 采用快速入门清单](teams-adoption-quick-start-checklist.md)

6.  开始计划将其他工作负荷移动到Microsoft 365或Office 365

7.  建立Skype for Business混合，并遵循针对 Skype for Business 和 Lync 服务器的建议升级路径  
    [从Skype for Business本地升级到 Teams](upgrade-to-teams-execute-skypeforbusinesshybridonprem.md)

## <a name="closing-statement"></a>结束语句

Microsoft Teams组织能够将所有员工、信息工作者和一线员工汇集在一个平台上。 你可以 [从今天开始](https://products.office.com/microsoft-teams/group-chat-software) 。 你可以在此处联系我们的所有最新公告和每月产品 [更新](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog)。

此外，随着世界各地的公司正在管理当前的 COVID-19 情况，我们创建了一系列内容来帮助你利用 Teams，以在组织中产生最大影响。

  - 我们在[COVID-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)期间为客户提供的承诺

  - [2 周内：我们已了解远程工作](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/18/making-the-switch-to-remote-work-5-things-weve-learned/)

  - [传送联机会议和事件](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/delivering-online-meetings-events/)

  - [协助中小型企业使用 Teams 远程工作](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/helping-smb-customers-work-remotely-microsoft-teams/)

  - [实时事件的数字化转换：Bob Bejan 从一线观察结果](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/13/digital-transformation-live-events-bob-bejans-observations-frontline/)

  - [Microsoft IT 便于员工远程工作的 9 大方式](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/top-9-ways-microsoft-it-enabling-remote-work-employees/)

  - [远程工作，保持安全 - 有关 CISOS 的提示](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/work-remotely-stay-secure-ciso-tips/)

  - [帮助教师和学生转换远程学习](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/11/helping-teachers-students-switch-remote-learning/)

  - [使用远程处理设备时保持Microsoft Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/)

## <a name="support-services-reference"></a>支持服务参考

Teams依赖于 Exchange Online、SharePoint Online、OneDrive for Business Microsoft 365 组为用户提供完全集成的 Microsoft 365 或 Office 365 体验。 如上所述，Teams完全部署这些服务（功能有限）即可正常工作。 可以在此处阅读有关Teams及其先决条件的更多信息：[欢迎使用 Teams。](teams-overview.md)

有关上面列出的每个服务的详细信息，请访问以下链接：

  - Exchange Online用于日历功能，以及将对等消息存储在 Teams。 有关详细信息，请阅读如何[Exchange Teams交互](exchange-teams-interact.md)

> [!IMPORTANT]
> 若要Teams本地 Exchange 的互操作，必须配置新的 Exchange OAuth 身份验证协议，如在 Exchange 和 Exchange Online 组织之间配置[OAuth](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)身份验证中所述。

  - SharePoint用于频道中的文件共享，而 /OneDrive for Business 用于 1：1 或群组聊天中的文件共享。 若要了解有关详细信息，请阅读[如何SharePoint联机OneDrive for Business如何与 Microsoft Teams](sharepoint-onedrive-interact.md)交互。

  - [Microsoft 365组](office-365-groups.md)用于团队和频道创建/管理。


## <a name="related-topics"></a>相关主题

[Microsoft Teams IT 体系结构和电话解决方案海报](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)

[规划 Skype for Business Server 与 Office 365 之间的混合连接](/SkypeForBusiness/hybrid/plan-hybrid-connectivity)

[使用远程工作程序支持Teams](support-remote-work-with-teams.md)

[远程处理Microsoft 365](https://aka.ms/remote-work)
