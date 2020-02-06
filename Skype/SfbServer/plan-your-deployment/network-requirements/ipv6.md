---
title: 规划 Skype for Business 中的 IPv6
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 01f77196-38f4-4292-9480-2e2fbd57eabe
description: 摘要：安装 Skype for Business 服务器之前，请先实施 IPv6。
ms.openlocfilehash: 5fe8cd186d152d368ac89c1d6bc9c07cebb7bfe7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802072"
---
# <a name="plan-for-ipv6-in-skype-for-business"></a><span data-ttu-id="0428f-103">规划 Skype for Business 中的 IPv6</span><span class="sxs-lookup"><span data-stu-id="0428f-103">Plan for IPv6 in Skype for Business</span></span>
 
<span data-ttu-id="0428f-104">**摘要：** 在安装 Skype for Business 服务器之前实施 IPv6。</span><span class="sxs-lookup"><span data-stu-id="0428f-104">**Summary:** Implement IPv6 before you install Skype for Business Server.</span></span>
  
<span data-ttu-id="0428f-105">Skype for business 服务器包括对 ip 版本6（IPv6）地址的支持，以及对 IP 版本4（IPv4）地址的连续支持。</span><span class="sxs-lookup"><span data-stu-id="0428f-105">Skype for Business Server includes support for IP version 6 (IPv6) addresses, along with continued support of IP version 4 (IPv4) addresses.</span></span> 

<span data-ttu-id="0428f-106">IPv4 地址是 32 位地址，允许计算机通过 Internet 进行通信。</span><span class="sxs-lookup"><span data-stu-id="0428f-106">IPv4 addresses are 32-bit addresses that allow a computer to communicate over the Internet.</span></span> <span data-ttu-id="0428f-107">由于世界各地的设备数量不断增加，可用的 IPv4 地址已用尽。因此，许多新设备将移动到使用 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="0428f-107">Due to the increasing number of devices worldwide, the available IPv4 addresses have run out. Because of this, many new devices are moving to using IPv6 addresses.</span></span> <span data-ttu-id="0428f-108">IPv6 地址执行与 IPv4 地址相同的功能（并另外增加了一些功能），只不过 IPv6 地址不是使用 32 位，而是使用 128 位。</span><span class="sxs-lookup"><span data-stu-id="0428f-108">IPv6 addresses perform the same function as IPv4 addresses (with some additional features), but instead of using only 32-bits, IPv6 addresses use 128-bits.</span></span> <span data-ttu-id="0428f-109">这不仅提供了一组新的地址，而且数量远远超过原来的地址集。</span><span class="sxs-lookup"><span data-stu-id="0428f-109">This provides not only a new set of addresses, but also a much larger number of them.</span></span> 

<span data-ttu-id="0428f-110">传统 IPv4 地址看起来类似于：192.0.2.235，而 IPv6 地址看起来类似于：2001:0db8:85a3:0000:0000:8a2e:0370:7334。</span><span class="sxs-lookup"><span data-stu-id="0428f-110">A typical IPv4 address looks something like this: 192.0.2.235, whereas an IPv6 address looks like this: 2001:0db8:85a3:0000:0000:8a2e:0370:7334.</span></span> <span data-ttu-id="0428f-111">对于使用 IPv6 地址的设备的格式设置和功能的更改，需要在 Skype for Business 服务器安装中执行一些部署和配置注意事项。</span><span class="sxs-lookup"><span data-stu-id="0428f-111">The change in formatting and functionality for devices that use IPv6 addresses requires several deployment and configuration considerations in your Skype for Business Server installation.</span></span> 

<span data-ttu-id="0428f-112">本主题包括以下部分：</span><span class="sxs-lookup"><span data-stu-id="0428f-112">This topic includes the following sections:</span></span>
  
- [<span data-ttu-id="0428f-113">Overview of IP address types</span><span class="sxs-lookup"><span data-stu-id="0428f-113">Overview of IP address types</span></span>](ipv6.md#over)
    
- [<span data-ttu-id="0428f-114">Technical requirements for IPv6</span><span class="sxs-lookup"><span data-stu-id="0428f-114">Technical requirements for IPv6</span></span>](ipv6.md#tech)
    
- [<span data-ttu-id="0428f-115">Migration and coexistence considerations for IPv6</span><span class="sxs-lookup"><span data-stu-id="0428f-115">Migration and coexistence considerations for IPv6</span></span>](ipv6.md#migration)
    
<span data-ttu-id="0428f-116">如果确定你将使用 IPv6 地址，请参阅[Skype For business 文章中的 "配置 IP 地址类型](ip-address-types.md)"。</span><span class="sxs-lookup"><span data-stu-id="0428f-116">If you determine you will be using IPv6 addresses, refer to the [Configure IP address types in Skype for Business](ip-address-types.md) article.</span></span>
  
## <a name="overview-of-ip-address-types"></a><span data-ttu-id="0428f-117">IP 地址类型概述</span><span class="sxs-lookup"><span data-stu-id="0428f-117">Overview of IP address types</span></span>
<span data-ttu-id="0428f-118"><a name="over"> </a></span><span class="sxs-lookup"><span data-stu-id="0428f-118"><a name="over"> </a></span></span>

<span data-ttu-id="0428f-119">在 Skype for Business 服务器中配置 IP 地址时，有三个选项。</span><span class="sxs-lookup"><span data-stu-id="0428f-119">You have three options when configuring IP addresses in Skype for Business Server.</span></span> <span data-ttu-id="0428f-120">你可以将 Skype for business 服务器配置为仅支持 IP 版本4（IPv4）、仅限 IP 版本6（IPv6）或二者（称为双重堆栈）的组合。</span><span class="sxs-lookup"><span data-stu-id="0428f-120">You can configure Skype for Business Server to support only IP version 4 (IPv4), only IP version 6 (IPv6), or a combination of both (known as a dual stack).</span></span> <span data-ttu-id="0428f-121">对于每种类型的配置，都需要考虑一些问题：</span><span class="sxs-lookup"><span data-stu-id="0428f-121">There are several issues to consider with each type of configuration:</span></span>
  
- <span data-ttu-id="0428f-122">**仅限 IPv4**由于全球 IPv4 地址不足，因此已创建 IPv6。</span><span class="sxs-lookup"><span data-stu-id="0428f-122">**IPv4 only** IPv6 was created because the world is running out of IPv4 addresses.</span></span> <span data-ttu-id="0428f-123">最终，IPv6 将在全球范围内获得全面支持，但就目前而言，您的企业需要与之通信的很多公司和设备可能尚不支持 IPv6，并且在一段时间内可能也不会提供相应支持。</span><span class="sxs-lookup"><span data-stu-id="0428f-123">Ultimately, IPv6 will be fully supported worldwide, but at this time, many companies and devices that your enterprise might need to communicate with do not yet support IPv6, and may not for some time.</span></span> <span data-ttu-id="0428f-124">仅 IPv4 配置将有助于确保 Skype for Business 服务器实现可以与大多数现有设备进行通信。</span><span class="sxs-lookup"><span data-stu-id="0428f-124">An IPv4-only configuration will help to ensure that your Skype for Business Server implementation can communicate with most existing devices.</span></span>
    
- <span data-ttu-id="0428f-125">**仅限 IPv6**相反，完整的 IPv6 实现将排除与许多现有设备的通信。</span><span class="sxs-lookup"><span data-stu-id="0428f-125">**IPv6 only** Conversely, a full IPv6 implementation will exclude communication with many existing devices.</span></span>
    
- <span data-ttu-id="0428f-126">**双栈**双堆栈是启用 IPv4 和 IPv6 地址的网络。</span><span class="sxs-lookup"><span data-stu-id="0428f-126">**Dual Stack** Dual stack is a network where both IPv4 and IPv6 addresses are enabled.</span></span> <span data-ttu-id="0428f-127">Skype for Business Server 支持此配置，因为在大多数情况下，从完整 IPv4 到完整 IPv6 的转换将需要几年。</span><span class="sxs-lookup"><span data-stu-id="0428f-127">This configuration is supported in Skype for Business Server because in most cases the transition from full-IPv4 to full-IPv6 will take several years.</span></span>
    
<span data-ttu-id="0428f-128">以下部分概述了各种 Skype for Business 服务器功能的这三种配置之间的兼容性。</span><span class="sxs-lookup"><span data-stu-id="0428f-128">The following sections outline the compatibility among these three configurations for various Skype for Business Server features.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0428f-p106">仅 IPv6 的客户端或服务器配置只受选项卡或验证的支持。仅 IPv6 配置在生产部署中不受支持。</span><span class="sxs-lookup"><span data-stu-id="0428f-p106">Client or server configuration with IPv6 only is supported only for lab or validation purposes. IPv6 only configuration is not supported in the production deployment.</span></span> 
  
### <a name="client-registration"></a><span data-ttu-id="0428f-131">客户端注册</span><span class="sxs-lookup"><span data-stu-id="0428f-131">Client Registration</span></span>
<span data-ttu-id="0428f-132"><a name="client"> </a></span><span class="sxs-lookup"><span data-stu-id="0428f-132"><a name="client"> </a></span></span>

|<span data-ttu-id="0428f-133">**客户端终结点网络**</span><span class="sxs-lookup"><span data-stu-id="0428f-133">**Client endpoint network**</span></span>|<span data-ttu-id="0428f-134">**服务器网络**</span><span class="sxs-lookup"><span data-stu-id="0428f-134">**Server network**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0428f-135">IPv4</span><span class="sxs-lookup"><span data-stu-id="0428f-135">IPv4</span></span>  <br/> |<span data-ttu-id="0428f-136">IPv4</span><span class="sxs-lookup"><span data-stu-id="0428f-136">IPv4</span></span>  <br/> |
|<span data-ttu-id="0428f-137">IPv4</span><span class="sxs-lookup"><span data-stu-id="0428f-137">IPv4</span></span>  <br/> |<span data-ttu-id="0428f-138">双协议栈</span><span class="sxs-lookup"><span data-stu-id="0428f-138">Dual stack</span></span>  <br/> |
|<span data-ttu-id="0428f-139">双协议栈</span><span class="sxs-lookup"><span data-stu-id="0428f-139">Dual stack</span></span>  <br/> |<span data-ttu-id="0428f-140">IPv4</span><span class="sxs-lookup"><span data-stu-id="0428f-140">IPv4</span></span>  <br/> |
|<span data-ttu-id="0428f-141">双协议栈</span><span class="sxs-lookup"><span data-stu-id="0428f-141">Dual stack</span></span>  <br/> |<span data-ttu-id="0428f-142">双协议栈</span><span class="sxs-lookup"><span data-stu-id="0428f-142">Dual stack</span></span>  <br/> |
|<span data-ttu-id="0428f-143">双协议栈</span><span class="sxs-lookup"><span data-stu-id="0428f-143">Dual stack</span></span>  <br/> |<span data-ttu-id="0428f-144">IPv6</span><span class="sxs-lookup"><span data-stu-id="0428f-144">IPv6</span></span>  <br/> |
|<span data-ttu-id="0428f-145">IPv6</span><span class="sxs-lookup"><span data-stu-id="0428f-145">IPv6</span></span>  <br/> |<span data-ttu-id="0428f-146">双协议栈</span><span class="sxs-lookup"><span data-stu-id="0428f-146">Dual stack</span></span>  <br/> |
|<span data-ttu-id="0428f-147">IPv6</span><span class="sxs-lookup"><span data-stu-id="0428f-147">IPv6</span></span>  <br/> |<span data-ttu-id="0428f-148">IPv6</span><span class="sxs-lookup"><span data-stu-id="0428f-148">IPv6</span></span>  <br/> |
   
### <a name="peer-to-peer-client"></a><span data-ttu-id="0428f-149">对等客户端</span><span class="sxs-lookup"><span data-stu-id="0428f-149">Peer-to-Peer Client</span></span>
<span data-ttu-id="0428f-150"><a name="peer"> </a></span><span class="sxs-lookup"><span data-stu-id="0428f-150"><a name="peer"> </a></span></span>

<span data-ttu-id="0428f-151">对等通信包括音频、音频/视频、应用程序共享和文件传输。</span><span class="sxs-lookup"><span data-stu-id="0428f-151">Peer-to-peer communications include audio, audio/video, application sharing, and file transfer.</span></span> <span data-ttu-id="0428f-152">两个客户端均注册成功后，将支持以下组合。</span><span class="sxs-lookup"><span data-stu-id="0428f-152">After both clients have successfully registered, the following combinations are supported.</span></span>
  
|<span data-ttu-id="0428f-153">**客户端终结点 1**</span><span class="sxs-lookup"><span data-stu-id="0428f-153">**Client endpoint 1**</span></span>|<span data-ttu-id="0428f-154">**客户端终结点 2**</span><span class="sxs-lookup"><span data-stu-id="0428f-154">**Client endpoint 2**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0428f-155">IPv4</span><span class="sxs-lookup"><span data-stu-id="0428f-155">IPv4</span></span>  <br/> |<span data-ttu-id="0428f-156">IPv4</span><span class="sxs-lookup"><span data-stu-id="0428f-156">IPv4</span></span>  <br/> |
|<span data-ttu-id="0428f-157">IPv4</span><span class="sxs-lookup"><span data-stu-id="0428f-157">IPv4</span></span>  <br/> |<span data-ttu-id="0428f-158">双协议栈</span><span class="sxs-lookup"><span data-stu-id="0428f-158">Dual stack</span></span>  <br/> |
|<span data-ttu-id="0428f-159">双协议栈</span><span class="sxs-lookup"><span data-stu-id="0428f-159">Dual stack</span></span>  <br/> |<span data-ttu-id="0428f-160">双协议栈</span><span class="sxs-lookup"><span data-stu-id="0428f-160">Dual stack</span></span>  <br/> |
|<span data-ttu-id="0428f-161">IPv6</span><span class="sxs-lookup"><span data-stu-id="0428f-161">IPv6</span></span>  <br/> |<span data-ttu-id="0428f-162">双协议栈</span><span class="sxs-lookup"><span data-stu-id="0428f-162">Dual stack</span></span>  <br/> |
|<span data-ttu-id="0428f-163">IPv6</span><span class="sxs-lookup"><span data-stu-id="0428f-163">IPv6</span></span>  <br/> |<span data-ttu-id="0428f-164">IPv6</span><span class="sxs-lookup"><span data-stu-id="0428f-164">IPv6</span></span>  <br/> |
   
### <a name="conferencing"></a><span data-ttu-id="0428f-165">会议</span><span class="sxs-lookup"><span data-stu-id="0428f-165">Conferencing</span></span>
<span data-ttu-id="0428f-166"><a name="conf"> </a></span><span class="sxs-lookup"><span data-stu-id="0428f-166"><a name="conf"> </a></span></span>

<span data-ttu-id="0428f-167">会议包括音频/视频、应用程序共享和数据协作应用程序（比如白板和文件共享）。</span><span class="sxs-lookup"><span data-stu-id="0428f-167">Conferencing includes audio/video, application sharing, and data collaboration applications like whiteboarding and file sharing.</span></span>
  
|<span data-ttu-id="0428f-168">**客户端终结点网络**</span><span class="sxs-lookup"><span data-stu-id="0428f-168">**Client endpoint network**</span></span>|<span data-ttu-id="0428f-169">**服务器网络**</span><span class="sxs-lookup"><span data-stu-id="0428f-169">**Server network**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0428f-170">IPv4</span><span class="sxs-lookup"><span data-stu-id="0428f-170">IPv4</span></span>  <br/> |<span data-ttu-id="0428f-171">IPv4</span><span class="sxs-lookup"><span data-stu-id="0428f-171">IPv4</span></span>  <br/> |
|<span data-ttu-id="0428f-172">IPv4</span><span class="sxs-lookup"><span data-stu-id="0428f-172">IPv4</span></span>  <br/> |<span data-ttu-id="0428f-173">双协议栈</span><span class="sxs-lookup"><span data-stu-id="0428f-173">Dual stack</span></span>  <br/> |
|<span data-ttu-id="0428f-174">双协议栈</span><span class="sxs-lookup"><span data-stu-id="0428f-174">Dual stack</span></span>  <br/> |<span data-ttu-id="0428f-175">IPv4</span><span class="sxs-lookup"><span data-stu-id="0428f-175">IPv4</span></span>  <br/> |
|<span data-ttu-id="0428f-176">双协议栈</span><span class="sxs-lookup"><span data-stu-id="0428f-176">Dual stack</span></span>  <br/> |<span data-ttu-id="0428f-177">双协议栈</span><span class="sxs-lookup"><span data-stu-id="0428f-177">Dual stack</span></span>  <br/> |
|<span data-ttu-id="0428f-178">双协议栈</span><span class="sxs-lookup"><span data-stu-id="0428f-178">Dual stack</span></span>  <br/> |<span data-ttu-id="0428f-179">IPv6</span><span class="sxs-lookup"><span data-stu-id="0428f-179">IPv6</span></span>  <br/> |
|<span data-ttu-id="0428f-180">IPv6</span><span class="sxs-lookup"><span data-stu-id="0428f-180">IPv6</span></span>  <br/> |<span data-ttu-id="0428f-181">双协议栈</span><span class="sxs-lookup"><span data-stu-id="0428f-181">Dual stack</span></span>  <br/> |
|<span data-ttu-id="0428f-182">IPv6</span><span class="sxs-lookup"><span data-stu-id="0428f-182">IPv6</span></span>  <br/> |<span data-ttu-id="0428f-183">IPv6</span><span class="sxs-lookup"><span data-stu-id="0428f-183">IPv6</span></span>  <br/> |
   
### <a name="mediation-serverpstn"></a><span data-ttu-id="0428f-184">中介服务器/PSTN</span><span class="sxs-lookup"><span data-stu-id="0428f-184">Mediation Server/PSTN</span></span>
<span data-ttu-id="0428f-185"><a name="med"> </a></span><span class="sxs-lookup"><span data-stu-id="0428f-185"><a name="med"> </a></span></span>

<span data-ttu-id="0428f-186">如果流量通过 IPv6 接口，则 Skype for business 服务器不支持公共交换电话网络（PSTN）呼叫的媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="0428f-186">Skype for Business Server does not support media bypass for public switched telephone network (PSTN) calls if the traffic is through an IPv6 interface.</span></span> <span data-ttu-id="0428f-187">如果需要媒体旁路，则我们建议将 PSTN 网关配置为 IPv4。</span><span class="sxs-lookup"><span data-stu-id="0428f-187">If media bypass is required, we recommend that the PSTN gateway is configured to IPv4.</span></span> 
  
|<span data-ttu-id="0428f-188">**主接口1**</span><span class="sxs-lookup"><span data-stu-id="0428f-188">**Primary interface 1**</span></span>|<span data-ttu-id="0428f-189">**PSTN 接口（位于中介服务器上）**</span><span class="sxs-lookup"><span data-stu-id="0428f-189">**PSTN interface (on Mediation Server)**</span></span>|<span data-ttu-id="0428f-190">**PSTN 网关设置**</span><span class="sxs-lookup"><span data-stu-id="0428f-190">**PSTN gateway setting**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0428f-191">IPv4</span><span class="sxs-lookup"><span data-stu-id="0428f-191">IPv4</span></span>  <br/> |<span data-ttu-id="0428f-192">双协议栈</span><span class="sxs-lookup"><span data-stu-id="0428f-192">Dual stack</span></span>  <br/> |<span data-ttu-id="0428f-193">IPv4</span><span class="sxs-lookup"><span data-stu-id="0428f-193">IPv4</span></span>  <br/> |
|<span data-ttu-id="0428f-194">双协议栈</span><span class="sxs-lookup"><span data-stu-id="0428f-194">Dual stack</span></span>  <br/> |<span data-ttu-id="0428f-195">双协议栈</span><span class="sxs-lookup"><span data-stu-id="0428f-195">Dual stack</span></span>  <br/> |<span data-ttu-id="0428f-196">IPv4</span><span class="sxs-lookup"><span data-stu-id="0428f-196">IPv4</span></span>  <br/> |
|<span data-ttu-id="0428f-197">双协议栈</span><span class="sxs-lookup"><span data-stu-id="0428f-197">Dual stack</span></span>  <br/> |<span data-ttu-id="0428f-198">双协议栈</span><span class="sxs-lookup"><span data-stu-id="0428f-198">Dual stack</span></span>  <br/> |<span data-ttu-id="0428f-199">IPv6</span><span class="sxs-lookup"><span data-stu-id="0428f-199">IPv6</span></span>  <br/> |
   
1. <span data-ttu-id="0428f-200">主界面是与 Skype for Business 服务器组件进行通信的接口。</span><span class="sxs-lookup"><span data-stu-id="0428f-200">The primary interface is the interface that communicates with the Skype for Business Server components.</span></span>
  
### <a name="remote-user-peer-to-peer-communications"></a><span data-ttu-id="0428f-201">远程用户对等通信</span><span class="sxs-lookup"><span data-stu-id="0428f-201">Remote User Peer-to-Peer Communications</span></span>
<span data-ttu-id="0428f-202"><a name="remote"> </a></span><span class="sxs-lookup"><span data-stu-id="0428f-202"><a name="remote"> </a></span></span>

<span data-ttu-id="0428f-203">与远程用户的对等通信包括即时消息、音频/视频、应用程序共享和文件传输。</span><span class="sxs-lookup"><span data-stu-id="0428f-203">Peer-to-peer communications with remote users include instant messaging, audio/video, application sharing, and file transfer.</span></span>
  
|<span data-ttu-id="0428f-204">**远程用户网络**</span><span class="sxs-lookup"><span data-stu-id="0428f-204">**Remote user network**</span></span>|<span data-ttu-id="0428f-205">**边缘服务器（外部边缘）**</span><span class="sxs-lookup"><span data-stu-id="0428f-205">**Edge server (External edge)**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0428f-206">IPv4</span><span class="sxs-lookup"><span data-stu-id="0428f-206">IPv4</span></span>  <br/> |<span data-ttu-id="0428f-207">IPv4</span><span class="sxs-lookup"><span data-stu-id="0428f-207">IPv4</span></span>  <br/> |
|<span data-ttu-id="0428f-208">双协议栈</span><span class="sxs-lookup"><span data-stu-id="0428f-208">Dual stack</span></span>  <br/> |<span data-ttu-id="0428f-209">IPv4</span><span class="sxs-lookup"><span data-stu-id="0428f-209">IPv4</span></span>  <br/> |
|<span data-ttu-id="0428f-210">双协议栈</span><span class="sxs-lookup"><span data-stu-id="0428f-210">Dual stack</span></span>  <br/> |<span data-ttu-id="0428f-211">双协议栈</span><span class="sxs-lookup"><span data-stu-id="0428f-211">Dual stack</span></span>  <br/> |
|<span data-ttu-id="0428f-212">IPv6</span><span class="sxs-lookup"><span data-stu-id="0428f-212">IPv6</span></span>  <br/> |<span data-ttu-id="0428f-213">双协议栈</span><span class="sxs-lookup"><span data-stu-id="0428f-213">Dual stack</span></span>  <br/> |
|<span data-ttu-id="0428f-214">IPv6</span><span class="sxs-lookup"><span data-stu-id="0428f-214">IPv6</span></span>  <br/> |<span data-ttu-id="0428f-215">IPv6</span><span class="sxs-lookup"><span data-stu-id="0428f-215">IPv6</span></span>  <br/> |
   
### <a name="front-end-pool-and-edge-pool-configuration"></a><span data-ttu-id="0428f-216">前端池和边缘池配置</span><span class="sxs-lookup"><span data-stu-id="0428f-216">Front End Pool and Edge Pool Configuration</span></span>
<span data-ttu-id="0428f-217"><a name="FE_pool"> </a></span><span class="sxs-lookup"><span data-stu-id="0428f-217"><a name="FE_pool"> </a></span></span>

<span data-ttu-id="0428f-218">下表显示了前端服务器池和内部边缘服务器池之间的支持列表。</span><span class="sxs-lookup"><span data-stu-id="0428f-218">The following table shows the support matrix between the Front End Server pool and the internal Edge Server pool.</span></span>
  
<span data-ttu-id="0428f-219">**前端池和边缘池（内部边缘）矩阵**</span><span class="sxs-lookup"><span data-stu-id="0428f-219">**Front End Pool and Edge Pool (Internal Edge) Matrix**</span></span>

||<span data-ttu-id="0428f-220">**边缘池：IPv4**</span><span class="sxs-lookup"><span data-stu-id="0428f-220">**Edge Pool: IPv4**</span></span> <br/> |<span data-ttu-id="0428f-221">**边缘池：双协议栈**</span><span class="sxs-lookup"><span data-stu-id="0428f-221">**Edge Pool: Dual Stack**</span></span> <br/> |<span data-ttu-id="0428f-222">**边缘池：IPv6**</span><span class="sxs-lookup"><span data-stu-id="0428f-222">**Edge Pool: IPv6**</span></span> <br/> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0428f-223">**前端池：IPv4**</span><span class="sxs-lookup"><span data-stu-id="0428f-223">**Front End Pool: IPv4**</span></span> <br/> |<span data-ttu-id="0428f-224">必需</span><span class="sxs-lookup"><span data-stu-id="0428f-224">Yes</span></span>  <br/> |<span data-ttu-id="0428f-225">是</span><span class="sxs-lookup"><span data-stu-id="0428f-225">Yes</span></span>  <br/> |<span data-ttu-id="0428f-226">否</span><span class="sxs-lookup"><span data-stu-id="0428f-226">No</span></span>  <br/> |
|<span data-ttu-id="0428f-227">**前端池：双协议栈**</span><span class="sxs-lookup"><span data-stu-id="0428f-227">**Front End Pool: Dual Stack**</span></span> <br/> |<span data-ttu-id="0428f-228">必需</span><span class="sxs-lookup"><span data-stu-id="0428f-228">Yes</span></span>  <br/> |<span data-ttu-id="0428f-229">是</span><span class="sxs-lookup"><span data-stu-id="0428f-229">Yes</span></span>  <br/> |<span data-ttu-id="0428f-230">否</span><span class="sxs-lookup"><span data-stu-id="0428f-230">No</span></span>  <br/> |
|<span data-ttu-id="0428f-231">**前端池：IPv6**</span><span class="sxs-lookup"><span data-stu-id="0428f-231">**Front End Pool: IPv6**</span></span> <br/> |<span data-ttu-id="0428f-232">否</span><span class="sxs-lookup"><span data-stu-id="0428f-232">No</span></span>  <br/> |<span data-ttu-id="0428f-233">否</span><span class="sxs-lookup"><span data-stu-id="0428f-233">No</span></span>  <br/> |<span data-ttu-id="0428f-234">是\*</span><span class="sxs-lookup"><span data-stu-id="0428f-234">Yes\*</span></span>  <br/> |
   
<span data-ttu-id="0428f-235">\*仅在实验室环境中使用此组合。</span><span class="sxs-lookup"><span data-stu-id="0428f-235">\* Use this combination only in a lab environment.</span></span>
  
<span data-ttu-id="0428f-236">下表是内部和外部边缘接口支持的组合矩阵。</span><span class="sxs-lookup"><span data-stu-id="0428f-236">The following table is a matrix of the supported combinations of internal and external edge interfaces.</span></span>
  
<span data-ttu-id="0428f-237">**边缘池（内部边缘）和边缘池（外部边缘）矩阵**</span><span class="sxs-lookup"><span data-stu-id="0428f-237">**Edge Pool (Internal Edge) and Edge pool (External Edge) Matrix**</span></span>

||<span data-ttu-id="0428f-238">**边缘池（外部边缘）：IPv4**</span><span class="sxs-lookup"><span data-stu-id="0428f-238">**Edge Pool (External Edge) : IPv4**</span></span> <br/> |<span data-ttu-id="0428f-239">**边缘池（外部边缘）：双协议栈**</span><span class="sxs-lookup"><span data-stu-id="0428f-239">**Edge Pool (External Edge): Dual Stack**</span></span> <br/> |<span data-ttu-id="0428f-240">**边缘池（外部边缘）：IPv6**</span><span class="sxs-lookup"><span data-stu-id="0428f-240">**Edge Pool (External Edge): IPv6**</span></span> <br/> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0428f-241">**边缘池（内部边缘）：IPv4**</span><span class="sxs-lookup"><span data-stu-id="0428f-241">**Edge Pool (Internal Edge): IPv4**</span></span> <br/> |<span data-ttu-id="0428f-242">是</span><span class="sxs-lookup"><span data-stu-id="0428f-242">Yes</span></span>  <br/> |<span data-ttu-id="0428f-243">是</span><span class="sxs-lookup"><span data-stu-id="0428f-243">Yes</span></span>  <br/> |<span data-ttu-id="0428f-244">否</span><span class="sxs-lookup"><span data-stu-id="0428f-244">No</span></span>  <br/> |
|<span data-ttu-id="0428f-245">**边缘池（内部边缘）：双协议栈**</span><span class="sxs-lookup"><span data-stu-id="0428f-245">**Edge Pool (Internal Edge): Dual Stack**</span></span> <br/> |<span data-ttu-id="0428f-246">否</span><span class="sxs-lookup"><span data-stu-id="0428f-246">No</span></span>  <br/> |<span data-ttu-id="0428f-247">是</span><span class="sxs-lookup"><span data-stu-id="0428f-247">Yes</span></span>  <br/> |<span data-ttu-id="0428f-248">否</span><span class="sxs-lookup"><span data-stu-id="0428f-248">No</span></span>  <br/> |
|<span data-ttu-id="0428f-249">**边缘池（内部边缘）：IPv6**</span><span class="sxs-lookup"><span data-stu-id="0428f-249">**Edge Pool (Internal Edge): IPv6**</span></span> <br/> |<span data-ttu-id="0428f-250">否</span><span class="sxs-lookup"><span data-stu-id="0428f-250">No</span></span>  <br/> |<span data-ttu-id="0428f-251">否</span><span class="sxs-lookup"><span data-stu-id="0428f-251">No</span></span>  <br/> |<span data-ttu-id="0428f-252">是\*</span><span class="sxs-lookup"><span data-stu-id="0428f-252">Yes\*</span></span>  <br/> |
   
<span data-ttu-id="0428f-253">\*仅在实验室环境中使用此组合。</span><span class="sxs-lookup"><span data-stu-id="0428f-253">\* Use this combination only in a lab environment.</span></span>
  
### <a name="advanced-enterprise-voice-support-for-ipv6"></a><span data-ttu-id="0428f-254">IPv6 的高级企业语音支持</span><span class="sxs-lookup"><span data-stu-id="0428f-254">Advanced Enterprise Voice Support for IPv6</span></span>
<span data-ttu-id="0428f-255"><a name="Ent_V"> </a></span><span class="sxs-lookup"><span data-stu-id="0428f-255"><a name="Ent_V"> </a></span></span>

<span data-ttu-id="0428f-p109">包括呼叫许可控制 (CAC)、增强型 9-1-1 (E9-1-1) 或媒体旁路的部署必须配置为仅 IPv4 或双协议栈实施。仅使用 IPv6 的终结点无法使用其中任何一项功能。</span><span class="sxs-lookup"><span data-stu-id="0428f-p109">Deployments that include call admission control (CAC), Enhanced 9-1-1 (E9-1-1), or media bypass must be configured as IPv4 only or as a dual-stacked implementation. Endpoints using only IPv6 cannot use any of these features.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0428f-258">在双堆栈部署中，即使 Skype for Business 服务器客户端通过使用 IPv6 连接到 Skype for business 服务器，Skype for business 服务器也能更好地映射合适的 IPv4 地址以支持 E9-1。</span><span class="sxs-lookup"><span data-stu-id="0428f-258">In a dual-stacked deployment, even if a Skype for Business Server client connects to a Skype for Business Server by using IPv6, Skype for Business Server will make a best effort to map an appropriate IPv4 address to support E9-1-1.</span></span> 
  
<span data-ttu-id="0428f-259">不支持具有 IPv6 地址的位置信息服务。</span><span class="sxs-lookup"><span data-stu-id="0428f-259">Location Information service with IPv6 addresses is not supported.</span></span>
  
<span data-ttu-id="0428f-p110">Exchange 统一消息 (UM) 不支持 IPv6。对于 Exchange UM，请确保 DNS 解析不会返回 IPv6 地址。使用 IPv6 可能会在将呼叫发送至语音信箱时导致失败。</span><span class="sxs-lookup"><span data-stu-id="0428f-p110">Exchange Unified Messaging (UM) does not support IPv6. For Exchange UM, be sure that DNS resolution does not return an IPv6 address. Using IPv6 may cause failure when calls are sent to voice mail.</span></span> 
  
### <a name="other-skype-for-business-server-feature-support-for-ipv6"></a><span data-ttu-id="0428f-263">适用于 IPv6 的其他 Skype for Business 服务器功能支持</span><span class="sxs-lookup"><span data-stu-id="0428f-263">Other Skype for Business Server Feature Support for IPv6</span></span>
<span data-ttu-id="0428f-264"><a name="Ent_V"> </a></span><span class="sxs-lookup"><span data-stu-id="0428f-264"><a name="Ent_V"> </a></span></span>

<span data-ttu-id="0428f-265">除了之前提到的功能和组件，Skype for business 服务器还支持针对以下功能的 IPv6：</span><span class="sxs-lookup"><span data-stu-id="0428f-265">In addition to the features and components mentioned previously, Skype for Business Server supports IPv6 for the following features:</span></span>
  
- <span data-ttu-id="0428f-266">**持久聊天**</span><span class="sxs-lookup"><span data-stu-id="0428f-266">**Persistent Chat**</span></span>
    
    <span data-ttu-id="0428f-267">可使用拓扑生成器为持久聊天配置 IPv6。</span><span class="sxs-lookup"><span data-stu-id="0428f-267">You configure IPv6 for Persistent Chat by using Topology Builder.</span></span> <span data-ttu-id="0428f-268">有关配置持久聊天的详细信息，请参阅部署持久聊天服务器文档。</span><span class="sxs-lookup"><span data-stu-id="0428f-268">For details about configuring Persistent Chat, see the Deploying Persistent Chat Server documentation.</span></span>
    
- <span data-ttu-id="0428f-269">**用户体验质量 (QoE) 和呼叫详细信息记录 (CDR) 报告**</span><span class="sxs-lookup"><span data-stu-id="0428f-269">**Quality of Experience (QoE) and call detail recording (CDR) reports**</span></span>
    
    <span data-ttu-id="0428f-270">监视报告将会包括 IP 地址，因为该地址存储在监视服务器数据库中（无论类型为 IPv4 还是 IPv6）。</span><span class="sxs-lookup"><span data-stu-id="0428f-270">Monitoring reports include the IP address as it is stored in the Monitoring Server database, whether of type IPv4 or IPv6.</span></span>
    
## <a name="technical-requirements-for-ipv6"></a><span data-ttu-id="0428f-271">IPv6 的技术要求</span><span class="sxs-lookup"><span data-stu-id="0428f-271">Technical requirements for IPv6</span></span>
<span data-ttu-id="0428f-272"><a name="tech"> </a></span><span class="sxs-lookup"><span data-stu-id="0428f-272"><a name="tech"> </a></span></span>

<span data-ttu-id="0428f-273">如果您计划为 IPv6 配置 Skype for business Server，请记住以下要求：</span><span class="sxs-lookup"><span data-stu-id="0428f-273">If you plan to configure Skype for Business Server for IPv6, keep the following requirements in mind:</span></span>
  
- <span data-ttu-id="0428f-274">若要将 IPv6 地址用于 Skype for Business 服务器，你需要为必须发现和解析为 IPv6 地址的记录创建域名系统（DNS）记录。</span><span class="sxs-lookup"><span data-stu-id="0428f-274">To use IPv6 addresses with Skype for Business Server, you need to create domain name system (DNS) records for records that must be discovered and resolved to an IPv6 address.</span></span> <span data-ttu-id="0428f-275">IPv6 DNS 使用主机 AAAA (4A) 记录。</span><span class="sxs-lookup"><span data-stu-id="0428f-275">IPv6 DNS uses host AAAA (quad-A) records.</span></span> <span data-ttu-id="0428f-276">如果在部署中同时使用 IPv4 和 IPv6，最好同时配置和维护 IPv4 的主机 A 记录和 IPv6 的主机 AAAA 记录。</span><span class="sxs-lookup"><span data-stu-id="0428f-276">If you use both IPv4 and IPv6 in your deployment, it is best to configure and maintain both host A records for IPv4 and host AAAA records for IPv6.</span></span> <span data-ttu-id="0428f-277">即使将部署完全转换到 IPv6 后，仍可能需要 IPv4 DNS 主机记录以满足仍使用 IPv4 的用户。</span><span class="sxs-lookup"><span data-stu-id="0428f-277">Even when you fully transition your deployment to IPv6, you may still require IPv4 DNS host records for external users who still use IPv4.</span></span>
    
    <span data-ttu-id="0428f-p113">您可以在开始使用 IPv6 前部署 IPv6 DNS 主机记录。如果客户端或服务器不使用 IPv6，该记录不会被引用。切换技术将根据切换技术配置和策略决定使用哪条记录。</span><span class="sxs-lookup"><span data-stu-id="0428f-p113">You can deploy IPv6 DNS host records before you start using IPv6. If the client or server doesn't use IPv6, the record will not be referenced. Transitional technologies will make the decision about which record to use, based on transition technology configuration and policies.</span></span>
    
- <span data-ttu-id="0428f-281">每个 IPv6 地址都有一个作用域。</span><span class="sxs-lookup"><span data-stu-id="0428f-281">Each IPv6 address has a scope.</span></span> <span data-ttu-id="0428f-282">可用于 IPv6 寻址的三个作用域是 IPv6 全局地址（类似于公用 IPv4 地址）、IPv6 唯一本地地址（类似于专用 IPv4 地址范围）和 IPv6 链接本地地址（类似于中的自动专用 IP 地址）Windows Server for IPv4）。</span><span class="sxs-lookup"><span data-stu-id="0428f-282">The three scopes that you can use for IPv6 addressing are IPv6 global addresses (similar to public IPv4 addresses), IPv6 unique local addresses (similar to the private IPv4 address ranges), and IPv6 link-local addresses (similar to automatic private IP addresses in Windows Server for IPv4).</span></span> <span data-ttu-id="0428f-283">池内所有服务器都应该具有作用域相同的 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="0428f-283">All the servers within a pool should have IPv6 addresses with the same scope.</span></span> 
    
> [!IMPORTANT]
> <span data-ttu-id="0428f-284">IPv6 是一个复杂的主题，需要仔细规划网络团队和 Internet 提供商，以帮助确保你在 Windows Server 级别和 Skype for Business 服务器级别分配的地址按预期工作。</span><span class="sxs-lookup"><span data-stu-id="0428f-284">IPv6 is a complex topic and requires careful planning with your networking team and your Internet provider to help ensure that the addresses that you assign at the Windows Server level and at the Skype for Business Server level work as expected.</span></span> <span data-ttu-id="0428f-285">请参阅本主题结尾处的链接，以了解有关 IPv6 寻址和规划的其他资源。</span><span class="sxs-lookup"><span data-stu-id="0428f-285">See the links at the end of this topic for additional resources on IPv6 addressing and planning.</span></span> 
  
## <a name="migration-and-coexistence-considerations-for-ipv6"></a><span data-ttu-id="0428f-286">IPv6 的迁移和共存注意事项</span><span class="sxs-lookup"><span data-stu-id="0428f-286">Migration and coexistence considerations for IPv6</span></span>
<span data-ttu-id="0428f-287"><a name="migration"> </a></span><span class="sxs-lookup"><span data-stu-id="0428f-287"><a name="migration"> </a></span></span>

<span data-ttu-id="0428f-288">Lync Server 2010 或 Office 通信服务器不支持 IP 版本6（IPv6）。</span><span class="sxs-lookup"><span data-stu-id="0428f-288">IP version 6 (IPv6) is not supported on Lync Server 2010 or Office Communications Server.</span></span> <span data-ttu-id="0428f-289">出于试验目的，你可以测试 Lync Server 2010 和 Skype for business 服务器双栈共存。</span><span class="sxs-lookup"><span data-stu-id="0428f-289">For piloting purposes, you can test Lync Server 2010 and Skype for Business Server dual-stack coexistence.</span></span> <span data-ttu-id="0428f-290">我们建议先将给定中心网站的所有池升级到 Skype for business 服务器，然后再为任何池启用 IPv6 （双堆栈网络）。</span><span class="sxs-lookup"><span data-stu-id="0428f-290">We recommend that all pools for a given central site are upgraded to Skype for Business Server before you enable IPv6 (dual-stack network) for any of the pools.</span></span> <span data-ttu-id="0428f-291">如果您需要为池配置仅 IPv6，则建议您在实验室环境中设置仅 IPv6 以进行测试。</span><span class="sxs-lookup"><span data-stu-id="0428f-291">If you need to configure a pool for IPv6 only, we recommend that you set up an IPv6-only pool in your lab environment for testing.</span></span>
  
<span data-ttu-id="0428f-292">迁移和共存期间支持下列方案：</span><span class="sxs-lookup"><span data-stu-id="0428f-292">The following scenarios are supported during migration and coexistence:</span></span>
  
- <span data-ttu-id="0428f-293">在双堆栈模式下与 Skype for business Server 共存的 IPv4 模式下的 skype for business 服务器、Lync Server 2013 和 Lync Server 2010 池。</span><span class="sxs-lookup"><span data-stu-id="0428f-293">Skype for Business Server, Lync Server 2013, and Lync Server 2010 pools in IPv4 mode, coexisting with Skype for Business Server in dual-stack mode.</span></span>
    
- <span data-ttu-id="0428f-294">仅限 IPv6 模式的 Skype for business 服务器池（如果仅限 IPv6 的池是孤立的池）。</span><span class="sxs-lookup"><span data-stu-id="0428f-294">Skype for Business Server pool in IPv6-only mode, if the IPv6-only pool is siloed.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="0428f-295">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0428f-295">See also</span></span>
<span data-ttu-id="0428f-296"><a name="migration"> </a></span><span class="sxs-lookup"><span data-stu-id="0428f-296"><a name="migration"> </a></span></span>

[<span data-ttu-id="0428f-297">Configure IP address types in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="0428f-297">Configure IP address types in Skype for Business</span></span>](ip-address-types.md)

[<span data-ttu-id="0428f-298">IP 版本6寻址体系结构</span><span class="sxs-lookup"><span data-stu-id="0428f-298">IP Version 6 Addressing Architecture</span></span>](https://tools.ietf.org/html/rfc4291)
  
[<span data-ttu-id="0428f-299">IPv6 全局单播地址格式</span><span class="sxs-lookup"><span data-stu-id="0428f-299">IPv6 Global Unicast Address Format</span></span>](https://tools.ietf.org/html/rfc3587)
  
[<span data-ttu-id="0428f-300">唯一本地 IPv6 单播地址</span><span class="sxs-lookup"><span data-stu-id="0428f-300">Unique Local IPv6 Unicast Addresses</span></span>](https://tools.ietf.org/html/rfc4193)
