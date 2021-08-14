---
title: Microsoft 365 电话系统 – 虚拟用户许可证
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
localization_priority: Normal
ms.custom:
- Licensing
- LIL_Placement
- seo-marvel-apr2020
description: 了解如何向组织的资源电话系统免费用户许可证或付费电话系统用户许可证。
ms.openlocfilehash: 2481d119bd1f053f0836c57d237d34edfbf6e260d9b8be9b9f7d40033dc6282a
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54328937"
---
# <a name="microsoft-365-phone-system--virtual-user-license"></a>Microsoft 365 电话系统 – 虚拟用户许可证

具有已电话系统的用户的组织可以将免费 Microsoft 365 电话系统 – 虚拟用户许可证或付费电话系统用户许可证分配给资源帐户。 呼叫计划不是必需的。 所有自动助理或呼叫队列都需要关联的资源帐户。 需要电话号码的资源帐户需要免费Microsoft 365 电话系统 – 虚拟用户许可证或付费电话系统用户许可证，然后才能将电话号码应用到资源帐户。

> [!TIP]
> 对于将用于嵌套自动助理或未分配电话号码的呼叫队列的资源帐户，不需要许可证。 有关参考，请参阅下图： 

![虚拟用户许可证](../media/resource-account.png)

## <a name="virtual-user-license-allocation"></a>虚拟用户许可证分配

根据组织的总体Microsoft 365 电话系统分配虚拟用户许可证。 具有至少一个许可证（包括电话系统或已添加电话系统）的任何组织都提供 25 个虚拟用户许可证，无需付费。 在组织中添加 10 电话系统用户许可证时，会再添加一Microsoft 365 电话系统 - 虚拟用户许可证变为可用。

> [!NOTE]
> 电话系统是一个附加许可证，适用于 Microsoft 365 Office 365 E1 E3。 电话系统许可证中也包含Microsoft 365 E5、Office 365 E5和Microsoft 365 商务语音许可证。

如果组织在创建自动助理或呼叫队列节点时Microsoft 365 电话系统免费许可证 – 虚拟用户许可证，仍可将付费 电话 系统许可证与资源帐户一起使用。 大多数组织将基于缩放计划拥有足够的虚拟用户许可证。 

### <a name="license-allocation-example"></a>许可证分配示例

Contoso， Inc. 购买了 600 个许可证，其中包括电话系统 (每个员工一) 。 为 Contoso 分配了初始 25 + 60 Microsoft 365 电话系统 – 虚拟用户许可证，总共 85 个。 其组织有 90 个呼叫队列和具有电话号码的自动助理。 他们需要分配所有Microsoft 365 电话系统 – 虚拟用户许可证，并获取五个常规价格电话系统许可证。

Contoso 应考虑重新设计自动助理和呼叫队列系统。 如果他们使用的电话号码较少，嵌套的节点也更多，并且不需要电话号码，则简化实现并降低成本。

## <a name="how-to-buy-microsoft-365-phone-system--virtual-user-licenses"></a>如何购买 Microsoft 365 电话系统 – 虚拟用户许可证

1. 登录到 Microsoft 365 管理中心。
2. 转到 **计费**  >  **购买服务**  >  **附加内容**
3. 滚动到末尾，找到 **"Microsoft 365 电话系统 – 虚拟用户"** 许可证。 选择"**立即购买"。**

> [!NOTE]
> 请记住，即使许可证的成本  **为零** ，仍必须购买许可证。

## <a name="change-an-existing-resource-account-to-use-a-microsoft-365-phone-system--virtual-user-license"></a>更改现有资源帐户以使用 Microsoft 365 电话系统 – 虚拟用户许可证

如果决定将资源帐户上的许可证从 电话系统 许可证切换到 Microsoft 365 电话系统 – 虚拟用户许可证：

1. 获取新的 Microsoft 365 电话系统 – 虚拟用户许可证。
2. 按照中心内的链接Microsoft 365 管理[将用户移到其他订阅](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription)。

> [!WARNING]
> 始终删除完整的电话系统许可证，并在同一许可证Microsoft 365 电话系统分配"虚拟用户"许可证。 如果删除旧许可证，请保存帐户更改，添加新许可证，然后再次保存帐户设置，资源帐户可能不再正常运行。 如果发生这种情况，建议为虚拟用户许可证创建Microsoft 365 电话系统资源帐户，并删除损坏的资源帐户。 

## <a name="related-information"></a>相关信息

[自动助理和呼叫队列服务更新](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521)

[在 Microsoft Teams 中管理资源帐户](../manage-resource-accounts.md)