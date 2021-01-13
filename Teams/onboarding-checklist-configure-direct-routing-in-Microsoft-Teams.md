---
title: 载入清单 - 配置直接路由 - Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 06/07/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: 在 Teams 中配置直接路由时，请遵循此清单中的核心任务和活动。
localization_priority: Normal
f1.keywords:
- NOCSH
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 19a196c9a995bf146e2737ff72b298a0be2b3392
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812922"
---
# <a name="configure-direct-routing-in-microsoft-teams"></a>在 Microsoft Teams 中配置直接路由

## <a name="direct-routing"></a>直接路由

| 否 | 活动或任务 | 描述 | 已完成？ | 其他信息 |
|----|-------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|1|确定将为组织的位置部署哪个 PSTN 连接|Microsoft 提供替代方法，为使用 Microsoft 365 或 Office 365 电话系统的用户提供 PSTN 连接。<ul><li>具有通话套餐的电话 ("通话套餐") ：Skype for Business Online 和 Teams<li>电话系统直接路由 ("直接路由") ：仅 Teams<li>具有本地 PSTN 连接的电话系统：仅 Skype for Business Online<li>Skype for Business Cloud Connector Edition：仅 Skype for Business Online</ul>直接路由为组织提供了与呼叫计划相同的优势，只不过 PSTN 连接由第三方提供商而不是 Microsoft 提供。 这允许在呼叫计划不可用的国家/地区部署，或在需要维护现有 PSTN 服务提供商合同或需要与某些本地系统互操作性的部署中部署。<br><br>确定最适合 () 的选项。 | |[音频会议和通话套餐的国家/地区可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)<br><br>[加入音频会议和通话计划的清单](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams) |
|2|验证用户列表和启用直接路由的部署节奏|检查你在使用 Teams 进行直接路由时是否包含业务单位或网站的列表。 使用目标和关键结果模型，确定哪些用户将参与直接路由。 我们建议你按站点工作，以便可以专注于资源。<br><br>作为启用计划的一部分，请确定要启用的用户， (试点、站点 1、站点 2 等进行) 。||[直接路由构想](2-envision-make-my-service-decisions-direct-routing.md)|
|3|计划和获取许可证|直接路由的用户必须在 Microsoft 365 或 Office 365 中分配以下许可证：<ul><li>Skype for Business Online（计划 2）<li>Microsoft Phone 系统<li>Microsoft Teams<li>Microsoft 音频会议</ul>直接路由还支持获得呼叫计划许可的用户。 具有呼叫计划的电话系统可以使用直接路由接口路由某些呼叫。<br><br>通过拨出或提供拨入号码将外部参与者添加到计划的会议需要音频会议许可证。||[直接路由许可](https://docs.microsoft.com/microsoftteams/direct-routing-plan#licensing-and-other-requirements)|
|4|规划会话边界控制器 (SBC) 域名|SBC 域名必须来自租户的"域"中注册的名称之一。<br><br>**注意：** 不能将 *.onmicrosoft.com 用于 SBC 的 FQDN () 域名。<br><br>在规划每个 SBC 所需的证书时，SBC 域名也很重要。||[SBC 域名](https://docs.microsoft.com/microsoftteams/direct-routing-plan#sbc-domain-names)|
|5|规划证书|强烈建议通过生成认证签名请求来请求 SBC 的证书， (CSR) 。<br><br>证书需要在主题、公用名称或主题备用名称字段中具有 SBC FQDN。 或者，直接路由支持公用名称或主题备用名称中的通配符。<br><br>有关为 SBC 生成 CSR 的详细说明，请参阅 SBC 供应商提供的文档。<br><br>"其他信息 **"列中的文章** 列出了支持的根证书颁发机构。||[SBC 的公共受信任证书](https://docs.microsoft.com/microsoftteams/direct-routing-plan#public-trusted-certificate-for-the-sbc)|
|6|计划和配置防火墙端口|直接路由的连接点为以下三个 FQDN：<ul><li>sip.pstnhub.microsoft.com<li>sip2.pstnhub.microsoft.com<li>sip3.pstnhub.microsoft.com</ul>必须在企业防火墙上允许这些连接点与 SDC 之间的流量。 配置 SBC 时，在 SBC 上定义 TCP 端口。<br><br>媒体流量位于 UDP 上。 此类流量流入和流出媒体处理器组件。 还必须在防火墙上允许 SDC 与媒体处理器之间的双向流量。<br><br>**注意：** 媒体处理器具有动态 IP 地址，静态 IP 地址将在以后提供。 必须允许 Azure 数据中心 IP 范围中列出的任何 [IP 地址](https://www.microsoft.com/download/details.aspx?id=41653)。||[SIP 信号：FQDN 和防火墙端口](https://docs.microsoft.com/microsoftteams/direct-routing-plan#sip-signaling-fqdns-and-firewall-ports)<br><br>[媒体流量：IP 地址和端口范围](https://docs.microsoft.com/microsoftteams/direct-routing-plan#media-traffic-port-ranges)<br><br>[Azure 数据中心 IP 范围](https://www.microsoft.com/download/details.aspx?id=41653)|
|7|配置 SDC|Microsoft 仅支持通过认证的 SDC 与直接路由配对。<br><br>使用特定于供应商的指南和"其他信息"列中文章中的说明配置 **SDC。**||[支持的会话边界控制器 (SDC) ](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs)|
|8|将 SDC 与直接路由配对|每个站点中的 SDC 必须与直接路由配对，以便使用自己的中继提供拨号音和 PSTN 呼叫功能。<br><br>验证该特定站点中的 SBC 已与直接路由配对，或者配置配对（如果以前未执行）。<br><br>Microsoft 仅支持通过认证的 SBC 与直接路由配对。 验证该站点中的 SBC 是否经过认证。||[将 SBC 与电话系统的直接路由服务配对](https://docs.microsoft.com/microsoftteams/direct-routing-configure#pair-the-sbc-to-direct-routing-service-of-phone-system)|
|9|验证 SBC 配对|为为特定站点配对的每个 SBC 运行 `Get-CsOnlinePSTNGateway` cmdlet，并验证 Enabled参数是否显示值 **True。**<br><br>使用 SBC 管理接口验证 SBC 是否获取了对传出 SIP 选项 **的 200**  个"正常"响应。|||
|10|验证用户配置|验证用户帐户是直接在 Microsoft 365 中创建，还是使用目录同步同步到 Microsoft 365 或 Office 365。<br><br>验证是否向用户分配了所需的许可证。<br><br>对于与直接路由的 PSTN 连接，你的用户必须在 Skype for Business Online 中并启用 Microsoft Teams。||[为用户启用直接路由服务](https://docs.microsoft.com/microsoftteams/direct-routing-configure#enable-users-for-direct-routing-service)|
|11|配置用户的电话号码|必须为位于直接路由范围的所有用户分配其电话号码和语音邮件。<br><br> 使用 `Set-CsUser` cmdlet 启用语音邮件并将电话号码分配给用户。||[配置电话号码并启用企业语音和语音邮件](https://docs.microsoft.com/microsoftteams/direct-routing-configure#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail)|
|12|配置语音路由|电话系统具有一种路由机制，允许基于：<ul><li>调用的编号模式<li>呼叫号码模式 + 进行呼叫的特定用户</ul>通过创建以下命令为用户配置语音路由：<ul><li>语音路由策略<li>PSTN 使用情况<li>语音路由<li>联机 PSTN 网关</ul>||[配置语音路由](https://docs.microsoft.com/microsoftteams/direct-routing-configure#configure-voice-routing)|
|13|将 Microsoft Teams 设置为用户的首选呼叫客户端|在用户可以看到 Microsoft  Teams 中的"呼叫"选项卡之前，你需要为 Microsoft Teams 中的租户启用专用呼叫，并且 Teams 客户端必须配置为用户 **的首选呼叫客户端**。||[为 Microsoft Teams 启用通话](https://docs.microsoft.com/microsoftteams/direct-routing-configure#enable-calling-for-microsoft-teams)<br><br>[将 Microsoft Teams 设置为用户的首选呼叫客户端](https://docs.microsoft.com/microsoftteams/direct-routing-configure#set-microsoft-teams-as-the-preferred-calling-client-for-the-users)|
|14|为用户启用直接路由|通过配置的 SBC 使用直接路由将语音路由策略分配给将拨打和接听 PSTN 呼叫的用户。||[为用户启用直接路由服务](https://docs.microsoft.com/microsoftteams/direct-routing-configure#enable-users-for-direct-routing-service)|
|15|准备并执行用户验收测试|准备并执行用户验收测试，包括拨入和拨出方案。||[在 Teams 中测试云语音工作负荷](https://docs.microsoft.com/MicrosoftTeams/1-onboard-prepare-my-service#test-cloud-voice-workloads-in-teams)|
|16|报告使用情况、运行状况、关键成功 (、) 以及质量|报告在"构想"阶段定义的使用情况、运行状况、KSIS 和质量。||[《操作指南》](https://docs.microsoft.com/MicrosoftTeams/1-drive-value-operate-my-service)|

## <a name="next-steps"></a>后续步骤

完成此清单后，你已成功通过 Teams 部署配置了直接路由。

下一步，使用 [Voice (Playbook) ](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) 网站启用 Playbook 来帮助你在每个网站上载入用户，并帮助确保你计划和执行重要的特定于网站的活动。
