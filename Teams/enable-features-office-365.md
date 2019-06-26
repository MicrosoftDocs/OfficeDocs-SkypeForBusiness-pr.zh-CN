---
title: 为你的组织管理 Microsoft Teams 设置
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 04/18/2019
ms.topic: article
ms.service: msteams
ms.reviewer: ritikag
search.appverid: MET150
description: 了解如何为组织打开或关闭组织范围的 Microsoft Teams 设置，包括应用、外部访问权限、来宾访问权限、Teams 设置和 Teams 升级首选项。
localization_priority: Priority
ms.custom:
- NewAdminCenter_Update
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c4ec207061e53024b45b4e5a8e2ec9dfc20b13f1
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2019
ms.locfileid: "35221533"
---
# <a name="manage-microsoft-teams-settings-for-your-organization"></a>为你的组织管理 Microsoft Teams 设置

所有 Teams 设置将很快迁移到新的 Microsoft Teams 管理中心。在 Microsoft 365 管理中心进行管理的唯一 Teams 功能是“应用”。 

除非另有说明，否则选项的默认值为“**开启**”。

## <a name="tenant-wide-settings-in-the-microsoft-365-admin-center"></a>在 Microsoft 365 管理中心的租户范围设置

你可以在 Microsoft 365 管理中心的“**租户范围的设置**”中关闭或打开 Teams 的应用功能。 

要编辑 Teams 的**租户范围的设置**，请访问 Microsoft 365 管理中心，然后选择“**设置**” > “**服务和外接程序**” > “**Microsoft Teams**”。如果你已使用 Office 365 管理员身份登录，单击此链接应该能转到相应位置： 

https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns  

### <a name="apps"></a>应用

应用为选项卡、连接器、机器人或这三者的任意组合，它们由 Teams（第一方应用，亦称为默认应用）或第三方（亦称为外部应用）提供。在“应用”**** 下，可以启用和禁用默认应用，并配置用于控制外部应用的设置。若要详细了解如何在 Teams 中推出应用、机器人、连接器和选项卡，请参阅[应用、机器人和连接器](https://docs.microsoft.com/microsoftteams/deploy-apps-microsoft-teams-landing-page)。

#### <a name="default-apps"></a>默认应用

默认应用（例如 Planner、Praise 和 Weather）由 Teams 提供。 要打开某个应用，请选中该应用对应的复选框。 要关闭某个应用，请取消选中相应的复选框。

![“默认应用”部分屏幕截图。](media/teams-manage-features-in-office365-image1.png "“默认应用”部分屏幕截图")

#### <a name="external-apps"></a>外部应用

外部应用由第三方提供。 你可以为外部应用配置以下设置。

![“外部应用”部分屏幕截图。](media/teams-manage-features-in-office365-image2.png "“外部应用”部分屏幕截图，显示了你可以打开和关闭的设置")

- **在 Microsoft Teams 中允许外部应用**：打开此设置后，用户可以添加贵组织可用的外部应用。 

- **允许外部应用的旁加载**：如果你希望打开一些外部应用并关闭其他外部应用，请关闭此设置，然后在外部应用列表中，关闭你不希望用户访问的应用。 打开此设置后，团队所有者和被授予权限的成员可以向 Teams 旁加载应用。 

- **默认启用新的外部应用**：打开此设置后，用户可以在新应用添加到 Teams 应用目录后立即激活它们。 如果你希望控制新应用，请关闭此设置。 当然，如果你关闭此设置，必须记得定期查看新应用，以免贵组织错过新应用。 

## <a name="teams-org-wide-settings-in-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理中心中的 Teams 组织范围设置
你可以在 Microsoft Teams 管理中心中控制组织范围内的用户设置。若要编辑组织范围内的设置，请转到 Microsoft Teams 管理中心，然后选择“**组织范围的设置**”。你可以配置以下设置。

### <a name="external-access"></a>外部访问

利用**外部访问**功能，你的 Teams 和 Skype for Business 用户可以与你的组织或域之外的用户通信。 若要配置外部访问，请访问[让你的 Teams 用户与其他 Teams 组织中的用户聊天和通信](let-your-teams-users-communicate-with-other-people.md)。

要添加或阻止某个域：

1. 选择“**添加域**”。
2. 在“添加域”窗格中，输入域名，然后单击空格键保存名称。
3. 选择“**已允许**”或“**已阻止**”。
4. 选择“**完成**”以保存更改。 

### <a name="guest-access"></a>来宾访问权限

利用 Microsoft Teams 中的**来宾访问**功能，贵组织中的团队可以通过为贵组织外的人员授予访问团队和频道的权限来与其协作。具有企业或消费者电子邮件帐户（例如 Outlook、Gmail 或其他帐户）的任何人都能以访客身份参与 Teams，并对团队聊天、会议和文件具有完全访问权限。有关详细信息，请参阅 [Microsoft Teams 中的来宾访问](guest-access.md)。

### <a name="teams-settings"></a>Teams 设置

在 **Teams 设置**中，你可以设置电子邮件集成、云存储选项、Skype for Business 互操作性和设备。

#### <a name="email-integration"></a>电子邮件集成

开启此功能，以便用户可以使用频道电子邮件地址向 Teams 中的频道发送电子邮件。用户可以对属于其所属团队的任何频道执行此操作。用户还可以向为团队成员启用了添加连接器的团队中的任何频道发送电子邮件。要启用电子邮件集成，请确保“**允许用户向频道电子邮件地址发送电子邮件**”为“**打开**” 

#### <a name="files"></a>文件

你可以在此处打开或关闭文件共享和云文件存储选项。 

用户可以在 Teams 频道和聊天中从云存储服务上载和共享文件。Teams 中的云存储选项当前包括 ShareFile、Dropbox、Box 和 Google Drive。可打开贵组织要使用的云存储提供商对应的开关。

#### <a name="organization"></a>组织

你可以在此处打开“**组织**”选项卡，其中显示用户组织的详细组织结构图。有关详细信息，请参阅[在 Teams 中使用“组织”选项卡](https://support.office.com/article/use-the-organization-tab-in-teams-ff02568b-290a-46d6-ae7a-cda22f723894)。

#### <a name="devices"></a>设备

这些设置控制参加 Microsoft Teams 会议的 Surface Hub 设备的资源帐户行为。可使用这些设置来配置身份验证要求、要求提供内容 PIN 以及启用 Surface Hub 资源帐户以发送消息。

- **要求进行辅助形式的身份验证才能访问会议内容** - 选择用户输入内容 PIN 时拥有的访问级别。
- **设置内容 PIN** - 要求用户输入此 PIN 以防止未经授权访问文档。这可防止未经授权的用户加入即将召开的会议以及浏览附件。
- **资源帐户可以发送消息** - **启用**此设置将允许 Surface Hub 资源帐户发送消息。

#### <a name="search-by-name"></a>按名称搜索

Microsoft Teams 范围目录搜索使用 Exchange 通讯簿策略 (APB) 允许组织创建虚拟边界，用于控制用户查找其组织中的其他用户以及与这些用户通信的方式。在某些情况下你可能想要使用范围目录搜索，例如：

- 贵组织的租户中有多家你要保持独立的公司。 
- 贵学校要限制教职员工与学生之间的聊天。 

**启用**此设置将启用范围目录搜索。

### <a name="teams-upgrade"></a>Teams 升级

你可以使用这些设置来配置你的用户从 Skype for Business 到 Microsoft Teams 的升级方式。 

#### <a name="coexistence-mode"></a>共存模式
你可以指定共存模式：“**仅 Teams**”、“**并行**”（Teams 和 Skype for Business 将共存）或“**仅 Skype for Business**”。 你选择的共存模式将决定传入通话和聊天的路由方式，以及用户用于启动聊天和通话或安排会议的应用。 有关共存模式的详细信息，请访问[了解 Microsoft Teams 和 Skype for Business 的共存和互操作性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)。

#### <a name="app-preferences"></a>应用首选项

你可以在此处选择用户加入 Skype for Business 会议时使用的应用（Skype for Business 或 [Skype Meetings 应用](https://support.office.com/zh-CN/article/What-is-Skype-Meetings-App-Skype-for-Business-Web-App-1FF3D412-718A-4982-8FF2-A4992608CDB5)）。此设置与共存模式设置无关。

## <a name="how-can-i-tell-which-features-are-available"></a>如何了解提供了哪些功能？

有关 Teams 新功能的信息，请参阅 [Microsoft 365 路线图](https://www.microsoft.com/en-us/microsoft-365/roadmap?rtc=1&filters=Microsoft%20Teams)。有关新功能和即将推出的功能的详细信息，请参阅 Teams [新增功能](https://support.office.com/zh-CN/article/what-s-new-in-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de?ui=en-US&rs=en-US&ad=US)页面和适用于 Teams 的[技术社区 Microsoft Teams 博客](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/What-s-new-in-Teams-Microsoft-Ignite-Edition/ba-p/252531)。 

## <a name="more-information"></a>更多信息

有关可以执行管理员功能的角色的信息，请参阅[使用 Microsoft Teams 管理员角色管理 Teams](using-admin-roles.md)。
