---
title: 在 Skype for Business 2015 中规划呼叫寄存
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 985dc326-0aef-4308-b98b-c1d0069311e7
description: 规划在 Skype 呼叫公园的业务服务器企业语音，这样使调用保留并将呼叫转接到部门。 包括容量规划、支持的呼叫和支持的客户端。
ms.openlocfilehash: 6198b54a93c36c2e6a2fcd28fa91f51c43fb59de
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-call-park-in-skype-for-business-2015"></a><span data-ttu-id="0b843-104">在 Skype for Business 2015 中规划呼叫寄存</span><span class="sxs-lookup"><span data-stu-id="0b843-104">Plan for Call Park in Skype for Business 2015</span></span>
 
<span data-ttu-id="0b843-105">规划在 Skype 呼叫公园的业务服务器企业语音，这样使调用保留并将呼叫转接到部门。</span><span class="sxs-lookup"><span data-stu-id="0b843-105">Planning for call park in Skype for Business Server Enterprise Voice, which enables putting calls on hold and transferring calls to departments.</span></span> <span data-ttu-id="0b843-106">包括容量规划、支持的呼叫和支持的客户端。</span><span class="sxs-lookup"><span data-stu-id="0b843-106">Includes capacity planning, supported calls, and supported clients.</span></span>
  
<span data-ttu-id="0b843-107">调用公园应用程序启用企业语音用户，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="0b843-107">The Call Park application enables Enterprise Voice users to do the following:</span></span>
  
- <span data-ttu-id="0b843-108">将呼叫置于保持状态并从同一电话或另一电话取回该呼叫。</span><span class="sxs-lookup"><span data-stu-id="0b843-108">Put a call on hold and then retrieve the call from the same phone or another phone.</span></span>
    
- <span data-ttu-id="0b843-109">将呼叫置于保持状态，以将其转接到某个部门或常规区域（例如，转接到有公用区域电话的销售部门或仓库）。</span><span class="sxs-lookup"><span data-stu-id="0b843-109">Put a call on hold to transfer it to a department or general area (for example, to a sales department or a warehouse where there is a common area phone).</span></span>
    
- <span data-ttu-id="0b843-110">将呼叫置于保持状态，并保持原始应答电话处于空闲状态，以接听其他呼叫。</span><span class="sxs-lookup"><span data-stu-id="0b843-110">Put a call on hold and keep the original answering phone free for other calls.</span></span>
    
<span data-ttu-id="0b843-111">当用户公园 Skype 业务服务器的调用，将传输调用一个称为轨道中，检索或超时之前调用地点的临时数字。Skype 业务服务器发送到停呼叫的用户运行轨道。</span><span class="sxs-lookup"><span data-stu-id="0b843-111">When a user parks a call, Skype for Business Server transfers the call to a temporary number, called an orbit, where the call is held until it is retrieved or it times out. Skype for Business Server sends the orbit to the user who parked the call.</span></span> <span data-ttu-id="0b843-112">用户可以通过拨打该通道号或单击“对话”窗口中的通道链接或按钮来取回寄存的呼叫。</span><span class="sxs-lookup"><span data-stu-id="0b843-112">To retrieve the parked call, the user can dial the orbit number or click the orbit link or button in the Conversation window.</span></span> 
  
<span data-ttu-id="0b843-p104">寄存呼叫的用户可以使用外部机制（如即时消息 (IM) 或寻呼系统）通知某人取回呼叫，以向其他人通知该通道号。寄存呼叫的用户可以使“对话”窗口保持打开状态，以在取回呼叫时接收通知。</span><span class="sxs-lookup"><span data-stu-id="0b843-p104">The user who parked a call can notify someone to retrieve the call by using an external mechanism, such as instant messaging (IM) or a paging system, to communicate the orbit number to someone else. The user who parked the call can leave the Conversation window open to receive notification when the call is retrieved.</span></span>
  
<span data-ttu-id="0b843-115">由于轨道范围是全局唯一的就可以从任何业务服务器站点或 PBX 电话 Skype 检索调用，如果路由配置正确。</span><span class="sxs-lookup"><span data-stu-id="0b843-115">Because orbit ranges are globally unique, it is possible to retrieve calls from any Skype for Business Server site or PBX phone if routing is configured appropriately.</span></span> <span data-ttu-id="0b843-116">如果在可配置的时间内没有人取回呼叫，则呼叫将回拨到寄存它的人。</span><span class="sxs-lookup"><span data-stu-id="0b843-116">If no one retrieves the call within a configurable amount of time, the call rings back to the person who parked it.</span></span> <span data-ttu-id="0b843-117">如果此人不应答回拨电话，呼叫将转接到回退目标，例如接线员（如果这样配置的话）。</span><span class="sxs-lookup"><span data-stu-id="0b843-117">If that person does not answer the ringback, the call is transferred to a fallback destination, such as to an operator, if so configured.</span></span> <span data-ttu-id="0b843-118">可以配置呼叫在转接前的回拨次数（1 到 10 次）。</span><span class="sxs-lookup"><span data-stu-id="0b843-118">You can configure the number of times the call rings back before being transferred from one to ten times.</span></span> <span data-ttu-id="0b843-119">如果没有人应答转接呼叫，则呼叫将断开连接。</span><span class="sxs-lookup"><span data-stu-id="0b843-119">If no one answers a transferred call, the call is disconnected.</span></span> <span data-ttu-id="0b843-120">呼叫取回或断开连接后会释放通道。</span><span class="sxs-lookup"><span data-stu-id="0b843-120">The orbit is freed when the call is retrieved or disconnected.</span></span>
  
<span data-ttu-id="0b843-121">部署呼叫寄存时，您需要为呼叫寄存保留一定范围的分机号。</span><span class="sxs-lookup"><span data-stu-id="0b843-121">When you deploy Call Park, you need to reserve ranges of extension numbers for parking calls.</span></span> <span data-ttu-id="0b843-122">这些分机应该是虚拟分机：尚未分配任何用户或电话的分机。</span><span class="sxs-lookup"><span data-stu-id="0b843-122">These extensions need to be virtual extensions: extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="0b843-123">然后根据分机号的范围配置呼叫寄存通道表，并指定承载负责处理每个范围的呼叫寄存应用程序的应用程序服务。</span><span class="sxs-lookup"><span data-stu-id="0b843-123">You then configure the call park orbit table with the ranges of extension numbers and specify which Application service hosts the Call Park application that handles each range.</span></span> <span data-ttu-id="0b843-124">每个前端池中有一个调用公园表上相应后端服务器，用于管理在池停的呼叫。</span><span class="sxs-lookup"><span data-stu-id="0b843-124">Each Front End pool has a Call Park table on the corresponding Back End Server that is used to manage calls that are parked on the pool.</span></span> <span data-ttu-id="0b843-125">轨道范围的列表存储在集中管理存储并被用来传送给目标池的轨道。</span><span class="sxs-lookup"><span data-stu-id="0b843-125">The list of orbit ranges is stored in Central Management store and is used to route orbits to the destination pool.</span></span> <span data-ttu-id="0b843-126">每个 Skype 业务服务器池公园调用应用程序在部署和配置可以有一个或多个运行轨道范围。</span><span class="sxs-lookup"><span data-stu-id="0b843-126">Each Skype for Business Server pool where the Call Park application is deployed and configured can have one or more orbit ranges.</span></span> <span data-ttu-id="0b843-127">对于业务服务器部署 Skype 轨道范围必须全局唯一。</span><span class="sxs-lookup"><span data-stu-id="0b843-127">Orbit ranges must be globally unique across the Skype for Business Server deployment.</span></span> 
  
<span data-ttu-id="0b843-p107">您还可以配置其他呼叫寄存设置，例如当呼叫超时时重定向到什么位置以及寄存时打电话的人是否可以听到音乐。您还可以指定呼叫处于保持状态时播放的音乐文件。</span><span class="sxs-lookup"><span data-stu-id="0b843-p107">You also configure other Call Park settings, such as where calls are redirected if they time out and whether the person on the phone hears music while parked. You can also specify the music file to play while the call is on hold.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0b843-130">自定义的音乐上保留文件调用公园未备份的 Skype 业务服务器的灾难恢复过程的一部分，将会丢失，如果将文件上载到该池被破坏、 损坏或删除。</span><span class="sxs-lookup"><span data-stu-id="0b843-130">Customized music-on-hold files for Call Park are not backed up as part of the Skype for Business Server disaster recovery process and will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span> <span data-ttu-id="0b843-131">始终保留已为呼叫寄存上载的自定义的保持音乐文件的单独备份副本。</span><span class="sxs-lookup"><span data-stu-id="0b843-131">Always keep a separate backup copy of the customized music-on-hold files that you have uploaded for Call Park.</span></span> 
  
<span data-ttu-id="0b843-132">呼叫寄存应用程序是企业语音的一个组件。</span><span class="sxs-lookup"><span data-stu-id="0b843-132">The Call Park application is a component of Enterprise Voice.</span></span> <span data-ttu-id="0b843-133">当您部署企业语音时，调用公园应用程序安装，并自动激活。</span><span class="sxs-lookup"><span data-stu-id="0b843-133">When you deploy Enterprise Voice, the Call Park application is installed and activated automatically.</span></span> <span data-ttu-id="0b843-134">可以使用调用公园之前，但是，企业语音管理员必须配置它并使其用户通过语音策略。</span><span class="sxs-lookup"><span data-stu-id="0b843-134">Before you can use Call Park, however, the Enterprise Voice administrator must configure it and enable it for users through voice policy.</span></span>
  
## <a name="deployment-and-requirements"></a><span data-ttu-id="0b843-135">部署和要求</span><span class="sxs-lookup"><span data-stu-id="0b843-135">Deployment and requirements</span></span>

<span data-ttu-id="0b843-136">当您部署企业语音，调用公园应用程序将自动安装。</span><span class="sxs-lookup"><span data-stu-id="0b843-136">The Call Park application is automatically installed when you deploy Enterprise Voice.</span></span> <span data-ttu-id="0b843-137">您可以通过配置语音策略启用调用公园。</span><span class="sxs-lookup"><span data-stu-id="0b843-137">You enable Call Park by configuring voice policy.</span></span>
  
### <a name="software-requirements"></a><span data-ttu-id="0b843-138">软件要求</span><span class="sxs-lookup"><span data-stu-id="0b843-138">Software requirements</span></span>

<span data-ttu-id="0b843-139">调用公园的部署位置的所有前端服务器和标准版服务器必须运行 Windows Server 2012 或 Windows 服务器的服务器中运行 Windows Server 2008 R2 或 Microsoft 媒体基础的服务器安装的 Windows 媒体格式运行时2012 R2。</span><span class="sxs-lookup"><span data-stu-id="0b843-139">All Front End Servers and Standard Edition servers where Call Park is deployed must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="0b843-140">对于 Windows Server 2008 R2，Windows 媒体格式运行时安装作为 Windows 桌面体验的一部分。</span><span class="sxs-lookup"><span data-stu-id="0b843-140">For Windows Server 2008 R2, Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span> <span data-ttu-id="0b843-141">Windows 媒体格式运行时或 Microsoft 媒体基础是 Windows Media 音频 (.wma) 文件需要调用公园播放音乐暂候状态。</span><span class="sxs-lookup"><span data-stu-id="0b843-141">Windows Media Format Runtime or Microsoft Media Foundation is required for Windows Media Audio (.wma) files that Call Park plays for music on hold.</span></span>
  
### <a name="port-requirements"></a><span data-ttu-id="0b843-142">端口要求</span><span class="sxs-lookup"><span data-stu-id="0b843-142">Port requirements</span></span>

<span data-ttu-id="0b843-143">调用公园应用程序使用**端口 5075** SIP 侦听请求。</span><span class="sxs-lookup"><span data-stu-id="0b843-143">The Call Park application uses **Port 5075**  for SIP listening requests.</span></span>
    
> [!NOTE]
> <span data-ttu-id="0b843-144">此端口是通过**设置 CsApplicationServer** cmdlet 可以更改默认设置。</span><span class="sxs-lookup"><span data-stu-id="0b843-144">This port is a default setting that you can change by using the **Set-CsApplicationServer** cmdlet.</span></span> <span data-ttu-id="0b843-145">此 cmdlet 的详细信息，请参阅 Lync 服务器管理外壳程序文档。</span><span class="sxs-lookup"><span data-stu-id="0b843-145">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>
  
### <a name="audio-file-requirements"></a><span data-ttu-id="0b843-146">音频文件要求</span><span class="sxs-lookup"><span data-stu-id="0b843-146">Audio File requirements</span></span>

<span data-ttu-id="0b843-147">保存应用程序仅支持 Windows Media 音频 (.wma) 文件的音乐调用公园。</span><span class="sxs-lookup"><span data-stu-id="0b843-147">The Call Park application supports only Windows Media Audio (.wma) files for music on hold.</span></span> <span data-ttu-id="0b843-148">您可以使用 Microsoft Expression Encoder 4 来自定义用作保持音乐的文件。</span><span class="sxs-lookup"><span data-stu-id="0b843-148">You can use the Microsoft Expression Encoder 4 to customize files for music on hold.</span></span> <span data-ttu-id="0b843-149">若要下载表达式编码器 4，请参阅["表达式编码器 4"](https://go.microsoft.com/fwlink/p/?linkId=202843)。</span><span class="sxs-lookup"><span data-stu-id="0b843-149">To download Expression Encoder 4, see   ["Expression Encoder 4"](https://go.microsoft.com/fwlink/p/?linkId=202843).</span></span> <span data-ttu-id="0b843-150">使用该工具可将文件转换为 .wma 格式。</span><span class="sxs-lookup"><span data-stu-id="0b843-150">Use the tool to convert the file to a .wma format.</span></span> <span data-ttu-id="0b843-151">建议的调用公园音乐上保留文件的格式是媒体音频 9、 44 kHz，16 位，单声道，CBR，32 kbps 速率进行传输。</span><span class="sxs-lookup"><span data-stu-id="0b843-151">The recommended format for Call Park music-on-hold files is Media Audio 9, 44 kHz, 16 bits, Mono, CBR, 32 kbps.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0b843-152">转换后的文件仅以 16 KHz 在电话上播放，即使录制时采用 44 KHz 也是如此。</span><span class="sxs-lookup"><span data-stu-id="0b843-152">The converted file plays over the phone only at 16 kHz, even if it was recorded at 44 kHz.</span></span> 
  
## <a name="supported-clients-and-calls"></a><span data-ttu-id="0b843-153">支持的客户端和呼叫</span><span class="sxs-lookup"><span data-stu-id="0b843-153">Supported clients and calls</span></span>

<span data-ttu-id="0b843-154">支持调用公园下面的客户端和调用的类型</span><span class="sxs-lookup"><span data-stu-id="0b843-154">The following clients and types of calls are supported for Call Park</span></span>
  
### <a name="clients-supported-for-parking-calls"></a><span data-ttu-id="0b843-155">支持寄存呼叫的客户端</span><span class="sxs-lookup"><span data-stu-id="0b843-155">Clients Supported for Parking Calls</span></span>

<span data-ttu-id="0b843-156">可寄存来自任意 IP、专用交换机 (PBX)、公用电话交换网 (PSTN) 或移动电话的呼叫。</span><span class="sxs-lookup"><span data-stu-id="0b843-156">Calls from any IP, private branch exchange (PBX), public switched telephone network (PSTN), or mobile phone can be parked.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0b843-p114">只能寄存音频呼叫。不能寄存即时消息和会议。</span><span class="sxs-lookup"><span data-stu-id="0b843-p114">Only audio calls can be parked. Instant messages and conferences cannot be parked.</span></span> 
  
<span data-ttu-id="0b843-159">下列客户端可以使用调用公园到公园的呼叫：</span><span class="sxs-lookup"><span data-stu-id="0b843-159">The following clients can use Call Park to park calls:</span></span>
  
- <span data-ttu-id="0b843-160">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="0b843-160">Skype for Business</span></span>
    
- <span data-ttu-id="0b843-161">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="0b843-161">Lync 2013</span></span>
    
- <span data-ttu-id="0b843-162">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="0b843-162">Lync 2010</span></span>
    
- <span data-ttu-id="0b843-163">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="0b843-163">Lync 2010 Attendant</span></span>
    
- <span data-ttu-id="0b843-164">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="0b843-164">Lync Phone Edition</span></span>
    
> [!NOTE]
> <span data-ttu-id="0b843-165">手机不能使用调用公园到公园的呼叫。</span><span class="sxs-lookup"><span data-stu-id="0b843-165">Mobile phones cannot use Call Park to park calls.</span></span> 
  
### <a name="clients-supported-for-retrieving-calls"></a><span data-ttu-id="0b843-166">支持取回呼叫的客户端</span><span class="sxs-lookup"><span data-stu-id="0b843-166">Clients Supported for Retrieving Calls</span></span>

<span data-ttu-id="0b843-p115">将通道范围配置为虚拟分机块（未分配用户或电话的分机）。将通道配置为虚拟分机时，移动电话和 PSTN 电话无法取回寄存的呼叫。</span><span class="sxs-lookup"><span data-stu-id="0b843-p115">Orbit ranges are configured as blocks of virtual extensions (extensions without an assigned user or phone). When you configure orbits as virtual extensions, mobile phones and PSTN phones cannot retrieve parked calls.</span></span>
  
<span data-ttu-id="0b843-169">联盟用户无法取回寄存的呼叫。</span><span class="sxs-lookup"><span data-stu-id="0b843-169">Federated users cannot retrieve parked calls.</span></span>
  
<span data-ttu-id="0b843-170">下列客户端可以检索调用停车场停的调用：</span><span class="sxs-lookup"><span data-stu-id="0b843-170">The following clients can retrieve calls that are parked on Call Park:</span></span>
  
- <span data-ttu-id="0b843-171">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="0b843-171">Skype for Business</span></span>
    
- <span data-ttu-id="0b843-172">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="0b843-172">Lync 2013</span></span>
    
- <span data-ttu-id="0b843-173">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="0b843-173">Lync 2010</span></span>
    
- <span data-ttu-id="0b843-174">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="0b843-174">Lync 2010 Attendant</span></span>
    
- <span data-ttu-id="0b843-175">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="0b843-175">Lync Phone Edition</span></span>
    
- <span data-ttu-id="0b843-176">IP 公用区域电话</span><span class="sxs-lookup"><span data-stu-id="0b843-176">IP common area phones</span></span>
    
- <span data-ttu-id="0b843-177">非 IP 电话连接到企业服务器基础架构，包括公共区域电话和专用分组交换机 (PBX) 电话 Skype</span><span class="sxs-lookup"><span data-stu-id="0b843-177">Non-IP phones that are connected to the Skype for Business Server infrastructure, including common area phones and private branch exchange (PBX) phones</span></span>
    
## <a name="call-park-capacity-planning"></a><span data-ttu-id="0b843-178">呼叫寄存容量规划</span><span class="sxs-lookup"><span data-stu-id="0b843-178">Call Park capacity planning</span></span>

<span data-ttu-id="0b843-179">下表描述了可用作容量规划需求基础的调用公园用户模型。</span><span class="sxs-lookup"><span data-stu-id="0b843-179">The following table describes the Call Park user model that you can use as the basis for capacity planning requirements.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="0b843-180">请记住，对于灾难恢复产能规划，成对池中每个池应该能够处理调用公园服务这两个池中的工作负载。</span><span class="sxs-lookup"><span data-stu-id="0b843-180">Keep in mind that, for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for Call Park services in both pools.</span></span> 
  
<span data-ttu-id="0b843-181">**调用公园用户模型**</span><span class="sxs-lookup"><span data-stu-id="0b843-181">**Call Park User Model**</span></span>

|<span data-ttu-id="0b843-182">**跃点计数**</span><span class="sxs-lookup"><span data-stu-id="0b843-182">**Metric**</span></span>|<span data-ttu-id="0b843-183">**每个前端池<br/>（带有 8 前端服务器）**</span><span class="sxs-lookup"><span data-stu-id="0b843-183">**Per Front End pool  <br/>  (with 8 Front End Servers)**</span></span>|<span data-ttu-id="0b843-184">**每个标准版服务器**</span><span class="sxs-lookup"><span data-stu-id="0b843-184">**Per Standard Edition server**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0b843-185">寄存速率</span><span class="sxs-lookup"><span data-stu-id="0b843-185">Park rate</span></span>  <br/> |<span data-ttu-id="0b843-186">每分钟 8 个</span><span class="sxs-lookup"><span data-stu-id="0b843-186">8 per minute</span></span>  <br/> |<span data-ttu-id="0b843-187">每分钟 1 个</span><span class="sxs-lookup"><span data-stu-id="0b843-187">1 per minute</span></span>  <br/> |
|<span data-ttu-id="0b843-188">取回寄存呼叫的速率</span><span class="sxs-lookup"><span data-stu-id="0b843-188">Retrieve parked call rate</span></span>  <br/> |<span data-ttu-id="0b843-189">每分钟 8 个</span><span class="sxs-lookup"><span data-stu-id="0b843-189">8 per minute</span></span>  <br/> |<span data-ttu-id="0b843-190">每分钟 1 个</span><span class="sxs-lookup"><span data-stu-id="0b843-190">1 per minute</span></span>  <br/> |
|<span data-ttu-id="0b843-191">平均寄存持续时间</span><span class="sxs-lookup"><span data-stu-id="0b843-191">Average park duration</span></span>  <br/> |<span data-ttu-id="0b843-192">60 秒</span><span class="sxs-lookup"><span data-stu-id="0b843-192">60 seconds</span></span>  <br/> |<span data-ttu-id="0b843-193">60 秒</span><span class="sxs-lookup"><span data-stu-id="0b843-193">60 seconds</span></span>  <br/> |
   

