---
title: 电话系统的功能
ms.reviewer: ''
author: CarolynRowe
ms.author: crowe
manager: serdars
msreviewer: jastarck, roykuntz
ms.topic: conceptual
ms.assetid: bc9756d1-8a2f-42c4-98f6-afb17c29231c
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
description: '了解功能、可用性以及如何为企业规划和设置Microsoft电话系统。 '
ms.openlocfilehash: 118f2d52193583149e881bf564fb1df616bf108c
ms.sourcegitcommit: 0d97dc6616b3d633564409e39c08311af1522705
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/14/2022
ms.locfileid: "69392242"
---
# <a name="heres-what-you-get-with-phone-system"></a>电话系统的功能

本文介绍电话系统功能。 有关使用电话系统作为专用分支 Exchange (PBX) 替换的详细信息，以及连接到公用电话交换网 (PSTN) 的选项，请参阅 [什么是电话系统](what-is-phone-system-in-office-365.md)。

客户端适用于电脑、Mac 和移动设备，它们提供从平板电脑和移动电话到电脑和桌面 IP 电话等设备上的功能。 有关详细信息，请参阅[获取适用于 Microsoft Teams 的客户端](get-clients.md)。

 > [!Note]
> 有关不同平台上的 Teams 电话系统的详细信息，请参阅 [按平台显示的 Teams 功能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。

若要使用电话系统功能，你的组织必须具有电话系统许可证。 有关许可的详细信息，请参阅 [Microsoft Teams 附加许可](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。

请注意，大多数功能都需要分配电话系统许可证并确保用户“已启用语音”。 若要分配许可证，请使用 [Set-CsPhoneNumberAssignment cmdlet](/powershell/module/teams/set-csphonenumberassignment?view=teams-ps) 并将 **EnterpriseVoiceEnabled** 参数设置为 $true。 一些功能（如云自动助理）不需要用户启用语音。 下表中列出了异常。
  
## <a name="phone-system-features"></a>电话系统功能

电话系统提供以下功能。
  
|电话系统功能  |说明 |
|:-----|:-----|
|[云自动助理](what-are-phone-system-auto-attendants.md)  |允许你创建一个菜单系统，使外部和内部呼叫者能够定位呼叫并转接到组织中的公司用户或部门。  <br/> 请注意，用户 *无需* 启用语音功能，就可以按名称、按号码目录搜索从自动助理拨号接收呼叫。 用户 *确实* 需要启用语音才能从自动助理菜单选项接收呼叫。 |
|[云呼叫队列](create-a-phone-system-call-queue.md) <br> |允许配置如何为组织管理呼叫队列：例如，设置保留问候语和音乐，搜索下一个可用的呼叫代理来处理呼叫，等等。  <br/> 请注意，用户 *确实* 需要启用语音才能从呼叫队列接收呼叫。|
|[保留音乐](music-on-hold.md) | 当从公用电话交换网络 (PSTN) 的外部呼叫处于保留状态时，播放由服务定义的默认音乐或租户管理员上传的自定义音乐。 除了对呼叫队列进行的呼叫外，此功能还适用于一对一 PSTN 到 Teams 呼叫。 此功能提供与其他平台的保留通知奇偶校验。 |
|呼叫接听/拨打（按姓名和号码）   |允许用户通过触摸接听入站呼叫，并通过拨打完整的电话号码或在客户端中单击某个名称来拨打出站呼叫。   |
|[呼叫转接选项和同时响铃](https://support.office.com/article/call-forwarding-call-groups-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)  |允许用户设置转接规则，以便呼叫可以在任何位置进行，或者呼叫可以转发给同事或语音邮件。   |
|[群组呼叫应答和转接到组](call-sharing-and-group-call-pickup.md)  | 允许用户与同事共享传入呼叫，以便同事可以接听在用户不可用时发生的呼叫。 与其他形式的呼叫共享 (（如呼叫转接或同时响铃) ）相比，对收件人的干扰更少，因为用户可以配置接收传入共享呼叫的通知方式。 |
|[转接呼叫和咨询转接](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0)  |允许用户将呼叫转接到其他人。 或者，如果他们需要离开办公室，但想要继续对话，他们可以将呼叫从电脑或 IP 电话转移到手机。  <br/> 请注意，用户 *无需* 启用语音功能，就可以接收来自其他用户的转接呼叫。 |
|[转接到语音邮件中呼叫*](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0)  | 允许用户在通话期间转移到语音邮件。 |
|[呼叫寄存和检索](call-park-and-retrieve.md)   | 允许用户在云中的 Teams 服务中保留呼叫。 当某个呼叫被寄存时，该服务将生成一个唯一的代码用于呼叫检索。 然后，停下呼叫的用户或其他人可以使用该代码以及受支持的应用或设备来检索呼叫。  |
|从搜索呼叫电话号码   | 允许用户使用 /call 命令并指定名称或号码，从搜索框发出呼叫。  |
|[来电显示](how-can-caller-id-be-used-in-your-organization.md)   |来自公司内部的呼叫显示详细的来电者 ID，该 ID 从公司目录拉取信息，显示图片 ID 和职务，而不仅仅是电话号码。 对于来自外部电话号码的呼叫，将显示电话服务提供商提供的来电者 ID。 如果外部电话号码是公司目录中的辅助号码，则会显示公司目录中的信息。   |
|设备切换   |允许用户在另一台连接到 Teams 的 HID 设备上进行通话或会议;例如，从电脑扬声器切换到头戴显示设备。    |
|基于状态的呼叫路由  |通过状态控制入站通信，使用户能够阻止除明确指示的通信以外的所有传入通信。   |
|[集成拨号盘](https://support.office.com/article/use-the-dial-pad-in-teams-27bc60b5-74c0-4e9c-808b-da4db9514d89)  | 允许用户在搜索栏和拨号盘的任意位置按名称或号码拨号，从而加快进行出站呼叫的过程。  |
|联合呼叫   |允许用户安全地与联合租户中的用户进行连接、通信和协作。   |
|[拨打和接听视频通话](https://support.office.com/article/abf62493-670f-4b0d-b2cf-fe03b49caf42)  | 如果为用户的帐户启用了视频通话，则用户可以与其联系人进行面对面视频通话。 他们只需要相机、计算机的扬声器和麦克风。 如果用户的计算机没有内置音频设备，还可以使用头戴显示设备。 |
|[云语音邮件](set-up-phone-system-voicemail.md)  | 当用户收到语音邮件时，语音邮件将作为附件作为电子邮件传递到其 Exchange 邮箱。 用户可以在其认证的桌面电话以及所有 Teams 或Skype for Business应用程序上收听其消息。 自 2017 年 3 月起，已添加对语音邮件听录的支持，默认情况下为所有组织和用户启用。 <br> 请注意，用户 *不需要* 电话系统许可证，*也* 不需要启用语音来使用云语音邮件功能。    |
|[云语音邮件用户设置](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f?ui=en-US&rs=en-US&ad=US)  | 允许用户配置语音邮件问候语、呼叫应答规则和问候语（包括外出问候语）的客户端设置。 <br> 请注意，用户 *不需要* 电话系统许可证，*也* 不需要启用语音来使用云语音邮件功能。  |
|[辅助响铃](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f)  | 连接到电脑的多个扬声器设备的用户除了默认扬声器外，还可以选择将辅助设备设置为响铃。 例如，将头戴显示设备连接到电脑和桌面扬声器的用户可以选择在呼叫传入时让头戴显示设备和桌面扬声器同时响铃，以便他们不会错过呼叫。  |
|仅) Teams ([独特的环形警报](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f) |允许用户为普通呼叫、转接呼叫和委托呼叫选择单独的铃声，以便他们能够区分呼叫类型。   |
|[共享线路外观](shared-line-appearance.md)  | 允许用户共享其电话线路，以便另一个用户可以代表他们拨打和接听电话。|
|[忙碌的](teams-calling-policy.md) (Teams 仅)   | 一个呼叫策略，可用于配置在用户处于以下情况下如何处理传入呼叫： <ul><li>在通话中 </li><li>在会议中</li><li>已将呼叫置于保留状态。 </li></ul> 调用方将收到以下响应之一： <ul><li>当被调用方在电话上时听到忙碌的信号</li> <li>将相应地路由到用户的未完成设置。 一个选项允许呼叫者为已通话的用户留下语音邮件。</li></ul> 被调用方会收到未接来电通知，但无法接听来电。 此功能默认处于禁用状态，但可由租户管理员启用。|
|[呼叫阻止](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f?ui=en-US&rs=en-US&ad=US)  | 允许用户将 (PSTN) 电话号码添加到阻止列表中，以便阻止来自该号码的下一个呼叫拨打用户。|
|[公用区域电话](set-up-common-area-phones.md)  | 公用区域电话通常放置在大厅或会议室等区域，可供多人使用。 公用区域电话设置为设备而不是用户，并且可以自动登录到网络。|
|仅限 Teams 直接路由的[媒体旁路支持](direct-routing-plan-media-bypass.md) ()   | 为了获得更好的性能，在会话边界控制器 (SBC) 和客户端之间保留媒体，而不是通过电话系统发送媒体。 |
|[未分配号码路由](routing-calls-to-unassigned-numbers.md) | 允许将未分配号码路由到用户、自动助理、呼叫队列或自定义通知。 |

## <a name="availability-in-gcc-high-and-dod-clouds"></a>GCC High 和 DoD 云中的可用性
<a name="bkmk_setup"> </a>

GCC High 和 DoD 云中尚不提供以下功能。 

- [辅助响铃、语音邮件和增强委派的呼叫设置](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f)
- [转接到语音邮件中呼叫](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0)
- 从搜索栏中呼叫电话号码
- 保留音乐
- Azure AD 反向数字查找

## <a name="related-topics"></a>相关主题

- [什么是电话系统？](what-is-phone-system-in-office-365.md)
- [Cloud voice in Microsoft Teams](cloud-voice-landing-page.md)
- [设置电话系统](setting-up-your-phone-system.md)
- [哪种通话套餐适合你？](calling-plan-landing-page.md)
- [监视和管理通话质量](monitor-call-quality-qos.md)
- [Microsoft Teams 附加许可](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [电话系统定价](https://products.office.com/microsoft-teams/voice-calling#requirements)
- [用于虚拟化桌面基础结构的 Teams（包含通话和会议）](teams-for-vdi.md#teams-on-vdi-with-calling-and-meetings)
