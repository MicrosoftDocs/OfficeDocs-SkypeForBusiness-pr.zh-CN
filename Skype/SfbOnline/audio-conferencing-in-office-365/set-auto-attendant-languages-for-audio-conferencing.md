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
ms.openlocfilehash: 93b6ea917c7f79747273366893efc47a22b89bb2
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2020
ms.locfileid: "44163893"
---
# <a name="set-auto-attendant-languages-for-audio-conferencing-in-skype-for-business-online"></a>在 Skype for Business Online 中设置音频会议自动助理语言

> [!Note]
> 有关在 Microsoft Teams 中设置自动助理语言的信息，请参阅 [在 Microsoft Teams 中设置音频会议自动助理语言](/MicrosoftTeams/set-auto-attendant-languages-for-audio-conferencing-in-teams)。

Skype for Business 的音频会议自动助理可以在加入会议时以多种不同语言向呼叫者播放问候语。
  
Choose one primary language and up to four secondary languages. The primary language that you set will be used first and the secondary languages will be used by the auto-attendant in order that you select. 
  
> [!NOTE]
>  只能更改专用类别的音频会议号码的语言。 无法更改共享音频会议号码的语言。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-conferencing-auto-attendant-languages"></a>设置会议自动助理语言

您必须是[全局管理员](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)或[Skype for business 管理员](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)才能执行此步骤。
    
1. 在**Skype For business 管理中心**的左侧导航中，转到 "**旧版门户**"。 在旧版门户中，选择 "**音频会议**"，然后单击 " **Microsoft bridge**"。
    
2. 从列表中选择音频会议电话号码，然后在 "操作" 窗格中，单击 "**设置语言**"。 仅可以更改专用音频会议号码的语言。  
    
3. 在 "**设置语言**" 页面上，单击 "**主要语言**" 列表以查看可用语言的完整列表。 如果需要，请单击每个**次要语言**列表以选择 "辅助语言"。
    
    > [!NOTE]
    > [!注释] 则会显示所支持的主要和辅助语言。 在列表中选择它们的顺序将是向呼叫方提供的语言的顺序。 
  
4. 单击“**保存**”。
    
## <a name="want-else-should-i-know"></a>还需了解哪些信息？

- 若要查看音频会议支持的语言列表，请参阅[音频会议支持的语言](/MicrosoftTeams/audio-conferencing-supported-languages)。
    
- 语言可以设置为专用，但不能设置为共享电话号码。
    
- 若要查看 Microsoft 365 或 Office 365 中使用 Microsoft 作为提供商的音频会议的国家/地区的列表，请参阅[音频会议的电话号码](phone-numbers-for-audio-conferencing.md)。
    
## <a name="want-to-use-windows-powershell"></a>想要使用 Windows PowerShell？

若要自动执行此步骤，你可以使用[set-csonlinedialinconferencingservicenumber](https://go.microsoft.com/fwlink/?LinkId=617689)和[get-csonlinedialinconferencinglanguagessupported](https://go.microsoft.com/fwlink/?LinkId=617684) cmdlet。
  
若要了解详细信息，请参阅[使用 Windows PowerShell 执行常见的 Skype For Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
  
## <a name="related-topics"></a>相关主题

[在 Microsoft 365 或 Office 365 中试用或购买音频会议](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
