---
title: Skype 会议室系统迁移注意事项
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: df9f33b6-0360-4354-b651-bd35da533e33
description: 阅读本主题，了解如何在具有多个版本的 Skype for Business Server 和 Lync Server 的环境中部署 Skype 会议室系统。
ms.openlocfilehash: 30b2a4733ea2e2e42b8a879914a2e0e3c4903c8e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805782"
---
# <a name="skype-room-system-migration-considerations"></a><span data-ttu-id="03ff7-103">Skype 会议室系统迁移注意事项</span><span class="sxs-lookup"><span data-stu-id="03ff7-103">Skype Room System migration considerations</span></span>
 
<span data-ttu-id="03ff7-104">阅读本主题，了解如何在具有多个版本的 Skype for Business Server 和 Lync Server 的环境中部署 Skype 会议室系统。</span><span class="sxs-lookup"><span data-stu-id="03ff7-104">Read this topic to learn about how to deploy Skype Room System in an environment that has multiple versions of Skype for Business Server and Lync Server.</span></span>
  
## <a name="migration-considerations"></a><span data-ttu-id="03ff7-105">迁移注意事项</span><span class="sxs-lookup"><span data-stu-id="03ff7-105">Migration considerations</span></span>

<span data-ttu-id="03ff7-106">如果正在包含不同版本的 Skype for Business Server 或 Lync Server 的多池环境中部署 Skype 会议室系统，本部分将提供指导。</span><span class="sxs-lookup"><span data-stu-id="03ff7-106">This section provides guidance if you are deploying Skype Room System in a multi-pool environment that includes different versions of Skype for Business Server, or Lync Server.</span></span> 
  
<span data-ttu-id="03ff7-107">Lync Server 中的用户 (URL) 组件从 Active Directory 获取用户对象，然后将它们放入 Lync Server 后端SQL Server数据库中。</span><span class="sxs-lookup"><span data-stu-id="03ff7-107">The User Replicator (UR) component in Lync Server gets user objects from Active Directory and places them into the Lync Server back-end SQL Server database.</span></span> <span data-ttu-id="03ff7-108">只有 Lync Server 2013 中的 UR 可以识别 Skype 会议室系统对象。</span><span class="sxs-lookup"><span data-stu-id="03ff7-108">Only the UR in Lync Server 2013 is aware of Skype Room System objects.</span></span> <span data-ttu-id="03ff7-109">以前版本的 Lync Server 和 Office Communications Server 中的 UR 不会检测指定 LRS 对象的 Active Directory 属性，因此无法识别它们。</span><span class="sxs-lookup"><span data-stu-id="03ff7-109">The UR in previous versions of Lync Server and Office Communications Server do not detect the Active Directory attributes that designate LRS objects, and therefore was not aware of them.</span></span> 
  
<span data-ttu-id="03ff7-110">如果 Skype 会议室系统帐户尝试登录 Lync，并基于 SRV 记录或 DNS A 记录执行自动发现，如果这些帐户指向以前版本的 Lync Server 或 Office Communications Server，LRS 将收到来自旧池的 404 未找到响应。</span><span class="sxs-lookup"><span data-stu-id="03ff7-110">If a Skype Room System account tries to sign in to Lync , and performs auto discovery based on SRV record or DNS A record look up, and if those accounts point to a previous version of Lync Server or Office Communications Server, LRS will receive a 404 Not Found response from the legacy pool.</span></span> <span data-ttu-id="03ff7-111">旧池将无法将 Skype 会议室系统重定向到其 Lync Server 2013 主池。</span><span class="sxs-lookup"><span data-stu-id="03ff7-111">The legacy pool will not be able to redirect Skype Room System to its Lync Server 2013 home pool.</span></span> 
  
<span data-ttu-id="03ff7-112">可以通过以下选项解决此问题：</span><span class="sxs-lookup"><span data-stu-id="03ff7-112">You can address this problem with the following options:</span></span> 
  
- <span data-ttu-id="03ff7-113">将自动发现 SRV 记录 (_sipinternaltls._tcp.contoso.com) Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="03ff7-113">Point your autodiscover SRV record (_sipinternaltls._tcp.contoso.com) to Lync Server 2013 pool.</span></span>
    
- <span data-ttu-id="03ff7-114">如果第一个选项不可行，则必须手动配置 LRS，并直接在 Skype 会议室系统控制台应用程序中配置 Lync Server 2013 池地址并提供该地址。</span><span class="sxs-lookup"><span data-stu-id="03ff7-114">If the first option isn't possible, you must manually configure LRS and provide the Lync Server 2013 pool address by directly configuring it in the Skype Room System console application.</span></span> 
    
- <span data-ttu-id="03ff7-115">如果 Skype 会议室系统部署在企业网络外部，并且 Lync 边缘服务器已部署并配置为指向旧池或控制器，则需要指向 Lync Server 2013 池的辅助边缘服务器站点。</span><span class="sxs-lookup"><span data-stu-id="03ff7-115">If Skype Room System is deployed outside the corporate network, and a Lync Edge Server has been deployed and configured to point to a legacy pool or director, a secondary Edge Server site is required, which points to the Lync Server 2013 pool.</span></span> <span data-ttu-id="03ff7-116">有关部署辅助边缘服务器详细信息，请参阅边缘服务器部署文档。</span><span class="sxs-lookup"><span data-stu-id="03ff7-116">Refer to the Edge Server deployment documentation for more information about deploying a secondary Edge Server.</span></span> 
    
## <a name="skype-room-system-interoperability-with-a-lync-server-2010-pool"></a><span data-ttu-id="03ff7-117">与 Lync Server 2010 池的 Skype 会议室系统互操作性</span><span class="sxs-lookup"><span data-stu-id="03ff7-117">Skype Room System Interoperability with a Lync Server 2010 Pool</span></span>

<span data-ttu-id="03ff7-118">在迁移过程中，如果位于 Lync Server 2010 池上的用户安排会议并邀请 Skype 会议室系统帐户，则 Skype 会议室系统客户端在参加会议时将具有有限的功能。</span><span class="sxs-lookup"><span data-stu-id="03ff7-118">During migration, if a user who is homed on a Lync Server 2010 pool schedules a meeting and invites the Skype Room System account, the Skype Room System client will have limited functionality while attending the meeting.</span></span> 
  
<span data-ttu-id="03ff7-119">当 Skype 会议室系统客户端加入由 Lync Server 2010 上用户组织的计划电话会议时，Skype 会议室系统具有以下会议限制：</span><span class="sxs-lookup"><span data-stu-id="03ff7-119">When the Skype Room System client joins a scheduled conference call that has been organized by a user homed on Lync Server 2010, Skype Room System has the following in-meeting limitations:</span></span> 
  
- <span data-ttu-id="03ff7-120">Skype 会议室系统无法显示多视图视频库。</span><span class="sxs-lookup"><span data-stu-id="03ff7-120">Skype Room System cannot show the multi-view video gallery.</span></span>
    
- <span data-ttu-id="03ff7-121">如果 Skype 会议室系统客户端是演示者，它将无法对参与者应用视频锁定。</span><span class="sxs-lookup"><span data-stu-id="03ff7-121">If the Skype Room System client is the presenter, it cannot apply video lock on participants.</span></span>
    
- <span data-ttu-id="03ff7-122">Skype 会议室系统无法显示 1080p 视频分辨率 (入站或出站) ，即使 Lync Server 2013 会议策略允许，原因如下：</span><span class="sxs-lookup"><span data-stu-id="03ff7-122">Skype Room System cannot show 1080p video resolution (inbound or outbound), even if the Lync Server 2013 conferencing policy allows it, because of the following:</span></span> 
    
  - <span data-ttu-id="03ff7-123">Lync Server 2010 不支持 1080p 分辨率。</span><span class="sxs-lookup"><span data-stu-id="03ff7-123">Lync Server 2010 doesn't support 1080p resolution.</span></span>
    
  - <span data-ttu-id="03ff7-124">Skype 会议室系统始终受组织者的视频分辨率会议策略限制。</span><span class="sxs-lookup"><span data-stu-id="03ff7-124">Skype Room System is always limited by the organizer's conferencing policy for video resolution.</span></span> <span data-ttu-id="03ff7-125">因此，即使 Lync 2010 池支持 720p 分辨率，只要组织者的策略不支持 720p 分辨率，Skype 会议室系统也将无法利用它。</span><span class="sxs-lookup"><span data-stu-id="03ff7-125">Therefore, even if the Lync 2010 pool supports 720p resolution, Skype Room System will not be able to take advantage of 720p resolution as long as organizer's policy doesn't support it.</span></span> 
    
- <span data-ttu-id="03ff7-126">Lync 2013 客户端检测会议室中的 LRS 状态，并自动将自己静音以避免物理会议室中出现回声。</span><span class="sxs-lookup"><span data-stu-id="03ff7-126">Lync 2013 clients detect LRS presence in the meeting room, and they auto-mute themselves to avoid echo in the physical meeting room.</span></span> <span data-ttu-id="03ff7-127">此功能在 Lync Server 2010 上托管的会议中不起作用。</span><span class="sxs-lookup"><span data-stu-id="03ff7-127">This feature does not work in meetings hosted on Lync Server 2010.</span></span>
    
- <span data-ttu-id="03ff7-128">Lync Server 2010 上托管的会议的桌面共享性能存在限制。</span><span class="sxs-lookup"><span data-stu-id="03ff7-128">There are limitations on desktop sharing performance for meetings hosted on Lync Server 2010.</span></span>
    
- <span data-ttu-id="03ff7-129">用户将无法加入在 Lync 2010 (Skype 会议室) 托管的受限会议。</span><span class="sxs-lookup"><span data-stu-id="03ff7-129">Users won't be able to join private (restricted) meetings that are hosted on Lync 2010 with Skype Room System.</span></span>
    

