---
title: 在 Outlook 中使用 Microsoft Teams 会议外接程序
author: ChuckEdmonson
ms.author: chucked
manager: serdars
audience: Admin
ms.date: 06/25/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams 会向 Outlook 中安装外接程序，从而让用户可以在 Outlook 中安排 Teams 会议。
ms.custom:
- NewAdminCenter_Update
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8e2c7bae819037d0140fab1fed3625e250b8a4c1
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36241785"
---
<a name="use-the-teams-meeting-add-in-in-outlook"></a>在 Outlook 中使用 Teams 会议外接程序
=======================================

借助 Teams 会议加载项，用户可以从 Outlook 安排 Teams 会议。 此加载项适用于 Windows 版 Outlook、Mac 版 Outlook、Outlook 网页版以及 Outlook 移动版。

## <a name="teams-meeting-add-in-in-outlook-for-windows"></a>Windows 版 Outlook 中的 Teams 会议加载项

对于在其 Windows PC 上安装了 Microsoft Teams 和 Office 2010、Office 2013 或 Office 2016 的用户，会自动安装 Teams 会议加载项。 用户将在 Outlook 日历功能区看到 Teams 会议加载项。

![Outlook 功能区中的 Teams 会议加载项屏幕截图](media/Teams-add-in-for-Outlook.png)

> [!NOTE]
> - 如果用户未看到 Teams 会议外接程序，请指示他们关闭 Outlook 和 Teams，然后按以下顺序执行操作：先重新启动 Teams 客户端，然后登录 Teams，再重新启动 Outlook 客户端。
> - Windows 7 用户必须在 Windows 中安装 [Windows 通用 C 运行时更新](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows)，Teams 会议加载项才能工作。

## <a name="teams-meeting-add-in-in-outlook-for-mac"></a>Outlook for Mac 中的 Teams 会议加载项

如果 Outlook 运行生产内部版本 16.24.414.0 和更高版本，则 Outlook for Mac 中的“Teams 会议”按钮将显示在 Outlook for Mac 功能区中。

用户单击“发送”后，会议协调（Teams 联接链接和拨入号码）将添加到会议邀请。****  

## <a name="teams-meeting-add-in-in-outlook-web-app"></a>Outlook Web App 中的 Teams 会议加载项

若用户在使用新 Outlook 网页版的早期版本，Outlook Web App 中的“Teams 会议”按钮将作为新事件创建的一部分显示。 若要了解用户如何试用新 Outlook 网页版的早期版本，请参阅 [Outlook 博客](https://techcommunity.microsoft.com/t5/Outlook-Blog/Designed-to-be-fast-The-Outlook-on-the-web-user-experience-gets/ba-p/234909?utm_source=t.co&utm_medium=referral)。

![Outlook Web App 中的 Teams 会议加载项屏幕截图](media/teams-meeting-add-in-web.png)

用户单击“发送”后，会议协调（Teams 联接链接和拨入号码）将添加到会议邀请。****  

## <a name="teams-meeting-add-in-in-outlook-mobile-ios-and-android"></a>Outlook 移动版（iOS 和 Android）中的 Teams 会议加载项

“Teams 会议”按钮会在 Outlook iOS 和 Android 应用的最新版本中显示。

![Outlook 移动版中的 Teams 会议加载项屏幕截图](media/teams-meeting-add-in-mobile.png)

用户单击“发送”后，会议协调（Teams 联接链接和拨入号码）将添加到会议邀请。****  

## <a name="teams-meeting-add-in-in-and-findtime-for-outlook"></a>Teams 会议加载项和 Outlook 的 FindTime
FindTime 是帮助公司之间在会议时间上达成一致的 Outlook 加载项。 会议受邀者提供首选时间后，FindTime 将代表用户发出会议邀请。 若在 FindTime 中选择了“联机会议”选项，FindTime 将安排 Skype for Business 或 Microsoft Teams 会议。**** （FindTime 会将组织设置的内容用作默认的联机会议频道。）

> [!NOTE]  
> 若在 [Findtime 仪表板](https://findtime.microsoft.com/UserDashboard)中保存了 Skype for Business 设置，FindTime 将使用此设置，而不使用 Microsoft Teams。 若想要使用 Microsoft Teams，请在仪表板中删除 Skype for Business 设置。

有关详细信息，请参阅[使用 FindTime 安排会议](https://support.office.com/article/scheduling-meetings-with-findtime-4dc806ed-fde3-4ea7-8c5e-b5d1fddab4a6)。

## <a name="authentication-requirements"></a>身份验证要求

Teams 会议外接程序要求用户使用新式身份验证登录 Teams。 如果用户未使用此方法登录，他们仍可使用 Teams 客户端，但无法使用 Outlook 外接程序安排 Teams 在线会议。 可以通过以下方式之一解决此问题：

- 如果贵组织未配置新式身份验证，则应配置新式身份验证。
- 如果配置了新式身份验证，但他们在对话框中取消了，则应该指示用户使用多重身份验证重新登录。

要了解关于如何配置身份验证的详细信息，请参阅 [Microsoft Teams 中的标识模式和身份验证](identify-models-authentication.md)。

## <a name="enable-private-meetings"></a>启用私人会议

必须在 Microsoft Teams 管理中心中启用“允许安排私人会议”，才能部署该加载项。**** 在管理中心中，转到“会议” > “会议策略”，然后在“常规”部分中将“允许安排私人会议”切换为“启用”。****************

![Microsoft Teams 管理中心中的设置屏幕截图。](media/teams-add-in-for-outlook-image1.png)

Teams 客户端通过确定用户需要 32 位还是 64 位版本来安装正确的外接程序。

> [!NOTE]
> 在安装或升级 Teams 后，用户可能需要重新启动 Outlook 才能获得最新的外接程序。

## <a name="teams-upgrade-policy-and-the-teams-meeting-add-in-for-outlook"></a>Teams 升级策略和适用于 Outlook 的 Teams 会议加载项

客户可以[选择从 Skype for Business 到 Teams 的升级过程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)。 租户管理员可以使用 Teams 共存模式来定义用户的这一过程。 租户管理员可以选择允许用户并行使用 Teams 和 Skype for Business（孤岛模式）。 

处于孤岛模式的用户在 Outlook 中安排会议时，这些用户通常希望能够选择是安排 Skype for Business 还是 Teams 会议。 在 Outlook 网页版、Outlook Windows 和 Outlook Mac 中，用户处于孤岛模式时将同时看到 Skype for Business 和 Teams 加载项。 由于初始版本中的某些限制，Outlook 移动版仅可以支持创建 Skype for Business **或** Teams 会议。 有关详细信息，请参阅下表。

| Teams 管理中心中的共存模式 | Outlook 移动版中的默认会议提供商 |
| --------------------------------------|---------------------------------------------|
| 孤岛 | Skype for Business |
| 仅 Skype for Business | Skype for Business |
| Skype for Business 和 Teams 协作 | Skype for Business |
| Skype for Business 和 Teams 协作及会议 | Teams |
| 仅 Teams | Teams |

## <a name="other-considerations"></a>其他注意事项

Teams 会议外接程序仍是正在构建的功能，因此请注意以下事项：

- 此外接程序用于特定参与者的安排会议，而非用于频道中的会议。 频道会议必须从 Teams 中安排。
- 若身份验证代理在用户电脑和 Teams 服务的网络路径中，此加载项将无法运行。
- 用户无法在 Outlook 中安排直播活动。 若要安排直播活动，请转到 Teams。 有关详细信息，请参阅[什么是 Microsoft Teams 直播活动？](teams-live-events/what-are-teams-live-events.md)。

## <a name="troubleshooting"></a>故障排除

若无法安装 Outlook 的 Teams 会议加载项，请尝试下列故障排除步骤。

- 确保已应用所有可用的 Outlook 桌面客户端更新。
- 重启 Teams 桌面客户端。
- 注销，然后重新登录到 Teams 桌面客户端。
- 重启 Outlook 桌面客户端。 （请确保 Outlook 未运行管理员模式。）
- 确保登录的用户帐户名称不包含空格。 （这是一个已知问题，将在后续更新中修复。）
- 确保单一登录 (SSO) 已启用。

若管理员已配置 Microsoft Exchange 来[控制对 Exchange Web Server (EWS) 的访问](https://docs.microsoft.com/zh-CN/exchange/client-developer/exchange-web-services/how-to-control-access-to-ews-in-exchange)，则代理无法代表上级安排 Teams 会议。 此配置的解决方案正在开发中，未来将予以发布。 

有关如何禁用外接程序的一般指导，请参阅[在 Office 程序中查看、管理和安装外接程序](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D)。

详细了解 [Microsoft Teams 中的会议和通话](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8)。
