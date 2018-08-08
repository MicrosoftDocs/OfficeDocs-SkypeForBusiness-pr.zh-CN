---
title: 在 Skype for Business Server 中配置 E9-1-1 语音路由
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6933b840-0e7b-4509-ae43-bc9065677547
description: 在 Skype for Business Server 企业语音配置 E9-1-1 语音路由。
ms.openlocfilehash: 85259b6490b0f14d94d4d7c26f343d638911d909
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20988746"
---
# <a name="configure-an-e9-1-1-voice-route-in-skype-for-business-server"></a><span data-ttu-id="b2453-103">在 Skype for Business Server 中配置 E9-1-1 语音路由</span><span class="sxs-lookup"><span data-stu-id="b2453-103">Configure an E9-1-1 voice route in Skype for Business Server</span></span>
 
<span data-ttu-id="b2453-104">在 Skype for Business Server 企业语音配置 E9-1-1 语音路由。</span><span class="sxs-lookup"><span data-stu-id="b2453-104">Configure E9-1-1 voice routes in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="b2453-105">若要部署 E9-1-1，首先需配置紧急呼叫语音路由。</span><span class="sxs-lookup"><span data-stu-id="b2453-105">To deploy E9-1-1, you first need to configure an emergency call voice route.</span></span> <span data-ttu-id="b2453-106">有关创建语音路由的详细信息，请参阅[创建或修改语音路由中的业务的 Skype](create-or-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="b2453-106">For details about creating voice routes, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span> <span data-ttu-id="b2453-107">例如，如果部署包括主要 SIP 中继和辅助 SIP 中继，则可定义多个路由。</span><span class="sxs-lookup"><span data-stu-id="b2453-107">You may define more than one route if, for example, your deployment includes a primary SIP trunk and a secondary SIP trunk.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="b2453-108">若要在 E9-1-1 INVITE 中包含位置信息，您需要配置连接到 E9-1-1 服务提供商的 SIP 中继以便通过网关路由紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="b2453-108">To include location information in an E9-1-1 INVITE, you need to configure the SIP trunk that connects to the E9-1-1 service provider to route emergency calls through the gateway.</span></span> <span data-ttu-id="b2453-109">若要执行此操作，请对**Set-cstrunkconfiguration** cmdlet 为 True 设置 EnablePIDFLOSupport 标志。</span><span class="sxs-lookup"><span data-stu-id="b2453-109">To do this, set the EnablePIDFLOSupport flag on the **Set-CsTrunkConfiguration** cmdlet to True.</span></span> <span data-ttu-id="b2453-110">EnablePIDFLOSupport 的默认值为 False。</span><span class="sxs-lookup"><span data-stu-id="b2453-110">The default value for EnablePIDFLOSupport is False.</span></span> <span data-ttu-id="b2453-111">例如： `Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.` ，无需为回退公共交换电话交换网 (PSTN) 网关和紧急位置识别号码 (ELIN) 网关启用接收位置。</span><span class="sxs-lookup"><span data-stu-id="b2453-111">For example: `Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.` It is not necessary to enable receiving locations for fallback public switched telephone network (PSTN) gateways and Emergency Location Identification Number (ELIN) gateways.</span></span>
  
### <a name="to-configure-an-e9-1-1-voice-route"></a><span data-ttu-id="b2453-112">配置 E9-1-1 语音路由</span><span class="sxs-lookup"><span data-stu-id="b2453-112">To configure an E9-1-1 voice route</span></span>

1. <span data-ttu-id="b2453-113">使用 RTCUniversalServerAdmins 组成员或 CsVoiceAdministrator 管理角色成员帐户登录计算机。</span><span class="sxs-lookup"><span data-stu-id="b2453-113">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins groups, or a member of the CsVoiceAdministrator administrative role.</span></span>
    
2.  <span data-ttu-id="b2453-114">启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。</span><span class="sxs-lookup"><span data-stu-id="b2453-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="b2453-115">运行以下 cmdlet 以创建新的 PSTN 用法记录。</span><span class="sxs-lookup"><span data-stu-id="b2453-115">Run the following cmdlet to create a new PSTN usage record.</span></span> 
    
    <span data-ttu-id="b2453-116">该名称必须与将用于位置策略中的 **PSTN** 设置的名称相同。</span><span class="sxs-lookup"><span data-stu-id="b2453-116">This must be the same name that you will use for the **PSTN** setting in the location policy.</span></span> <span data-ttu-id="b2453-117">尽管部署中将具有多个电话用法记录，但以下示例将“紧急用法”添加到可用 PSTN 用法的当前列表。</span><span class="sxs-lookup"><span data-stu-id="b2453-117">Although your deployment will have multiple phone usage records, the following example adds "Emergency Usage" to the current list of available PSTN usages.</span></span> <span data-ttu-id="b2453-118">有关详细信息，请参阅[配置语音策略、 PSTN 用法记录和 Skype for Business 中的语音路由](voice-and-pstn.md)。</span><span class="sxs-lookup"><span data-stu-id="b2453-118">For details, see [Configure voice policies, PSTN usage records, and voice routes in Skype for Business](voice-and-pstn.md).</span></span>
    
   ```
   Set-CsPstnUsage -Usage @{add='EmergencyUsage'}
   ```

4. <span data-ttu-id="b2453-119">运行以下 cmdlet 以使用上一步中创建的 PSTN 用法记录来创建新的语音路由。</span><span class="sxs-lookup"><span data-stu-id="b2453-119">Run the following cmdlet to create a new voice route by using the PSTN usage record that you created in the previous step.</span></span>
    
    <span data-ttu-id="b2453-120">该号码模式必须与位置策略中的“紧急拨号字符串”**** 设置中使用的号码模式相同。</span><span class="sxs-lookup"><span data-stu-id="b2453-120">The number pattern must be the same number pattern that is used in the **Emergency Dial String** setting in the location policy.</span></span> <span data-ttu-id="b2453-121">"+"登录所需因为 for Business 的 Skype 添加"+"紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="b2453-121">A "+" sign is needed because Skype for Business adds "+" to emergency calls.</span></span> <span data-ttu-id="b2453-122">“Co1-pstngateway-1”是用于 E9-1-1 服务提供商或 ELIN 网关服务 ID 的 SIP 中继服务 ID。</span><span class="sxs-lookup"><span data-stu-id="b2453-122">"Co1-pstngateway-1" is the SIP trunk service ID for the E9-1-1 service provider or for the ELIN gateway service ID.</span></span> <span data-ttu-id="b2453-123">以下示例将“EmergencyRoute”用作语音路由的名称。</span><span class="sxs-lookup"><span data-stu-id="b2453-123">The following example uses "EmergencyRoute" as the name of the voice route.</span></span>
    
   ```
   New-CsVoiceRoute -Name "EmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="EmergencyUsage"} -PstnGatewayList @{add="co1-pstngateway-1"}
   ```

5. <span data-ttu-id="b2453-124">（可选） 对于 SIP 中继连接，我们建议您运行以下 cmdlet 以创建本地路由的 E9-1-1 服务提供商的 SIP 中继不会处理的呼叫。</span><span class="sxs-lookup"><span data-stu-id="b2453-124">Optionally, for SIP trunk connections, we recommend that you run the following cmdlet to create a local route for calls that are not handled by the E9-1-1 service provider's SIP trunk.</span></span> <span data-ttu-id="b2453-125">如果 E9-1-1 服务提供商的连接不可用，则使用此路由。</span><span class="sxs-lookup"><span data-stu-id="b2453-125">This route will be used if the connection to the E9-1-1 service provider is not available.</span></span> 
    
    <span data-ttu-id="b2453-126">以下示例假定用户的语音策略中具有“本地”用法。</span><span class="sxs-lookup"><span data-stu-id="b2453-126">The following example assumes that user has "Local" usage in their voice policy.</span></span>
    
   ```
   New-CsVoiceRoute -Name "LocalEmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="Local"} -PstnGatewayList @{add="co1-pstngateway-2"}
   ```


