---
title: 为 Teams 准备贵组织的网络
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: jastark, kojika
audience: admin
description: 了解如何为 Microsoft 团队准备组织的网络，包括网络要求、网络优化和带宽要求。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
ms.openlocfilehash: bc81781e17b16820eebb134a0ee57f1fb82d403c
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/03/2020
ms.locfileid: "43143783"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a>为 Microsoft Teams 准备组织的网络 

## <a name="network-requirements"></a>网络要求

如果您已经针对[Office 365 优化了](https://docs.microsoft.com/Office365/Enterprise/assessing-network-connectivity)您的网络，您可能已经准备好参加 Microsoft 团队。 在任何情况下，尤其是当你作为第一个 Office 365 工作负荷快速推出团队以支持**远程工作人员**时-请先检查以下内容，然后再开始团队推出：

1.  您的所有位置是否都有 internet 访问权限（以便他们可以连接到 Office 365）？ 除了普通 web 流量之外，请确保已针对团队中的媒体打开以下内容：

    |  |  |
    |---------|---------|
    |端口     |UDP 端口<strong>3478</strong>到<strong>3481</strong>        |
    |[IP 地址](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) |<strong>13.107.64.0/18</strong>、 <strong>52.112.0.0/14</strong>和<strong>52.120.0.0/14</strong>         |

    
2.  您是否有经验证的 Office 365 域（例如，contoso.com）？
    
      - 如果你的组织尚未推出 Office 365，请参阅[office 365 for business](https://docs.microsoft.com/office365/admin/admin-overview/get-started-with-office-365)入门。
      - 如果你的组织尚未为 Office 365 添加或配置验证的域，请参阅[验证你的 office 365 域](https://docs.microsoft.com/office365/admin/setup/domains-faq)。

3.  您的组织是否已部署 Exchange Online 和 SharePoint Online？
    
      - 如果你的组织没有 Exchange Online，请参阅[了解 exchange 和 Microsoft 团队如何交互](exchange-teams-interact.md)。
      - 如果你的组织没有 SharePoint Online，请参阅[了解 Sharepoint online 和 OneDrive For business 如何与 Microsoft 团队进行交互](sharepoint-onedrive-interact.md)。

验证满足这些网络要求后，您可能已准备好[推出团队](How-to-roll-out-teams.md)。 如果你是大型跨国企业版，或者如果你知道你有一些网络限制，请继续阅读，了解如何评估和优化团队的网络。

> [!IMPORTANT]
> **对于教育机构**：如果您的组织是教育机构，并且您使用学生信息系统（SIS），请在推出团队之前[部署学校数据同步](https://docs.microsoft.com/schooldatasync/)。
>  
> **运行本地 skype for Business 服务器**：如果你的组织运行的是本地 skype For business 服务器（或 Lync server），则必须[配置 Azure AD Connect](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-azure-ad-connect)以将本地目录与 Office 365 同步。

### <a name="best-practice-monitor-your-network-using-cqd-and-call-analytics"></a>最佳做法：使用 CQD 和 call analytics 监控您的网络 

使用[通话质量仪表板（CQD）](turning-on-and-using-call-quality-dashboard.md) ，深入了解团队中的通话和会议的质量。 CQD 可通过保持密切关注的质量、可靠性和用户体验来帮助你优化网络。 CQD 查看整个组织的聚合遥测，其中整体模式可能会变得显而易见，这使你可以确定问题并计划补救措施。 此外，CQD 提供了丰富的度量报告，可提供总体质量、可靠性和用户体验的深入见解。 

你将使用[调用分析](set-up-call-analytics.md)来调查单个用户的通话和会议问题。

## <a name="network-optimization"></a>网络优化

以下任务是可选的，并且不是向团队推出所必需的，尤其是当你是小型企业并且已推出 Office 365 时。 使用本指南可优化您的网络和团队性能，或者如果您知道您有一些网络限制。

在以下情况中，可能需要执行其他网络优化：

  - 团队运行缓慢（也许你没有足够的带宽）
  - 呼叫继续丢弃（可能是由于防火墙或代理阻止程序）
  - 呼叫有静电和削减，或者声音类似机器人（可能是抖动或数据包丢失）

有关网络优化的深入讨论，包括用于识别和修复网络障碍的指南，请阅读[Office 365 网络连接原则](https://aka.ms/pnc)。

<table>
<thead>
<tr class="header">
<th><strong>网络优化任务</strong></th>
<th><strong>Details</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>网络 planner</td>
<td><p>有关评估网络的帮助（包括带宽计算和组织的物理位置的网络要求），请查看<a href="https://admin.teams.microsoft.com">团队管理中心</a>内的<a href="https://docs.microsoft.com/microsoftteams/network-planner">网络 Planner</a>工具。 当你提供网络详细信息和团队使用情况时，网络 Planner 会计算你的网络要求，以便在组织的物理位置部署团队和云语音。</p>
<p>有关示例方案，请参阅<a href="https://docs.microsoft.com/microsoftteams/tutorial-network-planner-example">使用网络 Planner-示例方案</a>。</p></td>
</tr>
<tr class="even">
<td>团队的顾问</td>
<td>团队的<a href="https://docs.microsoft.com/microsoftteams/use-advisor-teams-roll-out">顾问</a>是<a href="https://admin.teams.microsoft.com">团队管理中心</a>的一部分。 它将评估 Office 365 环境并确定更新或修改所需的最常用配置，帮助你成功推出 Teams。</td>
</tr>
<tr class="odd">
<td>外部名称解析</td>
<td>请确保运行团队客户端的所有计算机都可以解析外部 DNS 查询以发现 Office 365 提供的服务，并且你的防火墙不会阻止访问。 有关配置防火墙端口的信息，请转到<a href="https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges">Office 365 url 和 IP 范围</a>。</td>
</tr>
<tr class="odd">
<td>验证（NAT）池大小</td>
<td>验证用户连接所需的网络地址转换（NAT）池大小。 当多个用户和设备使用<a href="https://docs.microsoft.com/office365/enterprise/nat-support-with-office-365">网络地址转换（NAT）或端口地址转换（PAT）</a>访问 Office 365 时，您需要确保隐藏在每个可访问的 IP 地址后面的设备不会超过支持的号码。 确保为 NAT 池分配了足够的公共 IP 地址以防止端口耗尽。 端口耗尽将对内部用户和无法连接到 Office 365 服务的设备造成影响。</td>
</tr>
<tr class="even">
<td>路由到 Microsoft 数据中心</td>
<td><a href="https://docs.microsoft.com/office365/enterprise/client-connectivity">实现最高效的路由到 Microsoft 数据中心</a>。 确定可使用本地或区域传出点尽可能高效地连接到 Microsoft 网络的位置。</td>
</tr>
<tr class="odd">
<td>入侵检测和阻止指南</td>
<td>如果你的环境为出站连接的额外安全层部署了<a href="https://docs.microsoft.com/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools">入侵检测</a>或防护系统（IDS/IPS），请确保对所有 Office 365 url 进行白名单。</td>
</tr>
<tr class="even">
<td>配置拆分隧道 VPN</td>
<td><p>我们建议你为团队流量提供备用路径，该路径绕过虚拟专用网络（VPN），通常称为[拆分隧道 VPN](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-routing)。 拆分隧道意味着 Office 365 的流量不会通过 VPN，而是直接转到 Office 365。 绕过你的 VPN 将对团队质量产生积极影响，并减少从 VPN 设备和组织网络的负载。 要实现分割隧道 VPN，请与您的 VPN 供应商配合使用。</p>
<p>建议绕过 VPN 的其他原因：
<ul>
<li><p>Vpn 一般不是为支持实时媒体而设计或配置的。</p></li> 
<li><p>某些 Vpn 可能也不支持 UDP （这是团队所必需的）。</p></li> 
<li><p>Vpn 还会在已加密的媒体流量顶部引入额外的加密层。</p></li> 
<li><p>由于通过 VPN 设备有头发的流量，到团队的连接可能不会有效。</p></li></td>
</tr>
<tr class="odd">
<td>实施 QoS</td>
<td><a href="https://docs.microsoft.com/microsoftteams/qos-in-teams">使用服务质量（QoS）</a>配置数据包优先级。 这将改进团队的通话质量，帮助你监控和解决通话质量问题。 应在托管网络的所有段中实现 QoS。 即使已为带宽设置了充足的网络，QoS 在网络事件发生时也会带来风险降低。 通过 QoS，可以确定语音流量的优先顺序，以便这些意外事件不会对质量产生负面影响。</td>
</tr>
<tr class="even">
<td>优化 WiFi</td>
<td><p>与 VPN 类似，WiFi 网络不一定设计或配置为支持实时媒体。 规划或优化 WiFi 网络以支持团队是高质量部署的重要考虑事项。 请考虑以下因素：</p>
<ul>
<li><p>实施 QoS 或 WiFi 多媒体（WMM），确保媒体流量在您的 WiFi 网络上得到适当的优先级。</p></li>
<li><p>规划和优化 WiFi 频带和接入点放置。 2.4 GHz 范围可能会提供足够的体验，具体取决于接入点的位置，但访问点通常受在该范围内运行的其他消费者设备的影响。 由于其密集范围，5 GHz 范围更适合实时媒体，但需要更多访问点才能获得足够的服务。 此外，终结点还需要相应地支持该范围并配置为利用这些频带。</p></li>
<li><p>如果您使用的是双频 WiFi 网络，请考虑实施带通指导委员会。 <em>波段</em>控制是由 WiFi 供应商实施的一项技术，可影响双层客户使用 5 GHz 范围。</p></li>
<li><p>当同一频道的接入点太靠近时，它们可能会导致信号重叠并无意间竞争，从而导致用户遇到错误的体验。 确保彼此相邻的接入点位于不重叠的频道上。</p></li>
</ul>
<p>每个无线供应商都有自己的无线解决方案部署建议。 有关特定指南，请咨询 WiFi 供应商。</p></td>
</tr>
</tbody>
</table>

## <a name="bandwidth-requirements"></a>带宽要求

团队设计用于提供最佳音频、视频和内容共享体验，无论网络条件如何。 也就是说，当带宽不足时，团队将通过视频质量对音频质量进行优先级排定。

在带宽*不*受限制的情况下，团队会优化媒体质量，包括最高分辨率的视频分辨率、最多30fps 视频和15fps 内容以及高保真音频。 

[!INCLUDE [bandwidth-requirements](includes/bandwidth-requirements.md)]


## <a name="related-topics"></a>相关主题

[Office 365 网络连接原则](https://aka.ms/pnc)

[全球终结点： Skype for Business Online 和团队](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

[团队的代理服务器](proxy-servers-for-skype-for-business-online.md)

[团队中的媒体：为什么会议很简单](https://aka.ms/teams-media)

[团队中的媒体：深入了解媒体流](https://aka.ms/teams-media-flows)

[Teams 中的标识模式和身份验证](identify-models-authentication.md)

[如何部署 Teams](How-to-roll-out-teams.md)

