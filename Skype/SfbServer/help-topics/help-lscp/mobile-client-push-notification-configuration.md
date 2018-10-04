---
title: 移动客户端推送通知配置
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientPushNotificationCfgMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b7a85d75-9d36-4980-b669-2a009799d905
description: 若要配置的 Microsoft 推送通知和 Apple 推送通知，您必须创建策略，以定义需要哪些类型的推送通知。
ms.openlocfilehash: 4b0da70e5d66f31ed1c912efcdd7a13660c396f7
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25371474"
---
# <a name="mobile-client-push-notification-configuration"></a>移动客户端： 推送通知配置
 
若要配置的**Microsoft 推送通知**和**Apple 推送通知**，您必须创建策略，以定义所需的推送通知的类型。
  
在主配置屏幕上，您可以单击**刷新**以刷新并重新填充策略的列表。 提供一个搜索框是为了收缩显示策略的列表。 键入要搜索的名称时，自动缩小了策略的列表。
  
> [!IMPORTANT]
> 在一个策略级别应用的策略设置可能会覆盖在另一个策略级别应用的设置。策略优先顺序为：用户策略（影响力最大）覆盖站点策略，站点策略覆盖全局策略（影响力最小）。这意味着，策略设置与策略所影响的对象距离越近，它对该对象的影响力越大。 
  
有两个选项可用于策略创建和编辑：
  
1. **新建**： 单击以创建新的策略。 您必须提供用于将策略应用于的网站。 您然后配置推送通知的设置。 为**推送通知配置**，您可以仅创建策略对于您已创建的网站。
    
2. **编辑**： 选择一个用法，单击编辑，从下拉列表中选择的操作。 您只能编辑网站您已创建或编辑全局策略：
    
   - **显示详细信息...**: 显示有关当前所选策略的信息。 您将能够对现有的策略进行更改。
    
   - **全选**： 如果您具有多个策略，并需要选择所有策略，单击都选择所有
    
   - **删除**： 将删除所选的策略。 通过**选择全部**，并**删除**将删除所有策略
    
     > [!NOTE]
     > 无法删除默认的**全局**策略。 如果您尝试将其删除，将通知您已为默认值返回的全局策略 （即，清除所有设置），但不能删除策略。
  
创建新策略或编辑现有策略相关联两个操作：
  
- **提交**提交操作创建或更新策略并保存所做的更改
    
- **取消**取消操作会丢弃的上一提交操作以来已进行任何更改。 如果取消，所做的任何更改将会丢失。
    
两个设置是可能的**推送通知配置**。 设置是与 Microsoft 和 Apple 推送通知服务相关联。 通过选择服务的名称旁边的复选框来启用这两种服务的推送通知。 您可以通过选择它以将其清除清除复选框。 后所做选择，您提交或取消。 单击提交将保存对策略所做的更改。
  

