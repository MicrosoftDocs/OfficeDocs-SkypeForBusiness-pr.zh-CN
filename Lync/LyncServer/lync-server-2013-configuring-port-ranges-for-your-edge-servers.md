---
title: Lync Server 2013：为边缘服务器配置端口范围
description: Lync Server 2013：为边缘服务器配置端口范围。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring port ranges for your Edge Servers
ms:assetid: 6f0ae442-6624-4e3f-849a-5b9e387fb8cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204996(v=OCS.15)
ms:contentKeyID: 48184469
ms.date: 07/24/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c085a5dbc32bbf56842984eae2ef8896ab895c65
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548248"
---
# <a name="configuring-port-ranges-for-your-edge-servers-in-lync-server-2013"></a><span data-ttu-id="aff07-103">在 Lync Server 2013 中为边缘服务器配置端口范围</span><span class="sxs-lookup"><span data-stu-id="aff07-103">Configuring port ranges for your Edge Servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aff07-104">_**上次修改的主题：** 2015-07-24_</span><span class="sxs-lookup"><span data-stu-id="aff07-104">_**Topic Last Modified:** 2015-07-24_</span></span>

<span data-ttu-id="aff07-105">借助边缘服务器，您无需为音频、视频和应用程序共享配置单独的端口范围；同样地，用于边缘服务器的端口范围无需与用于会议、应用程序和中介服务器的端口范围相匹配。</span><span class="sxs-lookup"><span data-stu-id="aff07-105">With Edge servers you do not have to configure separate port ranges for audio, video, and application sharing; likewise, the port ranges used for Edge servers do not have to match the port ranges used with your Conferencing, Application, and Mediation servers.</span></span> <span data-ttu-id="aff07-106">在继续使用我们的示例之前，请务必强调此选项存在时，我们建议您不要更改端口范围，因为如果移出50000端口范围，这可能会对某些方案产生不利影响。</span><span class="sxs-lookup"><span data-stu-id="aff07-106">Before we proceed with our example, it's important to stress that while this option exists, we do recommend you not change the port ranges, as this may adversely affect some scenarios if you move out of the 50000 port range.</span></span>

<span data-ttu-id="aff07-107">例如，假定您已将会议、应用程序和中介服务器配置为使用这些端口范围：</span><span class="sxs-lookup"><span data-stu-id="aff07-107">For example, suppose you have configured your Conferencing, Application, and Mediation servers to use these port ranges:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aff07-108">数据包类型</span><span class="sxs-lookup"><span data-stu-id="aff07-108">Packet Type</span></span></th>
<th><span data-ttu-id="aff07-109">起始端口</span><span class="sxs-lookup"><span data-stu-id="aff07-109">Starting Port</span></span></th>
<th><span data-ttu-id="aff07-110">预留的端口数</span><span class="sxs-lookup"><span data-stu-id="aff07-110">Number of Ports Reserved</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aff07-111">应用程序共享</span><span class="sxs-lookup"><span data-stu-id="aff07-111">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="aff07-112">40803</span><span class="sxs-lookup"><span data-stu-id="aff07-112">40803</span></span></p></td>
<td><p><span data-ttu-id="aff07-113">8348</span><span class="sxs-lookup"><span data-stu-id="aff07-113">8348</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aff07-114">音频</span><span class="sxs-lookup"><span data-stu-id="aff07-114">Audio</span></span></p></td>
<td><p><span data-ttu-id="aff07-115">49152</span><span class="sxs-lookup"><span data-stu-id="aff07-115">49152</span></span></p></td>
<td><p><span data-ttu-id="aff07-116">8348</span><span class="sxs-lookup"><span data-stu-id="aff07-116">8348</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aff07-117">视频</span><span class="sxs-lookup"><span data-stu-id="aff07-117">Video</span></span></p></td>
<td><p><span data-ttu-id="aff07-118">57500</span><span class="sxs-lookup"><span data-stu-id="aff07-118">57500</span></span></p></td>
<td><p><span data-ttu-id="aff07-119">8034</span><span class="sxs-lookup"><span data-stu-id="aff07-119">8034</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aff07-120"><strong>总计</strong></span><span class="sxs-lookup"><span data-stu-id="aff07-120"><strong>Totals</strong></span></span></p></td>
<td><p>--</p></td>
<td><p><span data-ttu-id="aff07-121">24730</span><span class="sxs-lookup"><span data-stu-id="aff07-121">24730</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="aff07-122">正如您所看到的，音频、视频和应用程序共享的端口范围从端口40803开始，总共包括24732个端口。</span><span class="sxs-lookup"><span data-stu-id="aff07-122">As you can see, your port ranges for audio, video, and application sharing start at port 40803 and encompass a total of 24732 ports.</span></span> <span data-ttu-id="aff07-123">如果您愿意，可以通过从 Lync Server 命令行管理程序中运行与此命令类似的命令，来将一个给定边缘服务器配置为使用这些端口值：</span><span class="sxs-lookup"><span data-stu-id="aff07-123">If you prefer, you can configure a given Edge Server to use these overall port values by running a command similar to this one from within the Lync Server Management Shell:</span></span>

    Set-CsEdgeServer -Identity EdgeServer:atl-edge-001.litwareinc.com -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730

<span data-ttu-id="aff07-124">或者，可使用以下命令同时配置您组织中的所有边缘服务器：</span><span class="sxs-lookup"><span data-stu-id="aff07-124">Or, use the following command to simultaneously configure all the Edge Servers in your organization:</span></span>

    Get-CsService -EdgeServer | ForEach-Object {Set-CsEdgeServer -Identity $_.Identity -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730}

<span data-ttu-id="aff07-125">您可以使用此 Lync Server 命令行管理程序命令验证边缘服务器的当前端口设置：</span><span class="sxs-lookup"><span data-stu-id="aff07-125">You can verify the current port settings for your Edge Servers by using this Lync Server Management Shell command:</span></span>

    Get-CsService -EdgeServer | Select-Object Identity, MediaCommunicationPortStart, MediaCommunicationPortCount

<span data-ttu-id="aff07-126">同样，虽然我们提供了这些选项，但强烈建议您保留它们的端口配置。</span><span class="sxs-lookup"><span data-stu-id="aff07-126">Again, while we do provide these options, we strongly recommend you leave things as they are for the port configuration.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

