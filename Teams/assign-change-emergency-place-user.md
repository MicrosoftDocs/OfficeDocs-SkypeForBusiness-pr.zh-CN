---
title: 为用户分配、更改紧急位置的位置
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
description: 本文介绍了如何为贵组织的用户分配或更改紧急位置。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ff328f07a69676a4dbaf1c1370d9e225e9d67810
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120824"
---
# <a name="assign-or-change-the-place-for-an-emergency-location-for-a-user"></a>为用户分配或更改紧急位置的位置

将电话号码分配给用户时，每个活动电话号码必须具有关联的紧急位置。  (当您在 Office 365 中收到电话号码或转移电话号码时，您将关联该地址。) 当您将号码与紧急位置关联时，您还可以添加一个位置，在物理位置中提供更精确的位置。 一个地方可以是用户所在的楼层、建筑侧或办公室号码。 对于给定的紧急位置，你可以有无限数量的地点，并且如果用户移动到其他办公室或建筑物，你可以更改位置。 例如，如果用户从 34 楼移到 35 楼。
  
若要了解如何获取通话套餐及其费用，请参阅 [Teams 附加许可](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。
  
可以在 Microsoft Teams 管理中心或 PowerShell 中为用户分配或更改紧急位置的位置。

## <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

1. 在 Microsoft Teams 管理中心的左侧导航栏中，单击"**语音**  >  **电话号码"。**

2. 在"**电话号码"** 页面上，单击"号码 **"** 选项卡，在列表中选择用户号码，然后单击"编辑 **"。**

3. 在" **编辑** "窗格的 **"紧急位置"下**，执行下列操作之一：

    - 若要分配位置，请搜索位置或位置，然后在搜索结果中选择该位置。

    - 若要更改已分配给用户的位置，请单击 **"X"** 删除现有位置，搜索，然后选择要分配的位置。

4. 根据是否要向用户发送包含其电话号码信息的电子邮件，请关闭或打开包含 **电话号码信息的电子邮件用户**。 默认情况下，此选项为"打开"。

5. 单击“**应用**”。

## <a name="using-powershell"></a>使用 PowerShell

请参阅[Set-CsOnlineLisLocation。](/powershell/module/skype/set-csonlinelislocation)
    
## <a name="related-topics"></a>相关主题

- [管理紧急呼叫](what-are-emergency-locations-addresses-and-call-routing.md)
- [为你的组织添加、更改或删除紧急位置](add-change-remove-emergency-location-organization.md)
- [在组织中添加、更改或删除紧急位置的地点](add-change-remove-emergency-place-organization.md)
- [为用户分配或更改紧急位置](assign-change-emergency-location-user.md)
- [管理你的组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)
- [紧急呼叫条款和条件](./emergency-calling-terms-and-conditions.md)