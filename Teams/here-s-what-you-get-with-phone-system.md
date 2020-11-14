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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: '了解功能、可用性以及如何为你的企业规划和设置 Microsoft Phone 系统。 '
ms.openlocfilehash: b3a3da0a2cfd8038b3af84352c754c9014a1ad6c
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2020
ms.locfileid: "49030398"
---
# <a name="heres-what-you-get-with-phone-system"></a>电话系统的功能

本文介绍电话系统功能。 有关将电话系统用作专用分支 Exchange 的详细信息 (PBX) 替换以及用于连接到公共交换电话网络 (PSTN) 的选项，请参阅 [什么是电话系统](what-is-phone-system-in-office-365.md)。

客户端适用于电脑、Mac 和手机，可通过平板电脑和移动电话将设备上的功能提供给电脑和桌面 IP 电话。 有关详细信息，请参阅 [获取 Microsoft 团队客户端](get-clients.md)。

 > [!Note]
> 有关不同平台上的团队电话系统的详细信息，请参阅 [团队功能按平台](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。
  
## <a name="phone-system-features"></a>电话系统功能

电话系统提供下列功能。 除非另有说明，否则功能在团队和 Skype for business Online 中均可使用。
  
|||
|:-----|:-----|
|**电话系统功能** <br/> |**说明** <br/> |
|[云自动助理](what-are-phone-system-auto-attendants.md) <br/> |允许您创建一个菜单系统，使外部和内部呼叫者能够找到并将呼叫放入或转移到组织中的公司用户或部门。  <br/> |
|[云呼叫队列](create-a-phone-system-call-queue.md) <br/> |允许你配置为你的组织管理呼叫队列的方式：例如，设置问候语和暂停的音乐、搜索下一个可用的呼叫代理以处理呼叫等。  <br/> |
|保留音乐 | 当来自公共交换电话网络 (PSTN) 的外部呼叫处于暂候状态时，播放由该服务定义的默认音乐。 除了对呼叫队列拨打电话之外，此功能适用于一对一的 PSTN 到团队通话。 此功能提供与其他平台的保持状态通知奇偶校验。 此功能可由管理员配置，但 [当前只能通过 PowerShell](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)进行配置。 在 PSTN 呼叫的咨询转移中也不支持 "保留音乐"。|
|呼叫接听/拨打（按姓名和号码）  <br/> |允许用户通过触摸接听入站呼叫，并通过拨打完整的电话号码或通过单击客户端中的名称来发出出站呼叫。  <br/> |
|[呼叫转接选项和同时拨打](https://support.office.com/article/call-forwarding-call-groups-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) <br/> |允许用户设置转发规则，以便呼叫可以与他们进行任何地方的通话，也可以将来电转发给同事或语音邮件。  <br/> |
|[分组呼叫和转发到组](call-sharing-and-group-call-pickup.md) <br/> | 允许用户与同事共享传入呼叫，以便同事可以接听用户不可用时出现的呼叫。 对收件人的中断比其他形式的呼叫共享 (更少，例如呼叫转接或同时拨打) ，因为用户可以配置他们希望如何接收传入的共享呼叫。 |
|[转接呼叫和顾问式转移](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0) <br/> |允许用户将呼叫转移给其他人。 或者，如果他们需要离开自己的 office，但想要继续对话，他们可以将呼叫从其 PC 或 IP 电话转移到手机。  <br/> |
|[转接到语音邮件中间电话](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0) <br/> | 允许用户在通话期间转移到语音邮件。 |
|[呼叫寄存和检索](call-park-and-retrieve.md)  <br/> | 允许用户在云中的团队服务中将呼叫置于保持状态。 当通话暂停时，该服务将生成一个唯一的通话检索代码。 停用呼叫或其他人的用户可以使用该代码和受支持的应用或设备来检索呼叫。 <br/> |
|从搜索呼叫电话号码  <br/> | 允许用户通过使用/call 命令并指定名称或数字来在搜索框中放置呼叫。 <br/> |
|[来电显示](how-can-caller-id-be-used-in-your-organization.md)  <br/> |从公司内部进行呼叫将显示一个详细的呼叫方 ID，该 ID 从公司目录提取信息，显示图片 ID 和作业标题，而不是只显示电话号码。 对于来自外部电话号码的呼叫，将显示电话服务提供商提供的呼叫方 ID。 如果外部电话号码是公司目录中的辅助号码，则将显示来自公司目录的信息。  <br/> |
|设备切换  <br/> |允许用户在连接到团队的另一个 HID 设备上播放呼叫或会议;例如，从 PC 扬声器切换到耳机。   <br/> |
|基于状态的呼叫路由 <br/> |控制与状态的入站通信，使用户可以阻止所有传入通信，除了特别指示的之外。  <br/> |
|[集成拨号盘](https://support.office.com/article/use-the-dial-pad-in-teams-27bc60b5-74c0-4e9c-808b-da4db9514d89) <br/> | 允许用户在搜索栏和拨号盘中的任意位置按姓名或按号码拨号，从而加快出站呼叫过程。 <br/> |
|联合呼叫  <br/> |允许用户与联盟租户中的用户安全地连接、沟通和协作。  <br/> |
|[拨打和接听视频电话](https://support.office.com/article/abf62493-670f-4b0d-b2cf-fe03b49caf42) <br/> | 如果用户的帐户可以进行视频通话，则用户可以与他们的联系人进行面对面的视频通话。 他们只需要一部摄像头、计算机的扬声器和麦克风。 如果计算机没有内置音频设备，则用户也可以使用耳机。<br/> |
|[云语音邮件](set-up-phone-system-voicemail.md) <br/> | 当用户收到语音邮件时，将以电子邮件形式将邮件作为附件发送给其 Exchange 邮箱。 用户可以通过其认证的桌面电话、所有团队或 Skype for business 应用程序收听其邮件。 对语音邮件脚本的支持已添加到2017年3月，并且默认情况下为所有组织和用户启用。   <br/> |
|[云语音邮件用户设置](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f?ui=en-US&rs=en-US&ad=US) <br/> | 允许用户为语音邮件问候语、呼叫应答规则和问候语言（包括外出问候语）配置其客户端设置。   |
|[辅助铃声](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f) <br/> | 将多个扬声器设备连接到其电脑上的用户可以选择将辅助设备设置为除默认扬声器之外的电话。 例如，已连接到电脑和桌面扬声器的耳机的用户可以选择呼叫进入时同时使用耳机和桌面扬声器铃声，以便他们不会错过来电。  |
|仅 (团队的[独特震铃通知](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f)) <br/> |允许用户为正常呼叫、已转移呼叫和已委派呼叫选择单独的铃声，以便他们可以区分呼叫类型。  <br/> |
|[共享线路外观](shared-line-appearance.md) <br/> | 允许用户共享其电话线路，以便其他用户可以代表他们进行呼叫和接听呼叫。|
|[忙 (仅](teams-calling-policy.md) 限团队)  <br/> | 一种呼叫策略，可用于配置当用户已加入通话或会议或有呼叫处于保持状态时如何处理传入呼叫。 当被呼叫方在手机上时，呼叫者将听到占线信号。 被呼叫方获取未接来电通知，但无法应答传入呼叫。 默认情况下禁用此功能，但租户管理员可以将其打开。 |
|[通话阻止](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f?ui=en-US&rs=en-US&ad=US) <br/> | 允许用户将 (PSTN) 电话号码添加到被阻止的列表，以便阻止来自该号码的下一次通话以拨打用户。|
|[常见的区域电话](set-up-common-area-phones.md) <br/> | 常用的区域电话通常放置在一个区域（如前厅浏览或会议室）中，使其可供多人使用。 常用的区域电话设置为设备，而不是用户，并且可以自动登录到网络。|
|[媒体绕过支持](direct-routing-plan-media-bypass.md) (仅限团队直接路由)  <br/> | 为了提高性能，媒体在会话边界控制器 (SBC) 和客户端（而不是通过 Microsoft Phone 系统发送）之间保持。 |


## <a name="availability-in-gcc-high-and-dod-clouds"></a>在 GCC 高和 DoD 云中的可用性
<a name="bkmk_setup"> </a>

以下功能在 GCC 高和 DoD 云中尚不可用。 
- [辅助铃声、语音邮件和增强委派的呼叫设置](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f)
- [转接到语音邮件中间电话](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0)
- 从搜索栏呼叫电话号码
- 保留音乐
- Azure AD 反向号码查找

## <a name="related-topics"></a>相关主题

- [什么是电话系统？](what-is-phone-system-in-office-365.md)
- [Cloud voice in Microsoft Teams](cloud-voice-landing-page.md)
- [设置电话系统](setting-up-your-phone-system.md)
- [哪种通话套餐适合你？](calling-plan-landing-page.md)
- [电话系统直接路由](direct-routing-landing-page.md)
- [监视和管理通话质量](monitor-call-quality-qos.md)
- [Microsoft Teams 附加许可](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)
- [电话系统定价](https://products.office.com/microsoft-teams/voice-calling#requirements)
- [具有 callings 和会议的虚拟化桌面基础结构团队](teams-for-vdi.md#teams-on-vdi-with-calling-and-meetings)

  
 
