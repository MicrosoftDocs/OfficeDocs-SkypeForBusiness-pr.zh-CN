---
title: 移动客户端创建或编辑推送通知配置
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientPushNotificationCfgEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: fb39af60-c999-42fb-9538-0bd87098f508
ROBOTS: NOINDEX, NOFOLLOW
description: 推送通知和推送通知交换所 (PNCH) 是移动功能的主要组成部分。 推送通知是将消息发送到 PNCH 的过程。 消息将保留在此处，直到它能发往移动客户端或超时段过期为止。
ms.openlocfilehash: 3c72c5b123a906d74cfeb0a1fef5c1e765fe030c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49808742"
---
# <a name="mobile-client-create-or-edit-push-notification-configuration"></a><span data-ttu-id="825f1-105">移动客户端：创建或编辑推送通知配置</span><span class="sxs-lookup"><span data-stu-id="825f1-105">Mobile Client: Create or Edit Push Notification Configuration</span></span>
 
<span data-ttu-id="825f1-106">推送通知和推送通知交换所 (PNCH) 是移动功能的主要组成部分。</span><span class="sxs-lookup"><span data-stu-id="825f1-106">Push Notification and the Push Notification Clearing House (PNCH) are two key parts of the mobility feature.</span></span> <span data-ttu-id="825f1-107">推送通知是将消息发送到 PNCH 的过程。</span><span class="sxs-lookup"><span data-stu-id="825f1-107">Push notification is the process where a message is sent to the PNCH.</span></span> <span data-ttu-id="825f1-108">消息将保留在此处，直到它能发往移动客户端或超时段过期为止。</span><span class="sxs-lookup"><span data-stu-id="825f1-108">The message is held here until it can be delivered to the mobile client, or the timeout period expires.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="825f1-109">时间段在推送通知交换所设置，不能由部署的用户或管理员进行配置。</span><span class="sxs-lookup"><span data-stu-id="825f1-109">The time period is set at the Push Notification Clearing House and is not configurable by the user or the administrator of your deployment.</span></span> 
  
<span data-ttu-id="825f1-110">若要启用推送通知，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="825f1-110">To enable Push Notification, you do the following:</span></span>
  
1. <span data-ttu-id="825f1-111">**范围：** 记下此策略的范围。</span><span class="sxs-lookup"><span data-stu-id="825f1-111">**Scope:** Note the scope for this policy.</span></span> <span data-ttu-id="825f1-112">它可以是 **全局**，它适用于此部署中的所有用户，或站点 **，这是** 仅分配给指定站点中的主服务器的用户。</span><span class="sxs-lookup"><span data-stu-id="825f1-112">It can either be **Global**, which applies to all users in this deployment, or **Site**, which is only users assigned to home servers in the specified site.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="825f1-113">在一个策略级别应用的策略设置可覆盖在其他策略级别应用的设置。</span><span class="sxs-lookup"><span data-stu-id="825f1-113">Policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="825f1-114">策略优先级为：用户策略 (站点) 覆盖站点策略，然后站点策略覆盖全局策略 (影响最小) 。</span><span class="sxs-lookup"><span data-stu-id="825f1-114">Policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="825f1-115">这意味着，策略设置越接近策略影响的对象，它对对象的影响就越大。</span><span class="sxs-lookup"><span data-stu-id="825f1-115">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> 
  
2. <span data-ttu-id="825f1-116">通过单击以下复选框选择您要启用的推送通知服务：</span><span class="sxs-lookup"><span data-stu-id="825f1-116">Select which push notification services you want to enable by clicking the check box for:</span></span>
    
   - <span data-ttu-id="825f1-117">**启用 Microsoft 推送通知** 将启用推送通知到使用 Skype for Business 应用的基于云的 Windows Phone PNCH</span><span class="sxs-lookup"><span data-stu-id="825f1-117">**Enable Microsoft push notification** will enable the push notification to the cloud-based PNCH for Windows Phone with the Skype for Business app</span></span>
    
   - <span data-ttu-id="825f1-118">**启用 Apple** 推送通知将为运行 Apple iOS (（例如，iPhone、iPad) 以及使用 Skype for Business 应用）的设备启用推送通知到 Apple PNCH</span><span class="sxs-lookup"><span data-stu-id="825f1-118">**Enable Apple push notification** will enable the push notification to the Apple PNCH for devices running Apple's iOS (for example, iPhone, iPad) and using the Skype for Business app</span></span>
    
3. <span data-ttu-id="825f1-p105">完成策略编辑后，单击“提交”可保存更改。如果需要删除所做的更改，请选择“取消”。将不会保存对策略的任何更改。</span><span class="sxs-lookup"><span data-stu-id="825f1-p105">When you have completed the edits of the policy, click **Commit** to save your changes. If you need to delete the changes you have made, select **Cancel**. No changes will be saved to the policy.</span></span>
    

