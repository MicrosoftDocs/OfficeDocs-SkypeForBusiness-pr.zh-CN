---
title: 设置音频会议自动助理语言
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
description: 了解如何为音频会议号码选择音频会议自动助理语言Microsoft Teams。
ms.openlocfilehash: e96ebaff3c14dc9c7f09ceea63de7bec2d409758
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2021
ms.locfileid: "58731971"
---
# <a name="set-auto-attendant-languages-for-audio-conferencing-in-microsoft-teams"></a>在 Microsoft Teams 中设置音频会议自动助理语言

音频会议自动助理Microsoft Teams呼叫者加入会议时，可以使用多种语言问候音频呼叫者。
  
选择一种主要语言和最多四种辅助语言。 首先将使用你设置的主要语言，然后自动助理将按你选择的顺序使用辅助语言。 
  
> [!NOTE]
>  你只能更改"专用"类别的音频会议号码的语言。 无法更改共享音频会议号码的语言。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="set-the-conferencing-auto-attendant-languages"></a>设置会议自动助理语言

![一个图标，显示Microsoft Teams徽标。](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**

1. 在左侧导航中，转到“**会议**” > “**会议网桥**”。

2. 从 **列表中选择** 专用音频会议电话号码，在页面顶部单击"编辑 **"。** 只能更改专用音频会议号码的语言。 只有当 **选择** 专用音频会议号码时，才显示"编辑"选项。

3. 在右侧窗格中，选择需要的默认语言和任何备用语言。 
 
    > [!NOTE]
    > 将列出支持的默认语言和备用语言。 在列表中选择它们的顺序将是向呼叫者显示的语言顺序。 

4. 单击“**保存**”。

    
## <a name="want-else-should-i-know"></a>还需了解哪些信息？

- 若要查看音频会议支持的语言列表，请参阅[音频会议支持的语言](/SkypeForBusiness/audio-conferencing-in-office-365/audio-conferencing-supported-languages)。
    
- 语言可以设置为专用，但不能设置为共享电话号码。
    
- 若要查看使用 Microsoft 作为提供商的 Microsoft 365 或 Office 365 提供音频会议的国家/地区列表，请参阅音频电话[号码](phone-numbers-for-audio-conferencing-in-teams.md)。
    
## <a name="want-to-use-windows-powershell"></a>想要使用 Windows PowerShell？

有关详细信息[，Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps)参考。
  
## <a name="related-topics"></a>相关主题

[尝试或购买音频会议Microsoft 365或Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)