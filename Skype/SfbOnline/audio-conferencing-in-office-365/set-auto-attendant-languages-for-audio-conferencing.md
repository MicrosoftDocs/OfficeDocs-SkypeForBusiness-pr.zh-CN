---
title: 设置音频会议自动助理语言
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
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 请参阅如何选择音频会议号码的音频会议自动助理语言。
ms.openlocfilehash: c4461f61ce05afedc2663a3e5b61d37370394cd4
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="set-auto-attendant-languages-for-audio-conferencing"></a>设置音频会议自动助理语言

当用户加入会议时，业务和 Microsoft 团队的 Skype 音频会议自动助理可以通过多种不同的语言问候音频呼叫者。
  
选择一种主要语言和高达四种辅助语言。 将首先使用您之前设置的主要语言和自动助理将使用的辅助语言，以便您选择。 
  
> [!NOTE]
>  您可以在仅限国内音频访问电话号码配置语言。
  
## <a name="set-the-conferencing-auto-attendant-languages"></a>设置会议自动助理语言

![团队-徽标-30x30.png](../images/teams-logo-30x30.png) **使用的 Microsoft 团队和 Skype 的业务管理中心**

1. 在左侧导航窗格中，转到**会议** > **会议桥**。

2. 选择音频会议电话号码，从列表中，并在页面顶部，单击**编辑**。

3. 在右侧窗格中，选择所需的默认语言和任何备用语言。 
 
    > [!NOTE]
    > 列出默认和备用语言支持。 在其中选择这些列表中的顺序将向呼叫者显示的语言的顺序。 

4. 单击“**应用**”。

![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **for Business 联机使用 Skype**

您必须是[Office 365 全局管理员](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)或[Skype 针对业务管理员](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)才能执行此步骤。
    
1. 在**业务管理中心的 Skype**，在左侧导航窗格中，转到**音频会议**，然后单击**Microsoft 桥**。
    
2. 选择音频会议电话号码，从列表中，并在操作窗格中，单击**设置语言**。 
    
3. 在**设置语言**页上，单击**主要语言**列表，以查看可用的语言的完整列表。 如果需要请单击每个**辅助语言**列表选择辅助语言。
    
    > [!NOTE]
    > [!注释] 则会显示所支持的主要和辅助语言。 在其中选择这些列表中的顺序将向呼叫者显示的语言的顺序。 
  
4. 单击" **保存**"。
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="want-else-should-i-know"></a>还需了解哪些信息？

- 若要进行音频会议，请参阅支持的语言的列表，请参阅[音频会议支持的语言](audio-conferencing-supported-languages.md)。
    
- 专用的而不是为共享的电话号码，可以设置语言。
    
- 若要查看的国家/地区内使用为提供程序的 Microsoft Office 365 中的音频会议位于列表，请参阅[音频会议的电话号码](phone-numbers-for-audio-conferencing.md)。
    
## <a name="want-to-use-windows-powershell"></a>要使用 Windows PowerShell？

自动执行此步骤，您可以使用[集 CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617689)和[Get CsOnlineDialInConferencingLanguagesSupported](https://go.microsoft.com/fwlink/?LinkId=617684) cmdlet。
  
若要了解详细信息，请参阅[使用 Windows PowerShell，可以执行的业务 Online 管理任务的常见 Skype](https://go.microsoft.com/fwlink/?LinkId=525038)
  
## <a name="related-topics"></a>相关主题

[试用或购买 Office 365 中的音频会议](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
