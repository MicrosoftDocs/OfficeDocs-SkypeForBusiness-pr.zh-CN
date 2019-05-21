---
title: 为 Skype for Business Server 规划位置策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: da3cca7f-f6e5-4b6f-90a1-2008e3dd1ebd
description: 阅读本主题, 了解如何在 Skype for Business Server Enterprise Voice 中为增强的紧急服务 (E9-1) 部署计划位置策略。
ms.openlocfilehash: 8f21a5a0f54fbeaca4c46ed51bf4dafe4c2a3dcb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276752"
---
# <a name="plan-location-policies-for-skype-for-business-server"></a><span data-ttu-id="c4bb4-103">为 Skype for Business Server 规划位置策略</span><span class="sxs-lookup"><span data-stu-id="c4bb4-103">Plan location policies for Skype for Business Server</span></span>
 
<span data-ttu-id="c4bb4-104">阅读本主题, 了解如何在 Skype for Business Server Enterprise Voice 中为增强的紧急服务 (E9-1) 部署计划位置策略。</span><span class="sxs-lookup"><span data-stu-id="c4bb4-104">Read this topic to learn how to plan location policies for an enhanced emergency services (E9-1-1) deployment in Skype for Business Server Enterprise Voice.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="c4bb4-105">Skype for business 服务器现支持客户端的多个紧急号码的配置。</span><span class="sxs-lookup"><span data-stu-id="c4bb4-105">Skype for Business Server now supports the configuration of multiple emergency numbers for a client.</span></span> <span data-ttu-id="c4bb4-106">如果想要配置多个紧急号码, 您必须按照计划中的信息, 在[skype For Business 服务器中输入多个紧急](multiple-emergency-numbers.md)号码, 并[在 skype For business 中配置多个紧急号码](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md)。</span><span class="sxs-lookup"><span data-stu-id="c4bb4-106">If you want to configure multiple emergency numbers, you must follow the information in [Plan for multiple emergency numbers in Skype for Business Server](multiple-emergency-numbers.md) and [Configure multiple emergency numbers in Skype for Business](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md).</span></span> 
  
<span data-ttu-id="c4bb4-107">通过使用 Skype for Business 控制面板或使用[CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) cmdlet 创建位置策略。</span><span class="sxs-lookup"><span data-stu-id="c4bb4-107">You create location policies by using the Skype for Business Control Panel or by using the [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="c4bb4-108">有关详细信息, 请参阅[在 Skype For Business 服务器中创建位置策略](../../deploy/deploy-enterprise-voice/create-location-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="c4bb4-108">For more information, see [Create location policies in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-location-policies.md).</span></span>
  
<span data-ttu-id="c4bb4-109">每个位置策略包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="c4bb4-109">Each location policy contains the following information:</span></span>
  
 <span data-ttu-id="c4bb4-110">**启用增强型 9-1-1**</span><span class="sxs-lookup"><span data-stu-id="c4bb4-110">**Enable Enhanced 9-1-1**</span></span>
  
<span data-ttu-id="c4bb4-111">启用该值时，可为客户端启用增强型紧急服务 (E9-1-1)。</span><span class="sxs-lookup"><span data-stu-id="c4bb4-111">When this value is enabled, the client is enabled for enhanced emergency services (E9-1-1).</span></span> <span data-ttu-id="c4bb4-112">客户端注册时, 它会尝试从位置信息服务获取位置, 并将位置信息包含在紧急呼叫的一部分中。</span><span class="sxs-lookup"><span data-stu-id="c4bb4-112">When a client registers, it attempts to acquire a location from the Location Information service and will include the location information as part of an emergency call.</span></span>
  
 <span data-ttu-id="c4bb4-113">**位置**</span><span class="sxs-lookup"><span data-stu-id="c4bb4-113">**Location**</span></span>
  
<span data-ttu-id="c4bb4-114">仅当**启用增强型 9-1-1** 为启用状态时才使用此设置。</span><span class="sxs-lookup"><span data-stu-id="c4bb4-114">This setting is used only when **Enable Enhanced 9-1-1** is enabled.</span></span>
  
<span data-ttu-id="c4bb4-115">你可以将**位置**设置配置为按如下所示定义客户端行为：</span><span class="sxs-lookup"><span data-stu-id="c4bb4-115">You can configure the **Location** setting to define the client behavior as follows:</span></span>
  
- <span data-ttu-id="c4bb4-116">将该值设为**否**表示不会提示用户输入位置。</span><span class="sxs-lookup"><span data-stu-id="c4bb4-116">Setting the value to **No** means that the user will not be prompted for a location.</span></span>
    
- <span data-ttu-id="c4bb4-117">设为**是**表示将提示用户输入位置，但可以消除提示。</span><span class="sxs-lookup"><span data-stu-id="c4bb4-117">Setting the value to **Yes** means that the user will be prompted for a location, but can dismiss the prompt.</span></span>
    
- <span data-ttu-id="c4bb4-p104">设为**免责声明**表示将会提示用户输入位置，并且当用户尝试消除提示时将显示免责声明。在所有情况下，用户都可以继续使用该客户端。</span><span class="sxs-lookup"><span data-stu-id="c4bb4-p104">Setting the value to **Disclaimer** means that the user will be prompted for a location and also will be shown a disclaimer if they try to dismiss the prompt. In all cases, the user can continue to use the client.</span></span>
    
> [!NOTE]
> <span data-ttu-id="c4bb4-p105">如果在启用 E9-1-1 之前用户手动输入位置，则不会显示免责声明文本。已查看免责声明的用户将不能查看免责声明文本的更新。</span><span class="sxs-lookup"><span data-stu-id="c4bb4-p105">The disclaimer text will not appear if a user manually entered a location before being enabled for E9-1-1. Updates to the disclaimer text will not be viewed by users that have already viewed the disclaimer.</span></span> 
  
 <span data-ttu-id="c4bb4-122">**增强型紧急服务免责声明**</span><span class="sxs-lookup"><span data-stu-id="c4bb4-122">**Enhanced Emergency Service Disclaimer**</span></span>
  
<span data-ttu-id="c4bb4-123">该设置指定当用户消除输入位置提示时显示的免责声明。</span><span class="sxs-lookup"><span data-stu-id="c4bb4-123">This setting specifies the disclaimer that users see if they dismiss the prompt for a location.</span></span> <span data-ttu-id="c4bb4-124">在 Skype for Business Server 中, 你可以使用位置策略为不同的区域设置或不同的用户集设置不同的免责声明。</span><span class="sxs-lookup"><span data-stu-id="c4bb4-124">In Skype for Business Server, you can use location policy to set different disclaimers for different locales or different sets of users.</span></span>
  
 <span data-ttu-id="c4bb4-125">**紧急拨号串（E9-1-1 拨号号码）**</span><span class="sxs-lookup"><span data-stu-id="c4bb4-125">**Emergency Dial String (E9-1-1 dial number)**</span></span>
  
<span data-ttu-id="c4bb4-126">此拨号字符串 (较少前导 "+", 但包括由用户的拨号计划完成的任何规范化) 表示呼叫是紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="c4bb4-126">This dial string (less the leading "+", but including any normalization done by the user's Dial Plan) signifies that a call is an emergency call.</span></span> <span data-ttu-id="c4bb4-127">**紧急拨号串**使客户端包括有关呼叫的位置和回拨信息。</span><span class="sxs-lookup"><span data-stu-id="c4bb4-127">The **Emergency Dial String** causes the client to include location and callback information with the call.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c4bb4-128">如果您的组织不使用外部线路访问前缀, 则无需创建相应的拨号计划规范化规则, 以便在运行 Skype for business 服务器的服务器上将呼叫发送到出站路由之前将 "+" 添加到911字符串;作为位置策略的结果, Skype for Business 客户端将自动预置 "+"。</span><span class="sxs-lookup"><span data-stu-id="c4bb4-128">If your organization does not use an external line access prefix, you do not need to create a corresponding Dial Plan normalization rule that adds a "+" to the 911 string prior to sending the call to Outbound Routing on a server running Skype for Business Server; the "+" will be automatically prepended by the Skype for Business client as a result of the location policy.</span></span> <span data-ttu-id="c4bb4-129">但是, 如果您的网站使用外部访问前缀, 则需要将规范化规则添加到可访问外部访问前缀的适用拨号计划策略, 并添加 "+"。</span><span class="sxs-lookup"><span data-stu-id="c4bb4-129">However, if your site uses an external access prefix, you need to add a normalization rule to the applicable Dial Plan policy that strips the external access prefix and adds the "+".</span></span> <span data-ttu-id="c4bb4-130">例如, 如果您的位置使用外部访问前缀 9, 并且用户将 9 911 拨打电话到拨打电话, 则在呼叫者的位置档案中, 客户端将使用其拨号计划策略将此号码与 + 911 进行规范化。</span><span class="sxs-lookup"><span data-stu-id="c4bb4-130">For example, if your location uses an external access prefix of 9 and a user dials 9 911 to place an emergency call, the client will use its Dial Plan policy to normalize this to +911 before the dialed number is evaluated by the routes in the caller's location profile.</span></span> 
  
 <span data-ttu-id="c4bb4-131">**紧急拨号串掩码（E9-1-1 拨号掩码）**</span><span class="sxs-lookup"><span data-stu-id="c4bb4-131">**Emergency Dial String Masks (E9-1-1 dial mask)**</span></span>
  
<span data-ttu-id="c4bb4-132">一个分号分隔的拨号字符串列表，将转换为指定的**紧急拨号字符串**。</span><span class="sxs-lookup"><span data-stu-id="c4bb4-132">A semicolon-separated list of dial strings that is translated into the specified **Emergency Dial String**.</span></span> <span data-ttu-id="c4bb4-133">例如，你可能想要添加 112（欧洲大部分地区的紧急服务号码）。</span><span class="sxs-lookup"><span data-stu-id="c4bb4-133">For example, you may want to add 112, which is the emergency service number for most of Europe.</span></span> <span data-ttu-id="c4bb4-134">从欧洲访问 Skype for business 用户可能不知道911是美国的紧急电话号码, 但他们可以拨打112并获得相同的结果。</span><span class="sxs-lookup"><span data-stu-id="c4bb4-134">A visiting Skype for Business user from Europe may not know that 911 is the U.S. emergency number, but they can dial 112 and get the same result.</span></span> <span data-ttu-id="c4bb4-135">与 "紧急拨号字符串" 一样, 在每个号码前不要包含 "+", 如果您使用外部线路访问代码, 请确保用户的拨号计划策略中有规范化规则来去掉访问代码位。</span><span class="sxs-lookup"><span data-stu-id="c4bb4-135">As with the Emergency Dial String, do not include a "+" before each number, and if you use external line access codes, be sure there are normalization rules in the user's Dial Plan policy to strip off the access code digit.</span></span>
  
 <span data-ttu-id="c4bb4-136">**PSTN 用法**</span><span class="sxs-lookup"><span data-stu-id="c4bb4-136">**PSTN usage**</span></span>
  
<span data-ttu-id="c4bb4-137">包含确定紧急呼叫将转至哪一 SIP 中继、PSTN 网关或 ELIN 网关的路由路径的 PSTN 用法名称。</span><span class="sxs-lookup"><span data-stu-id="c4bb4-137">The name of the PSTN Usage that contains the routing paths that determine which SIP trunk, PSTN gateway, or ELIN gateway emergency calls will go to.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c4bb4-138">一个用法只能分配给一个位置策略。</span><span class="sxs-lookup"><span data-stu-id="c4bb4-138">Only one usage can be assigned to a location policy.</span></span> <span data-ttu-id="c4bb4-139">此 PSTN 使用覆盖分配给用户语音策略的 PSTN 使用, 但仅适用于拨入紧急拨号字符串或其中一个紧急拨号字符串掩码的呼叫。</span><span class="sxs-lookup"><span data-stu-id="c4bb4-139">This PSTN Usage overrides the PSTN Usages assigned to the user's voice policy, but applies only to calls placed to the Emergency Dial String or to one of the Emergency Dial String Masks.</span></span> 
  
 <span data-ttu-id="c4bb4-140">**通知 URI**</span><span class="sxs-lookup"><span data-stu-id="c4bb4-140">**Notification URI**</span></span>
  
<span data-ttu-id="c4bb4-p111">指定要在发出紧急呼叫时接收即时消息 (IM) 通知的安全人员的一个或多个 SIP URI。支持通讯组。</span><span class="sxs-lookup"><span data-stu-id="c4bb4-p111">Specifies one or more SIP URIs of the security personnel who receive an instant messaging (IM) notification when an emergency call is placed. Distribution groups are supported.</span></span>
  
 <span data-ttu-id="c4bb4-143">**会议 URI**</span><span class="sxs-lookup"><span data-stu-id="c4bb4-143">**Conference URI**</span></span>
  
<span data-ttu-id="c4bb4-144">指定在发出紧急呼叫时应加入会议的外线直拨分机 (DID) 号码（通常是安全服务台号码）。</span><span class="sxs-lookup"><span data-stu-id="c4bb4-144">Specifies a direct inward dialing (DID) number (typically, a security desk number) that should be conferenced in when an emergency call is placed.</span></span> 
  
 <span data-ttu-id="c4bb4-145">**会议模式**</span><span class="sxs-lookup"><span data-stu-id="c4bb4-145">**Conference Mode**</span></span>
  
<span data-ttu-id="c4bb4-146">指定会议 URI 将使用单向还是双向通信加入紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="c4bb4-146">Specifies if the conference URI will be conferenced into the emergency call by using one-way or two-way communication.</span></span> 
  
 <span data-ttu-id="c4bb4-147">**位置刷新间隔**</span><span class="sxs-lookup"><span data-stu-id="c4bb4-147">**Location Refresh Interval**</span></span>
  
<span data-ttu-id="c4bb4-148">指定从位置信息服务的位置更新的客户端请求之间的时间量 (以小时为单位)。</span><span class="sxs-lookup"><span data-stu-id="c4bb4-148">Specifies the amount of time (in hours) between client requests for a location update from the Location Information service.</span></span> <span data-ttu-id="c4bb4-149">该值可以设置为 1 和 12 之间的任意值。</span><span class="sxs-lookup"><span data-stu-id="c4bb4-149">The value can be set to any value between 1 and 12.</span></span> <span data-ttu-id="c4bb4-150">默认值为 4。</span><span class="sxs-lookup"><span data-stu-id="c4bb4-150">The default value is 4.</span></span>
  

