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
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 请参阅如何在 Skype for Business Online 中为音频会议号码选择音频会议自动助理语言。
ms.openlocfilehash: f7b7357d38941ba8d7e1f586f32daa8e02b29012
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882206"
---
# <a name="set-auto-attendant-languages-for-audio-conferencing-in-skype-for-business-online"></a>在 Skype for Business Online 中设置音频会议自动助理语言

> [!Note]
> 有关在 Microsoft Teams 中设置自动助理语言的信息，请参阅 [在 Microsoft Teams 中设置音频会议自动助理语言](/MicrosoftTeams/set-auto-attendant-languages-for-audio-conferencing-in-teams)。

Skype for Business 的音频会议自动助理可以在加入会议时以多种不同语言向呼叫者播放问候语。
  
选择一种主要语言和最多四种辅助语言。 将首先使用您之前设置的主要语言和自动助理将使用的辅助语言，以便您选择。 
  
> [!NOTE]
>  您可以在仅限国内音频访问电话号码配置语言。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-conferencing-auto-attendant-languages"></a>设置会议自动助理语言

你必须是[Office 365 全局管理员](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)或 [Skype for Business 管理员](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)才能执行此步骤。
    
1. 在**业务管理中心的 Skype**，在左侧导航窗格中，转到**音频会议**，然后单击**Microsoft 桥**。
    
2. 选择音频会议电话号码，从列表中，并在操作窗格中，单击**设置语言**。 
    
3. 在**设置语言**页上，单击**主要语言**列表，以查看可用的语言的完整列表。 如果需要请单击每个**辅助语言**列表选择辅助语言。
    
    > [!NOTE]
    > [!注释] 则会显示所支持的主要和辅助语言。 在其中选择这些列表中的顺序将向呼叫者显示的语言的顺序。 
  
4. 单击" **保存**"。
    
## <a name="want-else-should-i-know"></a>还需了解哪些信息？

- 若要查看音频会议支持的语言列表，请参阅[音频会议支持的语言](/MicrosoftTeams/audio-conferencing-supported-languages)。
    
- 语言可以设置为专用，但不能设置为共享电话号码。
    
- 若要查看在 Office 365 中使用 Microsoft 作为提供程序的音频会议可用的国家/地区列表，请参阅[音频会议的电话号码](phone-numbers-for-audio-conferencing.md)。
    
## <a name="want-to-use-windows-powershell"></a>想要使用 Windows PowerShell？

自动执行此步骤，您可以使用[集 CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617689)和[Get CsOnlineDialInConferencingLanguagesSupported](https://go.microsoft.com/fwlink/?LinkId=617684) cmdlet。
  
若要了解详细信息，请参阅[使用 Windows PowerShell，可以执行的业务 Online 管理任务的常见 Skype](https://go.microsoft.com/fwlink/?LinkId=525038)
  
## <a name="related-topics"></a>相关主题

[试用或购买 Office 365 中的音频会议](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
