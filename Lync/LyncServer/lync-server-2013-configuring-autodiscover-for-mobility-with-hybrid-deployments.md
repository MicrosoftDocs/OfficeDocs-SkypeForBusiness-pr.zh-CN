---
title: 使用混合部署配置移动性的自动发现
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Autodiscover for mobility with hybrid deployments
ms:assetid: f838af79-d8b4-4122-b81c-7889573d143e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215885(v=OCS.15)
ms:contentKeyID: 48706012
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1865cab188bace472996db6207de62ce8498976
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837276"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-autodiscover-in-lync-server-2013-for-mobility-with-hybrid-deployments"></a><span data-ttu-id="5027e-102">在 Lync Server 2013 中使用混合部署配置移动性的自动发现</span><span class="sxs-lookup"><span data-stu-id="5027e-102">Configuring Autodiscover in Lync Server 2013 for mobility with hybrid deployments</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5027e-103">_**主题上次修改时间:** 2014-06-18_</span><span class="sxs-lookup"><span data-stu-id="5027e-103">_**Topic Last Modified:** 2014-06-18_</span></span>

<span data-ttu-id="5027e-104">混合部署是使用 Microsoft Lync Online 云服务和本地部署的配置。</span><span class="sxs-lookup"><span data-stu-id="5027e-104">Hybrid Deployments are configurations that use both the Microsoft Lync Online cloud service and the on premises deployment.</span></span> <span data-ttu-id="5027e-105">在此类型的配置中, 自动发现服务必须能够找到用户实际所在的位置。</span><span class="sxs-lookup"><span data-stu-id="5027e-105">In this type of configuration, the Autodiscover service must be able to locate where the user is actually located.</span></span> <span data-ttu-id="5027e-106">也就是说, "自动发现" 帮助查找用户帐户和托管用户帐户的服务器所在的位置, 无论该帐户是在本地部署还是在 Lync Online 部署中。</span><span class="sxs-lookup"><span data-stu-id="5027e-106">That is to say, Autodiscover aids in finding the user account and where the server that hosts the user’s account is, regardless if it is in the on premises deployment or in the Lync Online deployment.</span></span>

<span data-ttu-id="5027e-107">例如, 如果用户的帐户托管在 Lync Online 中的服务器上, 则在称为 "*发现*" 的过程中, 尝试查找用户的操作将如下所示:</span><span class="sxs-lookup"><span data-stu-id="5027e-107">For example, if a user’s account is hosted on a server in Lync Online, the attempt to locate the user will happen as follows, in a process known as *discoverability*:</span></span>

  - <span data-ttu-id="5027e-108">用户启动到本地部署的连接尝试**contoso.com**。</span><span class="sxs-lookup"><span data-stu-id="5027e-108">User initiates a connection attempt to the on premises deployment, **contoso.com**.</span></span>

  - <span data-ttu-id="5027e-109">该尝试将发送到 lyncdiscover.contoso.com, 它是与自动发现服务关联的 DNS 名称。</span><span class="sxs-lookup"><span data-stu-id="5027e-109">The attempt is sent to lyncdiscover.contoso.com, the DNS name associated with the Autodiscover service.</span></span>

  - <span data-ttu-id="5027e-110">自动发现指在 contoso.com 本地部署中假定的注册机构池, 并提供有关用户在 Lync Online 中托管的实际主服务器的信息。</span><span class="sxs-lookup"><span data-stu-id="5027e-110">Autodiscover refers to the assumed registrar pool at the contoso.com on premises deployment and is given information on the user’s actual home server hosted in Lync Online.</span></span> <span data-ttu-id="5027e-111">然后, 自动发现将向用户发送**lync.com**联机自动发现服务的引用。</span><span class="sxs-lookup"><span data-stu-id="5027e-111">Autodiscover then sends the user a referral to the **lync.com** online Autodiscover service.</span></span>

  - <span data-ttu-id="5027e-112">用户启动到 lync.com online 自动发现服务的连接尝试, 并且能够找到用户的帐户和用户的主服务器。</span><span class="sxs-lookup"><span data-stu-id="5027e-112">The user initiates a connection attempt to the lync.com online Autodiscover service and is able to locate the user’s account and the user’s home server.</span></span>

<span data-ttu-id="5027e-113">若要使移动客户端能够发现用户主服务器所在的部署, 必须使用新的统一资源定位器 (URL) 配置自动发现服务。</span><span class="sxs-lookup"><span data-stu-id="5027e-113">To enable mobile clients to discover the deployment where the user home server is located, you must configure the Autodiscover service with a new uniform resource locator (URL).</span></span> <span data-ttu-id="5027e-114">执行以下操作以配置自动发现服务。</span><span class="sxs-lookup"><span data-stu-id="5027e-114">Do the following to configure the Autodiscover service.</span></span>

<div>

## <a name="configuring-autodiscover-for-hybrid-deployments"></a><span data-ttu-id="5027e-115">配置混合部署的自动发现</span><span class="sxs-lookup"><span data-stu-id="5027e-115">Configuring Autodiscover for Hybrid Deployments</span></span>

1.  <span data-ttu-id="5027e-116">使用 CsHostingProvider 检索属性 ProxyFQDN 的值。</span><span class="sxs-lookup"><span data-stu-id="5027e-116">You use Get-CsHostingProvider to retrieve the value of the attribute ProxyFQDN.</span></span>

2.  <span data-ttu-id="5027e-117">从 Lync Server 命令行管理程序中, 键入</span><span class="sxs-lookup"><span data-stu-id="5027e-117">From the Lync Server Management Shell, type</span></span>
    
        Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
    
    <span data-ttu-id="5027e-118">其中\[标识\]替换为共享 SIP 地址空间的域名。</span><span class="sxs-lookup"><span data-stu-id="5027e-118">Where \[identity\] is replaced with the domain name of the shared SIP address space.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5027e-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5027e-119">See Also</span></span>


<span data-ttu-id="5027e-120">[CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg413078(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5027e-120">[Get-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg413078(v=OCS.15))</span></span>  
<span data-ttu-id="5027e-121">[Set-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398532(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5027e-121">[Set-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398532(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

