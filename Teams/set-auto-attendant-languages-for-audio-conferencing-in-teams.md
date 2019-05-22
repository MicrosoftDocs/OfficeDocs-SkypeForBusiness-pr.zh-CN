---
title: 在 Microsoft Teams 中设置音频会议自动助理语言
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26d73dda-ab26-4af4-8aec-d17f3479ae50
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 了解如何在 Microsoft Teams 中针对音频会议号码选择音频会议自动助理语言。
ms.openlocfilehash: e99892ad42a8e7340558b8f0db7daa1da025777a
ms.sourcegitcommit: 30995da65ff6a9b33534c3818833cf0ae1952ab9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/22/2019
ms.locfileid: "34344247"
---
# <a name="set-auto-attendant-languages-for-audio-conferencing-in-microsoft-teams"></a>在 Microsoft Teams 中设置音频会议自动助理语言

Microsoft Teams 的音频会议自动助理可以在音频呼叫者加入会议时使用多种不同的语言向其问好。
  
可选择一种主要语言以及最多四种辅助语言。 自动助理将首先使用你设置的主要语言，然后按你选择的顺序使用辅助语言。 
  
> [!NOTE]
>  只能更改专用类别的音频会议号码的语言。 无法更改共享音频会议号码的语言。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="set-the-conferencing-auto-attendant-languages"></a>设置会议自动助理语言

![](media/teams-logo-30x30.png) **使用 microsoft 团队管理中心**显示 microsoft 团队徽标的图标

1. 在左侧导航中，转到“**会议**” > “**会议网桥**”。

2. 从列表中选择一个**专用**的音频会议电话号码, 然后在页面顶部, 单击 "**编辑**"。 仅可以更改专用音频会议号码的语言。 仅当选择了专用的音频会议号码时, 才会显示 "**编辑**" 选项。

3. 在右侧窗格中, 选择所需的默认语言和任何备用语言。 
 
    > [!NOTE]
    > 将列出受支持的默认语言和备用语言。 在列表中选择它们的顺序将是向呼叫方提供的语言的顺序。 

4. 单击“**保存**”。

    
## <a name="want-else-should-i-know"></a>还需了解哪些信息？

- 若要查看音频会议支持的语言列表，请参阅[音频会议支持的语言](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/audio-conferencing-supported-languages)。
    
- 语言可以设置为专用，但不能设置为共享电话号码。
    
- 若要查看在 Office 365 中使用 Microsoft 作为提供程序的音频会议可用的国家/地区列表，请参阅[音频会议的电话号码](phone-numbers-for-audio-conferencing-in-teams.md)。
    
## <a name="want-to-use-windows-powershell"></a>想要使用 Windows PowerShell？

有关详细信息, 请参阅[Microsoft 团队 PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)。
  
## <a name="related-topics"></a>相关主题

[试用或购买 Office 365 中的音频会议](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

