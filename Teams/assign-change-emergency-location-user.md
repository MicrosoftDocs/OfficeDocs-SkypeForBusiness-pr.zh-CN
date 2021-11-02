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
description: 本文介绍了如何为组织中用户分配或更改紧急位置。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: efe6b81961a4f7ca4eeb39e3f10b0c117cba7d6e
ms.sourcegitcommit: 197debacdcd1f7902f6e16940ef9bec8b07641af
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2021
ms.locfileid: "60634901"
---
# <a name="assign-or-change-an-emergency-location-for-a-user"></a>为用户分配或更改紧急位置

无论选择"Microsoft 呼叫计划["、"](pstn-connectivity.md)接线员连接"还是"直接路由"，都需要将紧急位置分配给每个电话号码或用户，而不考虑 PSTN &mdash; &mdash; 连接选项。

但是，你为用户管理和分配紧急位置可能有所不同，具体取决于 PSTN 连接选项。 有关详细信息，请参阅 [管理紧急呼叫](what-are-emergency-locations-addresses-and-call-routing.md)。

本文介绍如何为用户分配或更改紧急位置。 

本文适用于呼叫计划和运营商连接。
  
可以在管理中心或 PowerShell 中为Microsoft Teams分配或更改紧急位置。

## <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

1. 在管理中心的左侧导航Microsoft Teams，单击 **"语音电话**  >  **号码"。**

2. 在 **"电话"** 页上，单击"数字"选项卡，在列表中选择用户编号，然后单击"编辑 **"。**

3. 在" **编辑** "窗格的 **"紧急位置"下**，执行下列操作之一：

   - 若要分配紧急位置，请搜索并选择紧急位置。

   - 若要更改已分配给用户的紧急位置，请单击 **"X"** 删除现有位置，然后搜索并选择要分配的位置。

4. 根据是否要向用户发送包含其电话号码信息的电子邮件，请关闭或打开包含 **电话号码信息的电子邮件用户**。 默认情况下，此选项为"打开"。

5. 单击“**应用**”。

## <a name="using-powershell"></a>使用 PowerShell

请参阅[Set-CsOnlineVoiceUser。](/powershell/module/skype/set-csonlinevoiceuser) 

    
## <a name="related-topics"></a>相关主题

- [管理紧急呼叫](what-are-emergency-locations-addresses-and-call-routing.md)
- [为你的组织添加、更改或删除紧急位置](add-change-remove-emergency-location-organization.md)
- [为用户分配或更改紧急位置的地点](assign-change-emergency-place-user.md)
- [在组织中添加、更改或删除紧急位置的地点](add-change-remove-emergency-place-organization.md)
- [管理你的组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)
- [紧急呼叫条款和条件](./emergency-calling-terms-and-conditions.md)
