---
title: "如何在你的组织中使用来电显示"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
- Strat_SB_PSTN
description: "呼叫方 ID 可以通过使用称为 CallingLineIdentity 的策略控制入站和出站呼叫的电话系统用户。"
ms.openlocfilehash: e68b9c2130f5cfc8a054e485367351eccbffc93c
ms.sourcegitcommit: 6c59400d2e677c1022f320c91cd7f102b99d292b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2018
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a><span data-ttu-id="f17be-103">如何在你的组织中使用来电显示</span><span class="sxs-lookup"><span data-stu-id="f17be-103">How can caller ID be used in your organization</span></span>

<span data-ttu-id="f17be-104">呼叫方 ID 可以通过使用称为 CallingLineIdentity 的策略控制入站和出站呼叫的电话系统用户。</span><span class="sxs-lookup"><span data-stu-id="f17be-104">Caller ID can be controlled for both inbound and outbound calls for Phone System users by using a policy called CallingLineIdentity.</span></span>
  
<span data-ttu-id="f17be-105">呼叫方 ID 功能用户都可以使用所有电话系统而不考虑的 PSTN 连接性：</span><span class="sxs-lookup"><span data-stu-id="f17be-105">The Caller ID functionality is available to all Phone System users regardless of PSTN connectivity:</span></span>
  
- <span data-ttu-id="f17be-106">在线 PSTN 连接</span><span class="sxs-lookup"><span data-stu-id="f17be-106">Online PSTN Connectivity</span></span>
    
- <span data-ttu-id="f17be-107">使用 Skype for Business Cloud Connector Edition 的内部部署 PSTN 连接（要求使用 Cloud Connector Edition 1.4.2 及更高版本）</span><span class="sxs-lookup"><span data-stu-id="f17be-107">On-Premises PSTN Connectivity with Skype for Business Cloud Connector Edition (requires Cloud Connector Edition 1.4.2 and beyond)</span></span>
    
- <span data-ttu-id="f17be-108">使用 Skype for Business Server 的内部部署 PSTN 连接（要求使用 Skype for Business Server 2015 CU5 及更高版本）</span><span class="sxs-lookup"><span data-stu-id="f17be-108">On-Premises PSTN Connectivity with Skype for Business Server (requires Skype for Business Server 2015 CU5 and beyond)</span></span>
    
> [!NOTE]
> <span data-ttu-id="f17be-109">[!注释] 此策略在 Skype for Business 2015 Server 上不可用。</span><span class="sxs-lookup"><span data-stu-id="f17be-109">This policy isn't available in Skype for Business 2015 Server.</span></span> 
  
## <a name="outbound-caller-id"></a><span data-ttu-id="f17be-110">出站来电显示</span><span class="sxs-lookup"><span data-stu-id="f17be-110">Outbound caller ID</span></span>

<span data-ttu-id="f17be-111">出站 PSTN 来电显示有三个对应选项：</span><span class="sxs-lookup"><span data-stu-id="f17be-111">There are three options available for outbound PSTN Caller ID:</span></span>
  
- <span data-ttu-id="f17be-112">分配给用户，这是默认值的电话号码。</span><span class="sxs-lookup"><span data-stu-id="f17be-112">The telephone number assigned to the user, which is the default.</span></span>
    
- <span data-ttu-id="f17be-113">被归为一种*服务*的电话号码，*免费*在您调用计划在 Office 365 提供电话号码数字库存。</span><span class="sxs-lookup"><span data-stu-id="f17be-113">A telephone number that is classified as a *service* and *toll-free* number in your Calling Plans in Office 365 telephone number inventory.</span></span> <span data-ttu-id="f17be-114">它通常会指派给某个组织自动助理或调用队列。</span><span class="sxs-lookup"><span data-stu-id="f17be-114">It is usually assigned to an organizational auto attendant or call queue.</span></span>
    
- <span data-ttu-id="f17be-115">设置为匿名。</span><span class="sxs-lookup"><span data-stu-id="f17be-115">Set to anonymous.</span></span>
    
<span data-ttu-id="f17be-116">但你不能为出站来电显示分配以下类型的电话号码：</span><span class="sxs-lookup"><span data-stu-id="f17be-116">However, you can't assign these types of phone numbers for the outbound caller ID:</span></span>
  
- <span data-ttu-id="f17be-117">任何属于调用计划通过电话*用户*的电话号码数字库存</span><span class="sxs-lookup"><span data-stu-id="f17be-117">Any phone numbers that are classified as a  *user*  in your Calling Plans telephone number inventory</span></span>
    
- <span data-ttu-id="f17be-118">Skype for Business Server 内部部署电话号码</span><span class="sxs-lookup"><span data-stu-id="f17be-118">A Skype for Business Server on-premises phone number</span></span>
    
<span data-ttu-id="f17be-119">要设置出站来电显示，请参见[为用户设置来电显示](set-the-caller-id-for-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="f17be-119">To set the outbound caller ID, see [Set the Caller ID for a user](set-the-caller-id-for-a-user.md).</span></span>
  
### <a name="end-user-control-of-outbound-caller-id"></a><span data-ttu-id="f17be-120">出站来电显示的最终用户控制</span><span class="sxs-lookup"><span data-stu-id="f17be-120">End User Control of Outbound Caller ID</span></span>

<span data-ttu-id="f17be-121">EnableUserOverride 属性单个或多个用户可用来更改其呼叫方 ID 设置为**匿名**。</span><span class="sxs-lookup"><span data-stu-id="f17be-121">The EnableUserOverride attribute enables single or multiple users to change their Caller ID setting to **Anonymous**.</span></span> <span data-ttu-id="f17be-122">这只适用于 CallingLineIdentity 策略配置 CallingIDSubstitute 参数为 LineURI 或替代。</span><span class="sxs-lookup"><span data-stu-id="f17be-122">This only applies when a CallingLineIdentity policy is configured with a CallingIDSubstitute parameter of either LineURI or Substitute.</span></span> <span data-ttu-id="f17be-123">EnableUserOverride 的默认值为 False。</span><span class="sxs-lookup"><span data-stu-id="f17be-123">The default value of EnableUserOverride is False.</span></span>
  
<span data-ttu-id="f17be-124">最终用户可以使用的 Skype 的业务桌面客户端的**调用转发设置**选项卡上将其呼叫方 ID 设置为**匿名**。</span><span class="sxs-lookup"><span data-stu-id="f17be-124">Your end users can set their caller ID to **Anonymous** by using the **Call Forward Settings** tab in the Skype for Business desktop client.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="f17be-125">**Windows**</span><span class="sxs-lookup"><span data-stu-id="f17be-125">**Windows**</span></span> <br/> |<span data-ttu-id="f17be-126">**版本**</span><span class="sxs-lookup"><span data-stu-id="f17be-126">**Version**</span></span> <br/> |<span data-ttu-id="f17be-127">**支持**</span><span class="sxs-lookup"><span data-stu-id="f17be-127">**Supported**</span></span> <br/> |
|<span data-ttu-id="f17be-128">即点即用</span><span class="sxs-lookup"><span data-stu-id="f17be-128">Click-to-Run</span></span>  <br/> |<span data-ttu-id="f17be-129">2016 年 12 月 6 日发布的当前频道 - 版本 1611（内部版本 7571.2072）</span><span class="sxs-lookup"><span data-stu-id="f17be-129">Current Channel released on December 6, 2016 - version 1611 (Build 7571.2072)</span></span>  <br/> |<span data-ttu-id="f17be-130">是</span><span class="sxs-lookup"><span data-stu-id="f17be-130">Yes</span></span>  <br/> |
|<span data-ttu-id="f17be-131">即点即用</span><span class="sxs-lookup"><span data-stu-id="f17be-131">Click-to-Run</span></span>  <br/> |<span data-ttu-id="f17be-132">2017 年 2 月 22 日发布的延期频道的首次发布 - 版本 1701（内部版本 7766.2060）</span><span class="sxs-lookup"><span data-stu-id="f17be-132">First Release for Deferred Channel released on February 22, 2017 - Version 1701 (Build 7766.2060)</span></span>  <br/> |<span data-ttu-id="f17be-133">是</span><span class="sxs-lookup"><span data-stu-id="f17be-133">Yes</span></span>  <br/> |
|<span data-ttu-id="f17be-134">即点即用</span><span class="sxs-lookup"><span data-stu-id="f17be-134">Click-to-Run</span></span>  <br/> |<span data-ttu-id="f17be-135">延迟发布的 6 月 13，2017-版本 1701 (生成 7766.2092) 的通道</span><span class="sxs-lookup"><span data-stu-id="f17be-135">Deferred Channel released on June 13, 2017 - Version 1701 (Build 7766.2092)</span></span>  <br/> |<span data-ttu-id="f17be-136">是</span><span class="sxs-lookup"><span data-stu-id="f17be-136">Yes</span></span>  <br/> |
|<span data-ttu-id="f17be-137">MSI</span><span class="sxs-lookup"><span data-stu-id="f17be-137">MSI</span></span>  <br/> |<span data-ttu-id="f17be-138">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="f17be-138">Skype for Business</span></span>  <br/> |<span data-ttu-id="f17be-139">否</span><span class="sxs-lookup"><span data-stu-id="f17be-139">No</span></span>  <br/> |
|<span data-ttu-id="f17be-140">Mac</span><span class="sxs-lookup"><span data-stu-id="f17be-140">Mac</span></span>  <br/> |<span data-ttu-id="f17be-141">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="f17be-141">Skype for Business</span></span>  <br/> |<span data-ttu-id="f17be-142">否</span><span class="sxs-lookup"><span data-stu-id="f17be-142">No</span></span>  <br/> |
   
## <a name="inbound-caller-id"></a><span data-ttu-id="f17be-143">入站来电显示</span><span class="sxs-lookup"><span data-stu-id="f17be-143">Inbound Caller ID</span></span>

<span data-ttu-id="f17be-144">BlockIncomingCallerID 属性可以阻止传入的 PSTN 呼叫的呼叫者 ID。</span><span class="sxs-lookup"><span data-stu-id="f17be-144">The BlockIncomingCallerID attribute allows for blocking the caller ID on incoming PSTN calls.</span></span> <span data-ttu-id="f17be-145">您可以设置此属性，但它不是供最终用户在用户设置页上。</span><span class="sxs-lookup"><span data-stu-id="f17be-145">You can set this attribute, but it isn't available to your end users on the user settings page.</span></span> <span data-ttu-id="f17be-146">当前仅在使用在线 PSTN 连接时可用。</span><span class="sxs-lookup"><span data-stu-id="f17be-146">And it is currently available only with Online PSTN connectivity.</span></span>
  
<span data-ttu-id="f17be-147">要设置出站来电显示，请参见[为用户设置来电显示](set-the-caller-id-for-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="f17be-147">To set the outbound caller ID, see [Set the Caller ID for a user](set-the-caller-id-for-a-user.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="f17be-148">相关主题</span><span class="sxs-lookup"><span data-stu-id="f17be-148">Related topics</span></span>
[<span data-ttu-id="f17be-149">关于转移电话号码的常见问题</span><span class="sxs-lookup"><span data-stu-id="f17be-149">Transferring phone numbers common questions</span></span>](transferring-phone-numbers-common-questions.md)

[<span data-ttu-id="f17be-150">用于通话套餐的不同类型的电话号码</span><span class="sxs-lookup"><span data-stu-id="f17be-150">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="f17be-151">管理你的组织的电话号码</span><span class="sxs-lookup"><span data-stu-id="f17be-151">Manage phone numbers for your organization</span></span>](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[<span data-ttu-id="f17be-152">紧急呼叫条款和条件</span><span class="sxs-lookup"><span data-stu-id="f17be-152">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)

[<span data-ttu-id="f17be-153">Skype for Business Online：紧急呼叫免责标签</span><span class="sxs-lookup"><span data-stu-id="f17be-153">Skype for Business Online: Emergency Calling disclaimer label</span></span>](https://go.microsoft.com/fwlink/?LinkID=692099)

## <a name="feedback"></a><span data-ttu-id="f17be-154">反馈意见？</span><span class="sxs-lookup"><span data-stu-id="f17be-154">Feedback?</span></span>
<span data-ttu-id="f17be-155">提供产品反馈意见或让我们知道我们所执行的信息，请参阅[Skype 业务反馈](https://www.skypefeedback.com)。</span><span class="sxs-lookup"><span data-stu-id="f17be-155">To provide product feedback or to let us know how we're doing, see [Skype for Business Feedback](https://www.skypefeedback.com).</span></span>