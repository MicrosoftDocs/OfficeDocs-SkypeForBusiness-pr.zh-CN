---
title: 在 Microsoft Teams 中配置桌面共享
author: LolaJacobsen
ms.author: Lolaj
manager: serdars
ms.reviewer: jastark
ms.date: 03/22/2019
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 配置会议策略以允许用户在团队聊天或会议中共享其桌面
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: bb3340da960728b1a261efc510573702c5a17076
ms.sourcegitcommit: ed3a6789dedf54275e0b1ab41d4a4230eed6eb72
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2020
ms.locfileid: "41628708"
---
<a name="configure-desktop-sharing-in-microsoft-teams"></a>在 Microsoft Teams 中配置桌面共享
============================================

桌面共享允许用户在会议或聊天期间演示屏幕或应用。 管理员可以在 Microsoft 团队中配置屏幕共享，让用户共享整个屏幕、应用或文件。 你可以让用户提供或请求控制、允许 PowerPoint 共享、添加白板以及允许共享笔记。 你还可以配置匿名用户或外部用户是否可以请求共享屏幕的控制权。

若要配置屏幕共享，请创建新的会议策略，然后将其分配给要管理的用户。

**在[Microsoft 团队管理中心](https://admin.teams.microsoft.com/)**

1. 选择 "**会议** > **会议策略**"。

    ![显示所选会议策略的屏幕截图](media/configure-desktop-sharing-image1.png)

2. 在 "**会议策略**" 页面上，选择 "**新建策略**"。

    ![显示会议策略消息的屏幕截图](media/configure-desktop-sharing-image2.png)

3. 为你的策略提供一个唯一的标题，并输入简短说明。

4. 在 "**内容共享**" 下，从下拉列表中选择**屏幕共享模式**：

   - **整个屏幕**-允许用户共享其整个桌面。
   - **单个应用程序**-允许用户将屏幕共享限制在单个活动应用程序中。
   - **已禁用**–关闭屏幕共享。

    ![显示共享模式选项的屏幕截图](media/configure-desktop-sharing-image3.png)

5. 打开或关闭以下设置：

    - **允许参与者授予或请求控制**–允许团队成员授予或请求演示者的桌面或应用程序的控制权。
    - **允许外部参与者授予或请求控制**-允许来宾和外部（联合）用户向演示者的桌面或应用程序提供或请求控制。
    - **允许 powerpoint 共享**-允许用户创建允许上载和共享 PowerPoint 演示文稿的会议。
    - **允许使用白板**-允许用户共享白板。
    - **允许共享笔记**-使用户可以拍摄共享笔记。

6. 单击“**保存**”。

## <a name="use-powershell-to-configure-shared-desktop"></a>使用 PowerShell 配置共享桌面

你还可以使用[CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) cmdlet 控制桌面共享。 设置以下参数：

- 说明
- ScreenSharingMode
- AllowParticipantGiveRequestControl
- AllowExternalParticipantGiveRequestControl
- AllowPowerPointSharing
- AllowWhiteboard
- AllowSharedNotes

[了解有关使用 csTeamsMeetingPolicy cmdlet 的详细信息](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)。

