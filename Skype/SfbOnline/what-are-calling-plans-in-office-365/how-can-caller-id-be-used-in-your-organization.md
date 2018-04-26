---
title: 如何在你的组织中使用来电显示
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz
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
description: 呼叫方 ID 可以通过使用称为 CallingLineIdentity 的策略控制入站和出站呼叫的电话系统用户。
ms.openlocfilehash: 4dc596e8301310f2c229c46add5795e72c432daf
ms.sourcegitcommit: f942232d43fc4ad56b34dd400fdb4bca39013f5f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a><span data-ttu-id="73088-103">如何在你的组织中使用来电显示</span><span class="sxs-lookup"><span data-stu-id="73088-103">How can caller ID be used in your organization</span></span>

<span data-ttu-id="73088-104">呼叫方 ID 可以通过使用称为 CallingLineIdentity 的策略控制入站和出站呼叫的电话系统用户。</span><span class="sxs-lookup"><span data-stu-id="73088-104">Caller ID can be controlled for both inbound and outbound calls for Phone System users by using a policy called CallingLineIdentity.</span></span>
  
<span data-ttu-id="73088-105">呼叫方 ID 功能用户都可以使用所有电话系统而不考虑的 PSTN 连接性：</span><span class="sxs-lookup"><span data-stu-id="73088-105">The Caller ID functionality is available to all Phone System users regardless of PSTN connectivity:</span></span>
  
- <span data-ttu-id="73088-106">在线 PSTN 连接</span><span class="sxs-lookup"><span data-stu-id="73088-106">Online PSTN Connectivity</span></span>
    
- <span data-ttu-id="73088-107">使用 Skype for Business Cloud Connector Edition 的内部部署 PSTN 连接（要求使用 Cloud Connector Edition 1.4.2 及更高版本）</span><span class="sxs-lookup"><span data-stu-id="73088-107">On-Premises PSTN Connectivity with Skype for Business Cloud Connector Edition (requires Cloud Connector Edition 1.4.2 and beyond)</span></span>
    
- <span data-ttu-id="73088-108">使用 Skype for Business Server 的内部部署 PSTN 连接（要求使用 Skype for Business Server 2015 CU5 及更高版本）</span><span class="sxs-lookup"><span data-stu-id="73088-108">On-Premises PSTN Connectivity with Skype for Business Server (requires Skype for Business Server 2015 CU5 and beyond)</span></span>
    
> [!NOTE]
> <span data-ttu-id="73088-109">[!注释] 此策略在 Skype for Business 2015 Server 上不可用。</span><span class="sxs-lookup"><span data-stu-id="73088-109">This policy isn't available in Skype for Business 2015 Server.</span></span> 
  
## <a name="outbound-caller-id"></a><span data-ttu-id="73088-110">出站来电显示</span><span class="sxs-lookup"><span data-stu-id="73088-110">Outbound caller ID</span></span>

<span data-ttu-id="73088-111">出站 PSTN 来电显示有三个对应选项：</span><span class="sxs-lookup"><span data-stu-id="73088-111">There are three options available for outbound PSTN Caller ID:</span></span>
  
- <span data-ttu-id="73088-112">分配给用户，这是默认值的电话号码。</span><span class="sxs-lookup"><span data-stu-id="73088-112">The telephone number assigned to the user, which is the default.</span></span>
    
- <span data-ttu-id="73088-113">被归为一种*服务*的电话号码，*免费*在您调用计划在 Office 365 提供电话号码数字库存。</span><span class="sxs-lookup"><span data-stu-id="73088-113">A telephone number that is classified as a *service* and *toll-free* number in your Calling Plans in Office 365 telephone number inventory.</span></span> <span data-ttu-id="73088-114">它通常会指派给某个组织自动助理或调用队列。</span><span class="sxs-lookup"><span data-stu-id="73088-114">It is usually assigned to an organizational auto attendant or call queue.</span></span>
    
- <span data-ttu-id="73088-115">设置为匿名。</span><span class="sxs-lookup"><span data-stu-id="73088-115">Set to anonymous.</span></span>
    
<span data-ttu-id="73088-116">但你不能为出站来电显示分配以下类型的电话号码：</span><span class="sxs-lookup"><span data-stu-id="73088-116">However, you can't assign these types of phone numbers for the outbound caller ID:</span></span>
  
- <span data-ttu-id="73088-117">任何属于调用计划通过电话*用户*的电话号码数字库存</span><span class="sxs-lookup"><span data-stu-id="73088-117">Any phone numbers that are classified as a  *user*  in your Calling Plans telephone number inventory</span></span>
    
- <span data-ttu-id="73088-118">Skype for Business Server 内部部署电话号码</span><span class="sxs-lookup"><span data-stu-id="73088-118">A Skype for Business Server on-premises phone number</span></span>
    
<span data-ttu-id="73088-119">要设置出站来电显示，请参见[为用户设置来电显示](set-the-caller-id-for-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="73088-119">To set the outbound caller ID, see [Set the Caller ID for a user](set-the-caller-id-for-a-user.md).</span></span>
  
### <a name="end-user-control-of-outbound-caller-id"></a><span data-ttu-id="73088-120">出站来电显示的最终用户控制</span><span class="sxs-lookup"><span data-stu-id="73088-120">End User Control of Outbound Caller ID</span></span>

<span data-ttu-id="73088-121">EnableUserOverride 属性单个或多个用户可用来更改其呼叫方 ID 设置为**匿名**。</span><span class="sxs-lookup"><span data-stu-id="73088-121">The EnableUserOverride attribute enables single or multiple users to change their Caller ID setting to **Anonymous**.</span></span> <span data-ttu-id="73088-122">这只适用于 CallingLineIdentity 策略配置 CallingIDSubstitute 参数为 LineURI 或替代。</span><span class="sxs-lookup"><span data-stu-id="73088-122">This only applies when a CallingLineIdentity policy is configured with a CallingIDSubstitute parameter of either LineURI or Substitute.</span></span> <span data-ttu-id="73088-123">EnableUserOverride 的默认值为 False。</span><span class="sxs-lookup"><span data-stu-id="73088-123">The default value of EnableUserOverride is False.</span></span>
  
<span data-ttu-id="73088-124">最终用户可以使用的 Skype 的业务桌面客户端的**调用转发设置**选项卡上将其呼叫方 ID 设置为**匿名**。</span><span class="sxs-lookup"><span data-stu-id="73088-124">Your end users can set their caller ID to **Anonymous** by using the **Call Forward Settings** tab in the Skype for Business desktop client.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="73088-125">**Windows**</span><span class="sxs-lookup"><span data-stu-id="73088-125">**Windows**</span></span> <br/> |<span data-ttu-id="73088-126">**版本**</span><span class="sxs-lookup"><span data-stu-id="73088-126">**Version**</span></span> <br/> |<span data-ttu-id="73088-127">**支持**</span><span class="sxs-lookup"><span data-stu-id="73088-127">**Supported**</span></span> <br/> |
|<span data-ttu-id="73088-128">即点即用</span><span class="sxs-lookup"><span data-stu-id="73088-128">Click-to-Run</span></span>  <br/> |<span data-ttu-id="73088-129">2016 年 12 月 6 日发布的当前频道 - 版本 1611（内部版本 7571.2072）</span><span class="sxs-lookup"><span data-stu-id="73088-129">Current Channel released on December 6, 2016 - version 1611 (Build 7571.2072)</span></span>  <br/> |<span data-ttu-id="73088-130">是</span><span class="sxs-lookup"><span data-stu-id="73088-130">Yes</span></span>  <br/> |
|<span data-ttu-id="73088-131">即点即用</span><span class="sxs-lookup"><span data-stu-id="73088-131">Click-to-Run</span></span>  <br/> |<span data-ttu-id="73088-132">2017 年 2 月 22 日发布的延期频道的首次发布 - 版本 1701（内部版本 7766.2060）</span><span class="sxs-lookup"><span data-stu-id="73088-132">First Release for Deferred Channel released on February 22, 2017 - Version 1701 (Build 7766.2060)</span></span>  <br/> |<span data-ttu-id="73088-133">是</span><span class="sxs-lookup"><span data-stu-id="73088-133">Yes</span></span>  <br/> |
|<span data-ttu-id="73088-134">即点即用</span><span class="sxs-lookup"><span data-stu-id="73088-134">Click-to-Run</span></span>  <br/> |<span data-ttu-id="73088-135">延迟发布的 6 月 13，2017-版本 1701 (生成 7766.2092) 的通道</span><span class="sxs-lookup"><span data-stu-id="73088-135">Deferred Channel released on June 13, 2017 - Version 1701 (Build 7766.2092)</span></span>  <br/> |<span data-ttu-id="73088-136">是</span><span class="sxs-lookup"><span data-stu-id="73088-136">Yes</span></span>  <br/> |
|<span data-ttu-id="73088-137">MSI</span><span class="sxs-lookup"><span data-stu-id="73088-137">MSI</span></span>  <br/> |<span data-ttu-id="73088-138">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="73088-138">Skype for Business</span></span>  <br/> |<span data-ttu-id="73088-139">否</span><span class="sxs-lookup"><span data-stu-id="73088-139">No</span></span>  <br/> |
|<span data-ttu-id="73088-140">Mac</span><span class="sxs-lookup"><span data-stu-id="73088-140">Mac</span></span>  <br/> |<span data-ttu-id="73088-141">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="73088-141">Skype for Business</span></span>  <br/> |<span data-ttu-id="73088-142">否</span><span class="sxs-lookup"><span data-stu-id="73088-142">No</span></span>  <br/> |
   
## <a name="inbound-caller-id"></a><span data-ttu-id="73088-143">入站来电显示</span><span class="sxs-lookup"><span data-stu-id="73088-143">Inbound Caller ID</span></span>

<span data-ttu-id="73088-144">BlockIncomingCallerID 属性可以阻止传入的 PSTN 呼叫的呼叫者 ID。</span><span class="sxs-lookup"><span data-stu-id="73088-144">The BlockIncomingCallerID attribute allows for blocking the caller ID on incoming PSTN calls.</span></span> <span data-ttu-id="73088-145">您可以设置此属性，但它不是供最终用户在用户设置页上。</span><span class="sxs-lookup"><span data-stu-id="73088-145">You can set this attribute, but it isn't available to your end users on the user settings page.</span></span> <span data-ttu-id="73088-146">当前仅在使用在线 PSTN 连接时可用。</span><span class="sxs-lookup"><span data-stu-id="73088-146">And it is currently available only with Online PSTN connectivity.</span></span>
  
<span data-ttu-id="73088-147">要设置出站来电显示，请参见[为用户设置来电显示](set-the-caller-id-for-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="73088-147">To set the outbound caller ID, see [Set the Caller ID for a user](set-the-caller-id-for-a-user.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="73088-148">相关主题</span><span class="sxs-lookup"><span data-stu-id="73088-148">Related topics</span></span>
[<span data-ttu-id="73088-149">关于转移电话号码的常见问题</span><span class="sxs-lookup"><span data-stu-id="73088-149">Transferring phone numbers common questions</span></span>](transferring-phone-numbers-common-questions.md)

[<span data-ttu-id="73088-150">用于通话套餐的不同类型的电话号码</span><span class="sxs-lookup"><span data-stu-id="73088-150">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="73088-151">管理你的组织的电话号码</span><span class="sxs-lookup"><span data-stu-id="73088-151">Manage phone numbers for your organization</span></span>](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[<span data-ttu-id="73088-152">紧急呼叫条款和条件</span><span class="sxs-lookup"><span data-stu-id="73088-152">Emergency calling terms and conditions</span></span>](../legal-and-regulatory/emergency-calling-terms-and-conditions.md)

<span data-ttu-id="73088-153">[Skype for Business Online：紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="73088-153">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 