---
title: 打开或关闭会议中会议的进入和退出Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: 管理员可以了解如何在会议结束后打开或关闭进入和退出Microsoft Teams通知。
ms.openlocfilehash: 6a939495c3fe537873b464064656fc529719457f
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2021
ms.locfileid: "58728861"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-microsoft-teams"></a>在 Microsoft Teams 中打开或关闭会议的进入和退出公告

当你在会议或会议Microsoft 365设置Office 365，你将获得音频会议网桥。 会议网桥可以包含一个或多个供大家用于拨入 Microsoft Teams 会议的电话号码。
  
会议网桥负责应答使用电话拨入会议的用户的呼叫。 会议网桥通过来自会议自动助理的语音提示应答呼叫者，然后根据你的设置，可以播放通知、让呼叫者录制其姓名以及设置 PIN 安全。 将向 Microsoft Teams 会议组织者提供一个 PIN，如果组织者无法使用 Microsoft Teams 应用启动会议，可以使用该 PIN 启动会议。 但你可以设置不需要使用 PIN 即可启动会议。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a>设置会议加入选项

![一个图标，显示Microsoft Teams徽标。](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**

必须是 Teams 服务管理员才能管理这些策略。 请参阅 [Teams 管理员角色管理 Teams](./using-admin-roles.md) ，了解管理员角色和权限。

1. 登录到管理中心。

2. 在左侧导航中，转到“**会议**” > “**会议网桥**”。

3. 在“**会议网桥**”页面顶部，单击“**网桥设置**”。

4. 在“**网桥设置**”窗格中，启用或禁用“**会议进入和退出通知**”。 默认情况下，此选项处于选中状态。 如果你将其取消选中，则当有人进入或离开会议时，已加入会议的用户不会收到通知。

5. 在 **进入/退出公告类型** 下，选择 **姓名或电话号码** 或 **提示音**。

   > [!NOTE]
   > 默认情况下，外部参与者看不到拨入参与者的电话号码。 如果想要保持这些电话号码的隐私，请选择“**进入/退出公告类型**”的“**提示音**”（这会阻止 Teams 读出电话号码）。

6. 如果你选择“**姓名或电话号码**”，请启用或禁用“**要求呼叫者在加入会议之前录制其姓名**”。

7. 单击“**保存**”。

## <a name="want-to-know-more-about-windows-powershell"></a>想要了解有关Windows PowerShell

Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。 使用Windows PowerShell，可以使用Microsoft 365管理Office 365管理点来管理任务或任务，当您有多个任务需要执行时，可以简化日常工作。 若要开始使用 Windows PowerShell，请参阅下列主题：

- [为何需要将 Microsoft 365 或 Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [使用 Microsoft 365 Office 365 管理Office 365或Windows PowerShell](/previous-versions//dn568025(v=technet.10))

有关 Windows PowerShell 的详细信息，请参阅 [Microsoft Teams PowerShell 参考](/powershell/module/teams/?view=teams-ps)了解详细信息。
  
## <a name="related-topics"></a>相关主题

[音频会议常见问题](audio-conferencing-common-questions.md)