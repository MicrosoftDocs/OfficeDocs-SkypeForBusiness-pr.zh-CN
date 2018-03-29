---
title: Mobile Client Push Notification Configuration
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientPushNotificationCfgMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b7a85d75-9d36-4980-b669-2a009799d905
description: To configure the Microsoft push notifications and Apple push notifications, you must create a policy to define which types of push notification you require.
ms.openlocfilehash: 946e083ab9f3f4dbc2b59f7f3026ec3a6dd5ed19
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="mobile-client-push-notification-configuration"></a>Mobile Client: Push Notification Configuration
 
To configure the **Microsoft push notifications** and **Apple push notifications**, you must create a policy to define which types of push notification you require.
  
On the main configuration screen, you can click **Refresh** to refresh and re-populate the list of policies. A search box is provided for narrowing the list of displayed policies. As you type the name that you are searching for, the list of policies narrows automatically.
  
> [!IMPORTANT]
> 在一个策略级别应用的策略设置可能会覆盖在另一个策略级别应用的设置。策略优先顺序为：用户策略（影响力最大）覆盖站点策略，站点策略覆盖全局策略（影响力最小）。这意味着，策略设置与策略所影响的对象距离越近，它对该对象的影响力越大。 
  
Two selections are available for policy creation and editing:
  
1. **New**: Click to create a new policy. You must provide a site for the policy to apply to. You then configure the settings for the push notification. For **Push Notification Configuration**, you can only create policies for Sites that you have already created.
    
2. **Edit**: Select a policy and click Edit to select an action from a drop-down. You can only edit sites that you have already created or edit the Global policy:
    
  - **Show details…**: Displays information about the currently selected policy. You will be able to make changes to the existing policy.
    
  - **Select all**: If you have a number of policies and need to select all policies, click Select all
    
  - **Delete**: Will remove the selected policy. Using **Select all** and **Delete** will remove all policies
    
    > [!NOTE]
    > You cannot delete the default **Global** policy. If you attempt to delete it, you will be notified that the Global policy has been returned to the default values (that is, all settings are cleared), but the policy cannot be removed.
  
Creating a new policy or editing an existing policy is associated with two actions:
  
- **Commit** The commit action creates or updates the policy and saves the changes
    
- **Cancel** The cancel action discards any changes that have been made since the last commit action. If you cancel, any changes made will be lost.
    
Two settings are possible for **Push Notification Configuration**. The settings are associated with the push notification services for Microsoft and for Apple. You enable push notification for either service by selecting the check box next to the name of the service. You can clear the check box by selecting it to clear it. Once you have made your selections, you either commit or cancel. Clicking commit will save the changes to the policy.
  

