---
title: 在 Skype for Business Server 中配置 E9-1-1 语音路由
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6933b840-0e7b-4509-ae43-bc9065677547
description: 在 Skype for Business Server 服务中配置 E9-1-1 企业语音。
ms.openlocfilehash: b5f3d12bb586a65fc1c553a021c1a27efb0c7f77
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804172"
---
# <a name="configure-an-e9-1-1-voice-route-in-skype-for-business-server"></a><span data-ttu-id="e01b9-103">在 Skype for Business Server 中配置 E9-1-1 语音路由</span><span class="sxs-lookup"><span data-stu-id="e01b9-103">Configure an E9-1-1 voice route in Skype for Business Server</span></span>
 
<span data-ttu-id="e01b9-104">在 Skype for Business Server 服务中配置 E9-1-1 企业语音。</span><span class="sxs-lookup"><span data-stu-id="e01b9-104">Configure E9-1-1 voice routes in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="e01b9-105">若要部署 E9-1-1，首先需配置紧急呼叫语音路由。</span><span class="sxs-lookup"><span data-stu-id="e01b9-105">To deploy E9-1-1, you first need to configure an emergency call voice route.</span></span> <span data-ttu-id="e01b9-106">有关创建语音路由的详细信息，请参阅在 Skype for Business 中 [创建或修改语音路由](create-or-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="e01b9-106">For details about creating voice routes, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span> <span data-ttu-id="e01b9-107">例如，如果部署包括主要 SIP 中继和辅助 SIP 中继，则可定义多个路由。</span><span class="sxs-lookup"><span data-stu-id="e01b9-107">You may define more than one route if, for example, your deployment includes a primary SIP trunk and a secondary SIP trunk.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="e01b9-108">若要在 E9-1-1 INVITE 中包含位置信息，您需要配置连接到 E9-1-1 服务提供商的 SIP 中继以便通过网关路由紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="e01b9-108">To include location information in an E9-1-1 INVITE, you need to configure the SIP trunk that connects to the E9-1-1 service provider to route emergency calls through the gateway.</span></span> <span data-ttu-id="e01b9-109">为此，请在 **Set-CsTrunkConfiguration** cmdlet 上将 EnablePIDFLOSupport 标志设置为 True。</span><span class="sxs-lookup"><span data-stu-id="e01b9-109">To do this, set the EnablePIDFLOSupport flag on the **Set-CsTrunkConfiguration** cmdlet to True.</span></span> <span data-ttu-id="e01b9-110">EnablePIDFLOSupport 的默认值为 False。</span><span class="sxs-lookup"><span data-stu-id="e01b9-110">The default value for EnablePIDFLOSupport is False.</span></span> <span data-ttu-id="e01b9-111">例如：对于回退公用电话交换网 (PSTN) 网关和紧急位置标识号 (ELIN) 网关，不需要启用接收位置。 `Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.`</span><span class="sxs-lookup"><span data-stu-id="e01b9-111">For example: `Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.` It is not necessary to enable receiving locations for fallback public switched telephone network (PSTN) gateways and Emergency Location Identification Number (ELIN) gateways.</span></span>
  
### <a name="to-configure-an-e9-1-1-voice-route"></a><span data-ttu-id="e01b9-112">配置 E9-1-1 语音路由</span><span class="sxs-lookup"><span data-stu-id="e01b9-112">To configure an E9-1-1 voice route</span></span>

1. <span data-ttu-id="e01b9-113">使用 RTCUniversalServerAdmins 组成员或 CsVoiceAdministrator 管理角色成员帐户登录计算机。</span><span class="sxs-lookup"><span data-stu-id="e01b9-113">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins groups, or a member of the CsVoiceAdministrator administrative role.</span></span>
    
2.  <span data-ttu-id="e01b9-114">启动 Skype for Business Server命令行管理程序：单击"开始"，**单击"所有** 程序"，再单击 **"Skype for Business 2015"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**</span><span class="sxs-lookup"><span data-stu-id="e01b9-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="e01b9-115">运行以下 cmdlet 以创建新的 PSTN 用法记录。</span><span class="sxs-lookup"><span data-stu-id="e01b9-115">Run the following cmdlet to create a new PSTN usage record.</span></span> 
    
    <span data-ttu-id="e01b9-116">该名称必须与将用于位置策略中的 **PSTN** 设置的名称相同。</span><span class="sxs-lookup"><span data-stu-id="e01b9-116">This must be the same name that you will use for the **PSTN** setting in the location policy.</span></span> <span data-ttu-id="e01b9-117">尽管部署中将具有多个电话用法记录，但以下示例将“紧急用法”添加到可用 PSTN 用法的当前列表。</span><span class="sxs-lookup"><span data-stu-id="e01b9-117">Although your deployment will have multiple phone usage records, the following example adds "Emergency Usage" to the current list of available PSTN usages.</span></span> <span data-ttu-id="e01b9-118">有关详细信息，请参阅在 Skype for Business 中配置语音 [策略、PSTN 用法记录和语音路由](voice-and-pstn.md)。</span><span class="sxs-lookup"><span data-stu-id="e01b9-118">For details, see [Configure voice policies, PSTN usage records, and voice routes in Skype for Business](voice-and-pstn.md).</span></span>
    
   ```powershell
   Set-CsPstnUsage -Usage @{add='EmergencyUsage'}
   ```

4. <span data-ttu-id="e01b9-119">运行以下 cmdlet 以使用上一步中创建的 PSTN 用法记录来创建新的语音路由。</span><span class="sxs-lookup"><span data-stu-id="e01b9-119">Run the following cmdlet to create a new voice route by using the PSTN usage record that you created in the previous step.</span></span>
    
    <span data-ttu-id="e01b9-120">该号码模式必须与位置策略中的“紧急拨号字符串”设置中使用的号码模式相同。</span><span class="sxs-lookup"><span data-stu-id="e01b9-120">The number pattern must be the same number pattern that is used in the **Emergency Dial String** setting in the location policy.</span></span> <span data-ttu-id="e01b9-121">需要"+"符号，因为 Skype for Business 向紧急呼叫添加"+"。</span><span class="sxs-lookup"><span data-stu-id="e01b9-121">A "+" sign is needed because Skype for Business adds "+" to emergency calls.</span></span> <span data-ttu-id="e01b9-122">“Co1-pstngateway-1”是用于 E9-1-1 服务提供商或 ELIN 网关服务 ID 的 SIP 中继服务 ID。</span><span class="sxs-lookup"><span data-stu-id="e01b9-122">"Co1-pstngateway-1" is the SIP trunk service ID for the E9-1-1 service provider or for the ELIN gateway service ID.</span></span> <span data-ttu-id="e01b9-123">以下示例将“EmergencyRoute”用作语音路由的名称。</span><span class="sxs-lookup"><span data-stu-id="e01b9-123">The following example uses "EmergencyRoute" as the name of the voice route.</span></span>
    
   ```powershell
   New-CsVoiceRoute -Name "EmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="EmergencyUsage"} -PstnGatewayList @{add="co1-pstngateway-1"}
   ```

5. <span data-ttu-id="e01b9-124">（可选）对于 SIP 中继连接，建议您运行以下 cmdlet，为 E9-1-1 服务提供商的 SIP 中继未处理的呼叫创建本地路由。</span><span class="sxs-lookup"><span data-stu-id="e01b9-124">Optionally, for SIP trunk connections, we recommend that you run the following cmdlet to create a local route for calls that are not handled by the E9-1-1 service provider's SIP trunk.</span></span> <span data-ttu-id="e01b9-125">如果 E9-1-1 服务提供商的连接不可用，则使用此路由。</span><span class="sxs-lookup"><span data-stu-id="e01b9-125">This route will be used if the connection to the E9-1-1 service provider is not available.</span></span> 
    
    <span data-ttu-id="e01b9-126">以下示例假定用户的语音策略中具有“本地”用法。</span><span class="sxs-lookup"><span data-stu-id="e01b9-126">The following example assumes that user has "Local" usage in their voice policy.</span></span>
    
   ```powershell
   New-CsVoiceRoute -Name "LocalEmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="Local"} -PstnGatewayList @{add="co1-pstngateway-2"}
   ```


