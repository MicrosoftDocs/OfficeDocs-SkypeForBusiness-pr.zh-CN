---
title: Skype 会议室系统迁移注意事项
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/4/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df9f33b6-0360-4354-b651-bd35da533e33
description: 阅读本主题以了解有关如何在环境中的多个版本的 Skype 业务服务器和 Lync Server 部署 Skype 的空间系统。
ms.openlocfilehash: f71c6557a8b9a98f712541c4424ba57a49536164
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="skype-room-system-migration-considerations"></a><span data-ttu-id="9980f-103">Skype 会议室系统迁移注意事项</span><span class="sxs-lookup"><span data-stu-id="9980f-103">Skype Room System migration considerations</span></span>
 
<span data-ttu-id="9980f-104">阅读本主题以了解有关如何在环境中的多个版本的 Skype 业务服务器和 Lync Server 部署 Skype 的空间系统。</span><span class="sxs-lookup"><span data-stu-id="9980f-104">Read this topic to learn about how to deploy Skype Room System in an environment that has multiple versions of Skype for Business Server and Lync Server.</span></span>
  
## <a name="migration-considerations"></a><span data-ttu-id="9980f-105">迁移注意事项</span><span class="sxs-lookup"><span data-stu-id="9980f-105">Migration considerations</span></span>

<span data-ttu-id="9980f-106">此部分提供了指南，如果包括不同版本的 Skype 业务服务器、 Lync Server 或办公室通信服务器 2007 R2 多池环境中部署 Skype 的空间系统。</span><span class="sxs-lookup"><span data-stu-id="9980f-106">This section provides guidance if you are deploying Skype Room System in a multi-pool environment that includes different versions of Skype for Business Server, Lync Server, or Office Communications Server 2007 R2.</span></span> 
  
<span data-ttu-id="9980f-107">Lync Server 中的用户复制程序 (UR) 组件从 Active Directory 获取用户对象并将它们放入 Lync Server 后端 SQL Server 数据库中。</span><span class="sxs-lookup"><span data-stu-id="9980f-107">The User Replicator (UR) component in Lync Server gets user objects from Active Directory and places them into the Lync Server back-end SQL Server database.</span></span> <span data-ttu-id="9980f-108">仅在 Lync Server 2013 UR 已知道 Skype 的空间系统对象。</span><span class="sxs-lookup"><span data-stu-id="9980f-108">Only the UR in Lync Server 2013 is aware of Skype Room System objects.</span></span> <span data-ttu-id="9980f-109">以前版本的 Lync Server 和 Office Communications Server 中的 UR 不影响指定 LR 对象的 Active Directory 属性，因此无法识别它们。</span><span class="sxs-lookup"><span data-stu-id="9980f-109">The UR in previous versions of Lync Server and Office Communications Server do not detect the Active Directory attributes that designate LRS objects, and therefore was not aware of them.</span></span> 
  
<span data-ttu-id="9980f-110">LRS 如果 Skype 的空间系统帐户尝试登录 Lync，并执行基于 SRV 记录或 DNS A 记录查找的自动发现和这些帐户指向 Lync Server 或办公室通信服务器的早期版本，将会收到从 404 找不到回复 传统的池。</span><span class="sxs-lookup"><span data-stu-id="9980f-110">If a Skype Room System account tries to sign in to Lync , and performs auto discovery based on SRV record or DNS A record look up, and if those accounts point to a previous version of Lync Server or Office Communications Server, LRS will receive a 404 Not Found response from the legacy pool.</span></span> <span data-ttu-id="9980f-111">传统的池不能重定向到其 Lync Server 2013 主池 Skype 的空间系统。</span><span class="sxs-lookup"><span data-stu-id="9980f-111">The legacy pool will not be able to redirect Skype Room System to its Lync Server 2013 home pool.</span></span> 
  
<span data-ttu-id="9980f-112">你可以通过以下方法解决此问题：</span><span class="sxs-lookup"><span data-stu-id="9980f-112">You can address this problem with the following options:</span></span> 
  
- <span data-ttu-id="9980f-113">将你的自动发现 SRV 记录 (_sipinternaltls._tcp.contoso.com) 指向 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="9980f-113">Point your autodiscover SRV record (_sipinternaltls._tcp.contoso.com) to Lync Server 2013 pool.</span></span>
    
- <span data-ttu-id="9980f-114">如果第一个选项不是可能的您必须手动配置 LRS 并提供通过 Skype 的空间系统控制台应用程序中直接配置 Lync Server 2013 池地址。</span><span class="sxs-lookup"><span data-stu-id="9980f-114">If the first option isn't possible, you must manually configure LRS and provide the Lync Server 2013 pool address by directly configuring it in the Skype Room System console application.</span></span> 
    
- <span data-ttu-id="9980f-115">如果企业网络外部的部署 Skype 的空间系统和部署 Lync 边缘服务器并将其配置为指向旧池或控制器，辅助的边缘服务器站点是必需的它指向 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="9980f-115">If Skype Room System is deployed outside the corporate network, and a Lync Edge Server has been deployed and configured to point to a legacy pool or director, a secondary Edge Server site is required, which points to the Lync Server 2013 pool.</span></span> <span data-ttu-id="9980f-116">有关部署第二个边缘服务器的详细信息，请参阅边缘服务器部署文档。</span><span class="sxs-lookup"><span data-stu-id="9980f-116">Refer to the Edge Server deployment documentation for more information about deploying a secondary Edge Server.</span></span> 
    
## <a name="skype-room-system-interoperability-with-a-lync-server-2010-pool"></a><span data-ttu-id="9980f-117">Skype 的空间与 Lync 服务器 2010年池的系统互操作性</span><span class="sxs-lookup"><span data-stu-id="9980f-117">Skype Room System Interoperability with a Lync Server 2010 Pool</span></span>

<span data-ttu-id="9980f-118">在迁移期间，位于 Lync Server 2010 池的用户安排会议并邀请 Skype 的空间系统帐户，如果 Skype 的空间系统客户端功能将受到限制参加会议时。</span><span class="sxs-lookup"><span data-stu-id="9980f-118">During migration, if a user who is homed on a Lync Server 2010 pool schedules a meeting and invites the Skype Room System account, the Skype Room System client will have limited functionality while attending the meeting.</span></span> 
  
<span data-ttu-id="9980f-119">当 Skype 的空间系统客户端加入已按计划的会议呼叫用户驻留在 Lync Server 2010 上，Skype 的空间系统具有以下会议在限制：</span><span class="sxs-lookup"><span data-stu-id="9980f-119">When the Skype Room System client joins a scheduled conference call that has been organized by a user homed on Lync Server 2010, Skype Room System has the following in-meeting limitations:</span></span> 
  
- <span data-ttu-id="9980f-120">Skype 的空间系统无法显示多视图视频库。</span><span class="sxs-lookup"><span data-stu-id="9980f-120">Skype Room System cannot show the multi-view video gallery.</span></span>
    
- <span data-ttu-id="9980f-121">如果 Skype 的空间系统客户端的演示者，它不能在参与者应用视频锁。</span><span class="sxs-lookup"><span data-stu-id="9980f-121">If the Skype Room System client is the presenter, it cannot apply video lock on participants.</span></span>
    
- <span data-ttu-id="9980f-122">Skype 的空间系统无法显示 1080p 视频分辨率 （入站或出站），即使 Lync Server 2013 会议策略允许，原因如下：</span><span class="sxs-lookup"><span data-stu-id="9980f-122">Skype Room System cannot show 1080p video resolution (inbound or outbound), even if the Lync Server 2013 conferencing policy allows it, because of the following:</span></span> 
    
  - <span data-ttu-id="9980f-123">Lync Server 2010 不支持 1080p 分辨率。</span><span class="sxs-lookup"><span data-stu-id="9980f-123">Lync Server 2010 doesn't support 1080p resolution.</span></span>
    
  - <span data-ttu-id="9980f-124">Skype 的空间系统始终受到组织者的会议策略的视频分辨率。</span><span class="sxs-lookup"><span data-stu-id="9980f-124">Skype Room System is always limited by the organizer's conferencing policy for video resolution.</span></span> <span data-ttu-id="9980f-125">因此，即使 Lync 2010 池支持 720p 分辨率，Skype 的空间系统将无法利用 720p 分辨率，只要组织者的策略不支持它。</span><span class="sxs-lookup"><span data-stu-id="9980f-125">Therefore, even if the Lync 2010 pool supports 720p resolution, Skype Room System will not be able to take advantage of 720p resolution as long as organizer's policy doesn't support it.</span></span> 
    
- <span data-ttu-id="9980f-p105">Lync 2013 客户端在会议室中检测 LRS 状态，它们会自动将自己静音以避免物理会议室中产生回声。此功能在 Lync Server 2010 上主持的会议中不适用。</span><span class="sxs-lookup"><span data-stu-id="9980f-p105">Lync 2013 clients detect LRS presence in the meeting room, and they auto-mute themselves to avoid echo in the physical meeting room. This feature does not work in meetings hosted on Lync Server 2010.</span></span>
    
- <span data-ttu-id="9980f-128">对于在 Lync Server 2010 上主持的会议，桌面共享功能存在一些限制。</span><span class="sxs-lookup"><span data-stu-id="9980f-128">There are limitations on desktop sharing performance for meetings hosted on Lync Server 2010.</span></span>
    
- <span data-ttu-id="9980f-129">用户将不能加入专用 （受限） 会议承载 Lync 2010 与 Skype 的空间系统。</span><span class="sxs-lookup"><span data-stu-id="9980f-129">Users won't be able to join private (restricted) meetings that are hosted on Lync 2010 with Skype Room System.</span></span>
    

