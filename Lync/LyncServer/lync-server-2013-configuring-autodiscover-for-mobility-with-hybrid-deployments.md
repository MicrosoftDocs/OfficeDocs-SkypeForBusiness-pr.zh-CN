---
title: 为具有混合部署的移动性配置自动发现
description: 为具有混合部署的移动性配置自动发现。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Autodiscover for mobility with hybrid deployments
ms:assetid: f838af79-d8b4-4122-b81c-7889573d143e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215885(v=OCS.15)
ms:contentKeyID: 48706012
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a66f0045ec1fce65b8e21b6a6f4494b96c93912
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562458"
---
# <a name="configuring-autodiscover-in-lync-server-2013-for-mobility-with-hybrid-deployments"></a><span data-ttu-id="f9708-103">在 Lync Server 2013 中配置自动发现以实现与混合部署的移动性</span><span class="sxs-lookup"><span data-stu-id="f9708-103">Configuring Autodiscover in Lync Server 2013 for mobility with hybrid deployments</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9708-104">_**上次修改的主题：** 2014-06-18_</span><span class="sxs-lookup"><span data-stu-id="f9708-104">_**Topic Last Modified:** 2014-06-18_</span></span>

<span data-ttu-id="f9708-105">混合部署是使用 Microsoft Lync Online 云服务和本地部署的配置。</span><span class="sxs-lookup"><span data-stu-id="f9708-105">Hybrid Deployments are configurations that use both the Microsoft Lync Online cloud service and the on premises deployment.</span></span> <span data-ttu-id="f9708-106">在此类型的配置中，自动发现服务必须能够找到用户实际所处的位置。</span><span class="sxs-lookup"><span data-stu-id="f9708-106">In this type of configuration, the Autodiscover service must be able to locate where the user is actually located.</span></span> <span data-ttu-id="f9708-107">也就是说，自动发现功能会帮助查找用户帐户以及承载用户帐户的服务器所在的位置，而不管它是在本地部署中还是在 Lync Online 部署中。</span><span class="sxs-lookup"><span data-stu-id="f9708-107">That is to say, Autodiscover aids in finding the user account and where the server that hosts the user’s account is, regardless if it is in the on premises deployment or in the Lync Online deployment.</span></span>

<span data-ttu-id="f9708-108">例如，如果用户的帐户托管在 Lync Online 中的服务器上，则在称为 " *发现*" 的过程中，查找用户的尝试将按如下方式发生：</span><span class="sxs-lookup"><span data-stu-id="f9708-108">For example, if a user’s account is hosted on a server in Lync Online, the attempt to locate the user will happen as follows, in a process known as *discoverability*:</span></span>

  - <span data-ttu-id="f9708-109">用户启动对内部部署的连接尝试 **contoso.com**。</span><span class="sxs-lookup"><span data-stu-id="f9708-109">User initiates a connection attempt to the on premises deployment, **contoso.com**.</span></span>

  - <span data-ttu-id="f9708-110">会将尝试发送到 lyncdiscover.contoso.com，DNS 名称与自动发现服务相关联。</span><span class="sxs-lookup"><span data-stu-id="f9708-110">The attempt is sent to lyncdiscover.contoso.com, the DNS name associated with the Autodiscover service.</span></span>

  - <span data-ttu-id="f9708-111">自动发现是指在 contoso.com 本地部署中假定的注册器池，并提供有关 Lync Online 中托管的用户实际主服务器的信息。</span><span class="sxs-lookup"><span data-stu-id="f9708-111">Autodiscover refers to the assumed registrar pool at the contoso.com on premises deployment and is given information on the user’s actual home server hosted in Lync Online.</span></span> <span data-ttu-id="f9708-112">然后自动发现会向用户对 **lync.com** 联机自动发现服务发送一个引用。</span><span class="sxs-lookup"><span data-stu-id="f9708-112">Autodiscover then sends the user a referral to the **lync.com** online Autodiscover service.</span></span>

  - <span data-ttu-id="f9708-113">用户对 lync.com 联机自动发现服务启动一个连接尝试，并能够找到用户的帐户和用户的主服务器。</span><span class="sxs-lookup"><span data-stu-id="f9708-113">The user initiates a connection attempt to the lync.com online Autodiscover service and is able to locate the user’s account and the user’s home server.</span></span>

<span data-ttu-id="f9708-p103">要启用移动客户端来发现用户主服务器所在的部署，则必须使用新的统一资源定位器 (URL) 配置自动发现服务。执行下列操作可配置自动发现服务。</span><span class="sxs-lookup"><span data-stu-id="f9708-p103">To enable mobile clients to discover the deployment where the user home server is located, you must configure the Autodiscover service with a new uniform resource locator (URL). Do the following to configure the Autodiscover service.</span></span>

<div>

## <a name="configuring-autodiscover-for-hybrid-deployments"></a><span data-ttu-id="f9708-116">为混合部署配置自动发现</span><span class="sxs-lookup"><span data-stu-id="f9708-116">Configuring Autodiscover for Hybrid Deployments</span></span>

1.  <span data-ttu-id="f9708-117">您可以使用 Get-CsHostingProvider 检索 ProxyFQDN 属性的值。</span><span class="sxs-lookup"><span data-stu-id="f9708-117">You use Get-CsHostingProvider to retrieve the value of the attribute ProxyFQDN.</span></span>

2.  <span data-ttu-id="f9708-118">在 Lync Server 命令行管理程序中，键入</span><span class="sxs-lookup"><span data-stu-id="f9708-118">From the Lync Server Management Shell, type</span></span>
    
        Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
    
    <span data-ttu-id="f9708-119">其中 \[ 标识 \] 替换为共享 SIP 地址空间的域名。</span><span class="sxs-lookup"><span data-stu-id="f9708-119">Where \[identity\] is replaced with the domain name of the shared SIP address space.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f9708-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f9708-120">See Also</span></span>


<span data-ttu-id="f9708-121">[CsHostingProvider](https://technet.microsoft.com/library/Gg413078(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f9708-121">[Get-CsHostingProvider](https://technet.microsoft.com/library/Gg413078(v=OCS.15))</span></span>  
<span data-ttu-id="f9708-122">[CsHostingProvider](https://technet.microsoft.com/library/Gg398532(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f9708-122">[Set-CsHostingProvider](https://technet.microsoft.com/library/Gg398532(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

