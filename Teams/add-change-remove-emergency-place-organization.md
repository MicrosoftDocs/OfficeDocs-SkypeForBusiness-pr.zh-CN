---
title: 添加、更改、删除紧急位置的位置
author: cichur
ms.author: v-cichur
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
description: 了解如何在 Microsoft Teams 管理中心为组织添加、更改或删除紧急位置。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 50343fbd1d16694e46afafe53114f2dde4b7b150
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121500"
---
# <a name="add-change-or-remove-a-place-for-an-emergency-location-in-your-organization"></a>在组织中添加、更改或删除紧急位置的地点

根据组织中物理位置的数量，您可以为建筑物、楼层和办公室添加位置，以创建更具体的紧急位置。 有关详细信息 [，请参阅管理](what-are-emergency-locations-addresses-and-call-routing.md) 紧急呼叫。
  
若要了解如何获取通话计划及其费用，请参阅 [Teams 附加许可](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。

在 Microsoft Teams 管理中心或 PowerShell 中管理组织的紧急位置。
  
## <a name="add-a-place-to-an-emergency-location"></a>向紧急位置添加位置

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

1. 在 Microsoft Teams 管理中心的左侧导航栏中，单击 **"位置**  >  **""紧急地址"。**
2. 在列表中，单击要添加位置的位置的名称。
3. 在"**位置"选项卡** 上，单击"**添加"。**
4. 输入地点名称，然后单击"应用 **"。**

### <a name="using-powershell"></a>使用 PowerShell

请参阅[New-CsOnlineLisLocation。](/powershell/module/skype/new-csonlinelislocation)
    
## <a name="change-a-place-for-an-emergency-location"></a>更改紧急位置的位置

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

1. 在 Microsoft Teams 管理中心的左侧导航栏中，单击 **"位置**  >  **""紧急地址"。**
2. 在列表中，单击要更改其位置的位置的名称。
3. 在"**位置**"选项卡上，选择要更改的位置，然后单击"编辑 **"。**
4. 更新地点信息，然后单击"应用 **"。**

### <a name="using-powershell"></a>使用 PowerShell

请参阅[Set-CsOnlineLisLocation。](/powershell/module/skype/set-csonlinelislocation)
    
## <a name="remove-a-place-from-an-emergency-location"></a>从紧急位置删除位置

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

1. 在 Microsoft Teams 管理中心的左侧导航栏中，单击 **"位置**  >  **""紧急地址"。**
2. 在列表中，单击要删除位置的位置的名称。
3. 在"**位置**"选项卡上，选择要删除的位置，然后单击"删除 **"。**

### <a name="using-powershell"></a>使用 PowerShell

请参阅[Remove-CsOnlineLisLocation。](/powershell/module/skype/remove-csonlinelislocation)
    
## <a name="related-topics"></a>相关主题

- [在组织中添加、更改或删除紧急位置的地点](add-change-remove-emergency-place-organization.md)
- [管理你的组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)
- [紧急呼叫条款和条件](./emergency-calling-terms-and-conditions.md)