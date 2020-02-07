---
title: 用于在 Microsoft Teams 中配置直接路由的上线清单
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 06/07/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: 在团队中配置直接路由时，请按照此清单中的核心、待办任务和活动。
localization_priority: Normal
f1.keywords:
- NOCSH
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: e6179eec9d6f08bb40b5bae493cb49f59f8eddd6
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837422"
---
# <a name="configure-direct-routing-in-microsoft-teams"></a>在 Microsoft 团队中配置直接路由

## <a name="direct-routing"></a>直接路由

| 否 | 活动或任务 | 说明 | 已完成？ | 其他信息 |
|----|-------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|1|确定将为你的组织的位置部署哪些 PSTN 连接|Microsoft 为使用 Office 365 Phone 系统的用户提供了 PSTN 连接的备用方法。<ul><li>带有呼叫计划的电话系统（"通话计划"）： Skype for Business Online 和团队<li>电话系统直接路由（"直接路由"）：仅限团队<li>具有本地 PSTN 连接的电话系统：仅适用于 Skype for business Online<li>Skype for business 云连接器版：仅 Skype for business Online</ul>直接路由为组织提供与呼叫计划同样的好处，不同之处在于 PSTN 连接是由第三方提供商而不是 Microsoft 提供的。 这允许在不支持呼叫计划的国家/地区进行部署，或在需要维护现有 PSTN 服务提供商合同或需要与某些内部部署系统进行互操作的部署中进行部署。<br><br>确定哪些选项最适合你的组织。 | |[音频会议和通话套餐的国家/地区可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)<br><br>[用于音频会议和通话计划的加入清单](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams) |
|ppls-2|验证用于启用直接路由的用户和部署节奏列表|检查在范围内是否有业务部门或网站的列表，以便与团队直接路由。 使用 "目标" 和 "关键结果" 模型，即可处理直接路由范围内的用户。 我们建议你按逐个网站的方式工作，以便你可以专注于你的资源。<br><br>作为支持计划的一部分，确定将启用哪些用户（试验、站点1、站点2等）。||[直接路由展望](2-envision-make-my-service-decisions-direct-routing.md)|
|3|规划和获取许可证|直接路由用户必须在 Office 365 中分配以下许可证：<ul><li>Skype for Business Online（计划 2）<li>Microsoft Phone 系统<li>Microsoft Teams<li>Microsoft 音频会议</ul>直接路由还支持已授权呼叫计划的用户。 带有呼叫计划的电话系统可以通过使用直接路由界面来路由某些呼叫。<br><br>将外部参与者添加到计划会议需要使用音频会议许可证，方法是通过拨出或提供拨入号码。||[直接路由许可](https://docs.microsoft.com/microsoftteams/direct-routing-plan#licensing-and-other-requirements)|
|4|规划会话边框控制器（SBC）域名|SBC 域名必须来自租户的 "域" 中注册的一个名称。<br><br>**注意：** 不能对 SBC 的完全限定的域名（FQDN）使用 * onmicrosoft.com。<br><br>SBC 域名对于规划每个 SBC 所需的证书也很重要。||[SBC 域名称](https://docs.microsoft.com/microsoftteams/direct-routing-plan#sbc-domain-names)|
|5|对证书进行计划|我们强烈建议你通过生成证书签名请求（CSR）请求 SBC 的证书。<br><br>证书需要在 "主题"、"公用名" 或 "使用者备用名称" 字段中具有 SBC FQDN。 或者，直接路由支持公用名或使用者替换名称中的通配符。<br><br>有关为 SBC 生成 CSR 的特定说明，请参阅 SBC 供应商提供的文档。<br><br>"**其他信息**" 列中的文章将列出受支持的根证书颁发机构。||[适用于 SBC 的公共受信任证书](https://docs.microsoft.com/microsoftteams/direct-routing-plan#public-trusted-certificate-for-the-sbc)|
|6|规划和配置防火墙端口|直接路由的连接点是以下三个 Fqdn：<ul><li>sip.pstnhub.microsoft.com<li>sip2.pstnhub.microsoft.com<li>sip3.pstnhub.microsoft.com</ul>必须在企业防火墙上允许这些连接点和 SBCs 之间的流量。 配置 SBC 时，在 SBC 上定义 TCP 端口。<br><br>媒体流量采用 UDP。 此类流量流入和流出媒体处理器组件。 在 SBCs 和媒体处理器之间的双向通信也必须在防火墙上允许。<br><br>**注意：** 媒体处理器具有动态 IP 地址，静态 IP 地址将在以后可用。 请务必允许[Azure 数据中心 Ip 范围](https://www.microsoft.com/download/details.aspx?id=41653)内列出的任何 IP 地址。||[SIP 信号： Fqdn 和防火墙端口](https://docs.microsoft.com/microsoftteams/direct-routing-plan#sip-signaling-fqdns-and-firewall-ports)<br><br>[媒体流量： IP 地址和端口范围](https://docs.microsoft.com/microsoftteams/direct-routing-plan#media-traffic-port-ranges)<br><br>[Azure 数据中心 IP 范围](https://www.microsoft.com/download/details.aspx?id=41653)|
|7|配置 SBCs|Microsoft 仅支持经认证的 SBCs 与直接路由配对。<br><br>通过使用特定于供应商的指南和 "**其他信息**" 列中的文章中的说明来配置 SBCs。||[支持的会话边框控制器（SBCs）](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs)|
|个|通过直接路由对 SBCs 配对|每个站点中的 SBCs 必须与直接路由配对，以便使用您自己的中继提供拨号音和 PSTN 呼叫功能。<br><br>验证特定站点中的 SBC 是否已与直接路由配对，如果之前未执行，则配置配对。<br><br>Microsoft 仅支持经认证的 SBC 与直接路由配对。 验证该网站中的 SBC 是否已认证。||[将 SBC 配对到电话系统的直接路由服务](https://docs.microsoft.com/microsoftteams/direct-routing-configure#pair-the-sbc-to-direct-routing-service-of-phone-system)|
|db-9|验证 SBC 配对|针对为`Get-CsOnlinePSTNGateway`特定网站配对的每个 SBC 运行 cmdlet，并验证**启用**的参数是否显示值**True**。<br><br>使用 SBC 管理接口验证 SBC 是否收到对传出 SIP 选项的**200 "确定"** 响应。|||
|10|验证用户配置|验证用户帐户是在 Office 365 中直接创建还是通过使用目录同步与 Office 365 同步。<br><br>验证是否为用户分配了必要的许可证。<br><br>对于直接路由的 PSTN 连接，你的用户必须托管在 Skype for Business Online 中，并且已启用 Microsoft 团队。||[为用户启用直接路由服务](https://docs.microsoft.com/microsoftteams/direct-routing-configure#enable-users-for-direct-routing-service)|
|11|配置用户的电话号码|必须为直接路由范围内的所有用户分配其电话号码和语音邮件。<br><br> 使用`Set-CsUser` cmdlet 启用语音邮件并为用户分配电话号码。||[配置电话号码并启用企业语音和语音邮件](https://docs.microsoft.com/microsoftteams/direct-routing-configure#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail)|
|至|配置语音路由|电话系统具有一种路由机制，允许根据以下情况将呼叫发送到特定的 SBC：<ul><li>名为 "号码模式"<li>称为 "号码模式 +" 的特定用户进行呼叫</ul>通过创建以下内容为用户配置语音路由：<ul><li>语音路由策略<li>PSTN 用法<li>语音路由<li>联机 PSTN 网关</ul>||[配置语音路由](https://docs.microsoft.com/microsoftteams/direct-routing-configure#configure-voice-routing)|
|13|将 Microsoft 团队设置为用户的首选调用客户端|在用户可以在 Microsoft 团队中看到 "**调用**" 选项卡之前，需要在 microsoft 团队中为租户启用**专用呼叫**，并且团队客户端必须配置为用户的**首选调用客户端**。||[启用 Microsoft 团队通话](https://docs.microsoft.com/microsoftteams/direct-routing-configure#enable-calling-for-microsoft-teams)<br><br>[将 Microsoft 团队设置为用户的首选调用客户端](https://docs.microsoft.com/microsoftteams/direct-routing-configure#set-microsoft-teams-as-the-preferred-calling-client-for-the-users)|
|14|为用户启用直接路由|通过使用直接路由通过配置的 SBC 将语音路由策略分配给将通过直接路由进行的用户。||[为用户启用直接路由服务](https://docs.microsoft.com/microsoftteams/direct-routing-configure#enable-users-for-direct-routing-service)|
|岁|准备和执行用户验收测试|准备和执行用户验收测试，包括拨入和拨出方案。||[在团队中测试云语音工作负载](https://docs.microsoft.com/MicrosoftTeams/1-onboard-prepare-my-service#test-cloud-voice-workloads-in-teams)|
|utf-16|报表使用情况、运行状况、关键成功指示器（KSIs）和质量|在 Envision 阶段中定义的情况下报告使用情况、运行状况、KSIs 和质量。||[《操作指南》](https://docs.microsoft.com/MicrosoftTeams/1-drive-value-operate-my-service)|

## <a name="next-steps"></a>后续步骤

完成此清单后，您将成功配置了与团队部署的直接路由。

下一步，使用[网站支持行动手册 For 语音（行动手册）](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)帮助你在每个网站上为你的用户板载，并帮助确保你规划和执行重要的特定于网站的活动。
