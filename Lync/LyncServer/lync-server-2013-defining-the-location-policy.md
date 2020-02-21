---
title: Lync Server 2013：定义位置策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining the location policy
ms:assetid: da3cca7f-f6e5-4b6f-90a1-2008e3dd1ebd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398962(v=OCS.15)
ms:contentKeyID: 48185553
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 64c164f24f0f2c140a140b7343dd526979cc2bff
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208918"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-the-location-policy-for-lync-server-2013"></a><span data-ttu-id="b9e0a-102">定义 Lync Server 2013 的位置策略</span><span class="sxs-lookup"><span data-stu-id="b9e0a-102">Defining the location policy for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b9e0a-103">_**上次修改的主题：** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="b9e0a-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="b9e0a-104">每个位置策略包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="b9e0a-104">Each location policy contains the following information:</span></span>

  - <span data-ttu-id="b9e0a-105">**已启用紧急服务**</span><span class="sxs-lookup"><span data-stu-id="b9e0a-105">**Emergency Services Enabled**</span></span>  
    <span data-ttu-id="b9e0a-106">如果此值为 **"是"**，则为 E9-1-1 启用客户端。</span><span class="sxs-lookup"><span data-stu-id="b9e0a-106">When this value is **Yes**, the client is enabled for E9-1-1.</span></span> <span data-ttu-id="b9e0a-107">当客户端注册时，它会尝试从 Location 信息服务获取位置，并将位置信息作为紧急呼叫的一部分包括在内。</span><span class="sxs-lookup"><span data-stu-id="b9e0a-107">When a client registers, it attempts to acquire a location from the Location Information service and will include the location information as part of an emergency call.</span></span>

<!-- end list -->

  - <span data-ttu-id="b9e0a-108">**必需的位置**</span><span class="sxs-lookup"><span data-stu-id="b9e0a-108">**Location Required**</span></span>  
    <span data-ttu-id="b9e0a-109">此设置仅在 "**启用了激活** 服务" 设置为 **"是"** 时使用。</span><span class="sxs-lookup"><span data-stu-id="b9e0a-109">This setting is used only when **Emergence Services Enabled** is set to **Yes**.</span></span>
    
    <span data-ttu-id="b9e0a-110">您可以配置 "**需要的位置**" 设置以定义客户端行为。</span><span class="sxs-lookup"><span data-stu-id="b9e0a-110">You can configure the **Location Required** setting to define the client behavior.</span></span> <span data-ttu-id="b9e0a-111">如果将值设置为 "**否**"，则意味着将不会提示用户输入位置。</span><span class="sxs-lookup"><span data-stu-id="b9e0a-111">Setting the value to **No** means that the user will not be prompted for a location.</span></span> <span data-ttu-id="b9e0a-112">将值设置为 **"是"** 表示将提示用户输入位置，但可以消除提示。</span><span class="sxs-lookup"><span data-stu-id="b9e0a-112">Setting the value to **Yes** means that the user will be prompted for a location, but can dismiss the prompt.</span></span> <span data-ttu-id="b9e0a-113">将此值设置为**免责声明**意味着将提示用户输入位置，如果用户尝试消除提示，还会显示免责声明。</span><span class="sxs-lookup"><span data-stu-id="b9e0a-113">Setting the value to **Disclaimer** means that the user will be prompted for a location and also will be shown a disclaimer if they try to dismiss the prompt.</span></span> <span data-ttu-id="b9e0a-114">在所有情况下，用户都可以继续使用客户端。</span><span class="sxs-lookup"><span data-stu-id="b9e0a-114">In all cases, the user can continue to use the client.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b9e0a-115">如果用户在启用 E9-1-1 前手动输入了一个位置，则不会显示免责声明文本。</span><span class="sxs-lookup"><span data-stu-id="b9e0a-115">The disclaimer text will not appear if a user manually entered a location before being enabled for E9-1-1.</span></span> <span data-ttu-id="b9e0a-116">已查看免责声明的用户将不会查看对免责声明文本的更新。</span><span class="sxs-lookup"><span data-stu-id="b9e0a-116">Updates to the disclaimer text will not be viewed by users that have already viewed the disclaimer.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="b9e0a-117">**增强的紧急服务免责声明**</span><span class="sxs-lookup"><span data-stu-id="b9e0a-117">**Enhanced Emergency Service Disclaimer**</span></span>  
    <span data-ttu-id="b9e0a-118">此设置指定用户在消除对某个位置的提示时所看到的免责声明。</span><span class="sxs-lookup"><span data-stu-id="b9e0a-118">This setting specifies the disclaimer that users see if they dismiss the prompt for a location.</span></span> <span data-ttu-id="b9e0a-119">在 Lync Server 2013 中，可以使用位置策略为不同的区域设置或不同的用户集设置不同的免责声明。</span><span class="sxs-lookup"><span data-stu-id="b9e0a-119">In Lync Server 2013, you can use location policy to set different disclaimers for different locales or different sets of users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b9e0a-120">此位置策略设置与 Lync Server 2010 不同，您使用<STRONG>CsEnhancedEmergencyServiceDisclaimer</STRONG> cmdlet 为整个组织设置全局免责声明。</span><span class="sxs-lookup"><span data-stu-id="b9e0a-120">This location policy setting differs from Lync Server 2010, where you used the <STRONG>Set-CsEnhancedEmergencyServiceDisclaimer</STRONG> cmdlet to set a global disclaimer for the entire organization.</span></span> <span data-ttu-id="b9e0a-121">如果已存在全局免责声明，则需要在位置策略中指定该免责声明。</span><span class="sxs-lookup"><span data-stu-id="b9e0a-121">If a global disclaimer already exists, you need to specify that disclaimer in location policy.</span></span> <span data-ttu-id="b9e0a-122">也就是说，Lync Server 2013 仅使用在位置策略中指定的免责声明。</span><span class="sxs-lookup"><span data-stu-id="b9e0a-122">That is, Lync Server 2013 uses only disclaimers specified in location policy.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="b9e0a-123">**紧急拨号字符串**</span><span class="sxs-lookup"><span data-stu-id="b9e0a-123">**Emergency Dial String**</span></span>  
    <span data-ttu-id="b9e0a-124">此拨号字符串（少于前导 "+"，但包括由 Lync 用户的拨号计划完成的任何规范化）表示呼叫是紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="b9e0a-124">This dial string (less the leading “+”, but including any normalization done by the Lync user’s Dial Plan) signifies that a call is an emergency call.</span></span> <span data-ttu-id="b9e0a-125">**紧急拨号字符串**使客户端将位置和回叫信息包含在呼叫中。</span><span class="sxs-lookup"><span data-stu-id="b9e0a-125">The **Emergency Dial String** causes the client to include location and callback information with the call.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b9e0a-126">如果您的组织不使用外部线路访问前缀，则在将呼叫发送到 Lync 池服务器上的出站路由之前，无需创建相应的拨号计划规范化规则，将 "+" 添加到911字符串中;由于位置策略，Lync 客户端将自动预置 "+"。</span><span class="sxs-lookup"><span data-stu-id="b9e0a-126">If your organization does not use an external line access prefix, you do not need to create a corresponding Dial Plan normalization rule that adds a “+” to the 911 string prior to sending the call to Outbound Routing on a Lync pool server; the “+” will be automatically prepended by the Lync client as a result of the location policy.</span></span> <span data-ttu-id="b9e0a-127">但是，如果您的网站使用外部访问前缀，则需要向适用的拨号计划策略中添加规范化规则，以去除外部访问前缀并添加 "+"。</span><span class="sxs-lookup"><span data-stu-id="b9e0a-127">However, if your site uses an external access prefix, you need to add a normalization rule to the applicable Dial Plan policy that strips the external access prefix and adds the “+”.</span></span> <span data-ttu-id="b9e0a-128">例如，如果您的位置使用外部访问前缀9，并且用户拨打 9&nbsp;911 以发出紧急呼叫，则在呼叫者的位置配置文件中的路由评估拨号号码之前，客户端将使用其拨号计划策略将其与 + 911 进行规范化。</span><span class="sxs-lookup"><span data-stu-id="b9e0a-128">For example, if your location uses an external access prefix of 9 and a user dials 9&nbsp;911 to place an emergency call, the client will use its Dial Plan policy to normalize this to +911 before the dialed number is evaluated by the routes in the caller’s location profile.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="b9e0a-129">**紧急拨号字符串掩码**</span><span class="sxs-lookup"><span data-stu-id="b9e0a-129">**Emergency Dial String Masks**</span></span>  
    <span data-ttu-id="b9e0a-130">将以分号分隔的拨号字符串列表转换为指定的**紧急拨号字符串**。</span><span class="sxs-lookup"><span data-stu-id="b9e0a-130">A semicolon-separated list of dial strings that is translated into the specified **Emergency Dial String**.</span></span> <span data-ttu-id="b9e0a-131">例如，您可能希望添加112，这是欧洲大多数欧洲的紧急服务号码。</span><span class="sxs-lookup"><span data-stu-id="b9e0a-131">For example, you may want to add 112, which is the emergency service number for most of Europe.</span></span> <span data-ttu-id="b9e0a-132">来自欧洲的来访 Lync 用户可能不知道911是美国的紧急号码，但可以拨打112并获得相同的结果。</span><span class="sxs-lookup"><span data-stu-id="b9e0a-132">A visiting Lync user from Europe may not know that 911 is the U.S. emergency number, but they can dial 112 and get the same result.</span></span> <span data-ttu-id="b9e0a-133">与紧急拨号字符串一样，在每个号码前不包含 "+"，如果您使用外部线路访问代码，请确保用户的拨号计划策略中有规范化规则，以去除访问代码位。</span><span class="sxs-lookup"><span data-stu-id="b9e0a-133">As with the Emergency Dial String, do not include a “+” before each number, and if you use external line access codes, be sure there are normalization rules in the user’s Dial Plan policy to strip off the access code digit.</span></span>

<!-- end list -->

  - <span data-ttu-id="b9e0a-134">**PSTN 用法**</span><span class="sxs-lookup"><span data-stu-id="b9e0a-134">**PSTN Usage**</span></span>  
    <span data-ttu-id="b9e0a-135">包含用于确定哪些 SIP 中继、PSTN 网关或 ELIN 网关紧急呼叫将转到的路由路径的 PSTN 用法的名称。</span><span class="sxs-lookup"><span data-stu-id="b9e0a-135">The name of the PSTN Usage that contains the routing paths that determine which SIP trunk, PSTN gateway, or ELIN gateway emergency calls will go to.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b9e0a-136">一个位置策略只能分配一个用法。</span><span class="sxs-lookup"><span data-stu-id="b9e0a-136">Only one usage can be assigned to a location policy.</span></span> <span data-ttu-id="b9e0a-137">此 PSTN 用法覆盖分配给用户语音策略的 PSTN 用法，但仅适用于进入紧急拨号字符串或某个紧急拨号字符串掩码的呼叫。</span><span class="sxs-lookup"><span data-stu-id="b9e0a-137">This PSTN Usage overrides the PSTN Usages assigned to the user’s voice policy, but applies only to calls placed to the Emergency Dial String or to one of the Emergency Dial String Masks.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="b9e0a-138">**通知 URI**</span><span class="sxs-lookup"><span data-stu-id="b9e0a-138">**Notification URI**</span></span>  
    <span data-ttu-id="b9e0a-139">指定在发出紧急呼叫时接收即时消息（IM）通知的安全人员的一个或多个 SIP Uri。</span><span class="sxs-lookup"><span data-stu-id="b9e0a-139">Specifies one or more SIP URIs of the security personnel who receive an instant messaging (IM) notification when an emergency call is placed.</span></span> <span data-ttu-id="b9e0a-140">支持通讯组。</span><span class="sxs-lookup"><span data-stu-id="b9e0a-140">Distribution groups are supported.</span></span>

<!-- end list -->

  - <span data-ttu-id="b9e0a-141">**会议 URI**</span><span class="sxs-lookup"><span data-stu-id="b9e0a-141">**Conference URI**</span></span>  
    <span data-ttu-id="b9e0a-142">指定在发出紧急呼叫时应 conferenced 的直接向内拨号（已）号码（通常为 security 书桌号码）。</span><span class="sxs-lookup"><span data-stu-id="b9e0a-142">Specifies a direct inward dialing (DID) number (typically, a security desk number) that should be conferenced in when an emergency call is placed.</span></span>

<!-- end list -->

  - <span data-ttu-id="b9e0a-143">**会议模式**</span><span class="sxs-lookup"><span data-stu-id="b9e0a-143">**Conference Mode**</span></span>  
    <span data-ttu-id="b9e0a-144">指定是使用单向通信还是双向通信将会议 URI conferenced 为紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="b9e0a-144">Specifies if the conference URI will be conferenced into the emergency call by using one-way or two-way communication.</span></span>

<!-- end list -->

  - <span data-ttu-id="b9e0a-145">**位置刷新间隔**</span><span class="sxs-lookup"><span data-stu-id="b9e0a-145">**Location Refresh Interval**</span></span>  
    <span data-ttu-id="b9e0a-146">指定来自位置信息服务的位置更新的客户端请求之间的时间（以小时为单位）。</span><span class="sxs-lookup"><span data-stu-id="b9e0a-146">Specifies the amount of time (in hours) between client requests for a location update from the Location Information service.</span></span> <span data-ttu-id="b9e0a-147">值可以设置为1到12之间的任意值。</span><span class="sxs-lookup"><span data-stu-id="b9e0a-147">The value can be set to any value between 1 and 12.</span></span> <span data-ttu-id="b9e0a-148">默认值为 4。</span><span class="sxs-lookup"><span data-stu-id="b9e0a-148">The default value is 4.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

