---
title: 设置音频会议自动助理语言
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
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
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 了解如何选择音频会议号码的音频会议自动助理语言。
ms.openlocfilehash: e7c4adb2129a737ec34e5641a9724bdab665cd23
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/03/2018
---
# <a name="set-auto-attendant-languages-for-audio-conferencing"></a>设置音频会议自动助理语言

Skype 业务和 Microsoft 小组音频会议自动助理可以上任之初即音频呼叫者以多种不同的语言时他们加入会议。
  
选择一种主要的语言，多达四种第二语言。 将首先使用您设置的主要语言和辅助语言将由自动助理，以便您选择。 
  
> [!NOTE]
>  在国内的音频访问电话号码，您可以配置语言。
  
## <a name="set-the-conferencing-auto-attendant-languages"></a>设置自动助理语言的会议

您必须是[Office 365 全局管理员](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)或[Skype 业务管理员](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)才能执行此步骤。
  
1. 使用你的工作或学校帐户登录 Office 365。
    
2. Go to the **Office 365 admin center** > **Skype for Business**.
    
3. 在**业务管理中心的 Skype**，在左边的导航中，转到**音频会议**，然后单击**Microsoft 桥**。
    
4. 从列表中，然后在操作窗格中选择的音频会议电话号码，请单击**设置语言**。 
    
5. 在**设置语言**页上，单击**主要语言**列表以查看可用语言的完整列表。 如果需要请单击每个**辅助语言**列表以选择第二种语言。
    
    > [!NOTE]
    > [!注释] 则会显示所支持的主要和辅助语言。 所选的这些列表中的顺序将向调用方提供的语言的顺序。 
  
6. 单击" **保存**"。
    
## <a name="want-else-should-i-know"></a>还需了解哪些信息？

- 以音频会议，请参阅受支持语言的列表，请参阅[音频会议支持的语言](audio-conferencing-supported-languages.md)。
    
- 语言设置为专用，但不适用于共享的电话号码。
    
- 若要查看可用的提供程序使用 Microsoft Office 365 中的音频会议是国家/地区的列表，请参阅[音频电话会议的电话号码](phone-numbers-for-audio-conferencing.md)。
    
## <a name="want-to-use-windows-powershell"></a>要使用 Windows PowerShell？

要自动完成此步骤，您可以使用[组 CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617689)和[Get CsOnlineDialInConferencingLanguagesSupported](https://go.microsoft.com/fwlink/?LinkId=617684) cmdlet。
  
若要了解详细信息，请参阅[使用 Windows PowerShell 做常用 Skype 业务联机管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
  
## <a name="related-topics"></a>相关主题

[试用或购买 Office 365 中的音频会议](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
