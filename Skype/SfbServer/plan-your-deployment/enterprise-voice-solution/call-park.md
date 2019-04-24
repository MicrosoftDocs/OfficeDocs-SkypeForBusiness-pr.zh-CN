---
title: 规划呼叫寄存中 Skype for Business
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 985dc326-0aef-4308-b98b-c1d0069311e7
description: 这样可使业务 Server 企业语音规划呼叫寄存 Skype 中，将呼叫置于保持状态并将呼叫转接到的部门。 包括容量规划、支持的呼叫和支持的客户端。
ms.openlocfilehash: 92c896bb610827108379af2bca38cd7a89639af2
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32207025"
---
# <a name="plan-for-call-park-in-skype-for-business"></a><span data-ttu-id="983b1-104">规划呼叫寄存中 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="983b1-104">Plan for Call Park in Skype for Business</span></span>
 
<span data-ttu-id="983b1-105">这样可使业务 Server 企业语音规划呼叫寄存 Skype 中，将呼叫置于保持状态并将呼叫转接到的部门。</span><span class="sxs-lookup"><span data-stu-id="983b1-105">Planning for call park in Skype for Business Server Enterprise Voice, which enables putting calls on hold and transferring calls to departments.</span></span> <span data-ttu-id="983b1-106">包括容量规划、支持的呼叫和支持的客户端。</span><span class="sxs-lookup"><span data-stu-id="983b1-106">Includes capacity planning, supported calls, and supported clients.</span></span>
  
<span data-ttu-id="983b1-107">呼叫寄存应用程序启用企业语音用户执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="983b1-107">The Call Park application enables Enterprise Voice users to do the following:</span></span>
  
- <span data-ttu-id="983b1-108">将呼叫置于保持状态并从同一电话或另一电话取回该呼叫。</span><span class="sxs-lookup"><span data-stu-id="983b1-108">Put a call on hold and then retrieve the call from the same phone or another phone.</span></span>
    
- <span data-ttu-id="983b1-109">将呼叫置于保持状态，以将其转接到某个部门或常规区域（例如，转接到有公用区域电话的销售部门或仓库）。</span><span class="sxs-lookup"><span data-stu-id="983b1-109">Put a call on hold to transfer it to a department or general area (for example, to a sales department or a warehouse where there is a common area phone).</span></span>
    
- <span data-ttu-id="983b1-110">将呼叫置于保持状态，并保持原始应答电话处于空闲状态，以接听其他呼叫。</span><span class="sxs-lookup"><span data-stu-id="983b1-110">Put a call on hold and keep the original answering phone free for other calls.</span></span>
    
<span data-ttu-id="983b1-111">当用户公园呼叫，Skype 业务服务器将呼叫转接给临时号码，调用通道，呼叫将保存，直到它检索或超时。Skype 业务服务器将通道发送到寄存呼叫的用户。</span><span class="sxs-lookup"><span data-stu-id="983b1-111">When a user parks a call, Skype for Business Server transfers the call to a temporary number, called an orbit, where the call is held until it is retrieved or it times out. Skype for Business Server sends the orbit to the user who parked the call.</span></span> <span data-ttu-id="983b1-112">用户可以通过拨打该通道号或单击“对话”窗口中的通道链接或按钮来取回寄存的呼叫。</span><span class="sxs-lookup"><span data-stu-id="983b1-112">To retrieve the parked call, the user can dial the orbit number or click the orbit link or button in the Conversation window.</span></span> 
  
<span data-ttu-id="983b1-p104">寄存呼叫的用户可以使用外部机制（如即时消息 (IM) 或寻呼系统）通知某人取回呼叫，以向其他人通知该通道号。寄存呼叫的用户可以使“对话”窗口保持打开状态，以在取回呼叫时接收通知。</span><span class="sxs-lookup"><span data-stu-id="983b1-p104">The user who parked a call can notify someone to retrieve the call by using an external mechanism, such as instant messaging (IM) or a paging system, to communicate the orbit number to someone else. The user who parked the call can leave the Conversation window open to receive notification when the call is retrieved.</span></span>
  
<span data-ttu-id="983b1-115">因为通道范围是全局唯一，就可以从任何 Skype 业务 Server 网站或 PBX 电话取回呼叫，如果相应路由配置。</span><span class="sxs-lookup"><span data-stu-id="983b1-115">Because orbit ranges are globally unique, it is possible to retrieve calls from any Skype for Business Server site or PBX phone if routing is configured appropriately.</span></span> <span data-ttu-id="983b1-116">如果在可配置的时间内没有人取回呼叫，则呼叫将回拨到寄存它的人。</span><span class="sxs-lookup"><span data-stu-id="983b1-116">If no one retrieves the call within a configurable amount of time, the call rings back to the person who parked it.</span></span> <span data-ttu-id="983b1-117">如果此人不应答回拨电话，呼叫将转接到回退目标，例如接线员（如果这样配置的话）。</span><span class="sxs-lookup"><span data-stu-id="983b1-117">If that person does not answer the ringback, the call is transferred to a fallback destination, such as to an operator, if so configured.</span></span> <span data-ttu-id="983b1-118">可以配置呼叫在转接前的回拨次数（1 到 10 次）。</span><span class="sxs-lookup"><span data-stu-id="983b1-118">You can configure the number of times the call rings back before being transferred from one to ten times.</span></span> <span data-ttu-id="983b1-119">如果没有人应答转接呼叫，则呼叫将断开连接。</span><span class="sxs-lookup"><span data-stu-id="983b1-119">If no one answers a transferred call, the call is disconnected.</span></span> <span data-ttu-id="983b1-120">呼叫取回或断开连接后会释放通道。</span><span class="sxs-lookup"><span data-stu-id="983b1-120">The orbit is freed when the call is retrieved or disconnected.</span></span>
  
<span data-ttu-id="983b1-121">部署呼叫寄存时，您需要为呼叫寄存保留一定范围的分机号。</span><span class="sxs-lookup"><span data-stu-id="983b1-121">When you deploy Call Park, you need to reserve ranges of extension numbers for parking calls.</span></span> <span data-ttu-id="983b1-122">这些分机应该是虚拟分机：尚未分配任何用户或电话的分机。</span><span class="sxs-lookup"><span data-stu-id="983b1-122">These extensions need to be virtual extensions: extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="983b1-123">然后根据分机号的范围配置呼叫寄存通道表，并指定承载负责处理每个范围的呼叫寄存应用程序的应用程序服务。</span><span class="sxs-lookup"><span data-stu-id="983b1-123">You then configure the call park orbit table with the ranges of extension numbers and specify which Application service hosts the Call Park application that handles each range.</span></span> <span data-ttu-id="983b1-124">每个前端池具有相应后端服务器上用来管理池驻留的呼叫的呼叫寄存表。</span><span class="sxs-lookup"><span data-stu-id="983b1-124">Each Front End pool has a Call Park table on the corresponding Back End Server that is used to manage calls that are parked on the pool.</span></span> <span data-ttu-id="983b1-125">通道范围的列表存储在中央管理存储和用于将轨道路由到目标池。</span><span class="sxs-lookup"><span data-stu-id="983b1-125">The list of orbit ranges is stored in Central Management store and is used to route orbits to the destination pool.</span></span> <span data-ttu-id="983b1-126">为业务服务器池其中部署和配置呼叫寄存应用程序的每个 Skype 可以有一个或多个通道范围。</span><span class="sxs-lookup"><span data-stu-id="983b1-126">Each Skype for Business Server pool where the Call Park application is deployed and configured can have one or more orbit ranges.</span></span> <span data-ttu-id="983b1-127">对于业务服务器部署 Skype 通道范围必须全局唯一。</span><span class="sxs-lookup"><span data-stu-id="983b1-127">Orbit ranges must be globally unique across the Skype for Business Server deployment.</span></span> 
  
<span data-ttu-id="983b1-p107">您还可以配置其他呼叫寄存设置，例如当呼叫超时时重定向到什么位置以及寄存时打电话的人是否可以听到音乐。您还可以指定呼叫处于保持状态时播放的音乐文件。</span><span class="sxs-lookup"><span data-stu-id="983b1-p107">You also configure other Call Park settings, such as where calls are redirected if they time out and whether the person on the phone hears music while parked. You can also specify the music file to play while the call is on hold.</span></span>
  
> [!NOTE]
> <span data-ttu-id="983b1-130">呼叫寄存的自定义的保留音乐文件未备份的 Skype Business Server 灾难恢复过程的一部分，并且如果将文件上载到池被破坏、 损坏，或删除将会丢失。</span><span class="sxs-lookup"><span data-stu-id="983b1-130">Customized music-on-hold files for Call Park are not backed up as part of the Skype for Business Server disaster recovery process and will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span> <span data-ttu-id="983b1-131">始终保留已为呼叫寄存上载的自定义的保持音乐文件的单独备份副本。</span><span class="sxs-lookup"><span data-stu-id="983b1-131">Always keep a separate backup copy of the customized music-on-hold files that you have uploaded for Call Park.</span></span> 
  
<span data-ttu-id="983b1-132">呼叫寄存应用程序是企业语音的一个组件。</span><span class="sxs-lookup"><span data-stu-id="983b1-132">The Call Park application is a component of Enterprise Voice.</span></span> <span data-ttu-id="983b1-133">在部署企业语音时，呼叫寄存应用程序安装和自动激活。</span><span class="sxs-lookup"><span data-stu-id="983b1-133">When you deploy Enterprise Voice, the Call Park application is installed and activated automatically.</span></span> <span data-ttu-id="983b1-134">您可以使用呼叫寄存之前，但是，企业语音管理员必须将其配置并启用用户通过语音策略。</span><span class="sxs-lookup"><span data-stu-id="983b1-134">Before you can use Call Park, however, the Enterprise Voice administrator must configure it and enable it for users through voice policy.</span></span>
  
## <a name="deployment-and-requirements"></a><span data-ttu-id="983b1-135">部署和要求</span><span class="sxs-lookup"><span data-stu-id="983b1-135">Deployment and requirements</span></span>

<span data-ttu-id="983b1-136">部署企业语音时，会自动安装的呼叫寄存应用程序。</span><span class="sxs-lookup"><span data-stu-id="983b1-136">The Call Park application is automatically installed when you deploy Enterprise Voice.</span></span> <span data-ttu-id="983b1-137">通过配置语音策略启用呼叫寄存。</span><span class="sxs-lookup"><span data-stu-id="983b1-137">You enable Call Park by configuring voice policy.</span></span>
  
### <a name="software-requirements"></a><span data-ttu-id="983b1-138">软件要求</span><span class="sxs-lookup"><span data-stu-id="983b1-138">Software requirements</span></span>

<span data-ttu-id="983b1-139">部署呼叫寄存的位置的所有前端服务器和 Standard Edition 服务器必须运行 Windows Server 2012 或 Windows Server 的服务器运行 Windows Server 2008 R2 或 Microsoft 媒体 Foundation 的服务器上安装 Windows Media Format Runtime2012 R2。</span><span class="sxs-lookup"><span data-stu-id="983b1-139">All Front End Servers and Standard Edition servers where Call Park is deployed must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="983b1-140">对于 Windows Server 2008 R2，作为 Windows 桌面体验的一部分安装 Windows Media Format Runtime。</span><span class="sxs-lookup"><span data-stu-id="983b1-140">For Windows Server 2008 R2, Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span> <span data-ttu-id="983b1-141">Windows Media Format Runtime 或 Microsoft 媒体 Foundation 是必需的 Windows Media 音频 (.wma) 文件的呼叫寄存播放的音乐置于保持状态。</span><span class="sxs-lookup"><span data-stu-id="983b1-141">Windows Media Format Runtime or Microsoft Media Foundation is required for Windows Media Audio (.wma) files that Call Park plays for music on hold.</span></span>
  
### <a name="port-requirements"></a><span data-ttu-id="983b1-142">端口要求</span><span class="sxs-lookup"><span data-stu-id="983b1-142">Port requirements</span></span>

<span data-ttu-id="983b1-143">呼叫寄存应用程序使用**端口 5075**用于 SIP 侦听请求。</span><span class="sxs-lookup"><span data-stu-id="983b1-143">The Call Park application uses **Port 5075**  for SIP listening requests.</span></span>
    
> [!NOTE]
> <span data-ttu-id="983b1-144">此端口是默认设置，您可以使用 **Set-CsApplicationServer** cmdlet 对其进行更改。</span><span class="sxs-lookup"><span data-stu-id="983b1-144">This port is a default setting that you can change by using the **Set-CsApplicationServer** cmdlet.</span></span> <span data-ttu-id="983b1-145">有关此 cmdlet 的详细信息，请参阅 Lync Server Management Shell 文档。</span><span class="sxs-lookup"><span data-stu-id="983b1-145">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>
  
### <a name="audio-file-requirements"></a><span data-ttu-id="983b1-146">音频文件要求</span><span class="sxs-lookup"><span data-stu-id="983b1-146">Audio File requirements</span></span>

<span data-ttu-id="983b1-147">呼叫寄存应用程序仅支持 Windows Media 音频 (.wma) 文件的音乐保留。</span><span class="sxs-lookup"><span data-stu-id="983b1-147">The Call Park application supports only Windows Media Audio (.wma) files for music on hold.</span></span> <span data-ttu-id="983b1-148">您可以使用 Microsoft Expression Encoder 4 来自定义用作保持音乐的文件。</span><span class="sxs-lookup"><span data-stu-id="983b1-148">You can use the Microsoft Expression Encoder 4 to customize files for music on hold.</span></span> <span data-ttu-id="983b1-149">若要下载表达式编码器 4，请参阅["表达式编码器 4"](https://go.microsoft.com/fwlink/p/?linkId=202843)。</span><span class="sxs-lookup"><span data-stu-id="983b1-149">To download Expression Encoder 4, see   ["Expression Encoder 4"](https://go.microsoft.com/fwlink/p/?linkId=202843).</span></span> <span data-ttu-id="983b1-150">使用该工具可将文件转换为 .wma 格式。</span><span class="sxs-lookup"><span data-stu-id="983b1-150">Use the tool to convert the file to a .wma format.</span></span> <span data-ttu-id="983b1-151">呼叫寄存上保留音乐文件的建议的格式是 Media Audio 9，44 Khz,16 位，单声道，CBR，32 kbps。</span><span class="sxs-lookup"><span data-stu-id="983b1-151">The recommended format for Call Park music-on-hold files is Media Audio 9, 44 kHz, 16 bits, Mono, CBR, 32 kbps.</span></span>
  
> [!NOTE]
> <span data-ttu-id="983b1-152">转换后的文件仅以 16 KHz 在电话上播放，即使录制时采用 44 KHz 也是如此。</span><span class="sxs-lookup"><span data-stu-id="983b1-152">The converted file plays over the phone only at 16 kHz, even if it was recorded at 44 kHz.</span></span> 
  
## <a name="supported-clients-and-calls"></a><span data-ttu-id="983b1-153">支持的客户端和呼叫</span><span class="sxs-lookup"><span data-stu-id="983b1-153">Supported clients and calls</span></span>

<span data-ttu-id="983b1-154">以下客户端的呼叫类型支持的呼叫寄存</span><span class="sxs-lookup"><span data-stu-id="983b1-154">The following clients and types of calls are supported for Call Park</span></span>
  
### <a name="clients-supported-for-parking-calls"></a><span data-ttu-id="983b1-155">支持寄存呼叫的客户端</span><span class="sxs-lookup"><span data-stu-id="983b1-155">Clients Supported for Parking Calls</span></span>

<span data-ttu-id="983b1-156">可寄存来自任意 IP、专用交换机 (PBX)、公用电话交换网 (PSTN) 或移动电话的呼叫。</span><span class="sxs-lookup"><span data-stu-id="983b1-156">Calls from any IP, private branch exchange (PBX), public switched telephone network (PSTN), or mobile phone can be parked.</span></span>
  
> [!NOTE]
> <span data-ttu-id="983b1-p114">只能寄存音频呼叫。不能寄存即时消息和会议。</span><span class="sxs-lookup"><span data-stu-id="983b1-p114">Only audio calls can be parked. Instant messages and conferences cannot be parked.</span></span> 
  
<span data-ttu-id="983b1-159">以下客户端可以使用寄存呼叫的呼叫寄存：</span><span class="sxs-lookup"><span data-stu-id="983b1-159">The following clients can use Call Park to park calls:</span></span>
  
- <span data-ttu-id="983b1-160">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="983b1-160">Skype for Business</span></span>
    
- <span data-ttu-id="983b1-161">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="983b1-161">Lync 2013</span></span>
    
- <span data-ttu-id="983b1-162">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="983b1-162">Lync 2010</span></span>
    
- <span data-ttu-id="983b1-163">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="983b1-163">Lync 2010 Attendant</span></span>
    
- <span data-ttu-id="983b1-164">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="983b1-164">Lync Phone Edition</span></span>
    
> [!NOTE]
> <span data-ttu-id="983b1-165">移动电话不能使用寄存呼叫的呼叫寄存。</span><span class="sxs-lookup"><span data-stu-id="983b1-165">Mobile phones cannot use Call Park to park calls.</span></span> 
  
### <a name="clients-supported-for-retrieving-calls"></a><span data-ttu-id="983b1-166">支持取回呼叫的客户端</span><span class="sxs-lookup"><span data-stu-id="983b1-166">Clients Supported for Retrieving Calls</span></span>

<span data-ttu-id="983b1-p115">将通道范围配置为虚拟分机块（未分配用户或电话的分机）。将通道配置为虚拟分机时，移动电话和 PSTN 电话无法取回寄存的呼叫。</span><span class="sxs-lookup"><span data-stu-id="983b1-p115">Orbit ranges are configured as blocks of virtual extensions (extensions without an assigned user or phone). When you configure orbits as virtual extensions, mobile phones and PSTN phones cannot retrieve parked calls.</span></span>
  
<span data-ttu-id="983b1-169">联盟用户无法取回寄存的呼叫。</span><span class="sxs-lookup"><span data-stu-id="983b1-169">Federated users cannot retrieve parked calls.</span></span>
  
<span data-ttu-id="983b1-170">以下客户端可取回寄存在呼叫寄存的呼叫：</span><span class="sxs-lookup"><span data-stu-id="983b1-170">The following clients can retrieve calls that are parked on Call Park:</span></span>
  
- <span data-ttu-id="983b1-171">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="983b1-171">Skype for Business</span></span>
    
- <span data-ttu-id="983b1-172">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="983b1-172">Lync 2013</span></span>
    
- <span data-ttu-id="983b1-173">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="983b1-173">Lync 2010</span></span>
    
- <span data-ttu-id="983b1-174">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="983b1-174">Lync 2010 Attendant</span></span>
    
- <span data-ttu-id="983b1-175">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="983b1-175">Lync Phone Edition</span></span>
    
- <span data-ttu-id="983b1-176">IP 公用区域电话</span><span class="sxs-lookup"><span data-stu-id="983b1-176">IP common area phones</span></span>
    
- <span data-ttu-id="983b1-177">连接到业务服务器基础结构，包括公用区域电话和专用交换机 (PBX) 电话的 Skype 的非 IP 电话</span><span class="sxs-lookup"><span data-stu-id="983b1-177">Non-IP phones that are connected to the Skype for Business Server infrastructure, including common area phones and private branch exchange (PBX) phones</span></span>
    
## <a name="call-park-capacity-planning"></a><span data-ttu-id="983b1-178">呼叫寄存容量规划</span><span class="sxs-lookup"><span data-stu-id="983b1-178">Call Park capacity planning</span></span>

<span data-ttu-id="983b1-179">下表介绍可用作容量规划要求基础的呼叫寄存用户模型。</span><span class="sxs-lookup"><span data-stu-id="983b1-179">The following table describes the Call Park user model that you can use as the basis for capacity planning requirements.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="983b1-180">请记住，对于灾难恢复容量规划配对池中的每个池都应该能够处理这两个池中的呼叫寄存服务的工作负荷。</span><span class="sxs-lookup"><span data-stu-id="983b1-180">Keep in mind that, for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for Call Park services in both pools.</span></span> 
  
<span data-ttu-id="983b1-181">**呼叫寄存用户模型**</span><span class="sxs-lookup"><span data-stu-id="983b1-181">**Call Park User Model**</span></span>

|<span data-ttu-id="983b1-182">**指标**</span><span class="sxs-lookup"><span data-stu-id="983b1-182">**Metric**</span></span>|<span data-ttu-id="983b1-183">**每个前端池<br/>（具有 8 前端服务器）**</span><span class="sxs-lookup"><span data-stu-id="983b1-183">**Per Front End pool  <br/>  (with 8 Front End Servers)**</span></span>|<span data-ttu-id="983b1-184">**每台 Standard Edition Server**</span><span class="sxs-lookup"><span data-stu-id="983b1-184">**Per Standard Edition server**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="983b1-185">寄存速率</span><span class="sxs-lookup"><span data-stu-id="983b1-185">Park rate</span></span>  <br/> |<span data-ttu-id="983b1-186">每分钟 8 个</span><span class="sxs-lookup"><span data-stu-id="983b1-186">8 per minute</span></span>  <br/> |<span data-ttu-id="983b1-187">每分钟 1 个</span><span class="sxs-lookup"><span data-stu-id="983b1-187">1 per minute</span></span>  <br/> |
|<span data-ttu-id="983b1-188">取回寄存呼叫的速率</span><span class="sxs-lookup"><span data-stu-id="983b1-188">Retrieve parked call rate</span></span>  <br/> |<span data-ttu-id="983b1-189">每分钟 8 个</span><span class="sxs-lookup"><span data-stu-id="983b1-189">8 per minute</span></span>  <br/> |<span data-ttu-id="983b1-190">每分钟 1 个</span><span class="sxs-lookup"><span data-stu-id="983b1-190">1 per minute</span></span>  <br/> |
|<span data-ttu-id="983b1-191">平均寄存持续时间</span><span class="sxs-lookup"><span data-stu-id="983b1-191">Average park duration</span></span>  <br/> |<span data-ttu-id="983b1-192">60 秒</span><span class="sxs-lookup"><span data-stu-id="983b1-192">60 seconds</span></span>  <br/> |<span data-ttu-id="983b1-193">60 秒</span><span class="sxs-lookup"><span data-stu-id="983b1-193">60 seconds</span></span>  <br/> |
   

