---
title: "在 Outlook 中使用 Microsoft Teams 会议外接程序"
author: ChuckEdmonson
ms.author: chucked
manager: lolaj
ms.date: 01/23/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ninadara
description: "Microsoft Teams 会向 Outlook 中安装外接程序，从而让用户可以在 Outlook 中安排 Teams 会议。"
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: c8c8930787d74fdc0dddf2b7987a967e130721d2
ms.sourcegitcommit: 4b69ae91de3f82912eda3513cec65ae12e1ce2b2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2018
---
<a name="use-the-teams-meeting-add-in-in-outlook"></a>在 Outlook 中使用 Teams 会议外接程序
=======================================

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

必须在 [Office 365 管理中心](https://portal.office.com/adminportal/home)中启用“允许安排私人会议”，才能部署该插件。

![Office 365 管理中心中“通话和会议”部分中设置的屏幕截图。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image9.png)

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

如果你不希望用户看到 Teams 会议外接程序，可以将其删除。 有关如何禁用外接程序的一般指导，请参阅[在 Office 程序中查看、管理和安装外接程序](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D)。

详细了解 [Microsoft Teams 中的会议和通话](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8)。

