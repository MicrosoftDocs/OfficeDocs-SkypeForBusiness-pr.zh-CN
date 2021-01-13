---
title: Plan for Call Park in Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.assetid: 985dc326-0aef-4308-b98b-c1d0069311e7
description: 在 Skype for Business Server 企业语音中规划呼叫企业语音，从而将呼叫置于保持状态，以及将呼叫转接到部门。 包括容量规划、支持的呼叫和支持的客户端。
ms.openlocfilehash: c324e8d61f6d0e9e67870f05597a9157965a3eb3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825922"
---
# <a name="plan-for-call-park-in-skype-for-business"></a><span data-ttu-id="72308-104">Plan for Call Park in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="72308-104">Plan for Call Park in Skype for Business</span></span>
 
<span data-ttu-id="72308-105">在 Skype for Business Server 企业语音中规划呼叫企业语音，从而将呼叫置于保持状态，以及将呼叫转接到部门。</span><span class="sxs-lookup"><span data-stu-id="72308-105">Planning for call park in Skype for Business Server Enterprise Voice, which enables putting calls on hold and transferring calls to departments.</span></span> <span data-ttu-id="72308-106">包括容量规划、支持的呼叫和支持的客户端。</span><span class="sxs-lookup"><span data-stu-id="72308-106">Includes capacity planning, supported calls, and supported clients.</span></span>
  
<span data-ttu-id="72308-107">呼叫企业语音使用户可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="72308-107">The Call Park application enables Enterprise Voice users to do the following:</span></span>
  
- <span data-ttu-id="72308-108">将呼叫置于保持状态，然后从同一电话或其他电话检索呼叫。</span><span class="sxs-lookup"><span data-stu-id="72308-108">Put a call on hold and then retrieve the call from the same phone or another phone.</span></span>
    
- <span data-ttu-id="72308-109">将呼叫置于保留状态，以将呼叫转接到部门或 (区域，例如，销售部门或有公用区域电话) 。</span><span class="sxs-lookup"><span data-stu-id="72308-109">Put a call on hold to transfer it to a department or general area (for example, to a sales department or a warehouse where there is a common area phone).</span></span>
    
- <span data-ttu-id="72308-110">将呼叫置于保持状态，并保持原始应答电话对于其他呼叫是免费的。</span><span class="sxs-lookup"><span data-stu-id="72308-110">Put a call on hold and keep the original answering phone free for other calls.</span></span>
    
<span data-ttu-id="72308-111">当用户拨打呼叫时，Skype for Business Server 将呼叫转接到一个称为通道的临时号码，在此通道中，呼叫将一直持续到取回或取回时间。Skype for Business Server 将通道发送给等待呼叫的用户。</span><span class="sxs-lookup"><span data-stu-id="72308-111">When a user parks a call, Skype for Business Server transfers the call to a temporary number, called an orbit, where the call is held until it is retrieved or it times out. Skype for Business Server sends the orbit to the user who parked the call.</span></span> <span data-ttu-id="72308-112">若要检索已呼叫，用户可以拨打通道号码或单击"对话"窗口中的通道链接或按钮。</span><span class="sxs-lookup"><span data-stu-id="72308-112">To retrieve the parked call, the user can dial the orbit number or click the orbit link or button in the Conversation window.</span></span> 
  
<span data-ttu-id="72308-113">通过外部机制（如即时消息 (IM) 或分页系统）将通道号码传达给其他人，可通知呼叫的呼叫。</span><span class="sxs-lookup"><span data-stu-id="72308-113">The user who parked a call can notify someone to retrieve the call by using an external mechanism, such as instant messaging (IM) or a paging system, to communicate the orbit number to someone else.</span></span> <span data-ttu-id="72308-114">在取回呼叫时，将呼叫的保留为"对话"窗口的用户可以保持打开状态以接收通知。</span><span class="sxs-lookup"><span data-stu-id="72308-114">The user who parked the call can leave the Conversation window open to receive notification when the call is retrieved.</span></span>
  
<span data-ttu-id="72308-115">由于通道范围在全局范围内是唯一的，因此，如果路由配置得当，可以从任何 Skype for Business Server 站点或 PBX 电话检索呼叫。</span><span class="sxs-lookup"><span data-stu-id="72308-115">Because orbit ranges are globally unique, it is possible to retrieve calls from any Skype for Business Server site or PBX phone if routing is configured appropriately.</span></span> <span data-ttu-id="72308-116">如果在可配置的时间范围内没有人取回呼叫，呼叫将回响到该呼叫的接听人。</span><span class="sxs-lookup"><span data-stu-id="72308-116">If no one retrieves the call within a configurable amount of time, the call rings back to the person who parked it.</span></span> <span data-ttu-id="72308-117">如果此人未应答回叫，则呼叫将转接到回退目标，如已配置话务员。</span><span class="sxs-lookup"><span data-stu-id="72308-117">If that person does not answer the ringback, the call is transferred to a fallback destination, such as to an operator, if so configured.</span></span> <span data-ttu-id="72308-118">可以配置呼叫在从 1 到 10 次转接之前回叫次数。</span><span class="sxs-lookup"><span data-stu-id="72308-118">You can configure the number of times the call rings back before being transferred from one to ten times.</span></span> <span data-ttu-id="72308-119">如果没有人应答转接的呼叫，则呼叫将断开连接。</span><span class="sxs-lookup"><span data-stu-id="72308-119">If no one answers a transferred call, the call is disconnected.</span></span> <span data-ttu-id="72308-120">检索或断开呼叫时，将释放通道。</span><span class="sxs-lookup"><span data-stu-id="72308-120">The orbit is freed when the call is retrieved or disconnected.</span></span>
  
<span data-ttu-id="72308-121">部署呼叫库时，需要保留用于呼叫等待的分机号码范围。</span><span class="sxs-lookup"><span data-stu-id="72308-121">When you deploy Call Park, you need to reserve ranges of extension numbers for parking calls.</span></span> <span data-ttu-id="72308-122">这些分机需要为虚拟分机：未为其分配用户或电话的分机。</span><span class="sxs-lookup"><span data-stu-id="72308-122">These extensions need to be virtual extensions: extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="72308-123">然后，使用分机号码范围配置呼叫托管通道表，并指定哪个应用程序服务托管处理每个范围的呼叫托管应用程序。</span><span class="sxs-lookup"><span data-stu-id="72308-123">You then configure the call park orbit table with the ranges of extension numbers and specify which Application service hosts the Call Park application that handles each range.</span></span> <span data-ttu-id="72308-124">每个前端池在相应的后端服务器上都有一个呼叫停止表，该表用于管理池中的呼叫。</span><span class="sxs-lookup"><span data-stu-id="72308-124">Each Front End pool has a Call Park table on the corresponding Back End Server that is used to manage calls that are parked on the pool.</span></span> <span data-ttu-id="72308-125">通道范围列表存储在中央管理存储中，用于将通道路由到目标池。</span><span class="sxs-lookup"><span data-stu-id="72308-125">The list of orbit ranges is stored in Central Management store and is used to route orbits to the destination pool.</span></span> <span data-ttu-id="72308-126">部署和配置呼叫库应用程序的每个 Skype for Business Server 池可以有一个或多个通道范围。</span><span class="sxs-lookup"><span data-stu-id="72308-126">Each Skype for Business Server pool where the Call Park application is deployed and configured can have one or more orbit ranges.</span></span> <span data-ttu-id="72308-127">通道范围必须在 Skype for Business Server 部署中具有全局唯一性。</span><span class="sxs-lookup"><span data-stu-id="72308-127">Orbit ranges must be globally unique across the Skype for Business Server deployment.</span></span> 
  
<span data-ttu-id="72308-128">还可以配置其他呼叫离开设置，例如呼叫的重定向位置（如果呼叫时间过长）以及电话上的人在离开时是否听到音乐。</span><span class="sxs-lookup"><span data-stu-id="72308-128">You also configure other Call Park settings, such as where calls are redirected if they time out and whether the person on the phone hears music while parked.</span></span> <span data-ttu-id="72308-129">还可以指定呼叫保持时要播放的音乐文件。</span><span class="sxs-lookup"><span data-stu-id="72308-129">You can also specify the music file to play while the call is on hold.</span></span>
  
> [!NOTE]
> <span data-ttu-id="72308-130">呼叫保留的自定义保持音乐文件不会作为 Skype for Business Server 灾难恢复过程的一部分进行备份，如果上载到池的文件已损坏、已损坏或擦除，将会丢失。</span><span class="sxs-lookup"><span data-stu-id="72308-130">Customized music-on-hold files for Call Park are not backed up as part of the Skype for Business Server disaster recovery process and will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span> <span data-ttu-id="72308-131">始终保留为呼叫保留上载的自定义保持音乐文件的单独备份副本。</span><span class="sxs-lookup"><span data-stu-id="72308-131">Always keep a separate backup copy of the customized music-on-hold files that you have uploaded for Call Park.</span></span> 
  
<span data-ttu-id="72308-132">呼叫 Park 应用程序是呼叫企业语音。</span><span class="sxs-lookup"><span data-stu-id="72308-132">The Call Park application is a component of Enterprise Voice.</span></span> <span data-ttu-id="72308-133">部署呼叫企业语音，将自动安装并激活呼叫停止应用程序。</span><span class="sxs-lookup"><span data-stu-id="72308-133">When you deploy Enterprise Voice, the Call Park application is installed and activated automatically.</span></span> <span data-ttu-id="72308-134">但是，在可以使用呼叫企业语音管理员必须通过语音策略配置呼叫企业语音为用户启用它。</span><span class="sxs-lookup"><span data-stu-id="72308-134">Before you can use Call Park, however, the Enterprise Voice administrator must configure it and enable it for users through voice policy.</span></span>
  
## <a name="deployment-and-requirements"></a><span data-ttu-id="72308-135">部署和要求</span><span class="sxs-lookup"><span data-stu-id="72308-135">Deployment and requirements</span></span>

<span data-ttu-id="72308-136">部署呼叫停止应用程序时，会自动安装企业语音。</span><span class="sxs-lookup"><span data-stu-id="72308-136">The Call Park application is automatically installed when you deploy Enterprise Voice.</span></span> <span data-ttu-id="72308-137">通过配置语音策略启用呼叫管理。</span><span class="sxs-lookup"><span data-stu-id="72308-137">You enable Call Park by configuring voice policy.</span></span>
  
### <a name="software-requirements"></a><span data-ttu-id="72308-138">软件要求</span><span class="sxs-lookup"><span data-stu-id="72308-138">Software requirements</span></span>

<span data-ttu-id="72308-139">部署呼叫库的所有前端服务器和 Standard Edition Server 都必须为运行 Windows Server 2008 R2 的服务器安装 Windows Media Format Runtime，或为运行 Windows Server 2012 或 Windows Server 2012 R2 的服务器安装 Microsoft Media Foundation。</span><span class="sxs-lookup"><span data-stu-id="72308-139">All Front End Servers and Standard Edition servers where Call Park is deployed must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="72308-140">对于 Windows Server 2008 R2，Windows Media Format Runtime 作为 Windows 桌面体验的一部分进行安装。</span><span class="sxs-lookup"><span data-stu-id="72308-140">For Windows Server 2008 R2, Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span> <span data-ttu-id="72308-141">呼叫库播放保持音乐的 Windows Media Audio (.wma) 需要 Windows Media Format Runtime 或 Microsoft Media Foundation。</span><span class="sxs-lookup"><span data-stu-id="72308-141">Windows Media Format Runtime or Microsoft Media Foundation is required for Windows Media Audio (.wma) files that Call Park plays for music on hold.</span></span>
  
### <a name="port-requirements"></a><span data-ttu-id="72308-142">端口要求</span><span class="sxs-lookup"><span data-stu-id="72308-142">Port requirements</span></span>

<span data-ttu-id="72308-143">呼叫等待应用程序对 SIP 侦听请求使用 **端口 5075。**</span><span class="sxs-lookup"><span data-stu-id="72308-143">The Call Park application uses **Port 5075**  for SIP listening requests.</span></span>
    
> [!NOTE]
> <span data-ttu-id="72308-144">此端口是默认设置，您可以使用 **Set-CsApplicationServer** cmdlet 对其进行更改。</span><span class="sxs-lookup"><span data-stu-id="72308-144">This port is a default setting that you can change by using the **Set-CsApplicationServer** cmdlet.</span></span> <span data-ttu-id="72308-145">有关此 cmdlet 的详细信息，请参阅 Lync Server 命令行管理程序文档。</span><span class="sxs-lookup"><span data-stu-id="72308-145">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>
  
### <a name="audio-file-requirements"></a><span data-ttu-id="72308-146">音频文件要求</span><span class="sxs-lookup"><span data-stu-id="72308-146">Audio File requirements</span></span>

<span data-ttu-id="72308-147">呼叫保留应用程序仅支持 Windows Media Audio (.wma) 文件用于保持音乐。</span><span class="sxs-lookup"><span data-stu-id="72308-147">The Call Park application supports only Windows Media Audio (.wma) files for music on hold.</span></span> <span data-ttu-id="72308-148">您可以使用 Microsoft Expression Encoder 4 来自定义用作保持音乐的文件。</span><span class="sxs-lookup"><span data-stu-id="72308-148">You can use the Microsoft Expression Encoder 4 to customize files for music on hold.</span></span> <span data-ttu-id="72308-149">若要下载表达式编码器 4，请参阅["Expression Encoder 4"。](https://go.microsoft.com/fwlink/p/?linkId=202843)</span><span class="sxs-lookup"><span data-stu-id="72308-149">To download Expression Encoder 4, see   ["Expression Encoder 4"](https://go.microsoft.com/fwlink/p/?linkId=202843).</span></span> <span data-ttu-id="72308-150">使用此工具将文件转换为 .wma 格式。</span><span class="sxs-lookup"><span data-stu-id="72308-150">Use the tool to convert the file to a .wma format.</span></span> <span data-ttu-id="72308-151">呼叫寄存保持音乐文件的建议格式为 Media Audio 9，44 kHz，16 位，单声道，CBR，32 kbps。</span><span class="sxs-lookup"><span data-stu-id="72308-151">The recommended format for Call Park music-on-hold files is Media Audio 9, 44 kHz, 16 bits, Mono, CBR, 32 kbps.</span></span>
  
> [!NOTE]
> <span data-ttu-id="72308-152">转换后的文件仅以 16 KHz 在电话上播放，即使录制时采用 44 KHz 也是如此。</span><span class="sxs-lookup"><span data-stu-id="72308-152">The converted file plays over the phone only at 16 kHz, even if it was recorded at 44 kHz.</span></span> 
  
## <a name="supported-clients-and-calls"></a><span data-ttu-id="72308-153">支持的客户端和呼叫</span><span class="sxs-lookup"><span data-stu-id="72308-153">Supported clients and calls</span></span>

<span data-ttu-id="72308-154">呼叫等待支持以下客户端和呼叫类型</span><span class="sxs-lookup"><span data-stu-id="72308-154">The following clients and types of calls are supported for Call Park</span></span>
  
### <a name="clients-supported-for-parking-calls"></a><span data-ttu-id="72308-155">支持寄存呼叫的客户端</span><span class="sxs-lookup"><span data-stu-id="72308-155">Clients Supported for Parking Calls</span></span>

<span data-ttu-id="72308-156">可寄存来自任意 IP、专用交换机 (PBX)、公用电话交换网 (PSTN) 或移动电话的呼叫。</span><span class="sxs-lookup"><span data-stu-id="72308-156">Calls from any IP, private branch exchange (PBX), public switched telephone network (PSTN), or mobile phone can be parked.</span></span>
  
> [!NOTE]
> <span data-ttu-id="72308-p114">只能寄存音频呼叫。不能寄存即时消息和会议。</span><span class="sxs-lookup"><span data-stu-id="72308-p114">Only audio calls can be parked. Instant messages and conferences cannot be parked.</span></span> 
  
<span data-ttu-id="72308-159">以下客户端可以使用呼叫 Park 来呼叫的呼叫：</span><span class="sxs-lookup"><span data-stu-id="72308-159">The following clients can use Call Park to park calls:</span></span>
  
- <span data-ttu-id="72308-160">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="72308-160">Skype for Business</span></span>
    
- <span data-ttu-id="72308-161">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="72308-161">Lync 2013</span></span>
    
- <span data-ttu-id="72308-162">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="72308-162">Lync 2010</span></span>
    
- <span data-ttu-id="72308-163">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="72308-163">Lync 2010 Attendant</span></span>
    
- <span data-ttu-id="72308-164">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="72308-164">Lync Phone Edition</span></span>
    
> [!NOTE]
> <span data-ttu-id="72308-165">移动电话无法使用呼叫停叫来呼叫。</span><span class="sxs-lookup"><span data-stu-id="72308-165">Mobile phones cannot use Call Park to park calls.</span></span> 
  
### <a name="clients-supported-for-retrieving-calls"></a><span data-ttu-id="72308-166">支持取回呼叫的客户端</span><span class="sxs-lookup"><span data-stu-id="72308-166">Clients Supported for Retrieving Calls</span></span>

<span data-ttu-id="72308-p115">将通道范围配置为虚拟分机块（未分配用户或电话的分机）。将通道配置为虚拟分机时，移动电话和 PSTN 电话无法取回寄存的呼叫。</span><span class="sxs-lookup"><span data-stu-id="72308-p115">Orbit ranges are configured as blocks of virtual extensions (extensions without an assigned user or phone). When you configure orbits as virtual extensions, mobile phones and PSTN phones cannot retrieve parked calls.</span></span>
  
<span data-ttu-id="72308-169">联盟用户无法取回寄存的呼叫。</span><span class="sxs-lookup"><span data-stu-id="72308-169">Federated users cannot retrieve parked calls.</span></span>
  
<span data-ttu-id="72308-170">以下客户端可以检索在呼叫 Park 上停的呼叫：</span><span class="sxs-lookup"><span data-stu-id="72308-170">The following clients can retrieve calls that are parked on Call Park:</span></span>
  
- <span data-ttu-id="72308-171">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="72308-171">Skype for Business</span></span>
    
- <span data-ttu-id="72308-172">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="72308-172">Lync 2013</span></span>
    
- <span data-ttu-id="72308-173">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="72308-173">Lync 2010</span></span>
    
- <span data-ttu-id="72308-174">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="72308-174">Lync 2010 Attendant</span></span>
    
- <span data-ttu-id="72308-175">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="72308-175">Lync Phone Edition</span></span>
    
- <span data-ttu-id="72308-176">IP 公用区域电话</span><span class="sxs-lookup"><span data-stu-id="72308-176">IP common area phones</span></span>
    
- <span data-ttu-id="72308-177">连接到 Skype for Business Server 基础结构的非 IP 电话，包括公用区域电话和 PBX (专用交换机) 电话</span><span class="sxs-lookup"><span data-stu-id="72308-177">Non-IP phones that are connected to the Skype for Business Server infrastructure, including common area phones and private branch exchange (PBX) phones</span></span>
    
## <a name="call-park-capacity-planning"></a><span data-ttu-id="72308-178">呼叫安排容量规划</span><span class="sxs-lookup"><span data-stu-id="72308-178">Call Park capacity planning</span></span>

<span data-ttu-id="72308-179">下表介绍了可以用作容量规划要求基础的呼叫等待用户模型。</span><span class="sxs-lookup"><span data-stu-id="72308-179">The following table describes the Call Park user model that you can use as the basis for capacity planning requirements.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="72308-180">请记住，对于灾难恢复容量规划，配对池的每个池都应能够处理这两个池中呼叫保留服务的工作负荷。</span><span class="sxs-lookup"><span data-stu-id="72308-180">Keep in mind that, for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for Call Park services in both pools.</span></span> 
  
<span data-ttu-id="72308-181">**呼叫寄存用户模型**</span><span class="sxs-lookup"><span data-stu-id="72308-181">**Call Park User Model**</span></span>

|<span data-ttu-id="72308-182">**跃点数**</span><span class="sxs-lookup"><span data-stu-id="72308-182">**Metric**</span></span>|<span data-ttu-id="72308-183">**每个前端池  <br/>  池 (8 台前端服务器)**</span><span class="sxs-lookup"><span data-stu-id="72308-183">**Per Front End pool  <br/>  (with 8 Front End Servers)**</span></span>|<span data-ttu-id="72308-184">**每台 Standard Edition Server**</span><span class="sxs-lookup"><span data-stu-id="72308-184">**Per Standard Edition server**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="72308-185">寄存速率</span><span class="sxs-lookup"><span data-stu-id="72308-185">Park rate</span></span>  <br/> |<span data-ttu-id="72308-186">每分钟 8 个</span><span class="sxs-lookup"><span data-stu-id="72308-186">8 per minute</span></span>  <br/> |<span data-ttu-id="72308-187">每分钟 1 个</span><span class="sxs-lookup"><span data-stu-id="72308-187">1 per minute</span></span>  <br/> |
|<span data-ttu-id="72308-188">取回寄存呼叫的速率</span><span class="sxs-lookup"><span data-stu-id="72308-188">Retrieve parked call rate</span></span>  <br/> |<span data-ttu-id="72308-189">每分钟 8 个</span><span class="sxs-lookup"><span data-stu-id="72308-189">8 per minute</span></span>  <br/> |<span data-ttu-id="72308-190">每分钟 1 个</span><span class="sxs-lookup"><span data-stu-id="72308-190">1 per minute</span></span>  <br/> |
|<span data-ttu-id="72308-191">平均寄存持续时间</span><span class="sxs-lookup"><span data-stu-id="72308-191">Average park duration</span></span>  <br/> |<span data-ttu-id="72308-192">60 秒</span><span class="sxs-lookup"><span data-stu-id="72308-192">60 seconds</span></span>  <br/> |<span data-ttu-id="72308-193">60 秒</span><span class="sxs-lookup"><span data-stu-id="72308-193">60 seconds</span></span>  <br/> |
   

