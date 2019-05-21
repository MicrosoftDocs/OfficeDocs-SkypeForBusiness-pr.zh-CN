---
title: 存档策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.MonArchPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9b69f1fa-8f3b-450e-aa89-91fd462f198d
ROBOTS: NOINDEX, NOFOLLOW
description: 使用存档策略为驻留在 Skype for business 服务器上的用户启用和禁用存档。 在每个存档策略中，您可以对以下任一项或者两项启用或禁用存档：
ms.openlocfilehash: bdeb7925256e47ac61d0210e1be36e28dbdfc0d1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34291941"
---
# <a name="archiving-policy"></a>存档策略
 
使用存档策略为驻留在 Skype for business 服务器上的用户启用和禁用存档。 在每个存档策略中，您可以对以下任一项或者两项启用或禁用存档：
  
- 内部通信
    
- 外部通信（在内部网络之外至少包含一位用户的通信）
    
存档策略包括全局策略以及可选的一个或多个站点和用户存档策略：
  
- **全局策略**默认情况下, 全局策略在所有部署中创建。 您可以编辑全局策略，但无法删除此策略。 如果您尝试将其删除，则所有选项将重置为默认值。
    
- **网站策略 (可选)** 你可以指定一个或多个网站存档策略, 每个策略都可以配置为对单个网站启用和禁用内部或外部通信的存档。 站点策略会覆盖全局策略，但仅限于在存档站点策略中指定的站点。 可以编辑或删除站点策略。
    
- **用户策略 (可选)** 你可以指定一个或多个用户存档策略, 每个策略都可以配置为特定用户或用户组启用和禁用内部或外部通信的存档。 用户策略会覆盖全局策略和站点策略，但仅限于分配了用户级别存档策略的用户和用户组。 可以编辑或删除用户策略。
    
> [!NOTE]
> 存档策略仅适用于驻留在 Skype for Business 服务器上的用户。 如果您使用 Exchange 集成将存档数据存储在 Microsoft Exchange 中, 则 Exchange 策略将控制驻留在 Exchange 上的用户的存档。 若要为这些用户启用存档, 用户的邮箱必须放置在原地保留。 
  
“**存档策略**”页将列出为部署配置的每个存档策略。该页还将显示策略名称、范围（全局、站点或用户）以及为每个存档策略启用的存档选项。在“**存档策略**”页上，您有以下选项：
- **新**你可以添加以下每个可选存档策略中的一个或多个:
    
  - 站点策略
    
  - 用户策略
    
- **编辑**你可以更改页面上列出的任何存档策略的选项。 使用此选项, 您可以执行以下操作:
    
  - **显示详细信息** 此选项可打开一个对话框，您可在其中更改存档策略的存档选项。
    
  - **全选** 此选项可选择列表中的所有存档策略。
    
  - **删除** 此选项可删除所有选定的存档策略。
    
- **操作**可使用此选项快速启用或禁用对页面上列出的任何策略 (而不是编辑策略) 的内部或外部通信的存档。 "**操作**" 下的可用选项取决于存档策略中当前指定的选项。 除了当前对存档策略有效的选项之外, 所有选项均可用。 选项包括以下内容:
    
  - **启用内部通信的存档**
    
  - **禁用内部通信的存档**
    
  - **启用外部通信的存档**
    
  - **禁用外部通信的存档**
    
- **刷新**你可以刷新 "**存档策略**" 页面以验证所有存档策略的选项的状态。
    
有关存档功能和功能 (包括 Exchange 集成) 的详细信息, 请参阅[在 skype For Business 服务器中规划存档](../../../plan-your-deployment/archiving/archiving.md)、[部署 Skype for business 服务器存档](../../../deploy/deploy-archiving/deploy-archiving.md)和[管理 skype for business 中的存档服务器](../../../manage/archiving/archiving.md)。

