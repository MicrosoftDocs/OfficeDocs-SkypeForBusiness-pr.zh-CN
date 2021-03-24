---
title: 在 Teams 中管理消息传递策略
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.messagingpolicies.overview
- seo-marvel-apr2020
description: 本文介绍消息传送策略以及如何在 Teams 中控制聊天消息传送。
ms.openlocfilehash: f760fdf196bdeecf14e432445e619c968f66c081
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096116"
---
# <a name="manage-messaging-policies-in-teams"></a>在 Teams 中管理消息传递策略

<!--- Add zone marker here--->

消息传送策略用于控制哪些聊天和频道消息传递功能可供 Microsoft Teams ([所有者 ](assign-roles-permissions.md)) 成员使用。 可以使用自动创建的 (组织范围的默认) 策略，或者创建和分配自定义消息传送策略。

除非你创建并分配自定义策略，否则你组织中的用户将自动获取全局策略。 可以编辑全局策略中的设置，或者创建并分配一个或多个自定义策略以打开或关闭想要的功能。

## <a name="create-a-custom-messaging-policy"></a>创建自定义消息传送策略

1. 在 Microsoft Teams 管理中心的左侧导航栏中，转到"**消息策略"。**
2. 单击“**添加**”。
3. 输入策略的名称和说明。
4. 选择想要的设置。
5. 单击“**保存**”。

例如，假设你想要确保发送的邮件不会被删除或更改。 创建名为"保留已发送消息"的新自定义策略，并关闭以下设置：

- 所有者可以删除已发送的消息
- 用户可以删除已发送的消息
- 用户可以编辑已发送的消息

然后将策略分配给用户。

## <a name="edit-a-messaging-policy"></a>编辑消息策略

可以编辑全局策略和创建的任何自定义策略。 

1. 在 Microsoft Teams 管理中心的左侧导航栏中，转到"**消息策略"。**
2. 单击策略名称的左侧以选择用户，然后单击“**编辑**”。
3. 在此处根据需要进行更改。
4. 单击“**保存**”。

## <a name="assign-a-custom-messaging-policy-to-users"></a>向用户分配自定义消息传送策略

[!INCLUDE [assign-policy](includes/assign-policy.md)]

一次只能为用户分配一个消息传送策略。

> [!NOTE]
> 如果将用户分配到策略，则不能删除该策略。 必须先将不同的策略分配给所有受影响的用户，然后可以删除原始策略。

<!--- End zone marker here--->

## <a name="messaging-policy-settings"></a>消息策略设置

下面是可以配置的消息策略设置。

- **所有者可以删除已发送的消息**  使用此设置，让所有者删除用户在聊天中发送的消息。
- **用户可以删除已发送的消息** 使用此设置可让用户删除他们在聊天中发送的消息。
- **用户可以编辑已发送的消息** 使用此设置可让用户编辑他们在聊天中发送的消息。
- **已读回执** 阅读回执允许当收件人在 1：1 和群组聊天 20 人或更少时间阅读其消息时通知聊天消息的发送者。 消息已读回执会不确定地删除消息是否已阅读，并改进团队沟通。 请注意，电子数据展示报告不会捕获已读回执。  
    - **用户控制** 这意味着用户需要决定是打开还是关闭已读回执。 应用中的默认设置为"打开"。 然后，用户可以将其关闭。
    - **适用于所有人的打开** 这意味着租户中的每个人都将具有"打开"功能，没有关闭该功能的选项。 请注意，使用"针对所有人打开"设置时，设置整个租户的回执的唯一方法就是为整个租户只设置一个消息传送策略 (即名为"全局 (组织范围的默认值) ") ，或者让租户中所有消息传送策略对收据使用相同的设置。 当已读回执功能启用为“**面向所有人打开**”时，该功能最有效。
    - **为所有人关闭** 这意味着该功能已禁用，租户中没有任何用户具有已读回执，也不能将其打开。
<a name="bkchat"> </a>

- **聊天**  如果希望组织中用户能够使用 Teams 应用与其他用户聊天，请启用此设置。
- **在对话中使用 Giphy**  如果启用此功能，用户可以在与他人的聊天对话中包括 Giphy。 Giphy 是一个联机数据库和搜索引擎，允许用户搜索和共享动态 GIF 文件。 每个 Giphy 都分配有一个内容分级。 请注意，除了启用此设置外，还需要启用可选连接 [体验](/deployoffice/privacy/manage-privacy-controls#policy-setting-for-optional-connected-experiences) 以允许对话中的 Giphy。
- **Giphy 内容分级**
    - **无限制** 这意味着，无论内容评级如何，用户都能在聊天中插入任何 Giphy。
    - **中等**  这意味着你的用户将能够在聊天中插入 Giphy，但会适度限制成人内容。
    - **严格**  这意味着你的用户将能够在聊天中插入 Giphy，但将严格限制成人内容。
- **在对话中使用 Meme** 如果启用此功能，用户可以在与他人的聊天对话中包括 Meme。
- **在对话中使用贴纸** 如果启用此功能，用户可以在与他人的聊天对话中包括贴纸。
- **允许 URL 预览** 使用此设置可打开或关闭邮件中的自动 URL 预览。
- **允许用户翻译邮件** 打开此设置，让用户自动将 Teams 消息翻译成其 Microsoft 365 或 Office 365 个人语言设置指定的语言。
- **允许沉浸式阅读器查看消息** 打开此设置，让用户在 Microsoft 沉浸式阅读器中查看消息。 沉浸式阅读器是一种学习工具，可提供全屏阅读体验以提高文本可读性。
- **使用优先级通知发送紧急消息** 如果启用此功能，用户可以使用优先级通知 [发送消息](https://support.microsoft.com/article/mark-a-message-as-important-or-urgent-in-teams-ea99d5b6-1317-4550-8d75-86ff14cd4462)。 优先级通知每隔 2 分钟通知用户 20 分钟，或者直到收件人选取并阅读标记为紧急的邮件，从而最大程度地提高及时处理邮件的可能性。
- **音频消息创建** 
  > [!Important]
  > 电子数据展示报告不会捕获音频消息。
    - **在聊天和频道中允许** 这意味着用户可以在聊天和频道中留下音频消息。
    - **仅允许聊天** 这意味着用户可以在聊天中保留音频消息，但不能在频道中留下消息。
    - **已禁用** 这意味着用户无法在聊天或频道中创建音频消息。  
- **在移动设备上，显示最近聊天上方的收藏频道** 启用此设置，将收藏的频道移动到移动设备屏幕顶部，以便用户无需滚动查找它们。
- **允许用户从群组聊天中删除用户** 打开此设置，让用户从群组聊天中删除其他用户。 此功能允许你继续与一小组人员聊天，而不会丢失聊天历史记录。
- **启用建议的答复**  打开此设置，为聊天消息启用建议的答复。

> [!NOTE]
> 其中一些设置（例如使用 Giphys）也可由团队所有者在团队级别配置，在专用频道级别由专用频道所有者配置。

### <a name="related-topics"></a>相关主题

- [向 Teams 中的用户分配策略](assign-policies.md)
- [在 Microsoft Teams 中分配团队所有者和成员](assign-roles-permissions.md)