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
ms.openlocfilehash: feb7550412fa6cdcda3a8fc4dd9b7913912c34e1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728352"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-the-location-policy-for-lync-server-2013"></a><span data-ttu-id="9b240-102">定义 Lync Server 2013 的位置策略</span><span class="sxs-lookup"><span data-stu-id="9b240-102">Defining the location policy for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9b240-103">_**主题上次修改时间：** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="9b240-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="9b240-104">每个位置策略包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="9b240-104">Each location policy contains the following information:</span></span>

  - <span data-ttu-id="9b240-105">**已启用紧急服务**</span><span class="sxs-lookup"><span data-stu-id="9b240-105">**Emergency Services Enabled**</span></span>  
    <span data-ttu-id="9b240-106">如果此值为 **"是"**，则为 E9 启用客户端-1-1。</span><span class="sxs-lookup"><span data-stu-id="9b240-106">When this value is **Yes**, the client is enabled for E9-1-1.</span></span> <span data-ttu-id="9b240-107">客户端注册时，它会尝试从位置信息服务获取位置，并将位置信息包含在紧急呼叫的一部分中。</span><span class="sxs-lookup"><span data-stu-id="9b240-107">When a client registers, it attempts to acquire a location from the Location Information service and will include the location information as part of an emergency call.</span></span>

<!-- end list -->

  - <span data-ttu-id="9b240-108">**需要位置**</span><span class="sxs-lookup"><span data-stu-id="9b240-108">**Location Required**</span></span>  
    <span data-ttu-id="9b240-109">此设置仅在 "**已启用** 的兴起服务" 设置为 **"是"** 时使用。</span><span class="sxs-lookup"><span data-stu-id="9b240-109">This setting is used only when **Emergence Services Enabled** is set to **Yes**.</span></span>
    
    <span data-ttu-id="9b240-110">你可以配置 "**需要位置**" 设置以定义客户端行为。</span><span class="sxs-lookup"><span data-stu-id="9b240-110">You can configure the **Location Required** setting to define the client behavior.</span></span> <span data-ttu-id="9b240-111">将该值设为**否**表示不会提示用户输入位置。</span><span class="sxs-lookup"><span data-stu-id="9b240-111">Setting the value to **No** means that the user will not be prompted for a location.</span></span> <span data-ttu-id="9b240-112">设为**是**表示将提示用户输入位置，但可以消除提示。</span><span class="sxs-lookup"><span data-stu-id="9b240-112">Setting the value to **Yes** means that the user will be prompted for a location, but can dismiss the prompt.</span></span> <span data-ttu-id="9b240-113">设为**免责声明**表示将会提示用户输入位置，并且当用户尝试消除提示时将显示免责声明。</span><span class="sxs-lookup"><span data-stu-id="9b240-113">Setting the value to **Disclaimer** means that the user will be prompted for a location and also will be shown a disclaimer if they try to dismiss the prompt.</span></span> <span data-ttu-id="9b240-114">在所有情况下，用户都可以继续使用该客户端。</span><span class="sxs-lookup"><span data-stu-id="9b240-114">In all cases, the user can continue to use the client.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9b240-p103">如果在启用 E9-1-1 之前用户手动输入位置，则不会显示免责声明文本。已查看免责声明的用户将不能查看免责声明文本的更新。</span><span class="sxs-lookup"><span data-stu-id="9b240-p103">The disclaimer text will not appear if a user manually entered a location before being enabled for E9-1-1. Updates to the disclaimer text will not be viewed by users that have already viewed the disclaimer.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="9b240-117">**增强型紧急服务免责声明**</span><span class="sxs-lookup"><span data-stu-id="9b240-117">**Enhanced Emergency Service Disclaimer**</span></span>  
    <span data-ttu-id="9b240-118">该设置指定当用户消除输入位置提示时显示的免责声明。</span><span class="sxs-lookup"><span data-stu-id="9b240-118">This setting specifies the disclaimer that users see if they dismiss the prompt for a location.</span></span> <span data-ttu-id="9b240-119">在 Lync Server 2013 中，你可以使用位置策略为不同的区域设置或不同的用户集设置不同的免责声明。</span><span class="sxs-lookup"><span data-stu-id="9b240-119">In Lync Server 2013, you can use location policy to set different disclaimers for different locales or different sets of users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9b240-120">此位置策略设置与 Lync Server 2010 不同，您使用<STRONG>CsEnhancedEmergencyServiceDisclaimer</STRONG> cmdlet 为整个组织设置全局免责声明。</span><span class="sxs-lookup"><span data-stu-id="9b240-120">This location policy setting differs from Lync Server 2010, where you used the <STRONG>Set-CsEnhancedEmergencyServiceDisclaimer</STRONG> cmdlet to set a global disclaimer for the entire organization.</span></span> <span data-ttu-id="9b240-121">如果全局免责声明已存在，则需要在位置策略中指定该免责声明。</span><span class="sxs-lookup"><span data-stu-id="9b240-121">If a global disclaimer already exists, you need to specify that disclaimer in location policy.</span></span> <span data-ttu-id="9b240-122">也就是说，Lync Server 2013 仅使用位置策略中指定的免责声明。</span><span class="sxs-lookup"><span data-stu-id="9b240-122">That is, Lync Server 2013 uses only disclaimers specified in location policy.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="9b240-123">**紧急拨号字符串**</span><span class="sxs-lookup"><span data-stu-id="9b240-123">**Emergency Dial String**</span></span>  
    <span data-ttu-id="9b240-124">此拨号字符串（较少前导 "+"，但包括 Lync 用户的拨号计划完成的任何规范化）表示呼叫是紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="9b240-124">This dial string (less the leading “+”, but including any normalization done by the Lync user’s Dial Plan) signifies that a call is an emergency call.</span></span> <span data-ttu-id="9b240-125">**紧急拨号串**使客户端包括有关呼叫的位置和回拨信息。</span><span class="sxs-lookup"><span data-stu-id="9b240-125">The **Emergency Dial String** causes the client to include location and callback information with the call.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9b240-126">如果您的组织不使用外部线路访问前缀，则无需创建相应的拨号计划规范化规则，在将呼叫发送到 Lync 池服务器上的出站路由之前将 "+" 添加到911字符串;由于位置策略，Lync 客户端将自动预置 "+"。</span><span class="sxs-lookup"><span data-stu-id="9b240-126">If your organization does not use an external line access prefix, you do not need to create a corresponding Dial Plan normalization rule that adds a “+” to the 911 string prior to sending the call to Outbound Routing on a Lync pool server; the “+” will be automatically prepended by the Lync client as a result of the location policy.</span></span> <span data-ttu-id="9b240-127">但是，如果你的站点使用外部访问前缀，则需要向适用的拨号计划策略添加规范化规则，以去掉外部访问前缀并添加“+”。</span><span class="sxs-lookup"><span data-stu-id="9b240-127">However, if your site uses an external access prefix, you need to add a normalization rule to the applicable Dial Plan policy that strips the external access prefix and adds the “+”.</span></span> <span data-ttu-id="9b240-128">例如，如果你的位置使用了外部访问前缀9，并且用户拨了 9&nbsp;911 以进行紧急呼叫，则客户端将使用其拨号计划策略将此号码与 + 911 进行规范化，然后由呼叫者的位置配置文件中的路由评估该拨出的号码。</span><span class="sxs-lookup"><span data-stu-id="9b240-128">For example, if your location uses an external access prefix of 9 and a user dials 9&nbsp;911 to place an emergency call, the client will use its Dial Plan policy to normalize this to +911 before the dialed number is evaluated by the routes in the caller’s location profile.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="9b240-129">**紧急拨号字符串掩码**</span><span class="sxs-lookup"><span data-stu-id="9b240-129">**Emergency Dial String Masks**</span></span>  
    <span data-ttu-id="9b240-130">一个分号分隔的拨号字符串列表，将转换为指定的**紧急拨号字符串**。</span><span class="sxs-lookup"><span data-stu-id="9b240-130">A semicolon-separated list of dial strings that is translated into the specified **Emergency Dial String**.</span></span> <span data-ttu-id="9b240-131">例如，你可能想要添加 112（欧洲大部分地区的紧急服务号码）。</span><span class="sxs-lookup"><span data-stu-id="9b240-131">For example, you may want to add 112, which is the emergency service number for most of Europe.</span></span> <span data-ttu-id="9b240-132">从欧洲访问 Lync 用户可能不知道911是美国的紧急电话号码，但他们可以拨打112并获得相同的结果。</span><span class="sxs-lookup"><span data-stu-id="9b240-132">A visiting Lync user from Europe may not know that 911 is the U.S. emergency number, but they can dial 112 and get the same result.</span></span> <span data-ttu-id="9b240-133">使用紧急拨号字符串，每个号码前都没有“+”，如果你使用外线访问代码，请确保用户的拨号计划策略中存在规范化规则以去掉访问代码数字。</span><span class="sxs-lookup"><span data-stu-id="9b240-133">As with the Emergency Dial String, do not include a “+” before each number, and if you use external line access codes, be sure there are normalization rules in the user’s Dial Plan policy to strip off the access code digit.</span></span>

<!-- end list -->

  - <span data-ttu-id="9b240-134">**PSTN 用法**</span><span class="sxs-lookup"><span data-stu-id="9b240-134">**PSTN Usage**</span></span>  
    <span data-ttu-id="9b240-135">包含确定紧急呼叫将转至哪一 SIP 中继、PSTN 网关或 ELIN 网关的路由路径的 PSTN 用法名称。</span><span class="sxs-lookup"><span data-stu-id="9b240-135">The name of the PSTN Usage that contains the routing paths that determine which SIP trunk, PSTN gateway, or ELIN gateway emergency calls will go to.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9b240-p109">一个用法只能分配给一个位置策略。此 PSTN 用法覆盖分配给用户语音策略的 PSTN 用法，但仅适用于紧急拨号字符串或紧急拨号字符串掩码之一发出的呼叫。</span><span class="sxs-lookup"><span data-stu-id="9b240-p109">Only one usage can be assigned to a location policy. This PSTN Usage overrides the PSTN Usages assigned to the user’s voice policy, but applies only to calls placed to the Emergency Dial String or to one of the Emergency Dial String Masks.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="9b240-138">**通知 URI**</span><span class="sxs-lookup"><span data-stu-id="9b240-138">**Notification URI**</span></span>  
    <span data-ttu-id="9b240-p110">指定要在发出紧急呼叫时接收即时消息 (IM) 通知的安全人员的一个或多个 SIP URI。支持通讯组。</span><span class="sxs-lookup"><span data-stu-id="9b240-p110">Specifies one or more SIP URIs of the security personnel who receive an instant messaging (IM) notification when an emergency call is placed. Distribution groups are supported.</span></span>

<!-- end list -->

  - <span data-ttu-id="9b240-141">**会议 URI**</span><span class="sxs-lookup"><span data-stu-id="9b240-141">**Conference URI**</span></span>  
    <span data-ttu-id="9b240-142">指定在发出紧急呼叫时应加入会议的外线直拨分机 (DID) 号码（通常是安全服务台号码）。</span><span class="sxs-lookup"><span data-stu-id="9b240-142">Specifies a direct inward dialing (DID) number (typically, a security desk number) that should be conferenced in when an emergency call is placed.</span></span>

<!-- end list -->

  - <span data-ttu-id="9b240-143">**会议模式**</span><span class="sxs-lookup"><span data-stu-id="9b240-143">**Conference Mode**</span></span>  
    <span data-ttu-id="9b240-144">指定会议 URI 将使用单向还是双向通信加入紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="9b240-144">Specifies if the conference URI will be conferenced into the emergency call by using one-way or two-way communication.</span></span>

<!-- end list -->

  - <span data-ttu-id="9b240-145">**位置刷新间隔**</span><span class="sxs-lookup"><span data-stu-id="9b240-145">**Location Refresh Interval**</span></span>  
    <span data-ttu-id="9b240-146">指定从位置信息服务的位置更新的客户端请求之间的时间量（以小时为单位）。</span><span class="sxs-lookup"><span data-stu-id="9b240-146">Specifies the amount of time (in hours) between client requests for a location update from the Location Information service.</span></span> <span data-ttu-id="9b240-147">该值可以设置为 1 和 12 之间的任意值。</span><span class="sxs-lookup"><span data-stu-id="9b240-147">The value can be set to any value between 1 and 12.</span></span> <span data-ttu-id="9b240-148">默认值为 4。</span><span class="sxs-lookup"><span data-stu-id="9b240-148">The default value is 4.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

