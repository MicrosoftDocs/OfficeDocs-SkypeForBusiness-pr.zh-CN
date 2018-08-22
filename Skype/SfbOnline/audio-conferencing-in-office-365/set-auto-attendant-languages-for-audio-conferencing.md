---
title: Skype 中的音频会议自动助理语言设置为业务 Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26d73dda-ab26-4af4-8aec-d17f3479ae50
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
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
description: 请参阅 how to 业务 online Skype 中选择音频会议号码的音频会议自动助理语言。
ms.openlocfilehash: 026a09290c6e008493784c0d883220e03d13559f
ms.sourcegitcommit: 6207b98e8395f6c640b61cfb3f6c85d96520e33b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2018
ms.locfileid: "22490512"
---
# <a name="set-auto-attendant-languages-for-audio-conferencing-in-skype-for-business-online"></a>Skype 中的音频会议自动助理语言设置为业务 Online

> [!Note]
> 有关自动助理语言设置中的 Microsoft 团队的信息，请参阅[设置中的 Microsoft 团队的音频会议自动助理语言](/MicrosoftTeams/set-auto-attendant-languages-for-audio-conferencing-in-teams)。

当用户加入会议时，for Business 的 Skype 音频会议自动助理可以通过多种不同的语言问候音频呼叫者。
  
选择一种主要语言和高达四种辅助语言。 将首先使用您之前设置的主要语言和自动助理将使用的辅助语言，以便您选择。 
  
> [!NOTE]
>  您可以在仅限国内音频访问电话号码配置语言。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-conferencing-auto-attendant-languages"></a>设置会议自动助理语言

您必须是[Office 365 全局管理员](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)或[Skype 针对业务管理员](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)才能执行此步骤。
    
1. 在**业务管理中心的 Skype**，在左侧导航窗格中，转到**音频会议**，然后单击**Microsoft 桥**。
    
2. 选择音频会议电话号码，从列表中，并在操作窗格中，单击**设置语言**。 
    
3. 在**设置语言**页上，单击**主要语言**列表，以查看可用的语言的完整列表。 如果需要请单击每个**辅助语言**列表选择辅助语言。
    
    > [!NOTE]
    > [!注释] 则会显示所支持的主要和辅助语言。 在其中选择这些列表中的顺序将向呼叫者显示的语言的顺序。 
  
4. 单击" **保存**"。
    
## <a name="want-else-should-i-know"></a>还需了解哪些信息？

- 若要进行音频会议，请参阅支持的语言的列表，请参阅[音频会议支持的语言](audio-conferencing-supported-languages.md)。
    
- 专用的而不是为共享的电话号码，可以设置语言。
    
- 若要查看的国家/地区内使用为提供程序的 Microsoft Office 365 中的音频会议位于列表，请参阅[音频会议的电话号码](phone-numbers-for-audio-conferencing.md)。
    
## <a name="want-to-use-windows-powershell"></a>要使用 Windows PowerShell？

自动执行此步骤，您可以使用[集 CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617689)和[Get CsOnlineDialInConferencingLanguagesSupported](https://go.microsoft.com/fwlink/?LinkId=617684) cmdlet。
  
若要了解详细信息，请参阅[使用 Windows PowerShell，可以执行的业务 Online 管理任务的常见 Skype](https://go.microsoft.com/fwlink/?LinkId=525038)
  
## <a name="related-topics"></a>相关主题

[试用或购买 Office 365 中的音频会议](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
