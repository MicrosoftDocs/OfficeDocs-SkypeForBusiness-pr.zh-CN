---
title: Lync Server 2013：返回 A/V 边缘服务器配置信息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Return A/V Edge Server configuration information
ms:assetid: b041f5a4-2387-4075-846c-ec4f99640903
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721850(v=OCS.15)
ms:contentKeyID: 49733783
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b73a6460b6045d5f1f2e35afcf91af0ebdd9e2b9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511379"
---
# <a name="return-av-edge-server-configuration-information-in-lync-server-2013"></a><span data-ttu-id="10f90-102">在 Lync Server 2013 中返回 A/V 边缘服务器配置信息</span><span class="sxs-lookup"><span data-stu-id="10f90-102">Return A/V Edge Server configuration information in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="10f90-103">_**上次修改的主题：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="10f90-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="10f90-p101">A/V 边缘服务为您的内部用户（已登录到您的组织网络的用户）提供一种与外部用户（未登录到您的组织网络的用户）共享音频和视频的方法。A/V 边缘服务主要通过使用 A/V 边缘配置设置进行管理，即可在站点范围或服务范围进行配置（也就是，可以针对个别 A/V 边缘服务器进行配置）的设置。</span><span class="sxs-lookup"><span data-stu-id="10f90-p101">The A/V Edge service provide a way for your internal users (users who are logged on to your organizational network) to share audio and video with external users (users who are not logged on to your organizational network). The A/V Edge service is primarily managed by using A/V Edge configuration settings, setting that can be configured at the site scope or at the service scope (that is, can be configured for an individual A/V Edge server).</span></span>

<span data-ttu-id="10f90-106">若要返回有关组织中使用的 A/V 边缘配置设置的信息，必须使用 Windows PowerShell 和 Get-CsAVEdgeConfiguration cmdlet。</span><span class="sxs-lookup"><span data-stu-id="10f90-106">To return information about the A/V Edge configuration settings in use in your organization, you must use Windows PowerShell and the Get-CsAVEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="10f90-107">有关详细信息，请参阅 [CsAVEdgeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsAVEdgeConfiguration) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="10f90-107">For more information, see the help topic for the [Get-CsAVEdgeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsAVEdgeConfiguration) cmdlet.</span></span>

<span data-ttu-id="10f90-108">从 Get-CsAVEdgeConfiguration cmdlet 返回的信息将看起来与以下类似：</span><span class="sxs-lookup"><span data-stu-id="10f90-108">Information returned from the Get-CsAVEdgeConfiguration cmdlet will look similar to this:</span></span>

    Identity              : Global
    MaxTokenLifetime      : 08:00:00
    MaxBandwidthPerUserKb : 10000
    MaxBandwidthPerPortKb : 3000

<div>

## <a name="to-return-information-for-all-your-av-edge-configuration-settings"></a><span data-ttu-id="10f90-109">返回所有 A/V 边缘配置设置的信息</span><span class="sxs-lookup"><span data-stu-id="10f90-109">To return information for all your A/V Edge configuration settings</span></span>

  - <span data-ttu-id="10f90-110">以下命令会返回有关您的组织中使用的所有 A/V 边缘配置设置的信息：</span><span class="sxs-lookup"><span data-stu-id="10f90-110">The following command returns information about all the A/V Edge configuration settings currently in use in your organization:</span></span>
    
        Get-CsAVEdgeConfiguration

</div>

<div>

## <a name="to-return-information-for-site-scoped-av-edge-configuration-settings"></a><span data-ttu-id="10f90-111">返回网站范围内的 A/V 边缘配置设置的信息</span><span class="sxs-lookup"><span data-stu-id="10f90-111">To return information for site-scoped A/V Edge configuration settings</span></span>

  - <span data-ttu-id="10f90-p103">要返回有关特定的 A/V 边缘配置设置集合的信息，请在运行 Get-CsAVEdgeConfiguration cmdlet 时指定该集合的 Identity。例如，以下命令仅返回应用到 Redmond 站点的设置的信息：</span><span class="sxs-lookup"><span data-stu-id="10f90-p103">To return information about a specific collection of A/V Edge configuration settings, specify the Identity of that collection when running the Get-CsAVEdgeConfiguration cmdlet. For example, this command returns information only for the settings applied to the Redmond site:</span></span>
    
        Get-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-return-information-for-service-scoped-av-edge-configuration-settings"></a><span data-ttu-id="10f90-114">返回服务范围的 A/V 边缘配置设置的信息</span><span class="sxs-lookup"><span data-stu-id="10f90-114">To return information for service-scoped A/V Edge configuration settings</span></span>

  - <span data-ttu-id="10f90-115">以下命令仅返回应用到特定 A/V 边缘服务器的设置的信息：</span><span class="sxs-lookup"><span data-stu-id="10f90-115">And this command returns information only for settings applied the a specific A/V Edge server:</span></span>
    
        Get-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="10f90-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="10f90-116">See Also</span></span>


[<span data-ttu-id="10f90-117">在 Lync Server 2013 中创建或修改 A/V 边缘服务器配置设置的集合</span><span class="sxs-lookup"><span data-stu-id="10f90-117">Create or modify a collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  
[<span data-ttu-id="10f90-118">在 Lync Server 2013 中删除 A/V 边缘服务器配置设置的现有集合</span><span class="sxs-lookup"><span data-stu-id="10f90-118">Delete an existing collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  


[<span data-ttu-id="10f90-119">Lync Server 2013 中的音频/视频 (A/V) 边缘服务器</span><span class="sxs-lookup"><span data-stu-id="10f90-119">Audio/Video (A/V) Edge Servers in Lync Server 2013</span></span>](lync-server-2013-audio-video-a-v-edge-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

