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
description: '了解功能、可用性以及如何为业务规划和设置 Microsoft Phone 系统。 '
ms.openlocfilehash: ccc931bd15e511903715ca328a142eb4da313dea
ms.sourcegitcommit: cbcf37f395832bed871fe709b87c6eecb1fdfd72
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2022
ms.locfileid: "68584783"
---
# <a name="heres-what-you-get-with-phone-system"></a>电话系统的功能

本文介绍电话系统功能。 有关将电话系统用作专用分支交换 (PBX) 替换以及连接到公共交换电话网络 (PSTN) 的选项的详细信息， [请参阅什么是电话系统](what-is-phone-system-in-office-365.md)。

客户端适用于电脑、Mac 和移动设备，它们提供从平板电脑和手机到电脑和桌面 IP 电话等设备上的功能。 有关详细信息，请参阅 [获取 Microsoft Teams 的客户端](get-clients.md)。

 > [!Note]
> 有关不同平台上的 Teams 电话系统的详细信息，请 [参阅 Teams 功能（按平台）](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。

若要使用电话系统功能，组织必须具有电话系统许可证。 有关许可的详细信息，请参阅 [Microsoft Teams 附加许可](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。

请注意，大多数功能要求你分配电话系统许可证并确保用户已“启用语音”。 若要分配许可证，请使用 [Set-CsPhoneNumberAssignment cmdlet](/powershell/module/teams/set-csphonenumberassignment?view=teams-ps) 并将 **EnterpriseVoiceEnabled** 参数设置为$true。 云自动助理等一些功能不需要用户启用语音。 下表中列出了异常。
  
## <a name="phone-system-features"></a>电话系统功能

电话系统提供以下功能。
  
|电话系统功能  |说明 |
|:-----|:-----|
|[云自动助理](what-are-phone-system-auto-attendants.md)  |允许你创建一个菜单系统，使外部和内部调用方能够定位和放置或转移对组织中公司用户或部门的呼叫。  <br/> 请注意， *用户无需* 启用语音即可接收来自自动助理拨号的呼叫（按号码目录搜索拨号）。 用户 *确实* 需要启用语音才能接收来自自动助理菜单选项的呼叫。 |
|[云呼叫队列](create-a-phone-system-call-queue.md) <br> |你可以配置如何为组织管理呼叫队列：例如，设置待机问候语和音乐，搜索下一个可用呼叫代理来处理呼叫，等等。  <br/> 请注意，用户 *确实* 需要启用语音才能从呼叫队列接收呼叫。|
|[保留音乐](music-on-hold.md) | 当公共交换电话网络 (PSTN) 的外部呼叫处于保留状态时，播放由服务定义的默认音乐或租户管理员上传的自定义音乐。 除了对呼叫队列进行调用外，此功能还适用于一对一的 PSTN 到 Teams 呼叫。 此功能提供与其他平台的保留通知奇偶校验。 |
|呼叫接听/拨打（按姓名和号码）   |允许用户通过触摸接听入站呼叫，并通过拨打完整电话号码或单击客户端中的名称来放置出站呼叫。   |
|[呼叫转接选项和同时响铃](https://support.office.com/article/call-forwarding-call-groups-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)  |允许用户设置转发规则，以便呼叫可以随他们一起转到任何位置，或者呼叫可以转发给同事或语音邮件。   |
|[组呼叫取件和转发到组](call-sharing-and-group-call-pickup.md)  | 允许用户与同事共享传入呼叫，以便同事可以接听用户不可用时发生的呼叫。 与其他形式的呼叫共享 (（例如呼叫转接或同时拨打) ）相比，对收件人的干扰较小，因为用户可以配置想要如何收到传入共享呼叫的通知。 |
|[传输呼叫和咨询转移](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0)  |允许用户将呼叫转接到另一个人。 或者，如果他们需要离开办公室，但想要继续聊天，他们可以将电话从电脑或 IP 电话转移到手机。  <br/> 请注意， *用户无需* 启用语音即可接收来自其他用户的传输呼叫。 |
|[转到语音邮件中呼叫*](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0)  | 允许用户在通话期间转到语音邮件。 |
|[呼叫寄存和检索](call-park-and-retrieve.md)   | 允许用户在云中的 Teams 服务中保留呼叫。 停靠呼叫时，服务会生成用于检索呼叫的唯一代码。 然后，寄存呼叫或其他人的用户可以使用该代码和受支持的应用或设备来检索呼叫。  |
|通过搜索拨打电话号码   | 允许用户使用 /call 命令和指定名称或号码从搜索框进行呼叫。  |
|[来电显示](how-can-caller-id-be-used-in-your-organization.md)   |来自公司内部的呼叫显示从公司目录提取信息的详细呼叫者 ID，其中显示图片 ID 和职务，而不仅仅是电话号码。 对于来自外部电话号码的呼叫，将显示电话服务提供商提供的呼叫者 ID。 如果外部电话号码是公司目录中的辅助号码，则会显示来自公司目录的信息。   |
|设备切换   |允许用户在连接到 Teams 的另一个 HID 设备上进行呼叫或会议;例如，从电脑扬声器切换到耳机。    |
|基于状态的呼叫路由  |控制具有状态的入站通信，使用户能够阻止所有传入通信（具体指示的通信除外）。   |
|[集成拨号盘](https://support.office.com/article/use-the-dial-pad-in-teams-27bc60b5-74c0-4e9c-808b-da4db9514d89)  | 允许用户在搜索栏和拨号盘中的任意位置按名称或号码拨号，从而加快出站呼叫的进程。  |
|联合呼叫   |允许用户安全地连接、与联合租户中的用户通信和协作。   |
|[进行和接收视频呼叫](https://support.office.com/article/abf62493-670f-4b0d-b2cf-fe03b49caf42)  | 如果为用户的帐户启用了视频呼叫，则用户可以与其联系人进行面对面的视频呼叫。 他们只需要相机、计算机的扬声器和麦克风。 如果用户的计算机没有内置音频设备，则用户也可以使用耳机。 |
|[云语音邮件](set-up-phone-system-voicemail.md)  | 当用户收到语音邮件时，它将作为电子邮件发送到 Exchange 邮箱，其中包含语音邮件作为附件。 用户可以在经过认证的桌面电话以及所有 Teams 或Skype for Business应用程序上收听其消息。 自 2017 年 3 月起添加了对语音邮件听录的支持，默认情况下为所有组织和用户启用。 <br> 请注意，用户 *不需要* 电话系统许可证，*也* 不需要启用语音才能使用云语音邮件功能。    |
|[云语音邮件用户设置](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f?ui=en-US&rs=en-US&ad=US)  | 允许用户为语音信箱问候语、呼叫应答规则和问候语（包括外出问候语）配置客户端设置。 <br> 请注意，用户 *不需要* 电话系统许可证，*也* 不需要启用语音才能使用云语音邮件功能。  |
|[辅助响铃器](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f)  | 连接到其电脑的多个扬声器设备的用户除了默认扬声器外，还可以选择将辅助设备设置为响铃。 例如，具有连接到电脑和桌面扬声器的耳机的用户可以选择在呼叫到来时同时响铃，以便他们不会错过呼叫。  |
|仅) teams (独特的[环形警报](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f) |允许用户为普通调用、转发调用和委托调用选择单独的铃声，以便他们能够区分调用的类型。   |
|[共享线路外观](shared-line-appearance.md)  | 允许用户共享其电话线，以便其他用户可以代表他们拨打和接听电话。|
|[忙碌 (](teams-calling-policy.md) 仅)   | 一种调用策略，用于配置用户在以下情况下处理传入呼叫的方式： <ul><li>在呼叫中 </li><li>在会议中</li><li>有一个呼叫处于暂停状态。 </li></ul> 调用方将收到以下响应之一： <ul><li>当被调用方在电话上时，听到忙碌的信号</li> <li>将相应地路由到用户未答复的设置。 一个选项允许调用方为已在呼叫中的用户保留语音邮件。</li></ul> 被调用方收到未接听的呼叫通知，但无法接听传入的呼叫。 默认情况下禁用此功能，但租户管理员可以启用此功能。|
|[呼叫阻止](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f?ui=en-US&rs=en-US&ad=US)  | 允许用户将 (PSTN) 电话号码添加到阻止的列表，以便阻止来自该号码的下一个呼叫给用户打电话。|
|[公用区域电话](set-up-common-area-phones.md)  | 公共区域电话通常放置在大厅或会议室等区域中，可供多人使用。 公共区域电话设置为设备而不是用户，可以自动登录到网络。|
|仅对 Teams 直接路由的[媒体旁路支持](direct-routing-plan-media-bypass.md) (仅)   | 为了提高性能，介质保留在会话边框控制器 (SBC) 和客户端之间，而不是通过电话系统发送。 |
|[未分配的数字路由](routing-calls-to-unassigned-numbers.md) | 允许将未分配号码路由给用户、自动助理、呼叫队列或自定义公告。 |

## <a name="availability-in-gcc-high-and-dod-clouds"></a>GCC High 和 DoD 云中的可用性
<a name="bkmk_setup"> </a>

GCC High 和 DoD 云中尚不提供以下功能。 

- [辅助响铃声、语音邮件和增强委派的呼叫设置](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f)
- [传输到语音邮件中呼叫](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0)
- 从搜索栏拨打电话号码
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
- [包含通话和会议的虚拟化桌面基础结构团队](teams-for-vdi.md#teams-on-vdi-with-calling-and-meetings)
