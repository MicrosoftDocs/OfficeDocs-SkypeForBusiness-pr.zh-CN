---
title: Lync Server 2013：配置 E9-1 个语音路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure an E9-1-1 voice route
ms:assetid: 6933b840-0e7b-4509-ae43-bc9065677547
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398496(v=OCS.15)
ms:contentKeyID: 48184384
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d40d2ee5dcb0dd7f759751bdab0d3e09f4ebc577
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757836"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-an-e9-1-1-voice-route-in-lync-server-2013"></a><span data-ttu-id="b4af1-102">在 Lync Server 2013 中配置 E9-1 个语音路由</span><span class="sxs-lookup"><span data-stu-id="b4af1-102">Configure an E9-1-1 voice route in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b4af1-103">_**主题上次修改时间：** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="b4af1-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="b4af1-104">若要部署 E9-1-1，首先需配置紧急呼叫语音路由。</span><span class="sxs-lookup"><span data-stu-id="b4af1-104">To deploy E9-1-1, you first need to configure an emergency call voice route.</span></span> <span data-ttu-id="b4af1-105">有关创建语音路由的详细信息，请参阅[在 Lync Server 2013 中创建语音路由](lync-server-2013-create-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="b4af1-105">For details about creating voice routes, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span> <span data-ttu-id="b4af1-106">例如，如果部署包括主要 SIP 中继和辅助 SIP 中继，则可定义多个路由。</span><span class="sxs-lookup"><span data-stu-id="b4af1-106">You may define more than one route if, for example, your deployment includes a primary SIP trunk and a secondary SIP trunk.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b4af1-107">若要在 E9-1-1 INVITE 中包含位置信息，您需要配置连接到 E9-1-1 服务提供商的 SIP 中继以便通过网关路由紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="b4af1-107">To include location information in an E9-1-1 INVITE, you need to configure the SIP trunk that connects to the E9-1-1 service provider to route emergency calls through the gateway.</span></span> <span data-ttu-id="b4af1-108">为此，请在 <STRONG>Set-CsTrunkConfiguration</STRONG> cmdlet 上将 EnablePIDFLOSupport 标志设置为 True。</span><span class="sxs-lookup"><span data-stu-id="b4af1-108">To do this, set the EnablePIDFLOSupport flag on the <STRONG>Set-CsTrunkConfiguration</STRONG> cmdlet to True.</span></span> <span data-ttu-id="b4af1-109">EnablePIDFLOSupport 的默认值为 False。</span><span class="sxs-lookup"><span data-stu-id="b4af1-109">The default value for EnablePIDFLOSupport is False.</span></span> <span data-ttu-id="b4af1-110">例如：<CODE>Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.</CODE></span><span class="sxs-lookup"><span data-stu-id="b4af1-110">For example: <CODE>Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.</CODE></span></span><BR><span data-ttu-id="b4af1-111">无需为回退公用电话交换网 (PSTN) 网关和紧急位置标识号 (ELIN) 网关启用接收位置。</span><span class="sxs-lookup"><span data-stu-id="b4af1-111">It is not necessary to enable receiving locations for fallback public switched telephone network (PSTN) gateways and Emergency Location Identification Number (ELIN) gateways.</span></span>



</div>

<span data-ttu-id="b4af1-112">有关使用语音路由的详细信息，请参阅以下 cmdlet 的 Lync Server Management Shell 文档：</span><span class="sxs-lookup"><span data-stu-id="b4af1-112">For details about working with voice routes, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="b4af1-113">**Set-CsPstnUsage**</span><span class="sxs-lookup"><span data-stu-id="b4af1-113">**Set-CsPstnUsage**</span></span>

  - <span data-ttu-id="b4af1-114">**Get-CsPstnUsage**</span><span class="sxs-lookup"><span data-stu-id="b4af1-114">**Get-CsPstnUsage**</span></span>

  - <span data-ttu-id="b4af1-115">**新-CsVoiceRoute**</span><span class="sxs-lookup"><span data-stu-id="b4af1-115">**New-CsVoiceRoute**</span></span>

  - <span data-ttu-id="b4af1-116">**CsVoiceRoute**</span><span class="sxs-lookup"><span data-stu-id="b4af1-116">**Get-CsVoiceRoute**</span></span>

  - <span data-ttu-id="b4af1-117">**Set-CsVoiceRoute**</span><span class="sxs-lookup"><span data-stu-id="b4af1-117">**Set-CsVoiceRoute**</span></span>

  - <span data-ttu-id="b4af1-118">**Remove-CsVoiceRoute**</span><span class="sxs-lookup"><span data-stu-id="b4af1-118">**Remove-CsVoiceRoute**</span></span>

<div>

## <a name="to-configure-an-e9-1-1-voice-route"></a><span data-ttu-id="b4af1-119">配置 E9-1-1 语音路由</span><span class="sxs-lookup"><span data-stu-id="b4af1-119">To configure an E9-1-1 voice route</span></span>

1.  <span data-ttu-id="b4af1-120">使用 RTCUniversalServerAdmins 组成员或 CsVoiceAdministrator 管理角色成员帐户登录计算机。</span><span class="sxs-lookup"><span data-stu-id="b4af1-120">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins groups, or a member of the CsVoiceAdministrator administrative role.</span></span>

2.  <span data-ttu-id="b4af1-121">启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="b4af1-121">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="b4af1-122">运行以下 cmdlet 以创建新的 PSTN 用法记录。</span><span class="sxs-lookup"><span data-stu-id="b4af1-122">Run the following cmdlet to create a new PSTN usage record.</span></span>
    
    <span data-ttu-id="b4af1-123">该名称必须与将用于位置策略中的 **PSTN** 设置的名称相同。</span><span class="sxs-lookup"><span data-stu-id="b4af1-123">This must be the same name that you will use for the **PSTN** setting in the location policy.</span></span> <span data-ttu-id="b4af1-124">尽管部署中将具有多个电话用法记录，但以下示例将“紧急用法”添加到可用 PSTN 用法的当前列表。</span><span class="sxs-lookup"><span data-stu-id="b4af1-124">Although your deployment will have multiple phone usage records, the following example adds "Emergency Usage" to the current list of available PSTN usages.</span></span> <span data-ttu-id="b4af1-125">有关详细信息，请参阅[配置语音策略和 PSTN 使用记录以在 Lync Server 2013 中授权呼叫功能和权限](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)。</span><span class="sxs-lookup"><span data-stu-id="b4af1-125">For details, see [Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).</span></span>
    
        Set-CsPstnUsage -Usage @{add='EmergencyUsage'}

4.  <span data-ttu-id="b4af1-126">运行以下 cmdlet 以使用上一步中创建的 PSTN 用法记录来创建新的语音路由。</span><span class="sxs-lookup"><span data-stu-id="b4af1-126">Run the following cmdlet to create a new voice route by using the PSTN usage record that you created in the previous step.</span></span>
    
    <span data-ttu-id="b4af1-127">该号码模式必须与位置策略中的“紧急拨号字符串”\*\*\*\* 设置中使用的号码模式相同。</span><span class="sxs-lookup"><span data-stu-id="b4af1-127">The number pattern must be the same number pattern that is used in the **Emergency Dial String** setting in the location policy.</span></span> <span data-ttu-id="b4af1-128">由于 Lync 将 "+" 添加到紧急呼叫，因此需要 "+" 符号。</span><span class="sxs-lookup"><span data-stu-id="b4af1-128">A "+" sign is needed because Lync adds "+" to emergency calls.</span></span> <span data-ttu-id="b4af1-129">“Co1-pstngateway-1”是用于 E9-1-1 服务提供商或 ELIN 网关服务 ID 的 SIP 中继服务 ID。</span><span class="sxs-lookup"><span data-stu-id="b4af1-129">"Co1-pstngateway-1" is the SIP trunk service ID for the E9-1-1 service provider or for the ELIN gateway service ID.</span></span> <span data-ttu-id="b4af1-130">以下示例将“EmergencyRoute”用作语音路由的名称。</span><span class="sxs-lookup"><span data-stu-id="b4af1-130">The following example uses "EmergencyRoute" as the name of the voice route.</span></span>
    
        New-CsVoiceRoute -Name "EmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="EmergencyUsage"} -PstnGatewayList @{add="co1-pstngateway-1"}

5.  <span data-ttu-id="b4af1-p105">（可选）对于 SIP 中继连接，建议运行以下 cmdlet 为由 E9-1-1 服务提供商的 SIP 中继不处理的呼叫创建本地路由。如果 E9-1-1 服务提供商的连接不可用，则使用此路由。</span><span class="sxs-lookup"><span data-stu-id="b4af1-p105">Optionally, for SIP trunk connections, we recommend that you run the following cmdlet to create a local route for calls that are not handled by the E9-1-1 service provider’s SIP trunk. This route will be used if the connection to the E9-1-1 service provider is not available.</span></span>
    
    <span data-ttu-id="b4af1-133">以下示例假定用户的语音策略中具有“本地”用法。</span><span class="sxs-lookup"><span data-stu-id="b4af1-133">The following example assumes that user has "Local" usage in their voice policy.</span></span>
    
        New-CsVoiceRoute -Name "LocalEmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="Local"} -PstnGatewayList @{add="co1-pstngateway-2"}

</div>

</div>

<span> </span>

</div>

</div>

</div>

