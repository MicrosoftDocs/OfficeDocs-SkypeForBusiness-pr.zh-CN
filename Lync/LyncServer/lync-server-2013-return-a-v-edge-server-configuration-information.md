---
title: 'Lync Server 2013: 返回 A/V 边缘服务器配置信息'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Return A/V Edge Server configuration information
ms:assetid: b041f5a4-2387-4075-846c-ec4f99640903
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721850(v=OCS.15)
ms:contentKeyID: 49733783
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 15096099184525890328dbe1c89d891487b46d87
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822361"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="return-av-edge-server-configuration-information-in-lync-server-2013"></a><span data-ttu-id="212bd-102">返回 Lync Server 2013 中的 A/V 边缘服务器配置信息</span><span class="sxs-lookup"><span data-stu-id="212bd-102">Return A/V Edge Server configuration information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="212bd-103">_**主题上次修改时间:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="212bd-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="212bd-104">A/V 边缘服务为内部用户 (登录到你的组织网络的用户) 提供一种方法, 以便与外部用户 (未登录到你的组织网络的用户) 共享音频和视频。</span><span class="sxs-lookup"><span data-stu-id="212bd-104">The A/V Edge service provide a way for your internal users (users who are logged on to your organizational network) to share audio and video with external users (users who are not logged on to your organizational network).</span></span> <span data-ttu-id="212bd-105">A/V 边缘服务主要通过使用 A/V 边缘配置设置进行管理, 可在网站范围或在服务范围内配置的设置 (即, 可针对单个 A/V 边缘服务器进行配置)。</span><span class="sxs-lookup"><span data-stu-id="212bd-105">The A/V Edge service is primarily managed by using A/V Edge configuration settings, setting that can be configured at the site scope or at the service scope (that is, can be configured for an individual A/V Edge server).</span></span>

<span data-ttu-id="212bd-106">若要返回有关在你的组织中使用的 A/V 边缘配置设置的信息, 必须使用 Windows PowerShell 和 CsAVEdgeConfiguration cmdlet。</span><span class="sxs-lookup"><span data-stu-id="212bd-106">To return information about the A/V Edge configuration settings in use in your organization, you must use Windows PowerShell and the Get-CsAVEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="212bd-107">有关详细信息, 请参阅[CsAVEdgeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsAVEdgeConfiguration) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="212bd-107">For more information, see the help topic for the [Get-CsAVEdgeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsAVEdgeConfiguration) cmdlet.</span></span>

<span data-ttu-id="212bd-108">从 CsAVEdgeConfiguration cmdlet 返回的信息将如下所示:</span><span class="sxs-lookup"><span data-stu-id="212bd-108">Information returned from the Get-CsAVEdgeConfiguration cmdlet will look similar to this:</span></span>

    Identity              : Global
    MaxTokenLifetime      : 08:00:00
    MaxBandwidthPerUserKb : 10000
    MaxBandwidthPerPortKb : 3000

<div>

## <a name="to-return-information-for-all-your-av-edge-configuration-settings"></a><span data-ttu-id="212bd-109">返回所有 A/V 边缘配置设置的信息</span><span class="sxs-lookup"><span data-stu-id="212bd-109">To return information for all your A/V Edge configuration settings</span></span>

  - <span data-ttu-id="212bd-110">以下命令将返回你的组织中当前使用的所有 A/V 边缘配置设置的相关信息:</span><span class="sxs-lookup"><span data-stu-id="212bd-110">The following command returns information about all the A/V Edge configuration settings currently in use in your organization:</span></span>
    
        Get-CsAVEdgeConfiguration

</div>

<div>

## <a name="to-return-information-for-site-scoped-av-edge-configuration-settings"></a><span data-ttu-id="212bd-111">返回网站范围的 A/V 边缘配置设置的信息</span><span class="sxs-lookup"><span data-stu-id="212bd-111">To return information for site-scoped A/V Edge configuration settings</span></span>

  - <span data-ttu-id="212bd-112">若要返回有关 A/V 边缘配置设置的特定集合的信息, 请在运行 CsAVEdgeConfiguration cmdlet 时指定该集合的标识。</span><span class="sxs-lookup"><span data-stu-id="212bd-112">To return information about a specific collection of A/V Edge configuration settings, specify the Identity of that collection when running the Get-CsAVEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="212bd-113">例如, 此命令仅返回对雷德蒙站点应用的设置的信息:</span><span class="sxs-lookup"><span data-stu-id="212bd-113">For example, this command returns information only for the settings applied to the Redmond site:</span></span>
    
        Get-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-return-information-for-service-scoped-av-edge-configuration-settings"></a><span data-ttu-id="212bd-114">返回有关服务范围的 A/V 边缘配置设置的信息</span><span class="sxs-lookup"><span data-stu-id="212bd-114">To return information for service-scoped A/V Edge configuration settings</span></span>

  - <span data-ttu-id="212bd-115">此命令仅为应用了特定的 A/V 边缘服务器的设置返回信息:</span><span class="sxs-lookup"><span data-stu-id="212bd-115">And this command returns information only for settings applied the a specific A/V Edge server:</span></span>
    
        Get-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="212bd-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="212bd-116">See Also</span></span>


[<span data-ttu-id="212bd-117">在 Lync Server 2013 中创建或修改 A/V 边缘服务器配置设置的集合</span><span class="sxs-lookup"><span data-stu-id="212bd-117">Create or modify a collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  
[<span data-ttu-id="212bd-118">在 Lync Server 2013 中删除 A/V 边缘服务器配置设置的现有集合</span><span class="sxs-lookup"><span data-stu-id="212bd-118">Delete an existing collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  


[<span data-ttu-id="212bd-119">Lync Server 2013 中的音频/视频 (A/V) 边缘服务器</span><span class="sxs-lookup"><span data-stu-id="212bd-119">Audio/Video (A/V) Edge Servers in Lync Server 2013</span></span>](lync-server-2013-audio-video-a-v-edge-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

