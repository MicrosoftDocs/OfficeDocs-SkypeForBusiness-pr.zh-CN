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
search.appverid: MET150
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
description: 呼叫者 ID 可以通过使用名为 CallingLineIdentity 策略控制的电话系统的用户的入站和出站呼叫。
ms.openlocfilehash: 4ae5c54d68410096104f61bf8cdbd71fa0628003
ms.sourcegitcommit: 99bc2db8cb857b6fd2ddf9b837198be849dafb9b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/13/2019
ms.locfileid: "29981911"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a><span data-ttu-id="9f149-103">如何在你的组织中使用来电显示</span><span class="sxs-lookup"><span data-stu-id="9f149-103">How can caller ID be used in your organization</span></span>

<span data-ttu-id="9f149-104">呼叫者 ID 可以通过使用名为 CallingLineIdentity 策略控制的电话系统的用户的入站和出站呼叫。</span><span class="sxs-lookup"><span data-stu-id="9f149-104">Caller ID can be controlled for both inbound and outbound calls for Phone System users by using a policy called CallingLineIdentity.</span></span>
  
<span data-ttu-id="9f149-105">呼叫者 ID 功能，无论 PSTN 连接的所有电话系统用户：</span><span class="sxs-lookup"><span data-stu-id="9f149-105">The Caller ID functionality is available to all Phone System users regardless of PSTN connectivity:</span></span>
  
- <span data-ttu-id="9f149-106">在线 PSTN 连接</span><span class="sxs-lookup"><span data-stu-id="9f149-106">Online PSTN Connectivity</span></span>
    
- <span data-ttu-id="9f149-107">使用 Skype for Business Cloud Connector Edition 的内部部署 PSTN 连接（要求使用 Cloud Connector Edition 1.4.2 及更高版本）</span><span class="sxs-lookup"><span data-stu-id="9f149-107">On-Premises PSTN Connectivity with Skype for Business Cloud Connector Edition (requires Cloud Connector Edition 1.4.2 and beyond)</span></span>
    
- <span data-ttu-id="9f149-108">使用 Skype for Business Server 的内部部署 PSTN 连接（要求使用 Skype for Business Server 2015 CU5 及更高版本）</span><span class="sxs-lookup"><span data-stu-id="9f149-108">On-Premises PSTN Connectivity with Skype for Business Server (requires Skype for Business Server 2015 CU5 and beyond)</span></span>
    
> [!NOTE]
> <span data-ttu-id="9f149-109">[!注释] 此策略在 Skype for Business 2015 Server 上不可用。</span><span class="sxs-lookup"><span data-stu-id="9f149-109">This policy isn't available in Skype for Business 2015 Server.</span></span> 
  
## <a name="outbound-caller-id"></a><span data-ttu-id="9f149-110">出站来电显示</span><span class="sxs-lookup"><span data-stu-id="9f149-110">Outbound caller ID</span></span>

<span data-ttu-id="9f149-111">出站 PSTN 来电显示有三个对应选项：</span><span class="sxs-lookup"><span data-stu-id="9f149-111">There are three options available for outbound PSTN Caller ID:</span></span>
  
- <span data-ttu-id="9f149-112">分配给用户，这是默认电话号码。</span><span class="sxs-lookup"><span data-stu-id="9f149-112">The telephone number assigned to the user, which is the default.</span></span>
    
- <span data-ttu-id="9f149-113">在您的 Office 365 电话号码库存通话套餐中分类为*服务*和*免费电话*的电话号码。</span><span class="sxs-lookup"><span data-stu-id="9f149-113">A telephone number that is classified as a *service* and *toll-free* number in your Calling Plans in Office 365 telephone number inventory.</span></span> <span data-ttu-id="9f149-114">它通常分配给组织的自动助理或呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="9f149-114">It is usually assigned to an organizational auto attendant or call queue.</span></span>
    
- <span data-ttu-id="9f149-115">设置为匿名。</span><span class="sxs-lookup"><span data-stu-id="9f149-115">Set to anonymous.</span></span>
    
<span data-ttu-id="9f149-116">但你不能为出站来电显示分配以下类型的电话号码：</span><span class="sxs-lookup"><span data-stu-id="9f149-116">However, you can't assign these types of phone numbers for the outbound caller ID:</span></span>
  
- <span data-ttu-id="9f149-117">任何电话号码分类为*用户*在您调用计划的电话号码库存</span><span class="sxs-lookup"><span data-stu-id="9f149-117">Any phone numbers that are classified as a  *user*  in your Calling Plans telephone number inventory</span></span>
    
- <span data-ttu-id="9f149-118">Skype for Business Server 内部部署电话号码</span><span class="sxs-lookup"><span data-stu-id="9f149-118">A Skype for Business Server on-premises phone number</span></span>
    
<span data-ttu-id="9f149-119">要设置出站来电显示，请参见[为用户设置来电显示](set-the-caller-id-for-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="9f149-119">To set the outbound caller ID, see [Set the Caller ID for a user](set-the-caller-id-for-a-user.md).</span></span>
  
### <a name="end-user-control-of-outbound-caller-id"></a><span data-ttu-id="9f149-120">出站来电显示的最终用户控制</span><span class="sxs-lookup"><span data-stu-id="9f149-120">End User Control of Outbound Caller ID</span></span>

<span data-ttu-id="9f149-121">通过 EnableUserOverride 属性，单个用户或多个用户可以将其"来电显示"设置更改为" **匿名**"。</span><span class="sxs-lookup"><span data-stu-id="9f149-121">The EnableUserOverride attribute enables single or multiple users to change their Caller ID setting to **Anonymous**.</span></span> <span data-ttu-id="9f149-122">仅当 CallingLineIdentity 策略配置了 CallingIDSubstitute 参数 LineURI 或 Substitute 时适用。</span><span class="sxs-lookup"><span data-stu-id="9f149-122">This only applies when a CallingLineIdentity policy is configured with a CallingIDSubstitute parameter of either LineURI or Substitute.</span></span> <span data-ttu-id="9f149-123">EnableUserOverride 的默认值是 False。</span><span class="sxs-lookup"><span data-stu-id="9f149-123">The default value of EnableUserOverride is False.</span></span>
  
<span data-ttu-id="9f149-124">最终用户可以通过使用 for Business 桌面客户端的 Skype 中的**设置**选项卡将其呼叫者 ID 设置为**匿名**，选择**呼叫最终用户**（如果由管理员启用），选择所有呼叫的**隐藏我的电话号码和配置文件信息**.</span><span class="sxs-lookup"><span data-stu-id="9f149-124">Your end users can set their caller ID to **Anonymous** by using the **Settings** tab in the Skype for Business desktop client, select **Calls an End User** (if enabled by admin), select **Hide my phone number and profile information for all calls**.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="9f149-125">**Windows**</span><span class="sxs-lookup"><span data-stu-id="9f149-125">**Windows**</span></span> <br/> |<span data-ttu-id="9f149-126">**版本**</span><span class="sxs-lookup"><span data-stu-id="9f149-126">**Version**</span></span> <br/> |<span data-ttu-id="9f149-127">**支持**</span><span class="sxs-lookup"><span data-stu-id="9f149-127">**Supported**</span></span> <br/> |
|<span data-ttu-id="9f149-128">即点即用</span><span class="sxs-lookup"><span data-stu-id="9f149-128">Click-to-Run</span></span>  <br/> |<span data-ttu-id="9f149-129">2016 年 12 月 6 日发布的当前频道 - 版本 1611（内部版本 7571.2072）</span><span class="sxs-lookup"><span data-stu-id="9f149-129">Current Channel released on December 6, 2016 - version 1611 (Build 7571.2072)</span></span>  <br/> |<span data-ttu-id="9f149-130">是</span><span class="sxs-lookup"><span data-stu-id="9f149-130">Yes</span></span>  <br/> |
|<span data-ttu-id="9f149-131">即点即用</span><span class="sxs-lookup"><span data-stu-id="9f149-131">Click-to-Run</span></span>  <br/> |<span data-ttu-id="9f149-132">2017 年 2 月 22 日发布的延期频道的首次发布 - 版本 1701（内部版本 7766.2060）</span><span class="sxs-lookup"><span data-stu-id="9f149-132">First Release for Deferred Channel released on February 22, 2017 - Version 1701 (Build 7766.2060)</span></span>  <br/> |<span data-ttu-id="9f149-133">是</span><span class="sxs-lookup"><span data-stu-id="9f149-133">Yes</span></span>  <br/> |
|<span data-ttu-id="9f149-134">即点即用</span><span class="sxs-lookup"><span data-stu-id="9f149-134">Click-to-Run</span></span>  <br/> |<span data-ttu-id="9f149-135">延迟通道于 2017 年 6 月 13 日发布 - 版本 1701 (Build 7766.2092)</span><span class="sxs-lookup"><span data-stu-id="9f149-135">Deferred Channel released on June 13, 2017 - Version 1701 (Build 7766.2092)</span></span>  <br/> |<span data-ttu-id="9f149-136">是</span><span class="sxs-lookup"><span data-stu-id="9f149-136">Yes</span></span>  <br/> |
|<span data-ttu-id="9f149-137">MSI</span><span class="sxs-lookup"><span data-stu-id="9f149-137">MSI</span></span>  <br/> |<span data-ttu-id="9f149-138">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="9f149-138">Skype for Business</span></span>  <br/> |<span data-ttu-id="9f149-139">否</span><span class="sxs-lookup"><span data-stu-id="9f149-139">No</span></span>  <br/> |
|<span data-ttu-id="9f149-140">Mac</span><span class="sxs-lookup"><span data-stu-id="9f149-140">Mac</span></span>  <br/> |<span data-ttu-id="9f149-141">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="9f149-141">Skype for Business</span></span>  <br/> |<span data-ttu-id="9f149-142">否</span><span class="sxs-lookup"><span data-stu-id="9f149-142">No</span></span>  <br/> |
   
## <a name="inbound-caller-id"></a><span data-ttu-id="9f149-143">入站来电显示</span><span class="sxs-lookup"><span data-stu-id="9f149-143">Inbound Caller ID</span></span>

<span data-ttu-id="9f149-144">BlockIncomingCallerID 属性可以用于阻止 PSTN 来电的来电显示。</span><span class="sxs-lookup"><span data-stu-id="9f149-144">The BlockIncomingCallerID attribute allows for blocking the caller ID on incoming PSTN calls.</span></span> <span data-ttu-id="9f149-145">您可以设置此属性，而只是向最终用户在用户设置页上可用。</span><span class="sxs-lookup"><span data-stu-id="9f149-145">You can set this attribute, but it isn't available to your end users on the user settings page.</span></span> <span data-ttu-id="9f149-146">当前仅在使用在线 PSTN 连接时可用。</span><span class="sxs-lookup"><span data-stu-id="9f149-146">And it is currently available only with Online PSTN connectivity.</span></span>
  
<span data-ttu-id="9f149-147">要设置出站来电显示，请参见[为用户设置来电显示](set-the-caller-id-for-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="9f149-147">To set the outbound caller ID, see [Set the Caller ID for a user](set-the-caller-id-for-a-user.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="9f149-148">相关主题</span><span class="sxs-lookup"><span data-stu-id="9f149-148">Related topics</span></span>
[<span data-ttu-id="9f149-149">关于转移电话号码的常见问题</span><span class="sxs-lookup"><span data-stu-id="9f149-149">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="9f149-150">用于通话套餐的不同类型的电话号码</span><span class="sxs-lookup"><span data-stu-id="9f149-150">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="9f149-151">管理你的组织的电话号码</span><span class="sxs-lookup"><span data-stu-id="9f149-151">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="9f149-152">紧急呼叫条款和条件</span><span class="sxs-lookup"><span data-stu-id="9f149-152">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="9f149-153">[Skype for Business Online：紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="9f149-153">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 
