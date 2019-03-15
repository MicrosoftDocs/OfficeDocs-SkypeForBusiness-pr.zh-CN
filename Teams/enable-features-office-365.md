---
title: 在 Office 365 组织中管理 Microsoft Teams 功能
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 10/29/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ritikag
search.appverid: MET150
description: 了解如何在 Office 365 组织中打开或关闭 Microsoft Teams 应用，包括选项卡、连接器、聊天机器人或这三者的任意组合。
localization_priority: Priority
ms.custom:
- NewAdminCenter_Update
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a7712caa826804d26fd2e3527183128ce78520c3
ms.sourcegitcommit: 3014331fff89a0842c4db0b9adf0ef32f9728ade
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2019
ms.locfileid: "30460233"
---
# <a name="manage-microsoft-teams-features-in-your-office-365-organization"></a>在 Office 365 组织中管理 Microsoft Teams 功能

所有 Teams 设置将很快迁移到新的 Microsoft Teams 管理中心。在 Microsoft 365 管理中心进行管理的唯一 Teams 功能是“应用”。 

除非另有说明，否则选项的默认值为“**开启**”。

## <a name="tenant-wide-settings"></a>租户范围的设置 

你可以在 Microsoft 365 管理中心的“**租户范围的设置**”中关闭或打开 Teams 的应用功能。 

要编辑 Teams 的**租户范围的设置**，请访问 Microsoft 365 管理中心，然后选择“**设置**” > “**服务和外接程序**” > “**Microsoft Teams**”。如果你已使用 Office 365 管理员身份登录，单击此链接应该能转到相应位置： 

https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns  

### <a name="apps"></a>应用

Apps are tabs, connectors, bots, or any combination of these three, provided by Teams (first-party apps, also known as default apps) or by a third-party (also known as external apps). Under **Apps**, you can enable and disable default apps and configure settings to control external apps.  

#### <a name="default-apps"></a>默认应用

These apps, such as Planner, Praise, and Weather, are provided by Teams. To turn on an app, select the check box for that app. To turn off an app, clear the check box. 

![“默认应用”部分屏幕截图。](media/teams-manage-features-in-office365-image1.png "“默认应用”部分屏幕截图")

#### <a name="external-apps"></a>外部应用

These apps are provided by third parties. You can configure the following settings for external apps.

![“外部应用”部分屏幕截图。](media/teams-manage-features-in-office365-image2.png "“外部应用”部分屏幕截图，显示了你可以打开和关闭的设置")

- **在 Microsoft Teams 中允许外部应用**：打开此设置后，用户可以添加贵组织可用的外部应用。 

- **Allow sideloading of external apps**: If you want to turn on some external apps and turn off others , turn off this setting, and then in the list of external apps, turn off the apps that you don't want users to access. When this setting is turned on, team owners and members who are granted permission can sideload apps to Teams. 

- **Enable new external apps by default**: When this setting is turned on, users can activate new apps as soon as they're added to the Teams app catalog. Turn off this setting if you want to control new apps. Of course, if you turn it off, you have to remember to review new apps periodically so your organization doesn't miss out on new apps. 

要了解详细信息，请参阅 [Teams 中适用于应用的管理员设置](admin-settings.md)。 

## <a name="teams-org-wide-settings"></a>Teams 组织范围的设置

你可以在 Microsoft Teams 管理中心中控制组织范围内的用户设置。若要编辑组织范围内的设置，请转到 Microsoft Teams 管理中心，然后选择“**组织范围的设置**”。你可以配置以下设置。

### <a name="external-access"></a>外部访问

利用**外部访问**功能，你的 Teams 和 Skype for Business 用户可以与贵组织外部的用户通信。要配置外部访问，请访问[让你的 Teams 用户与其他 Teams 组织中的用户聊天和通信](let-your-teams-users-communicate-with-other-people.md)。

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

#### <a name="search"></a>搜索

Microsoft Teams 范围目录搜索使用 Exchange 通讯簿策略 (APB) 允许组织创建虚拟边界，用于控制用户查找其组织中的其他用户以及与这些用户通信的方式。在某些情况下你可能想要使用范围目录搜索，例如：

- 贵组织的租户中有多家你要保持独立的公司。 
- 贵学校要限制教职员工与学生之间的聊天。 

**启用**此设置将启用范围目录搜索。

### <a name="teams-upgrade"></a>Teams 升级

你可以使用这些设置来配置你的用户从 Skype for Business 到 Microsoft Teams 的升级方式。 

#### <a name="coexistence-mode"></a>共存模式
你可以指定共存模式：“**仅 Teams**”、“**群岛**”（Teams 和 Skype for Business 将共存）或“**仅 Skype for Business**”。你选择的共存模式将决定传入呼叫和聊天的路由方式，以及用户用于启动聊天和通话或安排会议的应用。有关共存模式的详细信息，请访问[了解 Microsoft Teams 和 Skype for Business 的共存和互操作性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)。

#### <a name="app-preferences"></a>应用首选项

你可以在此处选择用户加入 Skype for Business 会议时使用的应用（Skype for Business 或 [Skype Meetings 应用](https://support.office.com/zh-CN/article/What-is-Skype-Meetings-App-Skype-for-Business-Web-App-1FF3D412-718A-4982-8FF2-A4992608CDB5)）。此设置与共存模式设置无关。

## <a name="how-can-i-tell-which-features-are-available"></a>如何了解提供了哪些功能？

有关 Teams 新功能的信息，请参阅 [Microsoft 365 路线图](https://www.microsoft.com/en-us/microsoft-365/roadmap?rtc=1&filters=Microsoft%20Teams)。有关新功能和即将推出的功能的详细信息，请参阅 Teams [新增功能](https://support.office.com/en-us/article/what-s-new-in-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de?ui=en-US&rs=en-US&ad=US)页面和适用于 Teams 的[技术社区 Microsoft Teams 博客](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/What-s-new-in-Teams-Microsoft-Ignite-Edition/ba-p/252531)。 

## <a name="more-information"></a>更多信息

有关可以执行管理员功能的角色的信息，请参阅[使用 Microsoft Teams 管理员角色管理 Teams](using-admin-roles.md)。
