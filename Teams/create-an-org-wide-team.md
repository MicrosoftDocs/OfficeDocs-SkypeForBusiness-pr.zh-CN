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
description: 了解如何在团队中创建和管理组织范围内的团队，以便为中小型组织中的每个人提供自动方式进行协作。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 84f34ee9af678613580beefeb52b08e9ce924be3
ms.sourcegitcommit: 67c686810d37bffda72a6e92155d9c8ec86bfae6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2020
ms.locfileid: "47766866"
---
# <a name="create-an-org-wide-team-in-microsoft-teams"></a>在 Microsoft Teams 中创建组织范围的团队

组织范围的团队为中小型组织中的每个人提供了自动加入单个协作团队的方法。

使用组织范围的团队，全局管理员可以轻松创建一个公共团队来将组织中的所有用户包含进来，并在用户加入和离开组织时在 Active Directory 中更新成员身份。 只有全局管理员可以创建组织范围的团队，当前组织范围的团队仅限于不超过5000用户的组织。 每个租户也有五个组织范围的团队的限制。 如果满足这些要求，则当全局管理员在创建团队时选择“**从头开始构建团队**”时，将看到“**组织范围**”选项。 

![用于创建组织范围团队的“组织范围”选项的屏幕截图](media/create-org-wide-team.png "用于创建组织范围团队的“组织范围”选项的屏幕截图")

创建组织范围的团队后，所有全局管理员和团队服务管理员都将添加为团队所有者，并将所有活动用户添加为团队成员。 未经授权的用户也将添加到团队。 当未经授权的用户第一次登录团队时，将为该用户分配 Microsoft 团队探索性许可证。 若要了解有关探索性许可证的详细信息，请参阅 [管理 Microsoft 团队探索性许可证](teams-exploratory.md)。 

以下类型的帐户无法添加到组织范围的团队：

- 阻止登录的帐户
- 来宾用户
- 服务帐户
- 会议室或设备帐户
- 共享邮箱支持的帐户

当组织目录更新为包含新的活动用户时，或者如果用户不再在公司工作并且其帐户已被禁用，系统会自动同步更改，并从团队中添加或删除用户。 团队成员无法离开组织范围的团队。 作为团队所有者，你可以根据需要手动添加或删除用户。

> [!NOTE]
> - 如果在创建团队时看不到 **组织范围** 选项，并且您是全局管理员，则你可能已达到5个组织范围的团队限制，或者你的组织可能超过了5000个成员的当前大小限制。 我们想要在未来增加此限制。 对于 Teams 教育版，组织范围的团队不可用。
> - 未出现在会议室列表中的会议室、设备和资源帐户可能会添加或同步到组织范围的团队。 团队所有者可轻松从团队中删除这些帐户。
> - 系统添加或删除成员的所有操作均发布在常规频道中。 该频道还将在 Teams 客户端中标记为具有新活动。
> - 如果你的组织刚开始使用 Teams，且用户数不超过 5,000，我们将自动为贵组织创建一个组织范围的团队。 团队名称将反映租户名称，并且具有常规频道。 全局管理员可像任何其他团队一样编辑此团队。 

## <a name="best-practices"></a>最佳做法

若要充分利用组织范围的团队，建议团队所有者执行以下操作。

### <a name="allow-only-team-owners-to-post-to-the-general-channel"></a>仅允许团队所有者发布到常规频道

通过仅允许团队所有者发布到常规频道，减少频道中的杂乱信息。 转到团队，找到 "常规" 频道，然后选择 " **̇̇̇更多选项**  >  **管理频道**"。 在 " **通道设置** " 选项卡上，单击 " **权限**"，然后选择 " **仅所有者可以发布邮件**"。

### <a name="turn-off-team-and-team-name-mentions"></a>关闭 @团队和 @[团队名称]提及

 减少 @提及，以防止它们使整个组织超载。 转到团队并单击“**˙˙˙ 更多选项**” > “**管理团队**”。 在“**设置**”选项卡上，单击“<strong>@提及</strong>”>关闭“**向成员显示用于 @团队或 @[团队名称]的选项**”。 

### <a name="automatically-show-important-channels"></a>自动显示重要频道

显示重要频道，以确保组织中的每个人都能参与特定对话。 若要了解详细信息，请参阅[为整个团队自动收藏频道](https://support.office.com/article/auto-favorite-channels-for-the-whole-team-a948272c-5aa5-429c-863c-4e1e1cd6b0f6)。 

### <a name="set-up-channel-moderation"></a>设置频道审阅

考虑设置频道审阅并向某些团队成员提供审阅人功能。 （设置审阅后，团队所有者将自动获得审阅人功能。）审阅人可以控制谁能够在频道中发布新帖子、添加和删除审阅人、控制团队成员是否可以回复现有频道消息，以及控制机器人和连接器是否可以提交频道消息。 有关详细信息，请参阅[在 Microsoft Teams 中设置和管理频道审核](manage-channel-moderation-in-teams.md)。

### <a name="remove-accounts-that-might-not-belong"></a>删除可能不属于成员的帐户

即使成员不能离开组织范围的团队，作为团队所有者，你可以通过删除不属于的帐户来管理团队名单。 **请确保使用 Teams 从组织范围的团队中删除用户**。 如果使用其他方法删除用户（如 Microsoft 365 管理中心或 Outlook 中的组），则该用户可能会添加回组织范围的团队。

## <a name="faq"></a>常见问题

### <a name="is-there-a-way-to-create-an-org-wide-team-other-than-using-the-teams-client"></a>除了使用 Teams 客户端之外，是否有其他方法可以创建组织范围的团队？

全局管理员只能使用 Teams 客户端创建组织范围的团队。 如果贵组织将创建团队限制为使用 PowerShell，则建议的解决方法是将全局管理员添加到可以创建团队的用户安全组中。 有关详细信息，请参阅 [管理可以创建组的人员](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-creation-of-groups)。

如果这样做行不通，则可以使用 PowerShell 创建公共团队，并将全局管理员添加为团队所有者。 然后，让全局管理员单击团队名称旁边的“**更多选项**”，单击“**编辑团队**”，然后将隐私更改为“**组织范围 - 将自动添加你的组织中的所有人**”。 请注意，只有团队所有者才能访问“**编辑团队**”选项，并且只有全局管理员才能看到“**组织范围**”选项。

### <a name="is-there-a-way-to-convert-an-existing-team-to-an-org-wide-team"></a>可通过某种方式将现有团队转换为组织范围的团队吗？

全局管理员可通过在 Teams 客户端中编辑来将现有团队转换为组织范围的团队。 转到团队名称，单击“**更多选项**” > “**编辑团队**”。

### <a name="can-i-create-an-org-wide-team-using-a-team-template"></a>是否可以使用团队模板创建组织范围的团队？

团队模板不能用于创建组织范围的团队。 此功能的工作当前正在进行。 

## <a name="see-also"></a>另请参阅

观看有关 [在 Microsoft 团队中创建公司范围的团队](https://support.office.com/article/037bb27a-bcc9-48fe-8d72-44d9482420a3)的视频。
