---
title: Teams 中的消息传递策略是什么？
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.messagingpolicies.overview
description: 了解有关消息策略以及如何使用它们来控制聊天消息团队。
ms.openlocfilehash: d4d2a4f424de1750c70ea851d1d1d35a2aaf9e44
ms.sourcegitcommit: dfd075d092db9826c792cf947c83c33cfcd8ef4e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/07/2019
ms.locfileid: "29763713"
---
# <a name="what-are-messaging-policies-in-teams"></a>Teams 中的消息传递策略是什么？
::: zone target="docs"
邮件策略用于控制哪些聊天和消息功能的通道供 Microsoft 团队中的用户。 您可以使用创建或的组织中的人员创建一个或多个自定义的邮件策略的默认策略。 创建策略后，您将其分配用户组的组织中。

可以在工作组管理中心轻松地管理策略 (http://admin.teams.microsoft.com)左侧导航窗格中单击**消息策略**和日志记录使用管理员凭据。 若要编辑现有的默认策略为您的组织，选择**全局 （组织范围内默认值）** 行，然后单击**编辑**。 若要创建新的邮件策略，单击**新建策略**。

![团队中的邮件策略](media/messaging-policies.png)
::: zone-end

下面介绍了可用的策略设置： 

- **所有者可以删除发送的消息** 使用此设置可以让所有者删除聊天中的用户发送的邮件。
- **用户可以删除发送的消息**使用此设置可允许用户删除聊天中发送的邮件。
- **用户可以编辑已发送的邮件**使用此设置可允许用户编辑其聊天中发送的邮件。
- **已读回执**使用此设置指定是否读回执是控制、 每个人、 启用或禁用的用户。
<a name="bkchat"> </a>

- **聊天** 如果您希望能够使用团队应用程序与其他人聊天您组织中的用户，请打开此设置。
- **使用 Giphys 对话中** 如果关闭此，用户可以与其他人聊天对话中包括 Giphys。 Giphy 是联机数据库和搜索引擎，使用户可以搜索和共享动态的 GIF 文件。 每个 Giphy 分配内容评级。
- **Giphy 内容评级** 
    - **无限制**这意味着您的用户将能够在聊天内容的分级无论中插入所有 Giphys。
    - **中等** 这意味着您的用户将能够在聊天室中插入 Giphys，但将从成人内容适度限制。
    - **严格** 这意味着您的用户将能够在聊天室中插入 Giphys，但将从成人内容严格限制。
- **使用 Memes 对话中**如果关闭此，用户可以与其他人聊天对话中包括 Memes。 
- **在对话中使用标签**如果关闭此，用户可以与其他人聊天对话中包括标签。
- **允许 URL 预览**使用此设置以启用自动 URL 预览打开或关闭消息中。
- **允许用户将邮件**启用此设置以使用户可以自动将团队邮件转换为 Office 365 其个人语言设置由指定语言。

::: zone target="docs"
如果您已创建的自定义消息策略，它将仅处于活动状态的用户如果该策略分配给用户。  要自定义策略分配团队管理中心中的用户，请单击**用户**的左侧窗格中，选择要分配到的策略的用户，然后选择在**分配策略**下的**编辑**。
::: zone-end

### <a name="related-topics"></a>相关主题
[Teams 中的会议策略](meeting-policies-in-teams.md)
