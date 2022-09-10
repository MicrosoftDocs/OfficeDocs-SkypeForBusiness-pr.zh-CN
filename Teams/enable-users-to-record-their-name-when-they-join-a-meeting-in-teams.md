---
title: 使用户能够记录会议的名称
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1d649328-ada7-422d-a074-d6da4da36970
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 了解如何启用或禁用用户在 Microsoft Teams 中加入会议时是否可以记录其姓名。
ms.openlocfilehash: 8d626437d1e7dd04ce8b4f91428bfe22cc3aeb43
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2022
ms.locfileid: "67641723"
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting-in-microsoft-teams"></a>在 Microsoft Teams 中让用户能够在加入会议时录制其姓名

在 Microsoft 365 或 Office 365 中设置音频会议时，你将收到电话号码和所谓的音频会议网桥。 会议网桥可以包含一个或多个电话号码，这些号码可以是专用或共享电话号码。
  
会议网桥负责应答使用电话拨入会议的用户的呼叫。 会议网桥使用来自自动助理的语音提示回答呼叫者，然后，根据他们的设置，可以播放通知，要求呼叫者记录其姓名，并为会议组织者设置 PIN 安全性。 将 PIN 提供给会议组织者，以允许他们开始会议。 然而，你也可以将其设置为无需 PIN 即可启动会议。

## <a name="set-whether-callers-should-record-their-name"></a>设置呼叫者是否应录制其姓名

使用 Microsoft Teams 管理中心：

1. 在左侧导航中，转到“**会议**” > “**会议网桥**”。

2. 在 **“会议桥** ”页的顶部，单击 **“桥”设置**。

3. 启用或禁用 **会议进入和退出通知**。

4. 如果启用通知，请在 **进入/退出公告类型** 下选择 **“姓名”或“电话号码**”，然后打开 **“询问呼叫者”，在加入会议之前记录其姓名。**

5. 单击“**保存**”。

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="want-to-know-more-about-windows-powershell"></a>想要了解有关 Windows PowerShell 的详细信息？

Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。 使用Windows PowerShell，可以使用单个管理点来管理 Microsoft 365 或 Office 365，以便在需要执行多个任务时简化日常工作。 若要开始使用 Windows PowerShell，请参阅下列主题：

- [为什么要使用 Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [使用 Windows PowerShell 管理 Office 365 的最佳方式](/previous-versions//dn568025(v=technet.10))

有关 Windows PowerShell 的详细信息，请参阅 [Microsoft Teams PowerShell 参考](/powershell/module/teams/?view=teams-ps)了解详细信息。
