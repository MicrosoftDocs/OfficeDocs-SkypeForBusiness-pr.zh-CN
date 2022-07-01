---
title: 在 Teams 中管理消息传递策略
ms.author: mabond
author: mkbond007
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
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.messagingpolicies.overview
- seo-marvel-apr2020
description: 了解消息传送策略以及如何在 Teams 中使用它们来控制聊天消息传送。
ms.openlocfilehash: f74ae28176f147d768e8e551ac07d1bcf189836b
ms.sourcegitcommit: 472e46b6eb907f41920516616683a61f0fc6f741
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/30/2022
ms.locfileid: "66563960"
---
# <a name="manage-messaging-policies-in-teams"></a>在 Teams 中管理消息传递策略

<!--- Add zone marker here--->

消息传送策略用于控制哪些聊天和频道消息传送功能可供 [用户 (所有者和成员在 Microsoft Teams 中) ](assign-roles-permissions.md) 。 可以使用自动创建或创建和分配自定义消息传送策略的全局 (组织范围的默认) 策略。

除非创建并分配自定义策略，否则组织中的用户将自动获取全局策略。 编辑全局策略中的设置，或创建并分配一个或多个自定义策略来打开或关闭所需的功能。

> [!NOTE]
> 若要确保在策略更改后同步，某些实例可能需要重新启动。 

## <a name="create-a-custom-messaging-policy"></a>创建自定义消息传送策略

1. 在 Microsoft Teams 管理中心的左侧导航中，转到 **消息传送策略**。
2. 选择“**添加**”。
3. 输入策略的名称和说明。
4. 选择想要的设置。
5. 选择“**保存**”。

例如，你希望确保未删除或更改发送的消息。 创建名为“保留已发送消息”的新自定义策略并关闭以下设置：

- 所有者可以删除已发送的消息
- 用户可以删除已发送的消息
- 用户可以编辑已发送的消息

然后将策略分配给用户。

## <a name="edit-a-messaging-policy"></a>编辑消息传送策略

可以编辑全局策略和创建的任何自定义策略。

1. 在 Microsoft Teams 管理中心的左侧导航中，转到 **消息传送策略**。
2. 通过单击策略名称的左侧选择策略，然后选择 **“编辑”**。
3. 在此处根据需要进行更改。
4. 选择“**保存**”。

## <a name="assign-a-custom-messaging-policy-to-users"></a>向用户分配自定义消息传送策略

[!INCLUDE [assign-policy](includes/assign-policy.md)]

用户一次只能分配一个消息策略。

> [!NOTE]
> 如果已将它分配给用户，则无法删除该策略。 必须首先为所有受影响的用户指定不同的策略，然后才能删除原来的策略。

<!--- End zone marker here--->

## <a name="messaging-policy-settings"></a>消息策略设置

下面是可以配置的消息传送策略设置。

- **所有者可以删除已发送的消息**  使用此设置可让所有者删除用户发送的频道消息或帖子。
- **删除已发送的消息** 使用此设置可让用户删除他们在聊天中发送的消息。
- **删除聊天** 使用此设置可让用户删除他们在聊天中发送的消息。
- **编辑已发送的消息** 使用此设置可让用户编辑他们在聊天中发送的消息。
- **读取收据** 读取收据允许在收件人以 1：1 读取其邮件时通知聊天邮件的发件人，并让 20 人或更少的人进行群聊。 消息读取回执不确定地删除了是否已读取消息，并改善了团队通信。 电子数据展示报告中不会捕获读取回执。  
    - **用户控制** 这意味着用户可以决定是想要读取收据打开还是关闭。 应用中的默认设置为 ON。 然后，用户可以将其关闭。
    - **为所有人打开** 这意味着租户中的每个人都将拥有启用的功能，并且没有关闭该功能的选项。 **为所有人** 设置使用 On 时，为整个租户设置收据的唯一方法是， (名为“全局 (组织范围的默认) ”的默认策略 (整个租户仅有一个消息传送策略) 或让租户中的所有消息传送策略对收据使用相同的设置。 当已读回执功能启用为“**面向所有人打开**”时，该功能最有效。
    - **为所有人关闭** 这意味着该功能已禁用，并且租户中没有人具有读取收据，也无法打开它。
<a name="bkchat"> </a>

- **聊天**  如果希望组织中的用户能够使用 Teams 应用与其他人聊天，请启用此设置。
- *在对话中使用 Giphy** 如果启用 Giphys，用户可以在与其他人的聊天对话中包括 Giphys。 Giphy 是一个联机数据库和搜索引擎，允许用户搜索和共享动画 GIF 文件。 为每个 Giphy 分配一个内容分级。 除了启用此设置外，还需要启用 [可选连接体验](/deployoffice/privacy/manage-privacy-controls#policy-setting-for-optional-connected-experiences) 以允许 Giphys 参与对话。
- **Giphy 内容分级**
  - **无限制** 这意味着无论内容分级如何，用户都可以在聊天中插入任何 Giphy。
  - **温和**  这意味着你的用户将能够在聊天中插入 Giphys，但会适度限制成人内容。
  - **严格**  这意味着你的用户将能够在聊天中插入 Giphys，但严格限制为成人内容。
- **对话中的 Memes** 如果打开 Memes，用户可以在与其他人的聊天对话中包括 Memes。
- **对话中的贴纸** 如果启用此功能，用户可以将贴纸包含在与其他人的聊天对话中。
- **URL 预览** 使用此设置在消息中打开或关闭自动 URL 预览。
- **翻译消息** 启用此设置可让用户自动将 Teams 消息转换为由 Microsoft 365 或Office 365的个人语言设置指定的语言。
- **邮件的沉浸式阅读器** 启用此设置以允许用户在 Microsoft 沉浸式阅读器 中查看消息。 沉浸式阅读器是一种学习工具，提供全屏阅读体验，以提高文本的可读性。
- **使用优先级通知发送紧急消息** 如果启用此功能，用户可以使用 [优先级通知](https://support.microsoft.com/article/mark-a-message-as-important-or-urgent-in-teams-ea99d5b6-1317-4550-8d75-86ff14cd4462)发送消息。 优先级通知每隔 2 分钟通知用户 20 分钟，或直到收件人选取并读取标记为 *紧急* 的消息。 此功能增加了及时执行消息的可能性。 发送紧急消息后，无法编辑该消息。
- **创建语音消息**
  > [!Important]
  > 电子数据展示报告中不会捕获音频消息。
  - **允许在聊天和频道中使用** 这意味着用户可以在聊天和频道中留下音频消息。
  - **仅允许在聊天中使用** 这意味着用户可以在聊天中留下音频消息，但不能在频道中保留音频消息。
  - **未启用** 这意味着用户无法在聊天或频道中创建音频消息。  
- **在移动设备上，显示最近聊天上方的收藏频道** 启用此设置可将收藏频道移动到移动设备屏幕的顶部，以便用户无需滚动即可找到它们。
- **从群组聊天中删除用户** 打开此设置，让用户从群聊中删除其他用户。 此功能使你可以继续与一小群人聊天，而不会丢失聊天历史记录。
- **文本预测** 启用此设置，让用户获取聊天消息的文本预测。
- **建议的答复**  打开此设置，为聊天消息启用建议的答复。
- **聊天权限角色** 使用此设置定义用户的监督聊天角色。 深入了解如何 [的聊天](supervise-chats-edu.md)。
- **具有完全聊天权限的用户可以删除任何消息** 使用此设置可让具有完全权限的用户删除任何组或会议聊天消息。

> [!NOTE]
> 其中一些设置（例如使用 Giphys）也可以由团队所有者在团队级别以及由频道所有者在专用或共享频道级别进行配置。

### <a name="related-topics"></a>相关主题

- [在 Teams 中为用户和组分配策略](assign-policies-users-and-groups.md)
- [在 Microsoft Teams 中分配团队所有者和成员](assign-roles-permissions.md)
