---
title: Lync Server 2013：为 Microsoft Lync 客户端配置端口范围
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring port ranges for your Microsoft Lync clients
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204760(v=OCS.15)
ms:contentKeyID: 48183694
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea0300b042dc124f0fb8bf523221e39128cbf57a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033731"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-for-your-microsoft-lync-clients-in-lync-server-2013"></a><span data-ttu-id="bea90-102">在 Lync Server 2013 中为 Microsoft Lync 客户端配置端口范围</span><span class="sxs-lookup"><span data-stu-id="bea90-102">Configuring port ranges for your Microsoft Lync clients in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bea90-103">_**上次修改的主题：** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="bea90-103">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="bea90-104">默认情况下，Lync 客户端应用程序可以在通信会话中参与时使用端口1024和65535之间的任何端口;这是因为不会为客户端自动启用特定端口范围。</span><span class="sxs-lookup"><span data-stu-id="bea90-104">By default, Lync client applications can use any port between ports 1024 and 65535 when involved in a communication session; this is because specific port ranges are not automatically enabled for clients.</span></span> <span data-ttu-id="bea90-105">但是，若要使用服务质量，您将需要为一系列特定端口范围重新分配各种通信类型（音频、视频、媒体、应用程序共享和文件传输）。</span><span class="sxs-lookup"><span data-stu-id="bea90-105">In order to use Quality of Service, however, you will need to reassign the various traffic types (audio, video, media, application sharing, and file transfer) to a series of unique port ranges.</span></span> <span data-ttu-id="bea90-106">可使用 Set-CsConferencingConfiguration cmdlet 完成此操作。</span><span class="sxs-lookup"><span data-stu-id="bea90-106">This can be done by using the Set-CsConferencingConfiguration cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bea90-107">最终用户不能自行进行这些更改。</span><span class="sxs-lookup"><span data-stu-id="bea90-107">End users cannot make these changes themselves.</span></span> <span data-ttu-id="bea90-108">仅使用 CsConferencingConfiguration cmdlet 的管理员才能进行端口更改。</span><span class="sxs-lookup"><span data-stu-id="bea90-108">Port changes can only be made by administrators using the Set-CsConferencingConfiguration cmdlet.</span></span>



</div>

<span data-ttu-id="bea90-109">您可以通过在 Microsoft Lync Server 2013 命令行管理程序中运行以下命令，来确定当前用于通信会话的端口范围：</span><span class="sxs-lookup"><span data-stu-id="bea90-109">You can determine which port ranges are currently used for communication sessions by running the following command from within the Microsoft Lync Server 2013 Management Shell:</span></span>

    Get-CsConferencingConfiguration

<span data-ttu-id="bea90-110">假定您在安装 Lync Server 2013 后未对会议设置进行任何更改，则应返回包含这些属性值的信息：</span><span class="sxs-lookup"><span data-stu-id="bea90-110">Assuming that you have not made any changes to your conferencing settings since you installed Lync Server 2013, you should get back information that includes these property values:</span></span>

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

<span data-ttu-id="bea90-111">如果您仔细查看上面的输出，您会发现两点很重要。</span><span class="sxs-lookup"><span data-stu-id="bea90-111">If you look closely at the preceding output, you'll see two things of importance.</span></span> <span data-ttu-id="bea90-112">首先，ClientMediaPortRangeEnabled 属性设置为 False：</span><span class="sxs-lookup"><span data-stu-id="bea90-112">First, the ClientMediaPortRangeEnabled property is set to False:</span></span>

    ClientMediaPortRangeEnabled : False

<span data-ttu-id="bea90-113">这一点很重要，因为当此属性设置为 False 时，Lync 客户端将在通信会话中涉及时使用端口1024和65535之间的任何可用端口;无论任何其他端口设置（例如，ClientMediaPort 或 ClientVideoPort），都是如此。</span><span class="sxs-lookup"><span data-stu-id="bea90-113">That's important because, when this property is set to False, Lync clients will use any available port between ports 1024 and 65535 when involved in a communication session; this is true regardless of any other port settings (for example, ClientMediaPort or ClientVideoPort).</span></span> <span data-ttu-id="bea90-114">如果要限制对一组指定端口的使用（如果您计划实施服务质量，则需要这样做），则必须首先启用客户端媒体端口范围。</span><span class="sxs-lookup"><span data-stu-id="bea90-114">If you want to restrict usage to a specified set of ports (and this is something you do want to do if you plan on implementing Quality of Service) then you must first enable client media port ranges.</span></span> <span data-ttu-id="bea90-115">可以使用以下 Windows PowerShell 命令来执行此操作：</span><span class="sxs-lookup"><span data-stu-id="bea90-115">That can be done using the following Windows PowerShell command:</span></span>

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

<span data-ttu-id="bea90-p105">上述命令为会议配置设置的全局集合启用客户端媒体端口范围；但是，这些设置也可应用于站点范围和/或服务范围（仅限会议服务器服务）。若要为特定站点或服务器启用客户端媒体端口范围，请在调用 Set-CsConferencingConfiguration 时指定该站点或服务器的标识：</span><span class="sxs-lookup"><span data-stu-id="bea90-p105">The preceding command enables client media port ranges for the global collection of conferencing configuration settings; however, these settings can also be applied to the site scope and/or the service scope (for the Conferencing Server service only). To enable client media port ranges for a specific site or server, specify the Identity of that site or server when calling Set-CsConferencingConfiguration:</span></span>

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

<span data-ttu-id="bea90-118">或者，也可以使用此命令同时为您的所有会议配置设置启用端口范围：</span><span class="sxs-lookup"><span data-stu-id="bea90-118">Alternatively, you can use this command to simultaneously enable port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

<span data-ttu-id="bea90-119">您将发现的另一个重要事项是，示例输出显示默认情况下为每种类型的网络通信设置的媒体端口范围是相同的：</span><span class="sxs-lookup"><span data-stu-id="bea90-119">The second thing of importance you will notice is that the sample output shows that, by default, the media port ranges set for each type of network traffic are identical:</span></span>

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

<span data-ttu-id="bea90-p106">若要实施 QoS，其中每个端口范围都需要是唯一的。例如，您可以按如下所示配置端口范围：</span><span class="sxs-lookup"><span data-stu-id="bea90-p106">In order to implement QoS, each of these port ranges will need to be unique. For example, you might configure the port ranges like this:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bea90-122">客户端通信类型</span><span class="sxs-lookup"><span data-stu-id="bea90-122">Client Traffic Type</span></span></th>
<th><span data-ttu-id="bea90-123">起始端口</span><span class="sxs-lookup"><span data-stu-id="bea90-123">Port Start</span></span></th>
<th><span data-ttu-id="bea90-124">端口范围</span><span class="sxs-lookup"><span data-stu-id="bea90-124">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bea90-125">音频</span><span class="sxs-lookup"><span data-stu-id="bea90-125">Audio</span></span></p></td>
<td><p><span data-ttu-id="bea90-126">50020</span><span class="sxs-lookup"><span data-stu-id="bea90-126">50020</span></span></p></td>
<td><p><span data-ttu-id="bea90-127">20</span><span class="sxs-lookup"><span data-stu-id="bea90-127">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bea90-128">视频</span><span class="sxs-lookup"><span data-stu-id="bea90-128">Video</span></span></p></td>
<td><p><span data-ttu-id="bea90-129">58000</span><span class="sxs-lookup"><span data-stu-id="bea90-129">58000</span></span></p></td>
<td><p><span data-ttu-id="bea90-130">20</span><span class="sxs-lookup"><span data-stu-id="bea90-130">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bea90-131">应用程序共享</span><span class="sxs-lookup"><span data-stu-id="bea90-131">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="bea90-132">42000</span><span class="sxs-lookup"><span data-stu-id="bea90-132">42000</span></span></p></td>
<td><p><span data-ttu-id="bea90-133">20</span><span class="sxs-lookup"><span data-stu-id="bea90-133">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bea90-134">文件传输</span><span class="sxs-lookup"><span data-stu-id="bea90-134">File transfer</span></span></p></td>
<td><p><span data-ttu-id="bea90-135">42020</span><span class="sxs-lookup"><span data-stu-id="bea90-135">42020</span></span></p></td>
<td><p><span data-ttu-id="bea90-136">20</span><span class="sxs-lookup"><span data-stu-id="bea90-136">20</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="bea90-p107">在上表中，客户端端口范围表示为您的服务器配置的端口范围的一部分。例如，在服务器上，应用程序共享已配置为使用 40803 和 49151 之间的端口；在客户端计算机上，应用程序共享配置为使用 42000 和 42019 之间的端口。这样做也是为了便于管理 QoS：客户端端口不必表示为服务器上使用的端口的一部分。（例如，在客户端计算机上，您可以配置应用程序共享以使用 10000 和 10019 之间的端口。）但是，建议您使您的客户端端口范围位于服务器端口范围内。</span><span class="sxs-lookup"><span data-stu-id="bea90-p107">In the preceding table, client port ranges represent a subset of the port ranges configured for your servers. For example, on the servers, application sharing was configured to use ports 40803 through 49151; on the client computers, application sharing is configured to use ports 42000 through 42019. This, too is done primarily to make administration of QoS easier: client ports do not have to represent a subset of the ports used on the server. (For example, on the client computers you could configure application sharing to use, say, ports 10000 through 10019.) However, it is recommended that you make your client port ranges a subset of your server port ranges.</span></span>

<span data-ttu-id="bea90-p108">另外，您可能已注意到，为服务器上的应用程序共享留出了 8348 个端口，但为客户端上的应用程序共享只留出了 20 个端口。这也是建议做法，但不是硬性规定。通常，您可以考虑用每个可用端口来表示一个通信会话：如果端口范围内有 100 个可用端口，则意味着相关计算机在任何给定时间内最多可参与 100 个通信会话。因为服务器参与的会话数可能多于客户端，所以在服务器上打开的端口数应多于在客户端上打开的端口数。为客户端上的应用程序共享留出 20 个端口意味着用户可以参与指定设备上的 20 个应用程序共享会话，并且所有会话是同时进行的。对于您的大多数用户来说，这样做应该足够了。</span><span class="sxs-lookup"><span data-stu-id="bea90-p108">In addition, you might have noticed that 8348 ports were set aside for application sharing on the servers, but only 20 ports were set aside for application sharing on the clients. This, too is recommended, but is not a hard-and-fast rule. In general, you can consider each available port to represent a single communication session: if you have 100 ports available in a port range that means that the computer in question could participate in, at most, 100 communication sessions at any given time. Because servers will likely take part in many more conversations than clients, it makes sense to open many more ports on servers than on clients. Setting aside 20 ports for application sharing on a client means that a user could participate in 20 application sharing sessions on the specified device, and all at the same time. That should prove sufficient for the vast majority of your users.</span></span>

<span data-ttu-id="bea90-147">若要将之前的端口范围分配给全局会议配置设置集合，可以使用以下 Lync Server 命令行管理程序命令：</span><span class="sxs-lookup"><span data-stu-id="bea90-147">To assign the preceding port ranges to your global collection of conferencing configuration settings you can use the following Lync Server Management Shell command:</span></span>

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="bea90-148">或者，使用此命令为您的所有会议配置设置分配这些相同的端口范围：</span><span class="sxs-lookup"><span data-stu-id="bea90-148">Or, use this command to assign these same port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="bea90-149">单个用户必须从 Lync 注销，然后重新登录才能使这些更改实际生效。</span><span class="sxs-lookup"><span data-stu-id="bea90-149">Individual users must log off from Lync and then log back on before these changes will actually take effect.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bea90-150">您还可以启用客户端媒体端口范围，然后使用单个命令分配这些端口范围。</span><span class="sxs-lookup"><span data-stu-id="bea90-150">You can also enable client media port ranges, and then assign those port ranges, using a single command.</span></span> <span data-ttu-id="bea90-151">例如：</span><span class="sxs-lookup"><span data-stu-id="bea90-151">For example:</span></span><BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>



</div>

</div>

<span> </span>

</div>

</div>

</div>

