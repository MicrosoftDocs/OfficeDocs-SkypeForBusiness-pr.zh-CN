---
title: Lync Server 2013：边缘服务器 cmdlet
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Edge Server cmdlets
ms:assetid: 1a5427f4-a0d1-4652-8135-91333158ffc8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415635(v=OCS.15)
ms:contentKeyID: 48183534
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d18bea94d7844f611afb14d388d6655379ee047
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179949"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="edge-server-cmdlets-in-lync-server-2013"></a><span data-ttu-id="6186e-102">Lync Server 2013 中的边缘服务器 cmdlet</span><span class="sxs-lookup"><span data-stu-id="6186e-102">Edge Server cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6186e-103">_**上次修改的主题：** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="6186e-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="6186e-104">边缘服务器提供了一种将 Microsoft Lync Server 2013 的功能扩展到未登录到内部网络的用户的方法。</span><span class="sxs-lookup"><span data-stu-id="6186e-104">Edge Servers provide a way for you to extend the capabilities of Microsoft Lync Server 2013 to people who are not logged on to your internal network.</span></span> <span data-ttu-id="6186e-105">例如，如果您有通过 Internet 而不是通过内部网络登录到 Lync Server 2013 的远程用户-已通过身份验证的用户-您将需要设置运行 Lync Server 访问边缘服务的边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="6186e-105">For example, if you have remote users -- authenticated users who log on to Lync Server 2013 over the Internet rather than through the internal network -- you will need to set up an Edge Server that runs the Lync Server Access Edge service.</span></span> <span data-ttu-id="6186e-106">此外，如果要建立与其他组织的联盟，或者要向用户授予与具有公用即时消息服务（如 Yahoo\!、AOL 或 MSN）的帐户进行通信的用户的权利，则需要边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="6186e-106">Additionally, Edge Servers are required if you want to establish federation with another organization or if you want to give your users the right to communicate with people who have accounts with a public instant messaging service such as Yahoo\!, AOL, or MSN.</span></span>

<div>


> [!IMPORTANT]
> <UL>
> <LI>
> <P><span data-ttu-id="6186e-107">从2012年9月1日起，Microsoft Lync 公共 IM 连接用户订阅许可证（"PIC USL"）不再可用于购买新的或更新的协议。</span><span class="sxs-lookup"><span data-stu-id="6186e-107">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="6186e-108">拥有主动许可证的客户将能够继续与 Yahoo！联合联合</span><span class="sxs-lookup"><span data-stu-id="6186e-108">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="6186e-109">信使，直到服务关闭日期。</span><span class="sxs-lookup"><span data-stu-id="6186e-109">Messenger until the service shut down date.</span></span> <span data-ttu-id="6186e-110">AOL 和 Yahoo！的生命周期结束日期为2014年6月</span><span class="sxs-lookup"><span data-stu-id="6186e-110">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="6186e-111">已宣布。</span><span class="sxs-lookup"><span data-stu-id="6186e-111">has been announced.</span></span> <span data-ttu-id="6186e-112">有关详细信息，请参阅<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的支持公用即时信使连接</A>。</span><span class="sxs-lookup"><span data-stu-id="6186e-112">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="6186e-113">PIC USL 是 Lync Server 或 Office 通信服务器与 Yahoo！联合所需的每个用户每月订阅许可证。</span><span class="sxs-lookup"><span data-stu-id="6186e-113">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="6186e-114">Messenger.</span><span class="sxs-lookup"><span data-stu-id="6186e-114">Messenger.</span></span> <span data-ttu-id="6186e-115">Microsoft 提供此服务的能力因 Yahoo！中的支持而受到了支持，其下凸的底层协议。</span><span class="sxs-lookup"><span data-stu-id="6186e-115">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="6186e-116">Lync 是前所未有的强大工具，用于跨组织和世界各地的个人进行连接。</span><span class="sxs-lookup"><span data-stu-id="6186e-116">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="6186e-117">与 Windows Live Messenger 的联盟不需要除 Lync Standard CAL 之外的其他用户/设备许可证。</span><span class="sxs-lookup"><span data-stu-id="6186e-117">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="6186e-118">Skype 联合身份验证将添加到此列表中，使 Lync 用户可以使用即时消息和语音访问成百上千人。</span><span class="sxs-lookup"><span data-stu-id="6186e-118">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

<div>

## <a name="edge-server-cmdlets"></a><span data-ttu-id="6186e-119">边缘服务器 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="6186e-119">Edge Server Cmdlets</span></span>

<span data-ttu-id="6186e-120">以下是与管理边缘服务器直接相关的 cmdlet 列表：</span><span class="sxs-lookup"><span data-stu-id="6186e-120">The following is a list of cmdlets that relate directly to managing Edge Servers:</span></span>

<span data-ttu-id="6186e-121">**边缘服务器**</span><span class="sxs-lookup"><span data-stu-id="6186e-121">**Edge Server**</span></span>

  - <span></span>  
    <span data-ttu-id="6186e-122">[Set-csaccessedgeconfiguration](https://technet.microsoft.com/library/Gg398574(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6186e-122">[Get-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/Gg398574(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="6186e-123">[Set-csaccessedgeconfiguration](https://technet.microsoft.com/library/Gg413017(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6186e-123">[Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/Gg413017(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="6186e-124">[CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg413008(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6186e-124">[Get-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg413008(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="6186e-125">[新 CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6186e-125">[New-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="6186e-126">[CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6186e-126">[Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="6186e-127">[CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6186e-127">[Set-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="6186e-128">[Test-CsAVEdgeConnectivity](https://technet.microsoft.com/library/JJ205138(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6186e-128">[Test-CsAVEdgeConnectivity](https://technet.microsoft.com/library/JJ205138(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="6186e-129">[CsEdgeServer](https://technet.microsoft.com/library/Gg398859(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6186e-129">[Set-CsEdgeServer](https://technet.microsoft.com/library/Gg398859(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6186e-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6186e-130">See Also</span></span>


[<span data-ttu-id="6186e-131">Lync Server PowerShell 博客</span><span class="sxs-lookup"><span data-stu-id="6186e-131">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

