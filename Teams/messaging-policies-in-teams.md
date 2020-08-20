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
description: 在本文中，你将了解消息策略以及如何用于控制 Teams 中的聊天消息。
ms.openlocfilehash: 0a548eee32fc196157b6a363dd0427b187e52112
ms.sourcegitcommit: 34f407a6a40317056005e3bf38ce58f792c04810
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814178"
---
# <a name="manage-messaging-policies-in-teams"></a>在 Teams 中管理消息传递策略

<!--- Add zone marker here--->

消息策略用于控制在 Microsoft Teams 中，用户 [有哪些聊天和频道消息功能可供 (所有者和成员使用) ](assign-roles-permissions.md) 消息功能。 可使用全局管理员 (应用于内部创建) 或分配自定义消息策略。

除非你创建并分配了自定义策略，你组织中的用户将自动获取全局策略。 可以编辑全局策略中的设置或创建并分配一个或多个自定义策略以启用或禁用所需功能。

## <a name="create-a-custom-messaging-policy"></a>创建自定义消息策略

1. 在 Microsoft Teams 管理中心的左侧导航 **中，转到"消息策略**"。
2. 单击“添加”****。
3. 输入策略的名称和说明。
4. 选择所需的设置。
5. 单击“**保存**”。

例如，您想要确保已发送的邮件未被删除或更改。 创建一个名为"保留已发送邮件"的新自定义策略并关闭以下设置：

- 所有者可以删除已发送的消息
- 用户可以删除已发送的消息
- 用户可以编辑已发送的消息

然后将策略分配给用户。

## <a name="edit-a-messaging-policy"></a>编辑消息策略

您可以编辑全局策略和您创建的任何自定义策略。 

1. 在 Microsoft Teams 管理中心的左侧导航 **中，转到"消息策略**"。
2. 单击策略名称左侧位置选择策略，然后单击 **"编辑"。**
3. 在此处进行所需的更改。
4. 单击“**保存**”。

## <a name="assign-a-custom-messaging-policy-to-users"></a>为用户分配自定义消息策略

[!INCLUDE [assign-policy](includes/assign-policy.md)]

一次只能为一个消息策略分配一个消息策略。

> [!NOTE]
> 如果用户已分配了策略，则无法将其删除。 必须先向所有受影响的用户分配不同的策略，然后才能删除原始策略。

<!--- End zone marker here--->

## <a name="messaging-policy-settings"></a>消息策略设置

下面是您可以配置的消息策略设置。

- **所有者可以删除已发送的消息**  使用此设置，所有者可以删除用户在聊天中发送的消息。
- **用户可以删除已发送的消息** 使用此设置，用户可以删除他们在聊天中发送的消息。
- **用户可以编辑已发送的消息** 使用此设置，用户可以编辑他们聊天中发送的消息。
- **已读回收** 通过"已读"收件人，可以收到聊天消息的发件人在 1：1 及小组聊天 20 人或更少的时间进行阅读。 邮件已读回收结果将在很大程度上取消统一读取消息，并改进团队沟通。 请注意，未在电子数据展示报告中捕获已读回收。  
    - **用户已控制** 这意味着用户决定是否要打开或关闭已读回据。 应用程序内的默认设置为"打开"。 然后，用户可以将其关闭。
    - **对所有人启用** 这意味着租户中的每个人都将提供该功能，而不提供将其关闭的选项。 请注意，当为所有 **人** 设置使用"开"时，为整个租户设置收据的测量方法是只有 (一个邮件策略："全局 (组织范围默认值) ") 或者在租户中拥有对收据设置所用的相同设置。 如果对每个人都启用此功能，"已读回据"功能最 **有效**。
    - **对每个人禁用** 这意味着该功能被禁用，租户中没有人已读回收，也不能开启该功能。
<a name="bkchat"> </a>

- **聊天**  如果你希望组织中的用户能够使用 Teams 应用与其他人聊天，请启用此设置。
- **在对话中使用 Giphy**  如果启用此选项，用户可以将 Giphy 信息包含在与他人的聊天中。 Giphy 是联机数据库和搜索引文，可供用户搜索和共享动时 GIF 文件。 为每个 Ipiphy 分配了一个内容分级。
- **Giphy 内容分级**
    - **没有限制** 这意味着无管内容分级如何，您的用户将能够在聊天中插入任何 Giphy。
    - **"中等"**  这意味着你的用户将能够在聊天中插入 Giphy，但将受成人内容的中等限制。
    - **"限制"**  这意味着你的用户将能够在聊天中插入 Giphy，但将限制在成人内容中。
- **在对话中使用 Meme** 如果启用此选项，用户可以将 Meme 用于与其他人进行聊天。
- **在对话中使用贴中** 如果启用此设置，用户可以将贴子信息包含在与其他人的聊天中。
- **允许 URL 预览** 使用此设置来打开或关闭邮件中的自动 URL 预览。
- **允许用户翻译邮件** 启用此设置，让用户可以将 Teams 消息自动翻译为由 Microsoft 365 或 Office 365 的个人语言设置指定的语言。
- **允许沉浸式阅读器查看邮件** 打开此设置以允许用户在 Microsoft 沉浸式阅读器中查看邮件。 沉浸式阅读器是一种学习工具，它提供了全屏阅读体验，提高文本的可读性。
- **使用优先级通知发送明绿消息** 如果启用此功能，用户可以使用优先级 [通知发送消息](https://support.microsoft.com/article/mark-a-message-as-important-or-urgent-in-teams-ea99d5b6-1317-4550-8d75-86ff14cd4462)。 优先级通知用户每隔 20 分钟一段时间通知用户一次超过 20 分钟，或者直到收件人选取和*urgent*阅读被收件人标记为代理的消息，从而最大程度地使邮件及时作出的可能性最大。
- **创建音频消息** 
  > [!Important]
  > 电子数据展示报告中未捕获音频消息。
    - **在聊天和频道中允许** 这意味着用户可以将音频消息同时保留在聊天和频道中。
    - **仅在聊天中允许** 这意味着用户可以进行聊天，但不能在频道中进行语音发送消息。
    - **已禁用** 这意味着用户无法在聊天或频道中创建音频消息。  
- **在移动设备上，显示最近聊天上方的收藏频道** 启用此设置可将收藏的通道移动到移动设备屏幕顶部，以便用户无需滚动查找它们。
- **允许用户从群组聊天中删除用户** 打开此设置，使用户可以从群组聊天中删除其他用户。 利用此功能，你可以继续与较少一组人员的聊天，无需丢失聊天历史记录。
- **启用建议的答复**  打开此设置以启用聊天消息建议的回复。

> [!NOTE]
> 这些设置中的某些设置（如使用 Giphy）还可以由团队所有者和专用频道所有者在专用频道级别配置。

### <a name="related-topics"></a>相关主题

- [在 Teams 中向用户分配策略](assign-policies.md)
- [在 Microsoft Teams 中分配团队所有者和成员](assign-roles-permissions.md)
