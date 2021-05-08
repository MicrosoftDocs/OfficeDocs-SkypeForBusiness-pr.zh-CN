---
title: 载入清单 - 配置云语音工作负荷 - Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: rowille
description: 在云语音中配置云语音工作负荷时，请遵循此清单中的核心任务和活动Teams。
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7c9c22190a5a4237eaa61ede4c7aa82e7a7cee94
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098048"
---
# <a name="configure-cloud-voice-workloads-in-microsoft-teams"></a>在云中配置云语音Microsoft Teams

## <a name="audio-conferencing"></a>音频会议

| 不支持 | 活动或任务 | 说明 | 已完成？ | 其他信息 |
|----|-------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | 确定音频会议是否可用于组织的位置 | Microsoft 提供跨多个国家/地区和城市的音频会议。 有关涵盖 **的国家和地区的最新** 列表，请参阅"其他信息"列中的指南。 <br/><br/> 可以选择一个或多个国家/地区，Teams哪些语音工作负荷可用。 | | [音频会议和通话套餐的国家/地区可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) |
| 2  | 验证用户列表和启用音频会议部署的节奏    | 检查您是否有一个列表，其中列出了适用于音频会议Teams。 使用目标和关键结果模型，确定哪些用户将在范围内。 我们建议你按站点工作，以便专注于资源。<br/><br/> 作为启用计划的一部分，确定要启用的用户以及何时 (试点、站点 1、站点 2 等) 。 | | [音频会议构想](./audio-conferencing-in-office-365.md)|
| 3  | 获取电话号码 | 了解可用于音频会议工作负荷的服务Teams号码。<br/><br/> 从 Microsoft 获取新电话号码，或为网站的音频会议网桥号码安排号码移植。<br/><br/> 对于音频会议，您还可以转移现有的免费电话号码，或者从 Microsoft 获取新的免费电话号码。<br/><br/> 若要获取服务号码，如果列出的国家/地区在 Skype for Business 管理中心中不可用，请在美国) 或 (以外的国家/地区向 (发送新的电话号码请求 <ptn@microsoft.com> <ptneu@microsoft.com>) 。 有关详细信息，请参阅"其他信息"列中链接到的"管理组织 **的电话号码"** 指南。 <br/><br/>**注意：** 根据服务提供商的不同，号码移植过程最多可能需要 30 天。 请务必在规划中考虑到这一点。 | | [用于通话套餐的不同类型的电话号码](/SkypeForBusiness/what-are-calling-plans-in-office-365/different-kinds-of-phone-numbers-used-for-calling-plans) <br/><br/>[获取新的用户电话号码申请表](/SkypeForBusiness/what-are-calling-plans-in-office-365/get-new-user-phone-numbers-request-forms) <br/><br/>[为用户获取电话号码](./getting-phone-numbers-for-your-users.md) <br/><br/>[将电话号码转接到 Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) <br/><br/>[转接电话号码常见问题](/SkypeForBusiness/what-are-calling-plans-in-office-365/transferring-phone-numbers-common-questions) <br/><br/>[管理组织的电话号码](/SkypeForBusiness/what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization) |
| 4  | 配置默认会议网桥电话号码 | 您可以配置组织的默认会议网桥电话号码，该电话号码分配给已启用但没有显式分配会议网桥电话号码的用户。 默认数字应与组织的中心位置对齐。 | | [设置包含在邀请中的电话号码](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites) |
| 5  | 为会议网桥电话号码设置语言 | 为会议网桥电话号码配置主要语言和辅助语言。 <br/><br/>确认为区域会议网桥电话号码分配了相应的语言以支持你的用户。 | | [为音频会议设置自动助理语言](/SkypeForBusiness/audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing) |
| 6  | 配置会议网桥设置 | 配置会议加入体验、PIN 长度和会议进入/退出通知设置。 使这些会议网桥设置与组织的目标保持一致。 | | [更改音频会议网桥的设置](/SkypeForBusiness/audio-conferencing-in-office-365/change-the-settings-for-an-audio-conferencing-bridge) |
| 7  | 自定义会议邀请 | 作为管理员，您可以在会议邀请中包括链接到帮助或法律信息的 URL。 还可以更新徽标，向邀请添加页脚文本。 | | [自定义会议邀请](/SkypeForBusiness/set-up-skype-for-business-online/customize-meeting-invitations) |
| 8  | 配置拨号计划 | 拨号计划允许用户按其习惯拨打电话号码，例如省略本地呼叫的区号、省略国内呼叫的国家/地区代码，甚至使用短数字拨号在会议期间拨打给其他用户。 <br/><br/>服务拨号计划（默认）基于用户的Microsoft 365或Office 365位置，无法更改。 <br/><br/>如果默认服务拨号计划不能满足需求，可以在租户或用户级别配置租户拨号计划。 | | [音频会议Microsoft Teams拨号计划](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) <br/><br/>[Microsoft 365和Office 365呼叫计划拨号计划](/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans) |
| 9  | 向用户分配会议号码和 PIN | 默认情况下，会议号码根据管理员选择的默认号码分配给Teams用户。 初始用户 PIN 是基于 PIN 策略随机生成的。<br/><br/> 用户将在电子邮件中收到会议号码和 PIN。 用户可以更改其 PIN。 <br/><br/>作为管理员，你可以允许拨入用户使用不同于默认号码和本地位置的会议号码。 | | |
| 10 | 准备并执行用户验收测试 | 准备并执行用户验收测试，包括拨入和拨出方案。 | | [音频会议测试计划](./deploy-audio-conferencing-teams-landing-page.md) |
| 11 | 报告使用情况、运行状况、关键成功指标和质量 | 报告在"构想"阶段定义的使用情况、运行状况、KSIS 和质量。 | | [《操作指南》](./1-drive-value-operate-my-service.md) |

## <a name="calling-plans"></a>通话套餐

| 不支持 | 活动或任务 | 说明 | 已完成？ | 其他信息 |
|----|---------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | 确定呼叫计划功能是否可用于组织的位置 | Microsoft 提供电话系统和城市通话套餐。 <br/><br/>有关通话套餐涵盖的国家和地区的最新列表，请参阅"其他信息"列中的指南。 可以选择一个或多个国家/地区，查看"呼叫计划"和"通信信用额度"是否可用。 | | [音频会议和通话套餐的国家/地区可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) |
| 2  | 验证用户列表和启用呼叫计划的部署节奏 | 检查您是否有一个在"呼叫计划"范围内具有业务单位或Teams。 使用目标和关键结果模型，确定哪些用户将在"调用计划"范围内。 我们建议你按站点工作，以便专注于资源。<br/><br/> 作为启用计划的一部分，请确定要启用的用户， (试点、站点 1、站点 2 等时启用) 。 | | [具有通话套餐的电话系统](calling-plan-landing-page.md) |
| 3  | 获取电话号码 | 了解可用于通话套餐的订阅Teams号码。 <br/><br/>从 Microsoft 获取新电话号码，或计划用户电话号码的号码移植。 <br/><br/>如果要从 Microsoft 获取新的订阅者号码，请决定是请求地理号码还是非地理号码。 <br/><br/>**注意：** 根据服务提供商的不同，号码移植过程最多可能需要 30 天。 请务必在规划中考虑到这一点。 | | [用于通话套餐的不同类型的电话号码](/SkypeForBusiness/what-are-calling-plans-in-office-365/different-kinds-of-phone-numbers-used-for-calling-plans) <br/><br/>[获取新的用户电话号码申请表](/SkypeForBusiness/what-are-calling-plans-in-office-365/get-new-user-phone-numbers-request-forms) <br/><br/>[为用户获取电话号码](./getting-phone-numbers-for-your-users.md) <br/><br/>[将电话号码转接到 Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) <br/><br/>[转接电话号码常见问题](/SkypeForBusiness/what-are-calling-plans-in-office-365/transferring-phone-numbers-common-questions) <br/><br/>[管理组织的电话号码](/SkypeForBusiness/what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization) |
| 4  | 配置拨号计划 | 拨号计划允许用户按其习惯拨打电话号码，例如省略本地呼叫的区号、省略国内呼叫的国家/地区代码，甚至使用短数字拨号在会议期间拨出其他用户。 <br/><br/>服务拨号计划（默认）基于用户的Microsoft 365或Office 365位置，无法更改。 <br/><br/>如果默认服务计划不能满足需求，可以在租户或用户级别配置租户拨号计划。 检查是否已针对音频会议完成此步骤。 | | [具有通话套餐的电话系统](calling-plan-landing-page.md) <br/><br/>[Microsoft 365和Office 365呼叫计划拨号计划](/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans) |
| 5  | 配置紧急位置 | 若要为语音用户分配号码，还必须为其分配紧急位置，以便使用 E.911。 <br/><br/>建议使用 PowerShell 自动创建位置服务。| | [紧急位置、地址和呼叫路由](what-are-emergency-locations-addresses-and-call-routing.md) |
| 6  | 向用户分配许可证、电话号码、租户用户拨号计划和紧急位置 | 向用户分配 E5 许可证。 如果使用 E3/E4 SKUS，电话系统向最终用户分配附加内容。 <br/><br/>分配许可证后，通过分配电话号码、拨号计划和紧急位置继续。 使用用户启用脚本轻松同时配置多个用户。 | | |
| 7  | 配置 Azure 语音邮件 | 如果用户的邮箱托管在 Exchange Online，则会自动预配其语音邮箱。 <br/><br/>但是，对于本地部署的 Exchange Server，需要确保具有支持的版本和拓扑。 按照"其他信息" **列中的步骤** 操作。 你可以为组织打开或关闭语音邮件转录。| | [适用于 Exchange Server 的 Azure PBX 语音邮件Exchange Server](https://support.microsoft.com/help/3195158/customer-issues-between-exum-and-azure-voicemail) <br/><br/>[设置云语音邮件](/SkypeForBusiness/what-is-phone-system-in-office-365/phone-system-voicemail/set-up-phone-system-voicemail) |
| 8  | 可选：配置传入和传出呼叫的来电显示 | 默认情况下，所有出站呼叫使用分配的电话号码来呼叫 (呼叫方 ID) 。 <br/><br/>可以选择更改或阻止用户的来电显示。 <br/><br/>**注意：** 紧急呼叫始终将用户的电话号码作为呼叫方 ID 发送。 | | [如何在组织中使用来电显示？](./how-can-caller-id-be-used-in-your-organization.md) <br/><br/>[为用户设置来电显示](./set-the-caller-id-for-a-user.md)|
| 9  | 可选：配置与 Skype for Business 的互操作性 | 配置互操作性策略（如果组织从 Skype for Business 迁移到 Teams）。 <br/><br/>互操作性允许Skype for Business Teams用户聊天和呼叫。 <br/><br/>现有部署和计划推出策略Teams计划。 查看互操作性选项、要求和限制，并相应地配置策略。 <br/><br/>**注意：** 这些步骤仅适用于您的组织仍在 Skype for Business Online 上托管用户。 | | [Microsoft Teams 和 Skype for Business 互操作性](./teams-and-skypeforbusiness-coexistence-and-interoperability.md) <br/><br/>[快速入门指南：在 Microsoft Teams 中配置通话套餐](./configuring-teams-calling-quickstartguide.md) |
| 10 | 准备并执行用户验收测试 | 准备并执行用户验收测试，包括拨入和拨出方案。 | | [测试计划电话系统](./cloud-voice-landing-page.md) |
| 11 | 报告使用情况、运行状况、关键成功指标和质量 | 报告在"构想"阶段定义的使用情况、运行状况、KSIS 和质量。 | | [《操作指南》](./1-drive-value-operate-my-service.md) |

## <a name="next-steps"></a>后续步骤

完成此清单后，你已成功将语音功能添加到 Teams 部署。

下一步，使用 [Voice (Playbook) ](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) 网站启用 Playbook 来帮助你在每个网站上载入用户，并帮助确保你计划和执行重要的特定于网站的活动。