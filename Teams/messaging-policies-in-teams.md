---
title: 管理消息传递策略
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.messagingpolicies.overview
description: 了解有关消息策略以及如何使用它们来控制聊天消息团队。
ms.openlocfilehash: b30b14ef8db70a6d8d88d4413a82fd1d672da13b
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/07/2019
ms.locfileid: "30465297"
---
# <a name="what-are-messaging-policies-in-teams"></a>Teams 中的消息传递策略是什么？  

::: zone target="docs"
邮件策略用于控制哪些聊天和消息功能的通道供 Microsoft 团队中的用户。 您可以使用创建或的组织中的人员创建一个或多个自定义的邮件策略的默认策略。 创建策略后，您将其分配用户组的组织中。

可以在 Microsoft 团队管理中心轻松地管理策略 (http://admin.teams.microsoft.com) ，日志记录使用管理员凭据，然后在左侧的导航窗格中选择**消息策略**。 

![团队中的邮件策略](media/messaging-policies-image1.png)

若要编辑您的组织的现有默认消息策略，请单击**全局 （组织范围内默认值）** 行中，然后进行更改。 若要创建新的自定义邮件策略，单击**新建策略**，然后选择您的设置。 完成后，请选择**保存**。

![消息团队中的策略设置](media/messaging-policies-image2.png)
::: zone-end  
::: zone target="chromeless"
使用以下设置来更改全局消息策略或创建新的自定义策略：

- **所有者可以删除发送的消息** 使用此设置让删除邮件的所有者发送聊天中的用户。
- **用户可以删除发送的消息**使用此设置可允许用户删除它们聊天中发送的邮件。
- **用户可以编辑已发送的邮件**使用此设置以使用户可以编辑他们聊天中发送的消息。
- **已读回执**使用此设置指定是否读回执是控制、 每个人、 启用或禁用的用户。

<a name="bkchat"> </a>

- **聊天** 如果您希望能够使用团队应用程序与其他人聊天您组织中的用户，请打开此设置。
- **使用 Giphys 对话中** 如果关闭此，用户可以与其他人聊天对话中包括 Giphys。 Giphy 是联机数据库和搜索引擎，使用户可以搜索和共享动态的 GIF 文件。 每个 Giphy 分配内容评级。
- **Giphy 内容评级** 
    - **无限制**这意味着您的用户将能够在聊天内容的分级无论中插入任何 Giphy。
    - **中等** 这意味着您的用户将能够在聊天室中插入 Giphys，但将从成人内容适度限制。
    - **严格** 这意味着您的用户将能够在聊天室中插入 Giphys，但将从成人内容严格限制。
- **使用 Memes 对话中**如果关闭此，用户可以与其他人聊天对话中包括 Memes。 
- **在对话中使用标签**如果关闭此，用户可以与其他人聊天对话中包括标签。
- **允许 URL 预览**使用此设置以启用自动 URL 预览打开或关闭消息中。
- **允许用户将邮件**启用此设置以使用户可以自动将团队邮件转换为 Office 365 其个人语言设置由指定语言。 

[完整的文章](messaging-policies-in-teams.md)
::: zone-end

::: zone target="docs"
如果您已创建的自定义消息策略，它将仅处于活动状态的用户如果该策略分配给用户。 将自定义策略分配给用户的 Microsoft 团队管理中心中，选择**用户**的左侧窗格中，并选择您想要分配给策略的用户。 在用户的页上，选择**分配策略**旁边的**编辑**。
::: zone-end

### <a name="related-topics"></a>相关主题
[Teams 中的会议策略](meeting-policies-in-teams.md)



