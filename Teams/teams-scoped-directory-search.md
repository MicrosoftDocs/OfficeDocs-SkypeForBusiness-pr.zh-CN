---
title: 限制用户在Teams中搜索目录时可以看到的用户
author: MikePlumleyMSFT
ms.author: mikeplum
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 了解如何限制用户在Teams中搜索目录时可以看到的用户。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: c20c5acdafff69e5a43f02093b515b456daa8ff7
ms.sourcegitcommit: 193aec6f3f6b6ac14b07e778b3485eed813f5e99
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/13/2022
ms.locfileid: "66046424"
---
# <a name="limit-who-users-can-see-when-searching-the-directory-in-teams"></a>限制用户在Teams中搜索目录时可以看到的用户

Microsoft Teams允许组织向其用户提供目录的自定义视图。 如果有以下情况，则这些视图可能很有用：

- 贵组织的租户中有多家你要保持独立的公司。
- 业务策略要求防止组织内的某些组相互通信。
- 贵学校要限制教职员工与学生之间的聊天。

有两个选项用于限制用户在Teams中搜索目录时可以看到谁：

- [Microsoft Teams中的信息障碍](/MicrosoftTeams/information-barriers-in-teams)
- [Exchange Online中的通讯簿策略](/exchange/address-books/address-book-policies/address-book-policies)

如果使用任一选项，则必须在Teams管理中心按名称启用搜索。

如果组织满足 [所需的许可证和权限](/microsoft-365/compliance/information-barriers#required-licenses-and-permissions)，建议使用信息屏障。

按名称启用搜索

1. 在Microsoft Teams管理中心，选择 **Teams** >  **Teams设置**。

1. 在 **“按名称搜索**”下，**使用Exchange通讯簿策略在 Scope 目录搜索** 旁边 **打开切换。**

> [!Note]
> 此更改可能需要几个小时才能生效。
> 
> 按名称启用搜索会隐藏“加入”中的 **搜索团队** 框和公共团队列表，或在Teams中 **创建团队**。 它还将通过在Teams顶部的命令框中键`/join`入来禁用加入团队。
