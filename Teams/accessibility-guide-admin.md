---
title: Microsoft Teams 管理员的辅助功能指南
ms.author: meghan
author: meganrmhan
ms.reviewer: eljones
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
description: 通过启用字幕和听录、允许会议访问手语解释器和 CART 字幕、减少干扰、改善参与和共享资源，提高 Microsoft Teams 中的辅助功能。
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom: ''
ms.collection:
- M365-collaboration
ms.openlocfilehash: 7b089785695e9bef985107b5f1db8e5659c48c33
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/20/2022
ms.locfileid: "68614696"
---
# <a name="accessibility-guide-for-microsoft-teams-admins"></a>Microsoft Teams 管理员的辅助功能指南

作为你的组织的 Microsoft Teams 管理员，你可以帮助所有用户使 Teams 环境具有包容性和可访问性。 按照下面的指南和资源配置 Microsoft Teams 以获得最佳辅助功能。

> [!NOTE]
> 默认情况下，许多辅助功能选项处于打开状态，但你可以按照本指南中的步骤检查它们是否未关闭。

## <a name="turn-on-captions-and-transcription-for-meetings-and-calls"></a>打开会议和通话的字幕和听录

为残障人士创建包容性会议和呼叫，以便每个人都可以参与和参与。

### <a name="turn-on-live-captions-for-meetings"></a>为会议打开实时字幕

实时字幕是实时自动生成的会议内容文本。 对于已启用它们且未保存的用户，它们一次会显示几行。

若要为用户启用实时字幕，请执行以下操作：

1. 在 Microsoft Teams 管理中心，转到 **“会议**”，然后选择下拉列表 **会议策略**。

2. 选择要修改的策略。

3. 转到 **“参与者&来宾** ”部分。

4. 将 **实时字幕** 切换到 **“未启用”，但用户可以替代**。

5. 选择“**保存**”。

> [!TIP]
> 共享以下链接，以便用户可以了解如何 [在会议期间打开实时字幕](https://support.microsoft.com/office/use-live-captions-in-a-teams-meeting-4be2d304-f675-4b57-8347-cbd000a21260#ID0EBD=Desktop)。

> [!NOTE]
> 实时字幕可用于在商业和美国政府社区云 (GCC) 组织举行的会议。

### <a name="turn-on-transcription-for-calls"></a>为调用启用听录

听录是自动生成的，记录了通话中所述内容的文本。 启用后，用户可在呼叫结束后查看脚本。

若要为用户启用听录，请执行以下操作：

1. 在 Microsoft Teams 管理中心，转到 **“语音**”，然后选择下拉列表 **呼叫策略**。

2. 选择要修改的策略。

3. 将 **听录****打开，** 然后选择 **“保存**”。

### <a name="why-captions-and-transcripts-are-important"></a>为什么标题和脚本很重要

标题和脚本是某人正在说出的单词的文本版本。 他们为人们提供了查看文本的选项，而不是单独查看音频。 字幕还使失聪或听力困难的人受益，方法是提供其他信息，了解某些用户从他们可能使用的手语解释器或 CART 字幕中收到的信息。

在各种情况下，字幕和听录非常有用，但对于以下情况尤其有帮助：

- 人员失聪或听力困难

- 有学习障碍的人员

- 人员处于嘈杂或分散注意力的环境中，需要查看会议结束后共享的信息

有关详细信息，请参阅以下链接：

- [用于录制和听录的会议策略设置](/Microsoftteams/meetings-policies-recording-and-transcription)

- [WCAG) 1.2.4. (Web 内容辅助功能准则：实时)  (字幕 ](https://www.w3.org/WAI/WCAG21/Understanding/captions-live)

## <a name="give-meeting-access-to-sign-language-interpreters-and-cart-communication-access-real-time-translation-captioners"></a>授予会议对手语解释器和 CART (通信访问实时翻译) 字幕者的访问权限

让手语解释器和 CART (通信访问实时翻译) 字幕者访问 Microsoft Teams 会议，以便他们可以更有效地与失聪或听力较硬的用户一起工作。

### <a name="admit-sign-language-interpreters-and-cart-captioners-to-meetings"></a>允许手语解释员和 CART 字幕人员加入会议

手语解释器和 CART 字幕可能不适用于你的组织，但你可以 [通过授予他们来宾访问权限](/MicrosoftTeams/guest-access)来邀请他们参加 Microsoft Teams 会议。

提供来宾访问权限后，允许手语解释员和 CART 字幕人员参加会议：

1. 在 Microsoft Teams 管理中心，转到 **“会议**”，然后选择下拉列表 **会议策略**。

2. 选择要修改的策略。

3. 转到 **“参与者&来宾** ”部分。

4. 选择“ **自动允许** 最符合组织的合规性和安全要求的人员”下的选项。 可以选择以下选项之一：

   - 不建议每个人 () 

   - 组织中的人员和来宾 (推荐) 

   - 我的组织中人员、受信任的组织和来宾

   - 我的组织中的人员

   - 仅管理器

   - 仅邀请用户

5. 选择“**保存**”。

> [!NOTE]
> 设置 **自动允许用户** 不适用于拨入用户。

### <a name="turn-on-ip-video-feed-for-your-users"></a>为用户启用 IP 视频源

让手语翻译能够在 Microsoft Teams 会议期间共享 IP 视频源，以便他们能够与听力失聪或听力不佳的用户通信。

若要检查是否启用 IP 视频源，请执行以下操作：

1. 在 Microsoft Teams 管理中心，转到 **“会议**”，然后选择下拉列表 **会议策略**。

2. 选择要修改的策略。

3. 转到 **“音频&视频** ”部分。

4. 检查 **IP 视频** 是否已 **打开**，然后选择 **“保存**”。

> [!TIP]
> 与用户共享以下链接，以便他们能够调整使用 Teams 的方式，以最大程度地提高参与会议、集中注意力和协作的能力：
> - [自定义会议视图](https://support.microsoft.com/office/customize-your-meeting-view-95aaeaf8-0f22-46cf-a6f9-34ca9b04a1b2)
> - [使用 CART 字幕](https://support.microsoft.com/office/use-cart-captions-in-a-microsoft-teams-meeting-human-generated-captions-2dd889e8-32a8-4582-98b8-6c96cf14eb47#:~:text=Use%20CART%20captions%20in%20a%20Microsoft%20Teams%20meeting,out%20of%20your%20captions.%20...%204%20See%20also)

### <a name="why-its-important-to-include-sign-language-interpreters-and-cart-captioners"></a>为什么必须包括手语解释器和 CART 字幕

一些用户可能更愿意使用 CART 字幕，因为他们对特定行话、口音等比自动生成的字幕更准确。

主要通信方法为手语的用户需要手语解释，这需要提供人工解释器。

有关详细信息，请参阅 [WCAG) 1.2.6. (Web 内容辅助功能指南：手语解释](https://www.w3.org/TR/WCAG21/#sign-language-prerecorded)。

## <a name="reduce-distractions-in-meetings"></a>减少会议中的干扰

通过打开视频筛选器来鼓励用户参与，以减少 Teams 会议中的干扰。

### <a name="turn-on-video-filters"></a>打开视频筛选器

视频筛选器有助于减少会议期间的干扰。

打开视频筛选器：

1. 在 Microsoft Teams 管理中心，转到 **“会议**”，然后选择下拉列表 **会议策略**。

2. 选择要修改的策略。

3. 转到 **“内容共享”** 部分。

4. 选择最符合组织合规性和安全要求 **的视频筛选器** 下的选项。 选择以下选项之一：

   - 仅背景模糊

   - 背景模糊图像和默认图像

   - 所有筛选器

5. 选择“**保存**”。

> [!TIP]
> 共享以下链接，以便用户可以调整其 Teams 会议首选项以减少干扰：
> - [更改 Teams 会议中的背景效果](https://support.microsoft.com/office/change-your-background-for-a-teams-meeting-f77a2381-443a-499d-825e-509a140f4780#ID0EDD=Desktop)
> - [减少 Teams 会议中的背景噪音](https://support.microsoft.com/office/reduce-background-noise-in-teams-meetings-1a9c6819-137d-4b3b-a1c8-4ab20b234c0d)

### <a name="why-its-helpful-to-reduce-distractions"></a>为什么它有助于减少干扰

组织中的一些人可能会发现，由于参与者背景中的移动、光线和其他干扰，在视频会议和通话中很难集中注意力。 使用视频筛选器可帮助用户控制干扰并充分参与。

*背景效果* 可以帮助人们关注说话人，而不是说话人的背景。 Microsoft Teams 有一个背景库，用户也可以上传自己的资源库。

*背景模糊* 有助于提高会议或通话中的可见性和焦点，因为它可以减少后台干扰，但会使用户保持专注。

在各种情况下，视频筛选器非常有用，但对于以下情况尤其有帮助：

- 人员神经反面

- 人员失聪或听力困难

有关详细信息，请参阅 [ (WCAG) 1.4.8.：Visual Presentation 中的 Web 内容辅助功能指南](https://www.w3.org/WAI/WCAG21/Understanding/visual-presentation.html)。

## <a name="improve-participation-in-microsoft-teams-meetings"></a>提高 Microsoft Teams 会议的参与度

通过 **在会议中** 启用聊天以及聊天编辑、**沉浸式阅读器** 和表情符号等消息策略，鼓励用户通过更多控制和灵活性选项参与。

### <a name="turn-on-chat-in-meetings"></a>在会议中启用聊天

聊天使许多用户更容易在 Teams 会议中提问或添加信息。

检查会议内聊天是否已打开：

1. 在 Microsoft Teams 管理中心，转到 **“会议**”，然后选择下拉列表 **会议策略**。

2. 选择要修改的策略。

3. 转到 **“参与者&来宾** ”部分。

4. 在最符合组织合规性和安全要求的 **会议中选择“聊天** ”下的选项。 可以选择以下选项之一：

   -  (推荐) 为所有人启用它

   - 不建议)  (为所有人关闭它

   - 为除匿名用户之外的所有人启用它

5. 选择“**保存**”。

### <a name="use-messaging-policies-for-increased-flexibility-and-control"></a>使用消息传送策略提高灵活性和控制力

灵活的聊天选项使许多用户更容易理解他人的消息、修改自己的消息并表达自己。

若要检查是否启用了这些灵活的聊天选项，请执行以下操作：

在 **Microsoft Teams 管理中心**：

1. 在 Microsoft Teams 管理中心，转到 **消息传送策略**。

2. 选择要修改的策略。

3. 检查以下项是否已 **打开**：

   - **删除已发送的消息**

   - **编辑已发送的消息**

   - **聊天**

   - **对话中的 Giphys**

   - **对话中的 Memes**

   - **对话中的贴纸**

   - **URL 预览**

   - **翻译消息**

   - **邮件的沉浸式阅读器**

4. 选择“**保存**”。

> [!TIP]
> 与组织共享 [如何编写有效替换文字](https://support.microsoft.com/office/everything-you-need-to-know-to-write-effective-alt-text-df98f884-ca3d-456c-807b-1a1fa82f5dc2) 的链接，以帮助用户了解聊天中共享的非文本消息。

### <a name="why-alternate-participation-options-matter"></a>为什么备用参与选项很重要

灵活的聊天选项使用户能够更灵活地使用会议内聊天内容，并更好地控制他们如何通过聊天参与会议。

*会议内聊天* 为人们提供了另一种参与会议讨论的方式。 对于一些残障人士来说，聊天可能比语音或手语更适合作为参与会议讨论的一种方式。

*沉浸式阅读器* 是一种为有阅读障碍和阅读障碍的人设计的工具，有助于使文本更易于理解。 它还包括为喜欢使用不同语言进行通信的人员的内联翻译。 沉浸式阅读器的一些主要功能包括：

- 添加让内容大声朗读的选项

- 更改文本大小和背景色

- 将字词分解为音节

- 增加字母之间的间距

- 突出显示一行或多行文本

- 突出显示语音的各个部分

灵活聊天选项在各种情况下很有用，但可能特别有用：

- 失明或视力低下的人员

- 人员神经性 (，即有阅读障碍或阅读障碍) 

有关详细信息，请参阅 [WCAG (WCAG) 1.1.1.：文本替代项的 Web 内容辅助功能指南](https://www.w3.org/TR/WCAG21/#text-alternatives)。

## <a name="share-resources-with-users-to-further-accessibility-awareness"></a>与用户共享资源以进一步提高辅助功能意识

用户可以采取其他步骤来改善其辅助功能体验。 与组织和来宾用户共享以下链接。

### <a name="reference-links"></a>参考链接

Microsoft 的残疾应答服务台提供最终用户指南，用于自定义其体验以满足其辅助功能需求：

- [在会议期间打开实时字幕](https://support.microsoft.com/office/use-live-captions-in-a-teams-meeting-4be2d304-f675-4b57-8347-cbd000a21260#ID0EBD=Desktop)

- [自定义会议视图](https://support.microsoft.com/office/customize-your-meeting-view-95aaeaf8-0f22-46cf-a6f9-34ca9b04a1b2)

- [使用 CART 字幕](https://support.microsoft.com/office/use-cart-captions-in-a-microsoft-teams-meeting-human-generated-captions-2dd889e8-32a8-4582-98b8-6c96cf14eb47#:~:text=Use%20CART%20captions%20in%20a%20Microsoft%20Teams%20meeting,out%20of%20your%20captions.%20...%204%20See%20also)

- [更改 Teams 会议中的背景效果](https://support.microsoft.com/office/change-your-background-for-a-teams-meeting-f77a2381-443a-499d-825e-509a140f4780#ID0EDD=Desktop)

- [减少 Teams 会议中的背景噪音](https://support.microsoft.com/office/reduce-background-noise-in-teams-meetings-1a9c6819-137d-4b3b-a1c8-4ab20b234c0d)

- [编写有效的替换文字](https://support.microsoft.com/office/everything-you-need-to-know-to-write-effective-alt-text-df98f884-ca3d-456c-807b-1a1fa82f5dc2)

- [Microsoft Teams 的辅助功能工具](https://support.microsoft.com/office/accessibility-tools-for-microsoft-teams-2d4009e7-1300-4766-87e8-7a217496c3d5?ui=en-us&rs=en-us&ad=us)

### <a name="reference-web-content-accessibility-guidelines-wcag"></a>参考 WCAG)  (Web 内容辅助功能指南

WCAG 是一系列旨在提高 Web 辅助功能的国际标准。 本指南中引用的成功条件包括：

- [WCAG 1.2.4.：实时)  (标题 ](https://www.w3.org/WAI/WCAG21/Understanding/captions-live)

- [WCAG 1.2.6.：手语解释](https://www.w3.org/TR/WCAG21/#sign-language-prerecorded)

- [WCAG 1.4.8.：视觉对象演示文稿](https://www.w3.org/WAI/WCAG21/Understanding/visual-presentation.html)

- [WCAG 1.1.1.：文本替代项](https://www.w3.org/TR/WCAG21/#text-alternatives)
