---
title: Lync Server 2013：验证 Office Web Apps 服务器的配置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating the configuration of Office Web Apps Server
ms:assetid: f6e8ecbf-305d-4a13-92d0-b61dbd82b0ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205393(v=OCS.15)
ms:contentKeyID: 48185859
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 541929233eff5e401b3998aa84e463e2640378c0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763566"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-the-configuration-of-office-web-apps-server-in-lync-server-2013"></a><span data-ttu-id="0ee7a-102">在 Lync Server 2013 中验证 Office Web Apps 服务器的配置</span><span class="sxs-lookup"><span data-stu-id="0ee7a-102">Validating the configuration of Office Web Apps Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0ee7a-103">_**主题上次修改时间：** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="0ee7a-103">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="0ee7a-104">在将 Office Web Apps 服务器添加到拓扑后，在该拓扑发布后，你应该会在 Lync Server 事件日志中看到两个新的事件日志事件。</span><span class="sxs-lookup"><span data-stu-id="0ee7a-104">After Office Web Apps Server has been added to the topology, and after that topology has been published, you should see two new event log events in the Lync Server event log.</span></span> <span data-ttu-id="0ee7a-105">首先，应该添加 LS 数据 MCU 事件（事件 ID 41034）；此事件将报告已发现 Office Web Apps Server：</span><span class="sxs-lookup"><span data-stu-id="0ee7a-105">First, an LS Data MCU event (event ID 41034) should be added; this event will report that the Office Web Apps Server has been discovered:</span></span>

<span data-ttu-id="0ee7a-106">**已发现 Web 会议服务器 Office Web Apps Server，启用了 PowerPoint 内容。**</span><span class="sxs-lookup"><span data-stu-id="0ee7a-106">**Web Conferencing Server Office Web Apps Server is discovered, PowerPoint content is enabled.**</span></span>

<span data-ttu-id="0ee7a-p102">例如，除了应该查看报告回 Office Web Apps Server URL 的另一个 LS Data MCU 事件（事件 ID 41032），还应该查看类似以下内容：</span><span class="sxs-lookup"><span data-stu-id="0ee7a-p102">In addition to that you should see another LS Data MCU event (event ID 41032) that reports back Office Web Apps Server URLs. For example, you should see something similar to this:</span></span>

<span data-ttu-id="0ee7a-109">**已成功发现 Web 会议服务器 Office Web Apps Server。**</span><span class="sxs-lookup"><span data-stu-id="0ee7a-109">**Web Conferencing Server Office Web Apps Server discovery has succeeded.**</span></span>

<span data-ttu-id="0ee7a-110">**Office Web Apps 服务器内部演示者页面：https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed=**</span><span class="sxs-lookup"><span data-stu-id="0ee7a-110">**Office Web Apps Server internal presenter page: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed=**</span></span>

<span data-ttu-id="0ee7a-111">**Office Web Apps 服务器内部与会者页面：https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&=**</span><span class="sxs-lookup"><span data-stu-id="0ee7a-111">**Office Web Apps Server internal attendee page: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&=**</span></span>

<span data-ttu-id="0ee7a-112">**Office Web Apps 服务器外部演示者页面：https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed**</span><span class="sxs-lookup"><span data-stu-id="0ee7a-112">**Office Web Apps Server external presenter page: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed**</span></span>

<span data-ttu-id="0ee7a-113">**Office Web Apps 服务器内部与会者页面：https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&**</span><span class="sxs-lookup"><span data-stu-id="0ee7a-113">**Office Web Apps Server internal attendee page: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&**</span></span>

<span data-ttu-id="0ee7a-114">如果看到的 LS 数据 MCU 事件的事件 ID 为41033，表示 Office Web Apps 服务器发现失败。</span><span class="sxs-lookup"><span data-stu-id="0ee7a-114">If you see an LS Data MCU event with the event ID of 41033 that means that Office Web Apps Server discovery has failed.</span></span> <span data-ttu-id="0ee7a-115">在这种情况下，Microsoft Lync Server 2013 将根据需要尝试多次，以发现新配置的 Office Web Apps 服务器。</span><span class="sxs-lookup"><span data-stu-id="0ee7a-115">In that case, Microsoft Lync Server 2013 will try as many times as needed to discover the newly-configured Office Web Apps Server.</span></span> <span data-ttu-id="0ee7a-116">如果发现过程重复失败，则应从拓扑文档中删除 Office Web Apps 服务器，发布更新后的拓扑，然后尝试在连接问题解决后将 Office Web App 服务器重新添加到拓扑。</span><span class="sxs-lookup"><span data-stu-id="0ee7a-116">If the discovery process fails repeatedly you should remove Office Web Apps Server from your topology document, publish the updated topology, and then try adding Office Web Apps Server back to the topology after the connectivity issues have been resolved.</span></span>

<span data-ttu-id="0ee7a-117">如果 Office Web Apps 服务器似乎配置正确且已被发现过程识别，则可以通过在一对 Microsoft Lync 2013 客户端之间共享 PowerPoint 演示文稿来验证 Office Web Apps 服务器是否按预期工作。</span><span class="sxs-lookup"><span data-stu-id="0ee7a-117">If Office Web Apps Server appears to be configured correctly and has been recognized by the discovery process you can verify that Office Web Apps Server is working as expected by sharing a PowerPoint presentation between a pair of Microsoft Lync 2013 clients.</span></span> <span data-ttu-id="0ee7a-118">如果用户 A 可以加载和显示 PowerPoint 演示文稿，并且如果用户 B 可以加入会议并查看该演示文稿，则 Office Web Apps 服务器正在工作。</span><span class="sxs-lookup"><span data-stu-id="0ee7a-118">If User A can load and display the PowerPoint presentation and if User B can then join the meeting and see that presentation then Office Web Apps Server is working.</span></span>

<span data-ttu-id="0ee7a-119">即使 Office Web Apps 服务器显示正确配置，您也可能会收到错误消息 "当你尝试共享 PowerPoint 演示文稿时，由于服务器连接问题，某些共享功能不可用"。</span><span class="sxs-lookup"><span data-stu-id="0ee7a-119">Even if Office Web Apps Server appears to be configured correctly, you could potentially receive the error message “Some sharing features are unavailable due to server connectivity issues” when you try sharing a PowerPoint presentation.</span></span> <span data-ttu-id="0ee7a-120">如果您收到该错误消息，则应重新启动与新的 Office Web Apps 服务器相关联的前端服务器（或服务器）。</span><span class="sxs-lookup"><span data-stu-id="0ee7a-120">If you receive that error message you should restart the Front End server (or servers) associated with the new Office Web Apps Server.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

