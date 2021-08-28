---
title: 存档策略 创建新的或编辑现有的
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.MonArchPolicyEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: a4f948e7-e8f6-449a-8907-f61c5b143c05
ROBOTS: NOINDEX, NOFOLLOW
description: 使用存档策略可控制在部署中为位于内部部署中的用户的内部和外部通信Skype for Business Server。 存档策略包括全局策略以及可选的一个或多个站点和用户策略：
ms.openlocfilehash: 0bcc34f3e221c2faf0f358e2161885005e786ea5
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58618068"
---
# <a name="archiving-policy-create-new-or-edit-existing"></a>存档策略：创建新的或编辑现有的
 
使用存档策略可控制在部署中为位于内部部署中的用户的内部和外部通信Skype for Business Server。 存档策略包括全局策略以及可选的一个或多个站点和用户策略：
  
- **全局策略** 默认情况下，全局策略在所有部署Skype for Business Server创建。 您可以编辑全局策略，但无法删除此策略。 如果您尝试将其删除，则所有选项将重置为默认值。
    
- **网站策略 (可选)** 可以指定一个或多个站点存档策略，您可将每个存档策略分别配置为启用和禁用对特定站点的内部或外部通信的存档。 站点策略会覆盖全局策略，但仅限于在存档策略中指定的站点。 可以编辑或删除站点策略。
    
- **用户策略 (可选)** 可以指定一个或多个用户存档策略，您可将每个存档策略分别配置为为特定用户的内部或外部通信启用和禁用存档。 用户策略会覆盖全局策略和站点策略，但仅限于分配了用户策略的用户。 可以编辑或删除用户策略。
    
> [!NOTE]
> 如果使用集成Exchange Microsoft Exchange 中存储存档数据，Exchange策略将控制用户Exchange。 若要为这些用户启用存档，必须将用户的邮箱置于In-Place保留状态。 
  
若要为新的存档策略或现有的存档策略配置设置，请指定以下选项：
- **名称** 每个存档策略都需要一个名称。 该名称由要添加或编辑的策略类型决定：
    
  - **全局策略** 默认名称为 Global。 可以将该名称更改成一个更具描述性的名称。 例如，Contoso 北美机构。
    
  - **站点策略** 此对话框中列出的网站包括部署中所有可用的网站。 单击某个站点将其选中。 例如，Redmond 数据中心。
    
  - **用户策略** 指定适当的名称，例如特定用户的名称或组织中用户组或团队的名称。 例如，法律部门。
    
- **说明** 这是可选的。 使用它提供其他详细信息，例如策略的范围或使用。 例如，与其他网站的法律部门协调。
    
- **存档内部通信** 选中此复选框可启用内部网络上通信的存档。 默认情况下，任何策略中都未启用此功能。
    
- **存档外部通信** 选中此复选框可启用包括外部用户（如远程用户、 (匿名用户和 PIC 设置用户以及联盟伙伴) 通信的存档。 默认情况下，任何策略中都未启用此功能。
    
有关存档特性和功能（包括 Exchange 集成）的详细信息，请参阅在[Skype for Business Server](../../../plan-your-deployment/archiving/archiving.md)中规划存档、[为](../../../deploy/deploy-archiving/deploy-archiving.md)Skype for Business Server 部署存档和在 Skype for Business Server 中管理[存档](../../../manage/archiving/archiving.md)。

