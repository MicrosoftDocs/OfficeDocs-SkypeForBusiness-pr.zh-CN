---
title: 为 Teams 准备组织网络
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: jastark, kojika
audience: admin
description: 了解如何为 Microsoft Teams 准备组织网络，包括网络要求、网络优化和带宽要求。
ms.localizationpriority: high
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
ms.openlocfilehash: f9e11a089c75f1060e509dc9895e97176fc30345
ms.sourcegitcommit: cf2f96dbd485ac4cc822c5a591ccce6b47f12cc7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2021
ms.locfileid: "59456342"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a>为 Microsoft Teams 准备组织网络 

## <a name="network-requirements"></a>网络要求

如果您已[针对 Microsoft 365 或Office 365 应用优化了网络](/Office365/Enterprise/assessing-network-connectivity)，您可能已准备好使用 Microsoft Teams。 无论是哪种情况——尤其是将Teams作为首个 Microsoft 365 或 Office 365 工作负载迅速推出以支持 **远程工作者** 时——请在推出 Teams 之前检查以下内容：

1.  是否所有场所都可以访问 Internet （以便连接到 Microsoft 365 或 Office 365）？ 除了正常的 Web 流量，请确保已打开在 [Office 365 URL 和 IP 地址范围中为 Teams 列出的 TCP 端口和 IP 地址](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)。

    > [!IMPORTANT]
    > 如果需要与本地或联机 Skype for Business 联合，则需要配置一些额外的 DNS 记录。
    >
    >|DNS 记录  |服务  |协议  |优先级  |权重  |端口  |目标  |
    >|---------|---------|---------|---------|---------|---------|---------|
    >|SRV     |sipfederationtls     |TCP     |100     |{1}     |5061     |sipfed.online.lync.com     |
    
2.  您是否拥有 Microsoft 365 或 Office 365 的验证域（例如，contoso.com）？
    
    - 如果您的组织尚未推出 Microsoft 365 或 Office 365，请参阅 [入门](/microsoft-365/admin/admin-overview/get-started-with-office-365)。
    - 如果您的组织尚未添加或配置 Microsoft 365 或 Office 365 的验证域，请参阅 [域常见问题解答](/microsoft-365/admin/setup/domains-faq)。

3.  您的组织是否部署了 Exchange Online 和 SharePoint Online？
    
    - 如果您的组织没有 Exchange Online，请参阅[了解 Exchange 与 Microsoft Teams 如何交互](exchange-teams-interact.md)。
    - 如果您的组织没有 SharePoint Online，请参阅[了解 SharePoint Online 和 OneDrive for Business 与 Microsoft Teams 如何交互](sharepoint-onedrive-interact.md)。

确认满足这些网络要求后，即可推出 [Teams](./deploy-overview.md)。 如果您是大型跨国企业，或者清楚自身存在一些网络限制，请继续阅读，了解如何针对 Teams 对您的网络进行评估和优化。

> [!IMPORTANT]
> **对于教育机构**：如果您的组织是教育机构，并且使用学生信息系统 （SIS）， 请 [部署学校数据同步](/schooldatasync/) 之后再推出 Teams。
>  
> **运行本地 Skype for Business Server**：如果您的组织正在运行本地 Skype for Business Server（或 Lync Server），则必须 [配置 Azure AD Connect](/skypeforbusiness/hybrid/configure-azure-ad-connect) 以将您的本地目录与 Microsoft 365 或 Office 365 同步。

### <a name="best-practice-monitor-your-network-using-cqd-and-call-analytics"></a>最佳做法：使用 CQD 和呼叫分析监视网络 

利用 [通话质量仪表板 （CQD）](turning-on-and-using-call-quality-dashboard.md) 了解 Teams 中通话和会议的质量。 CQD 通过密切关注质量、可靠性和用户体验来帮助您优化网络。 CQD 对整个组织的聚合遥测可以凸显出其整体模式，以便于识别问题并规划改进措施。 此外，CQD 所提供的丰富的指标报告内包含对整体质量、可靠性和用户体验的洞见。 

你将使用 [呼叫分析](set-up-call-analytics.md) 来调查单个用户的通话和会议问题。

## <a name="network-optimization"></a>网络优化

以下任务不是推出 Teams 所必需的，尤其是对于已推出 Microsoft 365 或 Office 365 的小型企业。 如果需要优化网络和 Teams 性能，或者存在已知网络限制时，请使用本指南。

如果存在以下情况，建议进行额外的网络优化：

  - Teams 运行速度较慢（可能带宽不足）
  - 通话频繁掉线（可能由于防火墙或代理阻止程序）
  - 通话有杂音并且时断时续，或者语音生硬（可能因为信号波动或数据包丢失）

如需深入了解网络优化相关内容，包括如何识别和修复网络故障，请参阅 [Microsoft 365 和 Office 365 网络连接原则](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)。

<table>
<thead>
<tr class="header">
<th>网络优化任务</th>
<th>详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>网络规划器</td>
<td><p>如需评估您组织所有地点的网络，包括带宽计算和网络要求，请参阅 <a href="https://admin.teams.microsoft.com">Teams 管理中心</a> 内的 <a href="/microsoftteams/network-planner">网络规划</a> 工具。 只要您提供网络的详细信息和 Teams 的使用场景，网络规划器便会计算出在您组织的所有地点部署 Teams 和云语音的网络要求。</p>
<p>如需了解示例方案，请参阅 <a href="/microsoftteams/tutorial-network-planner-example">使用网络规划器 - 示例方案</a>。</p></td>
</tr>
<tr class="even">
<td>Teams 顾问</td>
<td><a href="/microsoftteams/use-advisor-teams-roll-out">Teams 顾问</a> 是 <a href="https://admin.teams.microsoft.com">Teams 管理中心</a> 的一部分。 它将评估 Microsoft 365 或 Office 365 环境并确定更新或修改所需的最常用配置，帮助你成功推出 Teams。</td>
</tr>
<tr class="odd">
<td>外部名称解析</td>
<td>确保所有运行 Teams 客户端的计算机都可以解析外部 DNS 查询，以发现您的防火墙没有阻止访问的 Microsoft 365 或 Office 365 服务。 关于配置防火墙端口的内容，请参阅 <a href="/microsoftteams/office-365-urls-ip-address-ranges">Microsoft 365 和 Office 365 URL 和 IP 范围</a>。</td>
</tr>
<tr class="odd">
<td>维持会话持续性</td>
<td>请确保防火墙不会更改 UDP 的映射网络地址转换 （NAT） 地址或端口。</td>
</tr><tr class="odd">
<td>验证 NAT 池大小</td>
<td>验证用户连接所需的网络地址转换 （NAT） 池大小。 当多个用户和设备使用 <a href="/office365/enterprise/nat-support-with-office-365">网络地址转换 （NAT） 或端口地址转换 （PAT）</a>访问 Microsoft 365 或 Office 365 时，需要确保每个可公开路由 IP 地址后隐藏的设备不超过支持的数量。 确保向 NAT 池分配了充足的公共 IP 地址，以防止端口耗尽。 端口耗尽将造成内部用户和设备无法连接到 Microsoft 365 或 Office 365 服务。</td>
</tr>
<tr class="even">
<td>路由至 Microsoft 数据中心</td>
<td><a href="/office365/enterprise/client-connectivity">实现到 Microsoft 数据中心的最有效的路由</a>。 尽可能有效地识别可使用本地或区域出口点连接到 Microsoft 网络的位置。</td>
</tr>
<tr class="odd">
<td>入侵检测和防护指南</td>
<td>如果您的环境为了额外提高出站连接安全性而部署了 <a href="/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools">入侵检测</a> 或防护系统 （IDS/IPS），请确保允许所有 Microsoft 365 或 Office 365 URL。</td>
</tr>
<tr class="even">
<td>配置拆分通道 VPN</td>
<td><p>建议为 Teams 流量提供一个绕过虚拟专用网络（VPN）的备用路径 <a href="/windows/security/identity-protection/vpn/vpn-routing">（通常被称为“拆分通道 VPN”）</a>。 拆分通道意味着 Microsoft 365 或 Office 365 的流量不会通过 VPN，而是直接转到 Microsoft 365 或 Office 365。 绕过 VPN 可以改善 Teams 使用质量，并减少来自 VPN 设备和组织网络的负载。 要实施拆分通道 VPN，请咨询 VPN 供应商。</p>
<p>建议绕过 VPN 的其他原因：
<ul>
<li><p>VPN 通常没有设计或配置为支持实时媒体。</p></li> 
<li><p>某些 VPN 可能也不支持 UDP（Teams 需要 UDP）。</p></li> 
<li><p>VPN 还会在已加密的媒体流量之上额外引入一层加密。</p></li> 
<li><p>由于流量经过 VPN 设备的回流，与 Teams 的连接效率可能不高。</p></li></td>
</tr>
<tr class="odd">
<td>实施 QoS</td>
<td><a href="/microsoftteams/qos-in-teams">使用服务质量 （QoS）</a> 来配置数据包优先顺序。 这将提高 Teams 的通话质量，并帮助监视和解决通话质量问题。 QoS 应在托管网络的所有段上实施。 即使网络带宽已预配充分，QoS 也可在发生意外网络事件时缓解风险。 QoS 会优先传输语音流量，以避免意外事件影响通话质量。</td>
</tr>
<tr class="even">
<td>优化 WiFi</td>
<td><p>与 VPN 类似，WiFi 网络不一定设计或配置为支持实时媒体。 为支持 Teams 而规划或优化 Wi-Fi 网络是实现高质量部署的一个重要考虑事项。 请考虑以下因素：</p>
<ul>
<li><p>实施 QoS 或 Wi-Fi 多媒体 (WMM)，以确保您的 Wi-Fi 网络优先处理媒体流量。</p></li>
<li><p>规划和优化 Wi-Fi 频带和接入点位置。 如果接入点位置合理， 2.4 GHz 频段也有可能提供合格的体验，但接入点通常会受到该频段内运行的其他用户设备的影响。 5 GHz 频段因其密集性更适合实时媒体，但需要更多接入点以获取充足的覆盖率。 另外，终结点还需要支持此频段，并进行相应配置才能利用这些频带。</p></li>
<li><p>如果部署的是双频 Wi-Fi 网络，不妨实施频带切换。 <em>频带转向</em>是一种由 Wi-Fi 供应商实现的技术，用于引导双频客户端使用 5GHz 频段。</p></li>
<li><p>如果同一信道的接入点距离太近，可能会造成信号重叠，在无意中产生竞争，进而导致用户体验不佳。 请确保相邻接入点的信道不会重叠。</p></li>
</ul>
<p>每个无线供应商都有自己的无线解决方案部署建议。 请咨询您的 WiFi 供应商以寻求具体指导。</p></td>
</tr>
</tbody>
</table>

## <a name="bandwidth-requirements"></a>带宽要求

Teams 旨在不受网络条件限制，提供最佳音频、视频和内容共享体验。 话虽如此，当带宽不足时，Teams 将优先确保音频质量，其次才是视频质量。

如果带宽不受限制，Teams 会优化媒体质量，包括高保真音频、高达 1080p 的视频分辨率，以及高达 30fps（帧/秒）的视频和内容。

下表介绍 Teams 如何使用带宽。 Teams 在带宽利用率方面始终保守，可在 1.5Mbps 以下提供高清视频质量。 每个音频/视频通话或会议中的实际带宽消耗量将取决于多种因素，如视频布局、视频分辨率和每秒视频帧。 如果有更多带宽可用，质量和使用率将会增加，以提供最佳体验。

:::row:::
   :::column span="":::
      **形态**
   :::column-end:::
   :::column span="3":::
      **带宽要求（比特率 Kb/s 向上/向下）**
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
   :::column-end:::
   :::column span="":::
      **最小值**
   :::column-end:::
   :::column span="":::
      **建议**
   :::column-end:::
   :::column span="":::
      **最佳性能**
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="4":::
      **音频**
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        一对一
   :::column-end:::
   :::column span="":::
        10/10
   :::column-end:::
   :::column span="":::
        58/58
   :::column-end:::
   :::column span="":::
        76/76
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        会议
   :::column-end:::
   :::column span="":::
        10/10
   :::column-end:::
   :::column span="":::
        58/58
   :::column-end:::
   :::column span="":::
        76/76
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="4":::
      **Video**
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        一对一
   :::column-end:::
   :::column span="":::
        150/150
   :::column-end:::
   :::column span="":::
        1,500/1,500
   :::column-end:::
   :::column span="":::
        4,000/4,000
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        会议
   :::column-end:::
   :::column span="":::
        150/200
   :::column-end:::
   :::column span="":::
        2,500/4,000
   :::column-end:::
   :::column span="":::
        4,000/4,000
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="4":::
      **屏幕共享**
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        一对一
   :::column-end:::
   :::column span="":::
        200/200
   :::column-end:::
   :::column span="":::
        1,500/1,500
   :::column-end:::
   :::column span="":::
        4,000/4,000
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        会议
   :::column-end:::
   :::column span="":::
        250/250
   :::column-end:::
   :::column span="":::
        2,500/2,500
   :::column-end:::
   :::column span="":::
        4,000/4,000
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="4":::
      **同框场景模式**
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        一对一
   :::column-end:::
   :::column span="":::
        不适用
   :::column-end:::
   :::column span="":::
        不适用
   :::column-end:::
   :::column span="":::
        不适用
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        会议
   :::column-end:::
   :::column span="":::
        1,000/1,500
   :::column-end:::
   :::column span="":::
        1,500/2,500
   :::column-end:::
   :::column span="":::
        2,500/4,000
   :::column-end:::
:::row-end:::

**最小**、 **推荐** 和 **最佳性能** 带宽要求基于每个终结点的使用情况。 通常，每个用户都有一个终结点，例如计算机或移动设备。 但是，如果用户在 *同时* 计算机 *和移动设备* 加入 Teams 会议，则两个终结点将与该用户关联。

- **视频通话的最小** 带宽要求最高为 240p 分辨率，屏幕共享内容帧速率自适应为 1.875 到 7.5fps，而"协同模式/大型库"视频分辨率高达 540p。  

- **建议** 视频通话带宽要求高达 1080p 分辨率 <sup>\*</sup>、屏幕共享内容帧速率自适应 7.5 到 30fps，以及高达 1080p 分辨率的汇总模式/大型库视频 <sup>\*</sup>。  

- **最佳性能** 指南允许使用屏幕共享内容帧速率自适应 15 到 30fps，为较大的与会者会议、高损失环境和更高的运动内容提供更高的保真视频。

<sup>\*</sup>预期质量最高为 1080p，但根据网络条件，视频分辨率和质量将相应地进行优化。  

## <a name="related-topics"></a>相关主题

[Microsoft 365 和 Office 365 网络连接原则](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[全球范围终结点：Skype for Business Online 和 Teams](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

[Teams 的代理服务器](proxy-servers-for-skype-for-business-online.md)

[Teams 中的媒体：会议简单的原因](https://aka.ms/teams-media)

[Teams 中的媒体：深入了解媒体流](https://aka.ms/teams-media-flows)

[Teams 中的标识模式和身份验证](identify-models-authentication.md)

[如何部署 Teams](./deploy-overview.md)

[Teams 疑难解答](/MicrosoftTeams/troubleshoot/teams)
