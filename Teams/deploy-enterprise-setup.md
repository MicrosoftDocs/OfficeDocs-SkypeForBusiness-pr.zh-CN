---
title: 在你的 Office 365 组织中设置 Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: 在企业中设置 Teams，让用户能够使用聊天和文件共享进行协作、安排和参加大型会议，以及通过视频和语音交谈。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: e4614bc88ba65803ea5a8696af9e55a104912855
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101298"
---
# <a name="set-up-microsoft-teams-in-your-enterprise"></a>在你的 Office 365 组织中设置 Microsoft Teams

使用本文中的信息指导你在你的组织中完成 Teams 的部署。

> [!NOTE]
> 若尚未进行部署，强烈建议通过试点开始 Teams 部署。 试点将允许你和一些早期采用者在规划和推出之前熟悉 Teams 及其功能。若要详细了解如何开始进行试点，请参阅[Microsoft Teams 入门指南](get-started-with-teams-quick-start.md)。

在大范围推出 Teams 之前，请参阅[确保你已准备就绪](get-started-with-teams-quick-start.md#make-sure-youre-ready)中的项目确保组织已做好准备。

## <a name="plan-your-deployment"></a>规划部署

开始部署 Teams 之前，请确保已完成规划过程。 您的规划过程应包括：

- 了解 Teams 体系结构
- 查看和了解 Teams 工作负荷及其如何使用 Microsoft 365
- 计算网络要求并确保网络和 Internet 连接具有支持实时通信等关键要求所需的硬件和容量
- 了解存储在 Teams 和其他 Microsoft 365 服务中信息的法规和合规性要求
- 创建采用计划以帮助用户了解使用 Teams 的好处

强烈建议使用 [Teams 顾问](https://admin.teams.microsoft.com/teams-deployment) 帮助进行部署。 有关 Teams 顾问工作方式的详细信息，请参阅 [使用 Teams 顾问来帮助你推出 Microsoft Teams](use-advisor-teams-roll-out.md)。

> [!TIP]
> 请参阅如何使用 Teams 顾问来帮助你规划团队部署，方法可以是完成 [Microsoft Learn 上的 Teams 顾问](/learn/modules/m365-teams-rollout-using-advisor/) 模块。

有关规划 Teams 的信息，请参阅 [Teams 企业部署概述](deploy-enterprise-overview.md)。

## <a name="workloads"></a>工作负载

自定义 Teams 的方法很多。 以下部分将展示如何设置每个 Teams 工作负载： **聊天、团队和频道**; **会议和会议**;和 **电话**。 设置各工作负载的顺序可自行决定。 建议首先设置聊天、团队和频道工作负载，但可先使用会议和会议，甚至是电话系统。

#### <a name="chat-teams-and-channels"></a>[聊天、团队和渠道](#tab/ChatTeamsChannels)

聊天、团队和频道是 Teams 的基础。 **聊天** 允许一个或多个用户相互讨论、共享文件及私下会面。 **团队** 可对组织中的所有人员可见，或仅对团队成员可见。其允许相关人员在任何任务或场合，无论是长期运行的项目还是计划生日聚会中团结协作。 **团队** 的频道可以细分主题、项目、部门或其他对团队有意义的内容。 有关聊天、团队和频道的详细信息，请参阅[团队和频道概述](teams-channels-overview.md)。

> [!TIP]
> 完成 Microsoft Learn 中的 [管理 Microsoft Teams](/learn/modules/m365-teams-collab-manage-teams/) 模块，了解如何管理团队角色、访问权限和消息传递策略。

### <a name="administration-and-team-ownership"></a>管理和团队所有权

| 决定 | 说明 |
|--|--|
| 谁应该成为 Teams 管理员？ | 管理员角色可帮助向希望管理 Teams 的人员授予特定权限。 在小型企业中，同一人员可能负责 Teams 的方方面面，因此，这些额外角色可能没有必要。 之后，你始终可添加或删除管理员。<p>[使用 Microsoft Teams 管理员角色管理 Teams](using-admin-roles.md) |
| 谁应成为团队所有者和成员？ | 团队所有者负责管控能够访问团队及其频道的人员。 他们可以决定团队或频道是（对组织）公开还是私密，也可以制定是否应审核频道等策略。 成员可访问团队及其频道（除非频道设为私密，且他们不是该频道成员），也可被指定为审核员。<p>[在 Microsoft Teams 中分配团队所有者和成员](assign-roles-permissions.md) |

### <a name="default-settings-and-lifecycle-policies"></a>默认设置和生命周期策略

| 决定 | 说明 |
|--|--|
| 应该应用哪些邮件策略？ | 邮件策略控制哪些聊天和频道消息功能（例如，谁可以使用聊天、哪些人可以编辑和删除已发送的邮件等）对 Teams 中用户可用。 Teams 具有适用于所有人的全球策略。 默认情况下，全局策略的所有功能 **位于** 启用状态。<p>如果希望对所有人应用相同的策略，只需对此全局策略进行更改（例如，在对话中关闭 Meme 支持）。<p>如果希望为不同人员组使用不同的策略（例如，一个策略针对办公室工作人员，而另一个策略针对工厂员工），可以创建和分配策略。 将策略分配给用户时，全局策略不再适用。<p>[在 Teams 中管理消息传递策略](messaging-policies-in-teams.md) |
| 应应用哪些团队设置？ | Teams 设置允许你针对诸如电子邮件集成、云存储选项、组织选项卡、会议室设备设置和搜索范围等功能设置团队。 更改这些设置时，所做更改将应用于组织中的所有团队。 <p>[Teams 设置](enable-features-office-365.md#teams-settings)  |

### <a name="external-and-guest-access"></a>外部和来宾访问

| 决定 | 说明 |
|--|--|
| 应该启用外部访问吗？ | 外部访问允许其他组织中任何人与组织内部人员交谈。 当与另一个组织（如供应商）保持密切关系，并且希望任一组织内的其他人员能够轻松地相互聊天、召开会议等时，此功能非常有用。 <p>外部访问不同于来宾访问。 通过外部访问，组织内部的每一位成员都有权访问与组织内部人员进行交互。 来宾访问邀请特定人员进行访问，与组织内部人员进行交互。<p>默认情况下，外部访问 **关闭**。<p>[在 Microsoft Teams 中管理外部访问](manage-external-access.md)  |
| 应该启用来宾访问吗？ |来宾访问允许组织内部人员邀请外部人员访问团队和频道。 来宾访问通常用于与组织外部人员进行协作，他们一般和你无正式关系。 例如，你可邀请项目规划员临时负责项目。<p>来宾访问不同于外部访问。 来宾访问邀请特定人员进行访问，与组织内部人员进行交互。 通过外部访问，组织内部的每一位成员都有权访问与组织内部人员进行交互。 <p>默认情况下，来宾访问 **关闭**。 <p>[开启或关闭对 Microsoft Teams 的来宾访问](set-up-guests.md)。  |

#### <a name="meetings-and-audio-conferencing"></a>[会议和音频会议](#tab/MeetingsAudioConferencing)

会话和电话会议允许组织内部人员相互会面，或与组织外部人员会面。 任何拥有 Teams 或 Skype for Business 客户端的人员受邀后即可加入 **会议**。 参与者可通过设备的麦克风、照相机和屏幕，无需手机便可加入对话。 参与者可使用电脑或移动设备彼此沟通、发起语音呼叫及共享视频和应用。

**音频会议** 允许参与者拨打会议电话号码并输入会议 ID 后，便可通过常规电话加入会议。 当参与者的 Internet 连接差、会议为仅语音会议或某些其他情况不允许他们通过 Teams 客户端加入会议时，音频会议便非常有用。

> [!TIP]
> 完成 Microsoft Learn 中的[使用 Microsoft Teams 管理会议、电话会议和事件](/learn/modules/m365-teams-collab-manage-meetings)模块，进一步熟悉相关内容。

### <a name="meetings"></a>会议

| 决定 | 说明 |
|--|--|
| 应应用组织范围的会议设置| 会议策略控制哪些会议功能可供会议组织者和参与者使用。 可以控制匿名参与者是否可以加入会议、自定义会议邀请、控制处理实时媒体的方式等。 对这些设置进行更改时，这些设置将应用于组织内的所有会议。 <p>[在 Microsoft Teams 中管理会议设置](meeting-settings-in-teams.md)|
| 应该应用哪些会议策略？ | 会议策略Meeting policies用于控制组织中用户安排的会议的与会者可用的功能。 你可以控制用户是否可以安排私人会议、启用"现在召开会议"选项、允许录制会议等。 Teams 具有适用于所有人的全球策略。<p> 如果希望对所有人应用相同的策略，只需对此全局策略进行更改（例如，关闭会议录制）。 <p>如果希望对不同人员组使用不同的策略（例如，一个针对办公室工作人员的策略，而另一个策略针对主管人员），可以创建和分配策略。 将策略分配给用户时，全局策略不再适用。<p> [管理 Teams 中的会议策略](meeting-policies-in-teams.md)|
| 是否想要允许会议录制和存档？| 会议组织者可在云中录制和存档会议。 可以使用会议策略打开或关闭会议录制和存档。<p> [Teams 云会议录制](cloud-recording.md) |

### <a name="audio-conferencing"></a>音频会议

| 决定 | 说明 |
|--|--|
| 是否想要设置视频和第三方解决方案之间的互操作性？| 云视频互操作性允许第三方电话会议和个人视频设备加入 Teams 会议。 如果您已经投资了视频会议和个人视频设备，就可以使用视频互操作性将这些设备与 Teams 集成。<p> [Microsoft Teams 的云视频互操作性](cloud-video-interop.md)|
| 应应用哪些组织级音频会议设置？| 音频会议设置用于控制与会者如何使用电话加入会议。 您可以设置加入会议、重置会议 ID、启用或禁用向参与者发送音频会议信息等所需的 PIN 的长度。 对音频会议设置所做的更改适用于您的组织中的每个人。<p>[在 Microsoft Teams 中管理贵组织的音频会议设置](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md) |
| 会议组织者是否需要拨出到任何目标地址？| 从音频会议呼叫组织外部的电话号码时，使用通信贷项。 需要购买足够的通信信用额度，以确保音频会议期间不会外接电话。<p>某些音频会议订阅可能包括出站呼叫。 查看订阅信息了解详细信息。<p> [设置组织的通信点数](set-up-communications-credits-for-your-organization.md)|
| 应该应用哪些出站呼叫限制？| 可使用出站呼叫控件限制组织中用户可以拨打的音频会议呼叫类型。 例如，你可以控制会议是否可以拨打国际电话号码、进行任何出站呼叫、仅拨打特定的国家/地区等。<p>[音频会议和用户 PSTN 通话的出站通话限制策略](outbound-calling-restriction-policies.md) |
| 是否想要更改 Teams 对拨号电话号码的解读方式？ | 您可以控制使用拨号计划解读电话号码的方式。 例如，你可以设置拨打哪一个号码才能到达外部电话线，控制处理电话扩展的方式，设置前缀，使拨号扩展被转换为完整的电话号码，等等。<p> [创建并管理拨号计划](create-and-manage-dial-plans.md) |
| 是否想要启用实时事件？ | 实时事件让你能够向大量观众广播视频和会议内容。 如果启用实时事件，可以设置策略以控制其使用方式。 例如，可配置 URL 参与者用于支持，配置第三方视频分发提供商（如果有）等。 Teams 具有适用于所有人的全球策略。<p>如果希望对所有人应用相同的策略，只需更改此全局策略。 <p>如果希望对不同人员组使用不同的策略（例如，一个针对办公室工作人员的策略，而另一个策略针对主管人员），可以创建和分配策略。 将策略分配给用户时，全局策略不再适用。<p> [在 Microsoft Teams 中为实时事件进行设置](teams-live-events/set-up-for-teams-live-events.md) |

#### <a name="phone-system-and-pstn-connectivity"></a>[电话系统和 PSTN 连接](#tab/PhoneSystem)

电话系统让你可以使用 Microsoft 365 提供并紧密集成到云体验中的一组功能替换现有本地电话系统。

| 决定 | 说明 |
|--|--|
| 是否希望替换本地电话系统？ | 设置电话系统、配置自动助理、呼叫计划、呼叫队列等。 <p> [在组织中设置电话系统](setting-up-your-phone-system.md)|
| 是否想要设置云语音邮件策略？| 你可以控制哪些云语音邮件功能可供用户使用，以及其操作方法。 例如，可启用或禁用整个组织的语音邮件脚本、启用或禁用特定用户的语音信箱掩码等。<p> [设置云语音邮件](set-up-phone-system-voicemail.md) |
| 是否想要启用动态紧急呼叫？| 动态紧急呼叫让你能够根据网络设置和其他元数据配置位置映射，以确定在用户发出紧急呼叫时将紧急人员发送到何处。 可以配置网络设置、将紧急地址分配给位置等。<p>[规划和配置动态紧急呼叫](configure-dynamic-emergency-calling.md) |
| 是否想要自定义呼叫方 ID 行为？ | 默认情况下，Teams 用户进行呼叫时显示的电话号码是用户的电话号码。 你可以将号码更改为公司的主号码、阻止电话号码、设置匿名号码或其他服务编号。 Teams 具有适用于所有人的全球策略。<p>如果希望对所有人应用相同的策略，只需更改此全局策略。 <p>如果希望对不同人员组使用不同的策略（例如，一个针对办公室工作人员的策略，而另一个策略针对主管人员），可以创建和分配策略。 将策略分配给用户时，全局策略不再适用。<p> [在 Microsoft Teams 中管理呼叫方 ID 策略](caller-id-policies.md) |

---

## <a name="security"></a>安全性

Teams 的设计和开发符合 Microsoft 可信任计算安全开发生命周期 (SDL) 的要求（见 [Microsoft 安全开发生命周期 (SDL)](https://www.microsoft.com/sdl/default.aspx)）。 为符合组织要求，Teams 将行业标准安全技术作为体系结构的基础部分，包括：

- 设计威胁模型，然后针对这些功能进行测试
- 将与安全性相关的改进纳入编码过程和做法
- 在代码签入产品之前，创建内部版本工具以检测缓冲过度和其他潜在安全威胁

尽管团队遵循"设计上可信"的方法，但是不可能设计来抵御所有未知安全威胁。 因此，了解 Teams 如何与其他系统运行并交互非常重要。 了解 IP 地址欺骗、拒绝服务攻击、男士中间攻击等常见威胁如何工作也很重要，以便您可以设计网络和团队配置以减少发生这些攻击的可能性。

要了解 Teams 如何将安全基础融入到其设计中，并阅读有关常见威胁 [阅读内容，请参阅  和 Microsoft Teams](teams-security-guide.md)。

## <a name="compliance"></a>合规性

Teams 和 Microsoft 365 提供了许多工具，可帮助你符合公司及其用户所在的法规要求。 请参阅下列文章，了解如何在 Teams 中配置每个合规性功能：

| 功能 | 说明|
|-|-|
| [信息屏障](information-barriers-in-teams.md)| 防止个人或组相互通信或在用户选取器中查找。|
| [保留策略](retention-policies.md)| 通过设置，可以控制 Teams 中数据的保留时间，或者数据是否必须在特定时间后删除。|
| [通信合规性](communication-compliance.md)| 通过识别并针对攻击性、攻击性、专业性以及宣传语言采取行动，帮助降低通信风险;和 Gory 图像;以及共享敏感信息。 |
| [呼叫和会议基于策略的录制](teams-recording-policy.md)| 允许控制何时或是否在何时自动存储和存储呼叫和会议，供以后处理、保留或分析。|
| [敏感度标签](sensitivity-labels.md)| 通过创建实施所选隐私选项的标签，帮助保护和控制对敏感信息的访问。|
| [数据丢失防护](/microsoft-365/compliance/dlp-microsoft-teams?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json&view=o365-worldwide)| 让你创建规则来确定如何处理某些信息，如社会保险号码、信用卡号等。 可阻止发送特定信息、阻止其离开组织等。|
| [电子数据展示](eDiscovery-investigation.md)| 当您的组织在法律诉讼中收到发现要求时，帮助您搜索和检索您组织的内容。 |
| [法定保留](legal-hold.md)| 帮助您在法律诉讼过程中需要时保留您组织的信息，即使用户将其删除，在电子数据展示调查期间也可以发现这些信息。 |
| [内容搜索](content-search.md)| 提供查询查询 Exchange、SharePoint Online 和 OneDrive for Business 的 Teams 信息的方法。|
| [Auditing](audit-log-events.md)| 让你能够查看有关指定操作的信息，包括执行该操作的人、执行的操作时间、使用的 IP 地址等。 操作包括创建或删除团队、创建频道、在 Teams 中更改设置等。|
| [客户密钥](/microsoft-365/compliance/customer-key-tenant-level?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json&view=o365-worldwide)| 让你能够使用你提供的加密密钥创建数据加密策略。|

## <a name="clients"></a>客户端

在准备好允许用户开始使用 Teams 后，他们便可在 Windows、Mac、Linux PC 或 Android、iOS 设备上安装 Teams 客户端。 用户可直接从<https://teams.microsoft.com/downloads>下载 Teams 客户端。

请确保所有使用 Teams 的人员拥有 Teams 许可证。 有关分配 Teams 许可证的详细信息，请参阅[管理 Teams 用户访问权限](user-access.md#using-the-microsoft-365-admin-center)。

> [!TIP]
> 完成 Microsoft Learn 中的[部署 Microsoft Teams 客户端](/learn/modules/m365-teams-collab-deploy-clients/)模块，获得相关部署计划建议。

若组织通过 Microsoft Endpoint Configuration Manager、组策略或第三方分配机制将软件部署到用户计算机，请参阅[使用 Microsoft Endpoint Configuration Manager 安装 Microsoft Teams](msi-deployment.md)。

若需部署 Teams 客户端的详细信息，请参阅[获取 Microsoft Teams 客户端](get-clients.md)。

## <a name="training"></a>培训

若要了解如何培训用户和管理员使用 Teams，请参阅 [Teams 培训](training-microsoft-teams-landing-page.md)。