---
title: 配置客户端的端口范围和的服务质量策略
ms.reviewer: ''
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204760(v=OCS.15)
ms:contentKeyID: 48183694
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 本文介绍如何配置端口范围为您的客户端和 Skype 中的配置服务质量策略业务服务器上 Windows 10 运行的客户端。
ms.openlocfilehash: 9377274b625af7a4ed93b46a0f6a741e89eee1eb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33913067"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-clients-in-skype-for-business-server"></a><span data-ttu-id="661ce-103">配置端口范围和客户端中的业务服务器 Skype 的服务质量策略</span><span class="sxs-lookup"><span data-stu-id="661ce-103">Configuring port ranges and a Quality of Service policy for your clients in Skype for Business Server</span></span>

<span data-ttu-id="661ce-104">本文介绍如何配置端口范围为您的客户端和 Skype 中的配置服务质量策略业务服务器上 Windows 10 运行的客户端。</span><span class="sxs-lookup"><span data-stu-id="661ce-104">This article describes how to configure port ranges for your clients and configuring Quality of Service policies in Skype for Business Server for clients running on Windows 10.</span></span>

## <a name="configure-port-ranges"></a><span data-ttu-id="661ce-105">配置端口范围</span><span class="sxs-lookup"><span data-stu-id="661ce-105">Configure port ranges</span></span>

<span data-ttu-id="661ce-106">默认情况下 Skype 业务客户端应用程序可以使用之间的任何端口的端口 1024年和 65535 之间时涉及的通信会话;这是因为客户端未自动启用特定的端口范围。</span><span class="sxs-lookup"><span data-stu-id="661ce-106">By default, Skype for Business client applications can use any port between ports 1024 and 65535 when involved in a communication session; this is because specific port ranges are not automatically enabled for clients.</span></span> <span data-ttu-id="661ce-107">若要使用的服务质量，但是，您需要将各种通信类型 （音频、 视频、 媒体、 应用程序共享和文件传输） 重新分配到一系列唯一的端口范围。</span><span class="sxs-lookup"><span data-stu-id="661ce-107">In order to use Quality of Service, however, you will need to reassign the various traffic types (audio, video, media, application sharing, and file transfer) to a series of unique port ranges.</span></span> <span data-ttu-id="661ce-108">这可以通过使用 Set-csconferencingconfiguration cmdlet。</span><span class="sxs-lookup"><span data-stu-id="661ce-108">This can be done by using the Set-CsConferencingConfiguration cmdlet.</span></span>

> [!NOTE]  
> <span data-ttu-id="661ce-109">最终用户无法进行这些更改本身。</span><span class="sxs-lookup"><span data-stu-id="661ce-109">End users cannot make these changes themselves.</span></span> <span data-ttu-id="661ce-110">端口更改仅可通过使用 Set-csconferencingconfiguration cmdlet 的管理员。</span><span class="sxs-lookup"><span data-stu-id="661ce-110">Port changes can only be made by administrators using the Set-CsConferencingConfiguration cmdlet.</span></span>


<span data-ttu-id="661ce-111">您可以确定哪些端口范围当前正在使用的通信会话的业务 Server Management Shell 中运行以下命令从 Skype 中：</span><span class="sxs-lookup"><span data-stu-id="661ce-111">You can determine which port ranges are currently used for communication sessions by running the following command from within the Skype for Business Server Management Shell:</span></span>

    Get-CsConferencingConfiguration

<span data-ttu-id="661ce-112">假定具有尚未对会议设置进行任何更改，因为业务服务器安装 Skype，应获得包括这些属性值的信息：</span><span class="sxs-lookup"><span data-stu-id="661ce-112">Assuming that you have not made any changes to your conferencing settings since you installed Skype for Business Server, you should get back information that includes these property values:</span></span>

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

<span data-ttu-id="661ce-113">仔细查看上述输出中，如果您将看到以下两项的重要性。</span><span class="sxs-lookup"><span data-stu-id="661ce-113">If you look closely at the preceding output, you'll see two things of importance.</span></span> <span data-ttu-id="661ce-114">首先，ClientMediaPortRangeEnabled 属性设置为 False:</span><span class="sxs-lookup"><span data-stu-id="661ce-114">First, the ClientMediaPortRangeEnabled property is set to False:</span></span>

    ClientMediaPortRangeEnabled : False

<span data-ttu-id="661ce-115">这是重要的因为当此属性设置为 False，Skype 业务客户端将使用之间的任何可用的端口的端口 1024年和 65535 之间时涉及的通信会话;这是无论任何其他端口设置 （例如，ClientMediaPort 或 ClientVideoPort），则返回 true。</span><span class="sxs-lookup"><span data-stu-id="661ce-115">That's important because, when this property is set to False, Skype for Business clients will use any available port between ports 1024 and 65535 when involved in a communication session; this is true regardless of any other port settings (for example, ClientMediaPort or ClientVideoPort).</span></span> <span data-ttu-id="661ce-116">如果您想要将使用率限制为一组指定的端口 （这是您想要执行操作，如果您计划实现服务质量），然后必须先启用客户端媒体端口范围。</span><span class="sxs-lookup"><span data-stu-id="661ce-116">If you want to restrict usage to a specified set of ports (and this is something you do want to do if you plan on implementing Quality of Service), then you must first enable client media port ranges.</span></span> <span data-ttu-id="661ce-117">可以完成的使用以下 Windows PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="661ce-117">That can be done using the following Windows PowerShell command:</span></span>

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

<span data-ttu-id="661ce-118">上述命令允许客户端的会议配置设置; 的全局集合的媒体端口范围但是，也可以将这些设置应用于站点作用域和/或服务范围 （对于仅会议服务器服务）。</span><span class="sxs-lookup"><span data-stu-id="661ce-118">The preceding command enables client media port ranges for the global collection of conferencing configuration settings; however, these settings can also be applied to the site scope and/or the service scope (for the Conferencing Server service only).</span></span> <span data-ttu-id="661ce-119">若要启用客户端媒体端口范围为特定网站或服务器，指定该网站或服务器的标识，调用 Set-csconferencingconfiguration 时：</span><span class="sxs-lookup"><span data-stu-id="661ce-119">To enable client media port ranges for a specific site or server, specify the Identity of that site or server when calling Set-CsConferencingConfiguration:</span></span>

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

<span data-ttu-id="661ce-120">此外，您可以使用此命令同时为所有会议配置设置启用端口范围：</span><span class="sxs-lookup"><span data-stu-id="661ce-120">Alternatively, you can use this command to simultaneously enable port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

<span data-ttu-id="661ce-121">您将发现的另一个重要是重要性的，默认情况下的媒体端口范围为每种类型的网络流量，示例输出显示相同：</span><span class="sxs-lookup"><span data-stu-id="661ce-121">The second thing of importance you will notice is that the sample output shows that, by default, the media port ranges set for each type of network traffic are identical:</span></span>

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

<span data-ttu-id="661ce-122">为了实现 QoS，每个这些端口范围需要是唯一的。</span><span class="sxs-lookup"><span data-stu-id="661ce-122">In order to implement QoS, each of these port ranges will need to be unique.</span></span> <span data-ttu-id="661ce-123">例如，您可能配置如下所示的端口范围：</span><span class="sxs-lookup"><span data-stu-id="661ce-123">For example, you might configure the port ranges like this:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="661ce-124">客户端通信类型</span><span class="sxs-lookup"><span data-stu-id="661ce-124">Client Traffic Type</span></span></th>
<th><span data-ttu-id="661ce-125">起始端口</span><span class="sxs-lookup"><span data-stu-id="661ce-125">Port Start</span></span></th>
<th><span data-ttu-id="661ce-126">端口范围</span><span class="sxs-lookup"><span data-stu-id="661ce-126">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="661ce-127">音频</span><span class="sxs-lookup"><span data-stu-id="661ce-127">Audio</span></span></p></td>
<td><p><span data-ttu-id="661ce-128">50020</span><span class="sxs-lookup"><span data-stu-id="661ce-128">50020</span></span></p></td>
<td><p><span data-ttu-id="661ce-129">20</span><span class="sxs-lookup"><span data-stu-id="661ce-129">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="661ce-130">视频</span><span class="sxs-lookup"><span data-stu-id="661ce-130">Video</span></span></p></td>
<td><p><span data-ttu-id="661ce-131">58000</span><span class="sxs-lookup"><span data-stu-id="661ce-131">58000</span></span></p></td>
<td><p><span data-ttu-id="661ce-132">20</span><span class="sxs-lookup"><span data-stu-id="661ce-132">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="661ce-133">应用程序共享</span><span class="sxs-lookup"><span data-stu-id="661ce-133">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="661ce-134">42000</span><span class="sxs-lookup"><span data-stu-id="661ce-134">42000</span></span></p></td>
<td><p><span data-ttu-id="661ce-135">20</span><span class="sxs-lookup"><span data-stu-id="661ce-135">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="661ce-136">文件传输</span><span class="sxs-lookup"><span data-stu-id="661ce-136">File transfer</span></span></p></td>
<td><p><span data-ttu-id="661ce-137">42020</span><span class="sxs-lookup"><span data-stu-id="661ce-137">42020</span></span></p></td>
<td><p><span data-ttu-id="661ce-138">20</span><span class="sxs-lookup"><span data-stu-id="661ce-138">20</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="661ce-139">在前面的表中，客户端端口范围代表的服务器配置的端口范围的子集。</span><span class="sxs-lookup"><span data-stu-id="661ce-139">In the preceding table, client port ranges represent a subset of the port ranges configured for your servers.</span></span> <span data-ttu-id="661ce-140">例如，在服务器，应用程序共享已配置为使用端口 40803 到 49151;客户端计算机上应用程序共享被配置为使用通过 42019 42000 的端口。</span><span class="sxs-lookup"><span data-stu-id="661ce-140">For example, on the servers, application sharing was configured to use ports 40803 through 49151; on the client computers, application sharing is configured to use ports 42000 through 42019.</span></span> <span data-ttu-id="661ce-141">过，这是主要是为了便于管理的 QoS： 客户端端口不必代表的服务器上使用的端口的子集。</span><span class="sxs-lookup"><span data-stu-id="661ce-141">This, too, is done primarily to make administration of QoS easier: client ports do not have to represent a subset of the ports used on the server.</span></span> <span data-ttu-id="661ce-142">（例如，客户端计算机上您无法配置应用程序共享才能使用，请说，端口通过 10019 10000。）但是，建议您使您的客户端端口范围，您服务器端口范围的子集。</span><span class="sxs-lookup"><span data-stu-id="661ce-142">(For example, on the client computers you could configure application sharing to use, say, ports 10000 through 10019.) However, it is recommended that you make your client port ranges a subset of your server port ranges.</span></span>

<span data-ttu-id="661ce-143">此外，您可能已经注意到用于应用程序共享服务器、 留出设置 8348 端口，但仅 20 个端口已留在客户端上共享的应用程序。</span><span class="sxs-lookup"><span data-stu-id="661ce-143">In addition, you might have noticed that 8348 ports were set aside for application sharing on the servers, but only 20 ports were set aside for application sharing on the clients.</span></span> <span data-ttu-id="661ce-144">太，这建议，但不严格的规则。</span><span class="sxs-lookup"><span data-stu-id="661ce-144">This, too, is recommended, but is not a hard-and-fast rule.</span></span> <span data-ttu-id="661ce-145">一般情况下，可以考虑每个可用的端口，以表示单个通信会话： 如果您有 100 端口的端口范围，这意味着无法参与问题的计算机中, 可用，最多，100 个通信会话在任何给定时间。</span><span class="sxs-lookup"><span data-stu-id="661ce-145">In general, you can consider each available port to represent a single communication session: if you have 100 ports available in a port range, that means that the computer in question could participate in, at most, 100 communication sessions at any given time.</span></span> <span data-ttu-id="661ce-146">因为服务器很有可能会部件中与客户端的多个详细对话，所以应该打开许多比客户端上的服务器上的多个端口。</span><span class="sxs-lookup"><span data-stu-id="661ce-146">Because servers will likely take part in many more conversations than clients, it makes sense to open many more ports on servers than on clients.</span></span> <span data-ttu-id="661ce-147">设置客户端上共享的应用程序的备用 20 个端口是指用户无法参与 20 应用程序共享会话，在指定的设备，以及所有同时。</span><span class="sxs-lookup"><span data-stu-id="661ce-147">Setting aside 20 ports for application sharing on a client means that a user could participate in 20 application sharing sessions on the specified device, and all at the same time.</span></span> <span data-ttu-id="661ce-148">应证明足以绝大多数您的用户。</span><span class="sxs-lookup"><span data-stu-id="661ce-148">That should prove sufficient for the vast majority of your users.</span></span>

<span data-ttu-id="661ce-149">要为您的会议配置设置的全局集合分配上述端口范围，可以使用以下 Skype 业务 Server 命令行管理程序命令：</span><span class="sxs-lookup"><span data-stu-id="661ce-149">To assign the preceding port ranges to your global collection of conferencing configuration settings, you can use the following Skype for Business Server Management Shell command:</span></span>

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="661ce-150">或者，使用此命令分配这些相同的端口范围，您的所有会议配置设置：</span><span class="sxs-lookup"><span data-stu-id="661ce-150">Or, use this command to assign these same port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="661ce-151">单个用户必须从 for Business 的 Skype 注销，然后重新登录，才能实际使这些更改生效。</span><span class="sxs-lookup"><span data-stu-id="661ce-151">Individual users must log off from Skype for Business and then log back on before these changes will actually take effect.</span></span>

> [!NOTE]  
> <span data-ttu-id="661ce-152">您可以还启用客户端媒体端口范围，并将这些端口范围，使用单个命令。</span><span class="sxs-lookup"><span data-stu-id="661ce-152">You can also enable client media port ranges, and then assign those port ranges, using a single command.</span></span> <span data-ttu-id="661ce-153">例如：</span><span class="sxs-lookup"><span data-stu-id="661ce-153">For example:</span></span><BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>

## <a name="configure-quality-of-service-policies-for-clients-running-on-windows-10"></a><span data-ttu-id="661ce-154">在 Windows 10 上运行的客户端配置服务质量策略</span><span class="sxs-lookup"><span data-stu-id="661ce-154">Configure Quality of Service policies for clients running on Windows 10</span></span>

<span data-ttu-id="661ce-155">除了指定供您 Skype 业务客户端使用的端口范围，您还必须创建单独的服务质量策略将应用于客户端计算机。</span><span class="sxs-lookup"><span data-stu-id="661ce-155">In addition to specifying port ranges for use by your Skype for Business clients, you must also create separate Quality of Service policies that will be applied to client computers.</span></span> <span data-ttu-id="661ce-156">（创建会议、 应用程序和中介服务器的服务质量策略应该不应用到客户端计算机。）此信息仅适用于运行 Skype 业务客户端和 Windows 10 的计算机。</span><span class="sxs-lookup"><span data-stu-id="661ce-156">(The Quality of Service policies created for Conferencing, Application, and Mediation servers should not be applied to client computers.) This information applies only to computers running the Skype for Business client and Windows 10.</span></span>

<span data-ttu-id="661ce-157">下面的示例使用此端口范围的设置创建音频策略和视频策略：</span><span class="sxs-lookup"><span data-stu-id="661ce-157">The following example uses this set of port ranges to create an audio policy and a video policy:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="661ce-158">客户端通信类型</span><span class="sxs-lookup"><span data-stu-id="661ce-158">Client Traffic Type</span></span></th>
<th><span data-ttu-id="661ce-159">起始端口</span><span class="sxs-lookup"><span data-stu-id="661ce-159">Port Start</span></span></th>
<th><span data-ttu-id="661ce-160">端口范围</span><span class="sxs-lookup"><span data-stu-id="661ce-160">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="661ce-161">音频</span><span class="sxs-lookup"><span data-stu-id="661ce-161">Audio</span></span></p></td>
<td><p><span data-ttu-id="661ce-162">50020</span><span class="sxs-lookup"><span data-stu-id="661ce-162">50020</span></span></p></td>
<td><p><span data-ttu-id="661ce-163">20</span><span class="sxs-lookup"><span data-stu-id="661ce-163">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="661ce-164">视频</span><span class="sxs-lookup"><span data-stu-id="661ce-164">Video</span></span></p></td>
<td><p><span data-ttu-id="661ce-165">58000</span><span class="sxs-lookup"><span data-stu-id="661ce-165">58000</span></span></p></td>
<td><p><span data-ttu-id="661ce-166">20</span><span class="sxs-lookup"><span data-stu-id="661ce-166">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="661ce-167">应用程序共享</span><span class="sxs-lookup"><span data-stu-id="661ce-167">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="661ce-168">42000</span><span class="sxs-lookup"><span data-stu-id="661ce-168">42000</span></span></p></td>
<td><p><span data-ttu-id="661ce-169">20</span><span class="sxs-lookup"><span data-stu-id="661ce-169">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="661ce-170">文件传输</span><span class="sxs-lookup"><span data-stu-id="661ce-170">File transfer</span></span></p></td>
<td><p><span data-ttu-id="661ce-171">42020</span><span class="sxs-lookup"><span data-stu-id="661ce-171">42020</span></span></p></td>
<td><p><span data-ttu-id="661ce-172">20</span><span class="sxs-lookup"><span data-stu-id="661ce-172">20</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="661ce-173">若要创建 Windows 10 计算机音频质量的服务策略，首次登录到计算机上已安装组策略管理。</span><span class="sxs-lookup"><span data-stu-id="661ce-173">To create a Quality of Service audio policy for Windows 10 computers, first log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="661ce-174">打开组策略管理 （单击**开始**、**管理工具**，，然后单击**组策略管理**），然后完成以下过程：</span><span class="sxs-lookup"><span data-stu-id="661ce-174">Open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**), and then complete the following procedure:</span></span>

1.  <span data-ttu-id="661ce-175">在组策略管理中，找到应在其中创建新策略的容器。</span><span class="sxs-lookup"><span data-stu-id="661ce-175">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="661ce-176">例如，如果您的所有客户端计算机位于名为客户端 OU，应客户端 OU 中创建新策略。</span><span class="sxs-lookup"><span data-stu-id="661ce-176">For example, if all your client computers are located in an OU named Clients, the new policy should be created in the Client OU.</span></span>

2.  <span data-ttu-id="661ce-177">右键单击相应的容器，然后单击**创建在这个域 GPO 并在此处链接**。</span><span class="sxs-lookup"><span data-stu-id="661ce-177">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="661ce-178">**新建 GPO**对话框中，在**名称**框中，键入新的组策略对象的名称，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="661ce-178">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box, and then click **OK**.</span></span>

4.  <span data-ttu-id="661ce-179">右键单击新创建的策略，然后单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="661ce-179">Right-click the newly-created policy, and then click **Edit**.</span></span>

5.  <span data-ttu-id="661ce-180">在组策略管理编辑器中，展开**计算机配置**，展开**Windows 设置**、**基于策略的 QoS**，右键单击，然后单击**新建策略**。</span><span class="sxs-lookup"><span data-stu-id="661ce-180">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6.  <span data-ttu-id="661ce-181">在**基于策略的 QoS**对话框中，在打开页上，键入**名称**框中的新策略的名称。</span><span class="sxs-lookup"><span data-stu-id="661ce-181">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy in the **Name** box.</span></span> <span data-ttu-id="661ce-182">选择**指定 DSCP 值**并将值设置为**46**。</span><span class="sxs-lookup"><span data-stu-id="661ce-182">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="661ce-183">保留未选择，**指定出站调节率**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="661ce-183">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7.  <span data-ttu-id="661ce-184">在下一页上，确保选中**所有应用程序**，，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="661ce-184">On the next page, make sure that **All applications** is selected, and then click **Next**.</span></span> <span data-ttu-id="661ce-185">此设置指示网络以查找所有包的特定应用程序创建的 46，而不仅仅是数据包的 DSCP 标记。</span><span class="sxs-lookup"><span data-stu-id="661ce-185">This setting instructs the network to look for all packets with a DSCP marking of 46, not just packets created by a specific application.</span></span>

8.  <span data-ttu-id="661ce-186">在第三页上，确保同时**任何源 IP 地址**和**任何目标 IP 地址**选中，则，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="661ce-186">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="661ce-187">这两个设置确保将管理数据包而不考虑哪台计算机 （IP 地址） 发送这些数据包和哪台计算机 （IP 地址） 将接收这些数据包。</span><span class="sxs-lookup"><span data-stu-id="661ce-187">These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

9.  <span data-ttu-id="661ce-188">在第四页中，从**选择此 QoS 策略应用于的协议**下拉列表中选择**TCP 和 UDP** 。</span><span class="sxs-lookup"><span data-stu-id="661ce-188">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="661ce-189">TCP （传输控制协议） 和 UDP （用户数据报协议） 是最常使用的业务服务器和其客户端应用程序的 Skype 的两个网络协议。</span><span class="sxs-lookup"><span data-stu-id="661ce-189">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Skype for Business Server and its client applications.</span></span>

10. <span data-ttu-id="661ce-190">在标题下**指定源端口号**，**从此源端口或范围**中进行选择。</span><span class="sxs-lookup"><span data-stu-id="661ce-190">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="661ce-191">在相应的文本框中，键入供音频传输的端口范围。</span><span class="sxs-lookup"><span data-stu-id="661ce-191">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="661ce-192">例如，如果预留端口 50020 通过端口 50039 音频流量输入使用以下格式的端口范围： **50020:50039**。</span><span class="sxs-lookup"><span data-stu-id="661ce-192">For example, if you reserved ports 50020 through ports 50039 for audio traffic enter the port range using this format: **50020:50039**.</span></span> <span data-ttu-id="661ce-193">单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="661ce-193">Click **Finish**.</span></span>

<span data-ttu-id="661ce-194">创建音频 QoS 策略后您随后应创建视频的第二个策略。</span><span class="sxs-lookup"><span data-stu-id="661ce-194">After you have created the QoS policy for audio you should then create a second policy for video.</span></span> <span data-ttu-id="661ce-195">若要创建视频的策略，请按照相同的基本过程您遵循创建音频策略时, 进行下列替换项操作：</span><span class="sxs-lookup"><span data-stu-id="661ce-195">To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="661ce-196">使用其他 （及唯一） 策略名称。</span><span class="sxs-lookup"><span data-stu-id="661ce-196">Use a different (and unique) policy name.</span></span>

  - <span data-ttu-id="661ce-197">设置为**34**而不是 46 的 DSCP 值。</span><span class="sxs-lookup"><span data-stu-id="661ce-197">Set the DSCP value to **34** instead of 46.</span></span> <span data-ttu-id="661ce-198">（如前所述，您无需使用的 DSCP 值 34; 您只需必须分配比音频所使用的是不同的 DSCP 值。）</span><span class="sxs-lookup"><span data-stu-id="661ce-198">(As noted previously, you do not have to use the DSCP value 34; you simply must assign a different DSCP value than the one used for audio.)</span></span>

  - <span data-ttu-id="661ce-199">使用视频流量的以前配置的端口范围。</span><span class="sxs-lookup"><span data-stu-id="661ce-199">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="661ce-200">例如，如果您保留了通过 58019 视频的端口 58000，设置为此的端口范围： **58000:58019**。</span><span class="sxs-lookup"><span data-stu-id="661ce-200">For example, if you have reserved ports 58000 through 58019 for video, set the port range to this: **58000:58019**.</span></span>

<span data-ttu-id="661ce-201">如果您决定创建用于管理应用程序共享流量的策略，请进行下列替换项：</span><span class="sxs-lookup"><span data-stu-id="661ce-201">If you decide to create a policy for managing application sharing traffic, make these substitutions:</span></span>

  - <span data-ttu-id="661ce-202">使用其他 （及唯一） 策略名称 (例如，**业务服务器应用程序共享的 Skype**)。</span><span class="sxs-lookup"><span data-stu-id="661ce-202">Use a different (and unique) policy name (for example, **Skype for Business Server Application Sharing**).</span></span>

  - <span data-ttu-id="661ce-203">设置为**24**而不是 46 的 DSCP 值。</span><span class="sxs-lookup"><span data-stu-id="661ce-203">Set the DSCP value to **24** instead of 46.</span></span> <span data-ttu-id="661ce-204">（同样，此值没有为 24; 它只是必须使用音频和视频的 DSCP 值以外的其他。）</span><span class="sxs-lookup"><span data-stu-id="661ce-204">(Again, this value does not have to be 24; it simply must be different than the DSCP values used for audio and for video.)</span></span>

  - <span data-ttu-id="661ce-205">使用视频流量的以前配置的端口范围。</span><span class="sxs-lookup"><span data-stu-id="661ce-205">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="661ce-206">例如，如果您保留了通过应用程序共享 42019 端口 42000，设置为此的端口范围： **42000:42019**。</span><span class="sxs-lookup"><span data-stu-id="661ce-206">For example, if you have reserved ports 42000 through 42019 for application sharing, set the port range to this: **42000:42019**.</span></span>

<span data-ttu-id="661ce-207">文件传输策略：</span><span class="sxs-lookup"><span data-stu-id="661ce-207">For a file transfer policy:</span></span>

  - <span data-ttu-id="661ce-208">使用其他 （及唯一） 策略名称 (例如，**业务 Server 文件传输的 Skype**)。</span><span class="sxs-lookup"><span data-stu-id="661ce-208">Use a different (and unique) policy name (for example, **Skype for Business Server File Transfers**).</span></span>

  - <span data-ttu-id="661ce-209">DSCP 值设置为**14**。</span><span class="sxs-lookup"><span data-stu-id="661ce-209">Set the DSCP value to **14**.</span></span> <span data-ttu-id="661ce-210">（同样，此值没有为 14; 它只是必须是唯一的 DSCP 代码。）</span><span class="sxs-lookup"><span data-stu-id="661ce-210">(Again, this value does not have to be 14; it simply must be a unique DSCP code.)</span></span>

  - <span data-ttu-id="661ce-211">对应用程序中使用以前配置的端口范围。</span><span class="sxs-lookup"><span data-stu-id="661ce-211">Use the previously configured port range for application.</span></span> <span data-ttu-id="661ce-212">例如，如果您保留了通过应用程序共享 42039 端口 42020，设置为此的端口范围： **42020:42039**。</span><span class="sxs-lookup"><span data-stu-id="661ce-212">For example, if you have reserved ports 42020 through 42039 for application sharing, set the port range to this: **42020:42039**.</span></span>

<span data-ttu-id="661ce-213">组策略已在客户端计算机上刷新，已创建的新策略才会生效。</span><span class="sxs-lookup"><span data-stu-id="661ce-213">The new policies you have created will not take effect until Group Policy has been refreshed on your client computers.</span></span> <span data-ttu-id="661ce-214">尽管组策略会自己定期刷新，但你可以在需要刷新组策略的每台计算机上运行以下命令，强制立即刷新：</span><span class="sxs-lookup"><span data-stu-id="661ce-214">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpudate.exe /force

<span data-ttu-id="661ce-215">此命令可以从在管理员凭据下运行的任何命令窗口运行。</span><span class="sxs-lookup"><span data-stu-id="661ce-215">This command can be run from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="661ce-216">若要在管理员凭据下运行命令窗口，请单击“**开始**”，右键单击“**命令提示符**”，然后单击“**以管理员身份运行**”。</span><span class="sxs-lookup"><span data-stu-id="661ce-216">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

<span data-ttu-id="661ce-217">请记住这些策略应面向客户端计算机。</span><span class="sxs-lookup"><span data-stu-id="661ce-217">Keep in mind that these policies should be targeted towards your client computers.</span></span> <span data-ttu-id="661ce-218">它们应不会应用到业务服务器运行 Skype 的服务器。</span><span class="sxs-lookup"><span data-stu-id="661ce-218">They should not be applied to servers running Skype for Business Server.</span></span>

<span data-ttu-id="661ce-219">为了帮助确保使用适当的 DSCP 值标记网络数据包，，还应通过完成以下过程在每台计算机上创建新的注册表项：</span><span class="sxs-lookup"><span data-stu-id="661ce-219">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="661ce-220">单击 **“开始”**，然后单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="661ce-220">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="661ce-221">在**运行**对话框中，键入**regedit**，，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="661ce-221">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="661ce-222">在注册表编辑器中，展开**HKEY\_本地\_计算机**，展开**系统**，展开**CurrentControlSet**，展开**服务**，然后展开**Tcpip**。</span><span class="sxs-lookup"><span data-stu-id="661ce-222">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="661ce-223">右键单击**Tcpip**，指向**新建**，，然后单击**项**。</span><span class="sxs-lookup"><span data-stu-id="661ce-223">Right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="661ce-224">创建新的注册表项后，键入**QoS**，，，然后按 ENTER 以重命名该项。</span><span class="sxs-lookup"><span data-stu-id="661ce-224">After the new registry key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="661ce-225">右键单击**QoS**，指向**新建**，，然后单击**字符串值**。</span><span class="sxs-lookup"><span data-stu-id="661ce-225">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="661ce-226">创建新的注册表值后，键入**不使用 NLA**，，，然后按 ENTER 以重命名该值。</span><span class="sxs-lookup"><span data-stu-id="661ce-226">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="661ce-227">双击**不使用 NLA**。</span><span class="sxs-lookup"><span data-stu-id="661ce-227">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="661ce-228">**编辑字符串**对话框中，在**值数据**框中，键入**1** ，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="661ce-228">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

7.  <span data-ttu-id="661ce-229">关闭注册表编辑器和 eboot 您的计算机。</span><span class="sxs-lookup"><span data-stu-id="661ce-229">Close the Registry Editor and eboot your computer.</span></span>

### <a name="configure-quality-of-service-on-computers-with-multiple-network-adapters"></a><span data-ttu-id="661ce-230">在具有多个网络适配器的计算机上配置服务质量</span><span class="sxs-lookup"><span data-stu-id="661ce-230">Configure Quality of Service on computers with multiple network adapters</span></span>

<span data-ttu-id="661ce-231">如果您有多个网络适配器的计算机，您可能会偶尔中运行 DSCP 值所示 0x00 的问题，而不是所配置的值。</span><span class="sxs-lookup"><span data-stu-id="661ce-231">If you have a computer that has multiple network adapters, you might occasionally run in to issues where DSCP values are shown as 0x00 rather than the configured value.</span></span> <span data-ttu-id="661ce-232">这通常会不能够访问您的 Active Directory 域 （例如，如果这些适配器均被使用专用网络） 一个或多个网络适配器的计算机上。</span><span class="sxs-lookup"><span data-stu-id="661ce-232">This will typically occur on computers where one or more of the network adapters are not able to access your Active Directory domain (for example, if these adapters are used for a private network).</span></span> <span data-ttu-id="661ce-233">在这样的情况下，DSCP 值标记的适配器的可以访问域，但不是将无法访问域的适配器将标记。</span><span class="sxs-lookup"><span data-stu-id="661ce-233">In cases like that, DSCP values will be tagged for the adapters that can access the domain, but will not be tagged for adapters that cannot access the domain.</span></span>

<span data-ttu-id="661ce-234">如果您想要包括到您的域，无权访问的适配器的计算机中的所有网络适配器的标记 DSCP 值您需要添加并配置对注册表值。</span><span class="sxs-lookup"><span data-stu-id="661ce-234">If you would like to tag DSCP values for all the network adapters in a computer, including adapters that do not have access to your domain, you will need to add and configure a value to the registry.</span></span> <span data-ttu-id="661ce-235">可通过完成以下过程：</span><span class="sxs-lookup"><span data-stu-id="661ce-235">That can be done by completing the following procedure:</span></span>

1.  <span data-ttu-id="661ce-236">单击 **“开始”**，然后单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="661ce-236">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="661ce-237">在**运行**对话框中，键入**regedit**，，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="661ce-237">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="661ce-238">在注册表编辑器中，展开**HKEY\_本地\_计算机**，展开**系统**，展开**CurrentControlSet**，展开**服务**，然后展开**Tcpip**。</span><span class="sxs-lookup"><span data-stu-id="661ce-238">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="661ce-239">如果看不到标记**QoS** ，然后右键单击**Tcpip**注册表项，指向**新建**，，然后单击**项**。</span><span class="sxs-lookup"><span data-stu-id="661ce-239">If you do not see a registry key labeled **QoS** then right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="661ce-240">创建新密钥后，键入**QoS**，，，然后按 ENTER 以重命名该项。</span><span class="sxs-lookup"><span data-stu-id="661ce-240">After the new key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="661ce-241">右键单击**QoS**，指向**新建**，，然后单击**字符串值**。</span><span class="sxs-lookup"><span data-stu-id="661ce-241">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="661ce-242">创建新的注册表值后，键入**不使用 NLA**，，，然后按 ENTER 以重命名该值。</span><span class="sxs-lookup"><span data-stu-id="661ce-242">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="661ce-243">双击**不使用 NLA**。</span><span class="sxs-lookup"><span data-stu-id="661ce-243">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="661ce-244">**编辑字符串**对话框中，在**值数据**框中，键入**1** ，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="661ce-244">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

<span data-ttu-id="661ce-245">创建并配置新的注册表值之后, 将需要重新启动计算机以使更改生效。</span><span class="sxs-lookup"><span data-stu-id="661ce-245">After creating and configuring the new registry value, you will need to reboot your computer for the changes to take effect.</span></span>

## <a name="see-also"></a><span data-ttu-id="661ce-246">另请参阅</span><span class="sxs-lookup"><span data-stu-id="661ce-246">See also</span></span>

[<span data-ttu-id="661ce-247">在 Windows 10 中创建组策略对象</span><span class="sxs-lookup"><span data-stu-id="661ce-247">Create a Group Policy Object in Windows 10</span></span>](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)
