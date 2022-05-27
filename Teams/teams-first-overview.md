---
title: 首先推出Microsoft Teams
author: LaszloSomi
ms.author: lsomi
manager: swerth
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: lsomi
ms.localizationpriority: medium
search.appverid: MET150
description: 使用本指南将Microsoft Teams作为第一个Microsoft 365或Office 365工作负荷推出。
ROBOTS: NOINDEX, NOFOLLOW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2621ea94e2a35e7de9eed3dac2994f9b1932b0bb
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681723"
---
# <a name="roll-out-microsoft-teams-first"></a>首先推出Microsoft Teams

Microsoft Teams可以帮助员工保持联系和协作，尤其是在目前远程工作成为全球员工现实的前所未有的时期。 能够在Teams中聊天、召开视频会议和协作处理Office文档可以帮助公司保持工作效率。 无论你是小型企业、非营利组织还是大型组织，在部署任何其他Office 应用或服务之前，都可以先开始将Teams作为Microsoft 365或Office 365套件中的第一个工作负荷。

本文详细介绍了必须使用“Teams第一”方法进行的注意事项。

> [!IMPORTANT]
> 虽然Teams可以是组织部署的第一个云工作负荷，但部署Teams应是整个云部署策略的一部分。

如果已推出其他Microsoft 365或Office 365服务，Teams下一个工作负载将推出 (而不是第一个) ，[请从如何推出Teams开始](./deploy-overview.md)。

## <a name="start-here"></a>从这里开始

若要开始Teams首次部署，至少需要满足一些先决条件。 以下列表将显示在启用Teams之前必须为组织准备的内容：

1.  使用域名配置的Microsoft 365或Office 365组织

2.  Azure Active Directory连接 (AAD 连接) 或类似的云标识同步解决方案 - 与租户同步的所有必需属性  
    若要了解与 AAD 同步同步的属性，请阅读 [Azure AD 连接同步：已同步到Azure Active Directory](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)

3.  为Teams分配的适当用户许可证  
    若要了解Teams许可，请阅读[Microsoft Teams服务说明](/office365/servicedescriptions/teams-service-description)。

4.  组织为Teams做好准备的网络  
    若要了解网络准备，请阅读[“为Teams准备组织的网络](prepare-network.md)”。

5.  允许网络访问Microsoft 365或Office 365中的Exchange、SharePoint和OneDrive for Business：[Office 365 URL 和 IP 地址范围](/office365/enterprise/urls-and-ip-address-ranges)。

> [!NOTE]
> 2019 年 9 月 1 日之后创建的租户以Teams仅限模式预配。
> 
> [!IMPORTANT]
> 如果已部署Skype for Business Server，并且租户已在 2019 年 9 月 1 日之后预配，请联系支持人员，为Teams启用共存功能。 在向用户分配任何Teams许可证<span class="underline">之前</span>，请确保你的“组织范围升级策略”设置为“岛模式”。

## <a name="migration-starting-points"></a>迁移起始点

Microsoft 365或Office 365以及Teams中提供的功能，具体取决于起点和本地Skype for Business或 Lync 服务器的存在。 除上述先决条件外，以下部分还将详细介绍基本功能和配置选项。 我们已将起点方案细分为以下主题：

**租户Teams配置**：租户和用户模式用于控制收件人的行为。 可以在组织中的租户级别或用户级别分配这些设置。 若要了解详细信息，请阅读[与Skype for Business共存](coexistence-chat-calls-presence.md)。

**Teams中的聊天/外部通信**：聊天服务是指组织内部或外部对等聊天对话或组织外部的对等聊天或群组聊天对话。 外部通信也称为Skype for Business中的联合。

**在Teams中创建和查看会议**：用户始终可以通过Outlook Teams加载项创建联机会议，并且在获得用户许可后，所有方案均可使用 PSTN 拨入。 Teams和Skype for Business将日历信息存储在用户的Exchange邮箱中。 本地Exchange服务器必须Exchange Server 2016 CU3 或更高版本，Teams客户端才能与用户的邮箱交互。 如果没有Exchange邮箱访问，Teams中的“日历”图标将不会显示，用户将无法在Teams客户端中查看、创建或修改会议。

**Teams中调用功能 VoIP/PSTN**：呼叫可以通过 IP (VoIP) 或公共交换电话网络 (PSTN) 进行语音传输。 VoIP 连接在Teams客户端之间本机发生，而当用户拨打外部电话号码时会发生 PSTN 连接。  

Teams支持两种类型的 PSTN 连接。 Microsoft 呼叫计划，当 Microsoft 提供电话基础结构（包括用户的电话号码）或直接路由配置时，客户通过会话边界控制器 (SBC) 为Teams用户提供电话连接。  
若要了解详细信息，请阅读[适合你的通话套餐？](calling-plan-landing-page.md)[并电话系统直接路由](direct-routing-landing-page.md)。

**Teams中的Teams和渠道协作**：在Teams中，团队是为工作、项目或共同利益而聚集在一起的一组人。 Teams由通道组成。 每个频道都是围绕一个主题构建的，例如“团队事件”，一个部门名称，或者只是为了好玩。 频道是你召开会议、进行对话和共同处理文件的通道。 协作期间

**OneDrive for Business (Teams中的 P2P 文件共享)**：在Teams和频道之外，Teams用户可以使用业务或其他 P2P 共享文件程序（如 Citrix 文件、DropBox、Box 和 Google 云端硬盘）的OneDrive来对等共享文件。 对于业务OneDrive，用户必须分配SharePoint联机许可证。

**应用程序平台**：应用为组织提供现的工具，以获取更多Teams。 这些应用结合了由第三方或组织中的开发人员生成的 Microsoft 提供的选项卡、消息传递扩展、连接器和机器人的功能。

**安全性和合规性功能：** Teams提供各种信息来帮助你了解合规性领域，包括保留策略、数据丢失防护 (DLP) 、电子数据展示以及频道、聊天和文件的法律保留、审核日志搜索。 若要了解详细信息，请阅读[Microsoft Teams中的安全性和符合性](security-compliance-overview.md)。  

> [!NOTE]
> 高级电子数据展示功能需要 E5 许可。

[比较许可选项](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)。

阅读[Exchange和Microsoft Teams如何交互](exchange-teams-interact.md)，了解方案中可用的符合性功能。

## <a name="organizations-span-classunderlinewithoutspan-skype-for-business-or-lync-server"></a>**<span class="underline">没有</span>** Skype for Business或 Lync Server 的组织

此起始点假定组织当前不使用 Skype for Business 或 Lync Server，Teams将是Microsoft 365或Office 365中的第一个应用程序。 下表详细介绍了核心服务Teams的高级配置和最终用户功能。

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
<td>Teams仅限模式，所有聊天和通话功能都仅Teams。</td>
</tr>
<tr class="even">
<td>Teams中的聊天/外部通信</td>
<td><p>内部 (Microsoft 365或Office 365组织) 和从Teams进行外部聊天通信。</p>
<p><em>注意：必须为外部访问配置 DNS 条目。 即使你在本地或Microsoft 365或Office 365中没有Skype for Business，也需要Skype for Business DNS 记录，以允许与 Lync 和Skype for Business环境联合：<br />
<a href="/office365/enterprise/external-domain-name-system-records">外部域名系统记录</a></em></p></td>
</tr>
<tr class="odd">
<td>在Teams中创建和查看会议</td>
<td><p>能够通过Outlook加载项创建内部和外部会议。</p>
<p>PSTN 拨入和拨入功能可用于音频会议许可证。</p>
<p>Teams日历访问需要在本地部署 Exchange 2016 CU3+ 并建立Exchange混合：<a href="/exchange/hybrid-deployment/deploy-hybrid">使用混合配置向导创建混合部署。</a> </p>

除了Exchange混合配置，还建立Exchange OAuth 身份验证：[在Exchange和Exchange Online组织之间配置 OAuth 身份验证](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)。 

</p></td>
</tr>
<tr class="even">
<td>调用功能<br />
Teams中的 VoIP/PSTN</td>
<td><p>可在租户内部和外部使用 VoIP。</p>
<p>可以通过Microsoft 电话系统配置 PSTN 服务，并添加 Microsoft 呼叫计划或直接路由。</p></td>
</tr>
<tr class="odd">
<td>Teams和频道协作Teams</td>
<td><p>若要获得完整的体验（包括合规性功能），需要向用户分配SharePoint联机许可证。</p>
<p>不需要迁移现有本地SharePoint站点。</p></td>
</tr>
<tr class="even">
<td>OneDrive for Business (P2P 文件共享) </td>
<td>OneDrive for Business要求用户分配SharePoint联机许可证。 如果没有此许可证，将无法进行对等文件共享。</td>
</tr>
<tr class="odd">
<td>应用程序平台</td>
<td>用户将能够根据公司策略使用为其指定的应用。<br />
在此处了解详细信息：<a href="/microsoftteams/admin-settings">管理员Teams中的应用设置</a></td>
</tr>
<tr class="even">
<td>安全性和符合性功能</td>
<td><ul>
<li><p>保留策略可用。</p></li>
<li><p>支持电子数据展示和法律保留以符合频道消息。</p></li>
<li><p>可使用 DLP)  (数据丢失防护策略。</p></li>
</ul>
<p>具有Exchange Online的完整功能集;Exchange本地支持大部分这些功能。 有关完整列表，请参阅<a href="/MicrosoftTeams/exchange-teams-interact">Exchange和Teams如何交互</a>。</p></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-without-skype-for-business-or-lync-server"></a>没有Skype for Business或 Lync Server 的组织的启用步骤

1.  满足上述“"开始"菜单此处”部分中详述的先决条件

2.  仅) ：[设置共存和升级设置](setting-your-coexistence-and-upgrade-settings.md)，将租户切换到Teams仅限现有租户的模式 (。

3.  根据公司的业务/公司策略配置租户：[管理组织的Microsoft Teams设置](enable-features-office-365.md)。

4.  将Teams客户端部署到用户：[获取客户端Teams](get-clients.md)

5.  推动采用计划  
    [采用 Microsoft Teams](adopt-microsoft-teams-landing-page.md)
    
    [Microsoft Teams 采用快速入门清单](teams-adoption-quick-start-checklist.md)

6.  开始计划将其他工作负荷移动到Microsoft 365或Office 365

## <a name="organizations-span-classunderlinewithspan-skype-for-business-or-lync-server"></a>**<span class="underline">具有</span>** Skype for Business 或 Lync 服务器的组织

此起始点假定组织在本地使用 Skype for Business 2019 或 2015+ 或 Lync 2013+ 服务器。 我们已经为从本地服务器迁移到Teams的组织提供了广泛的指导，应针对这些方案遵循该指南。 本指南特定于Teams是你在Microsoft 365或Office 365中使用的第一个应用程序的场景。 下表详细介绍了核心服务Teams的高级配置和最终用户功能。

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
<td>“岛屿”模式。</td>
</tr>
<tr class="even">
<td>Teams中的聊天/外部通信</td>
<td>仅在自己的租户内部，外部通信 (联合) 通过Skype for Business或 Lync 服务器部署。</td>
</tr>
<tr class="odd">
<td>在Teams中创建和查看会议</td>
<td><p>能够通过Outlook加载项创建内部和外部会议。</p>
<p>PSTN 拨入和拨入功能可用于音频会议许可证。</p>
<p>Teams日历访问需要Exchange 2016 CU3+ 本地部署且已建立Exchange混合：<br />
<a href="/exchange/hybrid-deployment/deploy-hybrid">使用混合配置向导创建混合部署。</a></p>
<p>管理员可以通过Teams会议策略的 PreferredMeetingProviderForIslandsMode 属性控制Skype for Business Outlook外接程序：<a href="/powershell/module/skype/set-csteamsmeetingpolicy">set-csteamsmeetingpolicy</a>。</p> 
</td>
</tr>
<tr class="even">
<td>调用功能<br />
Teams中的 VoIP/PSTN</td>
<td><p>租户内部的 VoIP 可用。</p>
<p>PSTN 或呼叫计划服务在用户移动到仅Teams体验之前不可用。</p></td>
</tr>
<tr class="odd">
<td>Teams和频道协作Teams</td>
<td><p>若要获得完整的体验（包括合规性功能），需要向用户分配SharePoint联机许可证。</p>
<p>不需要迁移现有本地SharePoint站点。</p></td>
</tr>
<tr class="even">
<td>OneDrive for Business (P2P 文件共享) </td>
<td>OneDrive for Business要求用户分配SharePoint联机许可证。 如果没有此许可证，就不可能进行对等文件共享。</td>
</tr>
<tr class="odd">
<td>应用程序平台</td>
<td>用户将能够根据公司策略使用为其指定的应用。<br />
在此处了解详细信息：<a href="/microsoftteams/admin-settings">管理员Teams中的应用设置</a></td>
</tr>
<tr class="even">
<td>安全性和符合性功能</td>
<td><ul>
<li><p>保留策略可用。</p></li>
<li><p>支持电子数据展示和法律保留以符合频道消息。</p></li>
<li><p>可使用 DLP)  (数据丢失防护策略。</p></li>
</ul>
<p>具有Exchange Online的完整功能集;Exchange本地支持大部分这些功能。 有关完整列表，请参阅<a href="/MicrosoftTeams/exchange-teams-interact">Exchange和Teams如何交互。</a></p>
<ul>
</ul></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-with-skype-for-business-server"></a>具有Skype for Business Server的组织的启用步骤  

1.  满足上述“"开始"菜单此处”部分中详述的先决条件。

2.  将租户切换到 2019 年 9 月 1 日之后预配的租户的“岛”模式 (，请联系支持部门进行此更改)   
    [设置共存和升级设置](setting-your-coexistence-and-upgrade-settings.md)

3.  根据公司的业务/公司策略配置租户  
    [为你的组织管理 Microsoft Teams 设置](enable-features-office-365.md)

4.  部署Teams客户端  
    [获取 Teams 客户端](get-clients.md)

5.   推动采用计划  
    [采用 Microsoft Teams](adopt-microsoft-teams-landing-page.md)<br/>
    [Microsoft Teams 采用快速入门清单](teams-adoption-quick-start-checklist.md)

6.  开始计划将其他工作负荷移动到Microsoft 365或Office 365

7.  建立Skype for Business混合，并遵循Skype for Business和 Lync 服务器的建议升级路径  
    [从本地Skype for Business升级到Teams](upgrade-to-teams-execute-skypeforbusinesshybridonprem.md)

## <a name="closing-statement"></a>Closing 语句

Microsoft Teams可以使组织能够将所有员工、信息工作者和一线员工聚集在一个平台上。 你今天可以 [开始](https://products.office.com/microsoft-teams/group-chat-software) 。 你可以在此处与我们所有最新的公告和每月 [产品更新保持](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog)联系。

此外，由于世界各地的公司都在管理当前的 COVID-19 情况，我们创建了一系列内容，可帮助你利用Teams来最大程度地影响组织。

  - 我们在 [COVID-19 期间对客户的承诺](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)

  - [2 周后：我们了解了远程工作](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/18/making-the-switch-to-remote-work-5-things-weve-learned/)

  - [提供联机会议和活动](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/delivering-online-meetings-events/)

  - [协助中小型企业使用 Teams 远程工作](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/helping-smb-customers-work-remotely-microsoft-teams/)

  - [直播活动的数字化转型：鲍勃·贝詹从前线的观察](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/13/digital-transformation-live-events-bob-bejans-observations-frontline/)

  - [Microsoft IT 便于员工远程工作的 9 大方式](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/top-9-ways-microsoft-it-enabling-remote-work-employees/)

  - [远程工作，保持安全 - CISO 提示](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/work-remotely-stay-secure-ciso-tips/)

  - [帮助教师和学生转向远程学习](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/11/helping-teachers-students-switch-remote-learning/)

  - [在远程使用Microsoft Teams时保持工作效率](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/)

## <a name="support-services-reference"></a>支持服务参考

Teams依靠Exchange Online、SharePoint联机、OneDrive for Business和Microsoft 365 组为用户提供完全集成的Microsoft 365或Office 365经验。 如上所述，Teams无需完全部署这些服务，但功能有限。 可在此处阅读有关Teams及其先决条件的详细信息：[欢迎使用Teams](teams-overview.md)。

有关上述每个服务的具体信息，请按照以下链接进行操作：

  - Exchange Online用于日历功能，并将对等消息存储在Teams中。 若要了解详细信息，请阅读[Exchange和Teams如何交互](exchange-teams-interact.md)

> [!IMPORTANT]
> 若要Teams与本地Exchange互操作，必须按照在Exchange和Exchange Online[组织之间配置 OAuth 身份验证中所述配置新的 Exchange OAuth 身份验证](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)协议。

  - SharePoint用于频道中的文件共享，/OneDrive for Business用于 1：1 或群组聊天中的文件共享。 若要了解详细信息，请阅读[SharePoint联机和OneDrive for Business如何与Microsoft Teams交互](sharepoint-onedrive-interact.md)。

  - [Microsoft 365 组](office-365-groups.md)用于团队和频道创建/管理。


## <a name="related-topics"></a>相关主题

[Microsoft Teams IT 体系结构和电话解决方案海报](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)

[规划 Skype for Business Server 与 Office 365 之间的混合连接](/SkypeForBusiness/hybrid/plan-hybrid-connectivity)

[使用Teams支持远程工作者](support-remote-work-with-teams.md)

[远程处理Microsoft 365](https://aka.ms/remote-work)
