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
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 管理员可以控制组织者在其会议中使用免费电话号码的情况。
ms.openlocfilehash: 6fd415575110f9c6ae1dcf7b4fc006213a23cedd
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/07/2019
ms.locfileid: "30464393"
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

1. 在左侧导航窗格中，单击**用户**，然后选择从可用的用户列表的用户。

2. 在“**音频会议**”旁边，单击“**编辑**”。

3. 将**包含在会议请求此用户从免费电话号码**设置为**关闭**。 

4. 单击“**保存**”。 

 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
 
**使用 PowerShell**  

有关详细信息，请参阅 [Microsoft Teams PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)。
