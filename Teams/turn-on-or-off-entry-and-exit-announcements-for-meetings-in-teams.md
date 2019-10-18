---
title: 在 Microsoft Teams 中打开或关闭会议的进入和退出公告
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
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: '了解如何在 Microsoft Teams 会议中打开或关闭进入和退出公告。 '
ms.openlocfilehash: 43141190d53cb3c32bd6645f850d2c6d9bb398b0
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2019
ms.locfileid: "37569297"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-microsoft-teams"></a>在 Microsoft Teams 中打开或关闭会议的进入和退出公告

当你在 Office 365 中设置音频会议时，你将获得一个音频会议网桥。 会议网桥可以包含一个或多个供大家用于拨入 Microsoft Teams 会议的电话号码。 
  
会议网桥负责应答使用电话拨入会议的用户的呼叫。 会议网桥通过来自会议自动助理的语音提示应答呼叫者，然后根据你的设置，可以播放通知、让呼叫者录制其姓名以及设置 PIN 安全。 将向 Microsoft Teams 会议组织者提供一个 PIN，如果组织者无法使用 Microsoft Teams 应用启动会议，可以使用该 PIN 启动会议。 但你可以设置不需要使用 PIN 即可启动会议。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a>设置会议加入选项

![](media/teams-logo-30x30.png) **使用 microsoft 团队管理中心**显示 microsoft 团队徽标的图标

1. 在左侧导航中，转到“**会议**” > “**会议网桥**”。 

2. 在“**会议网桥**”页面顶部，单击“**网桥设置**”。 

3. 在“**网桥设置**”窗格中，启用或禁用“**会议进入和退出通知**”。 默认情况下，此选项处于选中状态。 如果你将其取消选中，则当有人进入或离开会议时，已加入会议的用户不会收到通知。
    
4. 在“**进入/退出公告类型**”下，选择“**姓名或电话号码**”或“**声音**”。
    
5. 如果你选择“**姓名或电话号码**”，请启用或禁用“**要求呼叫者在加入会议之前录制其姓名**”。
    
6. 单击“**保存**”。

## <a name="want-to-know-more-about-windows-powershell"></a>想要了解有关 Windows PowerShell 的详细信息？

Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为什么要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
有关 Windows PowerShell 的详细信息，请参阅 [Microsoft Teams PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)了解详细信息。
  
## <a name="related-topics"></a>相关主题

[音频会议常见问题](audio-conferencing-common-questions.md)
