---
title: 移动客户端推送通知配置
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 若要配置“Microsoft 推送通知”和“Apple 推送通知”，您必须创建一个定义所需推送通知类型的策略。
ms.openlocfilehash: 693b954fffbbce56a2d95ce29128482937b6fa05
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49836672"
---
# <a name="mobile-client-push-notification-configuration"></a><span data-ttu-id="cb186-103">移动客户端：推送通知配置</span><span class="sxs-lookup"><span data-stu-id="cb186-103">Mobile Client: Push Notification Configuration</span></span>
 
<span data-ttu-id="cb186-104">若要配置“Microsoft 推送通知”和“Apple 推送通知”，您必须创建一个定义所需推送通知类型的策略。</span><span class="sxs-lookup"><span data-stu-id="cb186-104">To configure the **Microsoft push notifications** and **Apple push notifications**, you must create a policy to define which types of push notification you require.</span></span>
  
<span data-ttu-id="cb186-p101">在主配置屏幕上，单击“刷新”可刷新并重新填充策略列表。利用搜索框可缩小所显示策略的列表。当您键入要搜索的名称时，策略列表会自动缩小。</span><span class="sxs-lookup"><span data-stu-id="cb186-p101">On the main configuration screen, you can click **Refresh** to refresh and re-populate the list of policies. A search box is provided for narrowing the list of displayed policies. As you type the name that you are searching for, the list of policies narrows automatically.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="cb186-108">在一个策略级别应用的策略设置可覆盖在其他策略级别应用的设置。</span><span class="sxs-lookup"><span data-stu-id="cb186-108">Policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="cb186-109">策略优先级为：用户策略 (站点) 覆盖站点策略，然后站点策略覆盖全局策略 (影响最小) 。</span><span class="sxs-lookup"><span data-stu-id="cb186-109">Policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="cb186-110">这意味着，策略设置越接近策略影响的对象，它对对象的影响就越大。</span><span class="sxs-lookup"><span data-stu-id="cb186-110">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> 
  
<span data-ttu-id="cb186-111">有两个选项可用于策略创建和编辑：</span><span class="sxs-lookup"><span data-stu-id="cb186-111">Two selections are available for policy creation and editing:</span></span>
  
1. <span data-ttu-id="cb186-p103">**新建**：单击可创建一个新策略。必须为要应用的策略提供一个站点。然后配置推送通知的设置。对于 **推送通知配置**，您只能为已创建的站点创建策略。</span><span class="sxs-lookup"><span data-stu-id="cb186-p103">**New**: Click to create a new policy. You must provide a site for the policy to apply to. You then configure the settings for the push notification. For **Push Notification Configuration**, you can only create policies for Sites that you have already created.</span></span>
    
2. <span data-ttu-id="cb186-p104">**编辑**：选择一个策略并单击“编辑”可从下拉框中选择一个操作。您只能编辑已创建的站点或编辑全局策略：</span><span class="sxs-lookup"><span data-stu-id="cb186-p104">**Edit**: Select a policy and click Edit to select an action from a drop-down. You can only edit sites that you have already created or edit the Global policy:</span></span>
    
   - <span data-ttu-id="cb186-p105">**显示详细信息…**：显示有关当前所选策略的信息。您可以对现有策略进行更改。</span><span class="sxs-lookup"><span data-stu-id="cb186-p105">**Show details…**: Displays information about the currently selected policy. You will be able to make changes to the existing policy.</span></span>
    
   - <span data-ttu-id="cb186-120">**全选**：如果您有多个策略且需要选择所有策略，则单击“全选”</span><span class="sxs-lookup"><span data-stu-id="cb186-120">**Select all**: If you have a number of policies and need to select all policies, click Select all</span></span>
    
   - <span data-ttu-id="cb186-p106">**删除**：可删除所选策略。使用“全选”和“删除”可删除全部策略</span><span class="sxs-lookup"><span data-stu-id="cb186-p106">**Delete**: Will remove the selected policy. Using **Select all** and **Delete** will remove all policies</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="cb186-p107">您无法删除默认“全局”策略。如果试图删除全局策略，则系统会通知您全局策略已返回到默认值（即所有设置被清除），但无法删除该策略。</span><span class="sxs-lookup"><span data-stu-id="cb186-p107">You cannot delete the default **Global** policy. If you attempt to delete it, you will be notified that the Global policy has been returned to the default values (that is, all settings are cleared), but the policy cannot be removed.</span></span>
  
<span data-ttu-id="cb186-125">创建新策略或编辑现有策略与下列两种操作相关：</span><span class="sxs-lookup"><span data-stu-id="cb186-125">Creating a new policy or editing an existing policy is associated with two actions:</span></span>
  
- <span data-ttu-id="cb186-126">**提交** 提交操作创建或更新策略并保存更改</span><span class="sxs-lookup"><span data-stu-id="cb186-126">**Commit** The commit action creates or updates the policy and saves the changes</span></span>
    
- <span data-ttu-id="cb186-127">**取消** 取消操作将放弃自上次提交操作以来进行的任何更改。</span><span class="sxs-lookup"><span data-stu-id="cb186-127">**Cancel** The cancel action discards any changes that have been made since the last commit action.</span></span> <span data-ttu-id="cb186-128">如果取消，所做的更改将丢失。</span><span class="sxs-lookup"><span data-stu-id="cb186-128">If you cancel, any changes made will be lost.</span></span>
    
<span data-ttu-id="cb186-p109">两种设置可用于 **推送通知配置**。设置与 Microsoft 和 Apple 的推送通知服务相关联。通过选中服务名称旁边的复选框可为任意一种服务启用推送通知。也可以通过选择复选框将其清除来取消选中复选框。进行选择后，您可以提交或取消。单击提交可保存对策略的更改。</span><span class="sxs-lookup"><span data-stu-id="cb186-p109">Two settings are possible for **Push Notification Configuration**. The settings are associated with the push notification services for Microsoft and for Apple. You enable push notification for either service by selecting the check box next to the name of the service. You can clear the check box by selecting it to clear it. Once you have made your selections, you either commit or cancel. Clicking commit will save the changes to the policy.</span></span>
  

