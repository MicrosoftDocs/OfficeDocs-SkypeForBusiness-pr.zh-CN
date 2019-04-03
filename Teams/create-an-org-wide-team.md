---
title: 在 Microsoft Teams 中创建组织范围的团队
author: LanaChin
ms.author: v-lanac
ms.reviewer: phlouie
manager: serdars
ms.date: 09/27/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: 了解如何创建和管理团队中的组织范围团队。
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 625f3ef560dd1c994afa0a566fedc3ad0fbe1143
ms.sourcegitcommit: c011e4ab6f936a9e26d304835634293b1cedc57d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/03/2019
ms.locfileid: "31043402"
---
# <a name="create-an-org-wide-team-in-microsoft-teams"></a>在 Microsoft Teams 中创建组织范围的团队

组织范围团队提供的小型到中型组织成为进行协作的单个工作组中的每个人的自动方法。 
 
与组织范围团队全局管理员可以轻松创建拉入组织中的每个用户保留成员的最新的 Active Directory 作为用户加入和离开组织的公共团队。 仅全局管理员可创建组织范围团队和当前组织范围团队限于与不超过 5,000 名用户的组织。 如果满足这些要求，全局管理员将作为选项看到**组织范围内**，当用户选择**建立工作组从头**创建团队时。 

![要创建一个组织范围团队的组织范围选项的屏幕截图](media/create-org-wide-team.png "要创建一个组织范围团队的组织范围选项的屏幕截图")

创建一个组织范围团队后，所有的全局管理员添加作为团队所有者和所有活动用户将添加为工作组成员。 为团队、 来宾用户和大多数聊天室禁用的用户不会添加到团队。 贵组织的目录将更新以包括新的活动用户或更改如果用户在贵公司不再起作用，并且禁用团队许可证，将自动同步，并添加或从组中删除用户。 工作组成员都能使组织范围团队。 作为团队所有者，您可以手动添加或删除用户，如果需要。

> [!NOTE]
> - 如果您是全局管理员创建团队时，看不到**组织范围**选项，该功能仍可能推出或您的组织可能具有多台 5,000 成员的当前大小限制。 我们希望在将来增加此限制。
> - 可能添加或与组织范围团队同步聊天室的不属于会议室列表、 equipment 和资源帐户。 团队所有者可以轻松地从组中删除这些帐户。

## <a name="best-practices"></a>最佳做法
若要充分利用您的组织范围团队，建议团队所有者执行下列操作。

### <a name="allow-only-team-owners-to-post-to-the-general-channel"></a>允许仅团队发布到常规通道所有者
减少通道干扰具有仅团队所有者发布到常规通道。 转接至小组和单击**更多选项 （...）** > **管理团队**。 在**设置**选项卡上，单击**成员权限**> 选择**仅所有者可以发布消息**。
### <a name="turn-off-team-and-team-name-mentions"></a>关闭 @team 和 @ 提及 [工作组名称]
 减少 @mentions 以防止它们重载整个组织。 转接至小组和单击**更多选项 （...）** > **管理团队**。 在**设置**选项卡，单击 **@mentions** > 关闭**显示 @team 选项的成员或 @[工作组名称]**。 
### <a name="automatically-favorite-important-channels"></a>自动最喜爱的重要通道
 最喜爱的重要通道，以确保您的组织中的每个人参与了一个特定的对话。 若要了解详细信息，请参阅[自动收藏夹通道，整个团队](https://support.office.com/article/auto-favorite-channels-for-the-whole-team-a948272c-5aa5-429c-863c-4e1e1cd6b0f6)。

### <a name="remove-accounts-that-might-not-belong"></a>删除可能不属于的帐户
即使成员无法保留组织范围团队，作为团队所有者，您可以通过删除不属于帐户管理团队名单。 请确保您使用团队从您的组织范围团队中移除用户。  如果您使用另一种方式删除用户，如 Microsoft 365 管理中心或从组在 Outlook 中，用户可能会重新添加到组织范围团队。 

## <a name="faq"></a>常见问题解答

### <a name="is-there-a-way-to-create-an-org-wide-team-other-than-using-the-teams-client"></a>是否存在一种方法创建一个组织范围团队之外使用团队客户端？ 

全局管理员使用团队客户端只能创建一个组织范围团队。 如果您的组织限制使用 PowerShell 创建团队，建议的解决方法是将您的全局管理员添加到的用户可以创建工作组的安全组。 有关详细信息，请参阅[管理哪些人可以创建 Office 365 组](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups)。 

如果这不是一个选项，您可以创建公用工作组使用 PowerShell 并将全局管理员添加作为团队所有者。 这样，具有团队名称旁边单击**˙˙˙ 更多选项**，单击**编辑团队**，然后将隐私更改为**组织范围的组织中的所有人都将自动添加**的全局管理员。 请注意，仅团队所有者可以访问**编辑团队**选项和仅全局管理员可以查看**组织范围内**的选项。

### <a name="is-there-a-way-to-convert-an-existing-team-to-an-org-wide-team"></a>有一种方法可将现有团队转换为组织范围团队吗？

全局管理员可以将现有团队转换为编辑团队客户端中的组织范围团队。
转到工作组名称，然后单击更多选项...（省略号） > 编辑团队。
