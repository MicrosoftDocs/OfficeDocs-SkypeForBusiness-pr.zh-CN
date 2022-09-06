---
title: Microsoft Teams 显示
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
- Teams_ITAdmin_Devices
search.appverid: MET150
ms.localizationpriority: medium
description: 本文概述了 Microsoft Teams 显示支持的功能。
ms.openlocfilehash: 8b06078633dd8c7ee43c2ee98ad1f3e4751d3a51
ms.sourcegitcommit: 75dfc3cd9b59282d68e35e4d7185da572eb3795c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2022
ms.locfileid: "67606021"
---
# <a name="microsoft-teams-displays"></a>Microsoft Teams 显示

Microsoft Teams 显示器是一类一体专用 Teams 设备，具有环境触摸屏和 Cortana 支持的免提体验。 本文概述了 Teams 显示，可帮助你规划、交付和管理组织中的 Teams 显示。

Teams 显示会将你最喜欢的 Teams 功能&ndash;聊天、会议、通话、日历和文件&ndash;汇集到单个设备中。 使用 Teams 显示器，用户可以使用麦克风、相机和扬声器 (或蓝牙耳机) 实现可靠的通话和会议体验。 Teams 显示与用户的 Windows 电脑集成，以提供允许无缝跨设备交互的配套体验。

若要了解详细信息，请查看 [Teams 显示器入](https://support.microsoft.com/office/get-started-with-teams-displays-ff299825-7f13-4528-96c2-1d3437e6d4e6)门。

## <a name="features-supported-by-teams-displays"></a>Teams 支持的功能显示

除了 [Teams 手机支持的功能](phones-for-teams.md#features-supported-by-teams-phones)外，Teams 显示的功能也独一无二：

- **Teams 专用显示** 用户可以访问所有核心 Teams 功能，包括聊天、会议、呼叫、团队和频道、文件等。
- **环境体验** 用户可以使用始终打开且可浏览的显示器轻松地保持工作状态，以查看重要活动和通知，而无需在主工作设备上切换上下文。 用户还可以通过设置自定义背景来个性化 Teams 显示。
- **使用 Cortana 免提** 用户可以使用其语音与 Teams 显示器进行交互，以轻松加入和出席会议、听写对 Teams 聊天的答复、检查日历上的内容等。
- **在锁屏上留下便笺** 来宾可以选择留下音频、视频和文本笔记，用户可以检查来宾留下的笔记，并查看谁被拦住了。  

## <a name="required-licenses"></a>所需的许可证

Teams 许可证可以作为 [Microsoft 365 和Office 365订阅的一](/office365/servicedescriptions/teams-service-description)部分购买。 若要详细了解使用 Teams 显示器所需的许可证，请参阅 [Microsoft Teams 的语音和视频通话](https://products.office.com/microsoft-teams/voice-calling)。

有关如何获取 Teams 的详细信息，请查看[如何实现访问 Microsoft Teams？](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)

## <a name="deploy-teams-displays-using-intune"></a>使用 Intune 部署 Teams 显示

若要了解有关如何使用Intune部署 Teams 显示器的详细信息，请参阅[部署 Teams 手机和 Teams 显示器](phones-displays-deploy.md)。

## <a name="manage-teams-displays-in-your-organization"></a>管理组织中的 Teams 显示

若要管理 Teams 显示设备，请在 Microsoft Teams 管理中心的左侧导航中转到 **Teams 显示器**。 在此处，可以更改设备配置文件、管理更新、重启设备、添加和删除设备标记等。 有关详细信息，请参阅 [在 Teams 中管理设备](device-management.md)。

## <a name="set-up-hot-desking-on-teams-displays"></a>在 Teams 显示器上设置热桌面

热桌面允许组织中的人员通过 Teams 和 Outlook 或设备本身提前保留临时工作区。 启用热桌面后，登录 Teams 的用户会显示其 Microsoft 365 凭据来访问其会议、聊天和文件。 注销后，其所有个人信息将从设备中删除。

若要开始，需要获取[Microsoft Teams 会议室许可证](../rooms/rooms-licensing.md)并为每个 Teams 显示创建资源帐户。 请参阅 [为会议室和共享 Teams 设备创建资源帐户](../rooms/with-office-365.md) 以创建资源帐户。

创建资源帐户后，可以创建并分配策略以启用热桌面。 有关详细信息，请参阅 [New-CsTeamsIPPhonePolicy](/powershell/module/skype/new-csteamsipphonepolicy) 。

> [!IMPORTANT]
> 由于多个用户在共享工作区中使用具有热桌面的 Teams 显示，因此环境中的条件访问规则和其他标识配置（如多重身份验证）可能会影响这些设备并导致登录问题。 有关保护共享设备的指南，请参阅 [共享 Teams Android 设备的身份验证最佳做法](authentication-best-practices-for-android-devices.md)。

## <a name="upgrade-teams-phones-to-teams-displays"></a>将 Teams 手机升级到 Teams 显示

Teams 显示是 Teams 手机的演变。 可以使用 Microsoft Teams 管理中心将组织中的 Teams 手机升级到 Teams 显示。 此选项仅适用于支持升级到 Teams 显示器的手机。 若要了解详细信息，请参阅[“将 Teams 手机升级到 Teams”显示。](upgrade-phones-to-displays.md)

## <a name="see-also"></a>另请参阅

[Microsoft Teams 显示简介](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/introducing-microsoft-teams-displays/ba-p/1505437)

[Teams 市场](https://office.com/teamsdevices)

[Teams 电话](phones-for-teams.md)

[经 Microsoft Teams 认证的 IP 电话](teams-ip-phones.md)

[将 IP 电话升级到 Teams 显示](upgrade-phones-to-displays.md)

[Teams 中的 Cortana 语音协助](../cortana-in-teams.md)