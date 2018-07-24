---
title: 存档策略
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.MonArchPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9b69f1fa-8f3b-450e-aa89-91fd462f198d
ROBOTS: NOINDEX, NOFOLLOW
description: 使用存档策略以启用和禁用存档的用户的企业服务器驻留在 Skype。 在每个存档策略中，您可以对以下任一项或者两项启用或禁用存档：
ms.openlocfilehash: d673aa5474864d99895efc1e16e1e307f078c72f
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20973819"
---
# <a name="archiving-policy"></a>存档策略
 
使用存档策略以启用和禁用存档的用户的企业服务器驻留在 Skype。 在每个存档策略中，您可以对以下任一项或者两项启用或禁用存档：
  
- 内部通信
    
- 外部通信（在内部网络之外至少包含一位用户的通信）
    
存档策略包括全局策略以及可选的一个或多个站点和用户存档策略：
  
- **全局策略**默认情况下，所有部署中创建的全局策略。 您可以编辑全局策略，但无法删除此策略。 如果您尝试将其删除，则所有选项将重置为默认值。
    
- **（可选） 的站点策略**您可以指定一个或多个站点存档策略，您可以配置每种启用和禁用单个站点的内部或外部通信的存档。 站点策略会覆盖全局策略，但仅限于在存档站点策略中指定的站点。 可以编辑或删除站点策略。
    
- **（可选） 的用户策略**您可以指定一个或多个用户存档策略，您可以配置每种启用和禁用存档的内部或外部通信的特定用户或用户组。 用户策略会覆盖全局策略和站点策略，但仅限于分配了用户级别存档策略的用户和用户组。 可以编辑或删除用户策略。
    
> [!NOTE]
> 存档策略仅适用于用户的企业服务器驻留在 Skype 上。 如果您使用 Exchange 集成在 Microsoft Exchange 中存储存档数据，则 Exchange 策略控制的存档用户驻留在 Exchange 中。 要启用存档这些用户，用户邮箱必须置于就地保留上。 
  
“**存档策略**”页将列出为部署配置的每个存档策略。该页还将显示策略名称、范围（全局、站点或用户）以及为每个存档策略启用的存档选项。在“**存档策略**”页上，您有以下选项：
- **新**您可以添加一个或多个以下可选存档策略：
    
  - 站点策略
    
  - 用户策略
    
- **编辑**您可以更改的任何页面上列出的存档策略的选项。 使用此选项，可以执行以下操作：
    
  - **显示详细信息** 此选项可打开一个对话框，您可在其中更改存档策略的存档选项。
    
  - **全选** 此选项可选择列表中的所有存档策略。
    
  - **删除** 此选项可删除所有选定的存档策略。
    
- **操作**您可以使用此选项可快速启用或禁用而不是编辑策略页上列出的任何策略中的内部或外部通信的存档。 可在**操作**下的选项取决于在存档策略当前指定哪些选项。 所有选项都都可用，除选项当前的存档策略生效。 选项包括：
    
  - **启用内部通信的存档**
    
  - **禁用内部通信的存档**
    
  - **启用外部通信的存档**
    
  - **禁用外部通信的存档**
    
- **刷新**您可以刷新**存档策略**页以验证所有存档策略的选项状态。
    
有关的存档功能和功能，包括 Exchange 集成的详细信息，请参阅[Plan for Business Server 的 Skype 的存档](../../../plan-your-deployment/archiving/archiving.md)、 [Skype 业务服务器存档的部署](../../../deploy/deploy-archiving/deploy-archiving.md)，和[管理存档中 Skype for Business服务器](../../../manage/archiving/archiving.md)。

