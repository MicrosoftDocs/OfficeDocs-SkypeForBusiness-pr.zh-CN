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
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: 了解如何为组织添加、更改或删除紧急位置。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 23eb549592c8ead6983253d1a228020f3851e1a7
ms.sourcegitcommit: 179713dd2b22736c0d63060a6351eb69ec4abff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2022
ms.locfileid: "68551486"
---
# <a name="add-change-or-remove-an-emergency-location-for-your-organization"></a>添加、 更改或删除您的组织紧急地点

无论选择哪种 [PSTN 连接选项](pstn-connectivity.md) ，都可选择&mdash;Microsoft 呼叫计划、操作员连接、Teams Phone Mobile 或直接路由&mdash;紧急位置与电话号码相关联。

但是，根据 PSTN 连接选项，管理紧急位置和位置要求的方式可能会有所不同。 有关详细信息，请参阅 [“管理紧急呼叫](what-are-emergency-locations-addresses-and-call-routing.md)”。

本文介绍如何为组织添加、更改或删除紧急位置。 

本文适用于 Microsoft 通话套餐、运营商连接、Teams Phone Mobile 和直接路由。

在 Microsoft Teams 管理中心或使用 PowerShell 管理组织的紧急位置。

若要分配紧急位置，用户、电话号码和紧急位置都需要位于同一国家/地区。 有关详细信息，请参阅 [为用户分配或更改紧急位置](assign-change-emergency-location-user.md)。
  
## <a name="add-an-emergency-location"></a>添加紧急位置

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

1. 在 Microsoft Teams 管理中心的左侧导航中，单击 **“位置** > **紧急”地址**。
2. 单击“**添加**”。
3. 输入位置的名称和说明。
4. 选择国家或地区，然后输入地址。

   > [!NOTE]
   > 在比利时、法国、德国、爱尔兰、荷兰和西班牙，重要的是要了解，要成功激活 Microsoft 365 中的电话号码，在紧急位置设置的地址（用于获取号码）必须与电话号码的区号匹配。

5. 如果找不到该地址，并且要手动编辑地址，请 **手动打开“编辑地址**”。
6. 单击“**保存**”。

### <a name="using-powershell"></a>使用 PowerShell

请参阅 [New-CsOnlineLisCivicAddress](/powershell/module/skype/new-csonlineliscivicaddress)。
    
## <a name="change-an-emergency-location"></a>更改紧急位置

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

1. 在 Microsoft Teams 管理中心的左侧导航中，单击 **“位置** > **紧急”地址**。
2. 在列表中，选择要更改的位置，然后单击 **“编辑**”。
3. 进行所需的更改。
4. 单击“**保存**”。

> [!NOTE]
> 只有在未验证地址时，才能更改位置的地址信息。 如果地址已验证，并且需要更改地址，请删除该位置，然后创建具有正确地址的新位置。

### <a name="using-powershell"></a>使用 PowerShell

请参阅 [Set-CsOnlineLisCivicAddress](/powershell/module/skype/set-csonlineliscivicaddress)。
    
## <a name="remove-an-emergency-location"></a>删除紧急位置

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

1. 在 Microsoft Teams 管理中心的左侧导航中，单击 **“位置** > **紧急”地址**。
2. 在列表中，选择要删除的位置，然后单击 **“删除**”。

### <a name="using-powershell"></a>使用 PowerShell

请参阅 [Remove-CsOnlineLisCivicAddress](/powershell/module/skype/remove-csonlineliscivicaddress)。

## <a name="related-topics"></a>相关主题

- [管理紧急呼叫](what-are-emergency-locations-addresses-and-call-routing.md)
- [在组织中添加、更改或删除紧急位置的地点](add-change-remove-emergency-place-organization.md)
- [管理组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)
- [紧急呼叫条款和条件](./emergency-calling-terms-and-conditions.md)