---
title: 规划业务 Server Skype 的位置策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: da3cca7f-f6e5-4b6f-90a1-2008e3dd1ebd
description: 阅读本主题可了解如何规划业务 Server 企业语音的增强型紧急服务 (E9-1-1) 部署 Skype 中的位置策略。
ms.openlocfilehash: 7bb92559f79be7cb2f8c62f89620f4b93f76cb8f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924204"
---
# <a name="plan-location-policies-for-skype-for-business-server"></a><span data-ttu-id="43c40-103">规划业务 Server Skype 的位置策略</span><span class="sxs-lookup"><span data-stu-id="43c40-103">Plan location policies for Skype for Business Server</span></span>
 
<span data-ttu-id="43c40-104">阅读本主题可了解如何规划业务 Server 企业语音的增强型紧急服务 (E9-1-1) 部署 Skype 中的位置策略。</span><span class="sxs-lookup"><span data-stu-id="43c40-104">Read this topic to learn how to plan location policies for an enhanced emergency services (E9-1-1) deployment in Skype for Business Server Enterprise Voice.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="43c40-105">Skype 业务服务器现在支持的客户端的多个紧急号码的配置。</span><span class="sxs-lookup"><span data-stu-id="43c40-105">Skype for Business Server now supports the configuration of multiple emergency numbers for a client.</span></span> <span data-ttu-id="43c40-106">如果您想要配置多个紧急号码，则必须按照[Skype 业务服务器中的多个紧急号码规划](multiple-emergency-numbers.md)和[配置 Skype for Business 中的多个紧急号码](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md)中的信息。</span><span class="sxs-lookup"><span data-stu-id="43c40-106">If you want to configure multiple emergency numbers, you must follow the information in [Plan for multiple emergency numbers in Skype for Business Server](multiple-emergency-numbers.md) and [Configure multiple emergency numbers in Skype for Business](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md).</span></span> 
  
<span data-ttu-id="43c40-107">使用适用于业务 Control Panel Skype 或使用[New-cslocationpolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) cmdlet，您可以创建位置策略。</span><span class="sxs-lookup"><span data-stu-id="43c40-107">You create location policies by using the Skype for Business Control Panel or by using the [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="43c40-108">有关详细信息，请参阅[Skype 业务服务器中的创建位置策略](../../deploy/deploy-enterprise-voice/create-location-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="43c40-108">For more information, see [Create location policies in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-location-policies.md).</span></span>
  
<span data-ttu-id="43c40-109">每个位置策略包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="43c40-109">Each location policy contains the following information:</span></span>
  
 <span data-ttu-id="43c40-110">**启用增强型 9-1-1**</span><span class="sxs-lookup"><span data-stu-id="43c40-110">**Enable Enhanced 9-1-1**</span></span>
  
<span data-ttu-id="43c40-111">启用该值时，可为客户端启用增强型紧急服务 (E9-1-1)。</span><span class="sxs-lookup"><span data-stu-id="43c40-111">When this value is enabled, the client is enabled for enhanced emergency services (E9-1-1).</span></span> <span data-ttu-id="43c40-112">时客户端注册，它会尝试获取从位置信息服务位置，并将包括紧急呼叫的一部分的位置信息。</span><span class="sxs-lookup"><span data-stu-id="43c40-112">When a client registers, it attempts to acquire a location from the Location Information service and will include the location information as part of an emergency call.</span></span>
  
 <span data-ttu-id="43c40-113">**位置**</span><span class="sxs-lookup"><span data-stu-id="43c40-113">**Location**</span></span>
  
<span data-ttu-id="43c40-114">仅当**启用增强型 9-1-1** 为启用状态时才使用此设置。</span><span class="sxs-lookup"><span data-stu-id="43c40-114">This setting is used only when **Enable Enhanced 9-1-1** is enabled.</span></span>
  
<span data-ttu-id="43c40-115">你可以将**位置**设置配置为按如下所示定义客户端行为：</span><span class="sxs-lookup"><span data-stu-id="43c40-115">You can configure the **Location** setting to define the client behavior as follows:</span></span>
  
- <span data-ttu-id="43c40-116">将该值设为**否**表示不会提示用户输入位置。</span><span class="sxs-lookup"><span data-stu-id="43c40-116">Setting the value to **No** means that the user will not be prompted for a location.</span></span>
    
- <span data-ttu-id="43c40-117">设为**是**表示将提示用户输入位置，但可以消除提示。</span><span class="sxs-lookup"><span data-stu-id="43c40-117">Setting the value to **Yes** means that the user will be prompted for a location, but can dismiss the prompt.</span></span>
    
- <span data-ttu-id="43c40-p104">设为**免责声明**表示将会提示用户输入位置，并且当用户尝试消除提示时将显示免责声明。在所有情况下，用户都可以继续使用该客户端。</span><span class="sxs-lookup"><span data-stu-id="43c40-p104">Setting the value to **Disclaimer** means that the user will be prompted for a location and also will be shown a disclaimer if they try to dismiss the prompt. In all cases, the user can continue to use the client.</span></span>
    
> [!NOTE]
> <span data-ttu-id="43c40-p105">如果在启用 E9-1-1 之前用户手动输入位置，则不会显示免责声明文本。已查看免责声明的用户将不能查看免责声明文本的更新。</span><span class="sxs-lookup"><span data-stu-id="43c40-p105">The disclaimer text will not appear if a user manually entered a location before being enabled for E9-1-1. Updates to the disclaimer text will not be viewed by users that have already viewed the disclaimer.</span></span> 
  
 <span data-ttu-id="43c40-122">**增强型紧急服务免责声明**</span><span class="sxs-lookup"><span data-stu-id="43c40-122">**Enhanced Emergency Service Disclaimer**</span></span>
  
<span data-ttu-id="43c40-123">该设置指定当用户消除输入位置提示时显示的免责声明。</span><span class="sxs-lookup"><span data-stu-id="43c40-123">This setting specifies the disclaimer that users see if they dismiss the prompt for a location.</span></span> <span data-ttu-id="43c40-124">在业务服务器 Skype，可以使用位置策略设置为不同区域或不同的用户组的不同免责声明。</span><span class="sxs-lookup"><span data-stu-id="43c40-124">In Skype for Business Server, you can use location policy to set different disclaimers for different locales or different sets of users.</span></span>
  
 <span data-ttu-id="43c40-125">**紧急拨号串（E9-1-1 拨号号码）**</span><span class="sxs-lookup"><span data-stu-id="43c40-125">**Emergency Dial String (E9-1-1 dial number)**</span></span>
  
<span data-ttu-id="43c40-126">此拨号串 (小于前导"+"，但包括由用户的拨号计划完成任何规范化) 表示呼叫紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="43c40-126">This dial string (less the leading "+", but including any normalization done by the user's Dial Plan) signifies that a call is an emergency call.</span></span> <span data-ttu-id="43c40-127">**紧急拨号串**使客户端包括有关呼叫的位置和回拨信息。</span><span class="sxs-lookup"><span data-stu-id="43c40-127">The **Emergency Dial String** causes the client to include location and callback information with the call.</span></span>
  
> [!NOTE]
> <span data-ttu-id="43c40-128">如果您的组织不使用了外部访问前缀，不需要创建相应拨号计划的规范化规则"+"911 字符串发送出站路由到业务服务器; 运行 Skype 的服务器上的呼叫之前添加"+"将自动前加业务由于位置策略的客户端 Skype。</span><span class="sxs-lookup"><span data-stu-id="43c40-128">If your organization does not use an external line access prefix, you do not need to create a corresponding Dial Plan normalization rule that adds a "+" to the 911 string prior to sending the call to Outbound Routing on a server running Skype for Business Server; the "+" will be automatically prepended by the Skype for Business client as a result of the location policy.</span></span> <span data-ttu-id="43c40-129">但是，如果您的网站使用了外部访问前缀，您需要添加规范化规则的适用拨号计划策略中去除的外部访问前缀，并将添加到"+"。</span><span class="sxs-lookup"><span data-stu-id="43c40-129">However, if your site uses an external access prefix, you need to add a normalization rule to the applicable Dial Plan policy that strips the external access prefix and adds the "+".</span></span> <span data-ttu-id="43c40-130">例如，如果您所在的位置使用 9 的外部访问前缀，并将用户拨打 9 911 放置紧急呼叫，客户端将使用其拨号计划策略规范化此到 +911 之前已拨的号码计算的呼叫者的位置配置文件中的路由。</span><span class="sxs-lookup"><span data-stu-id="43c40-130">For example, if your location uses an external access prefix of 9 and a user dials 9 911 to place an emergency call, the client will use its Dial Plan policy to normalize this to +911 before the dialed number is evaluated by the routes in the caller's location profile.</span></span> 
  
 <span data-ttu-id="43c40-131">**紧急拨号串掩码（E9-1-1 拨号掩码）**</span><span class="sxs-lookup"><span data-stu-id="43c40-131">**Emergency Dial String Masks (E9-1-1 dial mask)**</span></span>
  
<span data-ttu-id="43c40-132">一个分号分隔的拨号字符串列表，将转换为指定的**紧急拨号字符串**。</span><span class="sxs-lookup"><span data-stu-id="43c40-132">A semicolon-separated list of dial strings that is translated into the specified **Emergency Dial String**.</span></span> <span data-ttu-id="43c40-133">例如，你可能想要添加 112（欧洲大部分地区的紧急服务号码）。</span><span class="sxs-lookup"><span data-stu-id="43c40-133">For example, you may want to add 112, which is the emergency service number for most of Europe.</span></span> <span data-ttu-id="43c40-134">欧洲业务用户的访问 Skype 可能不知道 911 是美国紧急号码，但他们可以拨打 112 并获得相同的结果。</span><span class="sxs-lookup"><span data-stu-id="43c40-134">A visiting Skype for Business user from Europe may not know that 911 is the U.S. emergency number, but they can dial 112 and get the same result.</span></span> <span data-ttu-id="43c40-135">根据与紧急拨号串，不包括"+"之前每个号码，并使用外部行访问代码，请确保中用户的拨号计划策略关闭访问代码数字去除规范化规则。</span><span class="sxs-lookup"><span data-stu-id="43c40-135">As with the Emergency Dial String, do not include a "+" before each number, and if you use external line access codes, be sure there are normalization rules in the user's Dial Plan policy to strip off the access code digit.</span></span>
  
 <span data-ttu-id="43c40-136">**PSTN 用法**</span><span class="sxs-lookup"><span data-stu-id="43c40-136">**PSTN usage**</span></span>
  
<span data-ttu-id="43c40-137">包含确定紧急呼叫将转至哪一 SIP 中继、PSTN 网关或 ELIN 网关的路由路径的 PSTN 用法名称。</span><span class="sxs-lookup"><span data-stu-id="43c40-137">The name of the PSTN Usage that contains the routing paths that determine which SIP trunk, PSTN gateway, or ELIN gateway emergency calls will go to.</span></span>
  
> [!NOTE]
> <span data-ttu-id="43c40-138">一个用法只能分配给一个位置策略。</span><span class="sxs-lookup"><span data-stu-id="43c40-138">Only one usage can be assigned to a location policy.</span></span> <span data-ttu-id="43c40-139">此 PSTN 用法将覆盖 PSTN 用法分配给用户的语音策略，但是仅适用于呼叫紧急拨号串或一个紧急拨号串掩码。</span><span class="sxs-lookup"><span data-stu-id="43c40-139">This PSTN Usage overrides the PSTN Usages assigned to the user's voice policy, but applies only to calls placed to the Emergency Dial String or to one of the Emergency Dial String Masks.</span></span> 
  
 <span data-ttu-id="43c40-140">**通知 URI**</span><span class="sxs-lookup"><span data-stu-id="43c40-140">**Notification URI**</span></span>
  
<span data-ttu-id="43c40-p111">指定要在发出紧急呼叫时接收即时消息 (IM) 通知的安全人员的一个或多个 SIP URI。支持通讯组。</span><span class="sxs-lookup"><span data-stu-id="43c40-p111">Specifies one or more SIP URIs of the security personnel who receive an instant messaging (IM) notification when an emergency call is placed. Distribution groups are supported.</span></span>
  
 <span data-ttu-id="43c40-143">**会议 URI**</span><span class="sxs-lookup"><span data-stu-id="43c40-143">**Conference URI**</span></span>
  
<span data-ttu-id="43c40-144">指定在发出紧急呼叫时应加入会议的外线直拨分机 (DID) 号码（通常是安全服务台号码）。</span><span class="sxs-lookup"><span data-stu-id="43c40-144">Specifies a direct inward dialing (DID) number (typically, a security desk number) that should be conferenced in when an emergency call is placed.</span></span> 
  
 <span data-ttu-id="43c40-145">**会议模式**</span><span class="sxs-lookup"><span data-stu-id="43c40-145">**Conference Mode**</span></span>
  
<span data-ttu-id="43c40-146">指定会议 URI 将使用单向还是双向通信加入紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="43c40-146">Specifies if the conference URI will be conferenced into the emergency call by using one-way or two-way communication.</span></span> 
  
 <span data-ttu-id="43c40-147">**位置刷新间隔**</span><span class="sxs-lookup"><span data-stu-id="43c40-147">**Location Refresh Interval**</span></span>
  
<span data-ttu-id="43c40-148">指定从位置信息服务的位置更新的客户端请求之间的时间 （以小时为单位）。</span><span class="sxs-lookup"><span data-stu-id="43c40-148">Specifies the amount of time (in hours) between client requests for a location update from the Location Information service.</span></span> <span data-ttu-id="43c40-149">该值可以设置为 1 和 12 之间的任意值。</span><span class="sxs-lookup"><span data-stu-id="43c40-149">The value can be set to any value between 1 and 12.</span></span> <span data-ttu-id="43c40-150">默认值为 4。</span><span class="sxs-lookup"><span data-stu-id="43c40-150">The default value is 4.</span></span>
  

