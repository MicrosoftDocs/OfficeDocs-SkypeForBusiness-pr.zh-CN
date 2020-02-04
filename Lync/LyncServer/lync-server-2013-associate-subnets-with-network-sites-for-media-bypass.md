---
title: Lync Server 2013：将子网与用于媒体绕过的网络站点关联
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associate subnets with network sites for media bypass
ms:assetid: 5bc632b7-1446-470f-b332-48ea0ca4d1fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398401(v=OCS.15)
ms:contentKeyID: 48184244
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd45daa964b51639c7fe1db3ff10e334e21641f2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722792"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="associate-subnets-with-network-sites-for-media-bypass-in-lync-server-2013"></a><span data-ttu-id="b1905-102">将子网与 Lync Server 2013 中的媒体绕过的网络站点关联</span><span class="sxs-lookup"><span data-stu-id="b1905-102">Associate subnets with network sites for media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b1905-103">_**主题上次修改时间：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="b1905-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b1905-104">本主题假定你已配置了媒体绕过全局设置，并且已配置了媒体绕过的网络区域和网络站点。</span><span class="sxs-lookup"><span data-stu-id="b1905-104">This topic assumes that you have configured media bypass global settings and that you have configured network region and network sites for media bypass.</span></span>



</div>

<span data-ttu-id="b1905-105">您的网络中的每个子网都必须与特定的网络站点相关联。</span><span class="sxs-lookup"><span data-stu-id="b1905-105">Every subnet in your network must be associated with a specific network site.</span></span> <span data-ttu-id="b1905-106">这是因为子网信息用于确定终结点所在的网络站点。</span><span class="sxs-lookup"><span data-stu-id="b1905-106">This is because subnet information is used to determine the network site on which an endpoint is located.</span></span> <span data-ttu-id="b1905-107">当会话中双方双方的位置已知时，媒体绕过可确定发送媒体以进行处理的位置。</span><span class="sxs-lookup"><span data-stu-id="b1905-107">When the locations of both parties in a session are known, media bypass can determine where to send media for processing.</span></span>

<span data-ttu-id="b1905-108">媒体绕过对将子网与网络站点相关联的特殊要求。</span><span class="sxs-lookup"><span data-stu-id="b1905-108">Media bypass does not have any special requirements for associating subnets with network sites.</span></span> <span data-ttu-id="b1905-109">若要在拓扑中的子网和网络站点之间创建关联，请按照[将子网与 Lync Server 2013 中的网络站点关联](lync-server-2013-associate-a-subnet-with-a-network-site.md)的过程进行操作。</span><span class="sxs-lookup"><span data-stu-id="b1905-109">To create an association between the subnets and network sites in your topology, follow the procedures in [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span></span>

<div>

## <a name="next-steps-create-bandwidth-policy-profiles"></a><span data-ttu-id="b1905-110">后续步骤：创建带宽策略配置文件</span><span class="sxs-lookup"><span data-stu-id="b1905-110">Next Steps: Create Bandwidth Policy Profiles</span></span>

<span data-ttu-id="b1905-111">将子网与用于媒体绕过的网络站点相关联后，必须创建一个或多个带宽策略配置文件，以便将子网分区为具有良好连接性的子网，而不是为了媒体绕过。</span><span class="sxs-lookup"><span data-stu-id="b1905-111">After you associate subnets with network sites for media bypass, you must create one or more bandwidth policy profiles that will partition subnets into those with good connectivity and those without, for the purposes of media bypass.</span></span> <span data-ttu-id="b1905-112">网络区域中的所有子网都没有带宽限制的网络站点具有良好的连接性，因此这些子网可以使用 "媒体绕过"。</span><span class="sxs-lookup"><span data-stu-id="b1905-112">All subnets within a network region with network sites that do not have bandwidth constraints have good connectivity, and, therefore, those subnets can use media bypass.</span></span>

<span data-ttu-id="b1905-113">有关配置带宽策略配置文件的过程，请参阅[在 Lync Server 2013 中创建带宽策略配置文件](lync-server-2013-create-bandwidth-policy-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="b1905-113">For procedures to configure bandwidth policy profiles, see [Create bandwidth policy profiles in Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

