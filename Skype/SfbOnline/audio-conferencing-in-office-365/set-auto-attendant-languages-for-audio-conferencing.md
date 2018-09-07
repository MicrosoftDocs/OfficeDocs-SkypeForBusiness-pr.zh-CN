---
title: 在 Skype for Business Online 中设置音频会议自动助理语言
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26d73dda-ab26-4af4-8aec-d17f3479ae50
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 请参阅如何在 Skype for Business Online 中为音频会议号码选择音频会议自动助理语言。
ms.openlocfilehash: 70313648f04b05e622ddb34e871ff1b303ac02a7
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23864982"
---
# <a name="set-auto-attendant-languages-for-audio-conferencing-in-skype-for-business-online"></a>在 Skype for Business Online 中设置音频会议自动助理语言

> [!Note]
> 有关在 Microsoft Teams 中设置自动助理语言的信息，请参阅 [在 Microsoft Teams 中设置音频会议自动助理语言](/MicrosoftTeams/set-auto-attendant-languages-for-audio-conferencing-in-teams)。

Skype for Business 的音频会议自动助理可以在加入会议时以多种不同语言向呼叫者播放问候语。
  
选择一种主要语言和最多四种辅助语言。 自动助理将优先使用设置的主要语言，随后按照选择的顺序使用辅助语言。 
  
> [!NOTE]
>  只能在国内音频访问电话号码上配置语言。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-conferencing-auto-attendant-languages"></a>设置会议自动助理语言

你必须是[Office 365 全局管理员](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)或 [Skype for Business 管理员](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)才能执行此步骤。
    
1. 在 **Skype for Business 管理中心** 中的左侧导航中，转到 **音频会议** ，然后单击 **Microsoft 网桥** 。
    
2. 从列表中选择音频会议电话号码，然后在操作窗格中单击 **设置语言** 。 
    
3. 在 **设置语言** 页面上，单击 **主要语言** 列表以查看可用语言的完整列表。 如果需要，单击每种 **辅助语言** 列表以选择辅助语言。
    
    > [!NOTE]
    > 则会显示所支持的主要语言和辅助语言。 在列表中选择它们的顺序将是向呼叫者显示的语言顺序。 
  
4. 单击 **保存** 。
    
## <a name="want-else-should-i-know"></a>还需了解哪些信息？

- 若要查看音频会议支持的语言列表，请参阅[音频会议支持的语言](/MicrosoftTeams/audio-conferencing-supported-languages)。
    
- 语言可以设置为专用，但不能设置为共享电话号码。
    
- 若要查看在 Office 365 中使用 Microsoft 作为提供程序的音频会议可用的国家/地区列表，请参阅[音频会议的电话号码](phone-numbers-for-audio-conferencing.md)。
    
## <a name="want-to-use-windows-powershell"></a>想要使用 Windows PowerShell？

为自动执行此操作，可以使用 [Set-CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617689) 和 [Get-CsOnlineDialInConferencingLanguagesSupported](https://go.microsoft.com/fwlink/?LinkId=617684) cmdlet 。
  
若要了解更多信息，请参阅 [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
  
## <a name="related-topics"></a>相关主题

[试用或购买 Office 365 中的音频会议](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
