---
title: 在 Outlook 中使用 Microsoft Teams 会议外接程序
author: ChuckEdmonson
ms.author: chucked
manager: serdars
audience: Admin
ms.date: 03/08/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams 会向 Outlook 中安装外接程序，从而让用户可以在 Outlook 中安排 Teams 会议。
ms.custom:
- NewAdminCenter_Update
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 801c4f43e9aafa7fe8331d85b601afd584505164
ms.sourcegitcommit: e5cb24ad166268392e692d3d1b92125646e5d66e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/23/2019
ms.locfileid: "34417440"
---
<a name="use-the-teams-meeting-add-in-in-outlook"></a>在 Outlook 中使用 Teams 会议外接程序
=======================================

对于在其 Windows PC 上安装了 Microsoft Teams 和 Office 2013 或 Office 2016 的用户，会自动安装 Teams 会议外接程序。 用户将在其 Outlook 日历功能区中看到 Teams 会议外接程序。 

![Outlook 功能区中的 Teams 外接程序屏幕截图。](media/Teams-add-in-for-Outlook.png)

> [!NOTE]
> Windows 7 用户必须安装[windows 中通用 C 运行时的更新](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows), 团队会议外接程序才能正常工作。

如果用户未看到 Teams 会议外接程序，请指示他们关闭 Outlook 和 Teams，然后按以下顺序执行操作：先重新启动 Teams 客户端，然后登录 Teams，再重新启动 Outlook 客户端。

> [!NOTE]
> Outlook for Mac 中的 "团队会议" 按钮将在 outlook for Mac 功能区中显示 (如果 Outlook 运行的是生产内部版本16.20 和更高版本)。

## <a name="authentication-requirements"></a>身份验证要求

Teams 会议外接程序要求用户使用新式身份验证登录 Teams。 如果用户未使用此方法登录，他们仍可使用 Teams 客户端，但无法使用 Outlook 外接程序安排 Teams 在线会议。 可以通过以下方式之一解决此问题：

- 如果贵组织未配置新式身份验证，则应配置新式身份验证。
- 如果配置了新式身份验证，但他们在对话框中取消了，则应该指示用户使用多重身份验证重新登录。

要了解关于如何配置身份验证的详细信息，请参阅 [Microsoft Teams 中的标识模式和身份验证](identify-models-authentication.md)。

## <a name="enable-private-meetings"></a>启用私人会议

必须在 Microsoft 团队管理中心中启用**专用会议的计划**, 才能使用插件进行部署。 在管理中心, 转到 "**会议** > **会议策略**", 然后在 "**常规**" 部分中, 切换**允许将私人会议安排**到 "开"。

![Microsoft 团队管理中心中的设置的屏幕截图。](media/teams-add-in-for-outlook-image1.png)

Teams 客户端通过确定用户需要 32 位还是 64 位版本来安装正确的外接程序。

> [!NOTE]
> 在安装或升级 Teams 后，用户可能需要重新启动 Outlook 才能获得最新的外接程序。

## <a name="other-considerations"></a>其他考虑事项

Teams 会议外接程序仍是正在构建的功能，因此请注意以下事项：
- 轮询尚不可用。
- 白板正在开始推出。
- 会议选项当前不可用。
- 当前只能邀请公司内部的人员，因为外部用户还不能加入会议。
- 此外接程序用于特定参与者的安排会议，而非用于频道中的会议。 频道会议必须从 Teams 中安排。 当前，仅面向 Windows 用户提供 Outlook 中的 Teams 会议外接程序，但即将面向 Mac 用户提供。
- 如果用户的 PC 和 Teams 服务的网络路径中存在身份验证代理，则此外接程序将无法工作。
- 外接程序将以增量方式进行滚动, 并且可能不会对你的组织提供。

## <a name="troubleshooting"></a>疑难解答

如果无法获取供 Outlook 安装的团队会议加载项, 请尝试以下疑难解答步骤。

- 确保已应用 Outlook 桌面客户端的所有可用更新 
- 重新启动团队桌面客户端。
- 注销, 然后重新登录到团队桌面客户端。
- 重新启动 Outlook 桌面客户端。 (请确保 Outlook 未在管理员模式下运行。)
- 请确保登录的用户帐户名称不包含空格。 (这是一个已知问题, 将在将来的更新中修复。)
- 请确保启用单一登录 (SSO)。

有关如何禁用外接程序的一般指导，请参阅[在 Office 程序中查看、管理和安装外接程序](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D)。

详细了解 [Microsoft Teams 中的会议和通话](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8)。

[!INCLUDE [new-feature-availability](includes/new-feature-availability.md)]

