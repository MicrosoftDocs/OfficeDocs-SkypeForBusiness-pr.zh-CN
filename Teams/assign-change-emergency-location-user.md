---
title: 为用户分配或更改紧急位置
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
description: 本文介绍如何为组织中的用户分配或更改紧急位置。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a43ca031b8787d62639e141c3f733acdb402f85a
ms.sourcegitcommit: 179713dd2b22736c0d63060a6351eb69ec4abff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2022
ms.locfileid: "68551646"
---
# <a name="assign-or-change-an-emergency-location-for-a-user"></a>为用户分配或更改紧急位置

无论 [选择 PSTN 连接选项](pstn-connectivity.md) 如何，都需要&mdash;为每个电话号码或用户分配 Microsoft 呼叫计划、运营商连接、Teams Phone Mobile 或直接路由&mdash;紧急位置。

但是，根据 PSTN 连接选项，为用户管理和分配紧急位置的方式可能会有所不同。 有关详细信息，请参阅 [“管理紧急呼叫](what-are-emergency-locations-addresses-and-call-routing.md)”。

本文介绍如何为用户分配或更改紧急位置。 

本文适用于通话套餐、运营商连接和 Teams Phone Mobile。
  
可以在 Microsoft Teams 管理中心或使用 PowerShell 为用户分配或更改紧急位置。

## <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

1. 在 Microsoft Teams 管理中心的左侧导航中，单击 **“语音** > **电话号码**”。

2. 在 **“电话号码** ”页上，单击 **“号码”** 选项卡，在列表中选择一个用户号，然后单击 **“编辑**”。

3. 在 **“编辑** ”窗格的 **“紧急位置**”下，执行下列操作之一：

   - 若要分配紧急位置，请搜索并选择紧急位置。

   - 若要更改已分配给用户的紧急位置，请单击 **X** 删除现有位置，然后搜索并选择要分配的位置。

4. 根据你是否要使用其电话号码信息向用户发送电子邮件，请关闭或打开 **Email用户的电话号码信息**。 默认情况下，此操作处于打开状态。

5. 单击“**应用**”。

## <a name="using-powershell"></a>使用 PowerShell

请参阅 [Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment)。 

    
## <a name="related-topics"></a>相关主题

- [管理紧急呼叫](what-are-emergency-locations-addresses-and-call-routing.md)
- [为你的组织添加、更改或删除紧急位置](add-change-remove-emergency-location-organization.md)
- [为用户分配或更改紧急位置的地点](assign-change-emergency-place-user.md)
- [在组织中添加、更改或删除紧急位置的地点](add-change-remove-emergency-place-organization.md)
- [管理组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)
- [紧急呼叫条款和条件](./emergency-calling-terms-and-conditions.md)
