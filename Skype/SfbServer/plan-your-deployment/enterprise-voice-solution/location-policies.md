---
title: 规划 Skype for Business Server 的位置策略
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: da3cca7f-f6e5-4b6f-90a1-2008e3dd1ebd
description: 阅读本主题，了解如何在 Skype for Business Server (中为增强型紧急服务 (E9-1-1) 规划位置企业语音。
ms.openlocfilehash: 1e89c2f0ea9d5115b29e9bc6d77b3863bb11888c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825532"
---
# <a name="plan-location-policies-for-skype-for-business-server"></a><span data-ttu-id="be1dc-103">规划 Skype for Business Server 的位置策略</span><span class="sxs-lookup"><span data-stu-id="be1dc-103">Plan location policies for Skype for Business Server</span></span>
 
<span data-ttu-id="be1dc-104">阅读本主题，了解如何在 Skype for Business Server (中为增强型紧急服务 (E9-1-1) 规划位置企业语音。</span><span class="sxs-lookup"><span data-stu-id="be1dc-104">Read this topic to learn how to plan location policies for an enhanced emergency services (E9-1-1) deployment in Skype for Business Server Enterprise Voice.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="be1dc-105">Skype for Business Server 现在支持为客户端配置多个紧急号码。</span><span class="sxs-lookup"><span data-stu-id="be1dc-105">Skype for Business Server now supports the configuration of multiple emergency numbers for a client.</span></span> <span data-ttu-id="be1dc-106">如果要配置多个紧急号码，必须按照 Skype for Business [Server](multiple-emergency-numbers.md) 中多个紧急号码的规划信息操作，在 Skype for Business 中配置 [多个紧急号码](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md)。</span><span class="sxs-lookup"><span data-stu-id="be1dc-106">If you want to configure multiple emergency numbers, you must follow the information in [Plan for multiple emergency numbers in Skype for Business Server](multiple-emergency-numbers.md) and [Configure multiple emergency numbers in Skype for Business](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md).</span></span> 
  
<span data-ttu-id="be1dc-107">可以使用 Skype for Business 控制面板或 [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) cmdlet 创建位置策略。</span><span class="sxs-lookup"><span data-stu-id="be1dc-107">You create location policies by using the Skype for Business Control Panel or by using the [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="be1dc-108">有关详细信息，请参阅在 [Skype for Business Server 中创建位置策略](../../deploy/deploy-enterprise-voice/create-location-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="be1dc-108">For more information, see [Create location policies in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-location-policies.md).</span></span>
  
<span data-ttu-id="be1dc-109">每个位置策略都包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="be1dc-109">Each location policy contains the following information:</span></span>
  
 <span data-ttu-id="be1dc-110">**启用增强型 9-1-1**</span><span class="sxs-lookup"><span data-stu-id="be1dc-110">**Enable Enhanced 9-1-1**</span></span>
  
<span data-ttu-id="be1dc-111">启用此值后，客户端将启用增强型紧急服务 (E9-1-1) 。</span><span class="sxs-lookup"><span data-stu-id="be1dc-111">When this value is enabled, the client is enabled for enhanced emergency services (E9-1-1).</span></span> <span data-ttu-id="be1dc-112">当客户端注册时，它会尝试从位置信息服务获取位置，并且将在紧急呼叫中包括位置信息。</span><span class="sxs-lookup"><span data-stu-id="be1dc-112">When a client registers, it attempts to acquire a location from the Location Information service and will include the location information as part of an emergency call.</span></span>
  
 <span data-ttu-id="be1dc-113">**位置**</span><span class="sxs-lookup"><span data-stu-id="be1dc-113">**Location**</span></span>
  
<span data-ttu-id="be1dc-114">此设置仅在启用增强型 **9-1-1 时** 使用。</span><span class="sxs-lookup"><span data-stu-id="be1dc-114">This setting is used only when **Enable Enhanced 9-1-1** is enabled.</span></span>
  
<span data-ttu-id="be1dc-115">可以配置位置 **设置** 以定义客户端行为，如下所示：</span><span class="sxs-lookup"><span data-stu-id="be1dc-115">You can configure the **Location** setting to define the client behavior as follows:</span></span>
  
- <span data-ttu-id="be1dc-116">将值设置为 **"否** "意味着不会提示用户输入位置。</span><span class="sxs-lookup"><span data-stu-id="be1dc-116">Setting the value to **No** means that the user will not be prompted for a location.</span></span>
    
- <span data-ttu-id="be1dc-117">将该值设置为 **"是** "意味着将提示用户输入位置，但可以消除提示。</span><span class="sxs-lookup"><span data-stu-id="be1dc-117">Setting the value to **Yes** means that the user will be prompted for a location, but can dismiss the prompt.</span></span>
    
- <span data-ttu-id="be1dc-118">将该值设置为 **"免责声明** "意味着将提示用户输入位置，并且如果用户尝试消除提示，也会显示免责声明。</span><span class="sxs-lookup"><span data-stu-id="be1dc-118">Setting the value to **Disclaimer** means that the user will be prompted for a location and also will be shown a disclaimer if they try to dismiss the prompt.</span></span> <span data-ttu-id="be1dc-119">在所有情况下，用户都可以继续使用客户端。</span><span class="sxs-lookup"><span data-stu-id="be1dc-119">In all cases, the user can continue to use the client.</span></span>
    
> [!NOTE]
> <span data-ttu-id="be1dc-120">如果用户在启用 E9-1-1 之前手动输入位置，则不显示免责声明文本。</span><span class="sxs-lookup"><span data-stu-id="be1dc-120">The disclaimer text will not appear if a user manually entered a location before being enabled for E9-1-1.</span></span> <span data-ttu-id="be1dc-121">已查看免责声明的用户不会查看对免责声明文本的更新。</span><span class="sxs-lookup"><span data-stu-id="be1dc-121">Updates to the disclaimer text will not be viewed by users that have already viewed the disclaimer.</span></span> 
  
 <span data-ttu-id="be1dc-122">**增强型紧急服务免责声明**</span><span class="sxs-lookup"><span data-stu-id="be1dc-122">**Enhanced Emergency Service Disclaimer**</span></span>
  
<span data-ttu-id="be1dc-123">此设置指定用户在消除位置提示时看到的免责声明。</span><span class="sxs-lookup"><span data-stu-id="be1dc-123">This setting specifies the disclaimer that users see if they dismiss the prompt for a location.</span></span> <span data-ttu-id="be1dc-124">在 Skype for Business Server 中，可以使用位置策略为不同的区域设置或不同的用户集设置不同的免责声明。</span><span class="sxs-lookup"><span data-stu-id="be1dc-124">In Skype for Business Server, you can use location policy to set different disclaimers for different locales or different sets of users.</span></span>
  
 <span data-ttu-id="be1dc-125">**紧急拨号 (E9-1-1 拨号号码)**</span><span class="sxs-lookup"><span data-stu-id="be1dc-125">**Emergency Dial String (E9-1-1 dial number)**</span></span>
  
<span data-ttu-id="be1dc-126">此拨号 (前导"+"，但包括用户的拨号计划) 表示呼叫是紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="be1dc-126">This dial string (less the leading "+", but including any normalization done by the user's Dial Plan) signifies that a call is an emergency call.</span></span> <span data-ttu-id="be1dc-127">紧急 **拨号串** 使客户端在呼叫中包括位置和回拨信息。</span><span class="sxs-lookup"><span data-stu-id="be1dc-127">The **Emergency Dial String** causes the client to include location and callback information with the call.</span></span>
  
> [!NOTE]
> <span data-ttu-id="be1dc-128">如果组织不使用外部线路访问前缀，则无需创建相应的拨号计划规范化规则，在将呼叫发送到运行 Skype for Business Server 的服务器上出站路由之前，向 911 字符串添加"+";由于位置策略，Skype for Business 客户端将自动预置"+"。</span><span class="sxs-lookup"><span data-stu-id="be1dc-128">If your organization does not use an external line access prefix, you do not need to create a corresponding Dial Plan normalization rule that adds a "+" to the 911 string prior to sending the call to Outbound Routing on a server running Skype for Business Server; the "+" will be automatically prepended by the Skype for Business client as a result of the location policy.</span></span> <span data-ttu-id="be1dc-129">但是，如果站点使用外部访问前缀，则需要将规范化规则添加到适用的拨号计划策略，该策略会去除外部访问前缀并添加"+"。</span><span class="sxs-lookup"><span data-stu-id="be1dc-129">However, if your site uses an external access prefix, you need to add a normalization rule to the applicable Dial Plan policy that strips the external access prefix and adds the "+".</span></span> <span data-ttu-id="be1dc-130">例如，如果您的位置使用外部访问前缀 9，而用户拨打 9 911 拨打紧急呼叫，则客户端将使用其拨号计划策略将拨打号码规范化为 +911，然后由呼叫者的位置配置文件中的路由评估拨打的号码。</span><span class="sxs-lookup"><span data-stu-id="be1dc-130">For example, if your location uses an external access prefix of 9 and a user dials 9 911 to place an emergency call, the client will use its Dial Plan policy to normalize this to +911 before the dialed number is evaluated by the routes in the caller's location profile.</span></span> 
  
 <span data-ttu-id="be1dc-131">**E9-1-1 拨号掩码 (E9-1-1 拨号掩码)**</span><span class="sxs-lookup"><span data-stu-id="be1dc-131">**Emergency Dial String Masks (E9-1-1 dial mask)**</span></span>
  
<span data-ttu-id="be1dc-132">转换为指定的紧急拨号字符串的拨号字符串的分号 **分隔列表**。</span><span class="sxs-lookup"><span data-stu-id="be1dc-132">A semicolon-separated list of dial strings that is translated into the specified **Emergency Dial String**.</span></span> <span data-ttu-id="be1dc-133">例如，你可能想要添加 112，这是欧洲大多数国家/地区紧急服务号码。</span><span class="sxs-lookup"><span data-stu-id="be1dc-133">For example, you may want to add 112, which is the emergency service number for most of Europe.</span></span> <span data-ttu-id="be1dc-134">从欧洲访问 Skype for Business 的用户可能不知道 911 是美国紧急号码，但他们可以拨打 112 并获取相同的结果。</span><span class="sxs-lookup"><span data-stu-id="be1dc-134">A visiting Skype for Business user from Europe may not know that 911 is the U.S. emergency number, but they can dial 112 and get the same result.</span></span> <span data-ttu-id="be1dc-135">与紧急拨号字符串一样，在每个号码之前不要包含"+"，如果使用外部线路访问代码，请确保用户的拨号计划策略中具有规范化规则，以去除访问代码数字。</span><span class="sxs-lookup"><span data-stu-id="be1dc-135">As with the Emergency Dial String, do not include a "+" before each number, and if you use external line access codes, be sure there are normalization rules in the user's Dial Plan policy to strip off the access code digit.</span></span>
  
 <span data-ttu-id="be1dc-136">**PSTN 用法**</span><span class="sxs-lookup"><span data-stu-id="be1dc-136">**PSTN usage**</span></span>
  
<span data-ttu-id="be1dc-137">PSTN 用法的名称，其中包含确定将转到哪个 SIP 中继、PSTN 网关或 ELIN 网关紧急呼叫的路由路径。</span><span class="sxs-lookup"><span data-stu-id="be1dc-137">The name of the PSTN Usage that contains the routing paths that determine which SIP trunk, PSTN gateway, or ELIN gateway emergency calls will go to.</span></span>
  
> [!NOTE]
> <span data-ttu-id="be1dc-138">只能将一个用法分配给位置策略。</span><span class="sxs-lookup"><span data-stu-id="be1dc-138">Only one usage can be assigned to a location policy.</span></span> <span data-ttu-id="be1dc-139">此 PSTN 用法会覆盖分配给用户的语音策略的 PSTN 用法，但仅适用于拨打紧急拨号串或紧急拨号串掩码之一的呼叫。</span><span class="sxs-lookup"><span data-stu-id="be1dc-139">This PSTN Usage overrides the PSTN Usages assigned to the user's voice policy, but applies only to calls placed to the Emergency Dial String or to one of the Emergency Dial String Masks.</span></span> 
  
 <span data-ttu-id="be1dc-140">**通知 URI**</span><span class="sxs-lookup"><span data-stu-id="be1dc-140">**Notification URI**</span></span>
  
<span data-ttu-id="be1dc-141">指定在发出紧急呼叫时接收即时消息 (IM) 的一个或多个 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="be1dc-141">Specifies one or more SIP URIs of the security personnel who receive an instant messaging (IM) notification when an emergency call is placed.</span></span> <span data-ttu-id="be1dc-142">支持通讯组。</span><span class="sxs-lookup"><span data-stu-id="be1dc-142">Distribution groups are supported.</span></span>
  
 <span data-ttu-id="be1dc-143">**会议 URI**</span><span class="sxs-lookup"><span data-stu-id="be1dc-143">**Conference URI**</span></span>
  
<span data-ttu-id="be1dc-144">指定 DID (DID) 号码 (，通常是在拨打紧急呼叫时) 应参加会议的安全服务台号码。</span><span class="sxs-lookup"><span data-stu-id="be1dc-144">Specifies a direct inward dialing (DID) number (typically, a security desk number) that should be conferenced in when an emergency call is placed.</span></span> 
  
 <span data-ttu-id="be1dc-145">**会议模式**</span><span class="sxs-lookup"><span data-stu-id="be1dc-145">**Conference Mode**</span></span>
  
<span data-ttu-id="be1dc-146">指定是否使用单向或双向通信将会议会议加入紧急呼叫的会议 URI。</span><span class="sxs-lookup"><span data-stu-id="be1dc-146">Specifies if the conference URI will be conferenced into the emergency call by using one-way or two-way communication.</span></span> 
  
 <span data-ttu-id="be1dc-147">**位置刷新间隔**</span><span class="sxs-lookup"><span data-stu-id="be1dc-147">**Location Refresh Interval**</span></span>
  
<span data-ttu-id="be1dc-148">指定从位置信息 (位置) 客户端请求之间使用的时间量（以小时表示）。</span><span class="sxs-lookup"><span data-stu-id="be1dc-148">Specifies the amount of time (in hours) between client requests for a location update from the Location Information service.</span></span> <span data-ttu-id="be1dc-149">该值可以设置为 1 到 12 之间的任意值。</span><span class="sxs-lookup"><span data-stu-id="be1dc-149">The value can be set to any value between 1 and 12.</span></span> <span data-ttu-id="be1dc-150">默认值为 4。</span><span class="sxs-lookup"><span data-stu-id="be1dc-150">The default value is 4.</span></span>
  

