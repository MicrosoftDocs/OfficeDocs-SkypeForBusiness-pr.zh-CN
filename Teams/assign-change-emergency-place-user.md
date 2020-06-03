---
title: 分配，为用户更改紧急位置的位置
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
description: 在本文中，你将了解如何为你的组织中的用户分配或更改紧急位置的位置。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 35f7dfe6572b7ef3dc76b6c224d206e2ee4f23a2
ms.sourcegitcommit: d8e05e66311725f8ff6d28011355129baeb305b3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/03/2020
ms.locfileid: "44539509"
---
# <a name="assign-or-change-the-place-for-an-emergency-location-for-a-user"></a>为用户分配或更改紧急位置的位置

为用户分配电话号码时，每个活动电话号码都必须有相关联的紧急位置。 （当您在 Office 365 中获取电话号码或转移电话号码时，您可以关联该地址。）将该号码与紧急位置相关联时，您还可以添加一个位置，以便在一个物理位置内提供更准确的位置。 地点可以是用户所在的楼层、建筑物翼形或办公室号码。 对于给定的紧急位置，您可以拥有无限数量的位置，如果用户移动到其他 office 或建筑物，则可以更改位置。 例如，如果用户从楼层34移动到地板35。
  
若要了解如何获取通话计划和费用，请参阅[团队附加许可](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。
  
你可以在 Microsoft 团队管理中心或通过使用 PowerShell 为用户分配或更改紧急位置的位置。

## <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

1. 在 Microsoft 团队管理中心的左侧导航中，单击 "**语音**  >  **电话号码**"。

2. 在 "**电话号码**" 页面上，单击 "**数字**" 选项卡，选择列表中的用户号码，然后单击 "**编辑**"。

3. 在 "**编辑**" 窗格的 "**紧急位置**" 下，执行下列操作之一：

    - 若要分配位置，请搜索位置或位置，然后在搜索结果中选择位置。

    - 若要更改已分配给用户的位置，请单击 " **X** " 以删除现有位置和位置，然后单击 "搜索"，然后选择要分配的位置。

4. 根据您是否想要使用电话号码信息向用户发送电子邮件，请关闭或打开**包含电话号码信息的电子邮件用户**。 默认情况下，此项处于打开状态。

5. 单击“**应用**”。

## <a name="using-powershell"></a>使用 PowerShell

请参阅[设置-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation)。
    
## <a name="related-topics"></a>相关主题

- [管理紧急电话](what-are-emergency-locations-addresses-and-call-routing.md)
- [为你的组织添加、更改或删除紧急位置](add-change-remove-emergency-location-organization.md)
- [在组织中添加、更改或删除紧急位置的地点](add-change-remove-emergency-place-organization.md)
- [为用户分配或更改紧急位置](assign-change-emergency-location-user.md)
- [管理你的组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)
- [紧急呼叫条款和条件](/microsoftteams/emergency-calling-terms-and-conditions)
