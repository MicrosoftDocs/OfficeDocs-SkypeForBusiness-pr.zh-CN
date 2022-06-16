---
title: 在 Outlook 中使用 Microsoft Teams 会议外接程序
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
ms.localizationpriority: high
search.appverid: MET150
description: Microsoft Teams 会向 Outlook 中安装外接程序，从而让用户可以在 Outlook 中安排 Teams 会议。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1b7ae345e3d3d94d93bb7ccc0eeb5f284296c2d5
ms.sourcegitcommit: 39fc58109da6b4628ffb658f2c6b94099e0ab604
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/15/2022
ms.locfileid: "66103259"
---
# <a name="use-the-teams-meeting-add-in-in-outlook"></a>在 Outlook 中使用 Teams 会议外接程序

本文详细介绍了 Outlook 中面向最终用户的 Teams 会议加载项的身份验证要求和功能。 它还展示了如何在孤岛模式下启用私人会议和调整用户的策略设置。 如果在使用加载项时遇到问题，请参阅我们[最新的故障排除指南](/MicrosoftTeams/troubleshoot/meetings/resolve-teams-meeting-add-in-issues)。

借助 Teams 会议加载项，用户可以从 Outlook 安排 Teams 会议。 此加载项适用于 Windows 版 Outlook、Mac 版 Outlook、Outlook 网页版以及 Outlook 移动版。

## <a name="teams-meeting-add-in-in-outlook-for-windows"></a>Windows 版 Outlook 中的 Teams 会议加载项

对于在其 Windows 电脑上安装了 Microsoft Teams 和任一 Office 产品（Office 2013、Office 2016、Office 2019 或 Office 2021）的用户，Teams 会议加载项将自动安装。用户将在 Outlook 日历功能区上看到 Teams 会议加载项。

![Outlook 功能区中的 Teams 会议加载项屏幕截图。](media/Teams-add-in-for-Outlook.png)

> [!NOTE]
>
>
> - **没有链接到 Teams 加载项的直接 URL**。
> - 如果你的组织同时运行 Teams 和 Skype for Business，则还有其他注意事项。 在某些情况下，Outlook 中不提供 Teams 加载项。 有关详细信息，请参阅[从 Skype for Business 升级到 Teams](upgrade-to-Teams-on-prem-tools.md)。
> - 执行 Regsvr32.exe 文件的用户权限是将 Teams 会议加载项安装在计算机上的最低要求。
> - 如果用户未看到 Teams 会议外接程序，请指示他们关闭 Outlook 和 Teams，然后按以下顺序执行操作：先重新启动 Teams 客户端，然后登录 Teams，再重新启动 Outlook 客户端。
> - 如果使用的是来自 Microsoft Store 的 Office Outlook 安装，则不支持 Teams 会议加载项。 建议需要此加载项的用户安装 Office 的即点即用版本，如[在 Windows 10 S 模式中的 Office](https://support.office.com/article/faq-office-on-windows-10-in-s-mode-717193b5-ff9f-4388-84c0-277ddf07fe3f) 一文中所述。
> - 需要安装 [Webview2](/microsoft-edge/webview2/concepts/distribution) 和 .Net 4.8，以避免 Teams 会议加载项体验降级。

## <a name="teams-meeting-add-in-in-outlook-for-mac"></a>Outlook for Mac 中的 Teams 会议加载项

如果 Outlook 运行生产内部版本 16.24.414.0 和更高版本并使用 Microsoft 365 或 Office 365 客户端订阅激活，则 Outlook for Mac 中的“Teams 会议”按钮将显示在 Outlook for Mac 功能区中。

用户单击“发送”后，会议协调（Teams 联接链接和拨入号码）将添加到会议邀请。  

## <a name="teams-meeting-add-in-in-outlook-web-app"></a>Outlook Web App 中的 Teams 会议加载项

若用户在使用新 Outlook 网页版的早期版本，Outlook Web App 中的“Teams 会议”按钮将作为新事件创建的一部分显示。 若要了解用户如何试用新 Outlook 网页版的早期版本，请参阅 [Outlook 博客](https://techcommunity.microsoft.com/t5/Outlook-Blog/Designed-to-be-fast-The-Outlook-on-the-web-user-experience-gets/ba-p/234909?utm_source=t.co&utm_medium=referral)。

![Outlook Web App 中的 Teams 会议加载项屏幕截图。](media/teams-meeting-add-in-web.png)

用户单击“发送”后，会议协调（Teams 联接链接和拨入号码）将添加到会议邀请。  

## <a name="teams-meeting-add-in-in-outlook-mobile-ios-and-android"></a>Outlook 移动版（iOS 和 Android）中的 Teams 会议加载项

“Teams 会议”按钮会在 Outlook iOS 和 Android 应用的最新版本中显示。

![Outlook 移动版中的 Teams 会议加载项屏幕截图。](media/teams-meeting-add-in-mobile.png)

用户单击“发送”后，会议协调（Teams 联接链接和拨入号码）将添加到会议邀请。  

## <a name="teams-meeting-add-in-and-findtime-for-outlook"></a>Teams 会议加载项和适用于 Outlook 的 FindTime

FindTime 是帮助公司之间在会议时间上达成一致的 Outlook 加载项。 会议受邀者提供首选时间后，FindTime 将代表用户发出会议邀请。 若在 FindTime 中选择了“联机会议”选项，FindTime 将安排 Skype for Business 或 Microsoft Teams 会议。 （FindTime 会将组织设置的内容用作默认的联机会议频道。）

> [!NOTE]  
> 若在 [Findtime 仪表板](https://findtime.microsoft.com/UserDashboard)中保存了 Skype for Business 设置，FindTime 将使用此设置，而不使用 Microsoft Teams。 若想要使用 Microsoft Teams，请在仪表板中删除 Skype for Business 设置。

有关详细信息，请参阅[使用 FindTime 安排会议](https://support.office.com/article/scheduling-meetings-with-findtime-4dc806ed-fde3-4ea7-8c5e-b5d1fddab4a6)。

## <a name="authentication-requirements"></a>身份验证要求

Teams 会议外接程序要求用户使用新式身份验证登录 Teams。 如果用户未使用此方法登录，他们仍可使用 Teams 客户端，但无法使用 Outlook 加载项安排 [Teams 在线会议](https://www.microsoft.com/microsoft-teams/online-meetings)。 可以通过以下方式之一解决此问题：

- 如果贵组织未配置新式身份验证，则应配置新式身份验证。
- 如果配置了新式身份验证，但他们在对话框中取消了，则应该指示用户使用多重身份验证重新登录。

要了解关于如何配置身份验证的详细信息，请参阅 [Microsoft Teams 中的标识模式和身份验证](identify-models-authentication.md)。

## <a name="enable-private-meetings"></a>启用私人会议

必须在 Microsoft Teams 管理中心中启用“允许安排私人会议”，才能部署该加载项。 在管理中心中，转到“会议” > “会议策略”，然后在“常规”部分中将“允许安排私人会议”切换为“启用”。

![Microsoft Teams 管理中心中的设置屏幕截图。](media/teams-add-in-for-outlook-image1.png)

Teams 客户端通过确定用户需要 32 位还是 64 位版本来安装正确的外接程序。

> [!NOTE]
> 在安装或升级 Teams 后，用户可能需要重新启动 Outlook 才能获得最新的外接程序。

## <a name="teams-upgrade-policy-and-the-teams-meeting-add-in-for-outlook"></a>Teams 升级策略和适用于 Outlook 的 Teams 会议加载项

客户可以[选择从 Skype for Business 到 Teams 的升级过程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)。 租户管理员可以使用 Teams 共存模式来定义用户的这一过程。 租户管理员可以选择允许用户并行使用 Teams 和 Skype for Business（孤岛模式）。

处于孤岛模式的用户在 Outlook 中安排会议时，这些用户通常希望能够选择是安排 Skype for Business 还是 Teams 会议。 在 Outlook 网页版、Outlook Windows 和 Outlook Mac 中，用户默认处于孤岛模式时将同时看到 Skype for Business 和 Teams 加载项。 你可以配置 Teams 会议策略设置，以控制处于孤岛模式的用户是只能使用 Teams 会议加载项，还是可同时使用 Teams 会议加载项和 Skype for Business 会议加载项。

由于初始版本中的某些限制，Outlook 移动版仅可以支持创建 Skype for Business **或** Teams 会议。请参阅下表以了解详细信息。

| Teams 管理中心中的共存模式 | Outlook 移动版中的默认会议提供商 |
| --------------------------------------|---------------------------------------------|
| 孤岛 | Skype for Business |
| 仅 Skype for Business | Skype for Business |
| Skype for Business 和 Teams 协作 | Skype for Business |
| Skype for Business 和 Teams 协作及会议 | Teams |
| 仅 Teams | Teams |

### <a name="set-whether-users-in-islands-mode-can-only-use-the-teams-meeting-add-in-or-both-the-teams-meeting-and-skype-for-business-meeting-add-ins"></a>设置处于孤岛模式的用户是只能使用 Teams 会议加载项，还是可同时使用 Teams 会议加载项和 Skype for Business 会议加载项

作为管理员，你可以配置 Teams 会议策略设置，以控制将哪个 Outlook 会议加载项用于 *处于孤岛模式的用户*。 你可以指定用户是只能使用 Team 会议加载项，还是可同时使用 Teams 会议加载项和 Skype for Business 会议加载项来在 Outlook 中安排会议。

你只能将此策略应用于处于孤岛模式且其 Teams 会议策略中的 **AllowOutlookAddIn** 参数设置为 **True** 的用户。 有关如何设置此策略的步骤，请参阅 [会议策略置 - 常规](meeting-policies-in-teams-general.md#meeting-provider-for-islands-mode)。

## <a name="other-considerations"></a>其他注意事项

Teams 会议外接程序仍是正在构建的功能，因此请注意以下事项：

- Teams 会议加载项需要负责安排会议的主要用户的 Exchange 邮箱。 确保在 Outlook 配置文件中至少配置了一个 Exchange 邮箱，并使用它和加载项来安排 Teams 会议。 有关 Exchange 要求，请参阅 [Exchange 和 Teams 如何交互](./exchange-teams-interact.md)。
- 此外接程序用于特定参与者的安排会议，而非用于频道中的会议。 频道会议必须从 Teams 中安排。
- 如果身份验证代理在用户电脑和 Teams 服务的网络路径中，此加载项将无法运行。
- 用户无法在 Outlook 中安排直播活动。 若要安排直播活动，请转到 Teams。 有关详细信息，请参阅[什么是 Microsoft Teams 直播活动？](teams-live-events/what-are-teams-live-events.md)。

详细了解 [Microsoft Teams 中的会议和通话](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8)。

## <a name="related-topics"></a>相关主题

- [Teams 疑难解答](/MicrosoftTeams/troubleshoot/teams)

- [从 Outlook 安排 Teams 会议](https://support.microsoft.com/office/schedule-a-teams-meeting-from-outlook-883cc15c-580f-441a-92ea-0992c00a9b0f)
