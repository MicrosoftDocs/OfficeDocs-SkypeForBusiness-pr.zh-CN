---
title: 在 Teams 管理中心管理“表扬”应用
author: LanaChin
ms.author: v-lanachin
manager: samanro
ms.reviewer: rjam
audience: admin
ms.topic: how-to
ms.service: msteams
ms.localizationpriority: medium
description: 了解如何在 Microsoft Teams 管理中心中管理“表扬”应用。
ms.collection:
- M365-collaboration
- m365-frontline
- tier2
- highpri
ms.openlocfilehash: 9b1155560c0f901b88d3983e2ff3738e5ffa6e47
ms.sourcegitcommit: 54c691bd34980a47a5ebf58555529a618a8cada7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2022
ms.locfileid: "69251765"
---
# <a name="manage-the-praise-app-in-the-microsoft-teams-admin-center"></a>在 Microsoft Teams 管理中心中管理表扬应用

Microsoft Teams 中的“表扬”应用可帮助用户向组织或课堂成员表示欣赏。 “表扬”中的徽章旨在帮助识别 Teams 用户所做的各种工作（从教师到一线员工）所做的工作。 若要了解详细信息，请查看 [向他人发送赞美](https://support.microsoft.com/office/send-praise-to-people-50f26b47-565f-40fe-8642-5ca2a5ed261e)。

管理员必须具有 Teams 许可证才能访问此功能。 如果尝试在没有 Teams 许可证的情况下访问此功能，将收到错误消息。

> [!NOTE]
> “表扬”应用适用于 GCC 云环境，但不适用于 GCC High 或 DoD。

## <a name="enable-or-disable-praise-in-your-organization"></a>在组织中启用或禁用“表扬”

默认情况下，为组织中的所有 Teams 用户启用“表扬”。 你可以在 Microsoft Teams 管理中心的[管理应用](manage-apps.md)页面在组织级别关闭或打开此应用。

:::image type="content" source="media/manage-praise-app-admin-center.png" alt-text="Teams 管理中心中“表扬应用详细信息”页的屏幕截图，其中显示了“状态”切换。":::

1. 在 Microsoft Teams 管理中心的左侧窗格中，转到“**Teams 应用**” > “**管理应用**”。
2. 在应用列表中，搜索“表扬”应用，将其选中，然后将 **“状态”** 切换开关切换为 **“已阻止** ”或 **“允许**”。

请记住，此设置会影响 Teams Viva Insights 应用中的“表扬”应用和“表扬”功能。

如果将状态设置为 **“已阻止**”，Teams 的“表扬”应用在几分钟内会被阻止。 但是，Viva Insights中的“赞美”可能需要 7-9 天才能被阻止。

## <a name="enable-or-disable-praise-for-specific-users-in-your-organization"></a>为组织中的特定用户启用或禁用“表扬”

若要允许或阻止组织中的特定用户使用“表扬”，请确保在 [“管理应用](manage-apps.md) ”页上为组织启用“表扬”。 然后为应用权限创建自定义策略并将其分配给这些用户。 要了解详细信息，请参阅[在 Teams 中管理应用权限策略](teams-app-permission-policies.md)。

## <a name="composer"></a>作曲家

组织中的 Teams 用户可以使用表扬作曲器来识别其同行，以超越其工作。 在制作信息时，他们可以从 14 个&mdash;标题（如 **勇气**、 **乐观**、 **善良的心** 和 **创造性**&mdash;）中选择，以表彰同事的贡献。

:::image type="content" source="media/praise.png" alt-text="表扬作曲家的屏幕截图。":::

## <a name="related-articles"></a>相关文章

[在 Microsoft Teams 管理中心中管理应用](manage-apps.md)
