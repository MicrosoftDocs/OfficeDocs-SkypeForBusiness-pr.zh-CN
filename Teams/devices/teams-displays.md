---
title: Microsoft Teams显示
ms.author: dstrome
author: dstrome
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
description: 本文概述了Microsoft Teams显示器支持的功能。
ms.openlocfilehash: 4b724370ff348f41b8d4c4406a218e1dd1ba0709
ms.sourcegitcommit: 726df9ecac561bda18e349a5adab9bc85e52844d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2022
ms.locfileid: "65760864"
---
# <a name="microsoft-teams-displays"></a>Microsoft Teams显示

Microsoft Teams显示器是一类一体专用Teams设备，这些设备具有环境触摸屏和由Cortana提供支持的免提体验。 本文概述了Teams显示，可以帮助你规划、交付和管理组织中的Teams显示。

Teams显示器将你最喜欢的Teams功能&ndash;聊天、会议、呼叫、日历和文件&ndash;汇集到单个设备中。 使用Teams显示器，用户可以使用麦克风、相机和扬声器 (或蓝牙耳机) 以获得可靠的通话和会议体验。 Teams显示器与用户的Windows电脑集成，以提供允许无缝跨设备交互的配套体验。

若要了解详细信息，请使用[Teams显示](https://support.microsoft.com/office/get-started-with-teams-displays-ff299825-7f13-4528-96c2-1d3437e6d4e6)器查看开始。

## <a name="features-supported-by-teams-displays"></a>Teams显示器支持的功能

除了[Teams手机支持的功能](phones-for-teams.md#features-supported-by-teams-phones)外，以下功能对于Teams显示器是唯一的：

- **专用显示Teams** 用户可以访问所有核心Teams功能，包括聊天、会议、呼叫、团队和频道、文件等。
- **环境体验** 用户可以使用始终打开且可浏览的显示器轻松地保持工作状态，以查看重要活动和通知，而无需在主工作设备上切换上下文。 用户还可以通过设置自定义背景来个性化Teams显示。
- 与Cortana用户可以使用语音与Teams显示器进行 **交** 互，以轻松地加入和出席会议、口述对Teams聊天的答复、检查日历上的内容等。
- **在锁屏上留下便笺** 来宾可以选择留下音频、视频和文本笔记，用户可以检查来宾留下的笔记，并查看谁被拦住了。  

## <a name="required-licenses"></a>所需的许可证

Teams许可证可以作为[Microsoft 365和Office 365订阅的一](/office365/servicedescriptions/teams-service-description)部分购买。 若要详细了解使用Teams显示器所需的许可证，请参阅[带Microsoft Teams的语音和视频通话](https://products.office.com/microsoft-teams/voice-calling)。

有关如何获取Teams的详细信息，请查看[如何实现获取Microsoft Teams的访问权限？](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)

## <a name="deploy-teams-displays-using-intune"></a>使用Intune部署Teams显示器

若要详细了解如何使用Intune部署Teams显示器，请[参阅部署Teams手机和Teams显示器](phones-displays-deploy.md)。

## <a name="manage-teams-displays-in-your-organization"></a>管理组织中的Teams显示

若要管理Teams显示设备，请在Microsoft Teams管理中心的左侧导航中，转到 **Teams显示器**。 在此处，可以更改设备配置文件、管理更新、重启设备、添加和删除设备标记等。 有关详细信息，请参阅[Teams中管理设备](device-management.md)。

## <a name="set-up-hot-desking-on-teams-displays"></a>在Teams显示器上设置热桌面

热桌面允许组织中的人员通过Teams和Outlook或设备本身提前保留临时工作区。 启用热桌面后，用户使用Microsoft 365凭据登录到Teams显示，以访问其会议、聊天和文件。 注销后，其所有个人信息将从设备中删除。

若要开始，需要获取Microsoft Teams 会议室标准版许可证并为每个Teams显示创建资源帐户。 请参阅[为会议室和共享Teams设备创建资源帐户](../rooms/with-office-365.md)，以创建资源帐户。

创建资源帐户后，可以创建并分配策略以启用热桌面。 有关详细信息，请参阅 [New-CsTeamsIPPhonePolicy](/powershell/module/skype/new-csteamsipphonepolicy?view=skype-ps) 。

> [!IMPORTANT]
> 由于具有热桌面的Teams显示在共享工作区中由多人使用，因此环境中的条件访问规则和其他标识配置（如多重身份验证）可能会影响这些设备并导致登录问题。 有关保护共享设备的指导，请参阅[共享Teams Android设备的身份验证最佳做法](authentication-best-practices-for-android-devices.md)。

## <a name="upgrade-teams-phones-to-teams-displays"></a>将Teams手机升级到Teams显示器

Teams显示是手机Teams演变。 可以使用Microsoft Teams管理中心将组织中的Teams手机升级到Teams显示器。 此选项仅适用于支持升级到Teams显示器的手机。 若要了解详细信息，请参阅[升级Teams手机以Teams显示。](upgrade-phones-to-displays.md)

## <a name="see-also"></a>另请参阅

[Microsoft Teams显示器简介](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/introducing-microsoft-teams-displays/ba-p/1505437)

[Teams市场](https://office.com/teamsdevices)

[Teams 电话](phones-for-teams.md)

[已通过Microsoft Teams认证的 IP 电话](teams-ip-phones.md)

[将 IP 电话升级到Teams显示器](upgrade-phones-to-displays.md)

[Cortana语音协助Teams](../cortana-in-teams.md)