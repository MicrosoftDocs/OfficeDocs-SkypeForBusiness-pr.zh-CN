---
title: Skype 会议室系统迁移注意事项
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df9f33b6-0360-4354-b651-bd35da533e33
description: 阅读本主题可了解如何在具有多个版本的 Skype Business Server 和 Lync Server 环境中部署 Skype 会议室系统。
ms.openlocfilehash: fef5e3e0a64fd1d533a53586b470584421a165ea
ms.sourcegitcommit: d3c3467320a2928d3bad14a1a44a31ee5a9a988c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "25699719"
---
# <a name="skype-room-system-migration-considerations"></a><span data-ttu-id="bf262-103">Skype 会议室系统迁移注意事项</span><span class="sxs-lookup"><span data-stu-id="bf262-103">Skype Room System migration considerations</span></span>
 
<span data-ttu-id="bf262-104">阅读本主题可了解如何在具有多个版本的 Skype Business Server 和 Lync Server 环境中部署 Skype 会议室系统。</span><span class="sxs-lookup"><span data-stu-id="bf262-104">Read this topic to learn about how to deploy Skype Room System in an environment that has multiple versions of Skype for Business Server and Lync Server.</span></span>
  
## <a name="migration-considerations"></a><span data-ttu-id="bf262-105">迁移注意事项</span><span class="sxs-lookup"><span data-stu-id="bf262-105">Migration considerations</span></span>

<span data-ttu-id="bf262-106">本节提供指导，如果企业服务器，或 Lync Server 包括不同版本的 Skype 多池环境中部署 Skype 会议室系统。</span><span class="sxs-lookup"><span data-stu-id="bf262-106">This section provides guidance if you are deploying Skype Room System in a multi-pool environment that includes different versions of Skype for Business Server, or Lync Server.</span></span> 
  
<span data-ttu-id="bf262-107">Lync Server 中的用户复制程序 (UR) 组件从 Active Directory 获取用户对象并将它们放入 Lync Server 后端 SQL Server 数据库中。</span><span class="sxs-lookup"><span data-stu-id="bf262-107">The User Replicator (UR) component in Lync Server gets user objects from Active Directory and places them into the Lync Server back-end SQL Server database.</span></span> <span data-ttu-id="bf262-108">Lync Server 2013 中的 UR 已知道 Skype 会议室系统对象。</span><span class="sxs-lookup"><span data-stu-id="bf262-108">Only the UR in Lync Server 2013 is aware of Skype Room System objects.</span></span> <span data-ttu-id="bf262-109">以前版本的 Lync Server 和 Office Communications Server 中的 UR 不影响指定 LR 对象的 Active Directory 属性，因此无法识别它们。</span><span class="sxs-lookup"><span data-stu-id="bf262-109">The UR in previous versions of Lync Server and Office Communications Server do not detect the Active Directory attributes that designate LRS objects, and therefore was not aware of them.</span></span> 
  
<span data-ttu-id="bf262-110">LRS 如果 Skype 会议室系统帐户尝试登录到 Lync，并执行基于 SRV 记录或 DNS A 记录查找自动发现，并且这些帐户指向 Lync Server 或 Office Communications Server 的早期版本，将收到 404 找不到响应 旧池。</span><span class="sxs-lookup"><span data-stu-id="bf262-110">If a Skype Room System account tries to sign in to Lync , and performs auto discovery based on SRV record or DNS A record look up, and if those accounts point to a previous version of Lync Server or Office Communications Server, LRS will receive a 404 Not Found response from the legacy pool.</span></span> <span data-ttu-id="bf262-111">旧池不能将 Skype 会议室系统重定向到其 Lync Server 2013 的主池。</span><span class="sxs-lookup"><span data-stu-id="bf262-111">The legacy pool will not be able to redirect Skype Room System to its Lync Server 2013 home pool.</span></span> 
  
<span data-ttu-id="bf262-112">你可以通过以下方法解决此问题：</span><span class="sxs-lookup"><span data-stu-id="bf262-112">You can address this problem with the following options:</span></span> 
  
- <span data-ttu-id="bf262-113">将你的自动发现 SRV 记录 (_sipinternaltls._tcp.contoso.com) 指向 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="bf262-113">Point your autodiscover SRV record (_sipinternaltls._tcp.contoso.com) to Lync Server 2013 pool.</span></span>
    
- <span data-ttu-id="bf262-114">如果不可能的第一个选项，您必须手动配置 LRS 并直接 Skype 会议室系统控制台应用程序中对其进行配置，以提供 Lync Server 2013 池地址。</span><span class="sxs-lookup"><span data-stu-id="bf262-114">If the first option isn't possible, you must manually configure LRS and provide the Lync Server 2013 pool address by directly configuring it in the Skype Room System console application.</span></span> 
    
- <span data-ttu-id="bf262-115">如果 Skype 会议室系统部署企业网络外部的并且已部署并配置为指向旧池或控制器 Lync 边缘服务器，第二的边缘服务器网站是必需的其指向 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="bf262-115">If Skype Room System is deployed outside the corporate network, and a Lync Edge Server has been deployed and configured to point to a legacy pool or director, a secondary Edge Server site is required, which points to the Lync Server 2013 pool.</span></span> <span data-ttu-id="bf262-116">有关部署第二个边缘服务器的详细信息，请参阅边缘服务器部署文档。</span><span class="sxs-lookup"><span data-stu-id="bf262-116">Refer to the Edge Server deployment documentation for more information about deploying a secondary Edge Server.</span></span> 
    
## <a name="skype-room-system-interoperability-with-a-lync-server-2010-pool"></a><span data-ttu-id="bf262-117">Skype 会议室与 Lync Server 2010 池的系统互操作性</span><span class="sxs-lookup"><span data-stu-id="bf262-117">Skype Room System Interoperability with a Lync Server 2010 Pool</span></span>

<span data-ttu-id="bf262-118">在迁移期间，如果用户驻留在 Lync Server 2010 池上安排会议并邀请 Skype 会议室系统帐户的 Skype 会议室 System 客户端功能将受到限制参加会议时。</span><span class="sxs-lookup"><span data-stu-id="bf262-118">During migration, if a user who is homed on a Lync Server 2010 pool schedules a meeting and invites the Skype Room System account, the Skype Room System client will have limited functionality while attending the meeting.</span></span> 
  
<span data-ttu-id="bf262-119">当的 Skype 会议室 System 客户端加入计划的电话会议的已按驻留在 Lync Server 2010 的用户，Skype 会议室系统具有以下会议中限制：</span><span class="sxs-lookup"><span data-stu-id="bf262-119">When the Skype Room System client joins a scheduled conference call that has been organized by a user homed on Lync Server 2010, Skype Room System has the following in-meeting limitations:</span></span> 
  
- <span data-ttu-id="bf262-120">Skype 会议室系统无法显示多视图视频库。</span><span class="sxs-lookup"><span data-stu-id="bf262-120">Skype Room System cannot show the multi-view video gallery.</span></span>
    
- <span data-ttu-id="bf262-121">如果演示者的 Skype 会议室 System 客户端，它不能在参与者应用视频锁。</span><span class="sxs-lookup"><span data-stu-id="bf262-121">If the Skype Room System client is the presenter, it cannot apply video lock on participants.</span></span>
    
- <span data-ttu-id="bf262-122">Skype 会议室系统无法显示 1080p 视频分辨率 （入站或出站），即使 Lync Server 2013 会议策略允许，原因如下：</span><span class="sxs-lookup"><span data-stu-id="bf262-122">Skype Room System cannot show 1080p video resolution (inbound or outbound), even if the Lync Server 2013 conferencing policy allows it, because of the following:</span></span> 
    
  - <span data-ttu-id="bf262-123">Lync Server 2010 不支持 1080p 的分辨率。</span><span class="sxs-lookup"><span data-stu-id="bf262-123">Lync Server 2010 doesn't support 1080p resolution.</span></span>
    
  - <span data-ttu-id="bf262-124">Skype 会议室系统始终受到组织者的会议策略的视频分辨率。</span><span class="sxs-lookup"><span data-stu-id="bf262-124">Skype Room System is always limited by the organizer's conferencing policy for video resolution.</span></span> <span data-ttu-id="bf262-125">因此，即使 Lync 2010 池支持 720 p 分辨率，Skype 会议室系统将不能利用 720 p 解决方案，只要组织者的策略不支持它。</span><span class="sxs-lookup"><span data-stu-id="bf262-125">Therefore, even if the Lync 2010 pool supports 720p resolution, Skype Room System will not be able to take advantage of 720p resolution as long as organizer's policy doesn't support it.</span></span> 
    
- <span data-ttu-id="bf262-p105">Lync 2013 客户端在会议室中检测 LRS 状态，它们会自动将自己静音以避免物理会议室中产生回声。此功能在 Lync Server 2010 上主持的会议中不适用。</span><span class="sxs-lookup"><span data-stu-id="bf262-p105">Lync 2013 clients detect LRS presence in the meeting room, and they auto-mute themselves to avoid echo in the physical meeting room. This feature does not work in meetings hosted on Lync Server 2010.</span></span>
    
- <span data-ttu-id="bf262-128">对于在 Lync Server 2010 上主持的会议，桌面共享功能存在一些限制。</span><span class="sxs-lookup"><span data-stu-id="bf262-128">There are limitations on desktop sharing performance for meetings hosted on Lync Server 2010.</span></span>
    
- <span data-ttu-id="bf262-129">用户将无法加入专用 （受限） 承载的会议在 Lync 2010 与 Skype 会议室系统。</span><span class="sxs-lookup"><span data-stu-id="bf262-129">Users won't be able to join private (restricted) meetings that are hosted on Lync 2010 with Skype Room System.</span></span>
    

