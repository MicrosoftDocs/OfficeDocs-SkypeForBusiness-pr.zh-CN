---
title: 存档策略创建新的或编辑现有的
ms.reviewer: ''
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
description: 您可以使用存档策略来控制用户的企业服务器驻留在 Skype 上部署中的内部和外部通信的存档。 存档策略包括全局策略以及可选的一个或多个站点和用户策略：
ms.openlocfilehash: 76dcc63ed6c08c0a8d11c79547b8a11f6b1e4b39
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30880733"
---
# <a name="archiving-policy-create-new-or-edit-existing"></a>存档策略：创建新的或编辑现有的
 
您可以使用存档策略来控制用户的企业服务器驻留在 Skype 上部署中的内部和外部通信的存档。 存档策略包括全局策略以及可选的一个或多个站点和用户策略：
  
- **全局策略**默认情况下，所有 Skype 业务服务器部署中创建的全局策略。 您可以编辑全局策略，但无法删除此策略。 如果您尝试将其删除，则所有选项将重置为默认值。
    
- **（可选） 的站点策略**您可以指定一个或多个站点存档策略，您可以配置每种启用和禁用为特定站点的内部或外部通信的存档。 站点策略会覆盖全局策略，但仅限于在存档策略中指定的站点。 可以编辑或删除站点策略。
    
- **（可选） 的用户策略**您可以指定一个或多个用户存档策略，您可以配置每种启用或禁用特定用户的内部或外部通信的存档。 用户策略会覆盖全局策略和站点策略，但仅限于分配了用户策略的用户。 可以编辑或删除用户策略。
    
> [!NOTE]
> 如果您使用 Exchange 集成存储存档数据在 Microsoft Exchange、 然后 Exchange 2013 策略控制的用户存档驻留在 Exchange 2013。 要启用存档这些用户，用户邮箱必须置于就地保留上。 
  
若要为新的存档策略或现有的存档策略配置设置，请指定以下选项：
- **名称**每个存档策略需要一个名称。 名称取决于要添加或编辑的策略类型：
    
  - **全局策略**默认名称为 Global。 可以将该名称更改成一个更具描述性的名称。 例如，Contoso 北美机构。
    
  - **站点策略**在此对话框中列出的站点部署中包括所有可用的站点。 单击某个站点即可将其选中。 例如，Redmond 数据中心。
    
  - **用户策略**指定适当的名称，如特定用户的名称或用户组或组织中的工作组的名称。 例如，法律部门。
    
- **说明**这是可选的。 使用它来提供其他详细信息，例如使用策略的范围。 例如，法律部门的其他网站与协调一致。
    
- **存档内部通信**选中此复选框可允许在内部网络通信的存档。 默认情况下，这不是中的任何策略启用。
    
- **外部通信的存档**选中此复选框以启用包括外部用户，例如 （包括匿名用户和 PIC 设置用户），远程用户和联盟伙伴的通信的存档。 默认情况下，这不是中的任何策略启用。
    
有关的存档功能和功能，包括 Exchange 集成的详细信息，请参阅[规划存档中的业务服务器 2015 Skype](../../plan-your-deployment/archiving/archiving.md)、[业务服务器 2015年的 Skype 存档的部署](../../deploy/deploy-archiving/deploy-archiving.md)，和[管理存档中的 Skype业务服务器 2015年](../../manage/archiving/archiving.md)。

