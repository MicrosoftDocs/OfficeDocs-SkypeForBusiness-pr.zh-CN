---
title: 加入清单 - 配置直接路由 - Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 06/07/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: 在 Teams 中配置直接路由时，请按照此清单中的核心、要执行的任务和活动进行操作。
ms.localizationpriority: medium
f1.keywords:
- NOCSH
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.collection:
- M365-voice
ms.openlocfilehash: b61e2f348a11df5003a1eaf4dd53897b0c72b027
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2022
ms.locfileid: "67270907"
---
# <a name="configure-direct-routing-in-microsoft-teams"></a>在 Microsoft Teams 中配置直接路由

## <a name="direct-routing"></a>直接路由

| 否 | 活动或任务 | 说明 | 已完成？ | 其他信息 |
|----|-------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|1|确定要为组织的位置部署哪些 PSTN 连接|Microsoft 提供了使用 Microsoft 365 或 Office 365 电话系统 为用户提供 PSTN 连接的替代方法。<ul><li>具有呼叫计划的电话系统 (“呼叫计划”) ：Skype for Business联机和 Teams<li>电话系统直接路由 (“直接路由”) ：仅限 Teams<li>具有本地 PSTN 连接的电话系统：仅Skype for Business联机<li>Skype for Business 云连接器版本：仅Skype for Business联机</ul>直接路由为组织提供与通话套餐相同的优势，但 PSTN 连接是由第三方提供商而不是 Microsoft 促进的。 这允许在通话套餐不可用的国家/地区或需要维护现有 PSTN 服务提供商合同或与某些本地系统互操作性的部署中进行部署。<br><br>确定哪个选项 () 最适合你的组织。 | |[音频会议和通话套餐的国家/地区可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)<br><br>[加入音频会议和通话套餐的清单](./onboarding-checklist-configure-cloud-voice-workloads-in-microsoft-teams.md) |
|2|验证用户列表以及启用直接路由的部署节奏|检查是否在 Teams 直接路由范围内包含业务单位或站点的列表。 使用目标和关键结果模型，确定哪些用户将在直接路由范围内。 我们建议你逐站点工作，以便可以集中资源。<br><br>作为启用计划的一部分，通过 (“试点”、“站点 1”、“站点 2”等) 来确定要启用的用户。||[直接路由构想](./direct-routing-landing-page.md)|
|3|规划和获取许可证|直接路由的用户必须在 Microsoft 365 或Office 365中分配以下许可证：<ul><li>Skype for Business Online（计划 2）<li>Microsoft Phone 系统<li>Microsoft Teams<li>Microsoft 音频会议</ul>直接路由还支持获得通话套餐许可的用户。 具有通话套餐的电话系统可以使用直接路由接口路由某些呼叫。<br><br>音频会议许可证是将外部参与者添加到计划会议所必需的，方法是向他们拨号或提供拨入号码。||[直接路由许可](direct-routing-plan.md)|
|4|规划会话边框控制器 (SBC) 域名|SBC 域名必须来自租户的“域”中注册的某个名称。<br><br>**注意：** 不能对 SBC 的 FQDN)  (完全限定的域名使用 *.onmicrosoft.com。<br><br>在规划每个 SBC 所需的证书时，SBC 域名也很重要。||[SBC 域名](direct-routing-plan.md)|
|5|规划证书|强烈建议通过生成证书签名请求 (CSR) 来请求 SBC 的证书。<br><br>证书需要在使用者、公用名称或使用者备用名称字段中具有 SBC FQDN。 或者，直接路由支持公用名称或使用者备用名称中的通配符。<br><br>有关为 SBC 生成 CSR 的具体说明，请参阅 SBC 供应商提供的文档。<br><br>“ **其他信息** ”列中的文章列出了支持的根证书颁发机构。||[SBC 的公共受信任证书](direct-routing-plan.md)|
|6|规划和配置防火墙端口|直接路由的连接点是以下三个 FQDN：<ul><li>sip.pstnhub.microsoft.com<li>sip2.pstnhub.microsoft.com<li>sip3.pstnhub.microsoft.com</ul>必须在公司防火墙上允许这些连接点与 SBC 之间的流量。 配置 SBC 时，可在 SBC 上定义 TCP 端口。<br><br>媒体流量位于 UDP 上。 此类流量流向和流出媒体处理器组件。 还必须在防火墙上允许 SBC 与媒体处理器之间的双向流量。<br><br>**注意：** 媒体处理器具有动态 IP 地址，静态 IP 地址稍后将可用。 请务必允许 [Azure 数据中心 IP 范围](https://www.microsoft.com/download/details.aspx?id=41653)中列出的任何 IP 地址。||[SIP 信号：FQDN 和防火墙端口](direct-routing-plan.md)<br><br>[媒体流量：IP 地址和端口范围](direct-routing-plan.md)<br><br>[Azure 数据中心 IP 范围](https://www.microsoft.com/download/details.aspx?id=41653)|
|7|配置 SBC|Microsoft 仅支持通过认证的 SBC 与直接路由配对。<br><br>使用特定于供应商的指南和“ **其他信息** ”列中文章中的说明配置 SBC。||[支持的会话边框控制器 (SBC) ](direct-routing-plan.md)|
|8|将 SBC 与直接路由配对|每个站点中的 SBC 必须与直接路由配对，才能使用自己的中继提供拨号音和 PSTN 呼叫功能。<br><br>验证该特定站点中的 SBC 已与直接路由配对，或者配置该对（如果之前未执行）。<br><br>Microsoft 仅支持经认证的 SBC 与直接路由配对。 验证该站点中的 SBC 是否已通过认证。||[将 SBC 与电话系统的直接路由服务配对](direct-routing-configure.md)|
|9|验证 SBC 配对|`Get-CsOnlinePSTNGateway`运行针对特定站点配对的每个 SBC 的 cmdlet，并验证 **启用** 的参数是否显示值 **True**。<br><br>使用 SBC 管理接口验证 SBC 是否获取对传出 SIP OPTIONS 的 **200 个“确定”**  响应。|||
|10|验证用户配置|验证用户帐户是直接在 Microsoft 365 中创建的，还是通过使用目录同步Office 365。<br><br>验证是否已将所需的许可证分配给用户。<br><br>对于 PSTN 与直接路由的连接，用户必须驻留在 Skype for Business Online 中并为 Microsoft Teams 启用。||[为用户启用直接路由服务](direct-routing-configure.md)|
|11|配置用户的电话号码|必须为直接路由范围内的所有用户分配其电话号码。<br><br> 使用 `Set-CsPhoneNumberAssignment` cmdlet 将电话号码分配给用户。||[配置电话号码并启用企业语音和语音邮件](direct-routing-configure.md)|
|12|配置语音路由|电话系统有一个路由机制，允许基于以下情况将呼叫发送到特定 SBC：<ul><li>调用的数字模式<li>调用号码模式 + 进行呼叫的特定用户</ul>通过创建以下方法为用户配置语音路由：<ul><li>语音路由策略<li>PSTN 使用情况<li>语音路由<li>联机 PSTN 网关</ul>||[配置语音路由](direct-routing-configure.md)|
|13|将 Microsoft Teams 设置为用户的首选呼叫客户端|用户在 Microsoft Teams 中看到 **“呼叫”** 选项卡之前，需要为 Microsoft Teams 中的租户启用 **专用呼叫** ，并且 Teams 客户端必须配置为用户的 **首选呼叫客户端** 。||[启用 Microsoft Teams 通话](direct-routing-configure.md)<br><br>[将 Microsoft Teams 设置为用户的首选呼叫客户端](direct-routing-configure.md)|
|14|为用户启用直接路由|通过配置的 SBC 使用直接路由将语音路由策略分配给将发出和获取 PSTN 呼叫的用户。||[为用户启用直接路由服务](direct-routing-configure.md)|
|15|准备并执行用户接受测试|准备和执行用户接受测试，包括拨入和拨出方案。||[在 Teams 中测试云语音工作负荷](1-onboard-prepare-my-service.md)|
|16|报告使用情况、运行状况、关键成功指标 (KSIS) 和质量|报告在构想阶段定义的使用情况、运行状况、KIS 和质量。||[《操作指南》](1-drive-value-operate-my-service.md)|

## <a name="next-steps"></a>后续步骤

完成此清单后，你将使用 Teams 部署成功配置直接路由。

下一步，请使用 [“语音 (Playbook 网站启用 Playbook) ](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) 来帮助你在每个网站上载入用户，并帮助确保规划和执行特定于网站的重要活动。
