---
title: Skype 会议室系统的部署概述
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99443d60-e64a-4a8a-a7bf-95f790b0ad5c
description: 阅读有关如何执行部署 Skype 会议室系统，会议房间解决方案集成的硬件和软件的优化业务会议加入 Skype 组成。
ms.openlocfilehash: 94a9b1cb7ff3f341a51944cdc678bc66e44831cb
ms.sourcegitcommit: d3c3467320a2928d3bad14a1a44a31ee5a9a988c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "25699315"
---
# <a name="deployment-planning-for-skype-room-system-in-skype-for-business"></a><span data-ttu-id="61448-103">部署规划中的业务的 Skype 的 Skype 会议室系统</span><span class="sxs-lookup"><span data-stu-id="61448-103">Deployment planning for Skype Room System in Skype for Business</span></span>
 
<span data-ttu-id="61448-104">阅读有关如何执行部署 Skype 会议室系统，会议房间解决方案集成的硬件和软件的优化业务会议加入 Skype 组成。</span><span class="sxs-lookup"><span data-stu-id="61448-104">Read about how do deploy Skype Room System, a meeting room solution consisting of integrated hardware and software that is optimized to join Skype for Business meetings.</span></span>
  
> [!NOTE]
> <span data-ttu-id="61448-105">对于此内容，Skype 的业务智能会议室系统 Crestron RL 和 Polycom CX8000 称为 Skype 会议室系统。</span><span class="sxs-lookup"><span data-stu-id="61448-105">For the purposes of this content, Skype for Business for SMART Room System, Crestron RL, and Polycom CX8000 will be referred to as Skype Room System.</span></span> 

> [!NOTE]
> <span data-ttu-id="61448-106">Skype 会议室系统 v2 是具有不同的依赖关系和部署过程的不同产品。</span><span class="sxs-lookup"><span data-stu-id="61448-106">Skype Room Systems v2 is a different product with different dependencies and deployment procedures.</span></span> <span data-ttu-id="61448-107">Skype 会议室系统 v2 的信息，请参阅[规划 Skype 会议室系统 v2](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)。</span><span class="sxs-lookup"><span data-stu-id="61448-107">For information on Skype Room Systems v2, see [Plan Skype Room Systems v2](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md).</span></span>
  
 <span data-ttu-id="61448-108">Skype 会议室系统是业务统一的通信客户端中物理会议室的业务会议优化的 Skype Skype。</span><span class="sxs-lookup"><span data-stu-id="61448-108">Skype Room System is a Skype for Business unified communications client that has been optimized for Skype for Business meetings in physical conference rooms.</span></span>
  
<span data-ttu-id="61448-109">从业务客户端 Skype 开发的 Skype 会议室 System 客户端是使用 Skype 业务 SDK。</span><span class="sxs-lookup"><span data-stu-id="61448-109">The Skype Room System client was developed from the Skype for Business client by using the Skype for Business SDK.</span></span> <span data-ttu-id="61448-110">在后台部分禁止显示在 UI 模式中运行业务客户端的 Skype。</span><span class="sxs-lookup"><span data-stu-id="61448-110">The Skype for Business client runs in the background in partial UI suppressed mode.</span></span> <span data-ttu-id="61448-111">业务客户端 Skype 控制视频库和在前面的聊天室在屏幕上的内容容器。</span><span class="sxs-lookup"><span data-stu-id="61448-111">The Skype for Business client controls the video gallery and content stage on the screen at the front of the room.</span></span> <span data-ttu-id="61448-112">Skype 会议室系统客户端提供有关用于控制会议和显示控制台体验。</span><span class="sxs-lookup"><span data-stu-id="61448-112">The Skype Room System client provides a console experience on the tabletop display for controlling the meetings.</span></span> <span data-ttu-id="61448-113">Skype 会议室系统提供了：</span><span class="sxs-lookup"><span data-stu-id="61448-113">Skype Room System provides:</span></span> 
  
- <span data-ttu-id="61448-114">一键式与会体验</span><span class="sxs-lookup"><span data-stu-id="61448-114">A one-touch meeting join experience</span></span>
    
- <span data-ttu-id="61448-115">多视图视频库的自动设置</span><span class="sxs-lookup"><span data-stu-id="61448-115">Automatic setup of multi-view video gallery</span></span> 
    
- <span data-ttu-id="61448-116">会议室前方的屏幕上的启用触摸的白板</span><span class="sxs-lookup"><span data-stu-id="61448-116">Touch-enabled white boarding on the screen at the front of the room</span></span> 
    
- <span data-ttu-id="61448-117">集成日历，可用于访问计划会议</span><span class="sxs-lookup"><span data-stu-id="61448-117">Calendar integration for access to scheduled meetings</span></span>
    
- <span data-ttu-id="61448-118">内容共享和交换</span><span class="sxs-lookup"><span data-stu-id="61448-118">Content sharing and switching</span></span> 
    
<span data-ttu-id="61448-119">本文档指导您完成业务 Server 和 Exchange Server 设置中 Skype 的 Skype 会议室系统。</span><span class="sxs-lookup"><span data-stu-id="61448-119">This document guides you through provisioning Skype Room System in Skype for Business Server and Exchange Server.</span></span> <span data-ttu-id="61448-120">请参阅您的管理员，指导您完成在会议室中设置的装置 PC 和设备提供的 Skype 会议室系统安装指南。</span><span class="sxs-lookup"><span data-stu-id="61448-120">See also the Skype Room System Installation Guide provided by your administrator, which guides you through setting up the appliance PC and devices in the meeting room.</span></span> 
  
## <a name="prerequisites"></a><span data-ttu-id="61448-121">先决条件</span><span class="sxs-lookup"><span data-stu-id="61448-121">Prerequisites</span></span>

<span data-ttu-id="61448-122">以下是 Skype 会议室系统要求：</span><span class="sxs-lookup"><span data-stu-id="61448-122">Following are the requirements for Skype Room System:</span></span> 
  
- <span data-ttu-id="61448-123">Exchange 资源邮箱帐户，促进为在 Exchange Server（首选 2013）上启用了自动发现服务的会议室安排日历计划。</span><span class="sxs-lookup"><span data-stu-id="61448-123">An Exchange resource mailbox account to facilitate calendar scheduling for the meeting rooms with AutoDiscover service enabled on Exchange Server (2013 preferred).</span></span>
    
- <span data-ttu-id="61448-124">启用业务的 Skype 会议室系统帐户上为业务服务器池 （Enterprise 或 Standard Edition） Skype Skype。</span><span class="sxs-lookup"><span data-stu-id="61448-124">A Skype for Business-enabled Skype Room System account on a Skype for Business Server pool (Enterprise or Standard Edition).</span></span>
    
- <span data-ttu-id="61448-125">Skype 会议室系统客户端设备 PC 了所有必需软件。</span><span class="sxs-lookup"><span data-stu-id="61448-125">A Skype Room System client appliance PC with all required software installed.</span></span> <span data-ttu-id="61448-126">家用电脑必须运行 Windows 7 Embedded Standard 操作系统。</span><span class="sxs-lookup"><span data-stu-id="61448-126">The appliance PC must be running Windows 7 Embedded Standard operating system.</span></span> <span data-ttu-id="61448-127">此硬件连同所有设备（显示屏、摄像头、麦克风、扬声器）由 OEM 合作伙伴提供。</span><span class="sxs-lookup"><span data-stu-id="61448-127">This hardware is provided by OEM partners along with all devices (displays, camera, microphone, speakers).</span></span>
    
- <span data-ttu-id="61448-128">如果您决定 Skype 会议室系统装置 PC 加入 Active Directory 域服务 (AD DS) 域，则必须指定不会干扰 Skype 会议室系统的组策略设置。</span><span class="sxs-lookup"><span data-stu-id="61448-128">If you decide to join the Skype Room System appliance PC to an Active Directory Domain Services (AD DS) domain, you must specify group policy settings that do not interfere with Skype Room System.</span></span> <span data-ttu-id="61448-129">或者，你可以将此家用电脑留在工作组中。</span><span class="sxs-lookup"><span data-stu-id="61448-129">Alternatively, you can leave this appliance PC in the Workgroup.</span></span> 
    
- <span data-ttu-id="61448-p106">此文档指定的运行 cmdlet 所需的合适用户权限。CsMeetingRoom cmdlet 是在 CsUser cmdlet 之后建模的。因此，运行 CsUser cmdlet 所需的所有基于角色的访问控制 (RBAC) 角色也适用于 CsMeetingRoom cmdlet。</span><span class="sxs-lookup"><span data-stu-id="61448-p106">Appropriate user rights to run the cmdlets specified in this document. The CsMeetingRoom cmdlets are modeled after the CsUser cmdlet. Therefore, all role-based access control (RBAC) roles required to run CsUser cmdlets also apply to CsMeetingRoom cmdlets.</span></span> 
    
## <a name="supported-topologies"></a><span data-ttu-id="61448-133">支持的拓扑</span><span class="sxs-lookup"><span data-stu-id="61448-133">Supported topologies</span></span>

<span data-ttu-id="61448-134">下表指示 Skype 会议室系统之间的业务和 Exchange 拓扑，本地或云中的 Skype 的各种部署的客户端互操作性：</span><span class="sxs-lookup"><span data-stu-id="61448-134">The following table indicates Skype Room System client interoperability among various deployments of Skype for Business and Exchange topologies, either on premises or in the cloud:</span></span> 
  

|<span data-ttu-id="61448-135">**拓扑**</span><span class="sxs-lookup"><span data-stu-id="61448-135">**Topology**</span></span>|<span data-ttu-id="61448-136">**AD**</span><span class="sxs-lookup"><span data-stu-id="61448-136">**AD**</span></span>|<span data-ttu-id="61448-137">**Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="61448-137">**Skype for Business**</span></span>|<span data-ttu-id="61448-138">**交换**</span><span class="sxs-lookup"><span data-stu-id="61448-138">**Exchange**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="61448-139">内部部署</span><span class="sxs-lookup"><span data-stu-id="61448-139">On premises</span></span>  <br/> |<span data-ttu-id="61448-140">内部部署</span><span class="sxs-lookup"><span data-stu-id="61448-140">On premises</span></span>  <br/> |<span data-ttu-id="61448-141">内部部署</span><span class="sxs-lookup"><span data-stu-id="61448-141">On premises</span></span>  <br/> |<span data-ttu-id="61448-142">内部部署</span><span class="sxs-lookup"><span data-stu-id="61448-142">On premises</span></span>  <br/> |
|<span data-ttu-id="61448-143">Office 365 多租户 (O365MT)</span><span class="sxs-lookup"><span data-stu-id="61448-143">Office 365 Multi-tenant (O365MT)</span></span>  <br/> |<span data-ttu-id="61448-144">Online</span><span class="sxs-lookup"><span data-stu-id="61448-144">Online</span></span>  <br/> |<span data-ttu-id="61448-145">Online</span><span class="sxs-lookup"><span data-stu-id="61448-145">Online</span></span>  <br/> |<span data-ttu-id="61448-146">联机</span><span class="sxs-lookup"><span data-stu-id="61448-146">Online</span></span>  <br/> |
|<span data-ttu-id="61448-147">Office 365 专用</span><span class="sxs-lookup"><span data-stu-id="61448-147">Office 365 Dedicated</span></span>  <br/> <span data-ttu-id="61448-148">（联系服务提供商）</span><span class="sxs-lookup"><span data-stu-id="61448-148">(Contact your service provider)</span></span>  <br/> |<span data-ttu-id="61448-149">内部部署</span><span class="sxs-lookup"><span data-stu-id="61448-149">On premises</span></span>  <br/> |<span data-ttu-id="61448-150">联机</span><span class="sxs-lookup"><span data-stu-id="61448-150">Online</span></span>  <br/> |<span data-ttu-id="61448-151">联机</span><span class="sxs-lookup"><span data-stu-id="61448-151">Online</span></span>  <br/> |
|<span data-ttu-id="61448-152">混合（拆分域）</span><span class="sxs-lookup"><span data-stu-id="61448-152">Hybrid (Split domain)</span></span>  <br/> <span data-ttu-id="61448-153">不支持</span><span class="sxs-lookup"><span data-stu-id="61448-153">Unsupported</span></span>  <br/> |<span data-ttu-id="61448-154">内部部署</span><span class="sxs-lookup"><span data-stu-id="61448-154">On premises</span></span>  <br/> <span data-ttu-id="61448-155">内部部署</span><span class="sxs-lookup"><span data-stu-id="61448-155">On premises</span></span>  <br/> <span data-ttu-id="61448-156">内部部署</span><span class="sxs-lookup"><span data-stu-id="61448-156">On premises</span></span>  <br/> |<span data-ttu-id="61448-157">内部部署</span><span class="sxs-lookup"><span data-stu-id="61448-157">On premises</span></span>  <br/> <span data-ttu-id="61448-158">联机</span><span class="sxs-lookup"><span data-stu-id="61448-158">Online</span></span>  <br/> <span data-ttu-id="61448-159">Online</span><span class="sxs-lookup"><span data-stu-id="61448-159">Online</span></span>  <br/> |<span data-ttu-id="61448-160">Online</span><span class="sxs-lookup"><span data-stu-id="61448-160">Online</span></span>  <br/> <span data-ttu-id="61448-161">联机</span><span class="sxs-lookup"><span data-stu-id="61448-161">Online</span></span>  <br/> <span data-ttu-id="61448-162">内部部署</span><span class="sxs-lookup"><span data-stu-id="61448-162">On premises</span></span>  <br/> |
   
<span data-ttu-id="61448-163">Lync Server 2013 之前的版本部分受支持。</span><span class="sxs-lookup"><span data-stu-id="61448-163">Releases prior to Lync Server 2013 are partially supported.</span></span> <span data-ttu-id="61448-164">在以下情况下，Skype 会议室系统可以参加 Skype 业务会议 （由用户安排的那些驻留在 Lync Server 2010），只要会议是"公共"，这意味着会议不为自定义受限制的访问。</span><span class="sxs-lookup"><span data-stu-id="61448-164">In these scenarios, Skype Room System can participate in Skype for Business conferences (those that are scheduled by users homed on Lync Server 2010) as long as the conferences are "public," meaning the conferences aren't customized for restricted access.</span></span> 
  
<span data-ttu-id="61448-165">Skype 会议室系统无法早于 Lync Server 2013 驻留在 Lync server 版本上。</span><span class="sxs-lookup"><span data-stu-id="61448-165">Skype Room System cannot be homed on a Lync server version earlier than Lync Server 2013.</span></span> <span data-ttu-id="61448-166">当 Skype 会议室系统无法连接到 Exchange 检索日历设置--例如，没有为 Skype 会议室系统帐户配置不 Exchange 邮箱或无法访问 Exchange-时立即开会和临时会议将工作，但加入不会预定的会议。</span><span class="sxs-lookup"><span data-stu-id="61448-166">When a Skype Room System cannot connect to Exchange to retrieve calendar settings--for example, when there is no Exchange mailbox configured for the Skype Room System account or Exchange cannot be accessed--Meet Now and ad hoc conferencing will work, but joining a scheduled meeting will not.</span></span> 
  
<span data-ttu-id="61448-167">下表指示 Skype 会议室系统与 Exchange Server 版本的客户端可支持性：</span><span class="sxs-lookup"><span data-stu-id="61448-167">The following table indicates Skype Room System client supportability with versions of Exchange Server:</span></span> 
  

|<span data-ttu-id="61448-168">**交换**</span><span class="sxs-lookup"><span data-stu-id="61448-168">**Exchange**</span></span>|<span data-ttu-id="61448-169">**内部部署**</span><span class="sxs-lookup"><span data-stu-id="61448-169">**On premises**</span></span>|<span data-ttu-id="61448-170">**Online**</span><span class="sxs-lookup"><span data-stu-id="61448-170">**Online**</span></span>|<span data-ttu-id="61448-171">**混合**</span><span class="sxs-lookup"><span data-stu-id="61448-171">**Hybrid**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="61448-172">Exchange 2010</span><span class="sxs-lookup"><span data-stu-id="61448-172">Exchange 2010</span></span>  <br/> |<span data-ttu-id="61448-173">是（仅限单林）</span><span class="sxs-lookup"><span data-stu-id="61448-173">Yes (single forest only)</span></span>  <br/> |<span data-ttu-id="61448-174">不适用</span><span class="sxs-lookup"><span data-stu-id="61448-174">N/A</span></span>  <br/> |<span data-ttu-id="61448-175">不适用</span><span class="sxs-lookup"><span data-stu-id="61448-175">N/A</span></span>  <br/> |
|<span data-ttu-id="61448-176">Exchange 2013</span><span class="sxs-lookup"><span data-stu-id="61448-176">Exchange 2013</span></span>  <br/> |<span data-ttu-id="61448-177">是（多林支持适用于 Exchange 2013 CU6 和更高版本）</span><span class="sxs-lookup"><span data-stu-id="61448-177">Yes (multi forest support available for Exchange 2013 CU6 and later versions)</span></span>  <br/> |<span data-ttu-id="61448-178">是</span><span class="sxs-lookup"><span data-stu-id="61448-178">Yes</span></span>  <br/> |<span data-ttu-id="61448-179">是</span><span class="sxs-lookup"><span data-stu-id="61448-179">Yes</span></span>  <br/> |
|<span data-ttu-id="61448-180">Exchange 2016</span><span class="sxs-lookup"><span data-stu-id="61448-180">Exchange 2016</span></span>  <br/> |<span data-ttu-id="61448-181">是 （多林提供支持）</span><span class="sxs-lookup"><span data-stu-id="61448-181">Yes (multi forest support available)</span></span>  <br/> |<span data-ttu-id="61448-182">是</span><span class="sxs-lookup"><span data-stu-id="61448-182">Yes</span></span>  <br/> |<span data-ttu-id="61448-183">是</span><span class="sxs-lookup"><span data-stu-id="61448-183">Yes</span></span>  <br/> |
   

