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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 请参阅如何在 Skype for Business Online 中为音频会议号码选择音频会议自动助理语言。
ms.openlocfilehash: 044d05ec8b67f1e7732140a90c47b0666568fafe241fe3a45f2d02c46824e903
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54326988"
---
# <a name="set-auto-attendant-languages-for-audio-conferencing-in-skype-for-business-online"></a>在 Skype for Business Online 中设置音频会议自动助理语言

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> 有关在 Microsoft Teams 中设置自动助理语言的信息，请参阅 [在 Microsoft Teams 中设置音频会议自动助理语言](/MicrosoftTeams/set-auto-attendant-languages-for-audio-conferencing-in-teams)。

Skype for Business 的音频会议自动助理可以在加入会议时以多种不同语言向呼叫者播放问候语。
  
选择一种主要语言和最多四种辅助语言。 首先将使用你设置的主要语言，自动助理将按你选择的顺序使用辅助语言。 
  
> [!NOTE]
>  你只能更改"专用"类别的音频会议号码的语言。 无法更改共享音频会议号码的语言。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-conferencing-auto-attendant-languages"></a>设置会议自动助理语言

只有全局[管理员或](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)Skype for Business[才能](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)执行此步骤。
    
1. 在Skype for Business **管理中心的** 左侧导航中，转到 **"旧门户"。** 进入旧门户后，选择"**音频会议"，** 然后单击 **"Microsoft 网桥"。**
    
2. 从列表中选择音频会议电话号码，在"操作"窗格中，单击"**设置语言"。** 只能更改专用音频会议号码的语言。  
    
3. 在"**设置语言**"页上，单击"主要语言"列表以查看可用语言的完整列表。 如果需要，请单击每个辅助 **语言** 列表以选择辅助语言。
    
    > [!NOTE]
    > [!注释] 则会显示所支持的主要和辅助语言。 在列表中选择它们的顺序将是向呼叫者显示的语言顺序。 
  
4. 单击“**保存**”。
    
## <a name="want-else-should-i-know"></a>还需了解哪些信息？

- 若要查看音频会议支持的语言列表，请参阅[音频会议支持的语言](/MicrosoftTeams/audio-conferencing-supported-languages)。
    
- 语言可以设置为专用，但不能设置为共享电话号码。
    
- 若要查看使用 Microsoft 作为提供商的 Microsoft 365 或 Office 365 提供音频会议的国家/地区列表，请参阅音频电话[号码](phone-numbers-for-audio-conferencing.md)。
    
## <a name="want-to-use-windows-powershell"></a>想要使用 Windows PowerShell？

若要自动执行此步骤，可以使用 [Set-CsOnlineDialInConferencingServiceNumber](/powershell/module/skype/Set-CsOnlineDialInConferencingServiceNumber) 和 [Get-CsOnlineDialInConferencingLanguagesSupported](/powershell/module/skype/Get-CsOnlineDialInConferencingLanguagesSupported) cmdlet。
  
有关详细信息，请参阅使用[Windows PowerShell 执行常见Skype for Business Online 管理任务](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
## <a name="related-topics"></a>相关主题

[尝试或购买音频会议Microsoft 365或Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
