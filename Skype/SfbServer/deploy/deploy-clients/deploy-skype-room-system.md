---
title: 在 Skype for Business Server 中部署 Skype 会议室系统
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/6/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99443d60-e64a-4a8a-a7bf-95f790b0ad5c
description: 了解如何执行部署 Skype 的空间系统，会议房间解决方案包含集成的硬件和软件的优化加入 Skype 业务会议。
ms.openlocfilehash: 11cbae1cdbdd0585a2ea67625179ee7862309723
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-skype-room-system-in-skype-for-business-server"></a><span data-ttu-id="4979c-103">在 Skype for Business Server 中部署 Skype 会议室系统</span><span class="sxs-lookup"><span data-stu-id="4979c-103">Deploy Skype Room System in Skype for Business Server</span></span>
 
<span data-ttu-id="4979c-104">了解如何执行部署 Skype 的空间系统，会议房间解决方案包含集成的硬件和软件的优化加入 Skype 业务会议。</span><span class="sxs-lookup"><span data-stu-id="4979c-104">Read about how do deploy Skype Room System, a meeting room solution consisting of integrated hardware and software that is optimized to join Skype for Business meetings.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4979c-105">为此目的内容、 业务智能的空间系统，Crestron RL 的 Skype 和 Polycom CX8000 称为 Skype 的空间系统。</span><span class="sxs-lookup"><span data-stu-id="4979c-105">For the purposes of this content, Skype for Business for SMART Room System, Crestron RL, and Polycom CX8000 will be referred to as Skype Room System.</span></span> 
  
 <span data-ttu-id="4979c-106">Skype 的空间系统是物理的会议室中的业务会议优化的 Skype 业务统一的通信客户端的 Skype。</span><span class="sxs-lookup"><span data-stu-id="4979c-106">Skype Room System is a Skype for Business unified communications client that has been optimized for Skype for Business meetings in physical conference rooms.</span></span>
  
<span data-ttu-id="4979c-107">Skype 的空间系统客户端的开发是从业务客户端的 Skype 通过 Skype 业务 SDK。</span><span class="sxs-lookup"><span data-stu-id="4979c-107">The Skype Room System client was developed from the Skype for Business client by using the Skype for Business SDK.</span></span> <span data-ttu-id="4979c-108">在部分抑制的 UI 模式在后台运行业务客户端的 Skype。</span><span class="sxs-lookup"><span data-stu-id="4979c-108">The Skype for Business client runs in the background in partial UI suppressed mode.</span></span> <span data-ttu-id="4979c-109">Skype 业务客户端控制的视频库和内容舞台前部文件室的屏幕上。</span><span class="sxs-lookup"><span data-stu-id="4979c-109">The Skype for Business client controls the video gallery and content stage on the screen at the front of the room.</span></span> <span data-ttu-id="4979c-110">Skype 的空间系统客户端提供用于控制会议和显示控制台体验。</span><span class="sxs-lookup"><span data-stu-id="4979c-110">The Skype Room System client provides a console experience on the tabletop display for controlling the meetings.</span></span> <span data-ttu-id="4979c-111">Skype 的空间系统提供了：</span><span class="sxs-lookup"><span data-stu-id="4979c-111">Skype Room System provides:</span></span> 
  
- <span data-ttu-id="4979c-112">一键式与会体验</span><span class="sxs-lookup"><span data-stu-id="4979c-112">A one-touch meeting join experience</span></span>
    
- <span data-ttu-id="4979c-113">多视图视频库的自动设置</span><span class="sxs-lookup"><span data-stu-id="4979c-113">Automatic setup of multi-view video gallery</span></span> 
    
- <span data-ttu-id="4979c-114">会议室前方的屏幕上的启用触摸的白板</span><span class="sxs-lookup"><span data-stu-id="4979c-114">Touch-enabled white boarding on the screen at the front of the room</span></span> 
    
- <span data-ttu-id="4979c-115">集成日历，可用于访问计划会议</span><span class="sxs-lookup"><span data-stu-id="4979c-115">Calendar integration for access to scheduled meetings</span></span>
    
- <span data-ttu-id="4979c-116">内容共享和交换</span><span class="sxs-lookup"><span data-stu-id="4979c-116">Content sharing and switching</span></span> 
    
<span data-ttu-id="4979c-117">本文档将指导您完成配置业务服务器和 Exchange Server Skype 在 Skype 的空间系统。</span><span class="sxs-lookup"><span data-stu-id="4979c-117">This document guides you through provisioning Skype Room System in Skype for Business Server and Exchange Server.</span></span> <span data-ttu-id="4979c-118">另请参阅由您的管理员联系，将引导您完成在会议室中设置的装置 PC 和设备提供 Skype 的空间系统安装指南。</span><span class="sxs-lookup"><span data-stu-id="4979c-118">See also the Skype Room System Installation Guide provided by your administrator, which guides you through setting up the appliance PC and devices in the meeting room.</span></span> 
  
## <a name="prerequisites"></a><span data-ttu-id="4979c-119">先决条件</span><span class="sxs-lookup"><span data-stu-id="4979c-119">Prerequisites</span></span>

<span data-ttu-id="4979c-120">Skype 的空间系统的要求如下：</span><span class="sxs-lookup"><span data-stu-id="4979c-120">Following are the requirements for Skype Room System:</span></span> 
  
- <span data-ttu-id="4979c-121">Exchange 资源邮箱帐户，促进为在 Exchange Server（首选 2013）上启用了自动发现服务的会议室安排日历计划。</span><span class="sxs-lookup"><span data-stu-id="4979c-121">An Exchange resource mailbox account to facilitate calendar scheduling for the meeting rooms with AutoDiscover service enabled on Exchange Server (2013 preferred).</span></span>
    
- <span data-ttu-id="4979c-122">启用业务的 Skype 的空间系统帐户业务服务器池 （企业版或标准版） Skype 上 Skype。</span><span class="sxs-lookup"><span data-stu-id="4979c-122">A Skype for Business-enabled Skype Room System account on a Skype for Business Server pool (Enterprise or Standard Edition).</span></span>
    
- <span data-ttu-id="4979c-123">Skype 的空间系统客户端装置的 PC 安装所需的全部软件。</span><span class="sxs-lookup"><span data-stu-id="4979c-123">A Skype Room System client appliance PC with all required software installed.</span></span> <span data-ttu-id="4979c-124">家用电脑必须运行 Windows 7 Embedded Standard 操作系统。</span><span class="sxs-lookup"><span data-stu-id="4979c-124">The appliance PC must be running Windows 7 Embedded Standard operating system.</span></span> <span data-ttu-id="4979c-125">此硬件连同所有设备（显示屏、摄像头、麦克风、扬声器）由 OEM 合作伙伴提供。</span><span class="sxs-lookup"><span data-stu-id="4979c-125">This hardware is provided by OEM partners along with all devices (displays, camera, microphone, speakers).</span></span>
    
- <span data-ttu-id="4979c-126">如果您决定将 Skype 的空间系统装置电脑加入到 Active Directory 域服务 (AD DS) 域，您必须指定组策略设置不会影响与 Skype 的空间系统。</span><span class="sxs-lookup"><span data-stu-id="4979c-126">If you decide to join the Skype Room System appliance PC to an Active Directory Domain Services (AD DS) domain, you must specify group policy settings that do not interfere with Skype Room System.</span></span> <span data-ttu-id="4979c-127">或者，你可以将此家用电脑留在工作组中。</span><span class="sxs-lookup"><span data-stu-id="4979c-127">Alternatively, you can leave this appliance PC in the Workgroup.</span></span> 
    
- <span data-ttu-id="4979c-p105">此文档指定的运行 cmdlet 所需的合适用户权限。CsMeetingRoom cmdlet 是在 CsUser cmdlet 之后建模的。因此，运行 CsUser cmdlet 所需的所有基于角色的访问控制 (RBAC) 角色也适用于 CsMeetingRoom cmdlet。</span><span class="sxs-lookup"><span data-stu-id="4979c-p105">Appropriate user rights to run the cmdlets specified in this document. The CsMeetingRoom cmdlets are modeled after the CsUser cmdlet. Therefore, all role-based access control (RBAC) roles required to run CsUser cmdlets also apply to CsMeetingRoom cmdlets.</span></span> 
    
## <a name="supported-topologies"></a><span data-ttu-id="4979c-131">支持的拓扑</span><span class="sxs-lookup"><span data-stu-id="4979c-131">Supported topologies</span></span>

<span data-ttu-id="4979c-132">下表指示 Skype 的空间系统之间各种业务和 Exchange 拓扑结构，在内部或在云中的 Skype 的部署的客户端互操作性：</span><span class="sxs-lookup"><span data-stu-id="4979c-132">The following table indicates Skype Room System client interoperability among various deployments of Skype for Business and Exchange topologies, either on premises or in the cloud:</span></span> 
  

|<span data-ttu-id="4979c-133">**拓扑**</span><span class="sxs-lookup"><span data-stu-id="4979c-133">**Topology**</span></span>|<span data-ttu-id="4979c-134">**广告**</span><span class="sxs-lookup"><span data-stu-id="4979c-134">**AD**</span></span>|<span data-ttu-id="4979c-135">**Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="4979c-135">**Skype for Business**</span></span>|<span data-ttu-id="4979c-136">**Exchange**</span><span class="sxs-lookup"><span data-stu-id="4979c-136">**Exchange**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4979c-137">内部部署</span><span class="sxs-lookup"><span data-stu-id="4979c-137">On premises</span></span>  <br/> |<span data-ttu-id="4979c-138">内部部署</span><span class="sxs-lookup"><span data-stu-id="4979c-138">On premises</span></span>  <br/> |<span data-ttu-id="4979c-139">内部部署</span><span class="sxs-lookup"><span data-stu-id="4979c-139">On premises</span></span>  <br/> |<span data-ttu-id="4979c-140">内部部署</span><span class="sxs-lookup"><span data-stu-id="4979c-140">On premises</span></span>  <br/> |
|<span data-ttu-id="4979c-141">Office 365 多租户 (O365MT)</span><span class="sxs-lookup"><span data-stu-id="4979c-141">Office 365 Multi-tenant (O365MT)</span></span>  <br/> |<span data-ttu-id="4979c-142">Online</span><span class="sxs-lookup"><span data-stu-id="4979c-142">Online</span></span>  <br/> |<span data-ttu-id="4979c-143">Online</span><span class="sxs-lookup"><span data-stu-id="4979c-143">Online</span></span>  <br/> |<span data-ttu-id="4979c-144">联机</span><span class="sxs-lookup"><span data-stu-id="4979c-144">Online</span></span>  <br/> |
|<span data-ttu-id="4979c-145">Office 365 专用</span><span class="sxs-lookup"><span data-stu-id="4979c-145">Office 365 Dedicated</span></span>  <br/> <span data-ttu-id="4979c-146">（请联系您的服务提供商）</span><span class="sxs-lookup"><span data-stu-id="4979c-146">(Contact your service provider)</span></span>  <br/> |<span data-ttu-id="4979c-147">内部部署</span><span class="sxs-lookup"><span data-stu-id="4979c-147">On premises</span></span>  <br/> |<span data-ttu-id="4979c-148">联机</span><span class="sxs-lookup"><span data-stu-id="4979c-148">Online</span></span>  <br/> |<span data-ttu-id="4979c-149">联机</span><span class="sxs-lookup"><span data-stu-id="4979c-149">Online</span></span>  <br/> |
|<span data-ttu-id="4979c-150">混合（拆分域）</span><span class="sxs-lookup"><span data-stu-id="4979c-150">Hybrid (Split domain)</span></span>  <br/> <span data-ttu-id="4979c-151">不支持</span><span class="sxs-lookup"><span data-stu-id="4979c-151">Unsupported</span></span>  <br/> |<span data-ttu-id="4979c-152">内部部署</span><span class="sxs-lookup"><span data-stu-id="4979c-152">On premises</span></span>  <br/> <span data-ttu-id="4979c-153">内部部署</span><span class="sxs-lookup"><span data-stu-id="4979c-153">On premises</span></span>  <br/> <span data-ttu-id="4979c-154">内部部署</span><span class="sxs-lookup"><span data-stu-id="4979c-154">On premises</span></span>  <br/> |<span data-ttu-id="4979c-155">内部部署</span><span class="sxs-lookup"><span data-stu-id="4979c-155">On premises</span></span>  <br/> <span data-ttu-id="4979c-156">联机</span><span class="sxs-lookup"><span data-stu-id="4979c-156">Online</span></span>  <br/> <span data-ttu-id="4979c-157">Online</span><span class="sxs-lookup"><span data-stu-id="4979c-157">Online</span></span>  <br/> |<span data-ttu-id="4979c-158">Online</span><span class="sxs-lookup"><span data-stu-id="4979c-158">Online</span></span>  <br/> <span data-ttu-id="4979c-159">联机</span><span class="sxs-lookup"><span data-stu-id="4979c-159">Online</span></span>  <br/> <span data-ttu-id="4979c-160">内部部署</span><span class="sxs-lookup"><span data-stu-id="4979c-160">On premises</span></span>  <br/> |
   
<span data-ttu-id="4979c-161">Lync Server 2013 之前的版本部分受支持。</span><span class="sxs-lookup"><span data-stu-id="4979c-161">Releases prior to Lync Server 2013 are partially supported.</span></span> <span data-ttu-id="4979c-162">在这些方案中，Skype 的空间系统可以参与 Skype （那些由用户计划宿主 Lync Server 2010） 的业务会议，只要会议是"公用"，意味着会议不为自定义的受限制的访问。</span><span class="sxs-lookup"><span data-stu-id="4979c-162">In these scenarios, Skype Room System can participate in Skype for Business conferences (those that are scheduled by users homed on Lync Server 2010) as long as the conferences are "public," meaning the conferences aren't customized for restricted access.</span></span> 
  
<span data-ttu-id="4979c-163">Skype 的空间系统不能早于 Lync Server 2013 穴 Lync 服务器版本上。</span><span class="sxs-lookup"><span data-stu-id="4979c-163">Skype Room System cannot be homed on a Lync server version earlier than Lync Server 2013.</span></span> <span data-ttu-id="4979c-164">当 Skype 的空间系统无法连接到 Exchange 可检索日历设置--例如，当 Skype 的空间系统帐户配置没有 Exchange 邮箱或不能访问 Exchange-立即开会和特别会议将工作，但加入已安排的会议不会。</span><span class="sxs-lookup"><span data-stu-id="4979c-164">When a Skype Room System cannot connect to Exchange to retrieve calendar settings--for example, when there is no Exchange mailbox configured for the Skype Room System account or Exchange cannot be accessed--Meet Now and ad hoc conferencing will work, but joining a scheduled meeting will not.</span></span> 
  
<span data-ttu-id="4979c-165">下表指示 Skype 的空间系统客户端支持的 Exchange Server 版本：</span><span class="sxs-lookup"><span data-stu-id="4979c-165">The following table indicates Skype Room System client supportability with versions of Exchange Server:</span></span> 
  

|<span data-ttu-id="4979c-166">**Exchange**</span><span class="sxs-lookup"><span data-stu-id="4979c-166">**Exchange**</span></span>|<span data-ttu-id="4979c-167">**内部部署**</span><span class="sxs-lookup"><span data-stu-id="4979c-167">**On premises**</span></span>|<span data-ttu-id="4979c-168">**联机**</span><span class="sxs-lookup"><span data-stu-id="4979c-168">**Online**</span></span>|<span data-ttu-id="4979c-169">**混合**</span><span class="sxs-lookup"><span data-stu-id="4979c-169">**Hybrid**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4979c-170">Exchange 2010</span><span class="sxs-lookup"><span data-stu-id="4979c-170">Exchange 2010</span></span>  <br/> |<span data-ttu-id="4979c-171">是（仅限单林）</span><span class="sxs-lookup"><span data-stu-id="4979c-171">Yes (single forest only)</span></span>  <br/> |<span data-ttu-id="4979c-172">不适用</span><span class="sxs-lookup"><span data-stu-id="4979c-172">N/A</span></span>  <br/> |<span data-ttu-id="4979c-173">不适用</span><span class="sxs-lookup"><span data-stu-id="4979c-173">N/A</span></span>  <br/> |
|<span data-ttu-id="4979c-174">Exchange 2013</span><span class="sxs-lookup"><span data-stu-id="4979c-174">Exchange 2013</span></span>  <br/> |<span data-ttu-id="4979c-175">是（多林支持适用于 Exchange 2013 CU6 和更高版本）</span><span class="sxs-lookup"><span data-stu-id="4979c-175">Yes (multi forest support available for Exchange 2013 CU6 and later versions)</span></span>  <br/> |<span data-ttu-id="4979c-176">是</span><span class="sxs-lookup"><span data-stu-id="4979c-176">Yes</span></span>  <br/> |<span data-ttu-id="4979c-177">是</span><span class="sxs-lookup"><span data-stu-id="4979c-177">Yes</span></span>  <br/> |
|<span data-ttu-id="4979c-178">Exchange 2016</span><span class="sxs-lookup"><span data-stu-id="4979c-178">Exchange 2016</span></span>  <br/> |<span data-ttu-id="4979c-179">是 （多目录林提供支持）</span><span class="sxs-lookup"><span data-stu-id="4979c-179">Yes (multi forest support available)</span></span>  <br/> |<span data-ttu-id="4979c-180">是</span><span class="sxs-lookup"><span data-stu-id="4979c-180">Yes</span></span>  <br/> |<span data-ttu-id="4979c-181">是</span><span class="sxs-lookup"><span data-stu-id="4979c-181">Yes</span></span>  <br/> |
   

