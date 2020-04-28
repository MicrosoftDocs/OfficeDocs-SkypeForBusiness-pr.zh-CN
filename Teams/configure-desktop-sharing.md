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
f1.keywords:
- NOCSH
description: 了解如何配置会议策略以让用户在团队聊天或会议中共享其桌面。
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 955a642d2a2309ccbaf9f9d6280170a93a9179ae
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905894"
---
<a name="configure-desktop-sharing-in-microsoft-teams"></a>在 Microsoft Teams 中配置桌面共享
============================================

桌面共享让用户可以在会议或聊天过程中呈现屏幕或应用。 管理员可在 Microsoft Teams 中配置屏幕共享，让用户共享整个屏幕、某个应用或文件。 你可以让用户提供或请求控制权、允许 PowerPoint 共享、添加白板以及允许共享笔记。 你还可以配置匿名或外部用户是否可以请求共享屏幕的控制权。

若要配置屏幕共享，请创建新的会议策略，然后将其分配给要管理的用户。

**在 [Microsoft Teams 管理中心](https://admin.teams.microsoft.com/)**

1. 选择“**会议**” > “**会议策略**”。

    ![显示已选中“会议策略”的屏幕截图](media/configure-desktop-sharing-image1.png)

2. 在“**会议策略**”页面上，选择“**新建策略**”。

    ![显示“会议策略”消息的屏幕截图](media/configure-desktop-sharing-image2.png)

3. 为策略提供唯一的标题，并输入简要说明。

4. 在“**内容共享**”下，从下拉列表中选择一种**屏幕共享模式**：

   - **整个屏幕** - 让用户共享其整个桌面。
   - **单个应用程序** - 允许用户将屏幕共享限制为单个活动的应用程序。
   - **已禁用** - 关闭屏幕共享。

    ![显示共享模式选项的屏幕截图](media/configure-desktop-sharing-image3.png)

5. 打开或关闭以下设置：

    - **允许参与者授予或请求控制**–允许团队成员授予或请求演示者的桌面或应用程序的控制权。
    - **允许外部参与者授予或请求控制**-允许来宾和外部（联合）用户向演示者的桌面或应用程序提供或请求控制。
    - **允许 PowerPoint 共享** - 允许用户创建可上传和共享 PowerPoint 演示文稿的会议。
    - **允许白板** - 允许用户共享白板。
    - **允许共享笔记** - 允许用户记录共享笔记。

6. 单击“**保存**”。

## <a name="use-powershell-to-configure-shared-desktop"></a>使用 PowerShell 配置共享桌面

你还可以使用 [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) cmdlet 来控制桌面共享。 设置以下参数：

- Description
- ScreenSharingMode
- AllowParticipantGiveRequestControl
- AllowExternalParticipantGiveRequestControl
- AllowPowerPointSharing
- AllowWhiteboard
- AllowSharedNotes

[了解有关使用 csTeamsMeetingPolicy cmdlet 的详细信息](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)。

