---
title: 为用户分配或更改紧急位置
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
description: 本文介绍了如何为组织中用户分配或更改紧急位置。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7dd986085a8c42df34d6634cbadc6e96fdfb14ca
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102978"
---
# <a name="assign-or-change-an-emergency-location-for-a-user"></a>为用户分配或更改紧急位置

设置呼叫计划时，需要为每个电话号码或用户分配紧急位置。 在欧洲国家/地区，从 Microsoft 365 或 Office 365 获取紧急位置时，或者将电话号码转移到 Microsoft 365 或 Office 365 时，紧急位置与电话号码相关联。 在美国，紧急位置与分配给用户的电话号码相关联。 如果分配紧急地址的用户移动到新位置，则紧急地址可能会更改。 有关紧急地址和位置的信息，请参阅什么是紧急位置、地点和[呼叫路由？。](./what-are-emergency-locations-addresses-and-call-routing.md)
  
若要了解如何获取通话套餐及其费用，请参阅 [Teams 附加许可](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。
  
可以在 Microsoft Teams 管理中心或 PowerShell 中为用户分配或更改紧急位置。

## <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

1. 在 Microsoft Teams 管理中心的左侧导航栏中，单击"**语音**  >  **电话号码"。**

2. 在"**电话号码"** 页面上，单击"号码 **"** 选项卡，在列表中选择用户号码，然后单击"编辑 **"。**

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
- [在组织中添加、更改或删除紧急位置的地点](add-change-remove-emergency-place-organization.md)
- [为用户分配或更改紧急位置的地点](assign-change-emergency-place-user.md)
- [管理你的组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)
- [紧急呼叫条款和条件](./emergency-calling-terms-and-conditions.md)
- [Teams PowerShell 概览](teams-powershell-overview.md)