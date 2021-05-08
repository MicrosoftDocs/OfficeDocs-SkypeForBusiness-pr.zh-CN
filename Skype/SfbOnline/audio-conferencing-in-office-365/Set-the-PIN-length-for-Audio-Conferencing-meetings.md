---
title: 在 Skype for Business Online 中设置音频会议的 PIN 长度
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 了解 PIN 的长度和要求的参数，并参阅如何在 Skype for Business 中设置会议的长度。
ms.openlocfilehash: 2e4e1d087ad6e0f91d034c6a5abe513e8b3aab01
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238597"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-skype-for-business-online"></a>在 Skype for Business Online 中设置音频会议的 PIN 长度

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


> [!NOTE]
> 有关在 Microsoft Teams 中设置 PIN 长度的信息，请参阅[在 Microsoft Teams 中设置音频会议的 PIN 长度](/en-us/MicrosoftTeams/Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams)。

为 Skype for Business 设置音频会议时，你将看到音频会议网桥。 会议网桥可以包含一个或多个电话号码。 你设置的电话号码将包括在 Skype for Business 应用的会议邀请中。
  
音频会议网桥负责应答使用电话拨入会议的用户的呼叫。 它通过自动助理的语音提示应答呼叫者，然后根据你的设置，可以播放通知并要求呼叫者录制其姓名。 **Microsoft 网桥** 设置允许您更改会议通知和会议加入体验的设置，并设置会议组织者使用的 PIN 的长度。 如果会议组织者无法使用 Skype for Business 应用加入会议，则会使用 PIN 来启动会议。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a>设置 PIN 长度
 
1. 在 **Skype for Business管理** 中心的 左侧导航中，转到"**音频会议**  >  **Microsoft 网桥设置"。**
    
2. 在 **"安全** PIN 长度"下，选择 PIN 的位数，然后单击  >  "保存 **"。**
    
> [!NOTE]
> [!注释] PIN 与会议 ID 不同。 会议 ID 由呼叫者在加入会议时使用。 它们用于标识会议。 PIN 用于对作为会议组织者的呼叫者进行身份验证。 

## <a name="want-to-know-more-about-pin-settings"></a>想要了解有关 PIN 设置的信息？

- PIN 可以是 4 到 12 个数字;默认值为 5。 在创建 PIN 时只能使用数字。 不能使用字母和特殊字符。
    
- 只有当用户尚未启动会议时，Skype for Business才需要 PIN。 如果每个人都是拨号进入会议，则会议组织者需要 PIN 才能启动会议。
    
- PIN 安全设置适用于与 Microsoft 网桥相关联的所有电话号码。它们将应用于使用与给定网桥相关联的电话号码的所有会议。 
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 进行管理吗？

- 为节省时间或自动执行此操作，可以使用 [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings) cmdlet。
    
- 若要将 PIN 的数字位数设置为 8： `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`
    
- Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。 使用Windows PowerShell，可以使用Microsoft 365管理Office 365管理点，在有多个任务需要执行时简化日常工作。 若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为何需要将 Microsoft 365 或 Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [使用 Microsoft 365 Office 365 管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell管理中心相比，Microsoft 365在速度、简单性和工作效率方面具有许多优势，例如，一次为许多用户更改设置时。 请在以下主题中了解这些优点： 
    
  - [Windows PowerShell 和 Skype for Business Online 简介](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    [使用 Windows PowerShell 管理 Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > [!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。
  
## <a name="see-also"></a>另请参阅

[尝试或购买音频会议Microsoft 365或Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
