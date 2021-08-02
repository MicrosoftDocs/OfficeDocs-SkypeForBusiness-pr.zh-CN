---
title: 在 Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: phlouie
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何在组织中创建和管理组织范围内的Teams，为小型到中型组织中的每个人提供自动协作方式。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 99847583e547deeb2732b88036d4a7a469590ba9
ms.sourcegitcommit: ad215c120d7e550a7aebf2e1bb620c69039e5d8d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/01/2021
ms.locfileid: "53679737"
---
# <a name="create-an-organization-wide-team-in-microsoft-teams"></a>在 Microsoft Teams

组织范围的团队为小型到中型组织中每个人提供自动方式，以成为单个协作团队的一部分。

使用组织范围的团队，全局管理员可以轻松地创建具有以下特征的公共团队：
- 拉取组织中每个用户 
- 当用户加入和离开组织时，使 Active Directory 的成员身份保持最新。

只有全局管理员可以创建组织范围的团队。 目前，组织范围内的团队仅限于用户数不超过 10，000 的组织。 每个租户还有 5 个组织范围的团队的限制。 创建团队时，如果满足这些要求，全局管理员在选择"从头开始构建团队"时，将看到"组织范围"**作为选项**。 

![用于创建组织范围的团队的"组织范围"选项的屏幕截图](media/create-org-wide-team.png "用于创建组织范围的团队的&quot;组织范围&quot;选项的屏幕截图")

创建组织范围的团队时，所有全局管理员Teams服务管理员添加为团队所有者，所有活动用户都添加为团队成员。 未经授权的用户也将添加到团队。 未授权用户首次登录 Teams时，会为该用户分配Microsoft Teams探索许可证。 若要详细了解探索许可证，请查看管理 Microsoft Teams[探索许可证](teams-exploratory.md)。 

以下类型的帐户不会添加到组织范围的团队：

- 阻止登录的帐户
- 来宾用户
- 资源或服务帐户 (例如，与自动助理和呼叫队列关联的帐户) 
- 会议室或设备帐户
- 共享邮箱支持的帐户

当组织的目录更新为包含新的活动用户或禁用不再在公司工作的用户帐户时，将自动同步更改，并且会向团队添加或删除用户。 团队成员不能离开组织范围内的团队。 作为团队所有者，你可以根据需要手动添加或删除用户。

> [!NOTE]
> - 如果在创建团队时看不到"组织范围"选项，并且你是全局管理员，则你可能已达到组织范围的五个团队限制，或者你的组织可能超过 10，000 个成员的当前大小限制。 我们想要在未来增加此限制。 对于 Teams 教育版，组织范围的团队不可用。
> - 非会议室列表、设备和资源帐户的一部分可能会添加或同步到组织范围的团队。 团队所有者可轻松从团队中删除这些帐户。
> - 系统添加或删除成员的所有操作均发布在常规频道中。 该频道还将在 Teams 客户端中标记为具有新活动。
> - 如果你的组织是新用户且用户数不超过 5，000 Teams，我们会自动为组织创建组织范围的团队。 团队名称将反映租户名称，并且具有常规频道。 全局管理员可像任何其他团队一样编辑此团队。

## <a name="best-practices"></a>最佳做法

若要在组织范围内最了解团队，我们建议团队所有者执行以下任务：

### <a name="allow-only-team-owners-to-post-to-the-general-channel"></a>仅允许团队所有者发布到常规频道

通过仅允许团队所有者发布到常规频道，减少频道中的杂乱信息。 

1. 转到团队，找到"常规"频道，然后选择 **"""更多选项""**  >  **管理频道"。** 
2. 在"**通道设置"** 选项卡上，单击 **"权限"，** 然后选择"**仅所有者可以发布消息"。**

### <a name="turn-off-team-and-team-name-mentions"></a>关闭 @团队和 @[团队名称]提及

减少 @提及，以防止它们使整个组织超载。 

1. 转到团队并单击“**˙˙˙ 更多选项**” > “**管理团队**”。 
2. 在“**设置**”选项卡上，单击“<strong>@提及</strong>”>关闭“**向成员显示用于 @团队或 @[团队名称]的选项**”。 

### <a name="automatically-show-important-channels"></a>自动显示重要频道

显示重要频道，以确保组织中的每个人都能参与特定对话。 若要了解详细信息，请参阅[为整个团队自动收藏频道](https://support.office.com/article/auto-favorite-channels-for-the-whole-team-a948272c-5aa5-429c-863c-4e1e1cd6b0f6)。 

### <a name="set-up-channel-moderation"></a>设置频道审阅

考虑设置频道审阅并向某些团队成员提供审阅人功能。  (设置审查时，将自动为团队所有者提供审阅者功能。) 审查器可以：

- 控制谁可以在频道中启动新帖子
- 添加和删除审阅人
- 控制团队成员是否可以回复现有频道消息
- 控制机器人和连接器是否可以提交通道消息。

有关详细信息，请参阅[在 Microsoft Teams 中设置和管理频道审核](manage-channel-moderation-in-teams.md)。

### <a name="remove-accounts-that-might-not-belong"></a>删除可能不属于成员的帐户

即使成员无法离开组织范围的团队，作为团队所有者，您也可以通过删除不属于的帐户来管理团队名单。 **请确保使用 Teams 从组织范围的团队中删除用户**。 如果使用另一种方法删除用户（例如 Microsoft 365 管理中心 或 Outlook 中的组，用户可能会重新添加到组织范围的团队。

## <a name="faq"></a>常见问题

### <a name="is-there-a-way-to-create-an-organization-wide-team-other-than-using-the-teams-client"></a>除了使用客户端外，是否还有一种方法可以创建组织范围的Teams？

全局管理员只能使用全局客户端创建组织范围的Teams团队。 如果贵组织将创建团队限制为使用 PowerShell，则建议的解决方法是将全局管理员添加到可以创建团队的用户安全组中。

有关详细信息，请参阅 [管理可以创建组的人](/microsoft-365/admin/create-groups/manage-creation-of-groups)。

如果无法使用此解决方法，可以使用 PowerShell 创建公共团队，并添加全局管理员作为团队所有者。 然后，让全局管理员单击团队名称旁边的“**更多选项**”，单击“**编辑团队**”，然后将隐私更改为“**组织范围 - 将自动添加你的组织中的所有人**”。 

> [!NOTE]
> 只有团队所有者可以访问" **编辑团队"** 选项，只有全局管理员才能看到 **"组织范围"** 选项。

### <a name="is-there-a-way-to-convert-an-existing-team-to-an-organization-wide-team"></a>是否有方法可将现有团队转换为组织范围内的团队？

全局管理员可以在客户端中编辑现有团队，将其转换为Teams团队。 转到团队名称，单击“**更多选项**” > “**编辑团队**”。

### <a name="can-i-create-an-organization-wide-team-using-a-team-template"></a>我可以使用团队模板创建组织范围内的团队吗？

团队模板不能用于创建组织范围内的团队。 此功能当前正在处理中。 

## <a name="see-also"></a>另请参阅

观看有关在[Microsoft Teams 创建公司范围的团队的视频](https://support.office.com/article/037bb27a-bcc9-48fe-8d72-44d9482420a3)。
