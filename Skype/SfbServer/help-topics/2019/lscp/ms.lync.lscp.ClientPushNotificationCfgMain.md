---
title: 移动客户端推送通知配置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientPushNotificationCfgMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: b7a85d75-9d36-4980-b669-2a009799d905
ROBOTS: NOINDEX, NOFOLLOW
description: 若要配置 Microsoft 推送通知和 Apple 推送通知，必须创建一个策略来定义所需的推送通知类型。
ms.openlocfilehash: 57c86185601616bb691a176e86b3a2696c8c8463
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798019"
---
# <a name="mobile-client-push-notification-configuration"></a>移动客户端：推送通知配置
 
若要配置**Microsoft 推送通知**和**Apple 推送通知**，必须创建一个策略来定义所需的推送通知类型。
  
在 "主配置" 屏幕上，您可以单击 "**刷新**" 以刷新并重新填充策略列表。 提供了一个搜索框，用于缩小显示的策略列表。 键入要搜索的名称时，策略列表会自动缩小。
  
> [!IMPORTANT]
> 在一个策略级别应用的策略设置可能会覆盖在另一个策略级别应用的设置。策略优先顺序为：用户策略（影响力最大）覆盖站点策略，站点策略覆盖全局策略（影响力最小）。这意味着，策略设置与策略所影响的对象距离越近，它对该对象的影响力越大。 
  
有两个选项可用于创建和编辑策略：
  
1. **新增**：单击以创建新策略。 你必须提供要应用到的策略的网站。 然后，配置推送通知的设置。 对于**推送通知配置**，只能为已创建的网站创建策略。
    
2. **编辑**：选择策略，然后单击 "编辑" 从下拉列表中选择一个操作。 只能编辑已创建的网站或编辑全局策略：
    
   - **显示详细信息 ...**：显示有关当前所选策略的信息。 你将能够对现有策略进行更改。
    
   - **选择 "全部**"：如果你有多个策略，并且需要选择所有策略，请单击 "全选"
    
   - **删除**：将删除所选策略。 使用 "**全选**" 和 "**删除**" 将删除所有策略
    
     > [!NOTE]
     > 您不能删除默认**全局**策略。 如果你尝试删除它，系统将通知你全局策略已返回默认值（即，所有设置均已清除），但无法删除该策略。
  
创建新策略或编辑现有策略与两个操作相关联：
  
- **提交**提交操作创建或更新策略并保存更改
    
- **取消**取消操作会放弃自上次提交操作后所做的任何更改。 如果取消，所做的任何更改都将丢失。
    
**推送通知配置**可能有两个设置。 这些设置与适用于 Microsoft 和 Apple 的推送通知服务相关联。 通过选择服务名称旁边的复选框来启用任一服务的推送通知。 您可以通过选择清除复选框来清除它。 做出选择后，您可以提交或取消。 单击 "提交" 将保存对策略所做的更改。
  

