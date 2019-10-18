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
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6a8a440859d5bb33dfa5f57fd952f642b0e88dc7
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2019
ms.locfileid: "37563319"
---
<a name="use-the-teams-meeting-add-in-in-outlook"></a>在 Outlook 中使用 Teams 会议外接程序
=======================================

团队会议外接程序允许用户从 Outlook 安排团队会议。 该加载项可用于 Windows、Mac、web 和手机上的 Outlook。

## <a name="teams-meeting-add-in-in-outlook-for-windows"></a>Outlook for Windows 中的团队会议外接程序

将为在 Windows 电脑上安装了 Microsoft 团队以及 Office 2010、Office 2013 或 Office 2016 的用户自动安装团队会议加载项。 用户将在其 Outlook 日历功能区中看到 Teams 会议外接程序。

![Outlook 功能区上的团队会议外接程序的屏幕截图](media/Teams-add-in-for-Outlook.png)

> [!NOTE]
> - 如果用户未看到 Teams 会议外接程序，请指示他们关闭 Outlook 和 Teams，然后按以下顺序执行操作：先重新启动 Teams 客户端，然后登录 Teams，再重新启动 Outlook 客户端。
> - Windows 7 用户必须在 Windows for windows 中安装适用于 windows 的[通用 C 运行时更新](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows)，团队会议外接程序才能正常工作。
> - 如果您使用的是 Microsoft Store 中的 Office Outlook 安装，则不支持团队会议加载项。 建议使用此加载项的用户安装即点即用版本的 Office，如[Windows 10 中的 office On S 模式](https://support.office.com/article/faq-office-on-windows-10-in-s-mode-717193b5-ff9f-4388-84c0-277ddf07fe3f)文章中所述。 

## <a name="teams-meeting-add-in-in-outlook-for-mac"></a>Outlook for Mac 中的团队会议外接程序

如果 Outlook 运行的是 "生产内部版本 16.24.414.0" 和更高版本，outlook for Mac 中的 "团队会议" 按钮将显示在 Outlook for Mac 功能区中。

用户单击 "**发送**" 后，会议坐标（团队加入链接和拨入号码）将添加到会议邀请中。  

## <a name="teams-meeting-add-in-in-outlook-web-app"></a>Outlook Web App 中的团队会议加载项

如果用户使用新 Outlook 网页版的早期版本，Outlook Web App 中的 "团队会议" 按钮将显示为新的事件创建的一部分。 请参阅[Outlook 博客](https://techcommunity.microsoft.com/t5/Outlook-Blog/Designed-to-be-fast-The-Outlook-on-the-web-user-experience-gets/ba-p/234909?utm_source=t.co&utm_medium=referral)，了解用户如何在 web 上试用新版 Outlook 的早期版本。

![Outlook Web App 中的团队会议外接程序的屏幕截图](media/teams-meeting-add-in-web.png)

用户单击 "**发送**" 后，会议坐标（团队加入链接和拨入号码）将添加到会议邀请中。  

## <a name="teams-meeting-add-in-in-outlook-mobile-ios-and-android"></a>Outlook mobile 中的团队会议加载项（iOS 和 Android）

"团队会议" 按钮显示在 Outlook iOS 和 Android 应用的最新版本中。

![Outlook mobile 中的团队会议外接程序的屏幕截图](media/teams-meeting-add-in-mobile.png)

用户单击 "**发送**" 后，会议坐标（团队加入链接和拨入号码）将添加到会议邀请中。  

## <a name="teams-meeting-add-in-in-and-findtime-for-outlook"></a>Outlook 中的团队会议外接程序和 FindTime
FindTime 是 Outlook 的加载项，可帮助用户在公司内通过会议时间达成共识。 会议被邀请者提供其首选时间后，FindTime 代表用户发送会议邀请。 如果在 FindTime 中选中 "**联机会议**" 选项，则 FindTime 将安排 Skype for Business 或 Microsoft 团队会议。 （FindTime 将使用您的组织设置为默认联机会议频道的任何人。）

> [!NOTE]  
> 如果您在[Findtime 仪表板](https://findtime.microsoft.com/UserDashboard)中保存了 "Skype for business" 设置，则 Findtime 将使用该设置，而不是 Microsoft 团队。 如果要使用 Microsoft 团队，请删除仪表板中的 "Skype for Business" 设置。

有关详细信息，请参阅[安排有关 FindTime 的会议](https://support.office.com/article/scheduling-meetings-with-findtime-4dc806ed-fde3-4ea7-8c5e-b5d1fddab4a6)。

## <a name="authentication-requirements"></a>身份验证要求

Teams 会议外接程序要求用户使用新式身份验证登录 Teams。 如果用户未使用此方法登录，他们仍可使用 Teams 客户端，但无法使用 Outlook 外接程序安排 Teams 在线会议。 可以通过以下方式之一解决此问题：

- 如果贵组织未配置新式身份验证，则应配置新式身份验证。
- 如果已配置新式身份验证，但在对话框中取消了这些身份验证，则应指示用户使用多重身份验证再次登录。

要了解关于如何配置身份验证的详细信息，请参阅 [Microsoft Teams 中的标识模式和身份验证](identify-models-authentication.md)。

## <a name="enable-private-meetings"></a>启用私人会议

必须在 Microsoft 团队管理中心中启用**专用会议的计划**，才能在加载项中进行部署。 在管理中心，转到 "**会议** > **会议策略**"，然后在 "**常规**" 部分中，切换**允许将私人会议安排**到 "开"。

![Microsoft 团队管理中心中的设置的屏幕截图。](media/teams-add-in-for-outlook-image1.png)

Teams 客户端通过确定用户需要 32 位还是 64 位版本来安装正确的外接程序。

> [!NOTE]
> 在安装或升级 Teams 后，用户可能需要重新启动 Outlook 才能获得最新的外接程序。

## <a name="teams-upgrade-policy-and-the-teams-meeting-add-in-for-outlook"></a>适用于 Outlook 的团队升级策略和团队会议外接程序

客户可以[选择其从 Skype For business 到团队的升级旅程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)。 租户管理员可以使用团队共存模式为其用户定义此旅程。 租户管理员可以选择使用户能够使用团队和 Skype for Business （孤岛模式）。 

当在 Outlook 中以 "岛" 模式安排会议的用户通常希望能够选择是安排 Skype for Business 还是团队会议。 在 Outlook 网页版、Outlook 窗口和 Outlook Mac 版中，用户在孤岛模式下会看到 Skype for business 和团队外接程序。 由于初始版本中的某些限制，Outlook mobile 仅支持创建 Skype for Business**或**团队会议。 有关详细信息，请参阅下表。

| 团队管理中心中的共存模式 | Outlook mobile 中的默认会议提供商 |
| --------------------------------------|---------------------------------------------|
| 群岛 | Skype for Business |
| 仅限 Skype for business | Skype for Business |
| 具有团队协作的 Skype for Business | Skype for Business |
| 具有团队协作和会议的 Skype for business | Teams |
| 仅限团队 | Teams |

## <a name="other-considerations"></a>其他考虑事项

Teams 会议外接程序仍是正在构建的功能，因此请注意以下事项：

- 此外接程序用于特定参与者的安排会议，而非用于频道中的会议。 频道会议必须从 Teams 中安排。
- 如果用户的 PC 和 Teams 服务的网络路径中存在身份验证代理，则此外接程序将无法工作。
- 用户无法在 Outlook 中安排实时事件。 转到团队以安排实时事件。 有关详细信息，请参阅[Microsoft 团队实时事件是什么？](teams-live-events/what-are-teams-live-events.md)。

## <a name="troubleshooting"></a>疑难解答

如果无法获取供 Outlook 安装的团队会议加载项，请尝试以下疑难解答步骤。

- 确保已应用 Outlook 桌面客户端的所有可用更新。
- 重新启动团队桌面客户端。
- 注销，然后重新登录到团队桌面客户端。
- 重新启动 Outlook 桌面客户端。 （请确保 Outlook 未在管理员模式下运行。）
- 请确保登录的用户帐户名称不包含空格。 （这是一个已知问题，将在将来的更新中修复。）
- 请确保启用单一登录（SSO）。

如果管理员已将 Microsoft Exchange 配置为[控制对 Exchange Web 服务器（EWS）的访问](https://docs.microsoft.com/en-us/exchange/client-developer/exchange-web-services/how-to-control-access-to-ews-in-exchange)，代理人将无法代表上司安排团队会议。 此配置的解决方案正在开发中，将在将来发布。 

有关如何禁用外接程序的一般指导，请参阅[在 Office 程序中查看、管理和安装外接程序](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D)。

详细了解 [Microsoft Teams 中的会议和通话](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8)。
