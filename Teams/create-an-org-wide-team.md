---
title: 在 Microsoft Teams 中使用组织范围的团队来帮助每个人进行协作
ms.author: mikeplum
author: MikePlumleyMSFT
ms.reviewer: phlouie
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何在 Teams 中创建和管理组织范围的团队，以便为中小型组织中的每个人提供协作方式。
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- EngageScoreOct2022
- ContentEnagagementFY23
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-apr2020
- chat-teams-channels-revamp
ms.openlocfilehash: 5acc918c4fbe3994a93020e7b4b09db4ab1671f3
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198914"
---
# <a name="use-organization-wide-teams-in-microsoft-teams-to-help-everyone-collaborate"></a>在 Microsoft Teams 中使用组织范围的团队来帮助每个人进行协作

全局管理员可以创建组织范围的团队，为中小型组织中的每个人提供成为单个协作团队的一员的方式。 组织范围的团队会自动包括组织中的每个用户，并在用户加入和离开组织时使成员身份保持最新。

如果你的组织不熟悉 Teams，并且用户不超过 5，000 个，则会自动创建组织范围的团队。 组织范围的团队仅限于用户数不超过 10，000 的组织。 最多可以有五个组织范围的团队。 

## <a name="create-an-organization-wide-team"></a>创建组织范围的团队

有两种方法可以创建组织范围的团队：

- 将现有团队转换为组织范围的团队。 转到团队名称，然后单击“ **更多选项** > **”“编辑团队**”。

- [从头开始创建新团队](https://support.microsoft.com/office/174adf5f-846b-4780-b765-de1a0a737e2b) ，然后选择 **“组织范围”** 选项。

    ![用于创建组织范围的团队的“组织范围”选项的屏幕截图。](media/create-org-wide-team.png "用于创建组织范围的团队的组织范围选项的屏幕截图")

## <a name="types-of-users-in-an-organization-wide-team"></a>组织范围团队中的用户类型

创建组织范围的团队时，所有全局管理员和 Teams 管理员都添加为团队所有者，所有活动用户将添加为团队成员。 团队成员不能离开组织范围的团队，但团队所有者可以根据需要手动添加或删除用户。 当 Teams 自动添加或删除某人时，将向常规频道发送通知。

未经授权的用户也将添加到团队。 未经许可的用户首次登录 Teams 时，系统会为他们分配Microsoft Teams 探索许可证。 若要了解有关 Exploratory 许可证的详细信息，请参阅[管理 Microsoft Teams Exploratory 许可证](teams-exploratory.md)。

以下类型的帐户不会添加到组织范围的团队：

- 被阻止登录的帐户
- 来宾
- 资源或服务帐户 (例如，与自动助理和呼叫队列关联的帐户) 
- 会议室或设备帐户
- 共享邮箱支持的帐户

> [!NOTE]
> 不属于会议室列表、设备和资源帐户的会议室可能会添加或同步到组织范围的团队。 团队所有者可轻松从团队中删除这些帐户。

## <a name="options-to-get-the-most-out-of-an-organization-wide-team"></a>充分利用组织范围的团队的选项

为了充分利用组织范围内的团队，我们建议团队所有者执行以下任务：

### <a name="allow-only-team-owners-to-post-to-the-general-channel"></a>仅允许团队所有者发布到常规频道

通过仅允许团队所有者发布到常规频道，减少频道中的杂乱信息。

1. 转到团队，找到“常规”频道，然后选择“ **...更多选项** > **管理频道**。
2. 在“ **频道设置** ”选项卡上，单击“ **权限**”，然后选择“ **只有所有者才能发布消息**”。

### <a name="turn-off-team-and-team-name-mentions"></a>关闭 @团队和 @[团队名称]提及

减少 @提及，以防止它们使整个组织超载。

1. 转到团队并单击“**...”“管理团队”的更多选项**\>。
2. 在 **“设置”** 选项卡上，单击 **@mentions**\>关闭 **“向成员显示@team或 @[团队名称]的选项**。

### <a name="automatically-show-important-channels"></a>自动显示重要频道

显示重要频道，以确保组织中的每个人都能参与特定对话。 若要了解详细信息，请参阅[为整个团队自动收藏频道](https://support.office.com/article/auto-favorite-channels-for-the-whole-team-a948272c-5aa5-429c-863c-4e1e1cd6b0f6)。

### <a name="set-up-channel-moderation"></a>设置频道审阅

考虑设置频道审阅并向某些团队成员提供审阅人功能。  (设置审查后，将自动为团队所有者提供审查员功能。) 审阅者可以：

- 控制谁可以在频道中启动新帖子
- 添加和删除审查员
- 控制团队成员是否可以回复现有频道消息
- 控制机器人和连接器是否可以提交通道消息。

有关详细信息，请参阅[在 Microsoft Teams 中设置和管理频道审核](manage-channel-moderation-in-teams.md)。

### <a name="remove-accounts-that-might-not-belong"></a>删除可能不属于成员的帐户

即使成员不能离开组织范围的团队，作为团队所有者，你可以通过删除不属于的帐户来管理团队名单。 **请确保使用 Teams 从组织范围的团队中删除用户**。 如果使用其他方法删除用户（例如Microsoft 365 管理中心或 Outlook 中的组），则用户可能会被添加回组织范围的团队。

## <a name="related-topics"></a>相关主题

观看有关如何[在 Microsoft Teams 中创建组织范围的团队](https://www.youtube.com/watch?v=x3qGlwwCz_w)的视频。
