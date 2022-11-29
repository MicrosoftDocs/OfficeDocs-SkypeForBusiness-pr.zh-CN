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
description: 了解消息传送策略以及如何在 Teams 中控制聊天消息传送。
ms.openlocfilehash: 83ee815651a0e08dc01d25639570c69f03edc588
ms.sourcegitcommit: e9718ad7e23317d490b238b3801267cb2e6b26e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2022
ms.locfileid: "69176679"
---
# <a name="manage-messaging-policies-in-teams"></a>在 Teams 中管理消息传递策略

<!--- Add zone marker here--->

消息策略用于控制哪些聊天和频道消息传递功能可供[用户在 Microsoft Teams 中)  (所有者和成员](assign-roles-permissions.md)使用。 可以使用自动创建的全局 (组织范围的默认) 策略，也可以创建和分配自定义消息传递策略。

除非创建并分配自定义策略，否则组织中的用户将自动获取全局策略。 编辑全局策略中的设置，或者创建并分配一个或多个自定义策略以打开或关闭所需的功能。

> [!NOTE]
> 若要确保在策略更改后同步，某些实例可能需要重新启动。 

## <a name="create-a-custom-messaging-policy"></a>创建自定义消息传递策略

1. 在 Microsoft Teams 管理中心的左侧导航栏中，转到 **“消息策略**”。
2. 选择“**添加**”。
3. 输入策略的名称和说明。
4. 选择想要的设置。
5. 选择“**保存**”。

例如，需要确保不会删除或更改已发送的消息。 创建名为“保留已发送邮件”的新自定义策略，并关闭以下设置：

- 所有者可以删除已发送的消息
- 用户可以删除已发送的消息
- 用户可以编辑发送的消息

然后将策略分配给用户。

## <a name="edit-a-messaging-policy"></a>编辑消息传递策略

可以编辑全局策略和创建的任何自定义策略。

1. 在 Microsoft Teams 管理中心的左侧导航栏中，转到 **“消息策略**”。
2. 通过单击策略名称的左侧选择策略，然后选择 **“编辑”**。
3. 在此处根据需要进行更改。
4. 选择“**保存**”。

## <a name="assign-a-custom-messaging-policy-to-users"></a>向用户分配自定义消息传递策略

[!INCLUDE [assign-policy](includes/assign-policy.md)]

一次只能为用户分配一个消息传递策略。

> [!NOTE]
> 如果已将它分配给用户，则无法删除该策略。 必须首先为所有受影响的用户指定不同的策略，然后才能删除原来的策略。

<!--- End zone marker here--->

## <a name="messaging-policy-settings"></a>消息传送策略设置

下面是可以配置的消息传送策略设置。

- **所有者可以删除已发送的消息**  使用此设置可让所有者删除用户发送的频道消息或帖子。
- **删除已发送的消息** 使用此设置可让用户删除他们在聊天中发送的消息。
- **编辑已发送的消息** 使用此设置可让用户编辑他们在聊天中发送的消息。
- **已读回执** 通过已读回执，当收件人以 1：1 和 20 人或更少的群组聊天方式阅读聊天邮件时，可以通知聊天邮件的发件人。 邮件已读回执消除了有关是否阅读消息的不确定性，并改进了团队沟通。 电子数据展示报告中不会捕获已读回执。  
    - **用户控制** 这意味着用户可以决定是打开还是关闭已读回执。 应用中的默认设置为“打开”。 然后，用户可以将其关闭。
    - **已为所有人打开** 这意味着租户中的每个人都将具有“打开”功能，而没有将其关闭的选项。 使用 **“对所有人** 启用”设置时，为整个租户设置回执的唯一方法是 (名为“全局 (组织范围默认) ”的默认策略) ，或者让租户中的所有消息传送策略对回执使用相同的设置。 当已读回执功能启用为“**面向所有人打开**”时，该功能最有效。
    - **已关闭所有人** 这意味着该功能已禁用，租户中没有任何人已读回执，也无法将其打开。
<a name="bkchat"> </a>

- **聊天**  如果希望组织中的用户能够使用 Teams 应用与其他人聊天，请启用此设置。
- **与组聊天** 用户可以开始与通讯组、启用邮件的安全组和 365 个组Microsoft聊天。
- *在对话中使用 Giphy** 如果打开 Giphys，用户可以在与其他人的聊天对话中包含 Giphys。 Giphy 是一个在线数据库和搜索引擎，允许用户搜索和共享动态 GIF 文件。 为每个 Giphy 分配内容分级。 除了启用此设置外，还需要启用 [可选连接体验](/deployoffice/privacy/manage-privacy-controls#policy-setting-for-optional-connected-experiences) ，以允许 Giphys 参与对话。
- **Giphy 内容分级**
  - **无限制** 这意味着，无论内容分级如何，用户都可以在聊天中插入任何 Giphy。
  - **温和**  这意味着，你的用户将能够插入聊天中的 Giphys，但会受到成人内容的适度限制。
  - **严格**  这意味着，你的用户将能够插入聊天中的 Giphys，但会严格限制成人内容。
- **对话中的 Meme** 如果启用 Meme，用户可以在与其他人的聊天对话中包含 Meme。
- **对话中的贴纸** 如果启用此功能，用户可以在与其他人的聊天对话中包含贴纸。
- **URL 预览** 使用此设置可打开或关闭邮件中的自动 URL 预览。
- **翻译消息** 打开此设置可让用户自动将 Teams 消息翻译为Microsoft 365 或 Office 365的个人语言设置指定的语言。
- **消息的沉浸式阅读器** 打开此设置可让用户在 Microsoft 沉浸式阅读器 中查看邮件。 沉浸式阅读器是一种学习工具，可提供全屏阅读体验，以提高文本的可读性。
- **使用优先级通知发送紧急消息** 如果启用此功能，用户可以使用 [优先级通知](https://support.microsoft.com/article/mark-a-message-as-important-or-urgent-in-teams-ea99d5b6-1317-4550-8d75-86ff14cd4462)发送消息。 优先级通知每 2 分钟通知一次，持续 20 分钟或直到收件人选取并阅读标记为 *紧急* 的邮件。 此功能增加了及时处理消息的可能性。 发送紧急消息后，无法对其进行编辑。
- **创建语音消息**
  > [!Important]
  > 在电子数据展示报告中不会捕获音频消息。
  - **允许在聊天和频道中** 这意味着用户可以在聊天和频道中留下音频消息。
  - **仅允许在聊天中** 这意味着用户可以在聊天中留下音频消息，但不能在频道中留下。
  - **未启用** 这意味着用户无法在聊天或频道中创建音频消息。  
- **在移动设备上，在最近聊天的上方显示收藏频道** 启用此设置可将收藏夹频道移动到移动设备屏幕顶部，以便用户无需滚动即可找到它们。
- **从群组聊天中删除用户** 打开此设置可让用户从群组聊天中删除其他用户。 此功能允许你继续与一小部分人聊天，而不会丢失聊天历史记录。
- **文本预测** 启用此设置可让用户获取聊天消息的文本预测。
- **建议的答复**  打开此设置以启用聊天消息的建议答复。
- **聊天权限角色** 使用此设置可定义用户的监督聊天角色。 深入了解如何 [的聊天](supervise-chats-edu.md)。
- **具有完全聊天权限的用户可以删除任何消息** 使用此设置可让具有完全权限的用户删除任何组或会议聊天消息。
- **视频消息** 如果希望组织中的用户能够使用 Teams 应用向聊天中的其他人发送视频消息，请启用此设置。

> [!NOTE]
> 其中一些设置（如使用 Giphys）也可以由团队所有者在团队级别以及频道所有者在专用或共享频道级别进行配置。

### <a name="related-topics"></a>相关主题

- [将策略分配给 Teams 中的用户和组](assign-policies-users-and-groups.md)
- [在 Microsoft Teams 中分配团队所有者和成员](assign-roles-permissions.md)
