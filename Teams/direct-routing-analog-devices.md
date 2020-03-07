---
title: 直接路由连接模拟设备
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: conceptual
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 阅读本文以了解如何将模拟设备与 Microsoft Phone 系统直接路由配合使用。
ms.openlocfilehash: 45128b8806644e4399687787bcce251ccb807d85
ms.sourcegitcommit: a6425a536746e129ab8bda3984b5ae63fb316192
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/07/2020
ms.locfileid: "42558512"
---
# <a name="how-to-use-analog-devices-with-phone-system-direct-routing"></a><span data-ttu-id="c0fbd-103">如何将模拟设备与电话系统直接路由配合使用</span><span class="sxs-lookup"><span data-stu-id="c0fbd-103">How to use analog devices with Phone System Direct Routing</span></span>

<span data-ttu-id="c0fbd-104">本文介绍如何将模拟设备与电话系统直接路由配合使用。</span><span class="sxs-lookup"><span data-stu-id="c0fbd-104">This article describes how to use analog devices with Phone System Direct Routing.</span></span> <span data-ttu-id="c0fbd-105">要将模拟设备连接到直接路由，必须使用模拟电话适配器（ATA），并且此适配器必须由认证的 "边界控制器（SBC）供应商" 支持。</span><span class="sxs-lookup"><span data-stu-id="c0fbd-105">To connect analog devices to Direct Routing, you must use an Analog Telephony Adapter (ATA), and this adapter must be supported by the certified Session Border Controller (SBC) vendor.</span></span> 

<span data-ttu-id="c0fbd-106">当用户从模拟设备进行呼叫时，信号和媒体将通过模拟电话适配器（ATA）传递给 SBC。</span><span class="sxs-lookup"><span data-stu-id="c0fbd-106">When a user makes a call from an analog device, the signaling and media flow through the Analog Telephony Adapter (ATA) to the SBC.</span></span>  <span data-ttu-id="c0fbd-107">SBC 将呼叫发送到 Microsoft 团队终结点或基于内部路由表的公共交换电话网络（PSTN）。</span><span class="sxs-lookup"><span data-stu-id="c0fbd-107">The SBC sends the call to a Microsoft Teams endpoint or to the Public Switched Telephone Network (PSTN) based on the internal routing table.</span></span>  <span data-ttu-id="c0fbd-108">当设备进行呼叫时，它所采用的路由取决于为设备创建的路由策略。</span><span class="sxs-lookup"><span data-stu-id="c0fbd-108">When a device makes a call, the route it takes depends on the routing policies created for the device.</span></span>

<span data-ttu-id="c0fbd-109">在下图中，配置了直接路由，以便任何团队从 + 1425 4XX XX XX 和 + 1425 5XX XX xx 之间的数字进行调用必须采用红色路线（点线），以及与 + 1425 4XX xx XX 和任何其他号码之间的任何 PSTN 呼叫，除了 号码范围 + 1425 5XX XX xx 必须采用蓝色路线（实线）。</span><span class="sxs-lookup"><span data-stu-id="c0fbd-109">In the following diagram, Direct Routing is configured so that any Teams calls to and from the numbers between +1425 4XX XX XX and +1425 5XX XX XX must take the red route (dotted line), and any PSTN call to and from numbers between +1425 4XX XX XX and any other number except number range +1425 5XX XX XX must take the blue route (solid line).</span></span> 

![显示直接路由配置的图表](media/direct-routing-analog-device.png)

## <a name="example--how-to-configure-the-use-of-analog-devices-with-direct-routing"></a><span data-ttu-id="c0fbd-111">示例：如何通过直接路由配置模拟设备的使用</span><span class="sxs-lookup"><span data-stu-id="c0fbd-111">Example:  How to configure the use of analog devices with Direct Routing</span></span>

<span data-ttu-id="c0fbd-112">若要配置使用直接路由的模拟设备，必须将模拟电话适配器连接到 SBC，并将 SBC 配置为使用直接路由。</span><span class="sxs-lookup"><span data-stu-id="c0fbd-112">To configure the use of analog devices with Direct Routing, you must connect the Analog Telephony Adapter to the SBC, and configure the SBC to work with Direct Routing.</span></span> 

<span data-ttu-id="c0fbd-113">此示例将指导你完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="c0fbd-113">This example walks you through the following steps:</span></span>

1. <span data-ttu-id="c0fbd-114">将 SBC 连接到直接路由。</span><span class="sxs-lookup"><span data-stu-id="c0fbd-114">Connect the SBC to Direct Routing.</span></span>
2. <span data-ttu-id="c0fbd-115">创建 PSTN 使用。</span><span class="sxs-lookup"><span data-stu-id="c0fbd-115">Create the PSTN Usage.</span></span>
3. <span data-ttu-id="c0fbd-116">创建一个语音路线，并将其与 PSTN 使用相关联。</span><span class="sxs-lookup"><span data-stu-id="c0fbd-116">Create a voice route and associate it with the PSTN Usage.</span></span>
4. <span data-ttu-id="c0fbd-117">将语音路由分配给 PSTN 使用。</span><span class="sxs-lookup"><span data-stu-id="c0fbd-117">Assign the voice route to the PSTN Usage.</span></span>
5. <span data-ttu-id="c0fbd-118">启用联机用户。</span><span class="sxs-lookup"><span data-stu-id="c0fbd-118">Enable the online user.</span></span>
6. <span data-ttu-id="c0fbd-119">将语音路由策略分配给用户。</span><span class="sxs-lookup"><span data-stu-id="c0fbd-119">Assign the voice route policy to the user.</span></span>
7. <span data-ttu-id="c0fbd-120">为模拟设备创建语音路由。</span><span class="sxs-lookup"><span data-stu-id="c0fbd-120">Create a voice route for an analog device.</span></span>

<span data-ttu-id="c0fbd-121">有关如何将 ATA 连接到 SBC 和配置 SBC 的信息，请参阅 SBC 制造商配置指南：</span><span class="sxs-lookup"><span data-stu-id="c0fbd-121">For information on how to connect an ATA to an SBC and configure the SBC, see your SBC manufacturer configuration guide:</span></span>
- [<span data-ttu-id="c0fbd-122">AudioCodes 配置文档</span><span class="sxs-lookup"><span data-stu-id="c0fbd-122">AudioCodes configuration documentation</span></span>](https://www.audiocodes.com/media/14278/connecting-audiocodes-sbc-with-analog-device-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf)
- [<span data-ttu-id="c0fbd-123">功能区配置文档</span><span class="sxs-lookup"><span data-stu-id="c0fbd-123">Ribbon configuration documentation</span></span>](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)

## <a name="step-1--connect-the-sbc-to-direct-routing"></a><span data-ttu-id="c0fbd-124">第 1 步</span><span class="sxs-lookup"><span data-stu-id="c0fbd-124">Step 1.</span></span>  <span data-ttu-id="c0fbd-125">将 SBC 连接到直接路由</span><span class="sxs-lookup"><span data-stu-id="c0fbd-125">Connect the SBC to Direct Routing</span></span>

<span data-ttu-id="c0fbd-126">以下命令将配置 SBC 连接，如下所示：</span><span class="sxs-lookup"><span data-stu-id="c0fbd-126">The following command configures the SBC connection as follows:</span></span>

- <span data-ttu-id="c0fbd-127">FQDN sbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c0fbd-127">FQDN sbc.contoso.com</span></span>
- <span data-ttu-id="c0fbd-128">发信号端口5068</span><span class="sxs-lookup"><span data-stu-id="c0fbd-128">Signaling port 5068</span></span>
- <span data-ttu-id="c0fbd-129">媒体绕过模式</span><span class="sxs-lookup"><span data-stu-id="c0fbd-129">Media bypass mode</span></span>
- <span data-ttu-id="c0fbd-130">向 SBC 转发的通话历史记录信息</span><span class="sxs-lookup"><span data-stu-id="c0fbd-130">Call history information forwarded to the SBC-</span></span>
- <span data-ttu-id="c0fbd-131">P-声明的标识（PAI）标头与呼叫一起转发</span><span class="sxs-lookup"><span data-stu-id="c0fbd-131">P-Asserted-Identity (PAI) header forwarded along with the call</span></span> 

```
PS C:\> New-CsOnlinePSTNGateway -FQDN sbc.contoso.com -SIPSignalingPort 5068 -ForwardCallHistory $true -ForwardPAI $true -MediaBypass $true -Enabled $true 
```

## <a name="step-2--create-the-pstn-usage"></a><span data-ttu-id="c0fbd-132">步骤2：创建 PSTN 使用</span><span class="sxs-lookup"><span data-stu-id="c0fbd-132">Step 2:  Create the PSTN usage</span></span> 

<span data-ttu-id="c0fbd-133">下一个命令将创建空的 PSTN 用法。</span><span class="sxs-lookup"><span data-stu-id="c0fbd-133">The next command creates an empty PSTN usage.</span></span> <span data-ttu-id="c0fbd-134">联机 PSTN 用法是用于呼叫授权的字符串值。</span><span class="sxs-lookup"><span data-stu-id="c0fbd-134">Online PSTN usages are string values that are used for call authorization.</span></span> <span data-ttu-id="c0fbd-135">在线 PSTN 使用将在线语音策略链接到一个路线。</span><span class="sxs-lookup"><span data-stu-id="c0fbd-135">An online PSTN usage links an online voice policy to a route.</span></span> <span data-ttu-id="c0fbd-136">此示例将字符串 "Interop" 添加到可用 PSTN 用法的当前列表。</span><span class="sxs-lookup"><span data-stu-id="c0fbd-136">This example adds the string "Interop" to the current list of available PSTN usages.</span></span> 

```
PS C:\> Set-CsOnlinePstnUsage -Identity global -Usage @{add="Interop"} 
```

## <a name="step-3--create-a-voice-route-and-associate-it-with-the-pstn-usage"></a><span data-ttu-id="c0fbd-137">步骤3：创建语音路由并将其与 PSTN 使用关联：</span><span class="sxs-lookup"><span data-stu-id="c0fbd-137">Step 3:  Create a voice route and associate it with the PSTN usage:</span></span>

<span data-ttu-id="c0fbd-138">此命令将创建一个新的在线语音路线，其中包含数字范围 + 1425 XXX xx XX 的标识 "模拟-互操作"。</span><span class="sxs-lookup"><span data-stu-id="c0fbd-138">This command creates a new online voice route with the identity “analog-interop” for the number range +1425 XXX XX XX.</span></span>  <span data-ttu-id="c0fbd-139">语音路线适用于联机网关 sbc.contoso.com 的列表，并将该路线与联机 PSTN 使用 "互操作" 关联。</span><span class="sxs-lookup"><span data-stu-id="c0fbd-139">The voice route is applicable to a list of online gateways sbc.contoso.com and associates the route with online PSTN usage “Interop”.</span></span> <span data-ttu-id="c0fbd-140">语音路由包括用于标识将通过给定语音路线路由哪些电话号码的正则表达式：</span><span class="sxs-lookup"><span data-stu-id="c0fbd-140">A voice route includes a regular expression that identifies which phone numbers will be routed through a given voice route:</span></span>

```
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(425)(\d{7}])$" -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "
```

## <a name="step-4-assign-the-voice-route-to-the-pstn-usage"></a><span data-ttu-id="c0fbd-141">步骤4：将语音路由分配给 PSTN 使用：</span><span class="sxs-lookup"><span data-stu-id="c0fbd-141">Step 4: Assign the voice route to the PSTN usage:</span></span>

<span data-ttu-id="c0fbd-142">此命令使用标识 "AnalogInteropPolicy" 创建新的每用户语音路由策略。</span><span class="sxs-lookup"><span data-stu-id="c0fbd-142">This command creates a new online per-user voice routing policy with the Identity “AnalogInteropPolicy”.</span></span> <span data-ttu-id="c0fbd-143">此策略被分配了一个在线 PSTN 使用： "互操作"。</span><span class="sxs-lookup"><span data-stu-id="c0fbd-143">This policy is assigned a single online PSTN usage: “Interop”.</span></span>

```
PS C:\> New-CsOnlineVoiceRoutingPolicy -Identity "AnalogInteropPolicy" -Name "AnalogInteropPolicy" -OnlinePstnUsages "Interop"
```

## <a name="step-5-enable-the-online-user"></a><span data-ttu-id="c0fbd-144">步骤5：启用联机用户</span><span class="sxs-lookup"><span data-stu-id="c0fbd-144">Step 5: Enable the online user</span></span>

<span data-ttu-id="c0fbd-145">此命令使用标识 exampleuser@contoso.com 修改用户帐户。</span><span class="sxs-lookup"><span data-stu-id="c0fbd-145">This command modifies the user account with the Identity exampleuser@contoso.com.</span></span> <span data-ttu-id="c0fbd-146">在这种情况下，修改帐户以启用企业语音、Microsoft VoIP 的 Microsoft 实现以及已启用的语音邮件，并向此用户分配数字 + 14255000000。</span><span class="sxs-lookup"><span data-stu-id="c0fbd-146">In this case, the account is modified to enable Enterprise Voice, the Microsoft implementation of VoIP, with enabled voice mail and assigns the number +14255000000 to this user.</span></span>  <span data-ttu-id="c0fbd-147">应为公司租户中的每个团队用户（不包括 ATA 设备用户）运行此命令。</span><span class="sxs-lookup"><span data-stu-id="c0fbd-147">This command should be run for each Teams user (excluding ATA device users) in the company tenant.</span></span>

```
PS C:\> Set-CsUser -Identity "exampleuser@contoso.com" -EnterpriseVoiceEnabled $True -HostedVoiceMail $True -OnPremLineUri "tel:+14255000000"
```

## <a name="step-6-assign-the-voice-route-policy-to-a-user"></a><span data-ttu-id="c0fbd-148">步骤6：将语音路由策略分配给用户</span><span class="sxs-lookup"><span data-stu-id="c0fbd-148">Step 6: Assign the voice route policy to a user</span></span>

<span data-ttu-id="c0fbd-149">此命令将每用户联机语音路由策略 AnalogInteropPolicy 分配给具有标识 exampleuser@contoso.com 的用户。</span><span class="sxs-lookup"><span data-stu-id="c0fbd-149">This command assigns the per-user online voice routing policy AnalogInteropPolicy to the user with the identity exampleuser@contoso.com.</span></span>  <span data-ttu-id="c0fbd-150">应为公司租户中的每个团队用户（不包括 ATA 设备用户）运行此命令。</span><span class="sxs-lookup"><span data-stu-id="c0fbd-150">This command should be run for each Teams user (excluding ATA device users) in the company tenant.</span></span>

```
PS C:\> Grant-CsOnlineVoiceRoutingPolicy -Identity "exampleuser@contoso.com" -PolicyName "AnalogInteropPolicy" 
```

## <a name="step-7--create-a-voice-route-for-an-analog-device"></a><span data-ttu-id="c0fbd-151">步骤7：为模拟设备创建语音路由</span><span class="sxs-lookup"><span data-stu-id="c0fbd-151">Step 7:  Create a voice route for an analog device</span></span>

<span data-ttu-id="c0fbd-152">此命令将创建一个在线语音路线，该路线的号码范围 + 1425 4XX XX xx （适用于联机网关 sbc.contoso.com 列表），并将其与在线 PSTN 使用 "互操作" 关联。</span><span class="sxs-lookup"><span data-stu-id="c0fbd-152">This command creates an online voice route with identity “analog-interop” for number range +1425 4XX XX XX applicable to a list of online gateways sbc.contoso.com and associates it with online PSTN usage “Interop”.</span></span>  <span data-ttu-id="c0fbd-153">应为具有相应电话号码模式的每个模拟设备运行此命令。</span><span class="sxs-lookup"><span data-stu-id="c0fbd-153">This command should be run for each analog device with appropriate phone number pattern.</span></span> <span data-ttu-id="c0fbd-154">或者，在前面的步骤中配置联机语音路由时，可以使用模拟设备的正确数字模式。</span><span class="sxs-lookup"><span data-stu-id="c0fbd-154">Alternatively, a proper number pattern for analog devices can be used while configuring the online voice route during one of the previous steps.</span></span>

```
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(4254)(\d{6}])$"  -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "Interop"
```

## <a name="considerations"></a><span data-ttu-id="c0fbd-155">考虑事项</span><span class="sxs-lookup"><span data-stu-id="c0fbd-155">Considerations</span></span>

- <span data-ttu-id="c0fbd-156">除非另有说明，模拟设备是可以发送 DTMF 数字的任何设备来发出呼叫。</span><span class="sxs-lookup"><span data-stu-id="c0fbd-156">Unless otherwise note, an analog device is any device that can send DTMF digits to place a call.</span></span> <span data-ttu-id="c0fbd-157">例如，模拟电话、传真机和投影机呼机。</span><span class="sxs-lookup"><span data-stu-id="c0fbd-157">For example, analog phones, fax machines, and overhead pagers.</span></span>
- <span data-ttu-id="c0fbd-158">连接到 ATA 的模拟电话无法从团队中搜索。</span><span class="sxs-lookup"><span data-stu-id="c0fbd-158">Analog phones connected to an ATA are not searchable from Teams.</span></span> <span data-ttu-id="c0fbd-159">团队用户必须手动输入与设备关联的电话号码才能调用该设备。</span><span class="sxs-lookup"><span data-stu-id="c0fbd-159">Teams users must manually enter the phone number associated with the device to call that device.</span></span>  
 

## <a name="see-also"></a><span data-ttu-id="c0fbd-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c0fbd-160">See also</span></span>

[<span data-ttu-id="c0fbd-161">规划直接路由</span><span class="sxs-lookup"><span data-stu-id="c0fbd-161">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="c0fbd-162">配置直接路由</span><span class="sxs-lookup"><span data-stu-id="c0fbd-162">Configure Direct Routing</span></span>](direct-routing-configure.md)
