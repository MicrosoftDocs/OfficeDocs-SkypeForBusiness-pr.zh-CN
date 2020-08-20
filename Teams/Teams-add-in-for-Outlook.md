---
title: 在 Outlook 中使用 Microsoft Teams 会议外接程序
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams 会向 Outlook 中安装外接程序，从而让用户可以在 Outlook 中安排 Teams 会议。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: dc543096965a3abc51964c5006795cf385a4cb55
ms.sourcegitcommit: 34f407a6a40317056005e3bf38ce58f792c04810
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814098"
---
<a name="use-the-teams-meeting-add-in-in-outlook"></a>在 Outlook 中使用 Teams 会议外接程序
=======================================

借助 Teams 会议加载项，用户可以从 Outlook 安排 Teams 会议。 此加载项适用于 Windows 版 Outlook、Mac 版 Outlook、Outlook 网页版以及 Outlook 移动版。

## <a name="teams-meeting-add-in-in-outlook-for-windows"></a>Windows 版 Outlook 中的 Teams 会议加载项

将为 Microsoft Teams 以及 Windows 电脑上安装了 Microsoft Teams、Office 2013、Office 2016 或 Office 2019 的用户自动安装 Teams 会议加载项。 用户将在 Outlook 日历功能区看到 Teams 会议加载项。

![Outlook 功能区中的 Teams 会议加载项屏幕截图](media/Teams-add-in-for-Outlook.png)

> [!NOTE]
> - 不 **存在直接链接** 到 Teams 外接内容的 URL。
> - 如果你的组织同时运行 Teams 和 Skype for Business，还有其他注意事项。 在某些情况下，Teams 加载项在 Outlook 中不可用。 有关详细信息[，请参阅从 Skype for Business 升级到 Teams。](https://docs.microsoft.com/microsoftteams/upgrade-to-teams-on-prem-overview#meetings)
> - 执行 Regsvr32.exe 文件的用户权限是将 Teams 会议加载项安装在计算机上的最低要求。
> - 如果用户未看到 Teams 会议外接程序，请指示他们关闭 Outlook 和 Teams，然后按以下顺序执行操作：先重新启动 Teams 客户端，然后登录 Teams，再重新启动 Outlook 客户端。
> - 如果使用的是来自 Microsoft Store 的 Office Outlook 安装，则不支持 Teams 会议加载项。 建议需要此加载项的用户安装 Office 的即点即用版本，如[在 Windows 10 S 模式中的 Office](https://support.office.com/article/faq-office-on-windows-10-in-s-mode-717193b5-ff9f-4388-84c0-277ddf07fe3f) 一文中所述。

## <a name="teams-meeting-add-in-in-outlook-for-mac"></a>Outlook for Mac 中的 Teams 会议加载项

如果 Outlook 运行生版版本 16.24.414.0 及更高版本并已使用 Microsoft 365 或 Office 365 客户端订阅激活，Outlook for Mac 功能区中的 Teams 会议按钮将显示在 Outlook for Mac 功能区中。

用户单击“发送”后，会议协调（Teams 联接链接和拨入号码）将添加到会议邀请。****  

## <a name="teams-meeting-add-in-in-outlook-web-app"></a>Outlook Web App 中的 Teams 会议加载项

若用户在使用新 Outlook 网页版的早期版本，Outlook Web App 中的“Teams 会议”按钮将作为新事件创建的一部分显示。 若要了解用户如何试用新 Outlook 网页版的早期版本，请参阅 [Outlook 博客](https://techcommunity.microsoft.com/t5/Outlook-Blog/Designed-to-be-fast-The-Outlook-on-the-web-user-experience-gets/ba-p/234909?utm_source=t.co&utm_medium=referral)。

![Outlook Web App 中的 Teams 会议加载项屏幕截图](media/teams-meeting-add-in-web.png)

用户单击“发送”后，会议协调（Teams 联接链接和拨入号码）将添加到会议邀请。****  

## <a name="teams-meeting-add-in-in-outlook-mobile-ios-and-android"></a>Outlook 移动版（iOS 和 Android）中的 Teams 会议加载项

“Teams 会议”按钮会在 Outlook iOS 和 Android 应用的最新版本中显示。

![Outlook 移动版中的 Teams 会议加载项屏幕截图](media/teams-meeting-add-in-mobile.png)

用户单击“发送”后，会议协调（Teams 联接链接和拨入号码）将添加到会议邀请。****  

## <a name="teams-meeting-add-in-and-findtime-for-outlook"></a>Teams 会议加载项和 FindTime for Outlook

FindTime 是 Outlook 的加载项，可帮助用户在公司即将参加会议时间感知。 会议受邀者提供首选时间后，FindTime 将代表用户发出会议邀请。 若在 FindTime 中选择了“联机会议”选项，FindTime 将安排 Skype for Business 或 Microsoft Teams 会议。**** （FindTime 会将组织设置的内容用作默认的联机会议频道。）

> [!NOTE]  
> 若在 [Findtime 仪表板](https://findtime.microsoft.com/UserDashboard)中保存了 Skype for Business 设置，FindTime 将使用此设置，而不使用 Microsoft Teams。 若想要使用 Microsoft Teams，请在仪表板中删除 Skype for Business 设置。

有关详细信息，请参阅"使用 [FindTime 安排会议](https://support.office.com/article/scheduling-meetings-with-findtime-4dc806ed-fde3-4ea7-8c5e-b5d1fddab4a6)"。

## <a name="authentication-requirements"></a>身份验证要求

Teams 会议外接程序要求用户使用新式身份验证登录 Teams。 如果用户未使用此方法登录，则仍然可以使用 Teams 客户端，但无法使用 Outlook 加载项安排 Teams 联机会议。 可以通过以下方式之一解决此问题：

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

处于孤岛模式的用户在 Outlook 中安排会议时，这些用户通常希望能够选择是安排 Skype for Business 还是 Teams 会议。 在 Outlook 网页版、Outlook Windows 和 Outlook Mac 中，默认情况下，用户在使用群模式时同时看到 Skype for Business 和 Teams 加载项。 你可以配置 Teams 会议策略设置来控制群值模式中的用户是否只能使用 Teams 会议加载项或同时使用 Teams 会议加载项和 Skype for Business 会议加载项。

由于初始版本中的某些限制，Outlook 移动版仅可以支持创建 Skype for Business **或** Teams 会议。 有关详细信息，请参阅下表。

| Teams 管理中心中的共存模式 | Outlook 移动版中的默认会议提供商 |
| --------------------------------------|---------------------------------------------|
| 孤岛 | Skype for Business |
| 仅 Skype for Business | Skype for Business |
| Skype for Business 和 Teams 协作 | Skype for Business |
| Skype for Business 和 Teams 协作及会议 | Teams |
| 仅 Teams | Teams |

### <a name="set-whether-users-in-islands-mode-can-only-use-the-teams-meeting-add-in-or-both-the-teams-meeting-and-skype-for-business-meeting-add-ins"></a>设置群模式中的用户是只能使用 Teams 会议加载项，还是同时使用 Teams 会议加载项和 Skype for Business 会议加载项

作为管理员，你可以配置 Teams 会议策略设置以控制针对处于群内模式的用户使用的 Outlook *会议加载项*。 你可以指定用户是否只能使用 Teams 会议加载项，还可以同时使用 Teams 会议和 Skype for Business 会议加载项来安排 Outlook 中的会议。

只能将此策略应用于处于群摸模式且在 Teams 会议策略中 **将 AllowOutlookAddIn** **参数设置为 True** 的用户。 有关如何设置此策略的步骤，请参阅 [针对群体模式的用户设置会议提供商](meeting-policies-in-teams.md#meeting-policy-settings---meeting-provider-for-islands-mode)。

## <a name="other-considerations"></a>其他注意事项

Teams 会议外接程序仍是正在构建的功能，因此请注意以下事项：

- Teams 会议加载项需要 Outlook 邮箱用于主要用户安排会议。 确保已在 Outlook 配置文件中至少配置了一个 Exchange 邮箱，并使用它来安排与该外程序安排 Teams 会议。 有关 Exchange 要求，请参阅 ["Exchange 与 Teams 如何交互](https://docs.microsoft.com/microsoftteams/exchange-teams-interact)"。
- 此外接程序用于特定参与者的安排会议，而非用于频道中的会议。 频道会议必须从 Teams 中安排。
- 如果身份验证代理位于用户电脑和 Teams 服务的网络路径中，加载项将无法正常工作。
- 用户无法在 Outlook 中安排直播活动。 若要安排直播活动，请转到 Teams。 有关详细信息，请参阅[什么是 Microsoft Teams 直播活动？](teams-live-events/what-are-teams-live-events.md)。

详细了解 [Microsoft Teams 中的会议和通话](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8)。

## <a name="troubleshooting"></a>故障排除

使用以下步骤解决 Teams 会议加载项的问题。

### <a name="teams-meeting-add-in-in-outlook-for-windows-does-not-show"></a>Outlook for Windows 中的 Teams 会议加载项不显示

若无法安装 Outlook 的 Teams 会议加载项，请尝试下列故障排除步骤。

[下载](https://aka.ms/SaRA-TeamsAddInScenario) 并运行 [Microsoft 支持恢复助手，](https://aka.ms/SaRA_Home) 以执行自动化疑难解答步骤和修补程序。

或者，手动执行下列步骤：

- Windows 7 用户必须安装 [Windows 中通用 C Runtime 的更新才能](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows) 运行 Teams 会议加载项。
- 检查用户是否具有 Teams 升级策略，该策略支持 Teams 中的安排会议。 有关详细信息[，请参阅从 Skype for Business 升级到 Teams。](https://docs.microsoft.com/microsoftteams/upgrade-to-teams-on-prem-overview#meetings)
- 检查用户是否具有了允许 Outlook 加载项的 Teams 会议策略。 有关详细信息 [，请参阅 Teams 中的"](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams#allow-the-outlook-add-in) 管理会议策略"。
- 确保用户已安装了 Teams 桌面客户端。 只有使用 Teams 网页版客户端时，会议加载项不会安装。
- 确保用户安装了 Outlook 2013 或更高版本。
- 确保用户有权执行regsvr32.exe。
- 确保已应用 Outlook 桌面客户端的所有可用更新。
- 请按以下步骤操作：
  - 重启 Teams 桌面客户端。
  - 注销，然后重新登录到 Teams 桌面客户端。
  - 重启 Outlook 桌面客户端。  (确保 Outlook 未在管理模式下运行。) 

如果仍然看不到该加载项，请确保它未在 Outlook 中禁用。

- 在 Outlook 中，依 **次选择"文件** "和 **"选项**"。
- 选择 **Outlook"选项"对话框中** 的 **"加载项** "选项卡。
- 确认"活动 **应用程序加载项"列表中Microsoft Office Microsoft Teams** **会议加载项** 已列入"可用
- 如果 Teams 会议加载项列在禁用 **的应用程序加载项** 列表中，请选择" **管理"** 中的 COM **加载项** ，然后选择 **"转到..."。**
- 在 Microsoft Teams 会议加载项**for Windows 网站版窗口旁边设置Microsoft Office。**
- 在 **所有** 对话框上选择"确定"并重新启动 Outlook。

有关如何在 Office 程序中管理加载项的常规 [指导，请参阅"查看"、"管理"和"安装加载项](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D)"。

如果仍未显示加载项，请使用下列步骤验证注册表设置。

> [!NOTE]
> 编辑注册表不当可能严重损坏系统。 更改注册表之前，应备份计算机上任何有价值的数据。
- 启动RegEdit.exe
- 导航到 HKEY_CURRENT_USER\Software\Microsoft\Office\Outlook\Addins
- 确认团队Addin.FastConnect 存在。
- 在 TeamsAddin.FastConnect 内，验证是否存在 LoadBehavior，并且已设置为 3。
  - 如果 LoadBehavior 具有 3 以外的值，请将其更改为 3 并重启 Outlook。

### <a name="delegate-scheduling-does-not-work"></a>代理的安排不工作

若管理员已配置 Microsoft Exchange 来[控制对 Exchange Web Server (EWS) 的访问](https://docs.microsoft.com/exchange/client-developer/exchange-web-services/how-to-control-access-to-ews-in-exchange)，则代理无法代表上级安排 Teams 会议。 此配置的解决方案正在开发中，未来将予以发布。 作为一种变通方法，管理员可以将以下字符串添加到 EWS 允许列表 *："SchedulingService"。* 


## <a name="related-topics"></a>相关主题

[Teams 疑难解答](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
