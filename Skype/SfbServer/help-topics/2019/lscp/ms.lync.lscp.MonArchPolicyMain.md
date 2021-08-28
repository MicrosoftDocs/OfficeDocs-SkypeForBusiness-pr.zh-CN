---
title: 存档策略
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.MonArchPolicyMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: 9b69f1fa-8f3b-450e-aa89-91fd462f198d
ROBOTS: NOINDEX, NOFOLLOW
description: 使用存档策略启用和禁用位于存档Skype for Business Server。 在每个存档策略中，您可以对以下任一项或者两项启用或禁用存档：
ms.openlocfilehash: dca1ec888a63297f89da062d22983d3d05182127
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58610059"
---
# <a name="archiving-policy"></a>存档策略
 
使用存档策略启用和禁用位于存档Skype for Business Server。 在每个存档策略中，您可以对以下任一项或者两项启用或禁用存档：
  
- 内部通信
    
- 外部通信（在内部网络之外至少包含一位用户的通信）
    
存档策略包括全局策略以及可选的一个或多个站点和用户存档策略：
  
- **全局策略** 默认情况下，全局策略在所有部署中创建。 您可以编辑全局策略，但无法删除此策略。 如果您尝试将其删除，则所有选项将重置为默认值。
    
- **站点策略 (可选)** 可以指定一个或多个站点存档策略，您可将每个存档策略分别配置为启用和禁用对单个站点的内部或外部通信的存档。 站点策略会覆盖全局策略，但仅限于在存档站点策略中指定的站点。 可以编辑或删除站点策略。
    
- **用户策略 (可选)** 可以指定一个或多个用户存档策略，您可将每个存档策略分别配置为启用和禁用对特定用户或用户组的内部或外部通信的存档。 用户策略会覆盖全局策略和站点策略，但仅限于分配了用户级别存档策略的用户和用户组。 可以编辑或删除用户策略。
    
> [!NOTE]
> 存档策略仅适用于位于存档Skype for Business Server。 如果使用集成Exchange Microsoft Exchange 中存储存档数据，Exchange策略将控制用户Exchange。 若要为这些用户启用存档，必须将用户的邮箱置于In-Place保留状态。 
  
“存档策略”页将列出为部署配置的每个存档策略。该页还将显示策略名称、范围（全局、站点或用户）以及为每个存档策略启用的存档选项。在“存档策略”页上，您有以下选项：
- **新建** 可以添加以下一个或多个可选的存档策略：
    
  - 站点策略
    
  - 用户策略
    
- **编辑** 您可以更改该页上列出的任何存档策略的选项。 使用此选项，可以执行以下操作：
    
  - **显示详细信息** 此选项可打开一个对话框，您可在其中更改存档策略的存档选项。
    
  - **全选** 此选项可选择列表中的所有存档策略。
    
  - **删除** 此选项可删除所有选定的存档策略。
    
- **操作** 可以使用此选项快速启用或禁用页面列出的任何策略中的内部或外部通信存档，而不是编辑策略。 "操作" **下可用的** 选项取决于当前在存档策略中指定的选项。 所有选项都可用，但当前对存档策略有效的选项除外。 选项包括：
    
  - **启用内部通信的存档**
    
  - **禁用内部通信的存档**
    
  - **启用外部通信的存档**
    
  - **禁用外部通信的存档**
    
- **刷新** 可以刷新" **存档策略"** 页以验证所有存档策略的选项状态。
    
有关存档特性和功能（包括 Exchange 集成）的详细信息，请参阅在[Skype for Business Server](../../../plan-your-deployment/archiving/archiving.md)中规划存档、[为](../../../deploy/deploy-archiving/deploy-archiving.md)Skype for Business Server 部署存档和在 Skype for Business Server 中管理[存档](../../../manage/archiving/archiving.md)。

