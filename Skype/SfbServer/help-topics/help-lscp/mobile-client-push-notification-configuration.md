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
# <a name="mobile-client-push-notification-configuration"></a><span data-ttu-id="72502-103">Mobile Client: Push Notification Configuration</span><span class="sxs-lookup"><span data-stu-id="72502-103">Mobile Client: Push Notification Configuration</span></span>
 
<span data-ttu-id="72502-104">To configure the **Microsoft push notifications** and **Apple push notifications**, you must create a policy to define which types of push notification you require.</span><span class="sxs-lookup"><span data-stu-id="72502-104">To configure the **Microsoft push notifications** and **Apple push notifications**, you must create a policy to define which types of push notification you require.</span></span>
  
<span data-ttu-id="72502-105">On the main configuration screen, you can click **Refresh** to refresh and re-populate the list of policies.</span><span class="sxs-lookup"><span data-stu-id="72502-105">On the main configuration screen, you can click **Refresh** to refresh and re-populate the list of policies.</span></span> <span data-ttu-id="72502-106">A search box is provided for narrowing the list of displayed policies.</span><span class="sxs-lookup"><span data-stu-id="72502-106">A search box is provided for narrowing the list of displayed policies.</span></span> <span data-ttu-id="72502-107">As you type the name that you are searching for, the list of policies narrows automatically.</span><span class="sxs-lookup"><span data-stu-id="72502-107">As you type the name that you are searching for, the list of policies narrows automatically.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="72502-p102">在一个策略级别应用的策略设置可能会覆盖在另一个策略级别应用的设置。策略优先顺序为：用户策略（影响力最大）覆盖站点策略，站点策略覆盖全局策略（影响力最小）。这意味着，策略设置与策略所影响的对象距离越近，它对该对象的影响力越大。</span><span class="sxs-lookup"><span data-stu-id="72502-p102">Policy settings that are applied at one policy level can override settings that are applied at another policy level. Policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence). This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> 
  
<span data-ttu-id="72502-111">Two selections are available for policy creation and editing:</span><span class="sxs-lookup"><span data-stu-id="72502-111">Two selections are available for policy creation and editing:</span></span>
  
1. <span data-ttu-id="72502-112">**New**: Click to create a new policy.</span><span class="sxs-lookup"><span data-stu-id="72502-112">**New**: Click to create a new policy.</span></span> <span data-ttu-id="72502-113">You must provide a site for the policy to apply to.</span><span class="sxs-lookup"><span data-stu-id="72502-113">You must provide a site for the policy to apply to.</span></span> <span data-ttu-id="72502-114">You then configure the settings for the push notification.</span><span class="sxs-lookup"><span data-stu-id="72502-114">You then configure the settings for the push notification.</span></span> <span data-ttu-id="72502-115">For **Push Notification Configuration**, you can only create policies for Sites that you have already created.</span><span class="sxs-lookup"><span data-stu-id="72502-115">For **Push Notification Configuration**, you can only create policies for Sites that you have already created.</span></span>
    
2. <span data-ttu-id="72502-116">**Edit**: Select a policy and click Edit to select an action from a drop-down.</span><span class="sxs-lookup"><span data-stu-id="72502-116">**Edit**: Select a policy and click Edit to select an action from a drop-down.</span></span> <span data-ttu-id="72502-117">You can only edit sites that you have already created or edit the Global policy:</span><span class="sxs-lookup"><span data-stu-id="72502-117">You can only edit sites that you have already created or edit the Global policy:</span></span>
    
  - <span data-ttu-id="72502-118">**Show details…**: Displays information about the currently selected policy.</span><span class="sxs-lookup"><span data-stu-id="72502-118">**Show details…**: Displays information about the currently selected policy.</span></span> <span data-ttu-id="72502-119">You will be able to make changes to the existing policy.</span><span class="sxs-lookup"><span data-stu-id="72502-119">You will be able to make changes to the existing policy.</span></span>
    
  - <span data-ttu-id="72502-120">**Select all**: If you have a number of policies and need to select all policies, click Select all</span><span class="sxs-lookup"><span data-stu-id="72502-120">**Select all**: If you have a number of policies and need to select all policies, click Select all</span></span>
    
  - <span data-ttu-id="72502-121">**Delete**: Will remove the selected policy.</span><span class="sxs-lookup"><span data-stu-id="72502-121">**Delete**: Will remove the selected policy.</span></span> <span data-ttu-id="72502-122">Using **Select all** and **Delete** will remove all policies</span><span class="sxs-lookup"><span data-stu-id="72502-122">Using **Select all** and **Delete** will remove all policies</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="72502-123">You cannot delete the default **Global** policy.</span><span class="sxs-lookup"><span data-stu-id="72502-123">You cannot delete the default **Global** policy.</span></span> <span data-ttu-id="72502-124">If you attempt to delete it, you will be notified that the Global policy has been returned to the default values (that is, all settings are cleared), but the policy cannot be removed.</span><span class="sxs-lookup"><span data-stu-id="72502-124">If you attempt to delete it, you will be notified that the Global policy has been returned to the default values (that is, all settings are cleared), but the policy cannot be removed.</span></span>
  
<span data-ttu-id="72502-125">Creating a new policy or editing an existing policy is associated with two actions:</span><span class="sxs-lookup"><span data-stu-id="72502-125">Creating a new policy or editing an existing policy is associated with two actions:</span></span>
  
- <span data-ttu-id="72502-126">**Commit** The commit action creates or updates the policy and saves the changes</span><span class="sxs-lookup"><span data-stu-id="72502-126">**Commit** The commit action creates or updates the policy and saves the changes</span></span>
    
- <span data-ttu-id="72502-127">**Cancel** The cancel action discards any changes that have been made since the last commit action.</span><span class="sxs-lookup"><span data-stu-id="72502-127">**Cancel** The cancel action discards any changes that have been made since the last commit action.</span></span> <span data-ttu-id="72502-128">If you cancel, any changes made will be lost.</span><span class="sxs-lookup"><span data-stu-id="72502-128">If you cancel, any changes made will be lost.</span></span>
    
<span data-ttu-id="72502-129">Two settings are possible for **Push Notification Configuration**.</span><span class="sxs-lookup"><span data-stu-id="72502-129">Two settings are possible for **Push Notification Configuration**.</span></span> <span data-ttu-id="72502-130">The settings are associated with the push notification services for Microsoft and for Apple.</span><span class="sxs-lookup"><span data-stu-id="72502-130">The settings are associated with the push notification services for Microsoft and for Apple.</span></span> <span data-ttu-id="72502-131">You enable push notification for either service by selecting the check box next to the name of the service.</span><span class="sxs-lookup"><span data-stu-id="72502-131">You enable push notification for either service by selecting the check box next to the name of the service.</span></span> <span data-ttu-id="72502-132">You can clear the check box by selecting it to clear it.</span><span class="sxs-lookup"><span data-stu-id="72502-132">You can clear the check box by selecting it to clear it.</span></span> <span data-ttu-id="72502-133">Once you have made your selections, you either commit or cancel.</span><span class="sxs-lookup"><span data-stu-id="72502-133">Once you have made your selections, you either commit or cancel.</span></span> <span data-ttu-id="72502-134">Clicking commit will save the changes to the policy.</span><span class="sxs-lookup"><span data-stu-id="72502-134">Clicking commit will save the changes to the policy.</span></span>
  

