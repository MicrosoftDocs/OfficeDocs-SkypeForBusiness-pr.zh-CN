---
title: 使用 Microsoft 团队范围目录搜索
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 10/09/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
localization_priority: Normal
search.appverid: MET150
description: 了解如何使用 Microsoft 团队作用域的目录搜索来提供目录的自定义的视图。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 65952539ceb52ec62f0c6cd2520f8b898a6a89b5
ms.sourcegitcommit: 7d65eafd5b0163ece91deb7801458c7a45fcc4f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2018
ms.locfileid: "25839259"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a>使用 Microsoft 团队范围目录搜索

Microsoft 团队作用域的目录搜索允许组织创建虚拟控制如何查找用户并与其他组织中的用户进行通信的边界。 

Microsoft 团队允许组织为用户提供的目录的自定义视图。 Microsoft 团队使用[Exchange 通讯簿策略](https://docs.microsoft.com/Exchange/email-addresses-and-address-books/address-book-policies/address-book-policies?view=exchserver-2019)以支持这些自定义视图。 一旦启用了策略，将根据配置的策略作用域 （例如，若要启动聊天，或添加到团队的成员） 的其他用户搜索返回的结果。 用户不能进行搜索或发现并加入新团队之外这些策略。 

## <a name="when-should-you-use-scoped-directory-searches"></a>您应该何时使用作用域的目录搜索？

受益于作用域的目录搜索的方案在类似于通讯簿策略方案。 例如，您可能想要在下列情况下使用作用域的目录搜索：

- 您的组织具有多个公司内您希望用于保存单独其租户。 
- 您的学校希望限制教职员工学生之间的聊天。 
 
您可以了解有关如何使用通讯簿策略的详细信息[此处](https://docs.microsoft.com/Exchange/email-addresses-and-address-books/address-book-policies/abp-scenarios?view=exchserver-2019)。

> [!IMPORTANT]
> 通讯簿策略提供分隔的用户从目录角度仅虚拟。 通过提供完整的电子邮件地址，用户仍然可以发起与其他人进行通信。 

## <a name="enable-scoped-directory-search"></a>启用作用域的目录搜索

1.  使用通讯簿策略来配置您的组织到虚拟组子组。 有关详细信息，请参阅[通讯簿策略的过程](https://docs.microsoft.com/Exchange/email-addresses-and-address-books/address-book-policies/abp-procedures?view=exchserver-2019)。

2.  登录到 Microsoft 365 管理中心，选择**管理中心**、，然后选择**工作组和 Skype**。
 
3.  选择**组织范围设置**中的 Microsoft 团队业务管理中心的 Skype， > **团队设置**。

4.  在**搜索****作用域目录搜索团队使用 Exchange 通讯簿策略 (APB) 中的**，旁边的下启用**上**的切换。 

    ![范围内的目录搜索团队和 Skype 业务管理中心](media/teams-scoped-directory-search-image1.png)

> [!NOTE]
> 混合配置 （与 Exchange 内部部署团队） 不支持限定的搜索模式。 

