---
title: Lync Server 2013：设置大型会议的支持
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up support for large meetings
ms:assetid: 8e22d34b-b395-408d-9d48-8f2a3abe9513
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205074(v=OCS.15)
ms:contentKeyID: 48184763
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e8331c28d5bd06e6a3f7d9dab2fba7db334cd00
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764558"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-support-for-large-meetings-in-lync-server-2013"></a><span data-ttu-id="e095d-102">在 Lync Server 2013 中设置对大型会议的支持</span><span class="sxs-lookup"><span data-stu-id="e095d-102">Setting up support for large meetings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e095d-103">_**主题上次修改时间：** 2014-05-12_</span><span class="sxs-lookup"><span data-stu-id="e095d-103">_**Topic Last Modified:** 2014-05-12_</span></span>

<span data-ttu-id="e095d-104">支持最多1000个用户的大型会议需要创建合适的拓扑、满足硬件和软件先决条件，并相应地配置环境。</span><span class="sxs-lookup"><span data-stu-id="e095d-104">Supporting large meetings of up to 1000 users requires creating an appropriate topology, meeting hardware and software prerequisites, and configuring the environment appropriately.</span></span>

<div>

## <a name="topology-requirements"></a><span data-ttu-id="e095d-105">拓扑要求</span><span class="sxs-lookup"><span data-stu-id="e095d-105">Topology Requirements</span></span>

<span data-ttu-id="e095d-106">一个大型会议至少需要一个前端服务器和一个后端服务器。</span><span class="sxs-lookup"><span data-stu-id="e095d-106">A single large meeting requires at least one Front End Server and one Back End Server.</span></span> <span data-ttu-id="e095d-107">但是，若要提供高可用性，建议使用具有镜像后端服务器的两个前端服务器池。</span><span class="sxs-lookup"><span data-stu-id="e095d-107">However, to provide high availability, we recommend a two Front End Server pool with mirrored Back End Servers.</span></span>

<span data-ttu-id="e095d-108">托管大型会议的用户必须将其用户帐户托管在此池中。</span><span class="sxs-lookup"><span data-stu-id="e095d-108">The user who hosts the large meetings must have their user account homed in this pool.</span></span> <span data-ttu-id="e095d-109">但是，我们不建议你在此池中托管其他用户帐户。</span><span class="sxs-lookup"><span data-stu-id="e095d-109">However, we do not recommend that you host other user accounts in this pool.</span></span> <span data-ttu-id="e095d-110">而只是将其用于大型会议。</span><span class="sxs-lookup"><span data-stu-id="e095d-110">Instead, use it only for the large meetings.</span></span> <span data-ttu-id="e095d-111">最佳做法是在此池中创建一个仅用于托管大型会议的特殊用户帐户。</span><span class="sxs-lookup"><span data-stu-id="e095d-111">The best practice is to create a special user account in this pool to be used only to host large meetings.</span></span> <span data-ttu-id="e095d-112">由于大型会议设置已针对性能进行优化，因此将其用作普通用户可能会遇到问题，例如在涉及 PSTN 终结点时无法将 P2P 会话提升到会议。</span><span class="sxs-lookup"><span data-stu-id="e095d-112">Since the large meeting setting is optimized for performance, using it as a normal user could have problems such as the inability to promote a P2P session to a meeting when a PSTN endpoint is involved.</span></span>

<span data-ttu-id="e095d-113">在管理恰好包含两个前端服务器的池时，有一些特别注意事项。</span><span class="sxs-lookup"><span data-stu-id="e095d-113">Managing a pool with exactly two Front End Servers requires some special considerations.</span></span> <span data-ttu-id="e095d-114">有关详细信息，请参阅[Lync Server 2013 中前端服务器、即时消息和状态的拓扑和组件](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md)。</span><span class="sxs-lookup"><span data-stu-id="e095d-114">For more information, see [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span></span>

<span data-ttu-id="e095d-115">此外，如果您希望选择性地提供针对用于大型会议的池的灾难恢复备份和故障转移，您可以将该池与其他数据中心内类似的设置专用池配对。</span><span class="sxs-lookup"><span data-stu-id="e095d-115">Additionally, if you want to optionally provide disaster recovery backup and failover for the pool used for large meetings, you can pair it with a similarly set up dedicated pool in a different data center.</span></span> <span data-ttu-id="e095d-116">有关详细信息，请参阅[在 Lync Server 2013 中规划高可用性和灾难恢复](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="e095d-116">For details, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

<span data-ttu-id="e095d-117">![大型会议池配置](images/JJ205074.ee00e1c0-c3b2-464d-aa89-a1e877cd034d(OCS.15).jpg "大型会议池配置")</span><span class="sxs-lookup"><span data-stu-id="e095d-117">![Large Meetings pool configuration](images/JJ205074.ee00e1c0-c3b2-464d-aa89-a1e877cd034d(OCS.15).jpg "Large Meetings pool configuration")</span></span>

<span data-ttu-id="e095d-118">有关拓扑的其他说明包括：</span><span class="sxs-lookup"><span data-stu-id="e095d-118">Additional notes about the topology include:</span></span>

  - <span data-ttu-id="e095d-119">文件共享是存储会议内容所必需的，如果已部署和启用存档服务器，则文件共享是存储存档文件所必需的。</span><span class="sxs-lookup"><span data-stu-id="e095d-119">A file share is required for storing meeting content and, if Archiving Server is deployed and enabled, for storing the archiving files.</span></span> <span data-ttu-id="e095d-120">文件共享可专用于池，也可以是已部署该池的站点中的另一个池所使用的同一文件共享。</span><span class="sxs-lookup"><span data-stu-id="e095d-120">The file share can be dedicated to the pool or can be the same file share used by another pool at the site in which the pool is deployed.</span></span> <span data-ttu-id="e095d-121">有关配置文件共享的详细信息，请参阅为[Lync Server 2013 配置文件存储](lync-server-2013-configure-dfs-file-storage.md)。</span><span class="sxs-lookup"><span data-stu-id="e095d-121">For details about configuring the file share, see [Configure file storage for Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).</span></span>

  - <span data-ttu-id="e095d-122">要启用大型会议中的 PowerPoint 演示文稿功能，需要使用 Office Web Apps 服务器。</span><span class="sxs-lookup"><span data-stu-id="e095d-122">A Office Web Apps Server is required for enabling the PowerPoint presentation functionality in large meetings.</span></span> <span data-ttu-id="e095d-123">Office Web Apps 服务器可以专用于大型会议池，也可以是部署了专用池的网站上的其他池使用的 Office Web Apps 服务器。</span><span class="sxs-lookup"><span data-stu-id="e095d-123">The Office Web Apps Server can be dedicated to the large meeting pool or, it can be the same Office Web Apps Server used by other pools at the site in which the dedicated pool is deployed.</span></span>

  - <span data-ttu-id="e095d-124">若要实现前端服务器的负载平衡，需要实现 HTTP 流量（如会议内容下载）的硬件负载平衡。</span><span class="sxs-lookup"><span data-stu-id="e095d-124">Load balancing of the Front End Servers requires hardware load balancing for the HTTP traffic (such as meeting content download).</span></span> <span data-ttu-id="e095d-125">建议对 SIP 流量实现 DNS 负载平衡。</span><span class="sxs-lookup"><span data-stu-id="e095d-125">DNS load balancing is recommended for SIP traffic.</span></span> <span data-ttu-id="e095d-126">有关详细信息，请参阅[Lync Server 2013 的负载平衡要求](lync-server-2013-load-balancing-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e095d-126">For details see [Load balancing requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span></span>

  - <span data-ttu-id="e095d-127">如果要对专用大型会议池使用监视服务器，我们建议使用在 Lync Server 部署中的所有前端服务器池共享的监视服务器及其数据库。</span><span class="sxs-lookup"><span data-stu-id="e095d-127">If you want to use Monitoring Server for the dedicated large-meeting pool, we recommend using the Monitoring Server and its database that are shared across all of the Front End Server pools in your Lync Server deployment.</span></span>

</div>

<div>

## <a name="hardware-and-software-requirements"></a><span data-ttu-id="e095d-128">硬件和软件要求</span><span class="sxs-lookup"><span data-stu-id="e095d-128">Hardware and Software Requirements</span></span>

<span data-ttu-id="e095d-129">专用大型会议池中的服务器硬件要求与您的其他 Lync Server 2013 服务器的硬件要求相同。</span><span class="sxs-lookup"><span data-stu-id="e095d-129">The hardware requirements for servers in a dedicated large-meeting pool are the same as for your other Lync Server 2013 servers.</span></span> <span data-ttu-id="e095d-130">有关硬件要求的详细信息，请参阅 "[Lync server 2013 的服务器硬件平台](lync-server-2013-server-hardware-platforms.md)"。</span><span class="sxs-lookup"><span data-stu-id="e095d-130">For details about hardware requirements, see "[Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="e095d-131">专用大型会议池中的服务器必须满足所有 Lync Server 2013 软件要求。</span><span class="sxs-lookup"><span data-stu-id="e095d-131">Servers in a dedicated large-meeting pool must meet all Lync Server 2013 software requirements.</span></span> <span data-ttu-id="e095d-132">有关软件要求的详细信息，请参阅以下文档：</span><span class="sxs-lookup"><span data-stu-id="e095d-132">For details about software requirements, please see the following documentation:</span></span>

  - [<span data-ttu-id="e095d-133">Lync Server 2013 中的服务器和工具操作系统支持</span><span class="sxs-lookup"><span data-stu-id="e095d-133">Server and tools operating system support in Lync Server 2013</span></span>](lync-server-2013-server-and-tools-operating-system-support.md)

  - [<span data-ttu-id="e095d-134">Lync Server 2013 中的数据库软件支持</span><span class="sxs-lookup"><span data-stu-id="e095d-134">Database software support in Lync Server 2013</span></span>](lync-server-2013-database-software-support.md)

  - [<span data-ttu-id="e095d-135">Lync Server 2013 的其他软件要求</span><span class="sxs-lookup"><span data-stu-id="e095d-135">Additional software requirements for Lync Server 2013</span></span>](lync-server-2013-additional-software-requirements.md)

<span data-ttu-id="e095d-136">此外，Lync Server 2013 和所有 Lync Server 2013 客户端都必须具有最新的更新。</span><span class="sxs-lookup"><span data-stu-id="e095d-136">Additionally, both Lync Server 2013 and all Lync Server 2013 clients must have the latest updates.</span></span>

</div>

<div>

## <a name="configuration-requirements"></a><span data-ttu-id="e095d-137">配置要求</span><span class="sxs-lookup"><span data-stu-id="e095d-137">Configuration Requirements</span></span>

<span data-ttu-id="e095d-138">我们建议专门为大型会议创建新的会议策略，然后将会议策略分配给托管在专用大型会议池的用户。</span><span class="sxs-lookup"><span data-stu-id="e095d-138">We recommend creating a new conferencing policy specifically for large meetings, and then assigning the conferencing policy to the users who are homed on the dedicated large-meeting pool.</span></span> <span data-ttu-id="e095d-139">使用以下设置配置会议策略：</span><span class="sxs-lookup"><span data-stu-id="e095d-139">Configure the conferencing policy using the following settings:</span></span>

  - <span data-ttu-id="e095d-140">将**MaxMeetingSize**选项设置为**1000**。</span><span class="sxs-lookup"><span data-stu-id="e095d-140">Set the **MaxMeetingSize** option to **1000**.</span></span> <span data-ttu-id="e095d-141">（默认值为**250**。）</span><span class="sxs-lookup"><span data-stu-id="e095d-141">(The default is **250**.)</span></span>

  - <span data-ttu-id="e095d-142">将 **AllowLargeMeetings** 选项设置为 **True**。</span><span class="sxs-lookup"><span data-stu-id="e095d-142">Set the **AllowLargeMeetings** option to **True**.</span></span>

  - <span data-ttu-id="e095d-143">将 **EnableAppDesktopSharing** 选项设置为“无”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e095d-143">Set the **EnableAppDesktopSharing** option to **None**.</span></span>

  - <span data-ttu-id="e095d-144">将 **AllowUserToScheduleMeetingsWithAppSharing** 选项设置为 **False**。</span><span class="sxs-lookup"><span data-stu-id="e095d-144">Set the **AllowUserToScheduleMeetingsWithAppSharing** option to **False**.</span></span>

  - <span data-ttu-id="e095d-145">将 **AllowSharedNotes** 选项设置为 **False**。</span><span class="sxs-lookup"><span data-stu-id="e095d-145">Set the **AllowSharedNotes** option to **False**.</span></span>

  - <span data-ttu-id="e095d-146">将 **AllowAnnotations** 选项设置为 **False**。</span><span class="sxs-lookup"><span data-stu-id="e095d-146">Set the **AllowAnnotations** option to **False**.</span></span>

  - <span data-ttu-id="e095d-147">将 **DisablePowerPointAnnotations** 选项设置为 **True**。</span><span class="sxs-lookup"><span data-stu-id="e095d-147">Set the **DisablePowerPointAnnotations** option to **True**.</span></span>

  - <span data-ttu-id="e095d-148">将 **AllowMultiview** 选项设置为 **False**。</span><span class="sxs-lookup"><span data-stu-id="e095d-148">Set the **AllowMultiview** option to **False**.</span></span>

  - <span data-ttu-id="e095d-149">将 **EnableMultiviewJoin** 选项设置为 **False**。</span><span class="sxs-lookup"><span data-stu-id="e095d-149">Set the **EnableMultiviewJoin** option to **False**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e095d-150">在 Lync Server 2013 中对1000用户大型会议的支持要求会议计划程序的会议策略中的<STRONG>AllowLargeMeetings</STRONG>设置设置为 true。</span><span class="sxs-lookup"><span data-stu-id="e095d-150">The support for 1000 user large meetings in Lync Server 2013 requires the <STRONG>AllowLargeMeetings</STRONG> setting in the conferencing policy for the meeting scheduler to be set to true.</span></span> <span data-ttu-id="e095d-151">当此设置设置为 true 时，当用户加入此类会议时，Lync 体验将针对额外的大型会议进行优化。</span><span class="sxs-lookup"><span data-stu-id="e095d-151">When this setting is set to true, the Lync experience will be optimized for extra large meetings when users joins such meeting.</span></span> <span data-ttu-id="e095d-152">特别是在大型会议中，Lync 不会显示完整会议参与者列表的初始或更新，这是客户端和 Lync Server 2013 的性能瓶颈。</span><span class="sxs-lookup"><span data-stu-id="e095d-152">Specifically, in a large meeting, Lync will not show the initial or update of the full meeting participant list, which is a performance bottleneck for both the client and Lync Server 2013.</span></span> <span data-ttu-id="e095d-153">Lync 将仅显示有关用户和会议演示者列表的信息。</span><span class="sxs-lookup"><span data-stu-id="e095d-153">Instead, Lync will only show information about the user and the list of presenters of the meeting.</span></span> <span data-ttu-id="e095d-154">Lync 仍将正确显示大型会议中可用参与者的总数。</span><span class="sxs-lookup"><span data-stu-id="e095d-154">Lync will still properly shows total number of participants available in the large meetings.</span></span>



</div>

<span data-ttu-id="e095d-155">若要禁用大型会议中不需要的会议功能，需要使用此处指定的所有会议策略设置（“最大会议规模”\*\*\*\* 设置除外）。</span><span class="sxs-lookup"><span data-stu-id="e095d-155">Except for the **Maximum meeting size** setting, all the other conferencing policy settings specified here are required in order to disable conferencing capabilities that are not necessary in large meetings.</span></span>

<span data-ttu-id="e095d-156">此外，你需要配置专用的大型会议池，以便托管在池中的每个 Lync Server 2013 用户拥有相应的权限。</span><span class="sxs-lookup"><span data-stu-id="e095d-156">Additionally, you need to configure the dedicated large-meeting pool so that each Lync Server 2013 user that is homed on the pool and responsible for managing the meeting schedule has the appropriate permissions.</span></span> <span data-ttu-id="e095d-157">为此，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e095d-157">To do this, do the following:</span></span>

  - <span data-ttu-id="e095d-p114">将“指定为演示者”\*\*\*\* 选项设置为“无”\*\*\*\*。通常，大型会议的所有参与者中仅一个或几个用户可成为演示者，因此不应自动允许参与者以演示者身份参加大型会议。相反，应在计划会议时明确指定演示者，或在大型会议进行中将参与者显式提升为演示者。</span><span class="sxs-lookup"><span data-stu-id="e095d-p114">Set the **Designate as presenter** option to **None**. Typically, one or just a few users of all the participants of a large meeting are presenters, so participants should not be automatically admitted to large meetings as presenters. Instead, the presenters should be explicitly designated at meeting scheduling time, or be explicitly promoted during the large meeting.</span></span>

  - <span data-ttu-id="e095d-161">确保未选中“默认分配的会议类型”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="e095d-161">Make sure that the **Assigned conference type by default** check box is not selected.</span></span> <span data-ttu-id="e095d-162">此设置控制 Lync 2013 的联机会议加载项是否始终使用组织者分配的会议安排会议，这意味着计划的会议具有相同的联接 URL 和音频信息。</span><span class="sxs-lookup"><span data-stu-id="e095d-162">This setting controls whether the Online Meeting Add-in for Lync 2013 always schedules conferences using the organizer’s assigned conference, which means that scheduled meetings have the same join URL and audio information.</span></span> <span data-ttu-id="e095d-163">在小组协作方案中，可确保此类分配的会议类型很好地进行，因为每个用户均具有自己的单独分配的会议，并且持续加入 URL 和音频信息有助于推动更快的会议加入。</span><span class="sxs-lookup"><span data-stu-id="e095d-163">In small group collaboration scenarios, having such assigned conference type works well because everyone has their own individual assigned conference, and the constant join URL and audio information helps to facilitate faster meeting joining.</span></span> <span data-ttu-id="e095d-164">但是，在大型会议方案中，大型会议支持人员将使用一组用户凭据来计划大型会议，然后向会议请求者提供加入 URL 和音频信息。</span><span class="sxs-lookup"><span data-stu-id="e095d-164">However, in the large-meeting scenario, the large meeting support staff schedules the large meetings using a single set of user credentials, and then provides join URLs and audio information to the meeting requesters.</span></span> <span data-ttu-id="e095d-165">在此情况下，使用不同的 URL 加入各个会议所达到的效果会更佳。</span><span class="sxs-lookup"><span data-stu-id="e095d-165">In this case, using a different URL to join each meeting works better.</span></span>

  - <span data-ttu-id="e095d-166">确保未选中“默认允许匿名用户”\*\*\*\* 复选框，除非需要这样做。</span><span class="sxs-lookup"><span data-stu-id="e095d-166">Ensure that the **Admit anonymous users by default** check box is not selected, unless it is required.</span></span> <span data-ttu-id="e095d-167">此设置影响在未使用分配的会议时由 Lync 2013 的联机会议加载项计划的默认会议访问类型。</span><span class="sxs-lookup"><span data-stu-id="e095d-167">This setting affects the default meeting access type scheduled by the Online Meeting Add-in for Lync 2013 when not using an assigned conference.</span></span> <span data-ttu-id="e095d-168">此设置的相应选项取决于您的组织需求。</span><span class="sxs-lookup"><span data-stu-id="e095d-168">The appropriate option for this setting depends on your organization’s needs.</span></span> <span data-ttu-id="e095d-169">如果您组织的大多数大型会议是内部会议，请不要选择此选项。</span><span class="sxs-lookup"><span data-stu-id="e095d-169">If most large meetings for your organization are internal meetings, do not select this option.</span></span> <span data-ttu-id="e095d-170">如果大多数大型会议需要外部用户能够加入，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="e095d-170">If most large meetings require that external users be able to join, select this option.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

