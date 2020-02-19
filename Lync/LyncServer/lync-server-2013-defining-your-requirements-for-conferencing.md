---
title: Lync Server 2013：定义会议要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your requirements for conferencing
ms:assetid: 5c83e268-22bf-42b2-bac3-3237b5e02e03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204935(v=OCS.15)
ms:contentKeyID: 48184255
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee3b7631a3c05fb497ee7fcdf37b6db984361845
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137813"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="70974-102">在 Lync Server 2013 中定义会议要求</span><span class="sxs-lookup"><span data-stu-id="70974-102">Defining your requirements for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="70974-103">_**上次修改的主题：** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="70974-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="70974-p101">在确定要部署的会议功能时，需要考虑您希望向用户提供的功能和网络带宽功能。以下问题列表将指导您完成会议规划过程，以便根据您的组织的要求确定应部署哪些会议功能。</span><span class="sxs-lookup"><span data-stu-id="70974-p101">When you are determining which conferencing capabilities to deploy, you need to consider the features that you want available to your users and your network bandwidth capabilities. The following list of questions guides you through the conferencing planning process to determine what features of conferencing you should deploy, based on your organization’s requirements.</span></span>

  - <span data-ttu-id="70974-106">**是否要启用包括文档协作和应用程序共享的 Web 会议？**</span><span class="sxs-lookup"><span data-stu-id="70974-106">**Do you want to enable web conferencing, which includes document collaboration and application sharing?**</span></span>
    
    <span data-ttu-id="70974-107">如果是这样，则必须在 Microsoft Lync Server 2013、规划工具或拓扑生成器中为前端池启用会议。</span><span class="sxs-lookup"><span data-stu-id="70974-107">If so, you must enable conferencing for your Front End pool in the Microsoft Lync Server 2013, Planning Tool or in Topology Builder.</span></span> <span data-ttu-id="70974-108">启用会议时会同时启用 Web 会议和 A/V 会议。</span><span class="sxs-lookup"><span data-stu-id="70974-108">When you enable conferencing, you enable both web conferencing and A/V conferencing.</span></span>
    
    <span data-ttu-id="70974-109">与文档协作相比，应用程序共享要求使用更多的网络带宽。</span><span class="sxs-lookup"><span data-stu-id="70974-109">Application sharing requires and uses more network bandwidth than document collaboration.</span></span> <span data-ttu-id="70974-110">Lync Server 2013 提供了用于控制每个应用程序共享会话的限制机制。</span><span class="sxs-lookup"><span data-stu-id="70974-110">Lync Server 2013 provides a throttling mechanism to control each application sharing session.</span></span> <span data-ttu-id="70974-111">默认情况下，每个会话设置为 1.5 KB/秒。</span><span class="sxs-lookup"><span data-stu-id="70974-111">By default, this is set to 1.5 KB/second for each session.</span></span>
    
    <span data-ttu-id="70974-112">如果您不希望启用应用程序共享，但希望启用文档协作，则可以启用会议并使用会议策略来禁用应用程序共享。</span><span class="sxs-lookup"><span data-stu-id="70974-112">If you do not want to enable application sharing but you do want document collaboration, you can enable conferencing and use meeting policies to disable application sharing.</span></span> <span data-ttu-id="70974-113">有关配置会议策略的详细信息，请参阅[Lync Server 2013 中的会议策略](lync-server-2013-conferencing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="70974-113">For details about configuring meeting policies, see [Conferencing policies in Lync Server 2013](lync-server-2013-conferencing-policies.md).</span></span>
    
    <span data-ttu-id="70974-114">若要使用户能够共享 PowerPoint 演示文稿，您需要配置 Office Web Apps Server。</span><span class="sxs-lookup"><span data-stu-id="70974-114">To enable users to share PowerPoint presentations, you need to configure Office Web Apps Server.</span></span> <span data-ttu-id="70974-115">有关配置 Office Web Apps Server 的详细信息，请参阅[配置与 Office Web Apps server 和 Lync Server 2013 的集成](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="70974-115">For details about configuring Office Web Apps Server, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

  - <span data-ttu-id="70974-116">**是否要启用 A/V 会议？**</span><span class="sxs-lookup"><span data-stu-id="70974-116">**Do you want to enable A/V conferencing?**</span></span>
    
    <span data-ttu-id="70974-117">如果是这样，则必须在 Lync Server 2013、规划工具或拓扑生成器中为前端池启用会议。</span><span class="sxs-lookup"><span data-stu-id="70974-117">If so, you must enable conferencing for your Front End pool in the Lync Server 2013, Planning Tool or in Topology Builder.</span></span> <span data-ttu-id="70974-118">启用会议时会同时启用 Web 会议和 A/V 会议。</span><span class="sxs-lookup"><span data-stu-id="70974-118">When you enable conferencing, you enable both web conferencing and A/V conferencing.</span></span>
    
    <span data-ttu-id="70974-p107">与 Web 会议（包括文档协作和应用程序共享）相比，A/V 会议要求并使用更多的网络带宽。如果您不希望启用 A/V 会议，但希望启用 Web 会议，则可以启用会议并使用会议策略来禁用 A/V 会议。</span><span class="sxs-lookup"><span data-stu-id="70974-p107">A/V conferencing requires and uses more network bandwidth than web conferencing (which includes document collaboration and application sharing). If you do not want to enable A/V conferencing but you do want to enable web conferencing, you can enable conferencing and use meeting policies to disable A/V conferences.</span></span>
    
    <span data-ttu-id="70974-p108">如果希望启用音频会议但不启用视频会议，则可以启用 A/V 会议并使用会议策略来阻止视频会议。或者，可以启用 A/V 会议并且只允许某些用户来启动或参加 A/V 会议。</span><span class="sxs-lookup"><span data-stu-id="70974-p108">If you do want to enable audio conferences but not video conferences, you can enable A/V conferencing and use meeting policies to prevent video conferences. Alternatively, you can enable A/V conferencing and enable only certain users to start or participate in A/V conferences.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="70974-123">您无需使用企业语音即可使用 A/V 会议。</span><span class="sxs-lookup"><span data-stu-id="70974-123">Enterprise Voice is not required for you to use A/V conferencing.</span></span> <span data-ttu-id="70974-124">如果您启用 A/V 会议，并且您的用户有音频设备，则他们可以将音频添加到其会议，即使您使用 PBX 作为电话解决方案也是如此。</span><span class="sxs-lookup"><span data-stu-id="70974-124">If you enable A/V conferencing, your users can add audio to their conferences if they have audio devices, even if you use a PBX for your telephone solution.</span></span>

    
    </div>

  - <span data-ttu-id="70974-125">**使用 PSTN 电话时，是否要允许用户加入会议的音频部分？**</span><span class="sxs-lookup"><span data-stu-id="70974-125">**Do you want to enable users to join the audio portion of conferences when using a PSTN phone?**</span></span>
    
    <span data-ttu-id="70974-p110">如果是，则部署并启用电话拨入式会议。然后，组织内部和外部的受邀用户可以使用 PSTN 电话加入会议的音频部分。</span><span class="sxs-lookup"><span data-stu-id="70974-p110">If so, deploy and enable dial-in conferencing. Invited users, both inside and outside your organization, can then join the audio portion of conferences by using a PSTN phone.</span></span>

  - <span data-ttu-id="70974-128">**是否要使用 Lync Server 2013 客户端启用外部用户以加入已启用的会议类型？**</span><span class="sxs-lookup"><span data-stu-id="70974-128">**Do you want to enable external users with Lync Server 2013 clients to join the types of conferences that you have enabled?**</span></span>
    
    <span data-ttu-id="70974-129">如果是，则应部署边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="70974-129">If so, you should deploy Edge Servers.</span></span> <span data-ttu-id="70974-130">通过允许外部参与会议，你可以最大限度地提高 Lync Server 2013 的投资。</span><span class="sxs-lookup"><span data-stu-id="70974-130">By allowing external participation in meetings, you maximize your investment in Lync Server 2013.</span></span> <span data-ttu-id="70974-131">例如，具有 Lync Server 2013 的便携式计算机的用户可以在在家、在机场或在客户网站中的任何地方加入会议。</span><span class="sxs-lookup"><span data-stu-id="70974-131">For example, users with laptops with Lync Server 2013 can join conferences from wherever they are—at home, in the airport, or at customer sites.</span></span>
    
    <span data-ttu-id="70974-132">此外，通过部署边缘服务器，可以与其他组织（如您的客户或供应商）建立联盟关系，这样，来自这些组织的用户便可以更轻松地与您的用户协作。</span><span class="sxs-lookup"><span data-stu-id="70974-132">Additionally, with Edge Servers deployed you can create federated relationships with other organizations-such as your customers or vendors-and users from those organizations can more easily collaborate with your users.</span></span>
    
    <span data-ttu-id="70974-133">有关部署边缘服务器的详细信息，请参阅在 lync server [2013 中规划外部用户访问](lync-server-2013-planning-for-external-user-access.md)和[在 lync Server 2013 中部署外部用户访问](lync-server-2013-deploying-external-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="70974-133">For details about deploying Edge Servers, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) and [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span></span> <span data-ttu-id="70974-134">有关启用 Office Web Apps Server 外部访问的详细信息，请参阅[使用反向代理服务器在 Lync Server 2013 中发布 Office Web Apps server](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md)。</span><span class="sxs-lookup"><span data-stu-id="70974-134">For details about enabling external access for Office Web Apps Server, see [Publishing Office Web Apps Server in Lync Server 2013 using a reverse proxy server](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md).</span></span>

  - <span data-ttu-id="70974-135">**是否要控制可加入 Lync Server 2013 会议的客户端？**</span><span class="sxs-lookup"><span data-stu-id="70974-135">**Do you want to control the clients that can join Lync Server 2013 meetings?**</span></span>
    
    <span data-ttu-id="70974-136">如果是，则应配置与会页面，以便只有要支持的客户端选项可用。</span><span class="sxs-lookup"><span data-stu-id="70974-136">If so, you should configure the meeting join page so that only the client options that you want to support are available.</span></span> <span data-ttu-id="70974-137">用户每次单击链接加入计划的会议时，Lync Server 2013 将检测是否已在计算机上安装了客户端。</span><span class="sxs-lookup"><span data-stu-id="70974-137">Each time a user clicks a link to join a scheduled meeting, Lync Server 2013 detects whether a client is already installed on the computer.</span></span> <span data-ttu-id="70974-138">然后，启动默认客户端，并打开包含备用客户端的链接的与会页面。</span><span class="sxs-lookup"><span data-stu-id="70974-138">It then starts the default client and opens the meeting join page, which contains links for alternate clients.</span></span> <span data-ttu-id="70974-139">与会页面始终包含使用 Microsoft Lync Web App 的选项。</span><span class="sxs-lookup"><span data-stu-id="70974-139">The meeting join page always contains the option to use Microsoft Lync Web App.</span></span> <span data-ttu-id="70974-140">除了此选项之外，您还可以决定是否包括与会者的链接和以前版本的 Communicator。</span><span class="sxs-lookup"><span data-stu-id="70974-140">In addition to this option, you can decide whether to include links for Attendee and previous versions of Communicator.</span></span> <span data-ttu-id="70974-141">有关详细信息，请参阅[在 Lync Server 2013 中配置会议加入页面](lync-server-2013-configuring-the-meeting-join-page.md)。</span><span class="sxs-lookup"><span data-stu-id="70974-141">For details, see [Configuring the meeting join page in Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="70974-142">本部分内容</span><span class="sxs-lookup"><span data-stu-id="70974-142">In This Section</span></span>

  - [<span data-ttu-id="70974-143">Lync Server 2013 中的 Web 会议要求</span><span class="sxs-lookup"><span data-stu-id="70974-143">Web conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-web-conferencing-requirements.md)

  - [<span data-ttu-id="70974-144">Lync Server 2013 中的 A/V 会议要求</span><span class="sxs-lookup"><span data-stu-id="70974-144">A/V conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-a-v-conferencing-requirements.md)

  - [<span data-ttu-id="70974-145">Lync Server 2013 中的电话拨入式会议要求</span><span class="sxs-lookup"><span data-stu-id="70974-145">Dial-in conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-dial-in-conferencing-requirements.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="70974-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="70974-146">See Also</span></span>


[<span data-ttu-id="70974-147">在 Lync Server 2013 中规划会议</span><span class="sxs-lookup"><span data-stu-id="70974-147">Planning for conferencing in Lync Server 2013</span></span>](lync-server-2013-planning-for-conferencing.md)  
[<span data-ttu-id="70974-148">Lync Server 2013 中的会议的部署清单</span><span class="sxs-lookup"><span data-stu-id="70974-148">Deployment checklist for conferencing in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

