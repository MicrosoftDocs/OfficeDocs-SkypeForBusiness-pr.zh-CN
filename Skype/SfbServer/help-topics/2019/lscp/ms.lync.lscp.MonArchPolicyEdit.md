---
title: 存档策略新建或编辑现有
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.MonArchPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a4f948e7-e8f6-449a-8907-f61c5b143c05
ROBOTS: NOINDEX, NOFOLLOW
description: 对于托管在 Skype for business 服务器上的用户, 使用存档策略控制部署内部和外部通信的存档。 存档策略包括全局策略以及可选的一个或多个站点和用户策略：
ms.openlocfilehash: 87dc7764f80f722108189fb99209d8a9388f5d8b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34291969"
---
# <a name="archiving-policy-create-new-or-edit-existing"></a>存档策略：创建新的或编辑现有的
 
对于托管在 Skype for business 服务器上的用户, 使用存档策略控制部署内部和外部通信的存档。 存档策略包括全局策略以及可选的一个或多个站点和用户策略：
  
- **全局策略**默认情况下, 全局策略在所有 Skype for Business 服务器部署中创建。 您可以编辑全局策略，但无法删除此策略。 如果您尝试将其删除，则所有选项将重置为默认值。
    
- **网站策略 (可选)** 你可以指定一个或多个网站存档策略, 每个策略都可以配置为为特定网站启用和禁用内部或外部通信的存档。 站点策略会覆盖全局策略，但仅限于在存档策略中指定的站点。 可以编辑或删除站点策略。
    
- **用户策略 (可选)** 你可以指定一个或多个用户存档策略, 每个策略都可以配置为针对特定用户启用和禁用内部或外部通信的存档。 用户策略会覆盖全局策略和站点策略，但仅限于分配了用户策略的用户。 可以编辑或删除用户策略。
    
> [!NOTE]
> 如果您使用 Exchange 集成将存档数据存储在 Microsoft Exchange 中, 则 Exchange 策略将控制驻留在 Exchange 上的用户的存档。 若要为这些用户启用存档, 用户的邮箱必须放置在原地保留。 
  
若要为新的存档策略或现有的存档策略配置设置，请指定以下选项：
- **名称**每个存档策略都需要一个名称。 该名称由你要添加或编辑的策略类型确定:
    
  - **全局策略**默认名称为全局名称。 可以将该名称更改成一个更具描述性的名称。 例如，Contoso 北美机构。
    
  - **网站策略**此对话框中列出的网站包括部署中的所有可用网站。 单击某个站点即可将其选中。 例如，Redmond 数据中心。
    
  - **用户策略**指定一个合适的名称, 例如特定用户的姓名或组织中的用户组或团队的名称。 例如，法律部门。
    
- **说明**这是可选操作。 使用它提供其他详细信息, 如策略的范围或使用。 例如, 与其他网站的法律部门协调。
    
- **存档内部通信**选中此复选框以启用内部网络上的通信存档。 默认情况下, 不会在任何策略中启用此功能。
    
- **存档外部通信**选中此复选框以启用包括外部用户 (如远程用户) (包括匿名和 PIC 设置用户) 和联盟合作伙伴的通信的存档。 默认情况下, 不会在任何策略中启用此功能。
    
有关存档功能和功能 (包括 Exchange 集成) 的详细信息, 请参阅[在 skype For Business 服务器中规划存档](../../../plan-your-deployment/archiving/archiving.md)、[部署 Skype for business 服务器存档](../../../deploy/deploy-archiving/deploy-archiving.md)和[管理 skype for business 中的存档服务器](../../../manage/archiving/archiving.md)。

