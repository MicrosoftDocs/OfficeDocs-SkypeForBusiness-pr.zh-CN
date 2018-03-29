---
title: 为 Skype for Business Server 2015 规划位置策略
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/17/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: da3cca7f-f6e5-4b6f-90a1-2008e3dd1ebd
description: 阅读本主题，以了解如何规划业务服务器企业语音增强紧急服务 (E9-1-1) 部署在 Skype 的位置策略。
ms.openlocfilehash: 246a4bcddece986d9488c5e2bccbbece5f1a2cc9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="plan-location-policies-for-skype-for-business-server-2015"></a><span data-ttu-id="47d96-103">为 Skype for Business Server 2015 规划位置策略</span><span class="sxs-lookup"><span data-stu-id="47d96-103">Plan location policies for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="47d96-104">阅读本主题，以了解如何规划业务服务器企业语音增强紧急服务 (E9-1-1) 部署在 Skype 的位置策略。</span><span class="sxs-lookup"><span data-stu-id="47d96-104">Read this topic to learn how to plan location policies for an enhanced emergency services (E9-1-1) deployment in Skype for Business Server Enterprise Voice.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="47d96-105">Skype 业务服务器现在支持的客户端配置的多个紧急号码。</span><span class="sxs-lookup"><span data-stu-id="47d96-105">Skype for Business Server now supports the configuration of multiple emergency numbers for a client.</span></span> <span data-ttu-id="47d96-106">如果您想要配置多个紧急号码，您必须遵循[多个紧急号码业务服务器 2015年的 Skype 中规划](multiple-emergency-numbers.md)和[配置多个紧急号码业务 2015年的 Skype 在](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md)中的信息。</span><span class="sxs-lookup"><span data-stu-id="47d96-106">If you want to configure multiple emergency numbers, you must follow the information in [Plan for multiple emergency numbers in Skype for Business Server 2015](multiple-emergency-numbers.md) and [Configure multiple emergency numbers in Skype for Business 2015](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md).</span></span> 
  
<span data-ttu-id="47d96-107">通过 Skype 业务控制面板或通过使用[New CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) cmdlet，您创建的位置策略。</span><span class="sxs-lookup"><span data-stu-id="47d96-107">You create location policies by using the Skype for Business Control Panel or by using the [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="47d96-108">有关详细信息，请参阅[创建业务服务器 2015年的 Skype 的位置策略](../../deploy/deploy-enterprise-voice/create-location-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="47d96-108">For more information, see [Create location policies in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/create-location-policies.md).</span></span>
  
<span data-ttu-id="47d96-109">每个位置策略包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="47d96-109">Each location policy contains the following information:</span></span>
  
 <span data-ttu-id="47d96-110">**启用增强型 9-1-1**</span><span class="sxs-lookup"><span data-stu-id="47d96-110">**Enable Enhanced 9-1-1**</span></span>
  
<span data-ttu-id="47d96-111">启用该值时，可为客户端启用增强型紧急服务 (E9-1-1)。</span><span class="sxs-lookup"><span data-stu-id="47d96-111">When this value is enabled, the client is enabled for enhanced emergency services (E9-1-1).</span></span> <span data-ttu-id="47d96-112">当客户端注册时，它试图获取位置信息服务中的位置，并将包括位置信息作为紧急调用的一部分。</span><span class="sxs-lookup"><span data-stu-id="47d96-112">When a client registers, it attempts to acquire a location from the Location Information service and will include the location information as part of an emergency call.</span></span>
  
 <span data-ttu-id="47d96-113">**位置**</span><span class="sxs-lookup"><span data-stu-id="47d96-113">**Location**</span></span>
  
<span data-ttu-id="47d96-114">仅当启用**启用增强 9-1-1**时，则使用此设置。</span><span class="sxs-lookup"><span data-stu-id="47d96-114">This setting is used only when **Enable Enhanced 9-1-1** is enabled.</span></span>
  
<span data-ttu-id="47d96-115">你可以将**位置**设置配置为按如下所示定义客户端行为：</span><span class="sxs-lookup"><span data-stu-id="47d96-115">You can configure the **Location** setting to define the client behavior as follows:</span></span>
  
- <span data-ttu-id="47d96-116">将该值设为**否**表示不会提示用户输入位置。</span><span class="sxs-lookup"><span data-stu-id="47d96-116">Setting the value to **No** means that the user will not be prompted for a location.</span></span>
    
- <span data-ttu-id="47d96-117">设为**是**表示将提示用户输入位置，但可以消除提示。</span><span class="sxs-lookup"><span data-stu-id="47d96-117">Setting the value to **Yes** means that the user will be prompted for a location, but can dismiss the prompt.</span></span>
    
- <span data-ttu-id="47d96-p104">设为**免责声明**表示将会提示用户输入位置，并且当用户尝试消除提示时将显示免责声明。在所有情况下，用户都可以继续使用该客户端。</span><span class="sxs-lookup"><span data-stu-id="47d96-p104">Setting the value to **Disclaimer** means that the user will be prompted for a location and also will be shown a disclaimer if they try to dismiss the prompt. In all cases, the user can continue to use the client.</span></span>
    
> [!NOTE]
> <span data-ttu-id="47d96-p105">如果在启用 E9-1-1 之前用户手动输入位置，则不会显示免责声明文本。已查看免责声明的用户将不能查看免责声明文本的更新。</span><span class="sxs-lookup"><span data-stu-id="47d96-p105">The disclaimer text will not appear if a user manually entered a location before being enabled for E9-1-1. Updates to the disclaimer text will not be viewed by users that have already viewed the disclaimer.</span></span> 
  
 <span data-ttu-id="47d96-122">**增强型紧急服务免责声明**</span><span class="sxs-lookup"><span data-stu-id="47d96-122">**Enhanced Emergency Service Disclaimer**</span></span>
  
<span data-ttu-id="47d96-123">该设置指定当用户消除输入位置提示时显示的免责声明。</span><span class="sxs-lookup"><span data-stu-id="47d96-123">This setting specifies the disclaimer that users see if they dismiss the prompt for a location.</span></span> <span data-ttu-id="47d96-124">在 Skype 业务服务器，您可以使用位置策略设置为不同的区域设置或不同的用户组不同免责声明。</span><span class="sxs-lookup"><span data-stu-id="47d96-124">In Skype for Business Server, you can use location policy to set different disclaimers for different locales or different sets of users.</span></span>
  
 <span data-ttu-id="47d96-125">**紧急拨号串（E9-1-1 拨号号码）**</span><span class="sxs-lookup"><span data-stu-id="47d96-125">**Emergency Dial String (E9-1-1 dial number)**</span></span>
  
<span data-ttu-id="47d96-126">此拨号字符串 (更少的前导"+"，但包括由用户的拨号计划完成任何正常化) 表示是一个紧急调用的调用。</span><span class="sxs-lookup"><span data-stu-id="47d96-126">This dial string (less the leading "+", but including any normalization done by the user's Dial Plan) signifies that a call is an emergency call.</span></span> <span data-ttu-id="47d96-127">**紧急拨号串**使客户端包括有关呼叫的位置和回拨信息。</span><span class="sxs-lookup"><span data-stu-id="47d96-127">The **Emergency Dial String** causes the client to include location and callback information with the call.</span></span>
  
> [!NOTE]
> <span data-ttu-id="47d96-128">如果您的组织不使用外部线接入前缀，您不需要创建相应拨号计划规范化规则添加一个"+"到 911 之前发送到出站路由业务服务器; 运行 Skype 的服务器上调用字符串"+"将自动预置通过 Skype 业务客户端的位置策略的结果。</span><span class="sxs-lookup"><span data-stu-id="47d96-128">If your organization does not use an external line access prefix, you do not need to create a corresponding Dial Plan normalization rule that adds a "+" to the 911 string prior to sending the call to Outbound Routing on a server running Skype for Business Server; the "+" will be automatically prepended by the Skype for Business client as a result of the location policy.</span></span> <span data-ttu-id="47d96-129">但是，如果您的站点使用一个外部访问前缀，您需要将规范化规则添加到适用拨号计划策略，以去除外部访问前缀并添加"+"。</span><span class="sxs-lookup"><span data-stu-id="47d96-129">However, if your site uses an external access prefix, you need to add a normalization rule to the applicable Dial Plan policy that strips the external access prefix and adds the "+".</span></span> <span data-ttu-id="47d96-130">例如，如果您所在的位置使用 9 的外部访问前缀和用户拨打 9 911 要发出紧急呼叫，客户端将使用其拨号计划策略标准化这对之前的 +911 通过在调用方的位置配置文件中的路由计算拨叫的号码。</span><span class="sxs-lookup"><span data-stu-id="47d96-130">For example, if your location uses an external access prefix of 9 and a user dials 9 911 to place an emergency call, the client will use its Dial Plan policy to normalize this to +911 before the the dialed number is evaluated by the routes in the caller's location profile.</span></span> 
  
 <span data-ttu-id="47d96-131">**紧急拨号串掩码（E9-1-1 拨号掩码）**</span><span class="sxs-lookup"><span data-stu-id="47d96-131">**Emergency Dial String Masks (E9-1-1 dial mask)**</span></span>
  
<span data-ttu-id="47d96-132">一个分号分隔的拨号字符串列表，将转换为指定的**紧急拨号字符串**。</span><span class="sxs-lookup"><span data-stu-id="47d96-132">A semicolon-separated list of dial strings that is translated into the specified **Emergency Dial String**.</span></span> <span data-ttu-id="47d96-133">例如，你可能想要添加 112（欧洲大部分地区的紧急服务号码）。</span><span class="sxs-lookup"><span data-stu-id="47d96-133">For example, you may want to add 112, which is the emergency service number for most of Europe.</span></span> <span data-ttu-id="47d96-134">来自欧洲的企业用户正在访问 Skype 可能不知道 911 是美国紧急号码，但他们可以拨打 112 和获得相同的结果。</span><span class="sxs-lookup"><span data-stu-id="47d96-134">A visiting Skype for Business user from Europe may not know that 911 is the U.S. emergency number, but they can dial 112 and get the same result.</span></span> <span data-ttu-id="47d96-135">如与紧急拨号字符串，但不包含一个"+"前每个数字，而且如果您使用外部行访问代码，请确保用户的拨号计划策略来访问代码数字中剥离中规范化规则。</span><span class="sxs-lookup"><span data-stu-id="47d96-135">As with the Emergency Dial String, do not include a "+" before each number, and if you use external line access codes, be sure there are normalization rules in the user's Dial Plan policy to strip off the access code digit.</span></span>
  
 <span data-ttu-id="47d96-136">**PSTN 用法**</span><span class="sxs-lookup"><span data-stu-id="47d96-136">**PSTN usage**</span></span>
  
<span data-ttu-id="47d96-137">包含确定紧急呼叫将转至哪一 SIP 中继、PSTN 网关或 ELIN 网关的路由路径的 PSTN 用法名称。</span><span class="sxs-lookup"><span data-stu-id="47d96-137">The name of the PSTN Usage that contains the routing paths that determine which SIP trunk, PSTN gateway, or ELIN gateway emergency calls will go to.</span></span>
  
> [!NOTE]
> <span data-ttu-id="47d96-138">一个用法只能分配给一个位置策略。</span><span class="sxs-lookup"><span data-stu-id="47d96-138">Only one usage can be assigned to a location policy.</span></span> <span data-ttu-id="47d96-139">此 PSTN 用法将覆盖指派给用户的语音策略，PSTN 用法，但仅适用于调用放置紧急拨号字符串或一个紧急拨号字符串面具。</span><span class="sxs-lookup"><span data-stu-id="47d96-139">This PSTN Usage overrides the PSTN Usages assigned to the user's voice policy, but applies only to calls placed to the Emergency Dial String or to one of the Emergency Dial String Masks.</span></span> 
  
 <span data-ttu-id="47d96-140">**通知 URI**</span><span class="sxs-lookup"><span data-stu-id="47d96-140">**Notification URI**</span></span>
  
<span data-ttu-id="47d96-p111">指定要在发出紧急呼叫时接收即时消息 (IM) 通知的安全人员的一个或多个 SIP URI。支持通讯组。</span><span class="sxs-lookup"><span data-stu-id="47d96-p111">Specifies one or more SIP URIs of the security personnel who receive an instant messaging (IM) notification when an emergency call is placed. Distribution groups are supported.</span></span>
  
 <span data-ttu-id="47d96-143">**会议 URI**</span><span class="sxs-lookup"><span data-stu-id="47d96-143">**Conference URI**</span></span>
  
<span data-ttu-id="47d96-144">指定在发出紧急呼叫时应加入会议的外线直拨分机 (DID) 号码（通常是安全服务台号码）。</span><span class="sxs-lookup"><span data-stu-id="47d96-144">Specifies a direct inward dialing (DID) number (typically, a security desk number) that should be conferenced in when an emergency call is placed.</span></span> 
  
 <span data-ttu-id="47d96-145">**会议模式**</span><span class="sxs-lookup"><span data-stu-id="47d96-145">**Conference Mode**</span></span>
  
<span data-ttu-id="47d96-146">指定会议 URI 将使用单向还是双向通信加入紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="47d96-146">Specifies if the conference URI will be conferenced into the emergency call by using one-way or two-way communication.</span></span> 
  
 <span data-ttu-id="47d96-147">**位置刷新间隔**</span><span class="sxs-lookup"><span data-stu-id="47d96-147">**Location Refresh Interval**</span></span>
  
<span data-ttu-id="47d96-148">指定的位置信息服务从一个位置更新的客户端请求之间的时间 （以小时为单位）。</span><span class="sxs-lookup"><span data-stu-id="47d96-148">Specifies the amount of time (in hours) between client requests for a location update from the Location Information service.</span></span> <span data-ttu-id="47d96-149">该值可以设置为 1 和 12 之间的任意值。</span><span class="sxs-lookup"><span data-stu-id="47d96-149">The value can be set to any value between 1 and 12.</span></span> <span data-ttu-id="47d96-150">默认值为 4。</span><span class="sxs-lookup"><span data-stu-id="47d96-150">The default value is 4.</span></span>
  

