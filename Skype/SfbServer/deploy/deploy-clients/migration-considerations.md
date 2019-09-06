---
title: Skype 会议室系统迁移注意事项
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df9f33b6-0360-4354-b651-bd35da533e33
description: 阅读本主题，了解如何在具有多个版本的 Skype for Business Server 和 Lync Server 的环境中部署 Skype 会议室系统。
ms.openlocfilehash: 6524a7312644ec306185b952caf17818d29344af
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "36774670"
---
# <a name="skype-room-system-migration-considerations"></a><span data-ttu-id="3a548-103">Skype 会议室系统迁移注意事项</span><span class="sxs-lookup"><span data-stu-id="3a548-103">Skype Room System migration considerations</span></span>
 
<span data-ttu-id="3a548-104">阅读本主题，了解如何在具有多个版本的 Skype for Business Server 和 Lync Server 的环境中部署 Skype 会议室系统。</span><span class="sxs-lookup"><span data-stu-id="3a548-104">Read this topic to learn about how to deploy Skype Room System in an environment that has multiple versions of Skype for Business Server and Lync Server.</span></span>
  
## <a name="migration-considerations"></a><span data-ttu-id="3a548-105">迁移注意事项</span><span class="sxs-lookup"><span data-stu-id="3a548-105">Migration considerations</span></span>

<span data-ttu-id="3a548-106">本部分介绍了如何在包含不同版本的 Skype for Business Server 或 Lync Server 的多池环境中部署 Skype 会议室系统。</span><span class="sxs-lookup"><span data-stu-id="3a548-106">This section provides guidance if you are deploying Skype Room System in a multi-pool environment that includes different versions of Skype for Business Server, or Lync Server.</span></span> 
  
<span data-ttu-id="3a548-107">Lync Server 中的用户复制程序 (UR) 组件从 Active Directory 获取用户对象并将它们放入 Lync Server 后端 SQL Server 数据库中。</span><span class="sxs-lookup"><span data-stu-id="3a548-107">The User Replicator (UR) component in Lync Server gets user objects from Active Directory and places them into the Lync Server back-end SQL Server database.</span></span> <span data-ttu-id="3a548-108">只有 Lync Server 2013 中的 UR 知道 Skype 会议室系统对象。</span><span class="sxs-lookup"><span data-stu-id="3a548-108">Only the UR in Lync Server 2013 is aware of Skype Room System objects.</span></span> <span data-ttu-id="3a548-109">以前版本的 Lync Server 和 Office Communications Server 中的 UR 不影响指定 LR 对象的 Active Directory 属性，因此无法识别它们。</span><span class="sxs-lookup"><span data-stu-id="3a548-109">The UR in previous versions of Lync Server and Office Communications Server do not detect the Active Directory attributes that designate LRS objects, and therefore was not aware of them.</span></span> 
  
<span data-ttu-id="3a548-110">如果 Skype 会议室系统帐户尝试登录 Lync，并基于 SRV 记录或 DNS A 记录查找来执行自动发现，并且如果这些帐户指向的是早期版本的 Lync Server 或 Office 通信服务器，LRS 将收到404未找到的响应 旧版池。</span><span class="sxs-lookup"><span data-stu-id="3a548-110">If a Skype Room System account tries to sign in to Lync , and performs auto discovery based on SRV record or DNS A record look up, and if those accounts point to a previous version of Lync Server or Office Communications Server, LRS will receive a 404 Not Found response from the legacy pool.</span></span> <span data-ttu-id="3a548-111">旧版池将无法将 Skype 会议室系统重定向到其 Lync Server 2013 主池。</span><span class="sxs-lookup"><span data-stu-id="3a548-111">The legacy pool will not be able to redirect Skype Room System to its Lync Server 2013 home pool.</span></span> 
  
<span data-ttu-id="3a548-112">你可以通过以下方法解决此问题：</span><span class="sxs-lookup"><span data-stu-id="3a548-112">You can address this problem with the following options:</span></span> 
  
- <span data-ttu-id="3a548-113">将你的自动发现 SRV 记录 (_sipinternaltls._tcp.contoso.com) 指向 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="3a548-113">Point your autodiscover SRV record (_sipinternaltls._tcp.contoso.com) to Lync Server 2013 pool.</span></span>
    
- <span data-ttu-id="3a548-114">如果无法使用第一个选项，则必须手动配置 LRS，并通过在 Skype 会议室系统控制台应用程序中直接配置来提供 Lync Server 2013 池地址。</span><span class="sxs-lookup"><span data-stu-id="3a548-114">If the first option isn't possible, you must manually configure LRS and provide the Lync Server 2013 pool address by directly configuring it in the Skype Room System console application.</span></span> 
    
- <span data-ttu-id="3a548-115">如果 Skype 会议室系统部署在公司网络外部，并且 Lync Edge 服务器已部署并配置为指向旧版池或控制器，则需要辅助边缘服务器网站，该站点指向 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="3a548-115">If Skype Room System is deployed outside the corporate network, and a Lync Edge Server has been deployed and configured to point to a legacy pool or director, a secondary Edge Server site is required, which points to the Lync Server 2013 pool.</span></span> <span data-ttu-id="3a548-116">有关部署第二个边缘服务器的详细信息，请参阅边缘服务器部署文档。</span><span class="sxs-lookup"><span data-stu-id="3a548-116">Refer to the Edge Server deployment documentation for more information about deploying a secondary Edge Server.</span></span> 
    
## <a name="skype-room-system-interoperability-with-a-lync-server-2010-pool"></a><span data-ttu-id="3a548-117">Skype 会议室系统与 Lync Server 2010 池的互操作性</span><span class="sxs-lookup"><span data-stu-id="3a548-117">Skype Room System Interoperability with a Lync Server 2010 Pool</span></span>

<span data-ttu-id="3a548-118">在迁移过程中，如果托管在 Lync Server 2010 池中的用户安排会议并邀请 Skype 会议室系统帐户，则 Skype 会议室系统客户将在参加会议时拥有有限的功能。</span><span class="sxs-lookup"><span data-stu-id="3a548-118">During migration, if a user who is homed on a Lync Server 2010 pool schedules a meeting and invites the Skype Room System account, the Skype Room System client will have limited functionality while attending the meeting.</span></span> 
  
<span data-ttu-id="3a548-119">当 Skype 会议室系统客户加入由驻留在 Lync Server 2010 上的用户组织的计划会议呼叫时，Skype 会议室系统具有下列会议内限制：</span><span class="sxs-lookup"><span data-stu-id="3a548-119">When the Skype Room System client joins a scheduled conference call that has been organized by a user homed on Lync Server 2010, Skype Room System has the following in-meeting limitations:</span></span> 
  
- <span data-ttu-id="3a548-120">Skype 会议室系统无法显示多视图视频库。</span><span class="sxs-lookup"><span data-stu-id="3a548-120">Skype Room System cannot show the multi-view video gallery.</span></span>
    
- <span data-ttu-id="3a548-121">如果 Skype 会议室系统客户是演示者，则不能对参与者应用视频锁。</span><span class="sxs-lookup"><span data-stu-id="3a548-121">If the Skype Room System client is the presenter, it cannot apply video lock on participants.</span></span>
    
- <span data-ttu-id="3a548-122">由于以下原因，Skype 会议室系统无法显示1080p 视频分辨率（入站或出站），即使 Lync Server 2013 会议策略允许它，也是如此：</span><span class="sxs-lookup"><span data-stu-id="3a548-122">Skype Room System cannot show 1080p video resolution (inbound or outbound), even if the Lync Server 2013 conferencing policy allows it, because of the following:</span></span> 
    
  - <span data-ttu-id="3a548-123">Lync Server 2010 不支持1080p 分辨率。</span><span class="sxs-lookup"><span data-stu-id="3a548-123">Lync Server 2010 doesn't support 1080p resolution.</span></span>
    
  - <span data-ttu-id="3a548-124">Skype 会议室系统始终受组织者的视频分辨率的会议策略的限制。</span><span class="sxs-lookup"><span data-stu-id="3a548-124">Skype Room System is always limited by the organizer's conferencing policy for video resolution.</span></span> <span data-ttu-id="3a548-125">因此，即使 Lync 2010 池支持720p 解析，如果组织者的策略不支持720p 解析，则 Skype 会议室系统将无法利用720p 解析。</span><span class="sxs-lookup"><span data-stu-id="3a548-125">Therefore, even if the Lync 2010 pool supports 720p resolution, Skype Room System will not be able to take advantage of 720p resolution as long as organizer's policy doesn't support it.</span></span> 
    
- <span data-ttu-id="3a548-p105">Lync 2013 客户端在会议室中检测 LRS 状态，它们会自动将自己静音以避免物理会议室中产生回声。此功能在 Lync Server 2010 上主持的会议中不适用。</span><span class="sxs-lookup"><span data-stu-id="3a548-p105">Lync 2013 clients detect LRS presence in the meeting room, and they auto-mute themselves to avoid echo in the physical meeting room. This feature does not work in meetings hosted on Lync Server 2010.</span></span>
    
- <span data-ttu-id="3a548-128">对于在 Lync Server 2010 上主持的会议，桌面共享功能存在一些限制。</span><span class="sxs-lookup"><span data-stu-id="3a548-128">There are limitations on desktop sharing performance for meetings hosted on Lync Server 2010.</span></span>
    
- <span data-ttu-id="3a548-129">用户无法通过 Skype 会议室系统加入 Lync 2010 上托管的专用（受限）会议。</span><span class="sxs-lookup"><span data-stu-id="3a548-129">Users won't be able to join private (restricted) meetings that are hosted on Lync 2010 with Skype Room System.</span></span>
    

