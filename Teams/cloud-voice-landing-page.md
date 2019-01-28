---
title: 在 Microsoft 团队中的云语音
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: crowe
search.appverid: MET150
description: 部署团队中的云语音登陆页面
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5f81c9a2c158781303e0d0db67448ae19964cb8d
ms.sourcegitcommit: 3a0b90af8eb3c10579b9eea7837c60a19a577881
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2019
ms.locfileid: "29595362"
---
# <a name="cloud-voice-in-microsoft-teams"></a>在 Microsoft 团队中的云语音

您已完成[开始](get-started-with-teams-quick-start.md)。 您已推出团队[聊天、 工作组、 通道和 & 应用程序](deploy-chat-teams-channels-microsoft-teams-landing-page.md)与您的组织内。 也许您已经部署了[会议 & 会议](deploy-meetings-microsoft-teams-landing-page.md)。 现在您已准备好添加云为您的用户的语音功能。 

云语音提供专用交换机 (PBX) 功能，并连接到公共公用电话交换网 (PSTN) 的选项。

本文帮助您确定是否需要更改任何默认云语音设置，根据您的组织配置文件和业务要求，则它引导您完成每次更改。 我们已拆分成两个组，从开始进行[要更容易进行的更改](#core-deployment-decisions)的核心集的设置。 第二个组包括您可能想要配置，请根据您的组织需要的[其他设置](#additional-deployment-decisions)。

我们建议所有组织的核心决策通过工作，然后，如果您的组织有其他要求，请查看以下材料。



## <a name="learn-more-about-cloud-voice"></a>了解有关云语音

以下文章提供有关部署和使用团队中的云语音功能的详细信息：

- [Office 365 中的电话系统](what-is-phone-system-in-office-365.md)
- [调用计划的电话系统](calling-plan-landing-page.md)
- [电话系统直接路由](direct-routing-landing-page.md)
- [云语音部署](cloud-voice-deployment.md)
- [Microsoft 电话服务解决方案](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/msft-telephony-solutions)
- 观看下面的会话，若要了解有关电话系统的详细信息：[简介中的 Microsoft 团队的电话系统](https://aka.ms/teams-phone-system)


## <a name="core-deployment-decisions"></a>核心部署决策

这些是大多数组织要更改 （如果组织不工作的团队默认设置） 的设置。

## <a name="phone-system-office-365"></a>电话系统 (Office 365)

电话系统是 Microsoft 的技术来启用呼叫控制和 Office 365 云中的专用交换机 (PBX) 功能。 电话系统允许您直接从 Office 365 中发送和紧密集成到公司的云生产力体验的功能的一组替换现有专用交换机 (PBX) 系统的信息。


|问自己|操作 |
|:------------|:-------|
|哪些用户位置或办公室中我将实现电话系统？ |有关电话系统的详细信息，请参阅[什么是 Office 365 中的电话系统](what-is-phone-system-in-office-365.md)。</li></ul>|
|||

## <a name="connection-to-the-public-switched-telephone-network-pstn"></a>连接到公共公用电话交换网 (PSTN)

若要将电话系统连接到公共公用电话交换网 (PSTN)，以便用户可以在世界各地发出电话呼叫，您可以根据业务需要的选项。  问自己以下：


|问自己|操作 |
| :------------|:-------|
| 是否要用作 Microsoft 调用规划我的电话运营商？ | 有关详细信息，请参阅[电话系统与调用计划](calling-plan-landing-page.md)。|
| 是否需要使用我自己电话运营商？ | 有关详细信息，请参阅[直接路由的电话系统](direct-routing-landing-page.md)。
|||


## <a name="additional-deployment-decisions"></a>其他部署决策

您可能想要更改设置以下内容，根据组织的需求和配置：

- 语音邮件
- 呼叫标识
- 从 Microsoft 的电话号码
- 拨号计划
- 呼叫队列
- 自动助理

### <a name="voicemail"></a>语音邮件

电话系统的语音邮件，由 Azure 语音邮件服务，支持语音邮件存款仅 Exchange 邮箱和不支持第三方电子邮件系统。 电话系统语音邮件包括语音邮件转录，默认情况下，为组织中的所有用户启用该功能。 您的业务需求可能需要您禁用语音邮件转录的特定用户或整个组织中的每个人。

|问自己|操作 |
|:------------|:-------|
| 是否要启用电话系统的语音邮件？ | 有关语音邮件设置过程，请参阅[设置电话系统的语音邮件](set-up-phone-system-voicemail.md)。
| 是否要启用的部分或所有用户的语音邮件转录？ | 若要关闭语音邮件转录，请参阅[设置您的组织中的语音邮件策略](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization)。</li></ul>|
|||

### <a name="calling-identity"></a>呼叫标识

默认情况下，所有出站呼叫的分配的电话号码用作调用 identity (呼叫者 ID)。 呼叫接收人可以快速识别呼叫方，并决定是接收还是拒绝呼叫。

|问自己|操作 |
|:------------|:-------|
|我想要屏蔽或禁用呼叫者 ID 吗？ | 若要更改或阻止呼叫者 ID，请参阅[设置用户的呼叫者 ID](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-the-caller-id-for-a-user)。 |
|||

### <a name="phone-numbers-from-microsoft"></a>从 Microsoft 的电话号码

Microsoft 有两种类型的电话号码：*订阅者*（用户） 号码，可以为其分配给您的组织中的用户，以及*服务*号码，可用作收费和免费电话服务号码，具有更高的并发呼叫容量比订户号且可分配给服务，如要进行音频会议、 自动助理或呼叫的队列。

|问自己|操作 |
| :------------|:-------|
| 哪些用户位置需要从 Microsoft 的新电话号码？ | 有关获取电话号码的信息，请参阅[管理您的组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)和[您的用户获取电话号码](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users)。 
| 是否需要哪种类型的电话号码 （订户或服务）？ | 若要帮助您选择所需的电话号码的类型，请参阅[不同种类的用于调用计划的电话号码](different-kinds-of-phone-numbers-used-for-calling-plans.md)。
如何实现到 Office 365 端口现有电话号码？|有关详细信息，请参阅[传输到 Office 365 的电话号码](transfer-phone-numbers-to-office-365.md)。
|||

### <a name="dial-plans"></a>拨号计划

Office 365 的电话系统功能中的拨号计划是翻译的规范化规则的一组呼叫授权和呼叫路由到的备用格式 （通常为 E.164 格式） 拨打的电话号码。

有关拨号计划的详细信息，请参阅[拨号计划是什么？](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)

|问自己|操作 |
|:------------|:-------|
| 我的组织是否需要自定义的拨号计划？ | 若要帮助确定您是否需要自定义的拨号计划，请参阅[Planning for 租户拨号计划](what-are-dial-plans.md#planning-for-tenant-dial-plans)|
哪些用户需要自定义的拨号计划，并且应将哪些租户拨号计划分配给每个用户？ | 若要将用户添加到在 PowerShell 中的自定义的拨号计划，请参阅[创建和管理拨号计划](create-and-manage-dial-plans.md)。 |
|||

### <a name="call-queues"></a>呼叫队列

队列包括问候语有人呼叫您的组织、 能够自动将呼叫置于保持状态，和搜索处理该呼叫的人员时的下一个可用呼叫代理的功能电话号码时所使用的电话系统呼叫者保留音乐侦听呼叫。 您可以为组织创建单个或多个呼叫的队列。 


|问自己|操作 |
|:------------|:-------|
| 我的组织是否需要调用队列？ | 有关详细信息，请参阅[创建电话系统呼叫队列](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)和[电话系统的设置](setting-up-your-phone-system.md)。 |

### <a name="auto-attendants"></a>自动助理

通过菜单系统，以查找并放置或将呼叫转接到您的组织中的部门或公司用户移动电话系统自动助理可以用于创建您的组织允许外部和内部呼叫者菜单系统。

|问自己|操作 |
|:------------|:-------|
| 我的组织是否需要自动助理？ | 有关详细信息，请参阅[什么是电话系统自动助理](what-are-phone-system-auto-attendants.md)和[设置电话系统自动助理](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)。 |

### <a name="devices"></a>设备

有关受支持设备的详细信息，请参阅以下资源：

- [在 Microsoft Teams 中管理设备](device-management.md)
- [IP 电话](https://docs.microsoft.com/en-us/skypeforbusiness/certification/devices-ip-phones?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [USB 音频和视频设备](https://docs.microsoft.com/en-us/skypeforbusiness/certification/devices-usb-devices?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [智能通信设备](https://products.office.com/en-gb/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)


