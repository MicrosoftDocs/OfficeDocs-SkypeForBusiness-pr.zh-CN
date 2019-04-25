---
title: 用于在 Microsoft Teams 中配置直接路由的上线清单
author: rmw2890
ms.author: MyAdvisor
manager: serdars
ms.date: 06/07/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: 直接路由配置中的团队时，请按照的核心、 待办事项任务和此检查表中的活动。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4e71ed6068c56ab6486e7b4d976ff82c325fe22a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32228412"
---
# <a name="configure-direct-routing-in-microsoft-teams"></a>配置中的 Microsoft 团队的直接路由

## <a name="direct-routing"></a>直接路由

| 否 | 活动或任务 | 说明 | 已完成？ | 其他信息 |
|----|-------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|1|确定将为您的组织的位置部署的 PSTN 连接|Microsoft 提供的其他方法来为您使用 Office 365 电话系统的用户提供 PSTN 连接。<ul><li>调用计划 （"呼叫计划"） 电话系统： Skype 在线业务和团队<li>电话系统，直接路由 （"直接路由"）： 仅团队<li>内部部署与 PSTN 连接电话系统： 业务 online 仅 Skype<li>商务云连接器版的 Skype: for Business 的 Skype 仅联机</ul>直接路由为组织提供了为调用计划，相同的好处在于通过第三方提供程序，而不是 Microsoft 方便了 PSTN 连接。 这样可以部署在国家/地区其中调用计划不可用，或在部署中现有 PSTN 服务提供程序合同需要进行维护或与特定的本地系统的互操作性所需的位置。<br><br>确定哪些选项最适合您的组织。 | |[音频会议和通话套餐的国家/地区可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)<br><br>[入职培训音频会议和调用计划的清单](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams) |
|2|验证您的用户和启用直接路由中的部署步调列表|确认您具有业务部门或网站的列表的直接路由与团队的范围内。 使用目标和关键结果模型，计算出哪些用户将直接路由的范围。 我们建议从事单独对网站的网站，以便您可以使您的资源。<br><br>为启用计划的一部分，确定哪些用户将启用，通过何时 （试验、 站点 1、 站点 2 等）。||[直接路由构想](2-envision-make-my-service-decisions-direct-routing.md)|
|3|规划和获取许可证|直接路由中的用户必须具有以下许可证分配 Office 365 中：<ul><li>Skype for Business Online（计划 2）<li>Microsoft 电话系统<li>Microsoft Teams<li>Microsoft 音频会议</ul>直接路由还支持的调用计划许可的用户。 与调用计划的电话系统可以将一些呼叫路由使用直接路由界面。<br><br>需要向计划的会议，外部参与者通过向他们拨出或通过提供的电话拨入式号码的音频会议许可证。||[直接路由许可](https://docs.microsoft.com/microsoftteams/direct-routing-plan#licensing-and-other-requirements)|
|4|规划会话边框控制器 (SBC) 域名|SBC 域名必须介于 1"域"的租户中注册的名称。<br><br>**注意：** 不能使用 *。 onmicrosoft.com SBC 的完全限定的域名 (FQDN)。<br><br>SBC 域名称也是规划所需的每个 SBC 证书重要的。||[SBC 域名](https://docs.microsoft.com/microsoftteams/direct-routing-plan#sbc-domain-names)|
|5|规划证书|我们强烈建议您申请证书的 SBC 通过生成证书签名请求 (CSR)。<br><br>证书需要有主题、 公共名称或使用者替代名称字段中的 SBC FQDN。 此外，直接路由中常见的名称或使用者替代名称中支持通配符。<br><br>生成发往 SBC CSR 的具体说明，请参阅您的 SBC 供应商提供的文档。<br><br>**的其他信息**列中的文章列出了受支持的根证书颁发机构。||[SBC 的受信任的公共证书](https://docs.microsoft.com/microsoftteams/direct-routing-plan#public-trusted-certificate-for-the-sbc)|
|6|规划和配置防火墙端口|直接路由的连接点是具有以下三个 Fqdn:<ul><li>sip.pstnhub.microsoft.com<li>sip2.pstnhub.microsoft.com<li>sip3.pstnhub.microsoft.com</ul>必须在企业防火墙允许这些连接点和您的 Sbc 之间的通信。 配置 SBC 时，可在 SBC 中定义的 TCP 端口。<br><br>UDP 上媒体流量。 此类型的通信流与媒体处理器组件。 此外必须在您的防火墙允许 Sbc 和媒体处理器之间的双向通信。<br><br>**注意：** 媒体处理器具有动态 IP 地址，并且的静态 IP 地址将提供更高版本。 务必您允许中的[Azure 数据中心 IP 范围](https://www.microsoft.com/download/details.aspx?id=41653)列出任意 IP 地址。||[SIP 信号： Fqdn 和防火墙端口](https://docs.microsoft.com/microsoftteams/direct-routing-plan#sip-signaling-fqdns-and-firewall-ports)<br><br>[媒体流量： IP 地址和端口范围](https://docs.microsoft.com/microsoftteams/direct-routing-plan#media-traffic-port-ranges)<br><br>[Azure 数据中心 IP 地址范围](https://www.microsoft.com/download/details.aspx?id=41653)|
|7|配置 Sbc|Microsoft 仅支持可直接路由与配对认证的 SBCs。<br><br>通过使用一文中的**其他信息**列中的供应商特定指导和说明配置 Sbc。||[支持会话边界控制器 (Sbc)](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs)|
|8|对 SBCs 直接路由|每个站点中的 Sbc 必须直接路由以使用自己中继提供拨号音和 PSTN 呼叫功能与配对。<br><br>验证该特定网站中的 SBC 直接路由与已配对时，或如果之前未执行配置对。<br><br>Microsoft 支持仅认证的 SBC 的可直接路由与配对。 验证该网站中的 SBC 认证。||[配对 SBC 定向电话系统的路由服务](https://docs.microsoft.com/microsoftteams/direct-routing-configure#pair-the-sbc-to-direct-routing-service-of-phone-system)|
|9|验证 SBC 配对|运行`Get-CsOnlinePSTNGateway`cmdlet 以获取每个 SBC 配对的特定站点并验证参数**启用**显示值**True**。<br><br>SBC 管理界面用于验证 SBC 获取**200"OK"** エ ・ 复 ハ 传出 SIP 选项。|||
|10|验证用户配置|验证的用户帐户是在 Office 365 中直接创建或使用目录同步同步到 Office 365。<br><br>验证所需的许可证已分配给用户。<br><br>直接路由中的 PSTN 连接，必须为业务 Online 驻留在 Skype 并启用的 Microsoft 团队您的用户。||[为用户启用直接路由服务](https://docs.microsoft.com/microsoftteams/direct-routing-configure#enable-users-for-direct-routing-service)|
|11|配置用户的电话号码|必须分配直接路由作用域中的所有用户，他们的电话号码和语音邮件。<br><br> 使用`Set-CsUser`cmdlet 启用语音邮件和向用户分配电话号码。||[配置的电话号码和启用企业语音和语音邮件](https://docs.microsoft.com/microsoftteams/direct-routing-configure#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail)|
|12|配置语音路由|电话系统具有可以将呼叫发送给基于特定 SBC 路由机制：<ul><li>呼叫的号码模式<li>呼叫的号码模式 + 调用的特定用户</ul>配置语音路由用户通过创建：<ul><li>语音路由策略<li>PSTN 用法<li>语音路由<li>联机 PSTN 网关</ul>||[配置语音路由](https://docs.microsoft.com/microsoftteams/direct-routing-configure#configure-voice-routing)|
|13|作为首选的呼叫客户端为用户的 Microsoft 团队|用户可以看到**呼叫**选项卡中的 Microsoft 团队之前，您需要启用租户中的 Microsoft 团队的**专用电话**和团队客户端必须配置为**首选调用客户端**的用户。||[启用 Microsoft 团队的呼叫](https://docs.microsoft.com/microsoftteams/direct-routing-configure#enable-calling-for-microsoft-teams)<br><br>[作为首选的呼叫客户端为用户的 Microsoft 团队](https://docs.microsoft.com/microsoftteams/direct-routing-configure#set-microsoft-teams-as-the-preferred-calling-client-for-the-users)|
|14|为用户启用直接路由|将语音路由策略分配给的用户将使并获取使用直接路由配置 SBC 通过 PSTN 呼叫。||[为用户启用直接路由服务](https://docs.microsoft.com/microsoftteams/direct-routing-configure#enable-users-for-direct-routing-service)|
|15|准备和执行用户验收测试|准备和执行用户验收测试，包括电话拨入式和拨出式应用场景。||[团队中的测试云语音工作负荷](https://docs.microsoft.com/MicrosoftTeams/1-onboard-prepare-my-service#test-cloud-voice-workloads-in-teams)|
|16|报告使用情况、 运行状况、 关键成功指标 (KSIs) 和质量|定义在构想阶段报告使用情况、 运行状况、 KSIs 和质量。||[《操作指南》](https://docs.microsoft.com/MicrosoftTeams/1-drive-value-operate-my-service)|

## <a name="next-steps"></a>后续步骤

完成此检查表后，您将已成功配置直接路由到团队的部署。

在下一步，使用[语音设置 （方案） 的网站启用设置方案](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)可帮助您加载您的用户在每个站点，并帮助确保您规划和执行特定于网站的重要活动。
