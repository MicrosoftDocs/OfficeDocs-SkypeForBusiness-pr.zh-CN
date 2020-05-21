---
title: 使用 Microsoft Teams 范围目录搜索
author: LolaJacobsen
ms.author: lolaj
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
description: 了解如何使用 Microsoft 团队范围的目录搜索以提供目录的自定义视图。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: e81e2fb588e718060ffbdf90a51c020ff2d6556c
ms.sourcegitcommit: b381d8f0b9fc45133d52175fa85901b66e744abd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2020
ms.locfileid: "44326589"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a>使用 Microsoft Teams 范围目录搜索

Microsoft 团队范围目录搜索允许组织创建虚拟边界，以控制用户如何与组织中的其他用户进行查找和通信。 

Microsoft 团队允许组织向其用户提供目录的自定义视图。 Microsoft 团队使用[信息障碍策略](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)来支持这些自定义视图。 启用策略后，搜索其他用户（例如启动聊天或向团队添加成员）所返回的结果将按配置的策略确定范围。 当范围搜索生效时，用户将无法搜索或发现团队。 

> [!NOTE]
> 在 Exchange 混合环境中，此功能仅适用于 Exchange Online 邮箱，而不适用于本地邮箱。

## <a name="when-should-you-use-scoped-directory-searches"></a>何时应使用目录搜索范围？

从作用域目录搜索中受益的方案类似于通讯簿策略方案。 例如，你可能希望在以下情况下使用限定的目录搜索：

- 贵组织的租户中有多家你要保持独立的公司。 
- 贵学校要限制教职员工与学生之间的聊天。 
 
若要了解如何使用通讯簿策略，请参阅[Exchange Online 中的信息屏障策略](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)。

> [!IMPORTANT]
> 通讯簿策略仅提供用户从目录角度进行虚拟分离。 通过提供完整的电子邮件地址，用户仍然可以发起与其他人的通信。 另外，请务必注意，在实施新的或更新的通讯簿策略之前，已缓存的任何用户数据在30天内仍可供用户使用。

## <a name="turn-on-scoped-directory-search"></a>打开范围的目录搜索

1. 使用信息屏障策略将组织配置为虚拟子组。 有关详细信息，请参阅[定义信息屏障策略](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-policies)。

2. 在 "Microsoft 团队管理中心" 中，选择 "**组织范围设置**"  >  **团队设置**。

3. 在 "**搜索**" 下，在**使用 Exchange 通讯簿策略（ABP）的团队中的 "范围目录搜索**" 旁边，打开 "打开 **"。**

    ![Microsoft 团队管理中心中的范围目录搜索](media/teams-scoped-directory-search-image1.png)


> [!IMPORTANT]
> 此更改可能需要几个小时才能进行复制。
