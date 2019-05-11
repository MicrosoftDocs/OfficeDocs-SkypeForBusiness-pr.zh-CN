---
title: 规划 Skype for Business 中的 IPv6
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
ms.assetid: 01f77196-38f4-4292-9480-2e2fbd57eabe
description: 摘要： 实现 IPv6 业务服务器安装 Skype 之前。
ms.openlocfilehash: fa00f769a277ae8ec1ecacae45560b4659082b21
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33905722"
---
# <a name="plan-for-ipv6-in-skype-for-business"></a><span data-ttu-id="22206-103">规划 Skype for Business 中的 IPv6</span><span class="sxs-lookup"><span data-stu-id="22206-103">Plan for IPv6 in Skype for Business</span></span>
 
<span data-ttu-id="22206-104">**摘要：** 在您安装 Skype 业务服务器之前，请实现 IPv6。</span><span class="sxs-lookup"><span data-stu-id="22206-104">**Summary:** Implement IPv6 before you install Skype for Business Server.</span></span>
  
<span data-ttu-id="22206-105">Skype 业务服务器包括对 IP 版本 6 (IPv6) 的支持地址，以及持续支持 ip 版本 4 (IPv4) 地址。</span><span class="sxs-lookup"><span data-stu-id="22206-105">Skype for Business Server includes support for IP version 6 (IPv6) addresses, along with continued support of IP version 4 (IPv4) addresses.</span></span> 

<span data-ttu-id="22206-106">IPv4 地址是 32 位地址，允许计算机通过 Internet 进行通信。</span><span class="sxs-lookup"><span data-stu-id="22206-106">IPv4 addresses are 32-bit addresses that allow a computer to communicate over the Internet.</span></span> <span data-ttu-id="22206-107">由于全球范围内的设备越来越多，可用的 IPv4 地址出完。因此，很多新设备移动到使用 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="22206-107">Due to the increasing number of devices worldwide, the available IPv4 addresses have run out. Because of this, many new devices are moving to using IPv6 addresses.</span></span> <span data-ttu-id="22206-108">IPv6 地址执行与 IPv4 地址相同的功能（并另外增加了一些功能），只不过 IPv6 地址不是使用 32 位，而是使用 128 位。</span><span class="sxs-lookup"><span data-stu-id="22206-108">IPv6 addresses perform the same function as IPv4 addresses (with some additional features), but instead of using only 32-bits, IPv6 addresses use 128-bits.</span></span> <span data-ttu-id="22206-109">这不仅提供了一组新的地址，而且数量远远超过原来的地址集。</span><span class="sxs-lookup"><span data-stu-id="22206-109">This provides not only a new set of addresses, but also a much larger number of them.</span></span> 

<span data-ttu-id="22206-110">传统 IPv4 地址看起来类似于：192.0.2.235，而 IPv6 地址看起来类似于：2001:0db8:85a3:0000:0000:8a2e:0370:7334。</span><span class="sxs-lookup"><span data-stu-id="22206-110">A typical IPv4 address looks something like this: 192.0.2.235, whereas an IPv6 address looks like this: 2001:0db8:85a3:0000:0000:8a2e:0370:7334.</span></span> <span data-ttu-id="22206-111">格式和使用 IPv6 地址的设备的功能更改业务服务器安装要求在您 Skype 的一些部署和配置注意事项。</span><span class="sxs-lookup"><span data-stu-id="22206-111">The change in formatting and functionality for devices that use IPv6 addresses requires several deployment and configuration considerations in your Skype for Business Server installation.</span></span> 

<span data-ttu-id="22206-112">本主题包括以下部分：</span><span class="sxs-lookup"><span data-stu-id="22206-112">This topic includes the following sections:</span></span>
  
- [<span data-ttu-id="22206-113">Overview of IP address types</span><span class="sxs-lookup"><span data-stu-id="22206-113">Overview of IP address types</span></span>](ipv6.md#over)
    
- [<span data-ttu-id="22206-114">Technical requirements for IPv6</span><span class="sxs-lookup"><span data-stu-id="22206-114">Technical requirements for IPv6</span></span>](ipv6.md#tech)
    
- [<span data-ttu-id="22206-115">Migration and coexistence considerations for IPv6</span><span class="sxs-lookup"><span data-stu-id="22206-115">Migration and coexistence considerations for IPv6</span></span>](ipv6.md#migration)
    
<span data-ttu-id="22206-116">如果您确定您将使用 IPv6 地址，请参阅[Skype for Business 中的配置的 IP 地址类型](ip-address-types.md)文章。</span><span class="sxs-lookup"><span data-stu-id="22206-116">If you determine you will be using IPv6 addresses, refer to the [Configure IP address types in Skype for Business](ip-address-types.md) article.</span></span>
  
## <a name="overview-of-ip-address-types"></a><span data-ttu-id="22206-117">IP 地址类型概述</span><span class="sxs-lookup"><span data-stu-id="22206-117">Overview of IP address types</span></span>
<span data-ttu-id="22206-118"><a name="over"> </a></span><span class="sxs-lookup"><span data-stu-id="22206-118"></span></span>

<span data-ttu-id="22206-119">配置 IP 地址中 Skype 业务服务器时，您可以具有三个选项。</span><span class="sxs-lookup"><span data-stu-id="22206-119">You have three options when configuring IP addresses in Skype for Business Server.</span></span> <span data-ttu-id="22206-120">您可以配置的业务服务器支持仅 IP 版本 4 (IPv4)，仅 IP 版本 6 (IPv6) 的 Skype 或二者的组合 （称为双协议栈）。</span><span class="sxs-lookup"><span data-stu-id="22206-120">You can configure Skype for Business Server to support only IP version 4 (IPv4), only IP version 6 (IPv6), or a combination of both (known as a dual stack).</span></span> <span data-ttu-id="22206-121">对于每种类型的配置，都需要考虑一些问题：</span><span class="sxs-lookup"><span data-stu-id="22206-121">There are several issues to consider with each type of configuration:</span></span>
  
- <span data-ttu-id="22206-122">**仅使用 IPv4**创建 IPv6，因为世界不足 IPv4 地址。</span><span class="sxs-lookup"><span data-stu-id="22206-122">**IPv4 only** IPv6 was created because the world is running out of IPv4 addresses.</span></span> <span data-ttu-id="22206-123">最终，IPv6 将在全球范围内获得全面支持，但就目前而言，您的企业需要与之通信的很多公司和设备可能尚不支持 IPv6，并且在一段时间内可能也不会提供相应支持。</span><span class="sxs-lookup"><span data-stu-id="22206-123">Ultimately, IPv6 will be fully supported worldwide, but at this time, many companies and devices that your enterprise might need to communicate with do not yet support IPv6, and may not for some time.</span></span> <span data-ttu-id="22206-124">仅 IPv4 配置将有助于确保您的业务服务器实现 Skype 可以和大多数现有设备通信。</span><span class="sxs-lookup"><span data-stu-id="22206-124">An IPv4-only configuration will help to ensure that your Skype for Business Server implementation can communicate with most existing devices.</span></span>
    
- <span data-ttu-id="22206-125">**仅 IPv6**完全实现 IPv6 将相反，通信与许多现有设备。</span><span class="sxs-lookup"><span data-stu-id="22206-125">**IPv6 only** Conversely, a full IPv6 implementation will exclude communication with many existing devices.</span></span>
    
- <span data-ttu-id="22206-126">**双协议栈**双协议栈是的网络中启用 IPv4 和 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="22206-126">**Dual Stack** Dual stack is a network where both IPv4 and IPv6 addresses are enabled.</span></span> <span data-ttu-id="22206-127">此配置是因为在大多数情况下从完全 IPv4 转换为完全 IPv6 将花费几年业务服务器 Skype 中支持的。</span><span class="sxs-lookup"><span data-stu-id="22206-127">This configuration is supported in Skype for Business Server because in most cases the transition from full-IPv4 to full-IPv6 will take several years.</span></span>
    
<span data-ttu-id="22206-128">以下各节概述了各种 Skype 业务 Server 功能的三种配置之间的兼容性。</span><span class="sxs-lookup"><span data-stu-id="22206-128">The following sections outline the compatibility among these three configurations for various Skype for Business Server features.</span></span>
  
> [!NOTE]
> <span data-ttu-id="22206-p106">仅 IPv6 的客户端或服务器配置只受选项卡或验证的支持。仅 IPv6 配置在生产部署中不受支持。</span><span class="sxs-lookup"><span data-stu-id="22206-p106">Client or server configuration with IPv6 only is supported only for lab or validation purposes. IPv6 only configuration is not supported in the production deployment.</span></span> 
  
### <a name="client-registration"></a><span data-ttu-id="22206-131">客户端注册</span><span class="sxs-lookup"><span data-stu-id="22206-131">Client Registration</span></span>
<span data-ttu-id="22206-132"><a name="client"> </a></span><span class="sxs-lookup"><span data-stu-id="22206-132"></span></span>

|<span data-ttu-id="22206-133">**客户端终结点网络**</span><span class="sxs-lookup"><span data-stu-id="22206-133">**Client endpoint network**</span></span>|<span data-ttu-id="22206-134">**服务器网络**</span><span class="sxs-lookup"><span data-stu-id="22206-134">**Server network**</span></span>|
|:-----|:-----|
|<span data-ttu-id="22206-135">IPv4</span><span class="sxs-lookup"><span data-stu-id="22206-135">IPv4</span></span>  <br/> |<span data-ttu-id="22206-136">IPv4</span><span class="sxs-lookup"><span data-stu-id="22206-136">IPv4</span></span>  <br/> |
|<span data-ttu-id="22206-137">IPv4</span><span class="sxs-lookup"><span data-stu-id="22206-137">IPv4</span></span>  <br/> |<span data-ttu-id="22206-138">双协议栈</span><span class="sxs-lookup"><span data-stu-id="22206-138">Dual stack</span></span>  <br/> |
|<span data-ttu-id="22206-139">双协议栈</span><span class="sxs-lookup"><span data-stu-id="22206-139">Dual stack</span></span>  <br/> |<span data-ttu-id="22206-140">IPv4</span><span class="sxs-lookup"><span data-stu-id="22206-140">IPv4</span></span>  <br/> |
|<span data-ttu-id="22206-141">双协议栈</span><span class="sxs-lookup"><span data-stu-id="22206-141">Dual stack</span></span>  <br/> |<span data-ttu-id="22206-142">双协议栈</span><span class="sxs-lookup"><span data-stu-id="22206-142">Dual stack</span></span>  <br/> |
|<span data-ttu-id="22206-143">双协议栈</span><span class="sxs-lookup"><span data-stu-id="22206-143">Dual stack</span></span>  <br/> |<span data-ttu-id="22206-144">IPv6</span><span class="sxs-lookup"><span data-stu-id="22206-144">IPv6</span></span>  <br/> |
|<span data-ttu-id="22206-145">IPv6</span><span class="sxs-lookup"><span data-stu-id="22206-145">IPv6</span></span>  <br/> |<span data-ttu-id="22206-146">双协议栈</span><span class="sxs-lookup"><span data-stu-id="22206-146">Dual stack</span></span>  <br/> |
|<span data-ttu-id="22206-147">IPv6</span><span class="sxs-lookup"><span data-stu-id="22206-147">IPv6</span></span>  <br/> |<span data-ttu-id="22206-148">IPv6</span><span class="sxs-lookup"><span data-stu-id="22206-148">IPv6</span></span>  <br/> |
   
### <a name="peer-to-peer-client"></a><span data-ttu-id="22206-149">对等客户端</span><span class="sxs-lookup"><span data-stu-id="22206-149">Peer-to-Peer Client</span></span>
<span data-ttu-id="22206-150"><a name="peer"> </a></span><span class="sxs-lookup"><span data-stu-id="22206-150"></span></span>

<span data-ttu-id="22206-151">对等通信包括音频、音频/视频、应用程序共享和文件传输。</span><span class="sxs-lookup"><span data-stu-id="22206-151">Peer-to-peer communications include audio, audio/video, application sharing, and file transfer.</span></span> <span data-ttu-id="22206-152">两个客户端均注册成功后，将支持以下组合。</span><span class="sxs-lookup"><span data-stu-id="22206-152">After both clients have successfully registered, the following combinations are supported.</span></span>
  
|<span data-ttu-id="22206-153">**客户端终结点 1**</span><span class="sxs-lookup"><span data-stu-id="22206-153">**Client endpoint 1**</span></span>|<span data-ttu-id="22206-154">**客户端终结点 2**</span><span class="sxs-lookup"><span data-stu-id="22206-154">**Client endpoint 2**</span></span>|
|:-----|:-----|
|<span data-ttu-id="22206-155">IPv4</span><span class="sxs-lookup"><span data-stu-id="22206-155">IPv4</span></span>  <br/> |<span data-ttu-id="22206-156">IPv4</span><span class="sxs-lookup"><span data-stu-id="22206-156">IPv4</span></span>  <br/> |
|<span data-ttu-id="22206-157">IPv4</span><span class="sxs-lookup"><span data-stu-id="22206-157">IPv4</span></span>  <br/> |<span data-ttu-id="22206-158">双协议栈</span><span class="sxs-lookup"><span data-stu-id="22206-158">Dual stack</span></span>  <br/> |
|<span data-ttu-id="22206-159">双协议栈</span><span class="sxs-lookup"><span data-stu-id="22206-159">Dual stack</span></span>  <br/> |<span data-ttu-id="22206-160">双协议栈</span><span class="sxs-lookup"><span data-stu-id="22206-160">Dual stack</span></span>  <br/> |
|<span data-ttu-id="22206-161">IPv6</span><span class="sxs-lookup"><span data-stu-id="22206-161">IPv6</span></span>  <br/> |<span data-ttu-id="22206-162">双协议栈</span><span class="sxs-lookup"><span data-stu-id="22206-162">Dual stack</span></span>  <br/> |
|<span data-ttu-id="22206-163">IPv6</span><span class="sxs-lookup"><span data-stu-id="22206-163">IPv6</span></span>  <br/> |<span data-ttu-id="22206-164">IPv6</span><span class="sxs-lookup"><span data-stu-id="22206-164">IPv6</span></span>  <br/> |
   
### <a name="conferencing"></a><span data-ttu-id="22206-165">会议</span><span class="sxs-lookup"><span data-stu-id="22206-165">Conferencing</span></span>
<span data-ttu-id="22206-166"><a name="conf"> </a></span><span class="sxs-lookup"><span data-stu-id="22206-166"></span></span>

<span data-ttu-id="22206-167">会议包括音频/视频、应用程序共享和数据协作应用程序（比如白板和文件共享）。</span><span class="sxs-lookup"><span data-stu-id="22206-167">Conferencing includes audio/video, application sharing, and data collaboration applications like whiteboarding and file sharing.</span></span>
  
|<span data-ttu-id="22206-168">**客户端终结点网络**</span><span class="sxs-lookup"><span data-stu-id="22206-168">**Client endpoint network**</span></span>|<span data-ttu-id="22206-169">**服务器网络**</span><span class="sxs-lookup"><span data-stu-id="22206-169">**Server network**</span></span>|
|:-----|:-----|
|<span data-ttu-id="22206-170">IPv4</span><span class="sxs-lookup"><span data-stu-id="22206-170">IPv4</span></span>  <br/> |<span data-ttu-id="22206-171">IPv4</span><span class="sxs-lookup"><span data-stu-id="22206-171">IPv4</span></span>  <br/> |
|<span data-ttu-id="22206-172">IPv4</span><span class="sxs-lookup"><span data-stu-id="22206-172">IPv4</span></span>  <br/> |<span data-ttu-id="22206-173">双协议栈</span><span class="sxs-lookup"><span data-stu-id="22206-173">Dual stack</span></span>  <br/> |
|<span data-ttu-id="22206-174">双协议栈</span><span class="sxs-lookup"><span data-stu-id="22206-174">Dual stack</span></span>  <br/> |<span data-ttu-id="22206-175">IPv4</span><span class="sxs-lookup"><span data-stu-id="22206-175">IPv4</span></span>  <br/> |
|<span data-ttu-id="22206-176">双协议栈</span><span class="sxs-lookup"><span data-stu-id="22206-176">Dual stack</span></span>  <br/> |<span data-ttu-id="22206-177">双协议栈</span><span class="sxs-lookup"><span data-stu-id="22206-177">Dual stack</span></span>  <br/> |
|<span data-ttu-id="22206-178">双协议栈</span><span class="sxs-lookup"><span data-stu-id="22206-178">Dual stack</span></span>  <br/> |<span data-ttu-id="22206-179">IPv6</span><span class="sxs-lookup"><span data-stu-id="22206-179">IPv6</span></span>  <br/> |
|<span data-ttu-id="22206-180">IPv6</span><span class="sxs-lookup"><span data-stu-id="22206-180">IPv6</span></span>  <br/> |<span data-ttu-id="22206-181">双协议栈</span><span class="sxs-lookup"><span data-stu-id="22206-181">Dual stack</span></span>  <br/> |
|<span data-ttu-id="22206-182">IPv6</span><span class="sxs-lookup"><span data-stu-id="22206-182">IPv6</span></span>  <br/> |<span data-ttu-id="22206-183">IPv6</span><span class="sxs-lookup"><span data-stu-id="22206-183">IPv6</span></span>  <br/> |
   
### <a name="mediation-serverpstn"></a><span data-ttu-id="22206-184">中介服务器/PSTN</span><span class="sxs-lookup"><span data-stu-id="22206-184">Mediation Server/PSTN</span></span>
<span data-ttu-id="22206-185"><a name="med"> </a></span><span class="sxs-lookup"><span data-stu-id="22206-185"></span></span>

<span data-ttu-id="22206-186">Skype 业务服务器不支持媒体绕过公用电话交换网 (pstn) 呼叫流量是否通过 IPv6 接口。</span><span class="sxs-lookup"><span data-stu-id="22206-186">Skype for Business Server does not support media bypass for public switched telephone network (PSTN) calls if the traffic is through an IPv6 interface.</span></span> <span data-ttu-id="22206-187">如果需要媒体旁路，则我们建议将 PSTN 网关配置为 IPv4。</span><span class="sxs-lookup"><span data-stu-id="22206-187">If media bypass is required, we recommend that the PSTN gateway is configured to IPv4.</span></span> 
  
|<span data-ttu-id="22206-188">**主接口 1**</span><span class="sxs-lookup"><span data-stu-id="22206-188">**Primary interface 1**</span></span>|<span data-ttu-id="22206-189">**PSTN 接口（位于中介服务器上）**</span><span class="sxs-lookup"><span data-stu-id="22206-189">**PSTN interface (on Mediation Server)**</span></span>|<span data-ttu-id="22206-190">**PSTN 网关设置**</span><span class="sxs-lookup"><span data-stu-id="22206-190">**PSTN gateway setting**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="22206-191">IPv4</span><span class="sxs-lookup"><span data-stu-id="22206-191">IPv4</span></span>  <br/> |<span data-ttu-id="22206-192">双协议栈</span><span class="sxs-lookup"><span data-stu-id="22206-192">Dual stack</span></span>  <br/> |<span data-ttu-id="22206-193">IPv4</span><span class="sxs-lookup"><span data-stu-id="22206-193">IPv4</span></span>  <br/> |
|<span data-ttu-id="22206-194">双协议栈</span><span class="sxs-lookup"><span data-stu-id="22206-194">Dual stack</span></span>  <br/> |<span data-ttu-id="22206-195">双协议栈</span><span class="sxs-lookup"><span data-stu-id="22206-195">Dual stack</span></span>  <br/> |<span data-ttu-id="22206-196">IPv4</span><span class="sxs-lookup"><span data-stu-id="22206-196">IPv4</span></span>  <br/> |
|<span data-ttu-id="22206-197">双协议栈</span><span class="sxs-lookup"><span data-stu-id="22206-197">Dual stack</span></span>  <br/> |<span data-ttu-id="22206-198">双协议栈</span><span class="sxs-lookup"><span data-stu-id="22206-198">Dual stack</span></span>  <br/> |<span data-ttu-id="22206-199">IPv6</span><span class="sxs-lookup"><span data-stu-id="22206-199">IPv6</span></span>  <br/> |
   
1. <span data-ttu-id="22206-200">主接口是与业务服务器组件的 Skype 进行通信的接口。</span><span class="sxs-lookup"><span data-stu-id="22206-200">The primary interface is the interface that communicates with the Skype for Business Server components.</span></span>
  
### <a name="remote-user-peer-to-peer-communications"></a><span data-ttu-id="22206-201">远程用户对等通信</span><span class="sxs-lookup"><span data-stu-id="22206-201">Remote User Peer-to-Peer Communications</span></span>
<span data-ttu-id="22206-202"><a name="remote"> </a></span><span class="sxs-lookup"><span data-stu-id="22206-202"></span></span>

<span data-ttu-id="22206-203">与远程用户的对等通信包括即时消息、音频/视频、应用程序共享和文件传输。</span><span class="sxs-lookup"><span data-stu-id="22206-203">Peer-to-peer communications with remote users include instant messaging, audio/video, application sharing, and file transfer.</span></span>
  
|<span data-ttu-id="22206-204">**远程用户网络**</span><span class="sxs-lookup"><span data-stu-id="22206-204">**Remote user network**</span></span>|<span data-ttu-id="22206-205">**边缘服务器（外部边缘）**</span><span class="sxs-lookup"><span data-stu-id="22206-205">**Edge server (External edge)**</span></span>|
|:-----|:-----|
|<span data-ttu-id="22206-206">IPv4</span><span class="sxs-lookup"><span data-stu-id="22206-206">IPv4</span></span>  <br/> |<span data-ttu-id="22206-207">IPv4</span><span class="sxs-lookup"><span data-stu-id="22206-207">IPv4</span></span>  <br/> |
|<span data-ttu-id="22206-208">双协议栈</span><span class="sxs-lookup"><span data-stu-id="22206-208">Dual stack</span></span>  <br/> |<span data-ttu-id="22206-209">IPv4</span><span class="sxs-lookup"><span data-stu-id="22206-209">IPv4</span></span>  <br/> |
|<span data-ttu-id="22206-210">双协议栈</span><span class="sxs-lookup"><span data-stu-id="22206-210">Dual stack</span></span>  <br/> |<span data-ttu-id="22206-211">双协议栈</span><span class="sxs-lookup"><span data-stu-id="22206-211">Dual stack</span></span>  <br/> |
|<span data-ttu-id="22206-212">IPv6</span><span class="sxs-lookup"><span data-stu-id="22206-212">IPv6</span></span>  <br/> |<span data-ttu-id="22206-213">双协议栈</span><span class="sxs-lookup"><span data-stu-id="22206-213">Dual stack</span></span>  <br/> |
|<span data-ttu-id="22206-214">IPv6</span><span class="sxs-lookup"><span data-stu-id="22206-214">IPv6</span></span>  <br/> |<span data-ttu-id="22206-215">IPv6</span><span class="sxs-lookup"><span data-stu-id="22206-215">IPv6</span></span>  <br/> |
   
### <a name="front-end-pool-and-edge-pool-configuration"></a><span data-ttu-id="22206-216">前端池和边缘池配置</span><span class="sxs-lookup"><span data-stu-id="22206-216">Front End Pool and Edge Pool Configuration</span></span>
<span data-ttu-id="22206-217"><a name="FE_pool"> </a></span><span class="sxs-lookup"><span data-stu-id="22206-217"></span></span>

<span data-ttu-id="22206-218">下表显示了前端服务器池和内部边缘服务器池之间的支持矩阵。</span><span class="sxs-lookup"><span data-stu-id="22206-218">The following table shows the support matrix between the Front End Server pool and the internal Edge Server pool.</span></span>
  
<span data-ttu-id="22206-219">**前端池和边缘池（内部边缘）矩阵**</span><span class="sxs-lookup"><span data-stu-id="22206-219">**Front End Pool and Edge Pool (Internal Edge) Matrix**</span></span>

||<span data-ttu-id="22206-220">**边缘池：IPv4**</span><span class="sxs-lookup"><span data-stu-id="22206-220">**Edge Pool: IPv4**</span></span> <br/> |<span data-ttu-id="22206-221">**边缘池：双协议栈**</span><span class="sxs-lookup"><span data-stu-id="22206-221">**Edge Pool: Dual Stack**</span></span> <br/> |<span data-ttu-id="22206-222">**边缘池：IPv6**</span><span class="sxs-lookup"><span data-stu-id="22206-222">**Edge Pool: IPv6**</span></span> <br/> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="22206-223">**前端池：IPv4**</span><span class="sxs-lookup"><span data-stu-id="22206-223">**Front End Pool: IPv4**</span></span> <br/> |<span data-ttu-id="22206-224">是</span><span class="sxs-lookup"><span data-stu-id="22206-224">Yes</span></span>  <br/> |<span data-ttu-id="22206-225">是</span><span class="sxs-lookup"><span data-stu-id="22206-225">Yes</span></span>  <br/> |<span data-ttu-id="22206-226">否</span><span class="sxs-lookup"><span data-stu-id="22206-226">No</span></span>  <br/> |
|<span data-ttu-id="22206-227">**前端池：双协议栈**</span><span class="sxs-lookup"><span data-stu-id="22206-227">**Front End Pool: Dual Stack**</span></span> <br/> |<span data-ttu-id="22206-228">是</span><span class="sxs-lookup"><span data-stu-id="22206-228">Yes</span></span>  <br/> |<span data-ttu-id="22206-229">是</span><span class="sxs-lookup"><span data-stu-id="22206-229">Yes</span></span>  <br/> |<span data-ttu-id="22206-230">否</span><span class="sxs-lookup"><span data-stu-id="22206-230">No</span></span>  <br/> |
|<span data-ttu-id="22206-231">**前端池：IPv6**</span><span class="sxs-lookup"><span data-stu-id="22206-231">**Front End Pool: IPv6**</span></span> <br/> |<span data-ttu-id="22206-232">否</span><span class="sxs-lookup"><span data-stu-id="22206-232">No</span></span>  <br/> |<span data-ttu-id="22206-233">否</span><span class="sxs-lookup"><span data-stu-id="22206-233">No</span></span>  <br/> |<span data-ttu-id="22206-234">是\*</span><span class="sxs-lookup"><span data-stu-id="22206-234">Yes\*</span></span>  <br/> |
   
<span data-ttu-id="22206-235">\*仅在实验室环境中使用此组合。</span><span class="sxs-lookup"><span data-stu-id="22206-235">\* Use this combination only in a lab environment.</span></span>
  
<span data-ttu-id="22206-236">下表是内部和外部边缘接口支持的组合矩阵。</span><span class="sxs-lookup"><span data-stu-id="22206-236">The following table is a matrix of the supported combinations of internal and external edge interfaces.</span></span>
  
<span data-ttu-id="22206-237">**边缘池（内部边缘）和边缘池（外部边缘）矩阵**</span><span class="sxs-lookup"><span data-stu-id="22206-237">**Edge Pool (Internal Edge) and Edge pool (External Edge) Matrix**</span></span>

||<span data-ttu-id="22206-238">**边缘池（外部边缘）：IPv4**</span><span class="sxs-lookup"><span data-stu-id="22206-238">**Edge Pool (External Edge) : IPv4**</span></span> <br/> |<span data-ttu-id="22206-239">**边缘池（外部边缘）：双协议栈**</span><span class="sxs-lookup"><span data-stu-id="22206-239">**Edge Pool (External Edge): Dual Stack**</span></span> <br/> |<span data-ttu-id="22206-240">**边缘池（外部边缘）：IPv6**</span><span class="sxs-lookup"><span data-stu-id="22206-240">**Edge Pool (External Edge): IPv6**</span></span> <br/> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="22206-241">**边缘池（内部边缘）：IPv4**</span><span class="sxs-lookup"><span data-stu-id="22206-241">**Edge Pool (Internal Edge): IPv4**</span></span> <br/> |<span data-ttu-id="22206-242">是</span><span class="sxs-lookup"><span data-stu-id="22206-242">Yes</span></span>  <br/> |<span data-ttu-id="22206-243">是</span><span class="sxs-lookup"><span data-stu-id="22206-243">Yes</span></span>  <br/> |<span data-ttu-id="22206-244">否</span><span class="sxs-lookup"><span data-stu-id="22206-244">No</span></span>  <br/> |
|<span data-ttu-id="22206-245">**边缘池（内部边缘）：双协议栈**</span><span class="sxs-lookup"><span data-stu-id="22206-245">**Edge Pool (Internal Edge): Dual Stack**</span></span> <br/> |<span data-ttu-id="22206-246">否</span><span class="sxs-lookup"><span data-stu-id="22206-246">No</span></span>  <br/> |<span data-ttu-id="22206-247">是</span><span class="sxs-lookup"><span data-stu-id="22206-247">Yes</span></span>  <br/> |<span data-ttu-id="22206-248">否</span><span class="sxs-lookup"><span data-stu-id="22206-248">No</span></span>  <br/> |
|<span data-ttu-id="22206-249">**边缘池（内部边缘）：IPv6**</span><span class="sxs-lookup"><span data-stu-id="22206-249">**Edge Pool (Internal Edge): IPv6**</span></span> <br/> |<span data-ttu-id="22206-250">否</span><span class="sxs-lookup"><span data-stu-id="22206-250">No</span></span>  <br/> |<span data-ttu-id="22206-251">否</span><span class="sxs-lookup"><span data-stu-id="22206-251">No</span></span>  <br/> |<span data-ttu-id="22206-252">是\*</span><span class="sxs-lookup"><span data-stu-id="22206-252">Yes\*</span></span>  <br/> |
   
<span data-ttu-id="22206-253">\*仅在实验室环境中使用此组合。</span><span class="sxs-lookup"><span data-stu-id="22206-253">\* Use this combination only in a lab environment.</span></span>
  
### <a name="advanced-enterprise-voice-support-for-ipv6"></a><span data-ttu-id="22206-254">IPv6 的高级企业语音支持</span><span class="sxs-lookup"><span data-stu-id="22206-254">Advanced Enterprise Voice Support for IPv6</span></span>
<span data-ttu-id="22206-255"><a name="Ent_V"> </a></span><span class="sxs-lookup"><span data-stu-id="22206-255"></span></span>

<span data-ttu-id="22206-p109">包括呼叫许可控制 (CAC)、增强型 9-1-1 (E9-1-1) 或媒体旁路的部署必须配置为仅 IPv4 或双协议栈实施。仅使用 IPv6 的终结点无法使用其中任何一项功能。</span><span class="sxs-lookup"><span data-stu-id="22206-p109">Deployments that include call admission control (CAC), Enhanced 9-1-1 (E9-1-1), or media bypass must be configured as IPv4 only or as a dual-stacked implementation. Endpoints using only IPv6 cannot use any of these features.</span></span>
  
> [!NOTE]
> <span data-ttu-id="22206-258">在双协议栈部署中，即使 Skype Business Server 客户端连接到 Skype 业务服务器使用 IPv6，Skype 业务服务器将尽力映射相应的 IPv4 地址以支持 E9-1-1。</span><span class="sxs-lookup"><span data-stu-id="22206-258">In a dual-stacked deployment, even if a Skype for Business Server client connects to a Skype for Business Server by using IPv6, Skype for Business Server will make a best effort to map an appropriate IPv4 address to support E9-1-1.</span></span> 
  
<span data-ttu-id="22206-259">不支持使用 IPv6 地址的位置信息服务。</span><span class="sxs-lookup"><span data-stu-id="22206-259">Location Information service with IPv6 addresses is not supported.</span></span>
  
<span data-ttu-id="22206-p110">Exchange 统一消息 (UM) 不支持 IPv6。对于 Exchange UM，请确保 DNS 解析不会返回 IPv6 地址。使用 IPv6 可能会在将呼叫发送至语音信箱时导致失败。</span><span class="sxs-lookup"><span data-stu-id="22206-p110">Exchange Unified Messaging (UM) does not support IPv6. For Exchange UM, be sure that DNS resolution does not return an IPv6 address. Using IPv6 may cause failure when calls are sent to voice mail.</span></span> 
  
### <a name="other-skype-for-business-server-feature-support-for-ipv6"></a><span data-ttu-id="22206-263">业务服务器功能支持 IPv6 的其他 Skype</span><span class="sxs-lookup"><span data-stu-id="22206-263">Other Skype for Business Server Feature Support for IPv6</span></span>
<span data-ttu-id="22206-264"><a name="Ent_V"> </a></span><span class="sxs-lookup"><span data-stu-id="22206-264"></span></span>

<span data-ttu-id="22206-265">除了中的功能和组件前面提到的业务服务器的 Skype 对以下功能支持 IPv6:</span><span class="sxs-lookup"><span data-stu-id="22206-265">In addition to the features and components mentioned previously, Skype for Business Server supports IPv6 for the following features:</span></span>
  
- <span data-ttu-id="22206-266">**持久聊天**</span><span class="sxs-lookup"><span data-stu-id="22206-266">**Persistent Chat**</span></span>
    
    <span data-ttu-id="22206-267">使用拓扑生成器的持久聊天配置 IPv6。</span><span class="sxs-lookup"><span data-stu-id="22206-267">You configure IPv6 for Persistent Chat by using Topology Builder.</span></span> <span data-ttu-id="22206-268">有关配置持久聊天的详细信息，请参阅 Deploying Persistent Chat Server 文档。</span><span class="sxs-lookup"><span data-stu-id="22206-268">For details about configuring Persistent Chat, see the Deploying Persistent Chat Server documentation.</span></span>
    
- <span data-ttu-id="22206-269">**用户体验质量 (QoE) 和呼叫详细信息记录 (CDR) 报告**</span><span class="sxs-lookup"><span data-stu-id="22206-269">**Quality of Experience (QoE) and call detail recording (CDR) reports**</span></span>
    
    <span data-ttu-id="22206-270">监视报告将会包括 IP 地址，因为该地址存储在监视服务器数据库中（无论类型为 IPv4 还是 IPv6）。</span><span class="sxs-lookup"><span data-stu-id="22206-270">Monitoring reports include the IP address as it is stored in the Monitoring Server database, whether of type IPv4 or IPv6.</span></span>
    
## <a name="technical-requirements-for-ipv6"></a><span data-ttu-id="22206-271">IPv6 的技术要求</span><span class="sxs-lookup"><span data-stu-id="22206-271">Technical requirements for IPv6</span></span>
<span data-ttu-id="22206-272"><a name="tech"> </a></span><span class="sxs-lookup"><span data-stu-id="22206-272"></span></span>

<span data-ttu-id="22206-273">如果您计划配置 IPv6 的 Skype 业务服务器，请谨记以下要求：</span><span class="sxs-lookup"><span data-stu-id="22206-273">If you plan to configure Skype for Business Server for IPv6, keep the following requirements in mind:</span></span>
  
- <span data-ttu-id="22206-274">若要对业务服务器与 Skype 使用 IPv6 地址，您需要创建域名系统 (DNS) 记录的记录，必须发现并解析为 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="22206-274">To use IPv6 addresses with Skype for Business Server, you need to create domain name system (DNS) records for records that must be discovered and resolved to an IPv6 address.</span></span> <span data-ttu-id="22206-275">IPv6 DNS 使用主机 AAAA (4A) 记录。</span><span class="sxs-lookup"><span data-stu-id="22206-275">IPv6 DNS uses host AAAA (quad-A) records.</span></span> <span data-ttu-id="22206-276">如果在部署中同时使用 IPv4 和 IPv6，最好同时配置和维护 IPv4 的主机 A 记录和 IPv6 的主机 AAAA 记录。</span><span class="sxs-lookup"><span data-stu-id="22206-276">If you use both IPv4 and IPv6 in your deployment, it is best to configure and maintain both host A records for IPv4 and host AAAA records for IPv6.</span></span> <span data-ttu-id="22206-277">即使将部署完全转换到 IPv6 后，仍可能需要 IPv4 DNS 主机记录以满足仍使用 IPv4 的用户。</span><span class="sxs-lookup"><span data-stu-id="22206-277">Even when you fully transition your deployment to IPv6, you may still require IPv4 DNS host records for external users who still use IPv4.</span></span>
    
    <span data-ttu-id="22206-p113">您可以在开始使用 IPv6 前部署 IPv6 DNS 主机记录。如果客户端或服务器不使用 IPv6，该记录不会被引用。切换技术将根据切换技术配置和策略决定使用哪条记录。</span><span class="sxs-lookup"><span data-stu-id="22206-p113">You can deploy IPv6 DNS host records before you start using IPv6. If the client or server doesn't use IPv6, the record will not be referenced. Transitional technologies will make the decision about which record to use, based on transition technology configuration and policies.</span></span>
    
- <span data-ttu-id="22206-281">每个 IPv6 地址都有一个作用域。</span><span class="sxs-lookup"><span data-stu-id="22206-281">Each IPv6 address has a scope.</span></span> <span data-ttu-id="22206-282">您可以使用 IPv6 寻址的三个范围是 IPv6 全局地址 （类似于公共 IPv4 地址）、 IPv6 唯一本地地址 （类似于专用的 IPv4 地址范围） 和 IPv6 链接-本地地址 （类似于自动中的专用 IP 地址Windows Server ipv4)。</span><span class="sxs-lookup"><span data-stu-id="22206-282">The three scopes that you can use for IPv6 addressing are IPv6 global addresses (similar to public IPv4 addresses), IPv6 unique local addresses (similar to the private IPv4 address ranges), and IPv6 link-local addresses (similar to automatic private IP addresses in Windows Server for IPv4).</span></span> <span data-ttu-id="22206-283">池内所有服务器都应该具有作用域相同的 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="22206-283">All the servers within a pool should have IPv6 addresses with the same scope.</span></span> 
    
> [!IMPORTANT]
> <span data-ttu-id="22206-284">IPv6 是一个复杂的主题，需要仔细规划您的网络团队和 Internet 提供商，以帮助确保您分配了在 Windows Server 级别和业务服务器级别 Skype 的地址按预期方式工作。</span><span class="sxs-lookup"><span data-stu-id="22206-284">IPv6 is a complex topic and requires careful planning with your networking team and your Internet provider to help ensure that the addresses that you assign at the Windows Server level and at the Skype for Business Server level work as expected.</span></span> <span data-ttu-id="22206-285">请参阅本主题结尾处的链接，以了解有关 IPv6 寻址和规划的其他资源。</span><span class="sxs-lookup"><span data-stu-id="22206-285">See the links at the end of this topic for additional resources on IPv6 addressing and planning.</span></span> 
  
## <a name="migration-and-coexistence-considerations-for-ipv6"></a><span data-ttu-id="22206-286">IPv6 的迁移和共存注意事项</span><span class="sxs-lookup"><span data-stu-id="22206-286">Migration and coexistence considerations for IPv6</span></span>
<span data-ttu-id="22206-287"><a name="migration"> </a></span><span class="sxs-lookup"><span data-stu-id="22206-287"></span></span>

<span data-ttu-id="22206-288">Lync Server 2010 或 Office Communications Server 不支持 IP 版本 6 (IPv6)。</span><span class="sxs-lookup"><span data-stu-id="22206-288">IP version 6 (IPv6) is not supported on Lync Server 2010 or Office Communications Server.</span></span> <span data-ttu-id="22206-289">为了试用，您可以测试 Lync Server 2010 和 Skype Business Server 双协议栈共存。</span><span class="sxs-lookup"><span data-stu-id="22206-289">For piloting purposes, you can test Lync Server 2010 and Skype for Business Server dual-stack coexistence.</span></span> <span data-ttu-id="22206-290">建议的给定中央站点的所有池都升级到 Skype 业务服务器启用 IPv6 之前 （双协议栈网络） 的任何池。</span><span class="sxs-lookup"><span data-stu-id="22206-290">We recommend that all pools for a given central site are upgraded to Skype for Business Server before you enable IPv6 (dual-stack network) for any of the pools.</span></span> <span data-ttu-id="22206-291">如果您需要为池配置仅 IPv6，则建议您在实验室环境中设置仅 IPv6 以进行测试。</span><span class="sxs-lookup"><span data-stu-id="22206-291">If you need to configure a pool for IPv6 only, we recommend that you set up an IPv6-only pool in your lab environment for testing.</span></span>
  
<span data-ttu-id="22206-292">迁移和共存期间支持下列方案：</span><span class="sxs-lookup"><span data-stu-id="22206-292">The following scenarios are supported during migration and coexistence:</span></span>
  
- <span data-ttu-id="22206-293">Skype 的业务 Server、 Lync Server 2013 和 Lync Server 2010 池处于 IPv4 模式，与 Skype 共存的企业服务器，在双协议栈模式下。</span><span class="sxs-lookup"><span data-stu-id="22206-293">Skype for Business Server, Lync Server 2013, and Lync Server 2010 pools in IPv4 mode, coexisting with Skype for Business Server in dual-stack mode.</span></span>
    
- <span data-ttu-id="22206-294">在仅 IPv6 模式下，如果存储仅 IPv6 池业务服务器池的 Skype。</span><span class="sxs-lookup"><span data-stu-id="22206-294">Skype for Business Server pool in IPv6-only mode, if the IPv6-only pool is siloed.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="22206-295">另请参阅</span><span class="sxs-lookup"><span data-stu-id="22206-295">See also</span></span>
<span data-ttu-id="22206-296"><a name="migration"> </a></span><span class="sxs-lookup"><span data-stu-id="22206-296"></span></span>

[<span data-ttu-id="22206-297">Configure IP address types in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="22206-297">Configure IP address types in Skype for Business</span></span>](ip-address-types.md)

[<span data-ttu-id="22206-298">IP 版本 6 寻址体系结构</span><span class="sxs-lookup"><span data-stu-id="22206-298">IP Version 6 Addressing Architecture</span></span>](https://tools.ietf.org/html/rfc4291)
  
[<span data-ttu-id="22206-299">IPv6 全局单播地址格式</span><span class="sxs-lookup"><span data-stu-id="22206-299">IPv6 Global Unicast Address Format</span></span>](https://tools.ietf.org/html/rfc3587)
  
[<span data-ttu-id="22206-300">唯一本地 IPv6 单播地址</span><span class="sxs-lookup"><span data-stu-id="22206-300">Unique Local IPv6 Unicast Addresses</span></span>](https://tools.ietf.org/html/rfc4193)
