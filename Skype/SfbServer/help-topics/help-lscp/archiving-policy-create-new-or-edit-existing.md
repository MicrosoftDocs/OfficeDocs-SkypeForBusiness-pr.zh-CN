---
title: 新建或编辑现有的存档策略
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.MonArchPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a4f948e7-e8f6-449a-8907-f61c5b143c05
description: 存档策略用于控制业务服务器驻留在 Skype 的用户部署中的内部和外部通信存档。 存档策略包括全局策略以及可选的一个或多个站点和用户策略：
ms.openlocfilehash: af8038371cd421b0232ce2df0ba92aa5b079702e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="archiving-policy-create-new-or-edit-existing"></a>存档策略：创建新的或编辑现有的
 
存档策略用于控制业务服务器驻留在 Skype 的用户部署中的内部和外部通信存档。 存档策略包括全局策略以及可选的一个或多个站点和用户策略：
  
- **全球政策**默认情况下，所有 Skype 业务服务器部署中创建全局策略。 您可以编辑全局策略，但无法删除此策略。 如果您尝试将其删除，则所有选项将重置为默认值。
    
- **站点策略 （可选）**您可以指定一个或多个网站存档策略，您可以配置每个启用和禁用特定站点的内部或外部通信存档。 站点策略会覆盖全局策略，但仅限于在存档策略中指定的站点。 可以编辑或删除站点策略。
    
- **用户策略 （可选）**您可以指定一个或多个用户存档策略，您可以配置每个启用和禁用针对特定用户的内部或外部通信存档。 用户策略会覆盖全局策略和站点策略，但仅限于分配了用户策略的用户。 可以编辑或删除用户策略。
    
> [!NOTE]
> 如果使用 Exchange 集成存储归档中 Microsoft Exchange，然后交换 2013年策略数据存档的用户控件驻留于 Exchange 2013 年。 为启用存档的用户，该用户的邮箱必须放在适当地存放。 
  
若要为新的存档策略或现有的存档策略配置设置，请指定以下选项：
- **名称**每个存档策略需要一个名称。 名称取决于您在添加或编辑的策略的类型：
    
  - **全球政策**默认名称是全局。 可以将该名称更改成一个更具描述性的名称。 例如，Contoso 北美机构。
    
  - **站点策略**在此对话框中列出的站点在部署中包括的所有可用站点。 单击某个站点将其选中。 例如，Redmond 数据中心。
    
  - **用户策略**指定适当的名称，例如特定的用户的名称或用户组或您的组织中的团队的名称。 例如，法律部门。
    
- **说明**这是可选的。 使用它来提供更多详细信息，如使用策略的范围。 例如，协调与其他站点的法律部门。
    
- **内部通信存档**选中此复选框可启用在您的内部网络上的通信存档。 默认情况下，这不是在任何策略中启用。
    
- **外部通信存档**选中此复选框可以包括外部用户，如远程用户 （包括匿名用户和 PIC 设置用户），用户和联盟伙伴的通信存档。 默认情况下，这不是在任何策略中启用。
    
有关存档功能和功能，其中包括交换集成详细信息请参阅[存档业务服务器 2015年的 Skype 的规划](../../plan-your-deployment/archiving/archiving.md)、[部署存档业务服务器 2015年的 Skype](../../deploy/deploy-archiving/deploy-archiving.md)，和[管理存档的 Skype 的商业服务器 2015年](../../manage/archiving/archiving.md)。

