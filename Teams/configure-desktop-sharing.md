---
title: 配置中的 Microsoft 团队的桌面共享
author: LolaJacobsen
ms.author: Lolaj
manager: serdars
ms.reviewer: jastark
ms.date: 12/07/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: 配置会议策略以让用户共享其桌面团队聊天或会议中
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 422d5fb3a19dad2e14e0cdf54a532b0afc6eed67
ms.sourcegitcommit: ea6ee8ce28e82fcd7c07554c3428ae242d6f04da
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/07/2018
ms.locfileid: "27202486"
---
<a name="configure-desktop-sharing-in-microsoft-teams"></a>配置中的 Microsoft 团队的桌面共享
============================================

桌面共享允许用户在会议或对话过程中演示屏幕或应用程序。 管理员可以配置屏幕中 Microsoft 团队以使用户可以共享整个屏幕、 应用程序或文件共享。 您可以让用户授予或请求控制、 允许共享 PowerPoint、 添加白板和允许共享的便笺。 您还可以配置是否匿名或外部用户可以请求对共享屏幕的控制权。

要配置屏幕共享，您创建新的会议策略，然后将其分配给您要管理的用户。

在 Microsoft 团队业务管理中心的 Skype:

1. 选择**会议** > **会议策略**。

    ![选择会议策略](media/configure-desktop-sharing-image1.png)

2. 在**会议策略**页上，选择**新建策略**。

    ![选择新策略](media/configure-desktop-sharing-image2.png)

3. 为您的策略指定唯一的标题，并输入的简要说明。

4. 在**内容共享**下从下拉列表中选择**屏幕共享模式**:

   - **整个屏幕**– 允许共享整个桌面的用户。
   - **单个应用程序**– 允许用户限制屏幕共享单个活动应用程序。
   - **禁用**— 将会关闭屏幕共享。

    ![选择屏幕共享模式](media/configure-desktop-sharing-image3.png)

5. 打开或关闭以下设置：

    - **允许参与者授予或请求控制权**– 允许工作组成员授予或请求演示者的桌面或应用程序的控制权。
    - **允许外部参与者授予或请求控制**– 允许来宾和外部 （联盟） 的用户授予或请求演示者的桌面或应用程序的控制权。
    - **允许 PowerPoint 共享**-允许用户创建允许 PowerPoint 演示文稿上载和共享的会议。
    - **允许白板**– 允许用户共享的白板。
    - **允许共享的便笺**– 允许用户执行共享的便笺。

6. 单击“**保存**”。

## <a name="use-powershell-to-configure-shared-desktop"></a>使用 PowerShell 配置共享的桌面

[设置 CsTeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) cmdlet 还可用于控制桌面共享。 设置以下参数：

- 说明
- ScreenSharingMode
- AllowParticipantGiveRequestControl
- AllowExternalParticipantGiveRequestControl
- AllowPowerPointSharing
- AllowWhiteboard
- AllowSharedNotes

[了解有关使用 csTeamsMeetingPolicy cmdlet](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)。

