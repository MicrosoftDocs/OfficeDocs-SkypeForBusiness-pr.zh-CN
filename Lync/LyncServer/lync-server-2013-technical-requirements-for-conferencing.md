---
title: Lync Server 2013 会议的技术要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for conferencing
ms:assetid: 3c0d89e1-53e6-46d7-bf8c-491260b292ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425889(v=OCS.15)
ms:contentKeyID: 48183923
ms.date: 06/26/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc548446120ae4088d90acb45c258f3f736063d0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006728"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="e5cf1-102">Lync Server 2013 中的会议的技术要求</span><span class="sxs-lookup"><span data-stu-id="e5cf1-102">Technical requirements for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5cf1-103">_**上次修改的主题：** 2014-06-25_</span><span class="sxs-lookup"><span data-stu-id="e5cf1-103">_**Topic Last Modified:** 2014-06-25_</span></span>

<span data-ttu-id="e5cf1-104">对于 Lync Server 2013，电话拨入式会议、A/V 会议、即时消息（IM）会议和 web 会议功能始终在前端服务器上运行。</span><span class="sxs-lookup"><span data-stu-id="e5cf1-104">For Lync Server 2013, dial-in conferencing, A/V conferencing, instant messaging (IM) conferencing and web conferencing capabilities always run on Front End Servers.</span></span>

<span data-ttu-id="e5cf1-105">本节详细介绍这些服务器的软硬件要求，以及支持的并置。</span><span class="sxs-lookup"><span data-stu-id="e5cf1-105">This section details the hardware and software requirements for these servers, along with the supported collocation.</span></span>

<span data-ttu-id="e5cf1-106">电话拨入式会议是包含各种组件的功能。</span><span class="sxs-lookup"><span data-stu-id="e5cf1-106">Dial-in conferencing is a feature that includes a variety of components.</span></span> <span data-ttu-id="e5cf1-107">一些组件是特定于电话拨入式会议的，一些组件是企业语音组件。</span><span class="sxs-lookup"><span data-stu-id="e5cf1-107">Some of the components are specific to dial-in conferencing and some are Enterprise Voice components.</span></span> <span data-ttu-id="e5cf1-108">本节介绍特定于电话拨入式会议的组件的要求。</span><span class="sxs-lookup"><span data-stu-id="e5cf1-108">This section describes the requirements for the components that are specific to dial-in conferencing.</span></span> <span data-ttu-id="e5cf1-109">有关中介服务器和公共交换电话网络（PSTN）网关要求的详细信息，请参阅规划文档中的 "在 lync server 2013 中的[中介服务器组件](lync-server-2013-mediation-server-component.md)和[组件和拓扑](lync-server-2013-components-and-topologies-for-mediation-server.md)中的中介服务器 2013"。</span><span class="sxs-lookup"><span data-stu-id="e5cf1-109">For details about Mediation Server and public switched telephone network (PSTN) gateway requirements, see [Mediation Server component in Lync Server 2013](lync-server-2013-mediation-server-component.md) and [Components and topologies for Mediation Server in Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) in the Planning documentation.</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="e5cf1-110">硬件要求</span><span class="sxs-lookup"><span data-stu-id="e5cf1-110">Hardware Requirements</span></span>

<span data-ttu-id="e5cf1-111">由于 web 会议和 A/V 会议与前端服务器并置，因此服务器的硬件要求与前端服务器的要求相同。</span><span class="sxs-lookup"><span data-stu-id="e5cf1-111">Because web conferencing and A/V conferencing are collocated with the Front End Server, the server hardware requirements are the same as for the Front End Servers.</span></span> <span data-ttu-id="e5cf1-112">有关硬件要求的详细信息，请参阅可支持性文档中的[Lync server 2013 的服务器硬件平台](lync-server-2013-server-hardware-platforms.md)。</span><span class="sxs-lookup"><span data-stu-id="e5cf1-112">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span> <span data-ttu-id="e5cf1-113">电话拨入式会议所需的以下组件也与前端服务器具有相同的硬件要求：</span><span class="sxs-lookup"><span data-stu-id="e5cf1-113">The following components required for dial-in conferencing also have the same hardware requirements as Front End Servers:</span></span>

  - <span data-ttu-id="e5cf1-114">应用程序服务</span><span class="sxs-lookup"><span data-stu-id="e5cf1-114">Application service</span></span>

  - <span data-ttu-id="e5cf1-115">会议助理应用程序</span><span class="sxs-lookup"><span data-stu-id="e5cf1-115">Conferencing Attendant application</span></span>

  - <span data-ttu-id="e5cf1-116">会议通知应用程序</span><span class="sxs-lookup"><span data-stu-id="e5cf1-116">Conferencing Announcement application</span></span>

<span data-ttu-id="e5cf1-117">前端服务器的硬件要求与 Lync Server 2013 中的许多其他服务器角色相同，如下表中所述。</span><span class="sxs-lookup"><span data-stu-id="e5cf1-117">The hardware requirements for Front End Server are the same as for many other server roles in Lync Server 2013 are outlined in the following table.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="e5cf1-118">软件要求</span><span class="sxs-lookup"><span data-stu-id="e5cf1-118">Software Requirements</span></span>

<span data-ttu-id="e5cf1-119">由于 web 会议和 A/V 会议与前端服务器并置，因此服务器软件要求与前端服务器的要求相同。</span><span class="sxs-lookup"><span data-stu-id="e5cf1-119">Because web conferencing and A/V conferencing are collocated with the Front End Server, the server software requirements are the same as for the Front End Servers.</span></span> <span data-ttu-id="e5cf1-120">有关软件要求的详细信息，请参阅可支持性文档中的[Lync server 2013 中的服务器和工具操作系统支持](lync-server-2013-server-and-tools-operating-system-support.md)。</span><span class="sxs-lookup"><span data-stu-id="e5cf1-120">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="e5cf1-121">对于 web 会议，Lync Server 2013 还需要 Office Web Apps 和 Office Web Apps Server （以前称为 WAC Server）来处理 PowerPoint 演示文稿。</span><span class="sxs-lookup"><span data-stu-id="e5cf1-121">For web conferencing, Lync Server 2013 also requires Office Web Apps and the Office Web Apps Server (formerly known as WAC Server) to handle PowerPoint presentations.</span></span> <span data-ttu-id="e5cf1-122">有关详细信息，请参阅[配置与 Office Web Apps server 和 Lync Server 2013 的集成](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="e5cf1-122">For details, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

<span data-ttu-id="e5cf1-123">对于电话拨入式会议，应用程序服务、会议助理应用程序和会议通知应用程序与前端服务器具有相同的操作系统要求。</span><span class="sxs-lookup"><span data-stu-id="e5cf1-123">For dial-in conferencing, Application service, Conferencing Attendant application, and Conferencing Announcement application have the same operating system requirements as Front End Servers.</span></span> <span data-ttu-id="e5cf1-124">有关软件要求的详细信息，请参阅可支持性文档中的[Lync server 2013 中的服务器和工具操作系统支持](lync-server-2013-server-and-tools-operating-system-support.md)。</span><span class="sxs-lookup"><span data-stu-id="e5cf1-124">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="e5cf1-125">会议助理应用程序和会议通知应用程序要求在前端服务器上安装 Windows Media Format Runtime。</span><span class="sxs-lookup"><span data-stu-id="e5cf1-125">Conferencing Attendant application and Conferencing Announcement application require that Windows Media Format Runtime is installed on Front End Servers.</span></span> <span data-ttu-id="e5cf1-126">Windows Media Format Runtime 是播放用于保持音乐、录制的名称和提示的 Windows Media 音频 (WMA) 文件所必需的。</span><span class="sxs-lookup"><span data-stu-id="e5cf1-126">The Windows Media Format Runtime is required to play Windows Media audio (WMA) files that are used for music on hold, recorded names, and prompts.</span></span> <span data-ttu-id="e5cf1-127">除了 Windows Server 2012 和 Windows Server 2012 R2 之外，在运行安装程序时，Windows Media Format 运行时将自动安装为 Windows 桌面体验的一部分，但您可能需要重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="e5cf1-127">Except for Windows Server 2012 and Windows Server 2012 R2, the Windows Media Format Runtime is installed automatically as part of the Windows Desktop Experience when you run Setup, but you might need to restart the computer.</span></span> <span data-ttu-id="e5cf1-128">因此，建议您在运行安装程序之前，作为 Windows 桌面体验的一部分安装，它包含 Windows Media Format Runtime。</span><span class="sxs-lookup"><span data-stu-id="e5cf1-128">Therefore, we recommend that you install as part of the Windows Desktop Experience, which includes Windows Media Format Runtime before you run Setup.</span></span> <span data-ttu-id="e5cf1-129">Windows Server 2012 和 Windows Server 2012 R2 需要 Microsoft Media Foundation。</span><span class="sxs-lookup"><span data-stu-id="e5cf1-129">Windows Server 2012 and Windows Server 2012 R2 requires Microsoft Media Foundation.</span></span>

</div>

<div>

## <a name="port-requirements-for-dial-in-conferencing"></a><span data-ttu-id="e5cf1-130">电话拨入式会议的端口要求</span><span class="sxs-lookup"><span data-stu-id="e5cf1-130">Port Requirements for dial-in conferencing</span></span>

<span data-ttu-id="e5cf1-p107">下表介绍了电话拨入式会议所使用的端口。如果使用负载平衡器，请确保已为将在池中运行的应用程序所使用的端口配置负载平衡器。</span><span class="sxs-lookup"><span data-stu-id="e5cf1-p107">The following table describes the ports that are used by dial-in conferencing. If you use a load balancer, ensure that the load balancer is configured for the ports used by any applications that will run in the pool.</span></span>

<span data-ttu-id="e5cf1-133">这些端口是默认设置，您可以使用 **Set-CsApplicationServer** cmdlet 更改。</span><span class="sxs-lookup"><span data-stu-id="e5cf1-133">These ports are default settings that you can change by using the **Set-CsApplicationServer** cmdlet.</span></span> <span data-ttu-id="e5cf1-134">有关此 cmdlet 的详细信息，请参阅 Lync Server 命令行管理程序文档。</span><span class="sxs-lookup"><span data-stu-id="e5cf1-134">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e5cf1-135">池中同一应用程序的所有实例都采用同一个 SIP 侦听端口。</span><span class="sxs-lookup"><span data-stu-id="e5cf1-135">All instances of the same application in a pool use the same SIP listening port.</span></span>



</div>

### <a name="ports-used-by-dial-in-conferencing"></a><span data-ttu-id="e5cf1-136">电话拨入式会议所使用的端口</span><span class="sxs-lookup"><span data-stu-id="e5cf1-136">Ports used by dial-in conferencing</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e5cf1-137">端口号</span><span class="sxs-lookup"><span data-stu-id="e5cf1-137">Port number</span></span></th>
<th><span data-ttu-id="e5cf1-138">说明</span><span class="sxs-lookup"><span data-stu-id="e5cf1-138">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e5cf1-139">5072</span><span class="sxs-lookup"><span data-stu-id="e5cf1-139">5072</span></span></p></td>
<td><p><span data-ttu-id="e5cf1-140">由会议助理应用程序用于 SIP 侦听请求</span><span class="sxs-lookup"><span data-stu-id="e5cf1-140">Used by Conferencing Attendant application for SIP listening requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5cf1-141">5073</span><span class="sxs-lookup"><span data-stu-id="e5cf1-141">5073</span></span></p></td>
<td><p><span data-ttu-id="e5cf1-142">由会议通知应用程序用于 SIP 侦听请求</span><span class="sxs-lookup"><span data-stu-id="e5cf1-142">Used by Conferencing Announcement application for SIP listening requests</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supported-clients-for-dial-in-conferencing"></a><span data-ttu-id="e5cf1-143">电话拨入式会议支持的客户端</span><span class="sxs-lookup"><span data-stu-id="e5cf1-143">Supported Clients for Dial-In Conferencing</span></span>

<span data-ttu-id="e5cf1-144">您可以使用以下客户端安排支持拨入访问的内部会议：</span><span class="sxs-lookup"><span data-stu-id="e5cf1-144">You can use the following client to schedule on-premises conferences that support dial-in access:</span></span>

  - <span data-ttu-id="e5cf1-145">Lync 2013 的联机会议外接程序（安装 Lync 2013 或与会者时自动安装）</span><span class="sxs-lookup"><span data-stu-id="e5cf1-145">Online Meeting Add-in for Lync 2013 (installed automatically when you install Lync 2013 or Attendee)</span></span>

</div>

<div>

## <a name="dial-in-conferencing-settings-page-requirements"></a><span data-ttu-id="e5cf1-146">电话拨入式会议设置页面要求</span><span class="sxs-lookup"><span data-stu-id="e5cf1-146">Dial-in Conferencing Settings page Requirements</span></span>

<span data-ttu-id="e5cf1-147">"电话拨入式会议设置" 页支持下表中所述的操作系统和 web 浏览器的组合。</span><span class="sxs-lookup"><span data-stu-id="e5cf1-147">The Dial-in Conferencing Settings page supports the combinations of operating systems and web browsers described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e5cf1-148">但支持 32 位和 64 位版本的操作系统。</span><span class="sxs-lookup"><span data-stu-id="e5cf1-148">32-bit and 64-bit versions of the operating systems are supported.</span></span>



</div>

### <a name="supported-operating-systems-and-web-browsers"></a><span data-ttu-id="e5cf1-149">支持的操作系统和 Web 浏览器</span><span class="sxs-lookup"><span data-stu-id="e5cf1-149">Supported Operating Systems and Web Browsers</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e5cf1-150">操作系统</span><span class="sxs-lookup"><span data-stu-id="e5cf1-150">Operating system</span></span></th>
<th><span data-ttu-id="e5cf1-151">Web 浏览器</span><span class="sxs-lookup"><span data-stu-id="e5cf1-151">Web browser</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e5cf1-152">Windows 7</span><span class="sxs-lookup"><span data-stu-id="e5cf1-152">Windows 7</span></span></p></td>
<td><p><span data-ttu-id="e5cf1-153">Internet Explorer 9</span><span class="sxs-lookup"><span data-stu-id="e5cf1-153">Internet Explorer 9</span></span></p>
<p><span data-ttu-id="e5cf1-154">Internet Explorer 8</span><span class="sxs-lookup"><span data-stu-id="e5cf1-154">Internet Explorer 8</span></span></p>
<p><span data-ttu-id="e5cf1-155">Firefox</span><span class="sxs-lookup"><span data-stu-id="e5cf1-155">Firefox</span></span></p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td> </td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5cf1-156">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="e5cf1-156">Windows Server 2008 R2</span></span></p></td>
<td><p><span data-ttu-id="e5cf1-157">Internet Explorer 9</span><span class="sxs-lookup"><span data-stu-id="e5cf1-157">Internet Explorer 9</span></span></p>
<p><span data-ttu-id="e5cf1-158">Internet Explorer 8</span><span class="sxs-lookup"><span data-stu-id="e5cf1-158">Internet Explorer 8</span></span></p>
<p><span data-ttu-id="e5cf1-159">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="e5cf1-159">Internet Explorer 7</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5cf1-160">Mac OS</span><span class="sxs-lookup"><span data-stu-id="e5cf1-160">Mac OS</span></span></p></td>
<td><p><span data-ttu-id="e5cf1-161">Firefox</span><span class="sxs-lookup"><span data-stu-id="e5cf1-161">Firefox</span></span></p>
<p><span data-ttu-id="e5cf1-162">Safari</span><span class="sxs-lookup"><span data-stu-id="e5cf1-162">Safari</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="audio-file-requirements-for-dial-in-conferencing"></a><span data-ttu-id="e5cf1-163">电话拨入式会议的音频文件要求</span><span class="sxs-lookup"><span data-stu-id="e5cf1-163">Audio File Requirements for dial-in conferencing</span></span>

<span data-ttu-id="e5cf1-164">Lync Server 2013 不支持为电话拨入式会议自定义语音提示和音乐。</span><span class="sxs-lookup"><span data-stu-id="e5cf1-164">Lync Server 2013 does not support customization of voice prompts and music for dial-in conferencing.</span></span> <span data-ttu-id="e5cf1-165">但是，如果您需要更改默认音频文件，则需要更改默认的音频文件，请参阅 Microsoft 知识库文章961177，[如何在 Microsoft Office 通信服务器 2007 R2 中为电话拨入式音频会议自定义语音提示或音乐文件](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=961177)。</span><span class="sxs-lookup"><span data-stu-id="e5cf1-165">However, if you have a strong business need that requires you to change the default audio files, see Microsoft Knowledge Base article 961177, [How to customize voice prompts or music files for dial-in audio conferencing in Microsoft Office Communications Server 2007 R2](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=961177).</span></span>

<span data-ttu-id="e5cf1-166">您还可以使用[Microsoft Lync Server 会议助理自定义语音提示](http://go.microsoft.com/fwlink/p/?linkid=396880)管理实用程序，使管理员能够替换在电话呼叫者加入具有自定义提示的 Lync 会议时使用的默认语音提示，以提供不同的会议输入体验。</span><span class="sxs-lookup"><span data-stu-id="e5cf1-166">You can also use the [Microsoft Lync Server Conferencing Attendant Custom Voice Prompts](http://go.microsoft.com/fwlink/p/?linkid=396880) management utility, which enables administrators to replace the default voice prompts used when a phone caller joins a Lync meeting with custom prompts to provide a different meeting entry experience.</span></span> <span data-ttu-id="e5cf1-167">自定义语音提示可以安装在运行 Lync Server 2010 或 Lync Server 2013 的服务器上（企业版或标准版）。</span><span class="sxs-lookup"><span data-stu-id="e5cf1-167">The custom voice prompts can be installed on a server that is running Lync Server 2010 or Lync Server 2013, either Enterprise or Standard Edition.</span></span>

<span data-ttu-id="e5cf1-168">会议助理应用程序和会议通知应用程序对处于保留状态的音乐、录制的名称和音频提示文件有以下要求：</span><span class="sxs-lookup"><span data-stu-id="e5cf1-168">Conferencing Attendant application and Conferencing Announcement application have the following requirements for music on hold, recorded name, and audio prompt files:</span></span>

  - <span data-ttu-id="e5cf1-169">Windows Media 音频 (WMA) 文件格式</span><span class="sxs-lookup"><span data-stu-id="e5cf1-169">Windows Media Audio (WMA) file format</span></span>

  - <span data-ttu-id="e5cf1-170">16 位单声道</span><span class="sxs-lookup"><span data-stu-id="e5cf1-170">16-bit mono</span></span>

  - <span data-ttu-id="e5cf1-171">48 kbps 2-pass CBR（恒定比特率）</span><span class="sxs-lookup"><span data-stu-id="e5cf1-171">48 kbps 2-pass CBR (constant bit rate)</span></span>

  - <span data-ttu-id="e5cf1-172">语音级别 - 24DB</span><span class="sxs-lookup"><span data-stu-id="e5cf1-172">Speech level at -24DB</span></span>

</div>

<div>

## <a name="user-requirements-for-dial-in-conferencing"></a><span data-ttu-id="e5cf1-173">电话拨入式会议的用户要求</span><span class="sxs-lookup"><span data-stu-id="e5cf1-173">User Requirements for Dial-In Conferencing</span></span>

<span data-ttu-id="e5cf1-174">电话拨入式会议用户必须为其帐户分配唯一的电话号码或分机。</span><span class="sxs-lookup"><span data-stu-id="e5cf1-174">Dial-in conferencing users must have a unique phone number or extension assigned to their account.</span></span> <span data-ttu-id="e5cf1-175">该要求支持在电话拨入式会议期间进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="e5cf1-175">This requirement supports authentication during dial-in conferencing.</span></span> <span data-ttu-id="e5cf1-176">企业用户（即，在组织内拥有 Active Directory 域服务凭据和 Lync Server 帐户的用户）输入其电话号码（或分机号码）和个人标识号（PIN），以在会议中拨入会议经过身份验证的用户。</span><span class="sxs-lookup"><span data-stu-id="e5cf1-176">Enterprise users (that is, users who have Active Directory Domain Services credentials and Lync Server accounts within your organization) enter their phone number (or extension) and a personal identification number (PIN) to dial in to conferences as an authenticated user.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

