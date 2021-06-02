---
title: 使用 Microsoft Teams 范围目录搜索
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 06/21/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 了解如何使用Microsoft Teams范围目录搜索来提供目录的自定义视图。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1048b6451163cd7b0cdbcd3f52e48c6b0f4811d1
ms.sourcegitcommit: 90615674e9703aa5ea32be64ab3638aa30e83127
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/02/2021
ms.locfileid: "52717793"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a>使用 Microsoft Teams 范围目录搜索

Microsoft Teams范围的目录搜索允许组织创建虚拟边界，控制用户如何查找和与组织中其他用户通信。 

Microsoft Teams允许组织向用户提供目录的自定义视图。 Microsoft Teams信息[屏障策略来支持](/microsoft-365/compliance/information-barriers)这些自定义视图。 启用策略后，将搜索其他用户返回的结果 (例如，启动聊天或将成员添加到团队) 将按配置的策略进行范围设置。 当范围搜索生效时，用户将无法搜索或发现任何团队，但这些团队中的现有成员可以添加用户，如活动信息屏障策略所允许。

> [!NOTE]
> 在Exchange环境中，此功能仅适用于Exchange Online邮箱，而与本地邮箱不同。

另请参阅[Exchange Online 中的通讯簿策略](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies)。

## <a name="when-should-you-use-scoped-directory-searches"></a>何时应该使用范围目录搜索？

受益于范围目录搜索的方案类似于通讯簿策略方案。 例如，你可能想要在下列情况下使用范围目录搜索：

- 贵组织的租户中有多家你要保持独立的公司。 
- 贵学校要限制教职员工与学生之间的聊天。 
 
若要了解如何使用通讯簿策略，请阅读中的信息[屏障Exchange Online。](/microsoft-365/compliance/information-barriers)

> [!IMPORTANT]
> 通讯簿策略仅从目录角度提供用户虚拟隔离。 另请注意，在强制执行新的或更新的通讯簿策略之前，已缓存的任何用户数据都将在最多 30 天内可供用户使用。

## <a name="turn-on-scoped-directory-search"></a>打开范围目录搜索

1. 使用信息屏障策略将组织配置为虚拟子组。 有关详细信息，请参阅 [定义信息屏障策略](/microsoft-365/compliance/information-barriers-policies)。

2. 在Microsoft Teams管理中心，选择 **"组织范围的设置"Teams**  >  **设置"。**

3. 在 **"搜索**"下，在"使用 ABP Teams地址簿策略Exchange范围目录搜索 **("** 下) "打开 **"。**

    ![管理中心中的Microsoft Teams目录搜索](media/teams-scoped-directory-search-image1.png)


> [!IMPORTANT]
> 此更改可能需要几个小时才能复制。
