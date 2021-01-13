---
title: 直接路由 - 连接模拟设备
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
description: 阅读本文，了解如何将模拟设备与 Microsoft Phone 系统直接路由一同使用。
ms.openlocfilehash: 855bf0dd21659c43037b6171f523983d67c4e755
ms.sourcegitcommit: 1889ca28b9cb952b13c84efa3588957a327f9702
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841483"
---
# <a name="how-to-use-analog-devices-with-phone-system-direct-routing"></a><span data-ttu-id="1c6ad-103">如何将模拟设备与电话系统直接路由一同使用</span><span class="sxs-lookup"><span data-stu-id="1c6ad-103">How to use analog devices with Phone System Direct Routing</span></span>

<span data-ttu-id="1c6ad-104">本文介绍如何将模拟设备与电话系统直接路由一同使用。</span><span class="sxs-lookup"><span data-stu-id="1c6ad-104">This article describes how to use analog devices with Phone System Direct Routing.</span></span> <span data-ttu-id="1c6ad-105">若要将模拟设备连接到直接路由，必须使用模拟电话适配器 (ATA) ，并且此适配器必须受经过认证的会话边界控制器 (SBC) 供应商的支持。</span><span class="sxs-lookup"><span data-stu-id="1c6ad-105">To connect analog devices to Direct Routing, you must use an Analog Telephony Adapter (ATA), and this adapter must be supported by the certified Session Border Controller (SBC) vendor.</span></span> 

<span data-ttu-id="1c6ad-106">当用户从模拟设备发出呼叫时，信号和媒体会流经 ATA (ATA) SBC。</span><span class="sxs-lookup"><span data-stu-id="1c6ad-106">When a user makes a call from an analog device, the signaling and media flow through the Analog Telephony Adapter (ATA) to the SBC.</span></span>  <span data-ttu-id="1c6ad-107">SBC 根据内部路由表将呼叫发送到 Microsoft Teams 终结点 (公用电话交换网) PSTN。</span><span class="sxs-lookup"><span data-stu-id="1c6ad-107">The SBC sends the call to a Microsoft Teams endpoint or to the Public Switched Telephone Network (PSTN) based on the internal routing table.</span></span>  <span data-ttu-id="1c6ad-108">当设备进行调用时，它采用路由取决于为设备创建的路由策略。</span><span class="sxs-lookup"><span data-stu-id="1c6ad-108">When a device makes a call, the route it takes depends on the routing policies created for the device.</span></span>

<span data-ttu-id="1c6ad-109">下图中配置了直接路由，以便任何 Teams 调用 +1425 4XX XX XX 和 +1425 5XX 之间的号码时，都必须使用红色路由 (虚线) ， 与 +1425 4XX XX XX 和除号码范围 +1425 5XX XX XX 以外的任何其他号码之间的任何 PSTN 呼叫都必须使用蓝色路线 (实线) 。</span><span class="sxs-lookup"><span data-stu-id="1c6ad-109">In the following diagram, Direct Routing is configured so that any Teams calls to and from the numbers between +1425 4XX XX XX and +1425 5XX XX XX must take the red route (dotted line), and any PSTN call to and from numbers between +1425 4XX XX XX and any other number except number range +1425 5XX XX XX must take the blue route (solid line).</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="1c6ad-110">![显示直接路由配置的示意图](media/direct-routing-analog-device.png)</span><span class="sxs-lookup"><span data-stu-id="1c6ad-110">![Diagram showing Direct Routing configuration](media/direct-routing-analog-device.png)</span></span>

## <a name="example--how-to-configure-the-use-of-analog-devices-with-direct-routing"></a><span data-ttu-id="1c6ad-111">示例：如何在直接路由中配置模拟设备的使用</span><span class="sxs-lookup"><span data-stu-id="1c6ad-111">Example:  How to configure the use of analog devices with Direct Routing</span></span>

<span data-ttu-id="1c6ad-112">若要通过直接路由配置模拟设备的使用，必须将模拟电话适配器连接到 SBC，并配置 SBC 以使用直接路由。</span><span class="sxs-lookup"><span data-stu-id="1c6ad-112">To configure the use of analog devices with Direct Routing, you must connect the Analog Telephony Adapter to the SBC, and configure the SBC to work with Direct Routing.</span></span> 

<span data-ttu-id="1c6ad-113">此示例指导完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="1c6ad-113">This example walks you through the following steps:</span></span>

1. <span data-ttu-id="1c6ad-114">将 SBC 连接到直接路由。</span><span class="sxs-lookup"><span data-stu-id="1c6ad-114">Connect the SBC to Direct Routing.</span></span>
2. <span data-ttu-id="1c6ad-115">创建 PSTN 使用情况。</span><span class="sxs-lookup"><span data-stu-id="1c6ad-115">Create the PSTN Usage.</span></span>
3. <span data-ttu-id="1c6ad-116">创建语音路由并将其与 PSTN 使用情况关联。</span><span class="sxs-lookup"><span data-stu-id="1c6ad-116">Create a voice route and associate it with the PSTN Usage.</span></span>
4. <span data-ttu-id="1c6ad-117">将语音路由分配给 PSTN 使用情况。</span><span class="sxs-lookup"><span data-stu-id="1c6ad-117">Assign the voice route to the PSTN Usage.</span></span>
5. <span data-ttu-id="1c6ad-118">启用联机用户。</span><span class="sxs-lookup"><span data-stu-id="1c6ad-118">Enable the online user.</span></span>
6. <span data-ttu-id="1c6ad-119">将语音路由策略分配给用户。</span><span class="sxs-lookup"><span data-stu-id="1c6ad-119">Assign the voice route policy to the user.</span></span>
7. <span data-ttu-id="1c6ad-120">为模拟设备创建语音路由。</span><span class="sxs-lookup"><span data-stu-id="1c6ad-120">Create a voice route for an analog device.</span></span>

<span data-ttu-id="1c6ad-121">若要了解如何将 ATA 连接到 SBC 并配置 SBC，请参阅 SBC 制造商配置指南：</span><span class="sxs-lookup"><span data-stu-id="1c6ad-121">For information on how to connect an ATA to an SBC and configure the SBC, see your SBC manufacturer configuration guide:</span></span>

- [<span data-ttu-id="1c6ad-122">AudioCodes 配置文档</span><span class="sxs-lookup"><span data-stu-id="1c6ad-122">AudioCodes configuration documentation</span></span>](https://www.audiocodes.com/media/14278/connecting-audiocodes-sbc-with-analog-device-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf)

- [<span data-ttu-id="1c6ad-123">功能区配置文档</span><span class="sxs-lookup"><span data-stu-id="1c6ad-123">Ribbon configuration documentation</span></span>](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)
- [<span data-ttu-id="1c6ad-124">Oracle 配置文档</span><span class="sxs-lookup"><span data-stu-id="1c6ad-124">Oracle configuration documentation</span></span>](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams)

## <a name="step-1--connect-the-sbc-to-direct-routing"></a><span data-ttu-id="1c6ad-125">第 1 步</span><span class="sxs-lookup"><span data-stu-id="1c6ad-125">Step 1.</span></span>  <span data-ttu-id="1c6ad-126">将 SBC 连接到直接路由</span><span class="sxs-lookup"><span data-stu-id="1c6ad-126">Connect the SBC to Direct Routing</span></span>

<span data-ttu-id="1c6ad-127">以下命令按如下所示配置 SBC 连接：</span><span class="sxs-lookup"><span data-stu-id="1c6ad-127">The following command configures the SBC connection as follows:</span></span>

- <span data-ttu-id="1c6ad-128">FQDN sbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1c6ad-128">FQDN sbc.contoso.com</span></span>
- <span data-ttu-id="1c6ad-129">信令端口 5068</span><span class="sxs-lookup"><span data-stu-id="1c6ad-129">Signaling port 5068</span></span>
- <span data-ttu-id="1c6ad-130">媒体旁路模式</span><span class="sxs-lookup"><span data-stu-id="1c6ad-130">Media bypass mode</span></span>
- <span data-ttu-id="1c6ad-131">已转发到 SBC 的呼叫历史记录信息-</span><span class="sxs-lookup"><span data-stu-id="1c6ad-131">Call history information forwarded to the SBC-</span></span>
- <span data-ttu-id="1c6ad-132">P-Asserted-Identity (PAI) 标头随调用一起转发</span><span class="sxs-lookup"><span data-stu-id="1c6ad-132">P-Asserted-Identity (PAI) header forwarded along with the call</span></span> 

```powershell
PS C:\> New-CsOnlinePSTNGateway -FQDN sbc.contoso.com -SIPSignalingPort 5068 -ForwardCallHistory $true -ForwardPAI $true -MediaBypass $true -Enabled $true 
```

## <a name="step-2--create-the-pstn-usage"></a><span data-ttu-id="1c6ad-133">步骤 2：创建 PSTN 使用情况</span><span class="sxs-lookup"><span data-stu-id="1c6ad-133">Step 2:  Create the PSTN usage</span></span> 

<span data-ttu-id="1c6ad-134">下一个命令将创建一个空的 PSTN 使用情况。</span><span class="sxs-lookup"><span data-stu-id="1c6ad-134">The next command creates an empty PSTN usage.</span></span> <span data-ttu-id="1c6ad-135">联机 PSTN 使用情况是用于呼叫授权的字符串值。</span><span class="sxs-lookup"><span data-stu-id="1c6ad-135">Online PSTN usages are string values that are used for call authorization.</span></span> <span data-ttu-id="1c6ad-136">联机 PSTN 使用将联机语音策略链接到路由。</span><span class="sxs-lookup"><span data-stu-id="1c6ad-136">An online PSTN usage links an online voice policy to a route.</span></span> <span data-ttu-id="1c6ad-137">此示例将字符串"互操作"添加到可用 PSTN 使用情况的当前列表。</span><span class="sxs-lookup"><span data-stu-id="1c6ad-137">This example adds the string "Interop" to the current list of available PSTN usages.</span></span> 

```powershell
PS C:\> Set-CsOnlinePstnUsage -Identity global -Usage @{add="Interop"} 
```

## <a name="step-3--create-a-voice-route-and-associate-it-with-the-pstn-usage"></a><span data-ttu-id="1c6ad-138">步骤 3：创建语音路由并将其与 PSTN 使用情况关联：</span><span class="sxs-lookup"><span data-stu-id="1c6ad-138">Step 3:  Create a voice route and associate it with the PSTN usage:</span></span>

<span data-ttu-id="1c6ad-139">此命令为数字范围 +1425 XXX XX XX 创建标识为"analog-interop"的新在线语音路由。</span><span class="sxs-lookup"><span data-stu-id="1c6ad-139">This command creates a new online voice route with the identity “analog-interop” for the number range +1425 XXX XX XX.</span></span>  <span data-ttu-id="1c6ad-140">语音路由适用于联机网关列表sbc.contoso.com将路由与在线 PSTN 使用情况"互操作"关联。</span><span class="sxs-lookup"><span data-stu-id="1c6ad-140">The voice route is applicable to a list of online gateways sbc.contoso.com and associates the route with online PSTN usage “Interop”.</span></span> <span data-ttu-id="1c6ad-141">语音路由包括一个正则表达式，用于标识将通过给定语音路由路由的电话号码：</span><span class="sxs-lookup"><span data-stu-id="1c6ad-141">A voice route includes a regular expression that identifies which phone numbers will be routed through a given voice route:</span></span>

```powershell
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(425)(\d{7}])$" -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "Interop"
```

## <a name="step-4-assign-the-voice-route-to-the-pstn-usage"></a><span data-ttu-id="1c6ad-142">步骤 4：将语音路由分配给 PSTN 使用情况：</span><span class="sxs-lookup"><span data-stu-id="1c6ad-142">Step 4: Assign the voice route to the PSTN usage:</span></span>

<span data-ttu-id="1c6ad-143">此命令使用标识"AnalogInteropPolicy"创建新的基于用户的联机语音路由策略。</span><span class="sxs-lookup"><span data-stu-id="1c6ad-143">This command creates a new online per-user voice routing policy with the Identity “AnalogInteropPolicy”.</span></span> <span data-ttu-id="1c6ad-144">此策略分配有单个联机 PSTN 用法："互操作"。</span><span class="sxs-lookup"><span data-stu-id="1c6ad-144">This policy is assigned a single online PSTN usage: “Interop”.</span></span>

```powershell
PS C:\> New-CsOnlineVoiceRoutingPolicy -Identity "AnalogInteropPolicy" -Name "AnalogInteropPolicy" -OnlinePstnUsages "Interop"
```

## <a name="step-5-enable-the-online-user"></a><span data-ttu-id="1c6ad-145">步骤 5：启用联机用户</span><span class="sxs-lookup"><span data-stu-id="1c6ad-145">Step 5: Enable the online user</span></span>

<span data-ttu-id="1c6ad-146">此命令使用标识服务修改exampleuser@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="1c6ad-146">This command modifies the user account with the Identity exampleuser@contoso.com.</span></span> <span data-ttu-id="1c6ad-147">在这种情况下，将修改帐户以启用 企业语音（启用语音邮件的 Microsoft VoIP 实现）并将号码 +14255000000 分配给此用户。</span><span class="sxs-lookup"><span data-stu-id="1c6ad-147">In this case, the account is modified to enable Enterprise Voice, the Microsoft implementation of VoIP, with enabled voice mail and assigns the number +14255000000 to this user.</span></span>  <span data-ttu-id="1c6ad-148">应针对每个 Teams 用户运行此命令 (公司租户中的 ATA) 用户除外。</span><span class="sxs-lookup"><span data-stu-id="1c6ad-148">This command should be run for each Teams user (excluding ATA device users) in the company tenant.</span></span>

```powershell
PS C:\> Set-CsUser -Identity "exampleuser@contoso.com" -EnterpriseVoiceEnabled $True -HostedVoiceMail $True -OnPremLineUri "tel:+14255000000"
```

## <a name="step-6-assign-the-voice-route-policy-to-a-user"></a><span data-ttu-id="1c6ad-149">步骤 6：将语音路由策略分配给用户</span><span class="sxs-lookup"><span data-stu-id="1c6ad-149">Step 6: Assign the voice route policy to a user</span></span>

<span data-ttu-id="1c6ad-150">此命令将按用户在线语音路由策略 AnalogInteropPolicy 分配给标识为 exampleuser@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="1c6ad-150">This command assigns the per-user online voice routing policy AnalogInteropPolicy to the user with the identity exampleuser@contoso.com.</span></span>  <span data-ttu-id="1c6ad-151">应针对每个 Teams 用户运行此命令 (公司租户中的 ATA) 用户除外。</span><span class="sxs-lookup"><span data-stu-id="1c6ad-151">This command should be run for each Teams user (excluding ATA device users) in the company tenant.</span></span>

```powershell
PS C:\> Grant-CsOnlineVoiceRoutingPolicy -Identity "exampleuser@contoso.com" -PolicyName "AnalogInteropPolicy" 
```

## <a name="step-7--create-a-voice-route-for-an-analog-device"></a><span data-ttu-id="1c6ad-152">步骤 7：为模拟设备创建语音路由</span><span class="sxs-lookup"><span data-stu-id="1c6ad-152">Step 7:  Create a voice route for an analog device</span></span>

<span data-ttu-id="1c6ad-153">此命令为适用于联机网关列表的编号范围 +1425 4XX XX XX 创建标识为"模拟互操作"的联机语音路由sbc.contoso.com并关联到联机 PSTN 使用情况"互操作"。</span><span class="sxs-lookup"><span data-stu-id="1c6ad-153">This command creates an online voice route with identity “analog-interop” for number range +1425 4XX XX XX applicable to a list of online gateways sbc.contoso.com and associates it with online PSTN usage “Interop”.</span></span>  <span data-ttu-id="1c6ad-154">此命令应该针对具有适当电话号码模式的每个模拟设备运行。</span><span class="sxs-lookup"><span data-stu-id="1c6ad-154">This command should be run for each analog device with appropriate phone number pattern.</span></span> <span data-ttu-id="1c6ad-155">或者，在之前的步骤之一中配置联机语音路由时，可以使用适当的模拟设备数字模式。</span><span class="sxs-lookup"><span data-stu-id="1c6ad-155">Alternatively, a proper number pattern for analog devices can be used while configuring the online voice route during one of the previous steps.</span></span>

```powershell
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(4254)(\d{6}])$"  -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "Interop"
```

## <a name="considerations"></a><span data-ttu-id="1c6ad-156">注意事项</span><span class="sxs-lookup"><span data-stu-id="1c6ad-156">Considerations</span></span>

- <span data-ttu-id="1c6ad-157">除非另有说明，否则模拟设备是可发送 DTMF 数字以发出呼叫的任何设备。</span><span class="sxs-lookup"><span data-stu-id="1c6ad-157">Unless otherwise note, an analog device is any device that can send DTMF digits to place a call.</span></span> <span data-ttu-id="1c6ad-158">例如，模拟电话、传真机和开销寻呼机。</span><span class="sxs-lookup"><span data-stu-id="1c6ad-158">For example, analog phones, fax machines, and overhead pagers.</span></span>

- <span data-ttu-id="1c6ad-159">连接到 ATA 的模拟电话不可从 Teams 搜索。</span><span class="sxs-lookup"><span data-stu-id="1c6ad-159">Analog phones connected to an ATA are not searchable from Teams.</span></span> <span data-ttu-id="1c6ad-160">Teams 用户必须手动输入与设备关联的电话号码才能呼叫该设备。</span><span class="sxs-lookup"><span data-stu-id="1c6ad-160">Teams users must manually enter the phone number associated with the device to call that device.</span></span>  
 

## <a name="see-also"></a><span data-ttu-id="1c6ad-161">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1c6ad-161">See also</span></span>

[<span data-ttu-id="1c6ad-162">规划直接路由</span><span class="sxs-lookup"><span data-stu-id="1c6ad-162">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="1c6ad-163">配置直接路由</span><span class="sxs-lookup"><span data-stu-id="1c6ad-163">Configure Direct Routing</span></span>](direct-routing-configure.md)
