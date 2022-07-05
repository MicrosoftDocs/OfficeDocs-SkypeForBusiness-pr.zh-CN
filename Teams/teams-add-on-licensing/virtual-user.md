---
title: Microsoft Teams 电话资源帐户许可证
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: waseemh
ms.topic: reference
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.custom:
- Licensing
- LIL_Placement
- seo-marvel-apr2020
description: 了解如何将免费 Teams 电话资源帐户许可证或付费Teams 电话标准版用户许可证分配到组织中的资源帐户。
ms.openlocfilehash: 07b47b2ec5b24b1edbfb599dc5a61e96169a02a2
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/05/2022
ms.locfileid: "66615398"
---
# <a name="microsoft-teams-phone-resource-account-licenses"></a>Microsoft Teams 电话资源帐户许可证

拥有Teams 电话标准版或 Teams 电话呼叫计划许可用户的组织可以向 *资源帐户分配免费Microsoft Teams 电话资源帐户* 许可证或 *付费Teams 电话标准版* 用户许可证。 Microsoft 呼叫计划并不总是必需的 (请参阅 [Teams 自动助理计划](../plan-auto-attendant-call-queue.md#prerequisites) ，并在将呼叫转移到外部电话号码) 时为先决条件呼叫队列。

所有自动助理和呼叫队列都需要关联的资源帐户。 需要电话号码的资源帐户需要免费 *Microsoft Teams 电话资源帐户* 许可证或 *付费Teams 电话标准版* 用户许可证，然后才能将电话号码应用到资源帐户。

> [!TIP]
> 对于将用于嵌套自动助理或未分配电话号码的呼叫队列的资源帐户，无需许可证。 请参阅下图供参考。

## <a name="resource-account-license-allocation"></a>资源帐户许可证分配

组织 *分配Microsoft Teams 电话资源帐户* 许可证，具体取决于其整体大小。 任何组织具有至少一个具有 Teams 电话系统功能的许可证（包括具有通话套餐许可证的 Teams 电话标准版 和 Teams 电话）都具有 25 个资源帐户许可证，无需付费。 当你在组织中添加 10 个具有通话套餐用户许可证的 Teams 电话标准版 或 Teams 电话时，将再添加一个 *Microsoft Teams 电话资源帐户* 许可证。

> [!NOTE]
> Teams 电话标准版和 Teams 电话通话套餐是所有 Microsoft 365 订阅者的附加许可证。 Teams 电话标准版许可证也作为Microsoft 365 E5计划的一部分包含在内。

如果你的组织在创建自动助理或调用队列节点时使用免费 *Microsoft Teams 电话资源帐户* 许可证，你仍然可以将付费 *Teams 电话标准版* 许可证与资源帐户一起使用。 大多数组织将根据缩放计划获得足够的资源帐户许可证。

### <a name="license-allocation-example"></a>许可证分配示例

Contoso， Inc. 为每个员工) 购买了 600 个许可证，其中包括电话系统 (一个。 Contoso 分配了初始 25 加 60 *Microsoft Teams 电话资源帐户* 许可证，总共 85 个。 他们的组织有 90 个呼叫队列和具有电话号码的自动助理。 他们需要分配所有 *Microsoft Teams 电话资源帐户* 许可证，并获取五个固定价格 *的Teams 电话标准版* 许可证。

Contoso 应考虑重新设计自动助理和调用队列系统。 如果他们使用更少的电话号码和更多不需要电话号码的嵌套节点，则可以简化实现并降低成本。

## <a name="how-to-buy-microsoft-teams-phone-resource-account-licenses"></a>如何购买Microsoft Teams 电话资源帐户许可证

1. 登录到 Microsoft 365 管理中心。
2. 转到 **“** > 计费 **购买服务** > **”加载项**。
3. 滚动查找 **Microsoft Teams 电话资源帐户** 许可证。 **立即选择“购买**”。

   > [!NOTE]
   > 请记住，即使许可证的成本为零，仍必须 **购买** 该许可证。

## <a name="change-an-existing-resource-account-to-use-a-microsoft-teams-phone-resource-account-license"></a>更改现有资源帐户以使用Microsoft Teams 电话资源帐户许可证

如果决定将资源帐户上的许可证从 *Teams 电话标准版* 许可证切换到 *Microsoft Teams 电话资源帐户* 许可证：

1. 获取新的 *Microsoft Teams 电话资源帐户* 许可证。
2. 按照Microsoft 365 管理中心中的链接步骤[将用户移动到其他订阅](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription)。

> [!WARNING]
> 始终删除完整的 *Teams 电话标准版* 许可证，并在同一许可证活动中分配 *Microsoft Teams 电话资源帐户* 许可证。 如果删除旧许可证，请保存帐户更改，添加新许可证，然后再次保存帐户设置，资源帐户可能不再按预期运行。 如果发生这种情况，建议为 *Microsoft Teams 电话资源帐户* 许可证创建新的资源帐户，并删除损坏的资源帐户。

## <a name="related-information"></a>相关信息

[自动助理和呼叫队列服务更新](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521)

[在 Microsoft Teams 中管理资源帐户](../manage-resource-accounts.md)
