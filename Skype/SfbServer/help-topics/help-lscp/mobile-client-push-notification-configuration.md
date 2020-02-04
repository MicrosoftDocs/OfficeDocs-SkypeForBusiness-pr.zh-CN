---
title: 移动客户端推送通知配置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.ClientPushNotificationCfgMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b7a85d75-9d36-4980-b669-2a009799d905
description: 若要配置 Microsoft 推送通知和 Apple 推送通知，必须创建一个策略来定义所需的推送通知类型。
ms.openlocfilehash: 36cf19d42a2378e024f90d3dbe60123b3d5473fa
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41700027"
---
# <a name="mobile-client-push-notification-configuration"></a><span data-ttu-id="f8520-103">移动客户端：推送通知配置</span><span class="sxs-lookup"><span data-stu-id="f8520-103">Mobile Client: Push Notification Configuration</span></span>
 
<span data-ttu-id="f8520-104">若要配置**Microsoft 推送通知**和**Apple 推送通知**，必须创建一个策略来定义所需的推送通知类型。</span><span class="sxs-lookup"><span data-stu-id="f8520-104">To configure the **Microsoft push notifications** and **Apple push notifications**, you must create a policy to define which types of push notification you require.</span></span>
  
<span data-ttu-id="f8520-105">在 "主配置" 屏幕上，您可以单击 "**刷新**" 以刷新并重新填充策略列表。</span><span class="sxs-lookup"><span data-stu-id="f8520-105">On the main configuration screen, you can click **Refresh** to refresh and re-populate the list of policies.</span></span> <span data-ttu-id="f8520-106">提供了一个搜索框，用于缩小显示的策略列表。</span><span class="sxs-lookup"><span data-stu-id="f8520-106">A search box is provided for narrowing the list of displayed policies.</span></span> <span data-ttu-id="f8520-107">键入要搜索的名称时，策略列表会自动缩小。</span><span class="sxs-lookup"><span data-stu-id="f8520-107">As you type the name that you are searching for, the list of policies narrows automatically.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="f8520-p102">在一个策略级别应用的策略设置可能会覆盖在另一个策略级别应用的设置。策略优先顺序为：用户策略（影响力最大）覆盖站点策略，站点策略覆盖全局策略（影响力最小）。这意味着，策略设置与策略所影响的对象距离越近，它对该对象的影响力越大。</span><span class="sxs-lookup"><span data-stu-id="f8520-p102">Policy settings that are applied at one policy level can override settings that are applied at another policy level. Policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence). This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> 
  
<span data-ttu-id="f8520-111">有两个选项可用于创建和编辑策略：</span><span class="sxs-lookup"><span data-stu-id="f8520-111">Two selections are available for policy creation and editing:</span></span>
  
1. <span data-ttu-id="f8520-112">**新增**：单击以创建新策略。</span><span class="sxs-lookup"><span data-stu-id="f8520-112">**New**: Click to create a new policy.</span></span> <span data-ttu-id="f8520-113">你必须提供要应用到的策略的网站。</span><span class="sxs-lookup"><span data-stu-id="f8520-113">You must provide a site for the policy to apply to.</span></span> <span data-ttu-id="f8520-114">然后，配置推送通知的设置。</span><span class="sxs-lookup"><span data-stu-id="f8520-114">You then configure the settings for the push notification.</span></span> <span data-ttu-id="f8520-115">对于**推送通知配置**，只能为已创建的网站创建策略。</span><span class="sxs-lookup"><span data-stu-id="f8520-115">For **Push Notification Configuration**, you can only create policies for Sites that you have already created.</span></span>
    
2. <span data-ttu-id="f8520-116">**编辑**：选择策略，然后单击 "编辑" 从下拉列表中选择一个操作。</span><span class="sxs-lookup"><span data-stu-id="f8520-116">**Edit**: Select a policy and click Edit to select an action from a drop-down.</span></span> <span data-ttu-id="f8520-117">只能编辑已创建的网站或编辑全局策略：</span><span class="sxs-lookup"><span data-stu-id="f8520-117">You can only edit sites that you have already created or edit the Global policy:</span></span>
    
   - <span data-ttu-id="f8520-118">**显示详细信息 ...**：显示有关当前所选策略的信息。</span><span class="sxs-lookup"><span data-stu-id="f8520-118">**Show details…**: Displays information about the currently selected policy.</span></span> <span data-ttu-id="f8520-119">你将能够对现有策略进行更改。</span><span class="sxs-lookup"><span data-stu-id="f8520-119">You will be able to make changes to the existing policy.</span></span>
    
   - <span data-ttu-id="f8520-120">**选择 "全部**"：如果你有多个策略，并且需要选择所有策略，请单击 "全选"</span><span class="sxs-lookup"><span data-stu-id="f8520-120">**Select all**: If you have a number of policies and need to select all policies, click Select all</span></span>
    
   - <span data-ttu-id="f8520-121">**删除**：将删除所选策略。</span><span class="sxs-lookup"><span data-stu-id="f8520-121">**Delete**: Will remove the selected policy.</span></span> <span data-ttu-id="f8520-122">使用 "**全选**" 和 "**删除**" 将删除所有策略</span><span class="sxs-lookup"><span data-stu-id="f8520-122">Using **Select all** and **Delete** will remove all policies</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="f8520-123">您不能删除默认**全局**策略。</span><span class="sxs-lookup"><span data-stu-id="f8520-123">You cannot delete the default **Global** policy.</span></span> <span data-ttu-id="f8520-124">如果你尝试删除它，系统将通知你全局策略已返回默认值（即，所有设置均已清除），但无法删除该策略。</span><span class="sxs-lookup"><span data-stu-id="f8520-124">If you attempt to delete it, you will be notified that the Global policy has been returned to the default values (that is, all settings are cleared), but the policy cannot be removed.</span></span>
  
<span data-ttu-id="f8520-125">创建新策略或编辑现有策略与两个操作相关联：</span><span class="sxs-lookup"><span data-stu-id="f8520-125">Creating a new policy or editing an existing policy is associated with two actions:</span></span>
  
- <span data-ttu-id="f8520-126">**提交**提交操作创建或更新策略并保存更改</span><span class="sxs-lookup"><span data-stu-id="f8520-126">**Commit** The commit action creates or updates the policy and saves the changes</span></span>
    
- <span data-ttu-id="f8520-127">**取消**取消操作会放弃自上次提交操作后所做的任何更改。</span><span class="sxs-lookup"><span data-stu-id="f8520-127">**Cancel** The cancel action discards any changes that have been made since the last commit action.</span></span> <span data-ttu-id="f8520-128">如果取消，所做的任何更改都将丢失。</span><span class="sxs-lookup"><span data-stu-id="f8520-128">If you cancel, any changes made will be lost.</span></span>
    
<span data-ttu-id="f8520-129">**推送通知配置**可能有两个设置。</span><span class="sxs-lookup"><span data-stu-id="f8520-129">Two settings are possible for **Push Notification Configuration**.</span></span> <span data-ttu-id="f8520-130">这些设置与适用于 Microsoft 和 Apple 的推送通知服务相关联。</span><span class="sxs-lookup"><span data-stu-id="f8520-130">The settings are associated with the push notification services for Microsoft and for Apple.</span></span> <span data-ttu-id="f8520-131">通过选择服务名称旁边的复选框来启用任一服务的推送通知。</span><span class="sxs-lookup"><span data-stu-id="f8520-131">You enable push notification for either service by selecting the check box next to the name of the service.</span></span> <span data-ttu-id="f8520-132">您可以通过选择清除复选框来清除它。</span><span class="sxs-lookup"><span data-stu-id="f8520-132">You can clear the check box by selecting it to clear it.</span></span> <span data-ttu-id="f8520-133">做出选择后，您可以提交或取消。</span><span class="sxs-lookup"><span data-stu-id="f8520-133">Once you have made your selections, you either commit or cancel.</span></span> <span data-ttu-id="f8520-134">单击 "提交" 将保存对策略所做的更改。</span><span class="sxs-lookup"><span data-stu-id="f8520-134">Clicking commit will save the changes to the policy.</span></span>
  

