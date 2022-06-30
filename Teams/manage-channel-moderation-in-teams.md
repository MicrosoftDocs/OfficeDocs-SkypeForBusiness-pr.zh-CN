---
title: 设置和管理通道审查
ms.author: mikeplum
author: MikePlumleyMSFT
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
description: 了解如何在 Microsoft Teams 中设置审查频道，包括如何将团队成员添加为频道审查器。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 52fb88d6371c033713c5b14d96ecf2a9211420b0
ms.sourcegitcommit: ff783fad2fb5d412e864e3af2ceaa8fedcd9da07
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/30/2022
ms.locfileid: "66562361"
---
# <a name="set-up-and-manage-channel-moderation-in-microsoft-teams"></a>在 Microsoft Teams 中设置和管理频道审查

在 Microsoft Teams 中，团队所有者可以启用标准频道的审查，以控制谁可以启动新帖子并回复该频道中的帖子。

团队所有者还可以将团队成员添加为审查器。 团队所有者可能没有频道级别的主题专业知识来最佳地支持频道审查。 通过允许特定团队成员审查频道，在团队所有者和频道审查器之间共享管理频道中的内容和上下文的责任。 例如，团队所有者可以将业务所有者或内容所有者添加为审查器，这样他们就可以控制该频道中的信息共享。

> [!NOTE]
> 频道审查适用于标准通道。 它不适用于常规频道或专用频道或共享频道。

## <a name="what-can-a-channel-moderator-do"></a>频道审查器可以做什么？

频道审查器可以：

- 在频道中启动新帖子。 为频道启用审查时，只有审查器才能在该频道中启动新帖子。
- 将团队成员作为审查器添加和删除到频道。 请记住，默认情况下，团队所有者是频道审查器，不能删除。
- 控制团队成员是否可以回复现有频道消息，以及机器人和连接器是否可以提交频道消息。

## <a name="scenarios"></a>方案

下面是组织如何在 Teams 中使用频道审查的一些示例。

### <a name="use-a-channel-as-an-announcement-channel"></a>将频道用作公告频道

市场营销团队使用特定渠道共享关键项目公告和可交付结果。 有时，团队成员会将内容发布到更恰当地属于其他频道的频道。 团队所有者希望将频道中的信息共享限制为仅发布公告，以便团队成员可以使用该频道来掌握重要内容。

在此方案中，团队所有者将 Marketing 潜在顾客添加为审查器，以便他们可以在频道中发布公告，并关闭团队成员答复该频道中消息的功能。

### <a name="use-a-channel-for-class-discussions-in-teams-for-education"></a>在Teams 教育版中使用频道进行类讨论

在Teams 教育版中，一位科学教师希望使用一个频道让学生参与有关特定课堂主题的集中讨论。

在这种情况下，教师允许其助教审查频道。 然后，助教可以创建新的职位，以启动和推动与学生的讨论。

## <a name="manage-channel-moderation"></a>管理通道审查

在 Teams 中，转到频道，单击 **“更多选项...”** > **管理通道**。 可在此处打开并关闭审查，将团队成员添加为审查器，并设置首选项。

通道审查是按通道设置。 没有用于通道审查的租户级设置。 如果希望我们添加租户级通道审查设置，请在 [Teams 反馈门户](https://feedbackportal.microsoft.com/feedback/forum/ad198462-1c1c-ec11-b6e7-0022481f8472)上请求它。

[!INCLUDE [uservoice-disclaimer-note](includes/uservoice-disclaimer-note.md)]

![在团队中管理频道审查的首选项。](media/manage-channel-moderation-in-teams-preferences.png)

### <a name="turn-on-or-turn-off-moderation-for-a-channel"></a>打开或关闭通道的审查

默认情况下，审查处于关闭状态，这意味着通常的频道设置适用于团队所有者和团队成员。 例如，可以将新帖子限制为仅团队成员，或者允许每个人（包括来宾）开始新帖子。

若要为频道启用审查，请在 **频道审查** 下单击 **“打开**”。 当频道审查处于打开状态时，只有审查器才能启动新帖子。 

### <a name="add-or-remove-channel-moderators"></a>添加或删除频道审查器

在 **“谁是审阅者？”** 下，单击 **“管理**”，然后以审查器身份添加或删除团队成员。 团队所有者和审查器可以添加和删除其他审查器。  

### <a name="set-team-member-permissions"></a>设置团队成员权限

在 **团队成员权限** 下，选择要允许的活动旁边的复选框。

## <a name="related-topics"></a>相关主题

- [Teams 中的团队和频道概述](teams-channels-overview.md)
