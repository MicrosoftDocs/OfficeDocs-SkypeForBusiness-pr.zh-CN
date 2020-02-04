---
title: 删除 A/V 边缘服务器配置设置的现有集合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of A/V Edge Server configuration settings
ms:assetid: 668d3613-e464-4b68-967a-cfff90b9ce4b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688077(v=OCS.15)
ms:contentKeyID: 49733673
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7cc085cd6ac39c4712647795c5baf06eaa68f77a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737542"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-av-edge-server-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="17e8d-102">在 Lync Server 2013 中删除 A/V 边缘服务器配置设置的现有集合</span><span class="sxs-lookup"><span data-stu-id="17e8d-102">Delete an existing collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="17e8d-103">_**主题上次修改时间：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="17e8d-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="17e8d-104">A/V 边缘服务为内部用户（登录到你的组织网络的用户）提供一种方法，以便与外部用户（未登录到你的组织网络的用户）共享音频和视频。</span><span class="sxs-lookup"><span data-stu-id="17e8d-104">The A/V Edge service provide a way for your internal users (users who are logged on to your organizational network) to share audio and video with external users (users who are not logged on to your organizational network).</span></span> <span data-ttu-id="17e8d-105">A/V 边缘服务主要通过使用 A/V 边缘配置设置进行管理，可在网站范围或在服务范围内配置的设置（即，可针对单个 A/V 边缘服务器进行配置）。</span><span class="sxs-lookup"><span data-stu-id="17e8d-105">The A/V Edge service is primarily managed by using A/V Edge configuration settings, setting that can be configured at the site scope or at the service scope (that is, can be configured for an individual A/V Edge server).</span></span>

<span data-ttu-id="17e8d-106">安装 Lync Server 时，将为你创建一个/V 边缘配置设置的全局集合。</span><span class="sxs-lookup"><span data-stu-id="17e8d-106">When you install Lync Server, a global collection of A/V Edge configuration settings is created for you.</span></span> <span data-ttu-id="17e8d-107">无法删除此全局集合。</span><span class="sxs-lookup"><span data-stu-id="17e8d-107">This global collection cannot be deleted.</span></span> <span data-ttu-id="17e8d-108">但是，你可以使用 Windows PowerShell 和 CsAVEdgeConfiguration cmdlet 来 "重置" 全局集合;这只意味着全局集合中的所有属性值都将重置为其默认值。</span><span class="sxs-lookup"><span data-stu-id="17e8d-108">However, you can use the Windows PowerShell and the Remove-CsAVEdgeConfiguration cmdlet to "reset" the global collection; that simply means that all the property values in the global collection will be reset to their default value.</span></span> <span data-ttu-id="17e8d-109">例如，如果您已将 MaxTokenLifetime 属性设置为16小时，则该属性将重置为其默认值8小时。</span><span class="sxs-lookup"><span data-stu-id="17e8d-109">For example, if you have set the MaxTokenLifetime property for 16 hours, that property will be reset to its default value of 8 hours.</span></span>

<span data-ttu-id="17e8d-110">但是，你可以使用 CsAVEdgeConfiguration cmdlet 删除你在网站范围或服务范围内创建的自定义设置集合。</span><span class="sxs-lookup"><span data-stu-id="17e8d-110">However, custom settings collections that you have created at either the site scope or the service scope can be deleted by using the Remove-CsAVEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="17e8d-111">如果您删除网站设置，则该网站中的 A/V 边缘服务器将由全局设置管理。</span><span class="sxs-lookup"><span data-stu-id="17e8d-111">If you delete site settings then A/V Edge servers in that site will be managed by the global settings.</span></span> <span data-ttu-id="17e8d-112">如果你删除了服务范围设置，则该服务器将由其网站设置（如果存在）或全局设置管理（如果没有可用的网站设置）。</span><span class="sxs-lookup"><span data-stu-id="17e8d-112">If you delete service-scope settings,, that server will then be managed by its site settings, if they exist, or by the global settings if no site settings are available.</span></span>

<span data-ttu-id="17e8d-113">有关详细信息，请参阅[CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398786(v=OCS.15)) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="17e8d-113">For more information, see the help topic for the [Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398786(v=OCS.15)) cmdlet.</span></span>

<div>

## <a name="to-reset-the-global-collection"></a><span data-ttu-id="17e8d-114">重置全局集合</span><span class="sxs-lookup"><span data-stu-id="17e8d-114">To reset the global collection</span></span>

  - <span data-ttu-id="17e8d-115">以下命令将重置 A/V 边缘配置设置的全局集合：</span><span class="sxs-lookup"><span data-stu-id="17e8d-115">The following command resets the global collection of A/V Edge configuration settings:</span></span>
    
        Remove-CsAVEdgeConfiguration -Identity "global"

</div>

<div>

## <a name="to-remove-a-collection-from-the-site-scope"></a><span data-ttu-id="17e8d-116">从网站范围中删除集合</span><span class="sxs-lookup"><span data-stu-id="17e8d-116">To remove a collection from the site scope</span></span>

  - <span data-ttu-id="17e8d-117">此命令将删除应用于 Redmond 网站的 A/V 边缘配置设置：</span><span class="sxs-lookup"><span data-stu-id="17e8d-117">This command removes the A/V Edge configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-a-collection-from-the-service-scope"></a><span data-ttu-id="17e8d-118">从服务范围中删除集合</span><span class="sxs-lookup"><span data-stu-id="17e8d-118">To remove a collection from the service scope</span></span>

  - <span data-ttu-id="17e8d-119">此命令将删除应用到 A/V 边缘服务器 atl-edge-001.litwareinc.com 的设置：</span><span class="sxs-lookup"><span data-stu-id="17e8d-119">This command removes the settings applied to the A/V Edge server atl-edge-001.litwareinc.com:</span></span>
    
        Remove-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="17e8d-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="17e8d-120">See Also</span></span>


[<span data-ttu-id="17e8d-121">返回 Lync Server 2013 中的 A/V 边缘服务器配置信息</span><span class="sxs-lookup"><span data-stu-id="17e8d-121">Return A/V Edge Server configuration information in Lync Server 2013</span></span>](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[<span data-ttu-id="17e8d-122">在 Lync Server 2013 中创建或修改 A/V 边缘服务器配置设置的集合</span><span class="sxs-lookup"><span data-stu-id="17e8d-122">Create or modify a collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  


[<span data-ttu-id="17e8d-123">Lync Server 2013 中的音频/视频（A/V）边缘服务器</span><span class="sxs-lookup"><span data-stu-id="17e8d-123">Audio/Video (A/V) Edge Servers in Lync Server 2013</span></span>](lync-server-2013-audio-video-a-v-edge-servers.md)  
<span data-ttu-id="17e8d-124">[Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398786(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="17e8d-124">[Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398786(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

