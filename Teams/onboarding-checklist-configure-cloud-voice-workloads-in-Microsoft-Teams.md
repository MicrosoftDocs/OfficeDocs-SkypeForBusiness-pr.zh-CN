---
title: 加入清单 - 配置云语音工作负荷 - Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: rowille
description: 在 Teams 中配置云语音工作负荷时，请按照此清单中的核心、要执行的任务和活动进行操作。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.collection:
- M365-voice
ms.openlocfilehash: 45e4259003730ea53240b7481dfe63bc7c15175f
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2022
ms.locfileid: "67269887"
---
# <a name="configure-cloud-voice-workloads-in-microsoft-teams"></a>在 Microsoft Teams 中配置云语音工作负荷

## <a name="audio-conferencing"></a>音频会议

| 否 | 活动或任务 | 说明 | 已完成？ | 其他信息 |
|----|-------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | 确定音频会议是否可用于组织的位置 | Microsoft 在许多国家和城市提供音频会议。 有关所涵盖国家和地区的最新列表，请参阅 **“其他信息** ”列中的指南。 <br/><br/> 可以选择国家或地区，查看哪些 Teams 语音工作负荷可用。 | | [音频会议和通话套餐的国家/地区可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) |
| 2  | 验证用户列表以及启用音频会议的部署节奏    | 检查是否在 Teams 的音频会议范围内有业务单位或网站列表。 使用目标和关键结果模型，确定哪些用户将在范围内。 我们建议你逐站点工作，以便可以集中资源。<br/><br/> 作为启用计划的一部分，确定要启用的用户，以及何时 (试点、站点 1、站点 2 等) 。 | | [音频会议构想](./audio-conferencing-in-office-365.md)|
| 3  | 获取电话号码 | 了解可与 Teams 音频会议工作负载一起使用的服务编号。<br/><br/> 从 Microsoft 获取新电话号码，或为网站的音频会议网桥号码计划号码移植。<br/><br/> 对于音频会议，还可以转移现有的免费号码，或者从 Microsoft 获取新的免费号码。<br/><br/> 若要获取服务号码，如果列出了您的国家或地区，但Skype for Business管理中心没有服务号码，请 (<ptn@microsoft.com> 向美国) 以外的国家发送美国) 或<ptneu@microsoft.com> (的新电话号码请求。 有关详细信息，请参阅“管理组织电话号码”指南，该指南链接到“ **其他信息** ”列中。 <br/><br/>**注意：** 根据服务提供商的不同，数字移植过程最多可能需要 30 天。 请务必在规划中考虑到这一点。 | | [用于通话套餐的不同类型的电话号码](/SkypeForBusiness/what-are-calling-plans-in-office-365/different-kinds-of-phone-numbers-used-for-calling-plans) <br/><br/>[获取新的用户电话号码申请表](/SkypeForBusiness/what-are-calling-plans-in-office-365/get-new-user-phone-numbers-request-forms) <br/><br/>[为用户获取电话号码](./getting-phone-numbers-for-your-users.md) <br/><br/>[将电话号码转接到 Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) <br/><br/>[转接电话号码常见问题](/SkypeForBusiness/what-are-calling-plans-in-office-365/transferring-phone-numbers-common-questions) <br/><br/>[管理组织的电话号码](/SkypeForBusiness/what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization) |
| 4  | 配置默认会议网桥电话号码 | 可以配置组织的默认会议网桥电话号码，该电话号码分配给已启用但未显式分配会议网桥电话号码的用户。 默认数字应与组织的中心位置保持一致。 | | [设置包含在邀请中的电话号码](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites) |
| 5  | 设置会议网桥电话号码的语言 | 为会议网桥电话号码配置主要语言和辅助语言。 <br/><br/>确认为区域会议网桥电话号码分配了适当的语言来支持用户。 | | [为音频会议设置自动助理语言](/SkypeForBusiness/audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing) |
| 6  | 配置会议网桥设置 | 配置会议加入体验、PIN 长度和会议进入/退出公告设置。 将这些会议网桥设置与组织的目标保持一致。 | | [更改音频会议网桥的设置](/SkypeForBusiness/audio-conferencing-in-office-365/change-the-settings-for-an-audio-conferencing-bridge) |
| 7  | 自定义会议邀请 | 作为管理员，可以在会议邀请中包含链接到“帮助”或“法律信息”的 URL。 还可以更新徽标并将页脚文本添加到邀请。 | | [自定义会议邀请](/SkypeForBusiness/set-up-skype-for-business-online/customize-meeting-invitations) |
| 8  | 配置拨号计划 | 拨号计划允许用户按其使用的方式拨打电话号码，例如省略本地呼叫的区号、省略国内呼叫的国家/地区代码，甚至使用短数字拨号在会议期间向其他用户拨号。 <br/><br/>服务拨号计划（默认值）基于用户的 Microsoft 365 或Office 365使用位置，无法更改。 <br/><br/>如果默认服务拨号计划不能满足你的需求，则可以在租户或用户级别配置租户拨号计划。 | | [在Microsoft Teams 音频会议中拨号计划](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) <br/><br/>[Microsoft 365 和 Office 365呼叫计划拨号计划](/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans) |
| 9  | 将会议号码和 PIN 分配给用户 | 默认情况下，会根据所选 Teams 管理员的默认号码将会议号码分配给用户。 初始用户 PIN 是根据 PIN 策略随机生成的。<br/><br/> 用户将在电子邮件中收到会议号码和 PIN。 用户可以更改其 PIN。 <br/><br/>作为管理员，你可以让拨入用户使用不同于默认号码和本地到其位置的会议号码。 | | |
| 10 | 准备并执行用户接受测试 | 准备和执行用户接受测试，包括拨入和拨出方案。 | | [音频会议测试计划](./deploy-audio-conferencing-teams-landing-page.md) |
| 11 | 报告使用情况、运行状况、关键成功指标和质量 | 报告在构想阶段定义的使用情况、运行状况、KIS 和质量。 | | [《操作指南》](./1-drive-value-operate-my-service.md) |

## <a name="calling-plans"></a>通话套餐

| 否 | 活动或任务 | 说明 | 已完成？ | 其他信息 |
|----|---------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | 确定呼叫计划功能是否可用于组织的位置 | Microsoft 为电话系统提供跨许多国家和城市的通话套餐。 <br/><br/>有关通话套餐涵盖的最新国家和地区列表，请参阅 **“其他信息** ”列中的指南。 可以选择一个国家或地区，查看通话套餐和通信额度是否可用。 | | [音频会议和通话套餐的国家/地区可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) |
| 2  | 验证用户列表以及启用通话套餐的部署节奏 | 检查是否有业务单位或网站列表在 Teams 通话套餐范围内。 使用目标和关键结果模型，确定哪些用户将在通话套餐范围内。 我们建议你逐站点工作，以便可以集中资源。<br/><br/> 作为启用计划的一部分，通过 (“试点”、“站点 1”、“站点 2”等) 来确定要启用的用户。 | | [具有通话套餐的电话系统](calling-plan-landing-page.md) |
| 3  | 获取电话号码 | 了解可与 Teams 通话套餐一起使用的订阅者号码。 <br/><br/>从 Microsoft 获取新电话号码，或计划用户电话号码的号码移植。 <br/><br/>如果要从 Microsoft 获取新的订阅者号码，请决定是请求地理号码还是非地理号码。 <br/><br/>**注意：** 根据服务提供商的不同，数字移植过程最多可能需要 30 天。 请务必在规划中考虑到这一点。 | | [用于通话套餐的不同类型的电话号码](/SkypeForBusiness/what-are-calling-plans-in-office-365/different-kinds-of-phone-numbers-used-for-calling-plans) <br/><br/>[获取新的用户电话号码申请表](/SkypeForBusiness/what-are-calling-plans-in-office-365/get-new-user-phone-numbers-request-forms) <br/><br/>[为用户获取电话号码](./getting-phone-numbers-for-your-users.md) <br/><br/>[将电话号码转接到 Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) <br/><br/>[转接电话号码常见问题](/SkypeForBusiness/what-are-calling-plans-in-office-365/transferring-phone-numbers-common-questions) <br/><br/>[管理组织的电话号码](/SkypeForBusiness/what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization) |
| 4  | 配置拨号计划 | 拨号计划允许用户按其使用的方式拨打电话号码，例如省略本地呼叫的区号、省略国内呼叫的国家/地区代码，甚至使用短数字拨号在会议期间拨打其他用户。 <br/><br/>服务拨号计划（默认值）基于用户的 Microsoft 365 或Office 365使用位置，无法更改。 <br/><br/>如果默认服务计划不能满足你的需求，则可以在租户或用户级别配置租户拨号计划。 检查是否已完成音频会议的此步骤。 | | [具有通话套餐的电话系统](calling-plan-landing-page.md) <br/><br/>[Microsoft 365 和 Office 365呼叫计划拨号计划](/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans) |
| 5  | 配置紧急位置 | 若要将数字分配给语音用户，还必须为其分配紧急位置以供 E.911 使用。 <br/><br/>建议使用 PowerShell 自动创建位置服务。| | [紧急位置、地址和呼叫路由](what-are-emergency-locations-addresses-and-call-routing.md) |
| 6  | 向用户分配许可证、电话号码、租户用户拨号计划和紧急位置 | 将 E5 许可证分配给用户。 如果使用 E3/E4 SKU，则将电话系统加载项分配给最终用户。 <br/><br/>分配许可证后，继续分配电话号码、拨号计划和紧急位置。 使用用户启用脚本一次轻松配置多个用户。 | | |
| 7  | 配置 Azure Voicemail | 如果用户的邮箱托管在Exchange Online上，则会自动预配其语音邮箱。 <br/><br/>但是，对于本地部署的Exchange Server，需要确保拥有支持的版本和拓扑。 按照“ **其他信息** ”列中的步骤操作。 可以为组织打开或关闭语音邮件听录。| | [Azure PBX 语音邮件支持Exchange Server](https://support.microsoft.com/help/3195158/customer-issues-between-exum-and-azure-voicemail) <br/><br/>[设置云语音邮件](/SkypeForBusiness/what-is-phone-system-in-office-365/phone-system-voicemail/set-up-phone-system-voicemail) |
| 8  | 可选：为传入和传出呼叫配置调用方 ID | 默认情况下，所有出站呼叫都使用分配的电话号码来呼叫标识 (呼叫者 ID) 。 <br/><br/>可以选择更改或阻止用户的调用方 ID。 <br/><br/>**注意：** 紧急呼叫始终将用户的电话号码作为呼叫者 ID 发送。 | | [如何在组织中使用调用方 ID？](./how-can-caller-id-be-used-in-your-organization.md) <br/><br/>[为用户设置来电显示](./set-the-caller-id-for-a-user.md)|
| 9  | 可选：使用Skype for Business配置互操作性 | 如果组织从Skype for Business迁移到 Teams，请配置互操作性策略。 <br/><br/>互操作性使Skype for Business和 Teams 用户能够相互聊天和呼叫。 <br/><br/>你的现有部署和 Teams 的预期推出策略将影响你的计划。 查看互操作性选项、要求和限制，并相应地配置策略。 <br/><br/>**注意：** 仅当组织仍托管Skype for Business Online 上的用户时，这些步骤才适用。 | | [Microsoft Teams 和 Skype for Business 互操作性](./teams-and-skypeforbusiness-coexistence-and-interoperability.md) <br/><br/>[快速入门指南：在 Microsoft Teams 中配置通话套餐](./configuring-teams-calling-quickstartguide.md) |
| 10 | 准备并执行用户接受测试 | 准备和执行用户接受测试，包括拨入和拨出方案。 | | [电话系统的测试计划](./cloud-voice-landing-page.md) |
| 11 | 报告使用情况、运行状况、关键成功指标和质量 | 报告在构想阶段定义的使用情况、运行状况、KIS 和质量。 | | [《操作指南》](./1-drive-value-operate-my-service.md) |

## <a name="next-steps"></a>后续步骤

完成此清单后，你将成功向 Teams 部署添加语音功能。

下一步，请使用 [“语音 (Playbook 网站启用 Playbook) ](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) 来帮助你在每个网站上载入用户，并帮助确保规划和执行特定于网站的重要活动。