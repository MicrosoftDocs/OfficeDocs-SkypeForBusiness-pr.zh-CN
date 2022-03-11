---
title: Microsoft Teams 电话标准 – 虚拟用户许可证
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
description: 了解如何向组织的资源Teams 电话免费标准 - 虚拟用户Teams 电话付费标准用户许可证。
ms.openlocfilehash: 542d80a8cb463df01e6e232454b2454a939a457b
ms.sourcegitcommit: ff975c21725e1812e6db8fc9fe37de1362f168c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/11/2022
ms.locfileid: "63435726"
---
# <a name="microsoft-teams-phone-standard--virtual-user-licenses"></a>Microsoft Teams 电话标准 – 虚拟用户许可证

具有 Teams 电话 标准版Teams 电话或具有呼叫计划许可的用户的组织可以将免费 *Microsoft Teams 电话 Standard – Virtual User* 许可证或付费的 Teams 电话 Standard 用户许可证分配给资源帐户。 Microsoft 呼叫计划并非始终是必需的 (请参阅规划自动助理Teams呼叫队列[](../plan-auto-attendant-call-queue.md#prerequisites)，了解将呼叫转接到外部电话号码时的先决条件) 。

所有自动助理和呼叫队列都需要关联的资源帐户。 需要电话号码的资源帐户需要免费 Microsoft Teams 电话 标准 *–* 虚拟用户许可证或付费 *Teams 电话 标准* 版用户许可证，然后才能将电话号码应用到资源帐户。

> [!TIP]
> 对于将用于嵌套自动助理或未分配电话号码的呼叫队列的资源帐户，不需要许可证。 有关参考，请参阅下图。

:::image type="content" alt-text="虚拟用户许可证。" source="../media/resource-account.png":::

## <a name="virtual-user-license-allocation"></a>虚拟用户许可证分配

根据组织的总体大小 *Microsoft Teams 电话标准 -* 虚拟用户许可证。 任何具有至少一个具有 Teams 电话系统 许可证的组织（包括 Teams 电话 Standard 和 Teams 电话 具有呼叫计划许可证的组织）都提供 25 个虚拟用户许可证，无需付费。 在组织中添加 10 个Teams 电话套餐或Teams 电话套餐的用户许可证时，会再添加一Microsoft Teams 电话 *标准 - 虚拟用户* 许可证可用。

> [!NOTE]
> Teams 电话"标准Teams 电话"和"呼叫计划"是可供所有订阅者Microsoft 365许可证。 Teams 电话标准版许可证也作为计划Microsoft 365 E5一部分。

如果组织在创建自动助理或呼叫队列节点 *Microsoft Teams 电话* 免费标准 – 虚拟用户许可证，则仍可将付费 Teams 电话 *标准* 版许可证与资源帐户一同使用。 大多数组织将基于缩放计划拥有足够的虚拟用户许可证。

### <a name="license-allocation-example"></a>许可证分配示例

Contoso， Inc. 购买了 600 个许可证，其中包括电话系统 (每个员工的许可证) 。 Contoso 分配了初始 25+ 60 Microsoft Teams 电话 *标准 – 虚拟用户* 许可证，总共 85 个。 其组织有 90 个呼叫队列和具有电话号码的自动助理。 他们需要分配所有标准Microsoft Teams 电话 *- 虚拟用户* 许可证，并获取五个标准Teams 电话 *价格*。

Contoso 应考虑重新设计自动助理和呼叫队列系统。 如果他们使用的电话号码较少，嵌套的节点也更多，并且不需要电话号码，则简化实现并降低成本。

## <a name="how-to-buy-microsoft-teams-phone-standard--virtual-user-licenses"></a>如何购买标准Microsoft Teams 电话 – 虚拟用户许可证

1. 登录到 Microsoft 365 管理中心。
2. 转到 **BillingPurchase** >  **servicesAdd-ons** > 。
3. 滚动到末尾，找到"**Microsoft Teams 电话标准 – 虚拟用户"** 许可证。 选择" **立即购买"**。

   > [!NOTE]
   > 请记住，即使许可证的成本 **为零** ，仍必须购买许可证。

## <a name="change-an-existing-resource-account-to-use-a-microsoft-teams-phone-standard--virtual-user-license"></a>将现有资源帐户更改为使用 Microsoft Teams 电话 标准 – 虚拟用户许可证

如果决定将资源帐户上的许可证从标准Teams 电话切换到 Microsoft Teams 电话 *标准 – 虚拟用户* 许可证：

1. 获取新的 Microsoft Teams 电话 标准 – 虚拟用户许可证。
2. 按照中心内的链接Microsoft 365 管理将[用户移到其他订阅](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription)。

> [!WARNING]
> 始终 *删除完整的标准* Teams 电话许可证，并在同一许可证Microsoft Teams 电话 *分配标准 –* 虚拟用户许可证。 如果删除旧许可证，请保存帐户更改，添加新许可证，然后再次保存帐户设置，资源帐户可能不再正常运行。 如果发生这种情况，建议为"标准 - 虚拟用户"Microsoft Teams 电话 *一* 个新的资源帐户，并删除损坏的资源帐户。

## <a name="related-information"></a>相关信息

[自动助理和呼叫队列服务更新](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521)

[在 Microsoft Teams 中管理资源帐户](../manage-resource-accounts.md)
