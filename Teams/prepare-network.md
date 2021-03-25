---
title: 为 Teams 准备贵组织的网络
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: jastark, kojika
audience: admin
description: 了解如何为 Microsoft Teams 准备组织的网络，包括网络要求、网络优化和带宽要求。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-deployteams
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
ms.openlocfilehash: 1c84a753146899011fa34be56e0746cc0c600b31
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117750"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a>为 Microsoft Teams 准备组织的网络 

## <a name="network-requirements"></a>网络要求

如果你已针对 [Microsoft 365 或 Office 365](/Office365/Enterprise/assessing-network-connectivity)优化网络，则你可能已准备好使用 Microsoft Teams。 在任何情况下，尤其是在作为第一个 Microsoft 365 或 Office 365 工作负荷快速推出 Teams 以支持远程工作者 **的情况下，在开始** 推出 Teams 之前，请检查以下内容：

1.  是否所有位置都有 Internet 访问 (以便它们可以连接到 Microsoft 365 或 Office 365) ？ 除了正常的 Web 流量外，至少请确保你已针对 Teams 中的媒体打开以下所有位置：

    |  |  |
    |---------|---------|
    |端口     |UDP 端口 <strong>3478</strong> 到 <strong>3481</strong>        |
    |[IP 地址](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) |<strong>13.107.64.0/18、52.112.0.0/14</strong>和<strong>52.120.0.0/14</strong> <strong></strong>         |

    > [!IMPORTANT]
    > 如果需要与本地或在线 Skype for Business 联合，则需要配置一些额外的 DNS 记录。
    >
    >|CNAME 记录/主机名  |TTL  |指向地址或值  |
    >|---------|---------|---------|
    >|sip     |    3600     |    sipdir.online.lync.com     |
    >|lyncdiscover     |   3600      |    webdir.online.lync.com     |
    
2.  你是否拥有 Microsoft 365 或 Office 365 (的已验证域，contoso.com) ？
    
    - 如果你的组织尚未推出 Microsoft 365 或 Office 365，请参阅 [入门](/microsoft-365/admin/admin-overview/get-started-with-office-365)。
    - 如果你的组织尚未添加或配置 Microsoft 365 或 Office 365 的已验证域，请参阅 [域常见问题解答](/microsoft-365/admin/setup/domains-faq)。

3.  您的组织是否部署了 Exchange Online 和 SharePoint Online？
    
    - 如果你的组织没有 Exchange Online，请参阅了解 Exchange 和 [Microsoft Teams 如何交互](exchange-teams-interact.md)。
    - 如果你的组织没有 SharePoint Online，请参阅了解 [SharePoint Online](sharepoint-onedrive-interact.md)和 OneDrive for Business 如何与 Microsoft Teams 交互。

确认满足这些网络要求后，即可开始推出[Teams。](./deploy-overview.md) 如果你是一家大型的跨国企业，或者你知道你存在一些网络限制，请继续阅读，了解如何评估和优化 Teams 的网络。

> [!IMPORTANT]
> **对于教育机构**：如果你的组织是教育机构，并且你使用学生信息系统 (SIS) ，请部署学校 [数据](/schooldatasync/) 同步，然后再推出 Teams。
>  
> 运行本地 **Skype for Business Server：** 如果你的组织运行本地 Skype for Business Server (或 Lync Server) ，则必须将 [Azure AD Connect](/skypeforbusiness/hybrid/configure-azure-ad-connect)配置为将本地目录与 Microsoft 365 或 Office 365 同步。

### <a name="best-practice-monitor-your-network-using-cqd-and-call-analytics"></a>最佳做法：使用 CQD 监视网络并调用分析 

使用 [CQD ](turning-on-and-using-call-quality-dashboard.md) (呼叫质量) ，深入了解 Teams 中的呼叫和会议质量。 CQD 可以通过密切关注质量、可靠性和用户体验来帮助优化网络。 CQD 查看整个组织的聚合遥测数据，其中的总体模式可能变得明显，从而让你能够识别问题和规划补救。 此外，CQD 还提供丰富的指标报告，用于深入了解总体质量、可靠性和用户体验。 

你将使用 [呼叫分析](set-up-call-analytics.md) 调查单个用户的呼叫和会议问题。

## <a name="network-optimization"></a>网络优化

以下任务是可选的，在推出 Teams 时不需要执行，尤其是当你是小型企业并且已经推出了 Microsoft 365 或 Office 365 时。 使用本指南优化网络和 Teams 性能，或者如果你知道你有一些网络限制。

如果：

  - 团队运行缓慢 (，可能是因为带宽不足) 
  - 调用不断 (可能是防火墙或代理阻止程序) 
  - 呼叫具有静态和剪切，或者声音像机器人 (可能是抖动或数据包丢失) 

有关网络优化的深入讨论，包括识别和修复网络障碍的指南，请阅读 [Microsoft 365 和 Office 365 网络连接原则](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)。

<table>
<thead>
<tr class="header">
<th><strong>网络优化任务</strong></th>
<th><strong>Details</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Network Planner</td>
<td><p>有关评估网络（包括组织物理位置的带宽计算和网络要求）的帮助，请查看 Teams 管理中心 中的<a href="https://admin.teams.microsoft.com">网络规划器工具</a>。 <a href="/microsoftteams/network-planner"></a> 提供网络详细信息和 Teams 使用情况时，网络规划器会计算跨组织物理位置部署 Teams 和云语音的网络要求。</p>
<p>有关示例方案，请参阅 <a href="/microsoftteams/tutorial-network-planner-example">使用网络规划器 - 示例方案</a>。</p></td>
</tr>
<tr class="even">
<td>Teams 顾问</td>
<td><a href="/microsoftteams/use-advisor-teams-roll-out">Teams 顾问</a> 是 Teams 管理 <a href="https://admin.teams.microsoft.com">中心的一部分</a>。 它将评估 Microsoft 365 或 Office 365 环境并确定更新或修改所需的最常用配置，帮助你成功推出 Teams。</td>
</tr>
<tr class="odd">
<td>外部名称解析</td>
<td>请确保运行 Teams 客户端的所有计算机都可以解析外部 DNS 查询，以发现 Microsoft 365 或 Office 365 提供的服务，并且防火墙不会阻止访问。 有关配置防火墙端口的信息，请转到 Microsoft <a href="/microsoftteams/office-365-urls-ip-address-ranges">365 和 Office 365 URL 和 IP 范围</a>。</td>
</tr>
<tr class="odd">
<td>保持会话持久性</td>
<td>请确保防火墙不会更改映射的网络地址转换 (UDP) 端口。</td>
</tr><tr class="odd">
<td>验证 NAT 池大小</td>
<td>验证 NAT 网络地址转换 (用户) 所需的池大小。 当多个用户和设备使用网络地址转换 (NAT) 或端口地址转换 <a href="/office365/enterprise/nat-support-with-office-365"> (PAT) </a>访问 Microsoft 365 或 Office 365 时，需要确保隐藏在每个可公开路由 IP 地址后面的设备不超过支持的数量。 确保向 NAT 池分配足够的公共 IP 地址，以防止端口耗尽。 端口耗尽会导致内部用户和设备无法连接到 Microsoft 365 或 Office 365 服务。</td>
</tr>
<tr class="even">
<td>路由到 Microsoft 数据中心</td>
<td><a href="/office365/enterprise/client-connectivity">实现到 Microsoft 数据中心最有效的路由</a>。 确定可以使用本地或区域出口点尽可能高效地连接到 Microsoft 网络的位置。</td>
</tr>
<tr class="odd">
<td>入侵检测和预防指南</td>
<td>如果环境为出站<a href="/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools"></a>连接部署了入侵检测或防护系统 (IDS/IPS) ，请确保允许所有 Microsoft 365 或 Office 365 URL。</td>
</tr>
<tr class="even">
<td>配置拆分隧道 VPN</td>
<td><p>我们建议为绕过虚拟专用网络（通常称为拆分隧道 <a href="/windows/security/identity-protection/vpn/vpn-routing">VPN） (</a>VPN) Teams 流量提供备用路径。 拆分隧道意味着 Microsoft 365 或 Office 365 的流量不会通过 VPN，而是直接转到 Microsoft 365 或 Office 365。 绕过 VPN 将对 Teams 质量产生积极的影响，并减少来自 VPN 设备和组织网络的负载。 若要实现拆分隧道 VPN，请与 VPN 供应商合作。</p>
<p>建议绕过 VPN 的其他原因：
<ul>
<li><p>VPN 通常未设计为或配置为支持实时媒体。</p></li> 
<li><p>某些 VPN 可能也不支持 Teams (所需的 UDP) 。</p></li> 
<li><p>VPN 还会在已加密的媒体流量上引入额外的加密层。</p></li> 
<li><p>由于通过 VPN 设备将流量固定在一起，与 Teams 的连接可能并不高效。</p></li></td>
</tr>
<tr class="odd">
<td>实施 QoS</td>
<td><a href="/microsoftteams/qos-in-teams">使用服务质量 (QoS) </a> 来配置数据包优先级。 这将提高 Teams 中的呼叫质量，并帮助你监视和排查呼叫质量问题。 QoS 应在托管网络的所有段上实现。 即使网络已充分预配带宽，QoS 也能够针对意外的网络事件提供风险缓解措施。 使用 QoS 时，语音流量优先，以便这些意外事件不会对质量造成负面影响。</td>
</tr>
<tr class="even">
<td>优化 WiFi</td>
<td><p>与 VPN 类似，WiFi 网络不一定设计为或配置为支持实时媒体。 规划或优化 WiFi 网络以支持 Teams 是高质量部署的一个重要考虑因素。 请考虑以下因素：</p>
<ul>
<li><p>实施 QoS 或 WiFi 多媒体 (WMM) 以确保媒体流量在 WiFi 网络上获得适当的优先级。</p></li>
<li><p>计划和优化 WiFi 带和接入点位置。 2.4 GHz 范围可能会提供足够的体验，具体取决于接入点的位置，但访问点通常受该范围内运行的其他使用者设备的影响。 由于 5 GHz 范围较密，因此更适合实时媒体，但需要更多的接入点才能获得足够的覆盖范围。 此外，终结点还需要相应地支持该范围并配置为利用这些频带。</p></li>
<li><p>如果你使用的是双带 WiFi 网络，请考虑实施带式操纵。 <em>带引导</em> 是 WiFi 供应商实现的技术，用于影响双带客户端以使用 5 GHz 范围。</p></li>
<li><p>当同一通道的访问点过于接近时，它们可能会导致信号重叠和意外竞争，从而导致用户体验不佳。 确保彼此旁边的访问点位于不重叠的通道上。</p></li>
</ul>
<p>每个无线供应商都有自己的无线解决方案部署建议。 有关特定指导，请咨询 WiFi 供应商。</p></td>
</tr>
</tbody>
</table>

## <a name="bandwidth-requirements"></a>带宽要求

Teams 旨在提供最佳的音频、视频和内容共享体验，而不考虑你的网络条件。 也就是说，当带宽不足时，Teams 将音频质量优先于视频质量。

在带宽没有限制的地方，Teams 会优化媒体质量，包括高达 1080p 的视频分辨率、高达 30fps 的视频和 15fps 的内容和高保真音频。 

[!INCLUDE [bandwidth-requirements](includes/bandwidth-requirements.md)]


## <a name="related-topics"></a>相关主题

[Microsoft 365 和 Office 365 网络连接原则](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[全球终结点：Skype for Business Online 和 Teams](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

[Teams 的代理服务器](proxy-servers-for-skype-for-business-online.md)

[Teams 中的媒体：为什么会议简单](https://aka.ms/teams-media)

[Teams 中的媒体：深入了解媒体流](https://aka.ms/teams-media-flows)

[Teams 中的标识模式和身份验证](identify-models-authentication.md)

[如何部署 Teams](./deploy-overview.md)

[Teams 疑难解答](/MicrosoftTeams/troubleshoot/teams)