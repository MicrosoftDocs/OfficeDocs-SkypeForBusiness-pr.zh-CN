---
title: 移动客户端创建或编辑推送通知配置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientPushNotificationCfgEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb39af60-c999-42fb-9538-0bd87098f508
description: 推送通知和推送通知交换所 (PNCH) 是移动功能的主要组成部分。推送通知是将消息发送到 PNCH 的过程。消息将保留在此处，直到它能发往移动客户端或超时段过期为止。
ms.openlocfilehash: ca302e0dbdde2c1628abc6c0257ee807f6f152a8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822665"
---
# <a name="mobile-client-create-or-edit-push-notification-configuration"></a><span data-ttu-id="395ef-105">移动客户端：创建或编辑推送通知配置</span><span class="sxs-lookup"><span data-stu-id="395ef-105">Mobile Client: Create or Edit Push Notification Configuration</span></span>
 
<span data-ttu-id="395ef-p102">推送通知和推送通知交换所 (PNCH) 是移动功能的主要组成部分。推送通知是将消息发送到 PNCH 的过程。消息将保留在此处，直到它能发往移动客户端或超时段过期为止。</span><span class="sxs-lookup"><span data-stu-id="395ef-p102">Push Notification and the Push Notification Clearing House (PNCH) are two key parts of the mobility feature. Push notification is the process where a message is sent to the PNCH. The message is held here until it can be delivered to the mobile client, or the timeout period expires.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="395ef-109">时间段在推送通知交换所设置，不能由部署的用户或管理员进行配置。</span><span class="sxs-lookup"><span data-stu-id="395ef-109">The time period is set at the Push Notification Clearing House and is not configurable by the user or the administrator of your deployment.</span></span> 
  
<span data-ttu-id="395ef-110">若要启用推送通知，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="395ef-110">To enable Push Notification, you do the following:</span></span>
  
1. <span data-ttu-id="395ef-p103">**范围：** 注意此策略的范围。范围可以是“**全局**”，此范围适用于该部署中的所有用户，也可以是“**站点**”，此范围是仅分配给指定站点中主服务器的用户。</span><span class="sxs-lookup"><span data-stu-id="395ef-p103">**Scope:** Note the scope for this policy. It can either be **Global**, which applies to all users in this deployment, or **Site**, which is only users assigned to home servers in the specified site.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="395ef-p104">在一个策略级别应用的策略设置可能会覆盖在另一个策略级别应用的设置。策略优先顺序为：用户策略（影响力最大）覆盖站点策略，站点策略覆盖全局策略（影响力最小）。这意味着，策略设置与策略所影响的对象距离越近，它对该对象的影响力越大。</span><span class="sxs-lookup"><span data-stu-id="395ef-p104">Policy settings that are applied at one policy level can override settings that are applied at another policy level. Policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence). This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> 
  
2. <span data-ttu-id="395ef-116">通过单击以下复选框选择您要启用的推送通知服务：</span><span class="sxs-lookup"><span data-stu-id="395ef-116">Select which push notification services you want to enable by clicking the check box for:</span></span>
    
   - <span data-ttu-id="395ef-117">**启用 Microsoft 推送通知**将针对使用 Skype for business 应用的 Windows Phone 的基于云的 PNCH 启用推送通知</span><span class="sxs-lookup"><span data-stu-id="395ef-117">**Enable Microsoft push notification** will enable the push notification to the cloud-based PNCH for Windows Phone with the Skype for Business app</span></span>
    
   - <span data-ttu-id="395ef-118">**启用 apple 推送通知**将为运行 apple iOS 的设备（例如，IPhone、iPad）启用 apple PNCH 的推送通知，并使用 Skype for business 应用</span><span class="sxs-lookup"><span data-stu-id="395ef-118">**Enable Apple push notification** will enable the push notification to the Apple PNCH for devices running Apple's iOS (for example, iPhone, iPad) and using the Skype for Business app</span></span>
    
3. <span data-ttu-id="395ef-p105">完成策略编辑后，单击“**提交**”可保存更改。如果需要删除所做的更改，请选择“**取消**”。将不会保存对策略的任何更改。</span><span class="sxs-lookup"><span data-stu-id="395ef-p105">When you have completed the edits of the policy, click **Commit** to save your changes. If you need to delete the changes you have made, select **Cancel**. No changes will be saved to the policy.</span></span>
    

