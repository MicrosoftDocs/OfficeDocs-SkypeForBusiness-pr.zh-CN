---
title: 为客户端配置端口范围和服务质量策略
ms.reviewer: ''
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204760(v=OCS.15)
ms:contentKeyID: 48183694
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 本文介绍如何为客户端配置端口范围，以及如何在 Skype for Business Server 中为在 Windows 10 上运行的客户端配置服务质量策略。
ms.openlocfilehash: b2961193bef799742ac3b79a4f421a7aa50c5a03
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814198"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-clients-in-skype-for-business-server"></a><span data-ttu-id="decb0-103">在 Skype for Business Server 中为客户端配置端口范围和服务质量策略</span><span class="sxs-lookup"><span data-stu-id="decb0-103">Configuring port ranges and a Quality of Service policy for your clients in Skype for Business Server</span></span>

<span data-ttu-id="decb0-104">本文介绍如何为客户端配置端口范围，以及如何在 Skype for Business Server 中为在 Windows 10 上运行的客户端配置服务质量策略。</span><span class="sxs-lookup"><span data-stu-id="decb0-104">This article describes how to configure port ranges for your clients and configuring Quality of Service policies in Skype for Business Server for clients running on Windows 10.</span></span>

## <a name="configure-port-ranges"></a><span data-ttu-id="decb0-105">配置端口范围</span><span class="sxs-lookup"><span data-stu-id="decb0-105">Configure port ranges</span></span>

<span data-ttu-id="decb0-106">默认情况下，当参与通信会话时，Skype for Business 客户端应用程序可以使用端口 1024 和 65535 之间的任意端口;这是因为不会自动为客户端启用特定端口范围。</span><span class="sxs-lookup"><span data-stu-id="decb0-106">By default, Skype for Business client applications can use any port between ports 1024 and 65535 when involved in a communication session; this is because specific port ranges are not automatically enabled for clients.</span></span> <span data-ttu-id="decb0-107">但是，若要使用服务质量，您将需要为一系列特定端口范围重新分配各种通信类型（音频、视频、媒体、应用程序共享和文件传输）。</span><span class="sxs-lookup"><span data-stu-id="decb0-107">In order to use Quality of Service, however, you will need to reassign the various traffic types (audio, video, media, application sharing, and file transfer) to a series of unique port ranges.</span></span> <span data-ttu-id="decb0-108">可使用 Set-CsConferencingConfiguration cmdlet 完成此操作。</span><span class="sxs-lookup"><span data-stu-id="decb0-108">This can be done by using the Set-CsConferencingConfiguration cmdlet.</span></span>

> [!NOTE]  
> <span data-ttu-id="decb0-109">最终用户无法自行进行这些更改。</span><span class="sxs-lookup"><span data-stu-id="decb0-109">End users cannot make these changes themselves.</span></span> <span data-ttu-id="decb0-110">端口更改只能由管理员使用 Set-CsConferencingConfiguration cmdlet 进行。</span><span class="sxs-lookup"><span data-stu-id="decb0-110">Port changes can only be made by administrators using the Set-CsConferencingConfiguration cmdlet.</span></span>


<span data-ttu-id="decb0-111">通过从 Skype for Business Server 命令行管理程序 中运行以下命令，可以确定当前用于通信会话的端口范围：</span><span class="sxs-lookup"><span data-stu-id="decb0-111">You can determine which port ranges are currently used for communication sessions by running the following command from within the Skype for Business Server Management Shell:</span></span>

    Get-CsConferencingConfiguration

<span data-ttu-id="decb0-112">假定自安装 Skype for Business Server 后未对会议设置进行任何更改，应返回包含以下属性值的信息：</span><span class="sxs-lookup"><span data-stu-id="decb0-112">Assuming that you have not made any changes to your conferencing settings since you installed Skype for Business Server, you should get back information that includes these property values:</span></span>

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

<span data-ttu-id="decb0-113">如果您仔细查看上面的输出，您会发现两点很重要。</span><span class="sxs-lookup"><span data-stu-id="decb0-113">If you look closely at the preceding output, you'll see two things of importance.</span></span> <span data-ttu-id="decb0-114">首先，ClientMediaPortRangeEnabled 属性设置为 False：</span><span class="sxs-lookup"><span data-stu-id="decb0-114">First, the ClientMediaPortRangeEnabled property is set to False:</span></span>

    ClientMediaPortRangeEnabled : False

<span data-ttu-id="decb0-115">这一点很重要，因为当此属性设置为 False 时，当参与通信会话时，Skype for Business 客户端将使用端口 1024 和 65535 之间的任何可用端口;无论使用任何其他端口设置， (例如 ClientMediaPort 或 ClientVideoPort) 。</span><span class="sxs-lookup"><span data-stu-id="decb0-115">That's important because, when this property is set to False, Skype for Business clients will use any available port between ports 1024 and 65535 when involved in a communication session; this is true regardless of any other port settings (for example, ClientMediaPort or ClientVideoPort).</span></span> <span data-ttu-id="decb0-116">如果要将用法限制为一组指定的端口 (并且如果您计划实施服务质量) ，则必须先启用客户端媒体端口范围。</span><span class="sxs-lookup"><span data-stu-id="decb0-116">If you want to restrict usage to a specified set of ports (and this is something you do want to do if you plan on implementing Quality of Service), then you must first enable client media port ranges.</span></span> <span data-ttu-id="decb0-117">可以使用以下命令完成Windows PowerShell操作：</span><span class="sxs-lookup"><span data-stu-id="decb0-117">That can be done using the following Windows PowerShell command:</span></span>

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

<span data-ttu-id="decb0-p105">上述命令为会议配置设置的全局集合启用客户端媒体端口范围；但是，这些设置也可应用于站点范围和/或服务范围（仅限会议服务器服务）。若要为特定站点或服务器启用客户端媒体端口范围，请在调用 Set-CsConferencingConfiguration 时指定该站点或服务器的标识：</span><span class="sxs-lookup"><span data-stu-id="decb0-p105">The preceding command enables client media port ranges for the global collection of conferencing configuration settings; however, these settings can also be applied to the site scope and/or the service scope (for the Conferencing Server service only). To enable client media port ranges for a specific site or server, specify the Identity of that site or server when calling Set-CsConferencingConfiguration:</span></span>

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

<span data-ttu-id="decb0-120">或者，也可以使用此命令同时为您的所有会议配置设置启用端口范围：</span><span class="sxs-lookup"><span data-stu-id="decb0-120">Alternatively, you can use this command to simultaneously enable port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

<span data-ttu-id="decb0-121">您将发现的另一个重要事项是，示例输出显示默认情况下为每种类型的网络通信设置的媒体端口范围是相同的：</span><span class="sxs-lookup"><span data-stu-id="decb0-121">The second thing of importance you will notice is that the sample output shows that, by default, the media port ranges set for each type of network traffic are identical:</span></span>

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

<span data-ttu-id="decb0-p106">若要实施 QoS，其中每个端口范围都需要是唯一的。例如，您可以按如下所示配置端口范围：</span><span class="sxs-lookup"><span data-stu-id="decb0-p106">In order to implement QoS, each of these port ranges will need to be unique. For example, you might configure the port ranges like this:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="decb0-124">客户端通信类型</span><span class="sxs-lookup"><span data-stu-id="decb0-124">Client Traffic Type</span></span></th>
<th><span data-ttu-id="decb0-125">起始端口</span><span class="sxs-lookup"><span data-stu-id="decb0-125">Port Start</span></span></th>
<th><span data-ttu-id="decb0-126">端口范围</span><span class="sxs-lookup"><span data-stu-id="decb0-126">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="decb0-127">音频</span><span class="sxs-lookup"><span data-stu-id="decb0-127">Audio</span></span></p></td>
<td><p><span data-ttu-id="decb0-128">50020</span><span class="sxs-lookup"><span data-stu-id="decb0-128">50020</span></span></p></td>
<td><p><span data-ttu-id="decb0-129">20</span><span class="sxs-lookup"><span data-stu-id="decb0-129">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="decb0-130">视频</span><span class="sxs-lookup"><span data-stu-id="decb0-130">Video</span></span></p></td>
<td><p><span data-ttu-id="decb0-131">58000</span><span class="sxs-lookup"><span data-stu-id="decb0-131">58000</span></span></p></td>
<td><p><span data-ttu-id="decb0-132">20</span><span class="sxs-lookup"><span data-stu-id="decb0-132">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="decb0-133">应用程序共享</span><span class="sxs-lookup"><span data-stu-id="decb0-133">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="decb0-134">42000</span><span class="sxs-lookup"><span data-stu-id="decb0-134">42000</span></span></p></td>
<td><p><span data-ttu-id="decb0-135">20</span><span class="sxs-lookup"><span data-stu-id="decb0-135">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="decb0-136">文件传输</span><span class="sxs-lookup"><span data-stu-id="decb0-136">File transfer</span></span></p></td>
<td><p><span data-ttu-id="decb0-137">42020</span><span class="sxs-lookup"><span data-stu-id="decb0-137">42020</span></span></p></td>
<td><p><span data-ttu-id="decb0-138">20</span><span class="sxs-lookup"><span data-stu-id="decb0-138">20</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="decb0-139">在上表中，客户端端口范围表示为您的服务器配置的端口范围的一部分。</span><span class="sxs-lookup"><span data-stu-id="decb0-139">In the preceding table, client port ranges represent a subset of the port ranges configured for your servers.</span></span> <span data-ttu-id="decb0-140">例如，在服务器上，应用程序共享已配置为使用 40803 和 49151 之间的端口；在客户端计算机上，应用程序共享配置为使用 42000 和 42019 之间的端口。</span><span class="sxs-lookup"><span data-stu-id="decb0-140">For example, on the servers, application sharing was configured to use ports 40803 through 49151; on the client computers, application sharing is configured to use ports 42000 through 42019.</span></span> <span data-ttu-id="decb0-141">这主要用于简化 QoS 管理：客户端端口不需要表示服务器上使用的端口的子集。</span><span class="sxs-lookup"><span data-stu-id="decb0-141">This, too, is done primarily to make administration of QoS easier: client ports do not have to represent a subset of the ports used on the server.</span></span> <span data-ttu-id="decb0-142"> (例如，在客户端计算机上，可以将应用程序共享配置为使用端口 10000 到 10019。) 但是，建议您使客户端端口范围成为服务器端口范围的子集。</span><span class="sxs-lookup"><span data-stu-id="decb0-142">(For example, on the client computers you could configure application sharing to use, say, ports 10000 through 10019.) However, it is recommended that you make your client port ranges a subset of your server port ranges.</span></span>

<span data-ttu-id="decb0-143">另外，您可能已注意到，为服务器上的应用程序共享留出了 8348 个端口，但为客户端上的应用程序共享只留出了 20 个端口。</span><span class="sxs-lookup"><span data-stu-id="decb0-143">In addition, you might have noticed that 8348 ports were set aside for application sharing on the servers, but only 20 ports were set aside for application sharing on the clients.</span></span> <span data-ttu-id="decb0-144">这也是建议这样做的，但这不是一种硬性规则。</span><span class="sxs-lookup"><span data-stu-id="decb0-144">This, too, is recommended, but is not a hard-and-fast rule.</span></span> <span data-ttu-id="decb0-145">通常，您可以考虑每个可用端口来表示单个通信会话：如果端口范围内有 100 个可用端口，这意味着有关计算机在任何给定时间最多可以参与 100 个通信会话。</span><span class="sxs-lookup"><span data-stu-id="decb0-145">In general, you can consider each available port to represent a single communication session: if you have 100 ports available in a port range, that means that the computer in question could participate in, at most, 100 communication sessions at any given time.</span></span> <span data-ttu-id="decb0-146">因为服务器参与的会话数可能多于客户端，所以在服务器上打开的端口数应多于在客户端上打开的端口数。</span><span class="sxs-lookup"><span data-stu-id="decb0-146">Because servers will likely take part in many more conversations than clients, it makes sense to open many more ports on servers than on clients.</span></span> <span data-ttu-id="decb0-147">为客户端上的应用程序共享留出 20 个端口意味着用户可以参与指定设备上的 20 个应用程序共享会话，并且所有会话是同时进行的。</span><span class="sxs-lookup"><span data-stu-id="decb0-147">Setting aside 20 ports for application sharing on a client means that a user could participate in 20 application sharing sessions on the specified device, and all at the same time.</span></span> <span data-ttu-id="decb0-148">对于您的大多数用户来说，这样做应该足够了。</span><span class="sxs-lookup"><span data-stu-id="decb0-148">That should prove sufficient for the vast majority of your users.</span></span>

<span data-ttu-id="decb0-149">若要将上述端口范围分配给会议配置设置的全局集合，可以使用以下 Skype for Business Server 命令行管理程序命令：</span><span class="sxs-lookup"><span data-stu-id="decb0-149">To assign the preceding port ranges to your global collection of conferencing configuration settings, you can use the following Skype for Business Server Management Shell command:</span></span>

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="decb0-150">或者，使用此命令为您的所有会议配置设置分配这些相同的端口范围：</span><span class="sxs-lookup"><span data-stu-id="decb0-150">Or, use this command to assign these same port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="decb0-151">个别用户必须从 Skype for Business 注销，然后重新登录，这些更改才能实际生效。</span><span class="sxs-lookup"><span data-stu-id="decb0-151">Individual users must log off from Skype for Business and then log back on before these changes will actually take effect.</span></span>

> [!NOTE]  
> <span data-ttu-id="decb0-152">您还可以启用客户端媒体端口范围，然后使用单个命令分配这些端口范围。</span><span class="sxs-lookup"><span data-stu-id="decb0-152">You can also enable client media port ranges, and then assign those port ranges, using a single command.</span></span> <span data-ttu-id="decb0-153">例如：</span><span class="sxs-lookup"><span data-stu-id="decb0-153">For example:</span></span><BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>

## <a name="configure-quality-of-service-policies-for-clients-running-on-windows-10"></a><span data-ttu-id="decb0-154">为在 Windows 10 上运行的客户端配置服务质量策略</span><span class="sxs-lookup"><span data-stu-id="decb0-154">Configure Quality of Service policies for clients running on Windows 10</span></span>

<span data-ttu-id="decb0-155">除了指定供 Skype for Business 客户端使用的端口范围外，还必须创建将应用于客户端计算机的单独服务质量策略。</span><span class="sxs-lookup"><span data-stu-id="decb0-155">In addition to specifying port ranges for use by your Skype for Business clients, you must also create separate Quality of Service policies that will be applied to client computers.</span></span> <span data-ttu-id="decb0-156"> (为会议、应用程序和中介服务器创建的服务质量策略不应应用于客户端计算机。) 此信息仅适用于运行 Skype for Business 客户端和 Windows 10 的计算机。</span><span class="sxs-lookup"><span data-stu-id="decb0-156">(The Quality of Service policies created for Conferencing, Application, and Mediation servers should not be applied to client computers.) This information applies only to computers running the Skype for Business client and Windows 10.</span></span>

<span data-ttu-id="decb0-157">以下示例使用此端口范围的设置创建音频策略和视频策略：</span><span class="sxs-lookup"><span data-stu-id="decb0-157">The following example uses this set of port ranges to create an audio policy and a video policy:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="decb0-158">客户端通信类型</span><span class="sxs-lookup"><span data-stu-id="decb0-158">Client Traffic Type</span></span></th>
<th><span data-ttu-id="decb0-159">起始端口</span><span class="sxs-lookup"><span data-stu-id="decb0-159">Port Start</span></span></th>
<th><span data-ttu-id="decb0-160">端口范围</span><span class="sxs-lookup"><span data-stu-id="decb0-160">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="decb0-161">音频</span><span class="sxs-lookup"><span data-stu-id="decb0-161">Audio</span></span></p></td>
<td><p><span data-ttu-id="decb0-162">50020</span><span class="sxs-lookup"><span data-stu-id="decb0-162">50020</span></span></p></td>
<td><p><span data-ttu-id="decb0-163">20</span><span class="sxs-lookup"><span data-stu-id="decb0-163">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="decb0-164">视频</span><span class="sxs-lookup"><span data-stu-id="decb0-164">Video</span></span></p></td>
<td><p><span data-ttu-id="decb0-165">58000</span><span class="sxs-lookup"><span data-stu-id="decb0-165">58000</span></span></p></td>
<td><p><span data-ttu-id="decb0-166">20</span><span class="sxs-lookup"><span data-stu-id="decb0-166">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="decb0-167">应用程序共享</span><span class="sxs-lookup"><span data-stu-id="decb0-167">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="decb0-168">42000</span><span class="sxs-lookup"><span data-stu-id="decb0-168">42000</span></span></p></td>
<td><p><span data-ttu-id="decb0-169">20</span><span class="sxs-lookup"><span data-stu-id="decb0-169">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="decb0-170">文件传输</span><span class="sxs-lookup"><span data-stu-id="decb0-170">File transfer</span></span></p></td>
<td><p><span data-ttu-id="decb0-171">42020</span><span class="sxs-lookup"><span data-stu-id="decb0-171">42020</span></span></p></td>
<td><p><span data-ttu-id="decb0-172">20</span><span class="sxs-lookup"><span data-stu-id="decb0-172">20</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="decb0-173">若要为 Windows 10 计算机创建服务质量音频策略，请首先登录到安装了组策略管理的计算机。</span><span class="sxs-lookup"><span data-stu-id="decb0-173">To create a Quality of Service audio policy for Windows 10 computers, first log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="decb0-174">打开组策略 **(单击"** 开始"，指向"管理工具"，然后单击"组策略管理 **) ，** 然后完成以下过程：</span><span class="sxs-lookup"><span data-stu-id="decb0-174">Open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**), and then complete the following procedure:</span></span>

1.  <span data-ttu-id="decb0-175">在组策略管理中，找到其中应创建新策略的容器。</span><span class="sxs-lookup"><span data-stu-id="decb0-175">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="decb0-176">例如，如果所有客户端计算机都位于名为"客户端"的 OU 中，应在客户端 OU 中创建新策略。</span><span class="sxs-lookup"><span data-stu-id="decb0-176">For example, if all your client computers are located in an OU named Clients, the new policy should be created in the Client OU.</span></span>

2.  <span data-ttu-id="decb0-177">右键单击相应的容器，然后单击"在此域中创建 **GPO"，并在此处链接它**。</span><span class="sxs-lookup"><span data-stu-id="decb0-177">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="decb0-178">在 **"新建 GPO"** 对话框中，在"名称"框中键入新组策略对象 **的名称，** 然后单击"**确定"。**</span><span class="sxs-lookup"><span data-stu-id="decb0-178">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box, and then click **OK**.</span></span>

4.  <span data-ttu-id="decb0-179">右键单击新建的策略，然后单击"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="decb0-179">Right-click the newly-created policy, and then click **Edit**.</span></span>

5.  <span data-ttu-id="decb0-180">在组策略管理编辑器中，展开"**计算机** 配置"，展开 **"Windows 设置**"，右键单击"基于策略的 **QoS"，** 然后单击"**创建新策略"。**</span><span class="sxs-lookup"><span data-stu-id="decb0-180">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6.  <span data-ttu-id="decb0-181">在 **基于策略的 QoS** 对话框中的打开页上，在"名称"框中键入新 **策略** 的名称。</span><span class="sxs-lookup"><span data-stu-id="decb0-181">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy in the **Name** box.</span></span> <span data-ttu-id="decb0-182">选择“指定 DSCP 值”，并将该值设置为“46”。</span><span class="sxs-lookup"><span data-stu-id="decb0-182">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="decb0-183">将“指定出站调节率”保留为未选中状态，然后单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="decb0-183">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7.  <span data-ttu-id="decb0-184">On the next page， select **Only applications with this executable name，** enter **Lync.exe** as the name， and then click **Next**.</span><span class="sxs-lookup"><span data-stu-id="decb0-184">On the next page, select **Only applications with this executable name**, enter **Lync.exe** as the name, and then click **Next**.</span></span> <span data-ttu-id="decb0-185">此设置指示策略仅对来自 Skype for Business 客户端的匹配流量设置优先级。</span><span class="sxs-lookup"><span data-stu-id="decb0-185">This setting instructs the policy to only prioritize matching traffic from the Skype for Business client.</span></span>

8.  <span data-ttu-id="decb0-186">第三页上，确保同时选择"任何 **源 IP** 地址"和"任何目标 **IP** 地址"，然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="decb0-186">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="decb0-187">这两个设置确保将管理这些数据包，与哪台计算机（IP 地址）发送这些数据包及哪台计算机（IP 地址）将接收这些数据包无关。</span><span class="sxs-lookup"><span data-stu-id="decb0-187">These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

9.  <span data-ttu-id="decb0-188">在第四页上，从“选择此 QoS 策略所适用的协议”下拉列表中选择“TCP 和 UDP”。</span><span class="sxs-lookup"><span data-stu-id="decb0-188">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="decb0-189">TCP (传输控制协议) 和 UDP (用户数据报协议) 是 Skype for Business Server 及其客户端应用程序最常使用的两种网络协议。</span><span class="sxs-lookup"><span data-stu-id="decb0-189">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Skype for Business Server and its client applications.</span></span>

10. <span data-ttu-id="decb0-p117">在标题“指定源端口号”下，选择“从此源端口或范围”。在附带的文本框中，键入为音频传输保留的端口范围。例如，如果您为音频流量保留端口 50020 到端口 50039，则使用以下格式输入端口范围：“50020:50039”。单击“完成”。</span><span class="sxs-lookup"><span data-stu-id="decb0-p117">Under the heading **Specify the source port number**, select **From this source port or range**. In the accompanying text box, type the port range reserved for audio transmissions. For example, if you reserved ports 50020 through ports 50039 for audio traffic enter the port range using this format: **50020:50039**. Click **Finish**.</span></span>

<span data-ttu-id="decb0-p118">在您为音频创建了 QoS 策略后，然后应该为视频创建第二个策略。要为视频创建策略，请按照您创建音频策略时遵循的相同基本过程，进行下列替换项：</span><span class="sxs-lookup"><span data-stu-id="decb0-p118">After you have created the QoS policy for audio you should then create a second policy for video. To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="decb0-196">使用不同的策略 (和唯) 策略名称。</span><span class="sxs-lookup"><span data-stu-id="decb0-196">Use a different (and unique) policy name.</span></span>

  - <span data-ttu-id="decb0-p119">将 DSCP 值设置为“34”代替 46。（如先前所述，您不必使用为 34 的 DSCP 值；只是必须分配一个与用于音频不同的 DSCP 值。）</span><span class="sxs-lookup"><span data-stu-id="decb0-p119">Set the DSCP value to **34** instead of 46. (As noted previously, you do not have to use the DSCP value 34; you simply must assign a different DSCP value than the one used for audio.)</span></span>

  - <span data-ttu-id="decb0-199">将以前配置的端口范围用于视频流量。</span><span class="sxs-lookup"><span data-stu-id="decb0-199">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="decb0-200">例如，如果为视频保留端口 58000 到 58019，请设置端口范围 **：58000：58019。**</span><span class="sxs-lookup"><span data-stu-id="decb0-200">For example, if you have reserved ports 58000 through 58019 for video, set the port range to this: **58000:58019**.</span></span>

<span data-ttu-id="decb0-201">如果您决定创建用于管理应用程序共享通信的策略，请进行以下替换：</span><span class="sxs-lookup"><span data-stu-id="decb0-201">If you decide to create a policy for managing application sharing traffic, make these substitutions:</span></span>

  - <span data-ttu-id="decb0-202">使用不同的 (和) 策略名称 (例如 **，Skype for Business Server 应用程序共享**) 。</span><span class="sxs-lookup"><span data-stu-id="decb0-202">Use a different (and unique) policy name (for example, **Skype for Business Server Application Sharing**).</span></span>

  - <span data-ttu-id="decb0-p121">将 DSCP 设置为“24”代替 46。（另外，此值不必为 24；只是必须用于不同于音频和视频的 DSCP 值。）</span><span class="sxs-lookup"><span data-stu-id="decb0-p121">Set the DSCP value to **24** instead of 46. (Again, this value does not have to be 24; it simply must be different than the DSCP values used for audio and for video.)</span></span>

  - <span data-ttu-id="decb0-205">将以前配置的端口范围用于视频流量。</span><span class="sxs-lookup"><span data-stu-id="decb0-205">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="decb0-206">例如，如果为应用程序共享保留端口 42000 到 42019，请设置端口范围 **：42000：42019。**</span><span class="sxs-lookup"><span data-stu-id="decb0-206">For example, if you have reserved ports 42000 through 42019 for application sharing, set the port range to this: **42000:42019**.</span></span>

<span data-ttu-id="decb0-207">对于文件传输策略：</span><span class="sxs-lookup"><span data-stu-id="decb0-207">For a file transfer policy:</span></span>

  - <span data-ttu-id="decb0-208">使用不同的 (和) 策略 (例如 **，Skype for Business Server 文件** 传输) 。</span><span class="sxs-lookup"><span data-stu-id="decb0-208">Use a different (and unique) policy name (for example, **Skype for Business Server File Transfers**).</span></span>

  - <span data-ttu-id="decb0-209">将 DSCP 值设置为 **14。**</span><span class="sxs-lookup"><span data-stu-id="decb0-209">Set the DSCP value to **14**.</span></span> <span data-ttu-id="decb0-210"> (，此值不一定为 14;它只是一个唯一的 DSCP 代码。) </span><span class="sxs-lookup"><span data-stu-id="decb0-210">(Again, this value does not have to be 14; it simply must be a unique DSCP code.)</span></span>

  - <span data-ttu-id="decb0-211">对应用程序使用以前配置的端口范围。</span><span class="sxs-lookup"><span data-stu-id="decb0-211">Use the previously configured port range for application.</span></span> <span data-ttu-id="decb0-212">例如，如果为应用程序共享保留端口 42020 到 42039，则端口范围设置为 **：42020：42039。**</span><span class="sxs-lookup"><span data-stu-id="decb0-212">For example, if you have reserved ports 42020 through 42039 for application sharing, set the port range to this: **42020:42039**.</span></span>

<span data-ttu-id="decb0-p125">在客户端计算机上刷新组策略之前，已创建的新策略不会生效。尽管组策略会定期自行刷新，但是您可以通过在需要刷新的组策略所在的每台计算机上运行下列命令来强制立即刷新：</span><span class="sxs-lookup"><span data-stu-id="decb0-p125">The new policies you have created will not take effect until Group Policy has been refreshed on your client computers. Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpupdate.exe /force

<span data-ttu-id="decb0-p126">可从在管理员凭据下运行的任何命令窗口运行此命令。要在管理员凭据下运行命令窗口，请单击“开始”，右键单击“命令提示符”，然后单击“以管理员身份运行”。</span><span class="sxs-lookup"><span data-stu-id="decb0-p126">This command can be run from any command window that is running under administrator credentials. To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

<span data-ttu-id="decb0-217">请记住，应该将这些策略指向客户端计算机目标。</span><span class="sxs-lookup"><span data-stu-id="decb0-217">Keep in mind that these policies should be targeted towards your client computers.</span></span> <span data-ttu-id="decb0-218">它们不应应用于运行 Skype for Business Server 的服务器。</span><span class="sxs-lookup"><span data-stu-id="decb0-218">They should not be applied to servers running Skype for Business Server.</span></span>

<span data-ttu-id="decb0-219">要确保将网络数据包标记为相应的 DSCP 值，还应该通过完成以下过程在每台计算机上创建新的注册表项：</span><span class="sxs-lookup"><span data-stu-id="decb0-219">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="decb0-220">单击“开始”，然后单击“运行”。</span><span class="sxs-lookup"><span data-stu-id="decb0-220">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="decb0-221">在 **"运行** "对话框中，键入 **regedit，** 然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="decb0-221">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="decb0-222">在注册表编辑器中，展开 **HKEY \_ LOCAL \_ MACHINE，** 展开 **系统**，展开 **CurrentControlSet，** 展开 **服务**，然后展开 **Tcpip。**</span><span class="sxs-lookup"><span data-stu-id="decb0-222">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="decb0-223">右键单击“Tcpip”，指向“新建”，然后单击“项”。</span><span class="sxs-lookup"><span data-stu-id="decb0-223">Right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="decb0-224">新建注册表项后，键入 **QoS，** 然后按 Enter 重命名该注册表项。</span><span class="sxs-lookup"><span data-stu-id="decb0-224">After the new registry key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="decb0-225">右键单击“QoS”，指向“新建”，然后单击“字符串值”。</span><span class="sxs-lookup"><span data-stu-id="decb0-225">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="decb0-226">创建新注册表值后，键入 **"不使用 NLA"，** 然后按 Enter 重命名该值。</span><span class="sxs-lookup"><span data-stu-id="decb0-226">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="decb0-227">双击“不使用 NLA”。</span><span class="sxs-lookup"><span data-stu-id="decb0-227">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="decb0-228">在 **"编辑字符串**"对话框中，在"值"数据框中键入 **1，** 然后单击"**确定"。**</span><span class="sxs-lookup"><span data-stu-id="decb0-228">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

7.  <span data-ttu-id="decb0-229">关闭注册表编辑器并引导计算机。</span><span class="sxs-lookup"><span data-stu-id="decb0-229">Close the Registry Editor and eboot your computer.</span></span>

### <a name="configure-quality-of-service-on-computers-with-multiple-network-adapters"></a><span data-ttu-id="decb0-230">在具有多个网络适配器的计算机上配置服务质量</span><span class="sxs-lookup"><span data-stu-id="decb0-230">Configure Quality of Service on computers with multiple network adapters</span></span>

<span data-ttu-id="decb0-231">如果计算机具有多个网络适配器，则有时可能会遇到 DSCP 值显示为 0x00 而不是配置值的问题。</span><span class="sxs-lookup"><span data-stu-id="decb0-231">If you have a computer that has multiple network adapters, you might occasionally run in to issues where DSCP values are shown as 0x00 rather than the configured value.</span></span> <span data-ttu-id="decb0-232">此错误通常会发生在一个或多个网络适配器无法访问 Active Directory 域的计算机上（例如，如果这些适配器用于专用网络）。</span><span class="sxs-lookup"><span data-stu-id="decb0-232">This will typically occur on computers where one or more of the network adapters are not able to access your Active Directory domain (for example, if these adapters are used for a private network).</span></span> <span data-ttu-id="decb0-233">如果出现这种情况，则将 DSCP 值标记为使这些适配器可以访问该域，但不会标记为使这些适配器无法访问该域。</span><span class="sxs-lookup"><span data-stu-id="decb0-233">In cases like that, DSCP values will be tagged for the adapters that can access the domain, but will not be tagged for adapters that cannot access the domain.</span></span>

<span data-ttu-id="decb0-234">如果要标记计算机中所有网络适配器（包括无法访问域的适配器）的 DSCP 值，则需要在注册表中添加和配置值。</span><span class="sxs-lookup"><span data-stu-id="decb0-234">If you would like to tag DSCP values for all the network adapters in a computer, including adapters that do not have access to your domain, you will need to add and configure a value to the registry.</span></span> <span data-ttu-id="decb0-235">这可通过执行下列过程来完成：</span><span class="sxs-lookup"><span data-stu-id="decb0-235">That can be done by completing the following procedure:</span></span>

1.  <span data-ttu-id="decb0-236">单击“开始”，然后单击“运行”。</span><span class="sxs-lookup"><span data-stu-id="decb0-236">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="decb0-237">在 **"运行** "对话框中，键入 **regedit，** 然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="decb0-237">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="decb0-238">在注册表编辑器中，展开 **HKEY \_ LOCAL \_ MACHINE，** 展开 **系统**，展开 **CurrentControlSet，** 展开 **服务**，然后展开 **Tcpip。**</span><span class="sxs-lookup"><span data-stu-id="decb0-238">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="decb0-239">如果没有看到标记为“QoS”的注册表项，则右键单击“Tcpip”，指向“新建”，然后单击“项”。</span><span class="sxs-lookup"><span data-stu-id="decb0-239">If you do not see a registry key labeled **QoS** then right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="decb0-240">创建新密钥后，键入 **QoS，** 然后按 Enter 重命名该密钥。</span><span class="sxs-lookup"><span data-stu-id="decb0-240">After the new key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="decb0-241">右键单击“QoS”，指向“新建”，然后单击“字符串值”。</span><span class="sxs-lookup"><span data-stu-id="decb0-241">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="decb0-242">创建新注册表值后，键入 **"不使用 NLA"，** 然后按 Enter 重命名该值。</span><span class="sxs-lookup"><span data-stu-id="decb0-242">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="decb0-243">双击“不使用 NLA”。</span><span class="sxs-lookup"><span data-stu-id="decb0-243">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="decb0-244">在 **"编辑字符串**"对话框中，在"值"数据框中键入 **1，** 然后单击"**确定"。**</span><span class="sxs-lookup"><span data-stu-id="decb0-244">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

<span data-ttu-id="decb0-245">创建并配置新注册表值后，需要重新启动计算机，更改才能生效。</span><span class="sxs-lookup"><span data-stu-id="decb0-245">After creating and configuring the new registry value, you will need to reboot your computer for the changes to take effect.</span></span>

## <a name="see-also"></a><span data-ttu-id="decb0-246">另请参阅</span><span class="sxs-lookup"><span data-stu-id="decb0-246">See also</span></span>

[<span data-ttu-id="decb0-247">在 Windows 10 中创建组策略对象</span><span class="sxs-lookup"><span data-stu-id="decb0-247">Create a Group Policy Object in Windows 10</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)
