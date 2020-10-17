---
title: 定义和配置前端池或 Standard Edition 服务器
description: 定义和配置前端池或 Standard Edition server。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define and configure a Front End pool or Standard Edition server
ms:assetid: 713fc263-23dd-414a-b001-82932e4fe966
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398538(v=OCS.15)
ms:contentKeyID: 48184457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd632564f0a5afd1f899ee8487f633c4685d12a7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569978"
---
# <a name="define-and-configure-a-front-end-pool-or-standard-edition-server-in-lync-server-2013"></a><span data-ttu-id="637ce-103">在 Lync Server 2013 中定义和配置前端池或 Standard Edition 服务器</span><span class="sxs-lookup"><span data-stu-id="637ce-103">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="637ce-104">_**上次修改的主题：** 2013-03-08_</span><span class="sxs-lookup"><span data-stu-id="637ce-104">_**Topic Last Modified:** 2013-03-08_</span></span>

<span data-ttu-id="637ce-p101">此过程不需要本地管理员或特许域组中的成员身份。您应该以标准用户身份登录到计算机。</span><span class="sxs-lookup"><span data-stu-id="637ce-p101">This procedure does not require membership in a local administrator or privileged domain group. You should log on to a computer as a standard user.</span></span>

<span data-ttu-id="637ce-107">如果要部署企业服务器，池中的最少前端服务器数必须始终处于运行状态。</span><span class="sxs-lookup"><span data-stu-id="637ce-107">If you are deploying an Enterprise server, a minimum number of Front End Servers in a pool must be running at all times.</span></span> <span data-ttu-id="637ce-108">下表总结了这些要求。</span><span class="sxs-lookup"><span data-stu-id="637ce-108">The following table summarizes these requirements.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="637ce-109">池中的前端服务器总数</span><span class="sxs-lookup"><span data-stu-id="637ce-109">Total number of Front End Servers in the pool</span></span></th>
<th><span data-ttu-id="637ce-110">要使池正常工作所必须运行的服务器的数目</span><span class="sxs-lookup"><span data-stu-id="637ce-110">Number of servers that must be running for pool to be functional</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="637ce-111">1-2</span><span class="sxs-lookup"><span data-stu-id="637ce-111">1-2</span></span></p></td>
<td><p><span data-ttu-id="637ce-112">1</span><span class="sxs-lookup"><span data-stu-id="637ce-112">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="637ce-113">3-4</span><span class="sxs-lookup"><span data-stu-id="637ce-113">3-4</span></span></p></td>
<td><p><span data-ttu-id="637ce-114">双面</span><span class="sxs-lookup"><span data-stu-id="637ce-114">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="637ce-115">5-6</span><span class="sxs-lookup"><span data-stu-id="637ce-115">5-6</span></span></p></td>
<td><p><span data-ttu-id="637ce-116">第三章</span><span class="sxs-lookup"><span data-stu-id="637ce-116">3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="637ce-117">7-8</span><span class="sxs-lookup"><span data-stu-id="637ce-117">7-8</span></span></p></td>
<td><p><span data-ttu-id="637ce-118">4 </span><span class="sxs-lookup"><span data-stu-id="637ce-118">4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="637ce-119">9-10</span><span class="sxs-lookup"><span data-stu-id="637ce-119">9-10</span></span></p></td>
<td><p><span data-ttu-id="637ce-120">5 </span><span class="sxs-lookup"><span data-stu-id="637ce-120">5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="637ce-121">11-12</span><span class="sxs-lookup"><span data-stu-id="637ce-121">11-12</span></span></p></td>
<td><p><span data-ttu-id="637ce-122">6 </span><span class="sxs-lookup"><span data-stu-id="637ce-122">6</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]
> <span data-ttu-id="637ce-123">对于 Lync Server 2013，无论何时在池中添加或删除前端服务器，都必须重新启动服务。</span><span class="sxs-lookup"><span data-stu-id="637ce-123">For Lync Server 2013, any time you add or remove a Front End Server from the pool, you must restart services.</span></span> <span data-ttu-id="637ce-124">删除和添加服务器应作为独立操作来完成。</span><span class="sxs-lookup"><span data-stu-id="637ce-124">Removing and adding servers should be done as separate operations.</span></span> <span data-ttu-id="637ce-125">例如，如果您打算添加两台前端服务器并删除两台前端服务器，请使用以下过程：</span><span class="sxs-lookup"><span data-stu-id="637ce-125">For example, if you are going to add two Front End Servers and remove two Front End Servers, use the following process:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="637ce-126">删除两台前端服务器。</span><span class="sxs-lookup"><span data-stu-id="637ce-126">Remove the two Front End Servers.</span></span></P>
> <LI>
> <P><span data-ttu-id="637ce-127">发布并重新激活拓扑。</span><span class="sxs-lookup"><span data-stu-id="637ce-127">Publish and re-activate the topology.</span></span></P>
> <LI>
> <P><span data-ttu-id="637ce-128">重新启动服务</span><span class="sxs-lookup"><span data-stu-id="637ce-128">Restart the services</span></span></P>
> <LI>
> <P><span data-ttu-id="637ce-129">添加两台前端服务器。</span><span class="sxs-lookup"><span data-stu-id="637ce-129">Add the two Front End Servers.</span></span></P>
> <LI>
> <P><span data-ttu-id="637ce-130">发布并重新激活拓扑。</span><span class="sxs-lookup"><span data-stu-id="637ce-130">Publish and re-activate the topology.</span></span></P>
> <LI>
> <P><span data-ttu-id="637ce-131">重新启动服务。</span><span class="sxs-lookup"><span data-stu-id="637ce-131">Restart the services.</span></span></P></LI></OL>



</div>

<span data-ttu-id="637ce-132">定义拓扑之后，请使用以下过程为您的网站定义前端池。</span><span class="sxs-lookup"><span data-stu-id="637ce-132">After you have defined your topology, use the following procedure to define a Front End pool for your site.</span></span> <span data-ttu-id="637ce-133">有关定义拓扑的详细信息，请参阅 [在拓扑生成器中定义和配置拓扑以使用 Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md)。</span><span class="sxs-lookup"><span data-stu-id="637ce-133">For details about defining the topology, see [Define and configure a topology in Topology Builder for Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md).</span></span>

<div>

## <a name="to-define-a-front-end-pool"></a><span data-ttu-id="637ce-134">定义前端池</span><span class="sxs-lookup"><span data-stu-id="637ce-134">To define a Front End pool</span></span>

1.  <span data-ttu-id="637ce-135">在“定义新的前端池”向导的 **“定义新的前端池”** 页上，单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="637ce-135">In the Define New Front End Pool Wizard, on the **Define the New Front End pool** page, click **Next**.</span></span>

2.  <span data-ttu-id="637ce-136">在 " **定义前端池 FQDN** " 页面上，输入要创建的池 (FQDN) 的完全限定域名，单击 " **Enterprise Edition 前端池**"，然后单击 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="637ce-136">On the **Define the Front End pool FQDN** page, enter a fully qualified domain name (FQDN) for the pool you are creating, click **Enterprise Edition Front End pool**, and then click **Next**.</span></span>

3.  <span data-ttu-id="637ce-137">在 " **定义此池中的计算机** " 页上，为池中的第一个前端服务器输入计算机 FQDN，然后单击 " **添加**"。</span><span class="sxs-lookup"><span data-stu-id="637ce-137">On the **Define the computers in this pool** page, enter a computer FQDN for the first Front End Server in the pool, and then click **Add**.</span></span> <span data-ttu-id="637ce-138">对任何其他计算机 (要添加到池中的 12) ，请重复此步骤，然后单击 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="637ce-138">Repeat this step for any additional computers (up to twelve) that you want to add to the pool, and then click **Next**.</span></span>

4.  <span data-ttu-id="637ce-139">在“选择功能”\*\*\*\* 页上，选中希望此前端池具有的功能的复选框。</span><span class="sxs-lookup"><span data-stu-id="637ce-139">On the **Select features** page, select the check boxes for the features that you want on this Front End pool.</span></span> <span data-ttu-id="637ce-140">例如，如果仅部署即时消息 (IM) 和状态功能，则应选中 " **会议** " 复选框以允许多方 IM，但不会选择 " **拨入 (PSTN) 会议**"、" **企业语音**" 或 " **呼叫允许控制** " 复选框，因为它们代表语音、视频和协作会议功能。</span><span class="sxs-lookup"><span data-stu-id="637ce-140">For example, if you are deploying only instant messaging (IM) and presence features, you would select the **Conferencing** check box to allow multiparty IM but would not select the **Dial-in (PSTN) conferencing**, **Enterprise Voice**, or **Call Admission Control** check boxes, because they represent voice, video, and collaborative conferencing features.</span></span>
    
      - <span data-ttu-id="637ce-141">**会议**    此选择启用了一组丰富的功能，包括：</span><span class="sxs-lookup"><span data-stu-id="637ce-141">**Conferencing**   This selection enables a rich set of features including:</span></span>
        
          - <span data-ttu-id="637ce-142">IM 会话中多于两方的即时消息。</span><span class="sxs-lookup"><span data-stu-id="637ce-142">IM with more than two parties in an IM session.</span></span>
        
          - <span data-ttu-id="637ce-143">包括文档协作、应用程序共享和桌面共享的会议。</span><span class="sxs-lookup"><span data-stu-id="637ce-143">Conferencing, which includes document collaboration, application sharing, and desktop sharing.</span></span>
        
          - <span data-ttu-id="637ce-144">A/V 会议，使用户可以在不需要外部服务（如 Live Meeting 服务或第三方音频网桥）的情况下 (A/V) 会议中进行实时音频/视频。</span><span class="sxs-lookup"><span data-stu-id="637ce-144">A/V conferencing, which enables users to have real-time audio/video (A/V) conferences without the need for external services such as the Live Meeting service or a third-party audio bridge.</span></span>
    
      - <span data-ttu-id="637ce-145">\*\* (PSTN) 会议\*\*     的电话拨入式允许用户使用公开交换的电话网络 (PSTN) 电话，而无需音频会议提供商，即可加入 Lync Server 2013 会议的音频部分。</span><span class="sxs-lookup"><span data-stu-id="637ce-145">**Dial-in (PSTN) conferencing**   Allows users to join the audio portion of a Lync Server 2013 conference by using a public switched telephone network (PSTN) phone without requiring an audio conferencing provider.</span></span>
    
      - <span data-ttu-id="637ce-146">**企业语音**    企业语音是 Lync Server 2013 中的 IP 语音 (VoIP) 解决方案，允许用户拨打和接听电话呼叫。</span><span class="sxs-lookup"><span data-stu-id="637ce-146">**Enterprise Voice**   Enterprise Voice is the Voice over IP (VoIP) solution in Lync Server 2013 that allows users to make and receive phone calls.</span></span> <span data-ttu-id="637ce-147">如果计划将 Lync Server 2013 用于语音呼叫、语音邮件和其他使用硬件设备或软件客户端的功能，则应部署此功能。</span><span class="sxs-lookup"><span data-stu-id="637ce-147">You would deploy this feature if you plan to use Lync Server 2013 for voice calls, voice mail, and other functions that use a hardware device or a software client.</span></span>
    
      - <span data-ttu-id="637ce-148">\*\*呼叫允许控制 (CAC) \*\*    CAC 根据可用的网络带宽确定是否允许建立实时通信会话（如语音或视频呼叫）。</span><span class="sxs-lookup"><span data-stu-id="637ce-148">**Call admission control (CAC)**   CAC determines, based on available network bandwidth, whether to allow real-time communications sessions such as voice or video calls to be established.</span></span> <span data-ttu-id="637ce-149">如果仅部署 IM 和状态，则无需 CAC，因为这两个功能都不使用 CAC。</span><span class="sxs-lookup"><span data-stu-id="637ce-149">If you have deployed only IM and presence, CAC is not needed because neither of these two features uses CAC.</span></span>
    
      - <span data-ttu-id="637ce-150">**存档**    存档为你提供一种方式来存档 IM 内容、会议 (会议) 内容，或同时通过 Lync Server 2013 发送这两者。</span><span class="sxs-lookup"><span data-stu-id="637ce-150">**Archiving**   Archiving provides a way for you to archive IM content, conferencing (meeting) content, or both that is sent through Lync Server 2013.</span></span>
    
      - <span data-ttu-id="637ce-151">**监控**    通过监控服务器，可以收集描述网络和终结点上的媒体质量的数字数据、VoIP 呼叫、IM 消息、A/V 对话、会议、应用程序共享和文件传输的使用情况信息，以及失败呼叫的呼叫错误和故障排除信息。</span><span class="sxs-lookup"><span data-stu-id="637ce-151">**Monitoring**   Monitoring Server enables you to collect numerical data that describes the media quality on your network and endpoints, usage information related to VoIP calls, IM messages, A/V conversations, meetings, application sharing, and file transfers, and call error and troubleshooting information for failed calls.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="637ce-p109">如果要在部署中启用 CAC，则需要在每个中央站点的一个池中启用 CAC。如果要部署语音功能或 A/V 会议，建议使用 CAC。</span><span class="sxs-lookup"><span data-stu-id="637ce-p109">If you would like to enable CAC in your deployment, it is required that you enable CAC in exactly one pool per central site. CAC is recommended if you are deploying voice features or A/V conferencing.</span></span>

    
    </div>
    
    <span data-ttu-id="637ce-p110">下表显示了可用功能（顶部）和为用户提供的功能（左侧）。表中的选择是为组织启用这些功能所需选择的内容。</span><span class="sxs-lookup"><span data-stu-id="637ce-p110">The following table shows the available features (top) and the functions offered to users (left). The selections in the table are what you should select to enable those features for your organization.</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 20%" />
    <col style="width: 20%" />
    <col style="width: 20%" />
    <col style="width: 20%" />
    <col style="width: 20%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th></th>
    <th><span data-ttu-id="637ce-156">会议</span><span class="sxs-lookup"><span data-stu-id="637ce-156">Conferencing</span></span></th>
    <th><span data-ttu-id="637ce-157">电话拨入式会议</span><span class="sxs-lookup"><span data-stu-id="637ce-157">Dial-In Conferencing</span></span></th>
    <th><span data-ttu-id="637ce-158">企业语音</span><span class="sxs-lookup"><span data-stu-id="637ce-158">Enterprise Voice</span></span></th>
    <th><span data-ttu-id="637ce-159">呼叫允许控制</span><span class="sxs-lookup"><span data-stu-id="637ce-159">Call Admission Control</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="637ce-160">即时消息和状态</span><span class="sxs-lookup"><span data-stu-id="637ce-160">Instant messaging and presence</span></span></p></td>
    <td><p><span data-ttu-id="637ce-161">X</span><span class="sxs-lookup"><span data-stu-id="637ce-161">X</span></span></p></td>
    <td></td>
    <td></td>
    <td></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="637ce-162">会议</span><span class="sxs-lookup"><span data-stu-id="637ce-162">Conferencing</span></span></p></td>
    <td><p><span data-ttu-id="637ce-163">X</span><span class="sxs-lookup"><span data-stu-id="637ce-163">X</span></span></p></td>
    <td><p><span data-ttu-id="637ce-164">X</span><span class="sxs-lookup"><span data-stu-id="637ce-164">X</span></span></p></td>
    <td></td>
    <td></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="637ce-165">A/V 会议</span><span class="sxs-lookup"><span data-stu-id="637ce-165">A/V conferencing</span></span></p></td>
    <td><p><span data-ttu-id="637ce-166">X</span><span class="sxs-lookup"><span data-stu-id="637ce-166">X</span></span></p></td>
    <td><p><span data-ttu-id="637ce-167">X</span><span class="sxs-lookup"><span data-stu-id="637ce-167">X</span></span></p></td>
    <td></td>
    <td><p><span data-ttu-id="637ce-168">X</span><span class="sxs-lookup"><span data-stu-id="637ce-168">X</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="637ce-169">企业语音</span><span class="sxs-lookup"><span data-stu-id="637ce-169">Enterprise Voice</span></span></p></td>
    <td></td>
    <td></td>
    <td><p><span data-ttu-id="637ce-170">X</span><span class="sxs-lookup"><span data-stu-id="637ce-170">X</span></span></p></td>
    <td><p><span data-ttu-id="637ce-171">X</span><span class="sxs-lookup"><span data-stu-id="637ce-171">X</span></span></p></td>
    </tr>
    </tbody>
    </table>


5.  <span data-ttu-id="637ce-172">在 " **选择并置服务器角色** " 页上，您可以在前端服务器上并置中介服务器，也可以将其作为独立服务器进行部署。</span><span class="sxs-lookup"><span data-stu-id="637ce-172">On the **Select collocated server roles** page, you can to collocate the Mediation Server on the Front End Server or to deploy it as a stand-alone server.</span></span>
    
    <span data-ttu-id="637ce-173">您可以在前端池上并置中介服务器。</span><span class="sxs-lookup"><span data-stu-id="637ce-173">You can collocate the Mediation Server on the Front End pool.</span></span>
    
      - <span data-ttu-id="637ce-174">如果打算在 Enterprise Edition 前端池上并置中介服务器，请确保选中 "" 复选框。</span><span class="sxs-lookup"><span data-stu-id="637ce-174">If you intend to collocate the Mediation Server on the Enterprise Edition Front End pool, ensure the check box is selected.</span></span> <span data-ttu-id="637ce-175">将在池服务器上部署服务器角色。</span><span class="sxs-lookup"><span data-stu-id="637ce-175">The server role will be deployed on the pool servers.</span></span>
    
      - <span data-ttu-id="637ce-176">如果打算将中介服务器作为独立服务器进行部署，请清除相应的复选框。</span><span class="sxs-lookup"><span data-stu-id="637ce-176">If you intend to deploy the Mediation Server as a stand-alone server, clear the appropriate check box.</span></span> <span data-ttu-id="637ce-177">在完全部署前端服务器之后，您将在单独的部署步骤中部署中介服务器。</span><span class="sxs-lookup"><span data-stu-id="637ce-177">You will deploy Mediation Server in a separate deployment step after you completely deploy the Front End Server.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="637ce-178">我们建议在可能时并置中介服务器。</span><span class="sxs-lookup"><span data-stu-id="637ce-178">We recommend that you collocate the Mediation Server if possible.</span></span> <span data-ttu-id="637ce-179">有关并置或独立中介服务器支持的详细信息，请参阅规划文档中的 <A href="lync-server-2013-components-and-topologies-for-mediation-server.md">Lync server 2013 中的中介服务器组件和拓扑</A> 。</span><span class="sxs-lookup"><span data-stu-id="637ce-179">For details about support for collocated or stand-alone Mediation Servers, see <A href="lync-server-2013-components-and-topologies-for-mediation-server.md">Components and topologies for Mediation Server in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

6.  <span data-ttu-id="637ce-180">" **将服务器角色与此前端池关联** " 页允许您定义服务器角色并将其与前端池相关联。</span><span class="sxs-lookup"><span data-stu-id="637ce-180">The **Associate server roles with this Front End pool** page lets you define and associate server roles with the Front End pool.</span></span> <span data-ttu-id="637ce-181">以下角色可用：</span><span class="sxs-lookup"><span data-stu-id="637ce-181">The following role is available:</span></span>
    
    <span data-ttu-id="637ce-182">**启用边缘池**    定义并关联单个边缘服务器或边缘服务器池。</span><span class="sxs-lookup"><span data-stu-id="637ce-182">**Enable an Edge pool**   Defines and associates a single Edge Server or a pool of Edge Servers.</span></span> <span data-ttu-id="637ce-183">边缘服务器可促进组织内部的用户与组织外部的人员之间的通信和协作，包括联合用户。</span><span class="sxs-lookup"><span data-stu-id="637ce-183">An Edge Server facilitates communication and collaboration between users inside the organization and people outside the organization, including federated users.</span></span>
    
    <span data-ttu-id="637ce-184">您可以使用两种方案来部署和关联服务器角色：</span><span class="sxs-lookup"><span data-stu-id="637ce-184">There are two possible scenarios that you can use to deploy and associate the server roles:</span></span>
    
    <span data-ttu-id="637ce-p116">方案一，为新的安装定义新的拓扑。可以使用两种方法之一完成安装：</span><span class="sxs-lookup"><span data-stu-id="637ce-p116">For scenario one, you are defining a new topology for a new installation. You can approach the installation in one of two ways:</span></span>
    
      - <span data-ttu-id="637ce-187">清除相应复选框，然后继续定义拓扑。</span><span class="sxs-lookup"><span data-stu-id="637ce-187">Leave the check box clear and proceed with defining the topology.</span></span> <span data-ttu-id="637ce-188">在发布、配置并测试了前端和后端服务器角色之后，可以再次运行拓扑生成器以将角色服务器添加到拓扑中。</span><span class="sxs-lookup"><span data-stu-id="637ce-188">After you have published, configured, and tested the Front End and Back End Server roles, you can run Topology Builder again to add the role servers to the topology.</span></span> <span data-ttu-id="637ce-189">通过此策略，您可以测试运行 SQL Server 的前端池和服务器，而不会增加其他角色的复杂性。</span><span class="sxs-lookup"><span data-stu-id="637ce-189">This strategy will enable you to test the Front End pool and the server running SQL Server without additional complications from additional roles.</span></span> <span data-ttu-id="637ce-190">完成初始测试后，可以再次运行拓扑生成器以选择需要部署的角色。</span><span class="sxs-lookup"><span data-stu-id="637ce-190">After you have completed your initial testing, you can run Topology Builder again to select the roles you need to deploy.</span></span>
    
      - <span data-ttu-id="637ce-191">选择需要安装的角色，然后设置硬件以适应所选择的角色。</span><span class="sxs-lookup"><span data-stu-id="637ce-191">Select roles that you need to install, and then set up the hardware to accommodate the selected roles.</span></span>
    
    <span data-ttu-id="637ce-192">对于第二种方案，您有现有的部署和基础结构已准备好使用新角色，或者您需要将现有角色与新的前端服务器相关联：</span><span class="sxs-lookup"><span data-stu-id="637ce-192">For scenario two, you have an existing deployment and your infrastructure is ready for new roles or you need to associate existing roles with a new Front End Server:</span></span>
    
      - <span data-ttu-id="637ce-193">在这种情况下，您将选择要部署或与新的前端服务器关联的角色。</span><span class="sxs-lookup"><span data-stu-id="637ce-193">In this case, you will select the roles that you intend to deploy or associate with the new Front End Server.</span></span> <span data-ttu-id="637ce-194">无论在哪种情况下，都需要定义角色，设置任何所需硬件，然后继续安装。</span><span class="sxs-lookup"><span data-stu-id="637ce-194">In either case, you will proceed with the definition of the roles, set up any needed hardware, and proceed with the installation.</span></span>

7.  <span data-ttu-id="637ce-195">在“定义 SQL 存储”\*\*\*\* 页上，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="637ce-195">On the **Define the SQL store** page, do one of the following:</span></span>
    
      - <span data-ttu-id="637ce-196">若要使用已在拓扑中定义的现有 SQL Server 存储，请选择“SQL 存储”\*\*\*\* 中的一个实例。</span><span class="sxs-lookup"><span data-stu-id="637ce-196">To use an existing SQL Server store that has already been defined in your topology, select an instance from **SQL store**.</span></span>
    
      - <span data-ttu-id="637ce-197">若要定义新的 SQL Server 实例以存储池信息，请单击 "**新建**"，然后在 "**定义新的 sql 存储**" 对话框中指定**SQL Server FQDN**。</span><span class="sxs-lookup"><span data-stu-id="637ce-197">To define a new SQL Server instance to store pool information, click **New** and then specify the **SQL Server FQDN**in the **Define New SQL Store** dialog box.</span></span>
    
      - <span data-ttu-id="637ce-198">要指定 SQL Server 实例的名称，请选择“命名实例”\*\*\*\*，然后指定实例的名称。</span><span class="sxs-lookup"><span data-stu-id="637ce-198">To specify the name of a SQL Server instance, select **Named Instance**, and then specify the name of the instance.</span></span>
    
      - <span data-ttu-id="637ce-199">要使用默认实例，请单击“默认实例”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="637ce-199">To use the default instance, click **Default instance**.</span></span>
    
      - <span data-ttu-id="637ce-200">若要使用 SQL 镜像，请选择“启用 SQL 镜像”\*\*\*\*，选择现有实例或创建一个新实例。</span><span class="sxs-lookup"><span data-stu-id="637ce-200">To use SQL Mirroring, select **Enable SQL mirroring** and select an existing instance or create a new instance.</span></span>

8.  <span data-ttu-id="637ce-201">在“定义文件共享”\*\*\*\* 页上，执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="637ce-201">On the **Define the file share** page, do one of the following:</span></span>
    
      - <span data-ttu-id="637ce-202">要使用已经在拓扑中定义的文件共享，请选择“使用先前定义的文件共享”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="637ce-202">To use a file share that has already been defined in your topology, select **Use a previously defined file share**.</span></span>
    
      - <span data-ttu-id="637ce-203">要定义新文件共享，请选择“定义新的文件共享”\*\*\*\*，在“文件服务器 FQDN”\*\*\*\* 框中，输入要放置文件共享的现有文件服务器的 FQDN，然后在“文件共享”\*\*\*\* 框中输入文件共享的名称。</span><span class="sxs-lookup"><span data-stu-id="637ce-203">To define a new file share, select **Define a new file share**, in the **File Server FQDN** box, enter the FQDN of the existing file server where the file share is to reside, and then enter a name for the file share in the **File Share** box.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="637ce-204">Lync Server 2013 的文件共享不能位于前端服务器上。</span><span class="sxs-lookup"><span data-stu-id="637ce-204">The file share for Lync Server 2013 cannot be located on the Front End Server.</span></span> <span data-ttu-id="637ce-205">请注意，在此示例中，文件共享位于基于 SQL Server 的后端服务器上。</span><span class="sxs-lookup"><span data-stu-id="637ce-205">Note that in this example, the file share has been located on the SQL Server-based Back End Server.</span></span> <span data-ttu-id="637ce-206">根据组织要求，这可能不是最佳位置，文件服务器可能是更好的选择。</span><span class="sxs-lookup"><span data-stu-id="637ce-206">This might not be an optimal location for your organization’s requirements, and a file server might be a better choice.</span></span> <span data-ttu-id="637ce-207">可以在尚未创建文件共享的情况下定义文件共享。</span><span class="sxs-lookup"><span data-stu-id="637ce-207">You can define the file share without the file share having been created.</span></span> <span data-ttu-id="637ce-208">在发布拓扑之前，您将需要在定义的位置创建文件共享。</span><span class="sxs-lookup"><span data-stu-id="637ce-208">You will need to create the file share in the location you define before you publish the topology.</span></span>

    
    </div>

9.  <span data-ttu-id="637ce-209">在“指定 Web 服务 URL”\*\*\*\* 页上，执行以下一项或两项操作：</span><span class="sxs-lookup"><span data-stu-id="637ce-209">On the **Specify the Web Services URL** page, do one or both of the following:</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="637ce-210">基 URL 指的是 URL 的 Web 服务标识减去 https://。</span><span class="sxs-lookup"><span data-stu-id="637ce-210">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="637ce-211">例如，如果池的 Web 服务的完整 URL 为 https://pool01.contoso.net ，则基 url 为 pool01.contoso.net。</span><span class="sxs-lookup"><span data-stu-id="637ce-211">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>

    
    </div>
    
    <div>
    

    > [!WARNING]
    > <span data-ttu-id="637ce-212">如果您有多个前端池或前端服务器，则外部 Web 服务 FQDN 必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="637ce-212">If you have more than one Front End pool or Front End Server, the external Web services FQDN must be unique.</span></span> <span data-ttu-id="637ce-213">例如，如果将前端服务器的外部 Web 服务 FQDN 定义为 <STRONG>pool01.contoso.com</STRONG>，则不能将 <STRONG>pool01.contoso.com</STRONG> 用于另一个前端池或前端服务器。</span><span class="sxs-lookup"><span data-stu-id="637ce-213">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span>

    
    </div>
    
    1.  <span data-ttu-id="637ce-214">如果要配置 DNS 负载平衡，请选中 " **覆盖内部 Web 服务池 FQDN** " 复选框，输入内部基本 url (它必须不同于池 FQDN，例如内部 \<your base URL\> **基 url**中的内部) 。</span><span class="sxs-lookup"><span data-stu-id="637ce-214">If you are configuring DNS load balancing, select the **Override internal Web Services pool FQDN** check box, enter the internal base URL (which must be different from the pool FQDN and could be, for example, internal-\<your base URL\>) in **Internal Base URL**.</span></span>
        
        <div>
        

        > [!WARNING]
        > <span data-ttu-id="637ce-215">如果决定使用自定义的 FQDN 覆盖内部 web 服务，则每个 FQDN 必须与任何其他前端池、控制器或控制器池都是唯一的。</span><span class="sxs-lookup"><span data-stu-id="637ce-215">If you decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span> <span data-ttu-id="637ce-216">定义 Url 或完全限定的域名时，<STRONG>仅使用标准字符</STRONG> (包括 A – z、A – z、0–9和连字符) 。</span><span class="sxs-lookup"><span data-stu-id="637ce-216"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when defining URLs or fully qualified domain names.</span></span> <span data-ttu-id="637ce-217">不要使用 Unicode 字符或下划线。</span><span class="sxs-lookup"><span data-stu-id="637ce-217">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="637ce-218">外部 DNS 和公共 Ca 通常不支持 URL 或 FQDN 中的非标准字符，即，在必须将 URL 或 FQDN 分配给证书) 中的使用者名称或使用者备用名称时 (。</span><span class="sxs-lookup"><span data-stu-id="637ce-218">Nonstandard characters in a URL or FQDN are often not supported by external DNS and public CAs (that is, when the URL or FQDN must be assigned to the subject name or subject alternative name in the certificate).</span></span>

        
        </div>
    
    2.  <span data-ttu-id="637ce-219">（可选）在“外部基 URL”\*\*\*\* 中输入外部基 URL。</span><span class="sxs-lookup"><span data-stu-id="637ce-219">Optionally enter the external base URL in **External Base URL**.</span></span> <span data-ttu-id="637ce-220">您可以输入外部基 URL 以将其与内部域命名区分开来。</span><span class="sxs-lookup"><span data-stu-id="637ce-220">You would enter the external base URL to differentiate it from your internal domain naming.</span></span> <span data-ttu-id="637ce-221">例如，内部域是 contoso.net，但外部域名是 contoso.com。</span><span class="sxs-lookup"><span data-stu-id="637ce-221">For example, your internal domain is contoso.net, but your external domain name is contoso.com.</span></span> <span data-ttu-id="637ce-222">则可以使用 contoso.com 域名来定义 URL。</span><span class="sxs-lookup"><span data-stu-id="637ce-222">You would define the URL using the contoso.com domain name.</span></span> <span data-ttu-id="637ce-223">如果是反向代理，这也很重要。</span><span class="sxs-lookup"><span data-stu-id="637ce-223">This is also important in the case of a reverse proxy.</span></span> <span data-ttu-id="637ce-224">外部基 URL 域名应该与反向代理的 FQDN 域名相同。</span><span class="sxs-lookup"><span data-stu-id="637ce-224">The external base URL domain name would be the same as the domain name of the FQDN of the reverse proxy.</span></span> <span data-ttu-id="637ce-225">即时消息和状态确实需要对前端池的 HTTP 访问。</span><span class="sxs-lookup"><span data-stu-id="637ce-225">Instant messaging and presence does require HTTP access to the Front End pool.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="637ce-226">要使用 DNS 负载平衡，必须创建相应的 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="637ce-226">To use DNS load balancing, you must create the appropriate DNS records.</span></span> <span data-ttu-id="637ce-227">有关详细信息，请参阅 <A href="lync-server-2013-configure-dns-for-load-balancing.md">在 Lync Server 2013 中为负载平衡配置 DNS</A>。</span><span class="sxs-lookup"><span data-stu-id="637ce-227">For details, see <A href="lync-server-2013-configure-dns-for-load-balancing.md">Configure DNS for load balancing in Lync Server 2013</A>.</span></span>

    
    </div>

10. <span data-ttu-id="637ce-228">如果您在 "**选择功能**" 页上选择了 "**会议**"，请在 "**选择 office web apps server** " 页上选择 "**关联池与 Office web Apps 服务器**"，然后单击 "**新建** (或从下拉列表中选择现有的 Office Web Apps Server) 。</span><span class="sxs-lookup"><span data-stu-id="637ce-228">If you selected **Conferencing** on the **Select Features** page, on the **Select an Office Web Apps Server** page select **Associate pool with an Office Web Apps Server** and then click **New** (or select an existing Office Web Apps Server from the drop-down list).</span></span>

11. <span data-ttu-id="637ce-229">在“定义新的 Office Web Apps 服务器”\*\*\*\* 对话框的“Office Web Apps 服务器 FQDN”\*\*\*\* 框中，键入您的 Office Web Apps 服务器计算机的完全限定域名 (FQDN)；执行此操作时，您的 Office Web Apps 服务器搜索 URL 应自动输入到“Office Web Apps 服务器搜索 URL”\*\*\*\* 框中。</span><span class="sxs-lookup"><span data-stu-id="637ce-229">In the **Define New Office Web Apps Server** dialog box, type the fully qualified domain name (FQDN) of your Office Web Apps Server computer in the **Office Web Apps Server FQDN** box; when you do this, your Office Web Apps Server discovery URL should automatically be entered into the **Office Web Apps Server discovery URL** box.</span></span>
    
    <span data-ttu-id="637ce-230">如果 Office Web Apps Server 安装在本地，并且在与 Lync Server 2013 相同的网络区域中，则会在 \*\*外部网络中部署选项 "Office Web Apps 服务器" (即不应选择 "外围/Internet) \*\* 。</span><span class="sxs-lookup"><span data-stu-id="637ce-230">If the Office Web Apps Server is installed on-premises and in the same network zone as Lync Server 2013 then the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)** should not be selected.</span></span>
    
    <span data-ttu-id="637ce-231">如果 Office Web Apps 服务器部署在内部防火墙之外，则请选择选项“在外部网络(即，外围/Internet)中部署 Office Web Apps 服务器”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="637ce-231">If the Office Web Apps Server is deployed outside your internal firewall, then select the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="637ce-232">有关详细信息，请参阅 <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">配置与 Office Web Apps server 和 Lync Server 2013 的集成</A>。</span><span class="sxs-lookup"><span data-stu-id="637ce-232">For details, see <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Configuring integration with Office Web Apps Server and Lync Server 2013</A>.</span></span>

    
    </div>

12. <span data-ttu-id="637ce-233">在“定义存档 SQL 存储”\*\*\*\* 页上，选择一个现有实例或 SQL Server，或定义新实例来存储与存档数据关联的数据。</span><span class="sxs-lookup"><span data-stu-id="637ce-233">On the **Define the Archiving SQL store** page, select an existing instance or SQL Server, or define a new instance to store the data associated with archiving data.</span></span>

13. <span data-ttu-id="637ce-234">在“定义监控 SQL 存储”\*\*\*\* 页上，选择一个现有实例或 SQL Server，或定义新实例来存储与监控数据关联的数据。</span><span class="sxs-lookup"><span data-stu-id="637ce-234">On the **Define the Monitoring SQL store** page, select an existing instance or SQL Server, or define a new instance to store the data associated with monitoring data.</span></span>

14. <span data-ttu-id="637ce-235">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="637ce-235">Click **Next**.</span></span> <span data-ttu-id="637ce-236">如果在 " **将服务器角色与此前端池关联** " 页上定义了其他角色服务器，则将打开 "单独角色配置向导" 页，以允许您配置服务器角色。</span><span class="sxs-lookup"><span data-stu-id="637ce-236">If you defined other role servers on the **Associate server roles with this Front End pool** page, separate role configuration wizard pages will open to let you configure the server roles.</span></span> <span data-ttu-id="637ce-237">有关详细信息，请参阅下文：</span><span class="sxs-lookup"><span data-stu-id="637ce-237">For details, see the following:</span></span>
    
    [<span data-ttu-id="637ce-238">在 Lync Server 2013 中部署外部用户访问</span><span class="sxs-lookup"><span data-stu-id="637ce-238">Deploying external user access in Lync Server 2013</span></span>](lync-server-2013-deploying-external-user-access.md)

15. <span data-ttu-id="637ce-239">如果未选择要配置和部署的其他服务器角色，或者已经完成其他角色服务器的配置，请单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="637ce-239">If you did not select additional server roles to configure and deploy, or when you have finished the configuration of the additional role servers, click **Finish**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

