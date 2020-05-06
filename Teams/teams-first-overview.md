---
title: 首先部署 Microsoft 团队
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
description: 使用本指南可以将 Microsoft 团队作为您的第一个 Office 365 工作负荷。
ROBOTS: NOINDEX, NOFOLLOW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2cd8fc92d3f46df8bcfaa07a96b69b84790750aa
ms.sourcegitcommit: 09ff11f8e4f6a93cedc34a5d732a133163df79a0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/05/2020
ms.locfileid: "44041709"
---
# <a name="roll-out-microsoft-teams-first"></a>首先部署 Microsoft 团队

Microsoft 团队可以帮助你的员工彼此保持联系并协作，尤其是在当前空前的时间，远程工作是世界各地员工的现实。 能够聊天、进行视频会议和协作处理团队中的 Office 文档可帮助公司保持高效。 无论您是小型企业、非盈利性组织还是大型组织，您都可以在部署任何其他 Office 应用或服务之前，开始将团队作为 Office 365 套件中的第一工作负荷。

本文详细介绍了 "团队优先" 方法中必须执行的注意事项。

> [!IMPORTANT]
> 尽管团队可以是你的组织的第一个云部署工作负载，但部署团队应该是整体云部署策略的一部分。

如果你已推出其他 Office 365 服务，并且团队是你要推出的下一个工作负荷（而不是第一个），请首先向[团队推出](How-to-roll-out-teams.md)。

## <a name="start-here"></a>从这里开始

若要开始使用你的团队首次部署，你需要至少满足某些预备先决条件。 以下列表将显示在启用团队之前你必须为你的组织设置的内容：

1.  使用您的域名配置的 Office 365 组织

2.  Azure Active Directory 连接（AAD connect）或类似的云标识同步解决方案-与你的租户同步的所有必需属性  
    若要了解与 AAD 同步同步的属性，请参阅[AZURE AD Connect 同步：属性同步到 Azure Active Directory](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)

3.  为团队分配的相应用户许可证  
    若要了解团队许可，请阅读[Microsoft 团队服务说明](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)。

4.  为团队准备的组织网络  
    若要了解网络准备，请阅读为[团队准备组织的网络](prepare-network.md)。

5.  允许 Office 365 中的 Exchange、Sharepoint 和 OneDrive for business 的网络访问： [office 365 url 和 IP 地址范围](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)。

> [!NOTE]
> 在2019年9月1日之后创建的租户将在 "仅团队" 模式下预配。
> 
> [!IMPORTANT]
> 如果你已部署 Skype for Business 服务器，并且你的租户是在2019年9月1日之后预配的，请联系支持人员以启用团队的共存功能。 在向用户分配任何团队许可证<span class="underline">之前</span>，请确保 "组织范围升级策略" 已设置为 "安全岛模式"。

## <a name="migration-starting-points"></a>迁移起始点

根据您的起点和在本地 Skype for business 或 Lync server 的存在，您可以在团队中使用 Office 365 和功能。 除了上述先决条件之外，以下部分还将详细介绍基本功能和配置选项。 我们已将起始点方案分解为以下主题：

**租户团队配置**：租户和用户模式用于控制收件人的行为。 可以在组织中的租户级别或用户级别分配这些设置。 若要了解详细信息，请阅读[Skype For Business 共存](coexistence-chat-calls-presence.md)。

**团队中的聊天/外部通信**：聊天服务指的是与组织内或外部组织内的对等或群组聊天对话。 外部通信也称为 "Skype for Business" 中的联盟。

**在团队中创建和查看会议**：用户随时可以通过 Outlook 团队外接程序和 PSTN 拨入功能创建联机会议。一旦用户获得许可，即可在所有方案中使用。 用户的 Exchange 邮箱中的团队和 Skype for business 存储日历信息。 本地 Exchange server 必须是 Exchange Server 2016 CU3 或更高版本才能使团队客户能够与用户的邮箱交互。 没有 Exchange 邮箱访问时，不会显示团队中的日历图标，用户将无法在团队客户端中查看、创建或修改会议。

**呼叫功能团队中的 VoIP/PSTN**：通话可通过 IP 语音（VoIP）或公共交换电话网络（PSTN）进行。 VoIP 连接在团队客户端之间进行，而 PSTN 连接在用户拨打外部电话号码时才会发生。  

团队支持两种类型的 PSTN 连接。 Microsoft 通话计划-当 Microsoft 为团队用户提供电话服务基础结构（包括用户的电话号码）或直接路由配置时，客户通过会话边界控制器（SBC）为团队用户提供电话连接。  
若要了解详细信息，请阅读适合[你的呼叫计划？](calling-plan-landing-page.md)和[手机系统直接路由](direct-routing-landing-page.md)。

团队**中的团队和渠道协作**：在团队中，团队是为工作、项目或常见兴趣共同工作的人员组。 团队由频道组成。 每个频道都围绕一个主题构建，如 "团队活动"、"部门名称" 或 "只是有趣"。 频道是您在其中举行会议、进行对话和协同处理文件的地方。 协作期间

**工作组中的 OneDrive For business （P2P 文件共享）**：团队和频道外，团队用户可以使用 OneDrive for business 或其他 P2P 共享文件程序（如 Citrix 文件、DropBox、Box 和 Google 驱动器）共享文件对等。 对于 OneDrive for business，用户必须分配有 SharePoint Online 许可证。

**应用程序平台**：应用为你的组织提供现成的工具，以充分利用团队。 这些应用结合由 Microsoft （由第三方构建）或您的组织中的开发人员提供的选项卡、消息扩展、连接器和 bot 的功能。

**安全性和合规性功能：** 团队有大量信息可帮助您处理合规性领域，包括保留策略、数据丢失保护（DLP）、电子数据展示和用于频道、聊天和文件的法律封存、审核日志搜索。 若要了解详细信息，请阅读[Microsoft 团队中的安全和合规性](security-compliance-overview.md)。  

> [!NOTE]
> 提前的电子数据展示功能需要 E5 许可。

[比较授权选项](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)。

了解[Exchange 和 Microsoft 团队如何交互](exchange-teams-interact.md)，以了解你的方案中提供了哪些合规性功能。

## <a name="organizations-span-classunderlinewithoutspan-skype-for-business-or-lync-server"></a>**<span class="underline">没有</span>** Skype for Business 或 Lync 服务器的组织

此起始点假定你的组织不利用 Skype for Business 或 Lync server，当前和团队将是 Office 365 中的第一个应用程序。 下表详细介绍了适用于核心服务的团队的高级配置和最终用户功能。

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
<td>仅限工作组模式，所有聊天和通话功能仅在团队中</td>
</tr>
<tr class="even">
<td>团队中的聊天/外部通信</td>
<td><p>内部（Office 365 内部组织）和团队外部聊天通信</p>
<p><em>注意：必须为外部访问配置 DNS 条目。 即使您在本地或 Office 365 中没有 Skype for business，也可以使用 skype for business DNS 记录来允许与 Lync 和 Skype for business 环境进行联盟。<br />
<a href="https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records">Office 365 的外部域名系统记录</a></em></p></td>
</tr>
<tr class="odd">
<td><em>在团队中创建和查看会议</em></td>
<td><p><em>能够通过 Outlook 加载项创建会议</em></p>
<p><em>可通过音频会议许可证使用 PSTN 拨入和拨出功能。<br />
注意：团队日历访问需要部署了 exchange 2016 CU3 + 本地部署和已建立的 Exchange 混合版：<a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">使用混合配置向导创建混合部署</a><br />
除了 Exchange 混合配置之外，建立 Exchange OAuth 身份验证：在<a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help">Exchange 和 Exchange Online 组织之间配置 OAuth 身份验证</a></em></p></td>
</tr>
<tr class="even">
<td>通话功能<br />
团队中的 VoIP/PSTN</td>
<td><p>可在租户内部和外部使用 VoIP</p>
<p>PSTN 服务可以通过 Microsoft Phone 系统进行配置，还可以添加 Microsoft 通话计划或直接路由。</p></td>
</tr>
<tr class="odd">
<td>团队中的团队和渠道协作</td>
<td><p>若要获得完整体验，包括合规性功能，需要向用户分配 SharePoint Online 许可证。</p>
<p>不需要迁移现有的本地 SharePoint 网站。</p></td>
</tr>
<tr class="even">
<td>OneDrive for Business （P2P 文件共享）</td>
<td>OneDrive for business 要求用户分配有 SharePoint Online 许可证。 不能进行此类许可证对等文件共享。</td>
</tr>
<tr class="odd">
<td>应用程序平台</td>
<td>用户将能够根据你的公司策略使用指定的适用应用。<br />
在此了解详细信息：<a href="https://docs.microsoft.com/microsoftteams/admin-settings">团队中的应用的管理员设置</a></td>
</tr>
<tr class="even">
<td>安全性和合规性功能</td>
<td><ul>
<li><p>保留策略可用</p></li>
<li><p>支持针对频道消息的电子数据展示和法律封存</p></li>
<li><p>数据丢失防护策略（DLP）可用</p></li>
</ul>
<p>完整功能集通过 Exchange Online 提供，本地 Exchange 支持这些功能中的大部分，请参阅</p>
<p><a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">Exchange 与 Teams 如何交互</a></p>
<p>对于完整列表</p></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-without-skype-for-business-or-lync-server"></a>没有 Skype for Business 或 Lync Server 的组织的启用步骤

1.  在上面的 "开始" 部分中，了解有关先决条件的详细信息

2.  将租户切换到 "仅限团队" 模式（仅适用于现有租户）：[设置你的共存和升级设置](setting-your-coexistence-and-upgrade-settings.md)。

3.  根据公司的业务/公司策略配置你的租户：[管理你的组织的 Microsoft 团队设置](enable-features-office-365.md)。

4.  将团队客户端部署到你的用户：[获取团队客户端](get-clients.md)

5.  推动你的采纳计划  
    [采用 Microsoft Teams](adopt-microsoft-teams-landing-page.md)
    
    [Microsoft Teams 采用快速入门清单](teams-adoption-quick-start-checklist.md)

6.  开始规划将其他工作负荷移动到 Office 365

## <a name="organizations-span-classunderlinewithspan-skype-for-business-or-lync-server"></a>具有 Skype for Business 或 Lync 服务器**<span class="underline">的</span>** 组织

此起始点假定你的组织使用 Skype for Business 2019 或 2015 + 或 Lync 2013 + server 内部部署。 对于从本地服务器迁移到团队的组织，我们已经有了详细指南，应遵循这些方案。 本指南特定于团队是你在 Office 365 中使用的第一个应用程序的方案。 下表详细介绍了适用于核心服务的团队的高级配置和最终用户功能。

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
<td>孤岛模式</td>
</tr>
<tr class="even">
<td>团队中的聊天/外部通信</td>
<td>仅限内部租户，外部通信（联合）通过 Skype for Business 或 Lync server 部署</td>
</tr>
<tr class="odd">
<td>在团队中创建和查看会议</td>
<td><p>能够通过 Outlook 加载项创建会议</p>
<p>可通过音频会议许可证使用 PSTN 拨入和拨出功能。<br />
团队日历访问需要 Exchange 2016 CU3 + 本地部署，并已建立 Exchange 混合版：<br />
<a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">使用混合配置向导创建混合部署</a></p></td>
</tr>
<tr class="even">
<td>通话功能<br />
团队中的 VoIP/PSTN</td>
<td><p>租户内部的 VoIP 可用</p>
<p>PSTN 或通话计划服务不可用，直到用户移动到团队仅体验</p></td>
</tr>
<tr class="odd">
<td>团队中的团队和渠道协作</td>
<td><p>若要获得完整体验，包括合规性功能，需要向用户分配 SharePoint Online 许可证。</p>
<p>不需要迁移现有的本地 SharePoint 网站。</p></td>
</tr>
<tr class="even">
<td>OneDrive for Business （P2P 文件共享）</td>
<td>OneDrive for business 要求用户分配有 SharePoint Online 许可证。 不能进行这种许可证的每对等文件共享。</td>
</tr>
<tr class="odd">
<td>应用程序平台</td>
<td>用户将能够根据你的公司策略使用指定的适用应用。<br />
在此了解详细信息：<a href="https://docs.microsoft.com/microsoftteams/admin-settings">团队中的应用的管理员设置</a></td>
</tr>
<tr class="even">
<td>安全性和合规性功能</td>
<td><ul>
<li><p>保留策略可用</p></li>
<li><p>支持针对频道消息的电子数据展示和法律封存</p></li>
<li><p>数据丢失防护策略（DLP）可用</p></li>
</ul>
<p>完整功能集通过 Exchange Online 提供，本地 Exchange 支持这些功能中的大部分，请参阅</p>
<p><a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">Exchange 与 Teams 如何交互</a></p>
<ul>
<li><p>对于完整列表</p></li>
</ul></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-with-skype-for-business-server"></a>具有 Skype for business 服务器的组织的启用步骤  

1.  在上面的 "开始" 部分中，满足上述先决条件。

2.  将租户切换到 "孤岛" 模式（在9/1/2019 之后预配租户），请联系支持人员进行此更改）  
    [设置共存和升级设置](setting-your-coexistence-and-upgrade-settings.md)

3.  根据公司的企业/公司策略配置租户  
    [为你的组织管理 Microsoft Teams 设置](enable-features-office-365.md)

4.  部署团队客户端  
    [获取 Teams 客户端](get-clients.md)

5.   推动你的采纳计划  
    [采用 Microsoft Teams](adopt-microsoft-teams-landing-page.md)
    
    [Microsoft Teams 采用快速入门清单](teams-adoption-quick-start-checklist.md)

6.  开始规划将其他工作负荷移动到 Office 365

7.  建立 Skype for business 混合，并按照推荐的升级路径进行 Skype for Business 和 Lync 服务器  
    [从本地 Skype for Business 升级到团队](upgrade-to-teams-execute-skypeforbusinesshybridonprem.md)

## <a name="closing-statement"></a>结算语句

Microsoft 团队可以是你的组织的一个启用码，以将所有员工、信息工作者和一线工作者汇集到一个平台上。 您可以立即[开始](https://products.office.com/microsoft-teams/group-chat-software)使用。 您可以在[此处](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog)与我们的所有最新通知和每月产品更新保持联系。

此外，随着全球各地的公司正在管理当前的 COVID-19，我们已创建一系列内容，帮助您利用团队最大程度地影响您的组织。

  - 我们[在 COVID 期间对客户的承诺-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)

  - [2周内：我们学到的有关远程工作的内容](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/18/making-the-switch-to-remote-work-5-things-weve-learned/)

  - [提供联机会议和事件](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/delivering-online-meetings-events/)

  - [协助中小型企业使用 Teams 远程工作](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/helping-smb-customers-work-remotely-microsoft-teams/)

  - [实时事件的数字转换： Bob Bejan 在 frontline 中的观测值](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/13/digital-transformation-live-events-bob-bejans-observations-frontline/)

  - [Microsoft IT 便于员工远程工作的 9 大方式](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/top-9-ways-microsoft-it-enabling-remote-work-employees/)

  - [远程工作，保持安全-CISOs 提示](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/work-remotely-stay-secure-ciso-tips/)

  - [帮助教师和学生将交换机转换为远程学习](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/11/helping-teachers-students-switch-remote-learning/)

  - [在与 Microsoft 团队远程协作的同时保持工作效率](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/)

## <a name="support-services-reference"></a>支持服务参考

团队依赖于 Exchange Online、SharePoint Online、OneDrive for Business 和 Microsoft 365 组，以便为你的用户提供完全集成的 Office 365 体验。 如上所述，团队将在不完全部署这些服务的情况下正常工作-但功能有限。 你可以在此处阅读有关团队及其先决条件的详细信息：[欢迎使用团队](teams-overview.md)。

有关以上列出的每项服务的详细信息，请访问以下链接：

  - Exchange Online 用于日历功能并将对等消息存储到团队中的对等消息中。 若要了解详细信息，请阅读[Exchange 和团队如何进行交互](exchange-teams-interact.md)

> [!IMPORTANT]
> 对于具有本地 Exchange 的团队互操作，必须按照在 [Exchange 和 Exchange Online 组织之间配置 OAuth 身份验证](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)中所述配置新的 Exchange OAuth 身份验证协议。

  - SharePoint 用于频道中的文件共享，而/OneDrive 用于在1:1 或群组聊天中进行文件共享。 若要了解详细信息，请参阅[SharePoint Online 和 OneDrive For Business 如何与 Microsoft 团队进行交互](sharepoint-onedrive-interact.md)。

  - [Microsoft 365 组](office-365-groups.md)用于团队和频道创建/管理。


## <a name="related-topics"></a>相关主题

[Microsoft Teams IT 体系结构和电话解决方案海报](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)

[规划 Skype for Business Server 与 Office 365 之间的混合连接](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity)

[支持使用团队的远程工作人员](support-remote-work-with-teams.md)

[使用 Office 365 远程工作](https://aka.ms/remote-work)
