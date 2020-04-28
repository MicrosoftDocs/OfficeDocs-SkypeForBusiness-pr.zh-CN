---
title: Cloud voice in Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- M365-voice
ms.reviewer: crowe
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.cloudvoice
- seo-marvel-apr2020
search.appverid: MET150
description: 了解有关云语音功能的详细信息，并了解你将面临的必要部署决策。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 20a46a82c336396ccb71587db71515b699a9056e
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905904"
---
# <a name="cloud-voice-in-microsoft-teams"></a>Cloud voice in Microsoft Teams

你已完成了[入门](get-started-with-teams-quick-start.md)。 你已在整个组织中部署了具有[聊天、团队、频道和应用](deploy-chat-teams-channels-microsoft-teams-landing-page.md)的 Teams。 也许你已将[会议部署 & 会议](deploy-meetings-microsoft-teams-landing-page.md)。 现在，你可以为你的用户添加云语音功能。 

云语音提供专用的分支交换（PBX）功能，以及用于连接到公共交换式电话网络（PSTN）的选项。

本文将帮助你确定是否需要根据组织的配置文件和业务要求更改任何默认云语音设置，然后将指导你完成每项更改。 我们已将设置拆分为两个组，从[你更可能进行](#core-deployment-decisions)的一组核心更改开始。 第二组包括你可能希望根据组织的需求配置的[其他设置](#additional-deployment-decisions)。

我们建议所有组织通过核心决策，然后，如果您的组织有其他要求，请查看以下资料。



## <a name="learn-more-about-cloud-voice"></a>了解有关云语音的详细信息

以下文章提供了有关在团队中部署和使用云语音功能的详细信息：

- [Office 365 中的电话系统](what-is-phone-system-in-office-365.md)
- [具有通话套餐的电话系统](calling-plan-landing-page.md)
- [电话系统直接路由](direct-routing-landing-page.md)
- [云语音部署](cloud-voice-deployment.md)
- [Microsoft 电话解决方案](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions)
- 观看以下会话以了解有关电话系统的详细信息： [Microsoft 团队中的电话系统简介](https://aka.ms/teams-phone-system)


## <a name="core-deployment-decisions"></a>核心部署决策

以下是大多数组织在默认设置不适合的情况下想要更改的设置。

## <a name="phone-system-office-365"></a>电话系统（Office 365）

电话系统是 Microsoft 在 Office 365 云中启用呼叫控制和专用分支交换（PBX）功能的技术。 电话系统允许你将现有的专用分支 Exchange （PBX）系统替换为直接从 Office 365 提供的一组功能，并紧密集成到公司的云生产效率体验中。


|询问你自己|操作 |
|:------------|:-------|
|哪些用户位置或办公室将实施电话系统？ |有关电话系统的详细信息，请参阅[Office 365 中的 "什么是电话系统](what-is-phone-system-in-office-365.md)"。</li></ul>|
|||

## <a name="connection-to-the-public-switched-telephone-network-pstn"></a>连接到公共交换电话网络（PSTN）

若要将电话系统连接到公共交换电话网络（PSTN），以便用户可以拨打世界各地的电话，您可以选择基于业务需求。  询问自己以下事项：


|询问你自己|操作 |
| :------------|:-------|
| 我是否希望使用 Microsoft 通话计划作为我的电话运营商？ | 有关详细信息，请参阅[带有通话计划的电话系统](calling-plan-landing-page.md)。|
| 我是否需要使用自己的电话运营商？ | 有关详细信息，请参阅[带有直接路由的电话系统](direct-routing-landing-page.md)。
|||


## <a name="additional-deployment-decisions"></a>其他部署决策

你可能需要根据组织的需求和配置来更改以下设置：

- 语音邮件
- 通话标识
- Microsoft 的电话号码
- 拨号计划
- 呼叫队列
- 自动助理

### <a name="voicemail"></a>语音邮件

云语音邮件（由 Azure 语音邮件服务提供支持）仅支持 Exchange 邮箱的语音邮件存款，不支持第三方电子邮件系统。 云语音邮件包括语音邮件脚本，默认情况下为组织中的所有用户启用。 您的业务需求可能要求您为整个组织中的特定用户或所有人禁用语音邮件脚本。

|询问你自己|操作 |
|:------------|:-------|
| 是否要启用云语音邮件？ | 有关语音邮件设置过程，请参阅[设置云语音邮件](set-up-phone-system-voicemail.md)。
| 我是否希望为部分或全部用户启用语音邮件功能？ | 要关闭语音邮件脚本，请参阅在[组织中设置语音邮件策略](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization)。</li></ul>|
|||

### <a name="calling-identity"></a>通话标识

默认情况下，所有出站呼叫均使用分配的电话号码作为呼叫标识（呼叫者 ID）。 呼叫接收人可以快速识别呼叫方，并决定是接收还是拒绝呼叫。

|询问你自己|操作 |
|:------------|:-------|
|我是否希望屏蔽或禁用来电显示？ | 若要更改或阻止呼叫方 ID，请参阅[为用户设置来电显示](set-the-caller-id-for-a-user.md)。 |
|||

### <a name="phone-numbers-from-microsoft"></a>Microsoft 的电话号码

Microsoft 有两种类型的电话*号码：可*分配给您组织中的用户的电话号码，以及*服务*号码，可用作收费电话和免费服务号码，这些号码具有比用户号码更高的并发通话能力，并且可以分配给诸如音频会议、自动助理或呼叫队列等服务。

|询问你自己|操作 |
| :------------|:-------|
| 哪些用户位置需要来自 Microsoft 的新电话号码？ | 有关获取电话号码的信息，请参阅[管理组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)和[获取用户的电话号码](getting-phone-numbers-for-your-users.md)。 
| 我需要哪种类型的电话号码（订阅者或服务）？ | 为帮助您选择所需的电话号码类型，请参阅[用于通话计划的不同类型的电话号码](different-kinds-of-phone-numbers-used-for-calling-plans.md)。
如何将现有电话号码移植到团队？|有关详细信息，请参阅[将电话号码转移给 Microsoft 团队](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)。
|||

### <a name="dial-plans"></a>拨号计划

Office 365 的电话系统功能中的拨号计划是一组规范化规则，可将拨出的电话号码转换为 "呼叫授权" 和 "呼叫路由" 的备用格式（通常为 E-164 格式）。

有关拨号计划的详细信息，请参阅[什么是拨号计划？](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)

|询问你自己|操作 |
|:------------|:-------|
| 我的组织是否需要自定义拨号计划？ | 若要帮助确定是否需要自定义拨号计划，请参阅[计划租户拨号计划](what-are-dial-plans.md#planning-for-tenant-dial-plans)|
哪些用户需要自定义拨号计划，应为每个用户分配哪种租户拨号计划？ | 若要将用户添加到 PowerShell 中的自定义拨号计划，请参阅[创建和管理拨号计划](create-and-manage-dial-plans.md)。 |
|||

### <a name="call-queues"></a>呼叫队列

云呼叫队列包括当某人拨入到您的组织的电话号码时使用的问候语、自动将呼叫置于保持状态的功能，以及搜索下一个可用的呼叫代理以处理呼叫的功能，同时呼叫正在收听音乐的用户。 您可以为您的组织创建单个或多个通话队列。 


|询问你自己|操作 |
|:------------|:-------|
| 我的组织是否需要呼叫队列？ | 有关详细信息，请参阅[创建云呼叫队列](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)和[设置电话系统](setting-up-your-phone-system.md)。 |

### <a name="auto-attendants"></a>自动助理

云自动助理可用于为你的组织创建菜单系统，该系统允许外部和内部调用方在菜单系统中移动到你的组织中的公司用户或部门查找和放置或转移呼叫。

|询问你自己|操作 |
|:------------|:-------|
| 我的组织是否需要自动助理？ | 有关详细信息，请参阅[什么是云自动](what-are-phone-system-auto-attendants.md)助理以及如何[设置云自动助理](create-a-phone-system-auto-attendant.md)。 |

### <a name="devices"></a>设备

有关支持的设备的详细信息，请参阅以下内容：

- [在 Microsoft Teams 中管理设备](device-management.md)
- [IP 电话](https://docs.microsoft.com/skypeforbusiness/certification/devices-ip-phones?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [USB 音频和视频设备](https://docs.microsoft.com/skypeforbusiness/certification/devices-usb-devices?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [适用于设备的智能通信](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)


