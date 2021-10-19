---
title: 电话系统的功能
ms.reviewer: ''
author: CarolynRowe
ms.author: crowe
manager: serdars
msreviewer: jastarck, makolomi
ms.topic: conceptual
ms.assetid: bc9756d1-8a2f-42c4-98f6-afb17c29231c
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
description: '了解功能、可用性以及如何为业务计划和Microsoft 电话系统。 '
ms.openlocfilehash: 57bffbdb9d8a6b7955106d369284f716b2723a97
ms.sourcegitcommit: 5a28d052379aef67531d3023cbe4dff30dba1136
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2021
ms.locfileid: "60465812"
---
# <a name="heres-what-you-get-with-phone-system"></a>电话系统的功能

本文介绍电话系统功能。 有关将 电话系统 用作专用分支 Exchange (PBX) 更换以及用于连接到公用电话交换网 (PSTN) 的选项的详细信息，请参阅什么是[电话系统。](what-is-phone-system-in-office-365.md)

客户端适用于电脑、Mac 和移动设备，在从平板电脑和移动电话到电脑和桌面 IP 电话的设备上提供功能。 有关详细信息，请参阅获取[适用于 Microsoft Teams 的客户端](get-clients.md)。

 > [!Note]
> 有关在不同平台上Teams手机系统的详细信息，请参阅Teams[平台提供的功能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。

若要电话系统功能，组织必须具有电话系统许可证。 有关许可的详细信息，请参阅 [Microsoft Teams 附加许可](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。

请注意，大多数功能都要求你分配电话系统许可证，并确保用户"启用了语音"。 若要分配许可证，请使用 [Set-CsUser cmdlet](/powershell/module/skype/set-csuser?view=skype-ps) 并将 **enterprisevoiceenabled** 参数设置为 $true。 云自动助理等一些功能不需要用户启用语音。 下表中列出了异常。
  
## <a name="phone-system-features"></a>电话系统功能

电话系统提供以下功能。 除非另有说明，否则这些功能在 Teams 和 Skype for Business Online 中均可用。
  
|电话系统功能  |说明 |
|:-----|:-----|
|[云自动助理](what-are-phone-system-auto-attendants.md)  |允许您创建一个菜单系统，使外部和内部呼叫者能够定位和拨打或转接组织中公司用户或部门的呼叫。  <br/> 请注意， *用户无需* 启用语音来接收来自自动助理的呼叫。 |
|[云呼叫队列](create-a-phone-system-call-queue.md) <br> |允许您配置如何为组织管理呼叫队列：例如，设置问候语和保持音乐、搜索下一个可用的呼叫代理来处理呼叫，等等。  <br/> 请注意， *用户需要* 启用语音来接收来自呼叫队列的呼叫。|
|保留音乐 | 当来自公共电话交换网或 PSTN 网络的外部呼叫处于保留状态时 (服务) 默认音乐。 此功能适用于一对一 PSTN 到 Teams呼叫以及呼叫队列的呼叫。 此功能与其他平台提供保留通知奇偶校验。 此功能由管理员配置，但目前 [仅通过 PowerShell 进行配置](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)。 PSTN 呼叫的咨询转移也不支持保留音乐。 有关详细信息，请参阅保持[音乐保持状态](music-on-hold.md)。|
|呼叫接听/拨打（按姓名和号码）   |允许用户通过触摸应答入站呼叫，并拨打完整电话号码或单击客户端中的姓名进行出站呼叫。   |
|[呼叫转发选项和同时拨打](https://support.office.com/article/call-forwarding-call-groups-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)  |允许用户设置转发规则，以便呼叫可以随他们随时随地进行，或者呼叫可以转发给同事或语音邮件。   |
|[组呼叫取件和转发到组](call-sharing-and-group-call-pickup.md)  | 允许用户与同事共享传入呼叫，以便同事可以应答在用户不可用时发生的呼叫。 与其他形式的呼叫共享（例如呼叫 (或同时拨打呼叫）相比，对收件人的干扰更少) 因为用户可以配置接收传入共享呼叫的通知方式。 |
|[转接呼叫和咨询转接](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0)  |允许用户将呼叫转接给其他人。 或者，如果他们需要离开办公室，但想要继续对话，他们可以将呼叫从电脑或 IP 电话转接到移动电话。  <br/> 请注意， *用户无需* 启用语音来接收其他用户的转接呼叫。 |
|[转接到语音邮件中间呼叫*](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0)  | 允许用户在通话期间转接到语音邮件。 |
|[呼叫寄存和检索](call-park-and-retrieve.md)   | 允许用户在云中的 Teams服务中保持呼叫。 当呼叫被停时，服务会生成一个唯一的代码用于调用检索。 然后，将呼叫停放在一起的用户或其他人可以使用该代码和支持的应用或设备来检索呼叫。  |
|通过搜索呼叫电话号码   | 允许用户通过使用 /call 命令并指定名称或号码从搜索框进行呼叫。  |
|[来电显示](how-can-caller-id-be-used-in-your-organization.md)   |来自公司内部的呼叫显示详细的来电显示，该 ID 从公司目录拉取信息，显示图片 ID 和职务，而不是仅显示电话号码。 对于来自外部电话号码的呼叫，将显示电话服务提供商提供的呼叫者 ID。 如果外部电话号码是公司目录中的辅助号码，则会显示公司目录中的信息。   |
|设备切换   |允许用户在连接到其他设备的 HID 设备上播放呼叫或Teams;例如，从电脑扬声器切换到耳机。    |
|基于状态呼叫路由  |使用状态控制入站通信，使用户能够阻止除明确指示的通信之外的所有传入通信。   |
|[集成的拨号盘](https://support.office.com/article/use-the-dial-pad-in-teams-27bc60b5-74c0-4e9c-808b-da4db9514d89)  | 允许用户在搜索栏和拨号盘中的任意位置按姓名或号码进行拨号，从而加快进行出站呼叫的过程。  |
|联合呼叫   |允许用户安全地与联合租户中的用户进行连接、通信和协作。   |
|[拨打和接收视频呼叫](https://support.office.com/article/abf62493-670f-4b0d-b2cf-fe03b49caf42)  | 如果为用户的帐户启用了视频呼叫，用户可以与联系人进行面对面视频通话。 他们只需要摄像机、计算机扬声器和麦克风。 如果用户的计算机没有内置音频设备，用户也可使用耳机。 |
|[云语音邮件](set-up-phone-system-voicemail.md)  | 当用户收到语音邮件时，语音邮件作为电子邮件Exchange以附件形式发送到其邮箱。 用户可以在经过认证的桌面电话上以及所有客户端或Teams Skype for Business收听消息。 自 2017 年 3 月起已添加对语音邮件转录的支持，默认情况下，所有组织和用户都启用此功能。 <br> 请注意，*用户不需要* 电话系统许可证，也不需要启用语音才能使用云语音邮件功能。    |
|[云语音邮件用户设置](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f?ui=en-US&rs=en-US&ad=US)  | 允许用户配置语音邮件问候语、呼叫应答规则和问候语语言（包括外出问候语）的客户端设置。 <br> 请注意，*用户不需要* 电话系统许可证，也不需要启用语音才能使用云语音邮件功能。  |
|[辅助响铃](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f)  | 具有多个扬声器设备连接到其电脑的用户可以选择除了默认扬声器之外，将辅助设备设置为响铃。 例如，使用耳机连接到电脑和桌面扬声器的用户可以选择在呼叫进入时同时让耳机和桌面扬声器同时响铃，以便他们不会错过呼叫。  |
|[独特的铃声警报 (Teams](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f)只有)  |允许用户为普通呼叫、已转发呼叫和委派呼叫选择单独的铃声，以便区分呼叫类型。   |
|[共享线路外观](shared-line-appearance.md)  | 允许用户共享其电话线路，以便其他用户可以代表他们拨打和接听呼叫。|
|[在"忙碌" (Teams](teams-calling-policy.md)仅)   | 一个呼叫策略，用于配置在用户为时如何处理传入呼叫： <ul><li>在通话中 </li><li>在会议上</li><li>将呼叫置于保持状态。 </li></ul> 调用方将收到以下响应之一： <ul><li>当被呼叫者正在接听电话时，将听到忙碌信号</li> <li>将相应地路由到用户的未拒绝设置。 一个选项允许呼叫者为已进行呼叫的用户留下语音邮件。</li></ul> 被呼叫者收到未接来电通知，但无法接听来电。 默认情况下禁用此功能，但租户管理员可以启用此功能。|
|[呼叫阻止](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f?ui=en-US&rs=en-US&ad=US)  | 允许用户将 PSTN (PSTN) 添加到阻止列表中，以便阻止来自该号码的下一个呼叫拨打用户。|
|[公用区域电话](set-up-common-area-phones.md)  | 公用区域电话通常放置在大厅或会议室等区域中，供多人使用。 常用区域电话设置为设备而不是用户，可以自动登录到网络。|
|[仅支持 (](direct-routing-plan-media-bypass.md)直接Teams的媒体旁路)   | 为了提高性能，媒体保留在会话边界控制器 (SBC) 与客户端之间，而不是通过 Microsoft 电话 系统发送。 |


## <a name="availability-in-gcc-high-and-dod-clouds"></a>高云GCC DoD 云中的可用性
<a name="bkmk_setup"> </a>

以下功能尚未在高云GCC DoD 云中提供。 

- [辅助铃声、语音邮件和增强委派的呼叫设置](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f)
- [转接到语音邮件中间呼叫](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0)
- 从搜索栏呼叫电话号码
- 保留音乐
- Azure AD反向数字查找

## <a name="related-topics"></a>相关主题

- [什么是电话系统？](what-is-phone-system-in-office-365.md)
- [Cloud voice in Microsoft Teams](cloud-voice-landing-page.md)
- [设置电话系统](setting-up-your-phone-system.md)
- [哪种通话套餐适合你？](calling-plan-landing-page.md)
- [电话系统直接路由](direct-routing-landing-page.md)
- [监视和管理通话质量](monitor-call-quality-qos.md)
- [Microsoft Teams 附加许可](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [电话系统定价](https://products.office.com/microsoft-teams/voice-calling#requirements)
- [Teams呼叫和会议的虚拟化桌面基础结构](teams-for-vdi.md#teams-on-vdi-with-calling-and-meetings)
