---
title: 添加、更改、删除紧急位置
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
description: '了解如何在 Microsoft Teams 管理中心为组织添加、更改或删除紧急位置。 '
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b918cbcbebf8edb2cd54d08e0e4a3177867fa623
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121520"
---
# <a name="add-change-or-remove-an-emergency-location-for-your-organization"></a>添加、 更改或删除您的组织紧急地点

紧急位置必须与电话号码相关联，但发生这种情况时可能因国家和地区而异。 例如，在美国，你需要在将电话号码分配给用户时关联紧急位置。 在英国，当你从 Microsoft 365 或 Office 365 获取电话号码或者从当前服务提供商转移电话号码时，你需要将紧急位置与电话号码关联。

无论你位于哪个国家/地区，都可以向紧急位置添加位置并删除紧急位置。 根据组织中物理位置的数量，你可以为建筑物、楼层和办公室创建位置。 请参阅 [管理紧急呼叫](what-are-emergency-locations-addresses-and-call-routing.md)。
  
若要了解如何获取通话计划及其费用，请参阅 [Teams 附加许可](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。

在 Microsoft Teams 管理中心或 PowerShell 中管理组织的紧急位置。
  
## <a name="add-an-emergency-location"></a>添加紧急位置

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

1. 在 Microsoft Teams 管理中心的左侧导航栏中，单击 **"位置**  >  **""紧急地址"。**
2. 单击“**添加**”。
3. 输入位置的名称和说明。
4. 选择国家/地区，然后输入地址。

   > [!NOTE]
   > 在比利时、法国、德国、爱尔兰、荷兰以及西班牙，必须了解，若要在 Microsoft 365 或 Office 365 中成功激活电话号码，紧急位置中设置的地址（用于获取号码）必须与电话号码的区号匹配。

5. 如果找不到地址，并且你想要手动编辑地址，请打开"手动 **编辑地址"。**
6. 单击“**保存**”。

### <a name="using-powershell"></a>使用 PowerShell

请参阅 [New-CsOnlineLisCivicAddress](/powershell/module/skype/new-csonlineliscivicaddress)。
    
## <a name="change-an-emergency-location"></a>更改紧急位置

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

1. 在 Microsoft Teams 管理中心的左侧导航栏中，单击 **"位置**  >  **""紧急地址"。**
2. 在列表中，选择要更改的位置，然后单击"编辑 **"。**
3. 进行您需要的更改。
4. 单击“**保存**”。

> [!NOTE]
> 只有当地址未经过验证时，才能更改位置的地址信息。 如果地址已经过验证，并且你需要更改地址，请删除该位置，然后使用正确的地址创建新位置。

### <a name="using-powershell"></a>使用 PowerShell

请参阅 [Set-CsOnlineLisCivicAddress](/powershell/module/skype/set-csonlineliscivicaddress)。
    
## <a name="remove-an-emergency-location"></a>删除紧急位置

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

1. 在 Microsoft Teams 管理中心的左侧导航栏中，单击 **"位置**  >  **""紧急地址"。**
2. 在列表中，选择要删除的位置，然后单击"删除 **"。**

### <a name="using-powershell"></a>使用 PowerShell

请参阅 [Remove-CsOnlineLisCivicAddress](/powershell/module/skype/remove-csonlineliscivicaddress)。

## <a name="related-topics"></a>相关主题

- [管理紧急呼叫](what-are-emergency-locations-addresses-and-call-routing.md)
- [在组织中添加、更改或删除紧急位置的地点](add-change-remove-emergency-place-organization.md)
- [管理你的组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)
- [紧急呼叫条款和条件](./emergency-calling-terms-and-conditions.md)