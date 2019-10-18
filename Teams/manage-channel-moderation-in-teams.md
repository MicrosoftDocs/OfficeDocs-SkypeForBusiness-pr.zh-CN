---
title: 在 Microsoft 团队中设置和管理渠道裁决
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jotaing
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 了解如何在 Microsoft 团队中设置用于裁决的频道，包括如何将团队成员添加为渠道审阅者。
ms.openlocfilehash: 52b89f21cd2b622b78f6dbee44d8efe5ce4ce490
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2019
ms.locfileid: "37570659"
---
# <a name="set-up-and-manage-channel-moderation-in-microsoft-teams"></a>在 Microsoft 团队中设置和管理渠道裁决

在 Microsoft 团队中，团队所有者可以为频道启用裁决，以控制哪些人可以开始新文章以及答复该频道中的帖子。

团队所有者还可以将团队成员添加为审阅人。 团队所有者可能在频道级别没有主题专业知识，以获得最佳支持渠道裁决。 通过允许特定团队成员来安排频道，管理频道中的内容和上下文的责任由团队所有者和渠道审阅者共享。 例如，团队所有者可以将企业所有者或内容所有者添加为审阅者，从而使他们可以控制该频道中的信息共享。

## <a name="what-can-a-channel-moderator-do"></a>频道审查方可以执行哪些操作？

频道审阅者可以：

- 在频道中开始新的文章。 为频道启用裁决后，只有审阅人可以在该频道中开始新的帖子。
- 将团队成员添加和删除为频道的审阅人。 请记住，默认情况下，团队所有者是 "频道审阅者"，不能删除。
- 控制团队成员是否可以答复现有信道消息，以及机器人和连接器是否可以提交频道消息。

## <a name="scenarios"></a>方案

下面是组织如何在团队中使用渠道裁决的一些示例。

### <a name="use-a-channel-as-an-announcement-channel"></a>将频道用作公告通道

市场营销团队使用特定的频道来共享关键项目公告和可交付结果。 有时，团队成员向频道发布内容更恰当地属于其他频道。 团队所有者希望将频道中的信息共享限制为仅通知通知，以便团队成员可以使用该频道保持最重要的内容。

在此方案中，团队所有者将市场营销线索添加为审阅者，以便他们可以在频道中发布公告，并关闭工作组成员答复该频道中的邮件的功能。

### <a name="use-a-channel-for-class-discussions-in-teams-for-education"></a>在教育团队中使用渠道进行课堂讨论

在 "教育团队" 中，一位科学老师希望使用频道在特定教室主题的重点讨论中吸引学生。

在这种情况下，教师可以通过 "教学助手" 来使频道适中。 然后，"教学助手" 可以创建新的文章来启动和推动与学生进行讨论。

## <a name="manage-channel-moderation"></a>管理渠道裁决

在 "团队" 中，转到频道，单击 "**更多选项 ...** " > **管理频道**。 在此处，您可以打开和关闭 "裁决"，将团队成员添加为审阅者，以及设置首选项。

通道裁决是每个通道的设置。 频道裁决没有租户级别的设置。 如果您希望我们添加租户级通道裁决设置，请在[团队 UserVoice](https://microsoftteams.uservoice.com/)上请求。

![manage-channel-moderation-in-teams-preferences](media/manage-channel-moderation-in-teams-preferences.png)

### <a name="turn-on-or-turn-off-moderation-for-a-channel"></a>打开或关闭频道裁决

默认情况下，"裁决" 处于关闭状态，这意味着常规频道设置适用于团队所有者和团队成员。 例如，您可以将新帖子限制为仅限团队成员，或允许每个人（包括来宾）开始新的文章。

若要为频道启用裁决，请在 "**通道裁决**" 下，单击 **"打开"**。 当频道裁决处于开启时，只有审阅人可以开始新的帖子。 

### <a name="add-or-remove-channel-moderators"></a>添加或删除频道审阅者

在 "**谁是审阅人**" 下，单击 "**管理**"，然后添加或删除团队成员为 "审阅者"。 团队所有者和审阅者可以添加和删除其他审阅人。  

### <a name="set-team-member-permissions"></a>设置团队成员权限

在 "**团队成员权限**" 下，选中要允许的活动旁边的复选框。

## <a name="related-topics"></a>相关主题

- [团队中的团队和频道概述](teams-channels-overview.md)
