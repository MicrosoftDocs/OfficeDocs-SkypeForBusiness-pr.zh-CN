---
title: 添加、更改、删除紧急位置的位置
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: 了解如何为组织添加、更改或删除紧急位置。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 5421ff4e73d93c12244b3419342110b419f1b500
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/20/2022
ms.locfileid: "68614185"
---
# <a name="add-change-or-remove-a-place-for-an-emergency-location-in-your-organization"></a>在组织中添加、更改或删除紧急位置的地点

根据组织中物理位置的数量，可以为建筑物、楼层和办公室添加 *位置* ，以创建更具体的紧急位置。

但是，根据 PSTN 连接选项，管理紧急位置和位置要求的方式可能会有所不同。 有关详细信息，请参阅 [“管理紧急呼叫](what-are-emergency-locations-addresses-and-call-routing.md)”。

本文介绍如何为组织添加、更改或删除紧急位置的位置。

本文适用于 Microsoft 通话套餐、运营商连接、Teams Phone Mobile 和直接路由。

在 Microsoft Teams 管理中心或使用 PowerShell 管理组织的紧急位置。
  
## <a name="add-a-place-to-an-emergency-location"></a>将位置添加到紧急位置

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

1. 在 Microsoft Teams 管理中心的左侧导航中，单击 **“位置** > **紧急”地址**。
2. 在列表中，单击要为其添加位置的位置的名称。
3. 在 **“位置”** 选项卡上，单击 **“添加**”。
4. 输入地名，然后单击“ **应用**”。

### <a name="using-powershell"></a>使用 PowerShell

请参阅 [New-CsOnlineLisLocation](/powershell/module/skype/new-csonlinelislocation)。
    
## <a name="change-a-place-for-an-emergency-location"></a>更改紧急位置的位置

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

1. 在 Microsoft Teams 管理中心的左侧导航中，单击 **“位置** > **紧急”地址**。
2. 在列表中，单击要更改位置的位置的名称。
3. 在 **“位置** ”选项卡上，选择要更改的位置，然后单击 **“编辑**”。
4. 更新位置信息，然后单击“ **应用**”。

### <a name="using-powershell"></a>使用 PowerShell

请参阅 [Set-CsOnlineLisLocation](/powershell/module/skype/set-csonlinelislocation)。
    
## <a name="remove-a-place-from-an-emergency-location"></a>从紧急位置删除位置

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

1. 在 Microsoft Teams 管理中心的左侧导航中，单击 **“位置** > **紧急”地址**。
2. 在列表中，单击要删除位置的位置的名称。
3. 在 **“位置** ”选项卡上，选择要删除的位置，然后单击 **“删除**”。

### <a name="using-powershell"></a>使用 PowerShell

请参阅 [Remove-CsOnlineLisLocation](/powershell/module/skype/remove-csonlinelislocation)。
    
## <a name="related-topics"></a>相关主题

- [管理紧急呼叫](what-are-emergency-locations-addresses-and-call-routing.md)
- [为你的组织添加、更改或删除紧急位置](add-change-remove-emergency-location-organization.md)
- [管理组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)
- [紧急呼叫条款和条件](./emergency-calling-terms-and-conditions.md)