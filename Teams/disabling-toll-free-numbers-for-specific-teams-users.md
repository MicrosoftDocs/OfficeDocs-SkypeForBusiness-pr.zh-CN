---
title: 对特定 Teams 用户禁用免费电话号码
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
description: 管理员可以控制组织者在其会议中使用免费电话号码的情况。
ms.openlocfilehash: 7bc830529fc24a61be914998e923ad2d5288b7c5
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837262"
---
# <a name="disabling-toll-free-numbers-for-specific-teams-users"></a>对特定 Teams 用户禁用免费电话号码

如果组织在其 Microsoft 音频会议网桥中拥有免费电话号码，可以在特定的组织者的会议中允许或阻止其使用免费电话号码。  

默认方式，组织中的所有用户均启用免费电话号码，这意味着，这些号码，如果可用，参会者可使用它们参加会议。 如果不希望组织中的某些用户可以这样参会，可以通过免费电话号码启用控件限制特定用户在其会议中使用这些号码。 

当针对某设定组织者禁用免费电话号码时： 
 - 免费电话号码将不再包含在他或她的会议邀请中。 
 - 免费电话号码将不再在"查找本地号码"页上列出，该页面在他或她的会议邀请中被引用。 
 - 参会者如果拨组织的任何免费电话号码，都将无法参加该设定组织者的会议。 
 - 将自动重新安排该组织者的所有会议，并将从其删除免费电话号码。  

    > [!IMPORTANT]
    > 因此将向这些会议的所有参与者重新发送该组织者的所有电子邮件邀请。 

 - 参会者可以继续使用收费电话号码参加该组织者的会议。 

## <a name="disabling-toll-free-numbers-for-specific-users"></a>对特定用户禁用免费电话号码 

从**Microsoft 团队管理中心**：

1. 在左侧导航中，单击 "**用户**"，然后从可用用户列表中选择用户。

2. 在“**音频会议**”旁边，单击“**编辑**”。

3. 设置**包括来自此用户的会议请求中**的免费电话号码 **。** 

4. 单击“**保存**”。 

 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
 
**使用 PowerShell**  

有关详细信息，请参阅 [Microsoft Teams PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)。
