---
title: 为用户分配或更改紧急位置
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
description: 在本文中，你将了解如何为你的组织中的用户分配或更改紧急位置。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 096e2dead1ede4f9769dafd85dfac23d6c44f399
ms.sourcegitcommit: 000515147632c6278bcda4505a1038014dda8e2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "44232473"
---
# <a name="assign-or-change-an-emergency-location-for-a-user"></a>为用户分配或更改紧急位置

设置呼叫计划时，您需要为每个电话号码或用户分配紧急地点。 在欧洲国家，当您从 Office 365 获取电话号码时，或将电话号码转移到 Office 365 时，紧急位置将与电话号码相关联。 在美国，紧急位置与分配给用户的电话号码相关联。 如果分配的用户移动到新位置，则可以更改紧急地址。 有关紧急地址和位置的详细信息，请参阅[管理紧急呼叫](what-are-emergency-locations-addresses-and-call-routing.md)。
  
若要了解如何获取呼叫计划以及成本，请参阅[团队附加许可](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。

你可以在 Microsoft 团队管理中心或通过使用 PowerShell 为用户分配或更改紧急位置。

## <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

1. 在 Microsoft 团队管理中心的左侧导航中，单击 "**语音**  >  **电话号码**"。

2. 在 "**电话号码**" 页面上，选择列表中的一个用户号码，然后单击 "**编辑**"。

3. 在 "**编辑**" 窗格的 "**紧急位置**" 下，执行下列操作之一：

   - 若要分配紧急位置，请搜索，然后选择紧急位置。

   - 若要更改已分配给用户的紧急位置，请单击 " **X** " 以删除现有位置，然后搜索并选择要分配的位置。

4. 单击“**保存**”。

## <a name="using-powershell"></a>使用 PowerShell

请参阅[设置-CsOnlineVoiceUser](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser)。 

    
## <a name="related-topics"></a>相关主题

- [管理紧急电话](what-are-emergency-locations-addresses-and-call-routing.md)
- [为你的组织添加、更改或删除紧急位置](add-change-remove-emergency-location-organization.md)
- [在组织中添加、更改或删除紧急位置的地点](add-change-remove-emergency-place-organization.md)
- [为用户分配或更改紧急位置的地点](assign-change-emergency-place-user.md)
- [管理你的组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)
- [紧急呼叫条款和条件](/microsoftteams/emergency-calling-terms-and-conditions)
- [Teams PowerShell 概览](teams-powershell-overview.md)
