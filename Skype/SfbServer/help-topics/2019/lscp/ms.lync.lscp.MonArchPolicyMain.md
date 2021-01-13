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
localization_priority: Normal
ms.assetid: 9b69f1fa-8f3b-450e-aa89-91fd462f198d
ROBOTS: NOINDEX, NOFOLLOW
description: 使用存档策略为 Skype for Business Server 上用户启用和禁用存档。 在每个存档策略中，您可以对以下任一项或者两项启用或禁用存档：
ms.openlocfilehash: 041fc71da18ff38b14e82ce9d2ab14f366326b29
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833612"
---
# <a name="archiving-policy"></a>存档策略
 
使用存档策略为 Skype for Business Server 上用户启用和禁用存档。 在每个存档策略中，您可以对以下任一项或者两项启用或禁用存档：
  
- 内部通信
    
- 外部通信（在内部网络之外至少包含一位用户的通信）
    
存档策略包括全局策略以及可选的一个或多个站点和用户存档策略：
  
- **全局策略** 默认情况下，在所有部署中创建全局策略。 您可以编辑全局策略，但无法删除此策略。 如果您尝试将其删除，则所有选项将重置为默认值。
    
- **站点策略 (可选)** 可以指定一个或多个站点存档策略，每个存档策略都可以配置为启用和禁用对单个站点的内部或外部通信的存档。 站点策略会覆盖全局策略，但仅限于在存档站点策略中指定的站点。 可以编辑或删除站点策略。
    
- **用户策略 (可选)** 可以指定一个或多个用户存档策略，每个存档策略都可以配置为为特定用户或用户组启用和禁用内部或外部通信的存档。 用户策略会覆盖全局策略和站点策略，但仅限于分配了用户级别存档策略的用户和用户组。 可以编辑或删除用户策略。
    
> [!NOTE]
> 存档策略仅适用于位于 Skype for Business Server 上的用户。 如果使用 Exchange 集成在 Microsoft Exchange 中存储存档数据，则 Exchange 策略将控制 Exchange 上用户存档。 若要为这些用户启用存档，必须将用户的邮箱置于In-Place保留状态。 
  
“存档策略”页将列出为部署配置的每个存档策略。该页还将显示策略名称、范围（全局、站点或用户）以及为每个存档策略启用的存档选项。在“存档策略”页上，您有以下选项：
- **新建** 可以添加以下一个或多个可选的存档策略：
    
  - 站点策略
    
  - 用户策略
    
- **编辑** 您可以更改页面上列出的任何存档策略的选项。 使用此选项，可以执行以下操作：
    
  - **显示详细信息** 此选项可打开一个对话框，您可在其中更改存档策略的存档选项。
    
  - **全选** 此选项可选择列表中的所有存档策略。
    
  - **删除** 此选项可删除所有选定的存档策略。
    
- **操作** 可以使用此选项快速启用或禁用页面上列出的任何策略中的内部或外部通信存档，而不是编辑该策略。 "操作" **下可用的** 选项取决于当前在存档策略中指定的选项。 所有选项都可用，但当前对存档策略有效的选项除外。 选项包括：
    
  - **启用内部通信的存档**
    
  - **禁用内部通信的存档**
    
  - **启用外部通信的存档**
    
  - **禁用外部通信的存档**
    
- **刷新** 可以刷新" **存档策略** "页以验证所有存档策略的选项状态。
    
有关存档特性和功能的详细信息，包括 Exchange 集成，请参阅 Plan [for archiving in Skype for Business Server，](../../../plan-your-deployment/archiving/archiving.md)Deploy archiving for Skype for Business [Server，](../../../deploy/deploy-archiving/deploy-archiving.md)and [Manage archiving in Skype for Business Server.](../../../manage/archiving/archiving.md)

