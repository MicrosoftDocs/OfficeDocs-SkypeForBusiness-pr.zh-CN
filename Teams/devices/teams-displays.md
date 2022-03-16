---
title: Microsoft Teams显示器
ms.author: czawideh
author: cazawideh
manager: serdars
ms.reviewer: weizxue
ms.topic: reference
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
search.appverid: MET150
ms.localizationpriority: medium
description: 本文概述了屏幕屏幕支持的功能Microsoft Teams功能。
ms.openlocfilehash: 77af5392b539045cdbacda2d6c278d35098437ed
ms.sourcegitcommit: dafe48cea1643e1bd79390482da9b002d7e9e0bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2022
ms.locfileid: "63514675"
---
# <a name="microsoft-teams-displays"></a>Microsoft Teams显示器

Microsoft Teams显示器是一类一体式专用Teams设备，具有环境触摸屏和由屏幕支持的免费Cortana。 本文概述了各种Teams，可帮助你规划、传送和管理Teams显示。

Teams显示将你喜爱的Teams聊天&ndash;&ndash;、会议、呼叫、日历和文件汇集到单个设备。 借助Teams，用户可以使用麦克风、相机和扬声器 (或耳机蓝牙耳机) 可靠的呼叫和会议体验。 Teams显示器与用户Windows电脑集成，带来一种支持无缝跨设备交互的配套体验。

若要了解有关详细信息，请查看[屏幕Teams入门](https://support.microsoft.com/office/get-started-with-teams-displays-ff299825-7f13-4528-96c2-1d3437e6d4e6)。

## <a name="features-supported-by-teams-displays"></a>显示器支持Teams功能

除了手机[支持的功能](phones-for-teams.md#features-supported-by-teams-phones)Teams，以下功能对于显示器Teams独一无二：

- **专用显示Teams** 用户可以访问所有核心Teams功能，包括聊天、会议、通话、团队和频道、文件等。
- **环境体验** 用户可以轻松地使用始终开启且易于浏览的显示来了解重要的活动和通知，而无需在主要工作设备上切换上下文。 用户还可通过Teams自定义背景来个性化显示。
- 使用 Cortana 用户可使用语音与 Teams 显示器交互，轻松加入和参加会议、口述对 Teams 聊天的答复、查看日历上显示内容等。
- **在锁屏上留下备注** 来宾可以选择保留音频、视频和文本笔记，用户可以查看来宾留下的笔记并查看被谁阻止。  

## <a name="required-licenses"></a>所需的许可证

Teams许可证可以购买为订阅和Microsoft 365 [Office 365的一部分](/office365/servicedescriptions/teams-service-description)。 若要了解有关使用显示器所需的许可证Teams，请参阅语音和视频[呼叫与](https://products.office.com/microsoft-teams/voice-calling) Microsoft Teams。

若要详细了解如何获取Teams，请参阅如何[获取对 Microsoft Teams？](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)

## <a name="deploy-teams-displays-using-intune"></a>使用 intune Teams视图

若要详细了解如何使用 Intune Teams屏幕，请参阅部署Teams[手机和Teams显示器](phones-displays-deploy.md)。

## <a name="manage-teams-displays-in-your-organization"></a>管理Teams显示

若要管理Teams显示设备，在 Microsoft Teams 管理中心的左侧导航中，转到Teams **显示。** 可在此处更改设备配置文件、管理更新、重启设备、添加和删除设备标记等。 有关详细信息，请参阅[在 Teams 中管理设备](device-management.md)。

## <a name="set-up-hot-desking-on-teams-displays"></a>在显示器上设置Teams桌面

使用热桌面，您的组织中的人员可以通过工作区和设备本身Teams Outlook预订临时工作区。 启用热桌面功能后，用户使用Teams凭据登录到 Microsoft 365，以访问其会议、聊天和文件。 当他们注销时，其所有个人信息将从设备中删除。

若要开始，需要获取Microsoft Teams 会议室标准版许可证，并为每个屏幕显示创建Teams帐户。 请参阅[为会议室和共享设备创建Teams帐户以](../rooms/with-office-365.md)创建资源帐户。

创建资源帐户后，可以创建并分配策略以启用热桌面。 有关详细信息 [，请参阅 New-CsTeamsIPPhonePolicy](/powershell/module/skype/new-csteamsipphonepolicy?view=skype-ps) 。

> [!IMPORTANT]
> 由于Teams在共享工作区中使用多个带热桌面的显示器，因此环境中的条件访问规则和其他标识配置（如多重身份验证）可能会影响这些设备，并造成登录问题。 有关保护共享设备的指南，请参阅 Android 设备上[共享设备的Teams最佳做法](authentication-best-practices-for-android-devices.md)。

## <a name="upgrade-teams-phones-to-teams-displays"></a>将Teams手机升级到Teams显示器

Teams显示是手机Teams的演变。 您可以使用 Teams 管理中心将Teams升级为Microsoft Teams显示。 此选项仅适用于支持升级到显示器Teams手机。 有关详细信息，请参阅将手机[Teams到Teams显示](upgrade-phones-to-displays.md)。

## <a name="see-also"></a>另请参阅

[显示Microsoft Teams介绍](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/introducing-microsoft-teams-displays/ba-p/1505437)

[Teams市场](https://office.com/teamsdevices)

[Teams 电话](phones-for-teams.md)

[经认证的 IP 电话Microsoft Teams](teams-ip-phones.md)

[将 IP 电话升级到Teams显示](upgrade-phones-to-displays.md)

[Cortana语音帮助Teams](../cortana-in-teams.md)