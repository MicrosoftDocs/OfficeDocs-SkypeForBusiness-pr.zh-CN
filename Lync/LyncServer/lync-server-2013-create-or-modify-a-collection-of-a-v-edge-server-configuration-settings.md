---
title: 创建或修改 A/V 边缘服务器配置设置的集合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of A/V Edge Server configuration settings
ms:assetid: 43899518-59c6-4be4-8892-d6f6207bfaab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688039(v=OCS.15)
ms:contentKeyID: 49733630
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: faff058e2d4e2ef3a874ad5fcece3ad1422605c1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151914"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-av-edge-server-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="394bc-102">在 Lync Server 2013 中创建或修改 A/V 边缘服务器配置设置的集合</span><span class="sxs-lookup"><span data-stu-id="394bc-102">Create or modify a collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="394bc-103">_**上次修改的主题：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="394bc-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="394bc-p101">A/V 边缘服务为您的内部用户（已登录到您的组织网络的用户）提供一种与外部用户（未登录到您的组织网络的用户）共享音频和视频的方法。A/V 边缘服务主要通过使用 A/V 边缘配置设置进行管理，即可在站点范围或服务范围进行配置（也就是，可以针对个别 A/V 边缘服务器进行配置）的设置。</span><span class="sxs-lookup"><span data-stu-id="394bc-p101">The A/V Edge service provide a way for your internal users (users who are logged on to your organizational network) to share audio and video with external users (users who are not logged on to your organizational network). The A/V Edge service is primarily managed by using A/V Edge configuration settings, setting that can be configured at the site scope or at the service scope (that is, can be configured for an individual A/V Edge server).</span></span>

<span data-ttu-id="394bc-106">当您安装 Lync Server 时，将为您创建 A/V 边缘配置设置的全局集合。</span><span class="sxs-lookup"><span data-stu-id="394bc-106">When you install Lync Server, a global collection of A/V Edge configuration settings is created for you.</span></span> <span data-ttu-id="394bc-107">除了这种情况外，还可以使用 Windows PowerShell 和 CsAVEdgeConfiguration cmdlet 在站点范围或服务范围（即，单个 A/V 边缘服务器）中创建新设置。</span><span class="sxs-lookup"><span data-stu-id="394bc-107">In addition to that, you can use the Windows PowerShell and the New-CsAVEdgeConfiguration cmdlet to create new settings at the site scope or the service scope (that is, for an individual A/V Edge server).</span></span> <span data-ttu-id="394bc-108">如果您创建新的设置，请记住：</span><span class="sxs-lookup"><span data-stu-id="394bc-108">If you create new settings keep in mind that:</span></span>

  - <span data-ttu-id="394bc-109">在服务范围（也就是，在个别服务器上）配置的设置的优先于一切。</span><span class="sxs-lookup"><span data-stu-id="394bc-109">Settings configured at the service scope (that is, on an individual server) take priority over everything.</span></span>

  - <span data-ttu-id="394bc-p103">在站点范围配置的设置的优先于在全局范围配置的设置。然而，服务范围设置还将取代站点范围设置。</span><span class="sxs-lookup"><span data-stu-id="394bc-p103">Settings configured at the site scope take priority over settings configured at the global scope. However, service scope settings will also supersede site-scope settings.</span></span>

  - <span data-ttu-id="394bc-112">只有未在个别服务器上配置任何服务设置，并且在服务器所在的站点没有站点设置时，才会使用全局范围的设置。</span><span class="sxs-lookup"><span data-stu-id="394bc-112">Settings at the global scope will be used only if there are no service settings configured on the individual server and if there are no site settings for the site where that server is located.</span></span>

<span data-ttu-id="394bc-113">随后，可使用 Set-CsAVEdgeConfiguration cmdlet 修改任何设置。</span><span class="sxs-lookup"><span data-stu-id="394bc-113">Any of your settings can then be modified by using the Set-CsAVEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="394bc-114">有关详细信息，请参阅[CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15))和[CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15)) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="394bc-114">For more information, see the help topics for the [New-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15)) and the [Set-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15)) cmdlets.</span></span>

<div>

## <a name="to-create-new-av-edge-configuration-settings-at-the-site-scope"></a><span data-ttu-id="394bc-115">在站点范围创建新的 A/V 边缘配置设置</span><span class="sxs-lookup"><span data-stu-id="394bc-115">To create new A/V Edge configuration settings at the site scope</span></span>

  - <span data-ttu-id="394bc-116">以下命令为 Redmond 站点创建新的 A/V 边缘配置设置集合：</span><span class="sxs-lookup"><span data-stu-id="394bc-116">The following command creates a new collection of A/V Edge configuration settings for the Redmond site:</span></span>
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-site-scope"></a><span data-ttu-id="394bc-117">在网站范围创建自定义 A/V 边缘配置设置</span><span class="sxs-lookup"><span data-stu-id="394bc-117">To create custom A/V Edge configuration settings at the site scope</span></span>

  - <span data-ttu-id="394bc-p105">由于未包含其他参数，因此这些新设置将使用 A/V 边缘服务的默认值。或者，您可以添加其他参数和参数值来创建自定义集合。例如，此命令将 MaxTokenLifetime 属性设置为 4 小时（04 小时:00 分钟:00 秒）：</span><span class="sxs-lookup"><span data-stu-id="394bc-p105">Because no additional parameters were included, these new settings will use the default values for the A/V Edge service. Alternatively, you can add additional parameters and parameter values to create a custom collection. For example, this command sets the MaxTokenLifetime property to 4 hours (04 hours : 00 minutes : 00 seconds):</span></span>
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-service-scope"></a><span data-ttu-id="394bc-121">在服务范围创建自定义 A/V 边缘配置设置</span><span class="sxs-lookup"><span data-stu-id="394bc-121">To create custom A/V Edge configuration settings at the service scope</span></span>

  - <span data-ttu-id="394bc-122">此命令将创建一个适用于 A/V 边缘服务器 atl-edge-001.litwareinc.com 的相似集合：</span><span class="sxs-lookup"><span data-stu-id="394bc-122">This command creates a similar collection applied to the A/V Edge server atl-edge-001.litwareinc.com:</span></span>
    
        New-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-modify-existing-av-edge-configuration-settings"></a><span data-ttu-id="394bc-123">修改现有的 A/V 边缘配置设置</span><span class="sxs-lookup"><span data-stu-id="394bc-123">To modify existing A/V Edge configuration settings</span></span>

  - <span data-ttu-id="394bc-124">在此示例中，Set-CsAVEdgeConfiguration cmdlet 用于将 Redmond 站点的最大令牌生存期更改为 12 小时：</span><span class="sxs-lookup"><span data-stu-id="394bc-124">In this example, the Set-CsAVEdgeConfiguration cmdlet is used to change the maximum token lifetime for the Redmond site to 12 hours:</span></span>
    
        Set-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "12:00:00"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="394bc-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="394bc-125">See Also</span></span>


[<span data-ttu-id="394bc-126">在 Lync Server 2013 中返回 A/V 边缘服务器配置信息</span><span class="sxs-lookup"><span data-stu-id="394bc-126">Return A/V Edge Server configuration information in Lync Server 2013</span></span>](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[<span data-ttu-id="394bc-127">在 Lync Server 2013 中删除 A/V 边缘服务器配置设置的现有集合</span><span class="sxs-lookup"><span data-stu-id="394bc-127">Delete an existing collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  


[<span data-ttu-id="394bc-128">Lync Server 2013 中的音频/视频（A/V）边缘服务器</span><span class="sxs-lookup"><span data-stu-id="394bc-128">Audio/Video (A/V) Edge Servers in Lync Server 2013</span></span>](lync-server-2013-audio-video-a-v-edge-servers.md)  
<span data-ttu-id="394bc-129">[新 CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="394bc-129">[New-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15))</span></span>  
<span data-ttu-id="394bc-130">[CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="394bc-130">[Set-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

