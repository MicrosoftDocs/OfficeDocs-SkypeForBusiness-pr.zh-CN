---
title: 在Teams管理中心管理表扬应用
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.reviewer: rjam
audience: admin
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
description: 了解如何在Microsoft Teams管理中心管理表扬应用。
ms.openlocfilehash: 364fb60b6a729062e358685426acd98704c7ac02
ms.sourcegitcommit: bf0071417188b33fc23e2a420187da5024d4bd40
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2022
ms.locfileid: "63442678"
---
# <a name="manage-the-praise-app-in-the-microsoft-teams-admin-center"></a>在Microsoft Teams管理中心管理表扬应用

Microsoft Teams中的表扬应用可帮助用户向组织或课堂成员表示欣赏。 表扬的徽章旨在帮助识别Teams用户所做的各种工作，从教师到一线工作人员。 若要了解详细信息，请查看[向用户发送表扬](https://support.microsoft.com/office/send-praise-to-people-50f26b47-565f-40fe-8642-5ca2a5ed261e)。

管理员必须具有Teams许可证才能访问此功能。 如果尝试在没有Teams许可证的情况下访问此功能，则会收到一条错误消息。

> [!NOTE]
> 表扬应用适用于GCC云环境，但不适用于 GCC High 或 DoD。

## <a name="enable-or-disable-praise-in-your-organization"></a>在组织中启用或禁用表扬

默认情况下，表扬为组织中的所有Teams用户启用。 你可以在 Microsoft Teams 管理中心的[管理应用](manage-apps.md)页面在组织级别关闭或打开此应用。

:::image type="content" source="media/manage-praise-app-admin-center.png" alt-text="Teams管理中心“表扬应用详细信息”页的屏幕截图，其中显示了“状态”切换。":::

1. 在 Microsoft Teams 管理中心的左侧导航中，转到“**Teams 应用**” > “**管理应用**”。
2. 在应用列表中，搜索表扬应用，选择它，然后将 **状态** 切换为 **“已阻止**”或 **“允许**”。

请记住，此设置会影响Teams中Viva Insights应用中的表扬应用和表扬功能。

## <a name="enable-or-disable-praise-for-specific-users-in-your-organization"></a>为组织中的特定用户启用或禁用表扬

若要允许或阻止组织中的特定用户使用表扬，请确保在“[管理应用](manage-apps.md)”页上为组织启用表扬。 然后创建自定义应用权限策略并将其分配给这些用户。 要了解详细信息，请参阅[在 Teams 中管理应用权限策略](teams-app-permission-policies.md)。

## <a name="badges"></a>徽章

下面是表扬中的默认徽章集。 Teams组织中的用户可以使用这些锁屏提醒来识别他们的对等方在工作上超越。

:::image type="content" source="media/default-set-praise.png" alt-text="默认徽章集中的徽章图像。":::

> [!NOTE]
> 从 2022 年 2 月开始，人们只能发送和接收默认徽章。 自定义徽章不再可用，自定义徽章的选项已从Teams管理中心删除。

## <a name="related-articles"></a>相关文章

[在Microsoft Teams管理中心管理应用](manage-apps.md)
