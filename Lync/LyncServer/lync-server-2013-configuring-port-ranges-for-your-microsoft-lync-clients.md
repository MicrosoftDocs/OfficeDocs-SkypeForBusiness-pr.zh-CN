---
title: 'Lync Server 2013: 为您的 Microsoft Lync 客户端配置端口范围'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring port ranges for your Microsoft Lync clients
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204760(v=OCS.15)
ms:contentKeyID: 48183694
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03cd4c109760756dd265526bd9d5285fdc9fed30
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837188"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-for-your-microsoft-lync-clients-in-lync-server-2013"></a><span data-ttu-id="3874e-102">在 Lync Server 2013 中为您的 Microsoft Lync 客户端配置端口范围</span><span class="sxs-lookup"><span data-stu-id="3874e-102">Configuring port ranges for your Microsoft Lync clients in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3874e-103">_**主题上次修改时间:** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="3874e-103">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="3874e-104">默认情况下, Lync 客户端应用程序可以使用端口1024和65535之间的任何端口参与通信会话;这是因为不会为客户端自动启用特定端口范围。</span><span class="sxs-lookup"><span data-stu-id="3874e-104">By default, Lync client applications can use any port between ports 1024 and 65535 when involved in a communication session; this is because specific port ranges are not automatically enabled for clients.</span></span> <span data-ttu-id="3874e-105">但是, 为了使用服务质量, 你需要将各种流量类型 (音频、视频、媒体、应用程序共享和文件传输) 重新分配给一系列唯一的端口范围。</span><span class="sxs-lookup"><span data-stu-id="3874e-105">In order to use Quality of Service, however, you will need to reassign the various traffic types (audio, video, media, application sharing, and file transfer) to a series of unique port ranges.</span></span> <span data-ttu-id="3874e-106">可通过使用 CsConferencingConfiguration cmdlet 完成此操作。</span><span class="sxs-lookup"><span data-stu-id="3874e-106">This can be done by using the Set-CsConferencingConfiguration cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3874e-107">最终用户不能自行进行这些更改。</span><span class="sxs-lookup"><span data-stu-id="3874e-107">End users cannot make these changes themselves.</span></span> <span data-ttu-id="3874e-108">仅管理员可以使用 CsConferencingConfiguration cmdlet 进行端口更改。</span><span class="sxs-lookup"><span data-stu-id="3874e-108">Port changes can only be made by administrators using the Set-CsConferencingConfiguration cmdlet.</span></span>



</div>

<span data-ttu-id="3874e-109">通过从 Microsoft Lync Server 2013 命令行管理程序中运行以下命令, 可以确定当前用于通信会话的端口范围:</span><span class="sxs-lookup"><span data-stu-id="3874e-109">You can determine which port ranges are currently used for communication sessions by running the following command from within the Microsoft Lync Server 2013 Management Shell:</span></span>

    Get-CsConferencingConfiguration

<span data-ttu-id="3874e-110">假设你在安装 Lync Server 2013 后未对会议设置进行任何更改, 你应返回包含这些属性值的信息:</span><span class="sxs-lookup"><span data-stu-id="3874e-110">Assuming that you have not made any changes to your conferencing settings since you installed Lync Server 2013, you should get back information that includes these property values:</span></span>

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

<span data-ttu-id="3874e-111">如果仔细查看前面的输出, 您将看到两个重要内容。</span><span class="sxs-lookup"><span data-stu-id="3874e-111">If you look closely at the preceding output, you'll see two things of importance.</span></span> <span data-ttu-id="3874e-112">首先, ClientMediaPortRangeEnabled 属性设置为 False:</span><span class="sxs-lookup"><span data-stu-id="3874e-112">First, the ClientMediaPortRangeEnabled property is set to False:</span></span>

    ClientMediaPortRangeEnabled : False

<span data-ttu-id="3874e-113">这很重要, 因为当此属性设置为 False 时, 当你参与通信会话时, Lync 客户端将使用端口1024和65535之间的任何可用端口;无论任何其他端口设置 (例如, ClientMediaPort 或 ClientVideoPort), 都是如此。</span><span class="sxs-lookup"><span data-stu-id="3874e-113">That's important because, when this property is set to False, Lync clients will use any available port between ports 1024 and 65535 when involved in a communication session; this is true regardless of any other port settings (for example, ClientMediaPort or ClientVideoPort).</span></span> <span data-ttu-id="3874e-114">如果你想要将使用率限制为指定的一组端口 (如果计划实现服务质量, 则需要执行此操作), 然后必须首先启用客户端媒体端口范围。</span><span class="sxs-lookup"><span data-stu-id="3874e-114">If you want to restrict usage to a specified set of ports (and this is something you do want to do if you plan on implementing Quality of Service) then you must first enable client media port ranges.</span></span> <span data-ttu-id="3874e-115">可以使用以下 Windows PowerShell 命令执行此操作:</span><span class="sxs-lookup"><span data-stu-id="3874e-115">That can be done using the following Windows PowerShell command:</span></span>

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

<span data-ttu-id="3874e-116">前面的命令为会议配置设置的全局集合启用了客户端媒体端口范围;但是, 这些设置也可以应用于网站范围和/或服务范围 (仅适用于会议服务器服务)。</span><span class="sxs-lookup"><span data-stu-id="3874e-116">The preceding command enables client media port ranges for the global collection of conferencing configuration settings; however, these settings can also be applied to the site scope and/or the service scope (for the Conferencing Server service only).</span></span> <span data-ttu-id="3874e-117">若要启用特定网站或服务器的客户端媒体端口范围, 请在调用 CsConferencingConfiguration 时指定该网站或服务器的标识:</span><span class="sxs-lookup"><span data-stu-id="3874e-117">To enable client media port ranges for a specific site or server, specify the Identity of that site or server when calling Set-CsConferencingConfiguration:</span></span>

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

<span data-ttu-id="3874e-118">或者, 你可以使用此命令同时为所有会议配置设置启用端口范围:</span><span class="sxs-lookup"><span data-stu-id="3874e-118">Alternatively, you can use this command to simultaneously enable port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

<span data-ttu-id="3874e-119">你将注意到的第二个重要事项是示例输出显示, 默认情况下, 为每种类型的网络流量设置的媒体端口范围是相同的:</span><span class="sxs-lookup"><span data-stu-id="3874e-119">The second thing of importance you will notice is that the sample output shows that, by default, the media port ranges set for each type of network traffic are identical:</span></span>

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

<span data-ttu-id="3874e-120">为了实现 QoS, 这些端口范围中的每一个都必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="3874e-120">In order to implement QoS, each of these port ranges will need to be unique.</span></span> <span data-ttu-id="3874e-121">例如, 你可以配置如下所示的端口范围:</span><span class="sxs-lookup"><span data-stu-id="3874e-121">For example, you might configure the port ranges like this:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3874e-122">客户端流量类型</span><span class="sxs-lookup"><span data-stu-id="3874e-122">Client Traffic Type</span></span></th>
<th><span data-ttu-id="3874e-123">端口启动</span><span class="sxs-lookup"><span data-stu-id="3874e-123">Port Start</span></span></th>
<th><span data-ttu-id="3874e-124">端口范围</span><span class="sxs-lookup"><span data-stu-id="3874e-124">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3874e-125">音频</span><span class="sxs-lookup"><span data-stu-id="3874e-125">Audio</span></span></p></td>
<td><p><span data-ttu-id="3874e-126">50020</span><span class="sxs-lookup"><span data-stu-id="3874e-126">50020</span></span></p></td>
<td><p><span data-ttu-id="3874e-127">名</span><span class="sxs-lookup"><span data-stu-id="3874e-127">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3874e-128">视频</span><span class="sxs-lookup"><span data-stu-id="3874e-128">Video</span></span></p></td>
<td><p><span data-ttu-id="3874e-129">58000</span><span class="sxs-lookup"><span data-stu-id="3874e-129">58000</span></span></p></td>
<td><p><span data-ttu-id="3874e-130">名</span><span class="sxs-lookup"><span data-stu-id="3874e-130">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3874e-131">应用程序共享</span><span class="sxs-lookup"><span data-stu-id="3874e-131">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="3874e-132">42000</span><span class="sxs-lookup"><span data-stu-id="3874e-132">42000</span></span></p></td>
<td><p><span data-ttu-id="3874e-133">名</span><span class="sxs-lookup"><span data-stu-id="3874e-133">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3874e-134">文件传输</span><span class="sxs-lookup"><span data-stu-id="3874e-134">File transfer</span></span></p></td>
<td><p><span data-ttu-id="3874e-135">42020</span><span class="sxs-lookup"><span data-stu-id="3874e-135">42020</span></span></p></td>
<td><p><span data-ttu-id="3874e-136">名</span><span class="sxs-lookup"><span data-stu-id="3874e-136">20</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="3874e-137">在上表中, 客户端端口范围表示为服务器配置的端口范围的子集。</span><span class="sxs-lookup"><span data-stu-id="3874e-137">In the preceding table, client port ranges represent a subset of the port ranges configured for your servers.</span></span> <span data-ttu-id="3874e-138">例如, 在服务器上, 应用程序共享配置为使用端口40803到 49151;在客户端计算机上, 将应用程序共享配置为使用端口42000到42019。</span><span class="sxs-lookup"><span data-stu-id="3874e-138">For example, on the servers, application sharing was configured to use ports 40803 through 49151; on the client computers, application sharing is configured to use ports 42000 through 42019.</span></span> <span data-ttu-id="3874e-139">这样做还主要是为了简化 QoS 的管理: 客户端端口不必表示服务器上使用的端口子集。</span><span class="sxs-lookup"><span data-stu-id="3874e-139">This, too is done primarily to make administration of QoS easier: client ports do not have to represent a subset of the ports used on the server.</span></span> <span data-ttu-id="3874e-140">(例如, 在客户端计算机上, 你可以配置要使用的应用程序共享, 例如端口10000到10019。)但是, 建议你将客户端端口范围设置为服务器端口范围的子集。</span><span class="sxs-lookup"><span data-stu-id="3874e-140">(For example, on the client computers you could configure application sharing to use, say, ports 10000 through 10019.) However, it is recommended that you make your client port ranges a subset of your server port ranges.</span></span>

<span data-ttu-id="3874e-141">此外, 你可能已注意到已为服务器上的应用程序共享保留了8348端口, 但仅为客户端上的应用程序共享设置了20个端口。</span><span class="sxs-lookup"><span data-stu-id="3874e-141">In addition, you might have noticed that 8348 ports were set aside for application sharing on the servers, but only 20 ports were set aside for application sharing on the clients.</span></span> <span data-ttu-id="3874e-142">我们也建议这样做, 但这并不是一种既难又快的规则。</span><span class="sxs-lookup"><span data-stu-id="3874e-142">This, too is recommended, but is not a hard-and-fast rule.</span></span> <span data-ttu-id="3874e-143">通常, 你可以考虑每个可用的端口来表示单个通信会话: 如果端口范围内有100个端口, 这意味着所涉及的计算机可以参与, 在任何给定时间最多可参与100个通信会话。</span><span class="sxs-lookup"><span data-stu-id="3874e-143">In general, you can consider each available port to represent a single communication session: if you have 100 ports available in a port range that means that the computer in question could participate in, at most, 100 communication sessions at any given time.</span></span> <span data-ttu-id="3874e-144">由于服务器可能会涉及比客户端更多的对话, 因此打开服务器上的更多端口比在客户端上更有意义。</span><span class="sxs-lookup"><span data-stu-id="3874e-144">Because servers will likely take part in many more conversations than clients, it makes sense to open many more ports on servers than on clients.</span></span> <span data-ttu-id="3874e-145">在客户端上为应用程序共享设置20个端口意味着, 用户可以同时在指定设备上参与20个应用程序共享会话。</span><span class="sxs-lookup"><span data-stu-id="3874e-145">Setting aside 20 ports for application sharing on a client means that a user could participate in 20 application sharing sessions on the specified device, and all at the same time.</span></span> <span data-ttu-id="3874e-146">这应该足以满足大多数用户的需要。</span><span class="sxs-lookup"><span data-stu-id="3874e-146">That should prove sufficient for the vast majority of your users.</span></span>

<span data-ttu-id="3874e-147">若要将之前的端口范围分配给你的会议配置设置的全局集合, 你可以使用以下 Lync Server Management Shell 命令:</span><span class="sxs-lookup"><span data-stu-id="3874e-147">To assign the preceding port ranges to your global collection of conferencing configuration settings you can use the following Lync Server Management Shell command:</span></span>

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="3874e-148">或者, 使用此命令为所有会议配置设置分配这些相同的端口范围:</span><span class="sxs-lookup"><span data-stu-id="3874e-148">Or, use this command to assign these same port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="3874e-149">单个用户必须从 Lync 注销, 然后重新登录才能使这些更改实际生效。</span><span class="sxs-lookup"><span data-stu-id="3874e-149">Individual users must log off from Lync and then log back on before these changes will actually take effect.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3874e-150">您还可以启用客户端媒体端口范围, 然后使用一个命令分配这些端口范围。</span><span class="sxs-lookup"><span data-stu-id="3874e-150">You can also enable client media port ranges, and then assign those port ranges, using a single command.</span></span> <span data-ttu-id="3874e-151">例如：</span><span class="sxs-lookup"><span data-stu-id="3874e-151">For example:</span></span><BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>



</div>

</div>

<span> </span>

</div>

</div>

</div>

