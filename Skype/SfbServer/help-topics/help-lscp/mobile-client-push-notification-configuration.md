---
title: 移动客户端推送通知配置
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientPushNotificationCfgMain
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: b7a85d75-9d36-4980-b669-2a009799d905
description: 若要配置“Microsoft 推送通知”和“Apple 推送通知”，您必须创建一个定义所需推送通知类型的策略。
ms.openlocfilehash: 22b1174eee06fd46bd69d1d9b6c1c4f3f12ac01f
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60841524"
---
# <a name="mobile-client-push-notification-configuration"></a>移动客户端：推送通知配置
 
若要配置“Microsoft 推送通知”和“Apple 推送通知”，您必须创建一个定义所需推送通知类型的策略。
  
在主配置屏幕上，单击“刷新”可刷新并重新填充策略列表。利用搜索框可缩小所显示策略的列表。当您键入要搜索的名称时，策略列表会自动缩小。
  
> [!IMPORTANT]
> 在一个策略级别应用的策略设置可覆盖在其他策略级别应用的设置。 策略优先级为：用户策略 (站点策略) ，站点策略覆盖全局策略， (影响最小) 。 这意味着，策略设置越接近策略影响的对象，它对对象的影响就越大。 
  
有两个选项可用于策略创建和编辑：
  
1. **新建**：单击可创建一个新策略。必须为要应用的策略提供一个站点。然后配置推送通知的设置。对于 **推送通知配置**，您只能为已创建的站点创建策略。
    
2. **编辑**：选择一个策略并单击“编辑”可从下拉框中选择一个操作。您只能编辑已创建的站点或编辑全局策略：
    
   - **显示详细信息…**：显示有关当前所选策略的信息。您可以对现有策略进行更改。
    
   - **全选**：如果您有多个策略且需要选择所有策略，则单击“全选”
    
   - **删除**：可删除所选策略。使用“全选”和“删除”可删除全部策略
    
     > [!NOTE]
     > 您无法删除默认“全局”策略。如果试图删除全局策略，则系统会通知您全局策略已返回到默认值（即所有设置被清除），但无法删除该策略。
  
创建新策略或编辑现有策略与下列两种操作相关：
  
- **提交** 提交操作创建或更新策略并保存更改
    
- **取消** 取消操作将放弃自上次提交操作以来进行的任何更改。 如果取消，所做的更改将丢失。
    
两种设置可用于 **推送通知配置**。设置与 Microsoft 和 Apple 的推送通知服务相关联。通过选中服务名称旁边的复选框可为任意一种服务启用推送通知。也可以通过选择复选框将其清除来取消选中复选框。进行选择后，您可以提交或取消。单击提交可保存对策略的更改。
  

