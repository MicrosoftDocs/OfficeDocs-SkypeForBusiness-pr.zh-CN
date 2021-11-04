---
title: 设置和管理频道审核
author: cichur
ms.author: v-mahoffman
manager: serdars
ms.reviewer: jotaing
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 了解如何在频道中设置审核Microsoft Teams，包括如何将团队成员添加为频道审阅人。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a012eb26ac9017e0d6a1110505aa1d1025c6a779
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60753985"
---
# <a name="set-up-and-manage-channel-moderation-in-microsoft-teams"></a>在视频中设置和管理Microsoft Teams

在Microsoft Teams中，团队所有者可以针对标准频道启用审核，以控制谁可以启动新帖子和回复该频道中的帖子。

团队所有者还可以将团队成员添加为审阅人。 团队所有者可能没有频道级别的主题专业知识，无法最好地支持频道审核。 通过允许特定团队成员审查频道，团队所有者和频道审查者可以分担管理频道中内容和上下文的责任。 例如，团队所有者可以将业务所有者或内容所有者添加为审阅人，这样他们就可以控制该频道中的信息共享。

> [!NOTE]
> 频道审核适用于标准通道。 不适用于常规频道或专用频道。

## <a name="what-can-a-channel-moderator-do"></a>频道审查器可以执行哪些功能？

频道审查器可以：

- 在频道中开始新文章。 当为频道启用审核时，只有审阅人可以在该频道中启动新帖子。
- 在频道中添加和删除作为审阅人的团队成员。 请记住，默认情况下，团队所有者是频道审查器，不能删除。
- 控制团队成员是否可以回复现有通道消息，以及机器人和连接器是否可以提交通道消息。

## <a name="scenarios"></a>方案

下面是一些示例，说明您的组织如何在 Teams。

### <a name="use-a-channel-as-an-announcement-channel"></a>使用频道作为公告频道

营销团队使用特定渠道共享关键项目公告和可交付结果。 有时，工作组成员将内容发布给其他频道中更合适的内容。 团队所有者希望将频道中的信息共享限制为仅发布公告，以便团队成员可以使用该频道随时了解重要内容。

在此方案中，团队所有者将市场营销潜在顾客添加为审阅人，以便他们可以在频道中发布公告，并关闭团队成员回复该频道中的消息的能力。

### <a name="use-a-channel-for-class-discussions-in-teams-for-education"></a>使用频道进行课堂讨论Teams 教育版

在Teams 教育版中，科学教师希望使用频道来让学生参与有关特定课堂主题的重点讨论。

在此方案中，教师允许其教学助手主持频道。 然后，教学助理可以创建新文章来发起和推动与学生的讨论。

## <a name="manage-channel-moderation"></a>管理频道审核

在Teams，转到频道，单击"**更多选项..."**  > **管理频道**。 在这里，可以启用和关闭审核、将团队成员添加为审阅人，以及设置首选项。

通道审核是按通道设置。 没有用于通道审核的租户级设置。 如果希望我们添加租户级通道审核设置，请通过[UserVoice](https://microsoftteams.uservoice.com/)Teams它。

[!INCLUDE [uservoice-disclaimer-note](includes/uservoice-disclaimer-note.md)]

![管理频道-审核-团队中的首选项。](media/manage-channel-moderation-in-teams-preferences.png)

### <a name="turn-on-or-turn-off-moderation-for-a-channel"></a>打开或关闭频道审核

默认情况下，审核已关闭，这意味着通常的频道设置适用于团队所有者和团队成员。 例如，您可以将新帖子限制为仅团队成员，或允许每个人（包括来宾）启动新文章。

若要为频道启用审核，请在"频道审查"**下，单击**"**打开"。** 当频道审查打开时，只有审阅人可以启动新文章。 

### <a name="add-or-remove-channel-moderators"></a>添加或删除频道审查器

在 **Who审阅人？"下**，单击 **"管理**"，然后添加或删除团队成员作为审阅人。 团队所有者和审阅人可以添加和删除其他审阅人。  

### <a name="set-team-member-permissions"></a>设置团队成员权限

在 **"团队成员权限**"下，选中要允许的活动旁边的复选框。

## <a name="related-topics"></a>相关主题

- [Teams 中的团队和频道概述](teams-channels-overview.md)
