---
title: 在 Outlook 中使用 Microsoft Teams 会议外接程序
author: ChuckEdmonson
ms.author: chucked
manager: serdars
audience: Admin
ms.date: 07/16/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ''
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams 会向 Outlook 中安装外接程序，从而让用户可以在 Outlook 中安排 Teams 会议。
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 07cc04f47da980bfb5a637c1cfe6bc2b72a26f8f
ms.sourcegitcommit: 6212645c485c41aafe1206bf7d39171ce35837b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2018
ms.locfileid: "24967356"
---
<a name="use-the-teams-meeting-add-in-in-outlook"></a>在 Outlook 中使用 Teams 会议外接程序
=======================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

对于在其 Windows PC 上安装了 Microsoft Teams 和 Office 2013 或 Office 2016 的用户，会自动安装 Teams 会议外接程序。 用户将在其 Outlook 日历功能区中看到 Teams 会议外接程序。 

![Outlook 功能区中的 Teams 外接程序屏幕截图。](media/Teams-add-in-for-Outlook.png)

如果用户未看到 Teams 会议外接程序，请指示他们关闭 Outlook 和 Teams，然后按以下顺序执行操作：先重新启动 Teams 客户端，然后登录 Teams，再重新启动 Outlook 客户端。

> [!NOTE]
> 当前未面向 Mac 用户提供 Outlook 的 Teams 会议外接程序。

## <a name="authentication-requirements"></a>身份验证要求

Teams 会议外接程序要求用户使用新式身份验证登录 Teams。 如果用户未使用此方法登录，他们仍可使用 Teams 客户端，但无法使用 Outlook 外接程序安排 Teams 在线会议。 可以通过以下方式之一解决此问题：

- 如果贵组织未配置新式身份验证，则应配置新式身份验证。
- 如果配置了新式身份验证，但他们在对话框中取消了，则应该指示用户使用多重身份验证重新登录。

要了解关于如何配置身份验证的详细信息，请参阅 [Microsoft Teams 中的标识模式和身份验证](identify-models-authentication.md)。

## <a name="enable-private-meetings"></a>启用私人会议

允许中团队业务管理中心此插件的 Skype 获取部署必须启用专用会议计划。 在管理中心，转到**会议** > **会议策略**，并在**常规**部分，为切换**允许安排专用会议**。)

![Skype 业务管理中心的团队中的设置的屏幕截图。](media/teams-add-in-for-outlook-image1.png)

Teams 客户端通过确定用户需要 32 位还是 64 位版本来安装正确的外接程序。

> [!NOTE]
> 在安装或升级 Teams 后，用户可能需要重新启动 Outlook 才能获得最新的外接程序。

## <a name="other-considerations"></a>其他考虑事项

Teams 会议外接程序仍是正在构建的功能，因此请注意以下事项：
- 一些在线会议功能（例如，录制、投票和白板）还不可用。
- 会议选项当前不可用。
- 当前只能邀请公司内部的人员，因为外部用户还不能加入会议。
- 此外接程序用于特定参与者的安排会议，而非用于频道中的会议。 频道会议必须从 Teams 中安排。 当前，仅面向 Windows 用户提供 Outlook 中的 Teams 会议外接程序，但即将面向 Mac 用户提供。
- 如果用户的 PC 和 Teams 服务的网络路径中存在身份验证代理，则此外接程序将无法工作。
- 外接程序要增量推出和可能不可用，贵组织尚未。

## <a name="troubleshooting"></a>疑难解答

如果无法让团队会议外接程序 Outlook 安装，请尝试以下疑难解答步骤。

- 确保已应用 Outlook 桌面客户端的所有可用更新 
- 重新启动团队桌面客户端。
- 注销并重新登录到团队桌面客户端。
- 重新启动 Outlook 桌面客户端。 （确保 Outlook 没有运行管理员模式中。）
- 请确保已登录的用户帐户名不包含空格。 （这是一个已知的问题，并将在以后更新修复。）
- 请确保已启用单一登录 (SSO)。

有关如何禁用外接程序的一般指导，请参阅[在 Office 程序中查看、管理和安装外接程序](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D)。

详细了解 [Microsoft Teams 中的会议和通话](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8)。

[!INCLUDE [new-feature-availability](includes/new-feature-availability.md)]

