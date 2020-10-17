---
title: Lync Server 2013：呼叫寄存的概述
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Call Park
ms:assetid: 985dc326-0aef-4308-b98b-c1d0069311e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205124(v=OCS.15)
ms:contentKeyID: 48184939
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 22811a0c55f0e0c7a7bfb7f3aeeb3ab5fcbc2653
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530669"
---
# <a name="overview-of-call-park-in-lync-server-2013"></a><span data-ttu-id="0a9f3-102">Lync Server 2013 中的呼叫寄存概述</span><span class="sxs-lookup"><span data-stu-id="0a9f3-102">Overview of Call Park in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0a9f3-103">_**上次修改的主题：** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="0a9f3-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="0a9f3-104">Lync Server 2013 呼叫寄存应用程序允许企业语音用户执行以下任一操作：</span><span class="sxs-lookup"><span data-stu-id="0a9f3-104">The Lync Server 2013 Call Park application lets Enterprise Voice users do any of the following:</span></span>

  - <span data-ttu-id="0a9f3-105">将呼叫置于保持状态，然后从同一电话或其他电话检索呼叫。</span><span class="sxs-lookup"><span data-stu-id="0a9f3-105">Put a call on hold and then retrieve the call from the same phone or another phone.</span></span>

  - <span data-ttu-id="0a9f3-106">将呼叫置于保持状态以将其转移到部门或常规区域 (例如，转移到存在公用区域电话) 的销售部门或仓库。</span><span class="sxs-lookup"><span data-stu-id="0a9f3-106">Put a call on hold to transfer it to a department or general area (for example, to a sales department or a warehouse where there is a common area phone).</span></span>

  - <span data-ttu-id="0a9f3-107">将呼叫置于保持状态，并保持原始应答电话对其他呼叫空闲。</span><span class="sxs-lookup"><span data-stu-id="0a9f3-107">Put a call on hold and keep the original answering phone free for other calls.</span></span>

<span data-ttu-id="0a9f3-108">当用户公园呼叫时，Lync Server 会将呼叫转移到一个临时号码（称为 " *轨道*"），其中呼叫将一直保留，直到检索或超时。Lync Server 将轨道发送给寄存呼叫的用户。</span><span class="sxs-lookup"><span data-stu-id="0a9f3-108">When a user parks a call, Lync Server transfers the call to a temporary number, called an *orbit*, where the call is held until it is retrieved or it times out. Lync Server sends the orbit to the user who parked the call.</span></span> <span data-ttu-id="0a9f3-109">若要检索寄存的呼叫，用户可以拨打轨道编号或单击对话窗口中的 "轨道" 链接或按钮。</span><span class="sxs-lookup"><span data-stu-id="0a9f3-109">To retrieve the parked call, the user can dial the orbit number or click the orbit link or button in the Conversation window.</span></span>

<span data-ttu-id="0a9f3-110">停用呼叫的用户可以通过外部机制（如即时消息 (IM) 或寻呼系统）通知他人检索呼叫，以将轨道编号传递给其他人。</span><span class="sxs-lookup"><span data-stu-id="0a9f3-110">The user who parked a call can notify someone to retrieve the call by using an external mechanism, such as instant messaging (IM) or a paging system, to communicate the orbit number to someone else.</span></span> <span data-ttu-id="0a9f3-111">停用呼叫的用户可以将对话窗口保持打开状态，以便在检索呼叫时接收通知。</span><span class="sxs-lookup"><span data-stu-id="0a9f3-111">The user who parked the call can leave the Conversation window open to receive notification when the call is retrieved.</span></span>

<span data-ttu-id="0a9f3-112">由于轨道范围是全局唯一的，因此，如果路由配置正确，则可以从任何 Lync Server 站点或 PBX 电话检索呼叫。</span><span class="sxs-lookup"><span data-stu-id="0a9f3-112">Because orbit ranges are globally unique, it is possible to retrieve calls from any Lync Server site or PBX phone if routing is configured appropriately.</span></span> <span data-ttu-id="0a9f3-113">如果没有人在一段可配置的时间内检索呼叫，则该呼叫将环回到寄存该呼叫的人。</span><span class="sxs-lookup"><span data-stu-id="0a9f3-113">If no one retrieves the call within a configurable amount of time, the call rings back to the person who parked it.</span></span> <span data-ttu-id="0a9f3-114">如果此人不应答回拨，则会将呼叫转移到一个回退目标，例如，如果配置了，则转移到某个操作员。</span><span class="sxs-lookup"><span data-stu-id="0a9f3-114">If that person does not answer the ringback, the call is transferred to a fallback destination, such as to an operator, if so configured.</span></span> <span data-ttu-id="0a9f3-115">可以将呼叫响铃的次数配置为从1到10次转接。</span><span class="sxs-lookup"><span data-stu-id="0a9f3-115">You can configure the number of times the call rings back before being transferred from one to ten times.</span></span> <span data-ttu-id="0a9f3-116">如果没有人应答转移的呼叫，则呼叫将断开连接。</span><span class="sxs-lookup"><span data-stu-id="0a9f3-116">If no one answers a transferred call, the call is disconnected.</span></span> <span data-ttu-id="0a9f3-117">检索或断开呼叫时，将释放轨道。</span><span class="sxs-lookup"><span data-stu-id="0a9f3-117">The orbit is freed when the call is retrieved or disconnected.</span></span>

<span data-ttu-id="0a9f3-118">当您部署呼叫寄存时，需要为停车呼叫保留分机号码的范围。</span><span class="sxs-lookup"><span data-stu-id="0a9f3-118">When you deploy Call Park, you need to reserve ranges of extension numbers for parking calls.</span></span> <span data-ttu-id="0a9f3-119">这些扩展必须是虚拟扩展：没有向其分配用户或电话的扩展。</span><span class="sxs-lookup"><span data-stu-id="0a9f3-119">These extensions need to be virtual extensions: extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="0a9f3-120">然后，使用分机号码范围配置呼叫寄存通道表，并指定哪个应用程序服务承载处理每个范围的呼叫寄存应用程序。</span><span class="sxs-lookup"><span data-stu-id="0a9f3-120">You then configure the call park orbit table with the ranges of extension numbers and specify which Application service hosts the Call Park application that handles each range.</span></span> <span data-ttu-id="0a9f3-121">每个前端池在对应的后端服务器上都有一个呼叫寄存表，用于管理驻留在池上的呼叫。</span><span class="sxs-lookup"><span data-stu-id="0a9f3-121">Each Front End pool has a Call Park table on the corresponding Back End Server that is used to manage calls that are parked on the pool.</span></span> <span data-ttu-id="0a9f3-122">轨道范围列表存储在中央管理存储中，用于将轨道式路由到目标池。</span><span class="sxs-lookup"><span data-stu-id="0a9f3-122">The list of orbit ranges is stored in Central Management store and is used to route orbits to the destination pool.</span></span> <span data-ttu-id="0a9f3-123">在其中部署和配置呼叫寄存应用程序的每个 Lync Server 池都可以有一个或多个轨道范围。</span><span class="sxs-lookup"><span data-stu-id="0a9f3-123">Each Lync Server pool where the Call Park application is deployed and configured can have one or more orbit ranges.</span></span> <span data-ttu-id="0a9f3-124">在 Lync Server 部署中，轨道范围必须是全局唯一的。</span><span class="sxs-lookup"><span data-stu-id="0a9f3-124">Orbit ranges must be globally unique across the Lync Server deployment.</span></span>

<span data-ttu-id="0a9f3-125">此外，还可以配置其他呼叫寄存设置，例如在呼叫超时的位置，以及电话上的人员是否在寄存时听到音乐。</span><span class="sxs-lookup"><span data-stu-id="0a9f3-125">You also configure other Call Park settings, such as where calls are redirected if they time out and whether the person on the phone hears music while parked.</span></span> <span data-ttu-id="0a9f3-126">您还可以指定要在呼叫处于保留状态时播放的音乐文件。</span><span class="sxs-lookup"><span data-stu-id="0a9f3-126">You can also specify the music file to play while the call is on hold.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0a9f3-127">在 Lync Server 2013 灾难恢复过程中，不会将呼叫寄存的自定义音乐保留文件作为一部分进行备份，如果上载到池的文件已损坏、损坏或清除，则将丢失。</span><span class="sxs-lookup"><span data-stu-id="0a9f3-127">Customized music-on-hold files for Call Park are not backed up as part of the Lync Server 2013 disaster recovery process and will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span> <span data-ttu-id="0a9f3-128">始终为已为呼叫寄存上载的自定义的保留音乐文件保留一个单独的备份副本。</span><span class="sxs-lookup"><span data-stu-id="0a9f3-128">Always keep a separate backup copy of the customized music-on-hold files that you have uploaded for Call Park.</span></span>



</div>

<span data-ttu-id="0a9f3-129">呼叫寄存应用程序是企业语音的一个组件。</span><span class="sxs-lookup"><span data-stu-id="0a9f3-129">The Call Park application is a component of Enterprise Voice.</span></span> <span data-ttu-id="0a9f3-130">部署企业语音时，会自动安装并激活呼叫寄存应用程序。</span><span class="sxs-lookup"><span data-stu-id="0a9f3-130">When you deploy Enterprise Voice, the Call Park application is installed and activated automatically.</span></span> <span data-ttu-id="0a9f3-131">但是，在使用呼叫寄存之前，企业语音管理员必须对其进行配置，并通过语音策略为用户启用呼叫寄存。</span><span class="sxs-lookup"><span data-stu-id="0a9f3-131">Before you can use Call Park, however, the Enterprise Voice administrator must configure it and enable it for users through voice policy.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

