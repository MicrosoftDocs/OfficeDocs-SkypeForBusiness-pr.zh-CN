---
title: 设置音频会议的 PIN 长度
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
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
description: 了解 PIN 的长度和要求的参数，并了解如何为 Microsoft Teams 中的会议设置长度。
ms.openlocfilehash: e589a550eba48401612e183200e54f678f9890c4
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2022
ms.locfileid: "67641953"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-microsoft-teams"></a>在 Microsoft Teams 中设置音频会议的 PIN 长度

为 Microsoft Teams 设置音频会议时，你将获得音频会议网桥。 会议网桥可以包含一个或多个电话号码。 设置的电话号码将包含在 Microsoft Teams 应用的会议邀请中。
  
音频会议网桥负责应答使用电话拨入会议的用户的呼叫。 它通过自动助理的语音提示回答呼叫者，然后，根据你的设置，可以播放通知，并要求呼叫者记录其姓名。 **Microsoft 网桥设置** 允许您更改会议通知和会议加入体验的设置，并设置会议组织者使用的 PIN 的长度。 如果会议组织者无法使用 Microsoft Teams 应用加入会议，则使用 PIN 启动会议。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a>设置 PIN 长度

使用 Microsoft Teams 管理中心：

1. 在左侧导航中，转到“**会议**” > “**会议网桥**”。

2. 在“**会议网桥**”页面顶部，单击“**网桥设置**”。

3. 在“ **桥设置”** 窗格的 **PIN 长度** 下，选择 PIN 所需的数字数。

4. 单击“**保存**”。

> [!NOTE]
> [!注释] PIN 与会议 ID 不同。 会议 ID 由呼叫者在加入会议时使用。 它们用于标识会议。 PIN 用于对作为会议组织者的呼叫者进行身份验证。

## <a name="want-to-know-more-about-pin-settings"></a>想要了解有关 PIN 设置的详细信息？

- PIN 可以是 4 到 12 位数字;默认值为 5。 在创建 PIN 时只能使用数字。 不能使用字母和特殊字符。

- 仅当 Microsoft Teams 用户尚未启动会议时，会议组织者才需要 PIN。 如果每个人都是拨号进入会议，则会议组织者需要 PIN 才能启动会议。

- PIN 安全设置适用于与 Microsoft 网桥相关联的所有电话号码。它们将应用于使用与给定网桥相关联的电话号码的所有会议。

## <a name="want-to-know-more-about-windows-powershell"></a>想要了解有关 Windows PowerShell 的详细信息？

Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。 借助Windows PowerShell，可以使用单个管理点来管理 Microsoft 365 或 Office 365，以便在需要执行多个任务时简化日常工作。 若要开始使用 Windows PowerShell，请参阅下列主题：

- [为什么要使用 Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [使用 Windows PowerShell 管理 Microsoft 365 或Office 365的最佳方法](/previous-versions//dn568025(v=technet.10))

有关 Windows PowerShell 的详细信息，请参阅 [Microsoft Teams PowerShell 参考](/powershell/module/teams/?view=teams-ps)了解详细信息。

## <a name="related-topics"></a>相关主题

[尝试或购买 Microsoft 365 for Microsoft Teams 中的音频会议](try-or-purchase-audio-conferencing-in-office-365-for-teams.md)
