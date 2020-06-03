---
title: 添加、更改、删除紧急位置的位置
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
description: 了解如何在 Microsoft 团队管理中心中为你的组织添加、更改或删除紧急位置的位置。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 5ba712602ef2a966343282d4e467365f3c1c3329
ms.sourcegitcommit: d8e05e66311725f8ff6d28011355129baeb305b3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/03/2020
ms.locfileid: "44539429"
---
# <a name="add-change-or-remove-a-place-for-an-emergency-location-in-your-organization"></a>在组织中添加、更改或删除紧急位置的地点

根据您的组织中的物理位置数，您可以添加建筑物、楼层和办事处的位置，以创建更具体的紧急位置。 有关详细信息，请参阅[管理紧急电话](what-are-emergency-locations-addresses-and-call-routing.md)。
  
若要了解如何获取呼叫计划以及成本，请参阅[团队附加许可](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。

可在 Microsoft 团队管理中心或通过使用 PowerShell 管理你的组织的紧急位置。
  
## <a name="add-a-place-to-an-emergency-location"></a>将地点添加到紧急位置

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

1. 在 Microsoft 团队管理中心的左侧导航中，单击 "**位置**  >  **紧急地址**"。
2. 在列表中，单击要为其添加位置的位置的名称。
3. 在 "**位置**" 选项卡上，单击 "**添加**"。
4. 输入一个位置名称，然后单击 "**应用**"。

### <a name="using-powershell"></a>使用 PowerShell

请参阅[新-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/new-csonlinelislocation)。
    
## <a name="change-a-place-for-an-emergency-location"></a>更改紧急位置的位置

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

1. 在 Microsoft 团队管理中心的左侧导航中，单击 "**位置**  >  **紧急地址**"。
2. 在列表中，单击要更改位置的位置的名称。
3. 在 "**位置**" 选项卡上，选择要更改的位置，然后单击 "**编辑**"。
4. 更新位置信息，然后单击 "**应用**"。

### <a name="using-powershell"></a>使用 PowerShell

请参阅[设置-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation)。
    
## <a name="remove-a-place-from-an-emergency-location"></a>从紧急位置删除位置

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

1. 在 Microsoft 团队管理中心的左侧导航中，单击 "**位置**  >  **紧急地址**"。
2. 在列表中，单击要删除其位置的位置的名称。
3. 在 "**位置**" 选项卡上，选择要删除的位置，然后单击 "**删除**"。

### <a name="using-powershell"></a>使用 PowerShell

请参阅[删除-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelislocation)。
    
## <a name="related-topics"></a>相关主题

- [在组织中添加、更改或删除紧急位置的地点](add-change-remove-emergency-place-organization.md)
- [管理你的组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)
- [紧急呼叫条款和条件](/microsoftteams/emergency-calling-terms-and-conditions)
