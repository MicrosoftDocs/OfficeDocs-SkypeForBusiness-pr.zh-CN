---
title: 添加、更改、删除紧急位置
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
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: '了解如何为组织添加、更改或删除紧急位置。 '
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 4d9c7c56b4e2b2fd14f703d51b4c07cfc173dfa3
ms.sourcegitcommit: 197debacdcd1f7902f6e16940ef9bec8b07641af
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2021
ms.locfileid: "60634851"
---
# <a name="add-change-or-remove-an-emergency-location-for-your-organization"></a>添加、 更改或删除您的组织紧急地点

无论使用[PSTN 连接](pstn-connectivity.md)选项，都可以选择"Microsoft 呼叫计划连接"接线员呼叫"或"直接路由"紧急位置可以与 &mdash; &mdash; 电话号码相关联。

但是，根据 PSTN 连接选项，管理紧急位置和位置要求可能有所不同。 有关详细信息，请参阅 [管理紧急呼叫](what-are-emergency-locations-addresses-and-call-routing.md)。

本文介绍如何为组织添加、更改或删除紧急位置。 

本文适用于 Microsoft 呼叫计划、连接和直接路由。

在安全管理中心或 PowerShell 中Microsoft Teams组织的紧急位置。

要分配紧急位置，用户、电话号码和紧急位置全部需要位于同一国家/地区。 有关详细信息，请参阅 [为用户分配或更改紧急位置](assign-change-emergency-location-user.md)。
  
## <a name="add-an-emergency-location"></a>添加紧急位置

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

1. 在管理中心的左侧导航Microsoft Teams，单击 **"位置**  >  **""紧急地址"。**
2. 单击“**添加**”。
3. 输入位置的名称和说明。
4. 选择国家/地区，然后输入地址。

   > [!NOTE]
   > 在比利时、法国、德国、爱尔兰、荷兰以及西班牙，必须了解，若要在 Microsoft 365 中成功激活电话号码，在紧急位置设置的地址（用于获取号码）必须与电话号码的区号匹配。

5. 如果找不到地址，并且你想要手动编辑地址，请打开"手动 **编辑地址"。**
6. 单击“**保存**”。

### <a name="using-powershell"></a>使用 PowerShell

请参阅 [New-CsOnlineLisCivicAddress](/powershell/module/skype/new-csonlineliscivicaddress)。
    
## <a name="change-an-emergency-location"></a>更改紧急位置

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

1. 在管理中心的左侧导航Microsoft Teams，单击 **"位置**  >  **""紧急地址"。**
2. 在列表中，选择要更改的位置，然后单击"编辑 **"。**
3. 进行您需要的更改。
4. 单击“**保存**”。

> [!NOTE]
> 只有当地址未经过验证时，才能更改位置的地址信息。 如果地址已经过验证，并且你需要更改地址，请删除该位置，然后使用正确的地址创建新位置。

### <a name="using-powershell"></a>使用 PowerShell

请参阅 [Set-CsOnlineLisCivicAddress](/powershell/module/skype/set-csonlineliscivicaddress)。
    
## <a name="remove-an-emergency-location"></a>删除紧急位置

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

1. 在管理中心的左侧导航Microsoft Teams，单击 **"位置**  >  **""紧急地址"。**
2. 在列表中，选择要删除的位置，然后单击"删除 **"。**

### <a name="using-powershell"></a>使用 PowerShell

请参阅 [Remove-CsOnlineLisCivicAddress](/powershell/module/skype/remove-csonlineliscivicaddress)。

## <a name="related-topics"></a>相关主题

- [管理紧急呼叫](what-are-emergency-locations-addresses-and-call-routing.md)
- [在组织中添加、更改或删除紧急位置的地点](add-change-remove-emergency-place-organization.md)
- [管理你的组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)
- [紧急呼叫条款和条件](./emergency-calling-terms-and-conditions.md)