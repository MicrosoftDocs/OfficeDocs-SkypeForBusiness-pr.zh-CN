---
title: 移动客户端推送通知配置
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientPushNotificationCfgMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b7a85d75-9d36-4980-b669-2a009799d905
ROBOTS: NOINDEX, NOFOLLOW
description: 若要配置的 Microsoft 推送通知和 Apple 推送通知，您必须创建策略，以定义需要哪些类型的推送通知。
ms.openlocfilehash: 96f3b65e522df0629a9e3fca6558442bc7de3792
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25374110"
---
# <a name="mobile-client-push-notification-configuration"></a><span data-ttu-id="8ab25-103">移动客户端： 推送通知配置</span><span class="sxs-lookup"><span data-stu-id="8ab25-103">Mobile Client: Push Notification Configuration</span></span>
 
<span data-ttu-id="8ab25-104">若要配置的**Microsoft 推送通知**和**Apple 推送通知**，您必须创建策略，以定义所需的推送通知的类型。</span><span class="sxs-lookup"><span data-stu-id="8ab25-104">To configure the **Microsoft push notifications** and **Apple push notifications**, you must create a policy to define which types of push notification you require.</span></span>
  
<span data-ttu-id="8ab25-105">在主配置屏幕上，您可以单击**刷新**以刷新并重新填充策略的列表。</span><span class="sxs-lookup"><span data-stu-id="8ab25-105">On the main configuration screen, you can click **Refresh** to refresh and re-populate the list of policies.</span></span> <span data-ttu-id="8ab25-106">提供一个搜索框是为了收缩显示策略的列表。</span><span class="sxs-lookup"><span data-stu-id="8ab25-106">A search box is provided for narrowing the list of displayed policies.</span></span> <span data-ttu-id="8ab25-107">键入要搜索的名称时，自动缩小了策略的列表。</span><span class="sxs-lookup"><span data-stu-id="8ab25-107">As you type the name that you are searching for, the list of policies narrows automatically.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="8ab25-p102">在一个策略级别应用的策略设置可能会覆盖在另一个策略级别应用的设置。策略优先顺序为：用户策略（影响力最大）覆盖站点策略，站点策略覆盖全局策略（影响力最小）。这意味着，策略设置与策略所影响的对象距离越近，它对该对象的影响力越大。</span><span class="sxs-lookup"><span data-stu-id="8ab25-p102">Policy settings that are applied at one policy level can override settings that are applied at another policy level. Policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence). This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> 
  
<span data-ttu-id="8ab25-111">有两个选项可用于策略创建和编辑：</span><span class="sxs-lookup"><span data-stu-id="8ab25-111">Two selections are available for policy creation and editing:</span></span>
  
1. <span data-ttu-id="8ab25-112">**新建**： 单击以创建新的策略。</span><span class="sxs-lookup"><span data-stu-id="8ab25-112">**New**: Click to create a new policy.</span></span> <span data-ttu-id="8ab25-113">您必须提供用于将策略应用于的网站。</span><span class="sxs-lookup"><span data-stu-id="8ab25-113">You must provide a site for the policy to apply to.</span></span> <span data-ttu-id="8ab25-114">您然后配置推送通知的设置。</span><span class="sxs-lookup"><span data-stu-id="8ab25-114">You then configure the settings for the push notification.</span></span> <span data-ttu-id="8ab25-115">为**推送通知配置**，您可以仅创建策略对于您已创建的网站。</span><span class="sxs-lookup"><span data-stu-id="8ab25-115">For **Push Notification Configuration**, you can only create policies for Sites that you have already created.</span></span>
    
2. <span data-ttu-id="8ab25-116">**编辑**： 选择一个用法，单击编辑，从下拉列表中选择的操作。</span><span class="sxs-lookup"><span data-stu-id="8ab25-116">**Edit**: Select a policy and click Edit to select an action from a drop-down.</span></span> <span data-ttu-id="8ab25-117">您只能编辑网站您已创建或编辑全局策略：</span><span class="sxs-lookup"><span data-stu-id="8ab25-117">You can only edit sites that you have already created or edit the Global policy:</span></span>
    
   - <span data-ttu-id="8ab25-118">**显示详细信息...**: 显示有关当前所选策略的信息。</span><span class="sxs-lookup"><span data-stu-id="8ab25-118">**Show details…**: Displays information about the currently selected policy.</span></span> <span data-ttu-id="8ab25-119">您将能够对现有的策略进行更改。</span><span class="sxs-lookup"><span data-stu-id="8ab25-119">You will be able to make changes to the existing policy.</span></span>
    
   - <span data-ttu-id="8ab25-120">**全选**： 如果您具有多个策略，并需要选择所有策略，单击都选择所有</span><span class="sxs-lookup"><span data-stu-id="8ab25-120">**Select all**: If you have a number of policies and need to select all policies, click Select all</span></span>
    
   - <span data-ttu-id="8ab25-121">**删除**： 将删除所选的策略。</span><span class="sxs-lookup"><span data-stu-id="8ab25-121">**Delete**: Will remove the selected policy.</span></span> <span data-ttu-id="8ab25-122">通过**选择全部**，并**删除**将删除所有策略</span><span class="sxs-lookup"><span data-stu-id="8ab25-122">Using **Select all** and **Delete** will remove all policies</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="8ab25-123">无法删除默认的**全局**策略。</span><span class="sxs-lookup"><span data-stu-id="8ab25-123">You cannot delete the default **Global** policy.</span></span> <span data-ttu-id="8ab25-124">如果您尝试将其删除，将通知您已为默认值返回的全局策略 （即，清除所有设置），但不能删除策略。</span><span class="sxs-lookup"><span data-stu-id="8ab25-124">If you attempt to delete it, you will be notified that the Global policy has been returned to the default values (that is, all settings are cleared), but the policy cannot be removed.</span></span>
  
<span data-ttu-id="8ab25-125">创建新策略或编辑现有策略相关联两个操作：</span><span class="sxs-lookup"><span data-stu-id="8ab25-125">Creating a new policy or editing an existing policy is associated with two actions:</span></span>
  
- <span data-ttu-id="8ab25-126">**提交**提交操作创建或更新策略并保存所做的更改</span><span class="sxs-lookup"><span data-stu-id="8ab25-126">**Commit** The commit action creates or updates the policy and saves the changes</span></span>
    
- <span data-ttu-id="8ab25-127">**取消**取消操作会丢弃的上一提交操作以来已进行任何更改。</span><span class="sxs-lookup"><span data-stu-id="8ab25-127">**Cancel** The cancel action discards any changes that have been made since the last commit action.</span></span> <span data-ttu-id="8ab25-128">如果取消，所做的任何更改将会丢失。</span><span class="sxs-lookup"><span data-stu-id="8ab25-128">If you cancel, any changes made will be lost.</span></span>
    
<span data-ttu-id="8ab25-129">两个设置是可能的**推送通知配置**。</span><span class="sxs-lookup"><span data-stu-id="8ab25-129">Two settings are possible for **Push Notification Configuration**.</span></span> <span data-ttu-id="8ab25-130">设置是与 Microsoft 和 Apple 推送通知服务相关联。</span><span class="sxs-lookup"><span data-stu-id="8ab25-130">The settings are associated with the push notification services for Microsoft and for Apple.</span></span> <span data-ttu-id="8ab25-131">通过选择服务的名称旁边的复选框来启用这两种服务的推送通知。</span><span class="sxs-lookup"><span data-stu-id="8ab25-131">You enable push notification for either service by selecting the check box next to the name of the service.</span></span> <span data-ttu-id="8ab25-132">您可以通过选择它以将其清除清除复选框。</span><span class="sxs-lookup"><span data-stu-id="8ab25-132">You can clear the check box by selecting it to clear it.</span></span> <span data-ttu-id="8ab25-133">后所做选择，您提交或取消。</span><span class="sxs-lookup"><span data-stu-id="8ab25-133">Once you have made your selections, you either commit or cancel.</span></span> <span data-ttu-id="8ab25-134">单击提交将保存对策略所做的更改。</span><span class="sxs-lookup"><span data-stu-id="8ab25-134">Clicking commit will save the changes to the policy.</span></span>
  

