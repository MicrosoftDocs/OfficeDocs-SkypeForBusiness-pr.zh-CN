---
title: 创建或修改 A/V 边缘服务器配置设置的集合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a collection of A/V Edge Server configuration settings
ms:assetid: 43899518-59c6-4be4-8892-d6f6207bfaab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688039(v=OCS.15)
ms:contentKeyID: 49733630
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a4010c209e1231c47c328d616f686f55fc89008
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830815"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-av-edge-server-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="81df2-102">在 Lync Server 2013 中创建或修改 A/V 边缘服务器配置设置的集合</span><span class="sxs-lookup"><span data-stu-id="81df2-102">Create or modify a collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="81df2-103">_**主题上次修改时间:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="81df2-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="81df2-104">A/V 边缘服务为内部用户 (登录到你的组织网络的用户) 提供一种方法, 以便与外部用户 (未登录到你的组织网络的用户) 共享音频和视频。</span><span class="sxs-lookup"><span data-stu-id="81df2-104">The A/V Edge service provide a way for your internal users (users who are logged on to your organizational network) to share audio and video with external users (users who are not logged on to your organizational network).</span></span> <span data-ttu-id="81df2-105">A/V 边缘服务主要通过使用 A/V 边缘配置设置进行管理, 可在网站范围或在服务范围内配置的设置 (即, 可针对单个 A/V 边缘服务器进行配置)。</span><span class="sxs-lookup"><span data-stu-id="81df2-105">The A/V Edge service is primarily managed by using A/V Edge configuration settings, setting that can be configured at the site scope or at the service scope (that is, can be configured for an individual A/V Edge server).</span></span>

<span data-ttu-id="81df2-106">安装 Lync Server 时, 将为你创建一个/V 边缘配置设置的全局集合。</span><span class="sxs-lookup"><span data-stu-id="81df2-106">When you install Lync Server, a global collection of A/V Edge configuration settings is created for you.</span></span> <span data-ttu-id="81df2-107">除了这些, 你还可以使用 Windows PowerShell 和 CsAVEdgeConfiguration cmdlet 在网站范围或服务作用域 (即单个 A/V 边缘服务器) 上创建新设置。</span><span class="sxs-lookup"><span data-stu-id="81df2-107">In addition to that, you can use the Windows PowerShell and the New-CsAVEdgeConfiguration cmdlet to create new settings at the site scope or the service scope (that is, for an individual A/V Edge server).</span></span> <span data-ttu-id="81df2-108">如果您创建新设置, 请记住:</span><span class="sxs-lookup"><span data-stu-id="81df2-108">If you create new settings keep in mind that:</span></span>

  - <span data-ttu-id="81df2-109">在服务作用域 (即在单个服务器上) 中配置的设置优先于所有内容。</span><span class="sxs-lookup"><span data-stu-id="81df2-109">Settings configured at the service scope (that is, on an individual server) take priority over everything.</span></span>

  - <span data-ttu-id="81df2-110">在网站范围内配置的设置优先于在全局范围内配置的设置。</span><span class="sxs-lookup"><span data-stu-id="81df2-110">Settings configured at the site scope take priority over settings configured at the global scope.</span></span> <span data-ttu-id="81df2-111">但是, 服务范围设置还将取代网站范围的设置。</span><span class="sxs-lookup"><span data-stu-id="81df2-111">However, service scope settings will also supersede site-scope settings.</span></span>

  - <span data-ttu-id="81df2-112">只有在单个服务器上没有配置任何服务设置且该服务器所在的网站没有网站设置的情况下, 才会使用全局范围内的设置。</span><span class="sxs-lookup"><span data-stu-id="81df2-112">Settings at the global scope will be used only if there are no service settings configured on the individual server and if there are no site settings for the site where that server is located.</span></span>

<span data-ttu-id="81df2-113">然后, 你可以使用 CsAVEdgeConfiguration cmdlet 修改你的任何设置。</span><span class="sxs-lookup"><span data-stu-id="81df2-113">Any of your settings can then be modified by using the Set-CsAVEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="81df2-114">有关详细信息, 请参阅[新的-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412884(v=OCS.15))和[CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412869(v=OCS.15)) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="81df2-114">For more information, see the help topics for the [New-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412884(v=OCS.15)) and the [Set-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412869(v=OCS.15)) cmdlets.</span></span>

<div>

## <a name="to-create-new-av-edge-configuration-settings-at-the-site-scope"></a><span data-ttu-id="81df2-115">在网站范围内创建新的 A/V 边缘配置设置</span><span class="sxs-lookup"><span data-stu-id="81df2-115">To create new A/V Edge configuration settings at the site scope</span></span>

  - <span data-ttu-id="81df2-116">以下命令为雷德蒙站点的 A/V 边缘配置设置创建新的集合:</span><span class="sxs-lookup"><span data-stu-id="81df2-116">The following command creates a new collection of A/V Edge configuration settings for the Redmond site:</span></span>
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-site-scope"></a><span data-ttu-id="81df2-117">在网站范围内创建自定义 A/V 边缘配置设置</span><span class="sxs-lookup"><span data-stu-id="81df2-117">To create custom A/V Edge configuration settings at the site scope</span></span>

  - <span data-ttu-id="81df2-118">由于未包括任何其他参数, 因此这些新设置将使用 A/V 边缘服务的默认值。</span><span class="sxs-lookup"><span data-stu-id="81df2-118">Because no additional parameters were included, these new settings will use the default values for the A/V Edge service.</span></span> <span data-ttu-id="81df2-119">或者, 你可以添加其他参数和参数值以创建自定义集合。</span><span class="sxs-lookup"><span data-stu-id="81df2-119">Alternatively, you can add additional parameters and parameter values to create a custom collection.</span></span> <span data-ttu-id="81df2-120">例如, 此命令将 MaxTokenLifetime 属性设置为4小时 (04 小时:00 分:00 秒):</span><span class="sxs-lookup"><span data-stu-id="81df2-120">For example, this command sets the MaxTokenLifetime property to 4 hours (04 hours : 00 minutes : 00 seconds):</span></span>
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-service-scope"></a><span data-ttu-id="81df2-121">在服务范围内创建自定义 A/V 边缘配置设置</span><span class="sxs-lookup"><span data-stu-id="81df2-121">To create custom A/V Edge configuration settings at the service scope</span></span>

  - <span data-ttu-id="81df2-122">此命令将创建一个类似的集合, 该集合应用于 A/V 边缘服务器 atl-edge-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="81df2-122">This command creates a similar collection applied to the A/V Edge server atl-edge-001.litwareinc.com:</span></span>
    
        New-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-modify-existing-av-edge-configuration-settings"></a><span data-ttu-id="81df2-123">修改现有的 A/V 边缘配置设置</span><span class="sxs-lookup"><span data-stu-id="81df2-123">To modify existing A/V Edge configuration settings</span></span>

  - <span data-ttu-id="81df2-124">在此示例中, CsAVEdgeConfiguration cmdlet 用于将雷德蒙站点的最大令牌生命周期更改为12个小时:</span><span class="sxs-lookup"><span data-stu-id="81df2-124">In this example, the Set-CsAVEdgeConfiguration cmdlet is used to change the maximum token lifetime for the Redmond site to 12 hours:</span></span>
    
        Set-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "12:00:00"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="81df2-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="81df2-125">See Also</span></span>


[<span data-ttu-id="81df2-126">返回 Lync Server 2013 中的 A/V 边缘服务器配置信息</span><span class="sxs-lookup"><span data-stu-id="81df2-126">Return A/V Edge Server configuration information in Lync Server 2013</span></span>](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[<span data-ttu-id="81df2-127">在 Lync Server 2013 中删除 A/V 边缘服务器配置设置的现有集合</span><span class="sxs-lookup"><span data-stu-id="81df2-127">Delete an existing collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  


[<span data-ttu-id="81df2-128">Lync Server 2013 中的音频/视频 (A/V) 边缘服务器</span><span class="sxs-lookup"><span data-stu-id="81df2-128">Audio/Video (A/V) Edge Servers in Lync Server 2013</span></span>](lync-server-2013-audio-video-a-v-edge-servers.md)  
<span data-ttu-id="81df2-129">[新-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412884(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="81df2-129">[New-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412884(v=OCS.15))</span></span>  
<span data-ttu-id="81df2-130">[Set-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412869(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="81df2-130">[Set-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412869(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

