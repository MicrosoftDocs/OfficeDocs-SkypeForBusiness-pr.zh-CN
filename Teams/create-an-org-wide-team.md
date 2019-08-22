---
title: 在 Microsoft Teams 中创建组织范围的团队
author: LanaChin
ms.author: v-lanac
ms.reviewer: phlouie
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何在团队中创建和管理组织范围的团队。
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 901f0dd116bf152433d226e0c131f795675784cc
ms.sourcegitcommit: f2cdb2c1abc2c347d4dbdca659e026a08e60ac11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "36493108"
---
# <a name="create-an-org-wide-team-in-microsoft-teams"></a>在 Microsoft Teams 中创建组织范围的团队

组织范围的团队为一个规模较小的组织中的每个人提供自动方法, 以成为单个团队协作的一部分。

有了组织范围的团队, 全局管理员可以轻松地创建一个公共团队, 在组织中的每个用户中提取, 并在用户加入和离开组织时保持与 Active Directory 的成员身份保持最新。 只有全局管理员可以创建组织范围的团队, 并且当前组织范围的团队仅限于不超过5000用户的组织。 每个租户也有五个组织范围的团队限制。 如果满足这些要求, 当创建团队时, 全局管理员会在选择 "**从头开始构建团队**" 时看到**组织范围**。 

![组织范围选项的屏幕截图, 用于创建组织范围的团队](media/create-org-wide-team.png "组织范围选项的屏幕截图, 用于创建组织范围的团队")

创建组织范围的团队后, 所有全局管理员都将添加为团队所有者, 并将所有活动用户添加为团队成员。 未经授权的用户也将添加到团队。 当未经授权的用户第一次登录团队时, 将为用户分配 Microsoft 团队商业云试用版许可证。 若要了解有关试用许可证的详细信息, 请查看[管理团队商业云试用版优惠](iw-trial-teams.md)。 

这些类型的帐户不会添加到组织范围的团队:

- 阻止登录的帐户
- 来宾用户
- 服务帐户
- 会议室或设备帐户
- 由共享邮箱支持的帐户

由于您的组织的目录已更新为包括新的活动用户, 或者如果用户在您的公司中不再工作, 并且帐户已禁用, 则更改将自动同步, 并且用户将添加或从团队中删除。 工作组成员无法离开组织范围的团队。 作为团队所有者, 你可以根据需要手动添加或删除用户。

> [!NOTE]
> - 如果在创建团队时看不到**组织范围**选项, 并且您是全局管理员, 则该功能可能仍在进行滚动, 已达到5个组织范围的团队限制, 或者你的组织可能超过了5000个成员的当前大小限制。 我们希望将来增加此限额。
> - 不属于会议室列表、设备和资源帐户的会议室可能会添加或同步到组织范围的团队。 团队所有者可以轻松地从团队中删除这些帐户。
> - 系统将在 "常规" 频道中发布系统用于添加或删除成员的所有操作。 该频道也将标记为在团队客户端中具有新活动。

## <a name="best-practices"></a>最佳做法

为了充分利用组织范围的团队, 我们建议团队所有者执行下列操作。

### <a name="allow-only-team-owners-to-post-to-the-general-channel"></a>仅允许团队所有者发布到常规频道

只需将团队所有者发布到常规频道, 即可减少频道噪音。 转到团队, 然后单击 " **̇̇̇更多选项** > "**管理团队**。 在 "**设置**" 选项卡上, 单击 "**成员权限**" > 选择 "**仅所有者可以发布邮件**"。

### <a name="turn-off-team-and-team-name-mentions"></a>关闭 @team 和 @ [团队名称] 提及

 减少 @mentions 使其避免整个组织的过载。 转到团队, 然后单击 " **̇̇̇更多选项** > "**管理团队**。 在 "**设置**" 选项卡上, 单击 " <strong>@mentions</strong> " > 关闭 **"显示成员" 选项 @team 或 @ [团队名称]**。 

### <a name="automatically-favorite-important-channels"></a>自动收藏重要频道

收藏的重要频道, 确保您的组织中的每个人都参与特定对话。 若要了解详细信息, 请参阅[整个团队的自动常用频道](https://support.office.com/article/auto-favorite-channels-for-the-whole-team-a948272c-5aa5-429c-863c-4e1e1cd6b0f6)。

### <a name="set-up-channel-moderation"></a>设置频道裁决

考虑设置渠道裁决并向特定团队成员提供版主功能。 (如果设置了 "裁决", 团队所有者将自动获得仲裁人功能。)审阅人可以控制哪些人可以在频道中开始新文章、添加和删除审阅人、控制团队成员是否可以答复现有频道邮件以及控制机器人和连接器是否可以提交频道消息。 有关详细信息, 请参阅[在 Microsoft 团队中设置和管理通道裁决](manage-channel-moderation-in-teams.md)。

### <a name="remove-accounts-that-might-not-belong"></a>删除可能不属于的帐户

即使成员不能离开组织范围的团队, 作为团队所有者, 你可以通过删除不属于的帐户来管理团队名单。 **请确保使用团队从组织范围内的团队中删除用户**。 如果您使用另一种方法来删除用户 (如 Microsoft 365 管理中心或 Outlook 中的组), 则该用户可能会添加回组织范围的团队。

## <a name="faq"></a>常见问题解答

### <a name="is-there-a-way-to-create-an-org-wide-team-other-than-using-the-teams-client"></a>是否有一种方法可用于创建组织范围之外的团队, 而不是使用团队客户端？

全局管理员只能通过使用团队客户端来创建组织范围的团队。 如果你的组织限制创建团队使用 PowerShell, 则建议的解决方法是将全局管理员添加到可以创建团队的用户的安全组。 有关详细信息，请参阅[管理哪些人可以创建 Office 365 组](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups)。

如果这不是一个选项, 则可以使用 PowerShell 创建公共团队, 并将全局管理员添加为团队所有者。 然后, 让全局管理员单击团队名称旁边的 "**更多选项**", 单击 "**编辑团队**", 然后将隐私更改为组织范围内的**所有人都将自动添加**。 请注意, 只有团队所有者可以访问 "**编辑团队**" 选项, 并且只有全局管理员才能看到**组织范围**的选项。

### <a name="is-there-a-way-to-convert-an-existing-team-to-an-org-wide-team"></a>是否有办法将现有团队转换为组织范围的团队？

全局管理员可以通过在团队客户端中编辑现有团队, 将其转换为组织范围的团队。 转到团队名称, 单击 "**更多选项** > "**编辑团队**。
