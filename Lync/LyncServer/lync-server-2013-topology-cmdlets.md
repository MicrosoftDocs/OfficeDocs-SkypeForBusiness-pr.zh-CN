---
title: Lync Server 2013：拓扑 cmdlet
description: Lync Server 2013：拓扑 cmdlet。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topology cmdlets
ms:assetid: 3ed739a7-d58d-475d-8240-fa8d2c6dc7e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415648(v=OCS.15)
ms:contentKeyID: 48183942
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f77febaa3beb4acc25bc5bc54dd0d5585fe18fc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549108"
---
# <a name="topology-cmdlets-jn-lync-server-2013"></a><span data-ttu-id="33ba1-103">Jn Lync Server 2013 的拓扑 cmdlet</span><span class="sxs-lookup"><span data-stu-id="33ba1-103">Topology cmdlets jn Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="33ba1-104">_**上次修改的主题：** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="33ba1-104">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="33ba1-105">Microsoft Lync Server 2013 中包含的许多拓扑 cmdlet 都设计为与安装和拓扑生成器配合使用;因此，管理员很少会直接调用许多拓扑 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="33ba1-105">Many of the topology cmdlets included in Microsoft Lync Server 2013 are designed for use with Setup and Topology Builder; because of that, there are a number of topology cmdlets that administrators will rarely call directly.</span></span> <span data-ttu-id="33ba1-106">不过，有时管理员将需要使用这些 cmdlet;例如，在创建新的 Kerberos 帐户之后，您必须运行 [enable-cstopology](https://technet.microsoft.com/library/Gg398398(v=OCS.15)) cmdlet，以使更改生效。</span><span class="sxs-lookup"><span data-stu-id="33ba1-106">However, there will be times when administrators will be required to use these cmdlets; for example, after creating new Kerberos accounts you must run the [Enable-CsTopology](https://technet.microsoft.com/library/Gg398398(v=OCS.15)) cmdlet to cause the changes to take effect.</span></span> <span data-ttu-id="33ba1-107">此外，管理员很可能会运行 [enable-cstopology](https://technet.microsoft.com/library/Gg398127(v=OCS.15)) 和 [CsComputer](https://technet.microsoft.com/library/Gg398162(v=OCS.15)) 等 cmdlet，以帮助确保已正确安装 Lync Server 2013 并按预期方式工作。</span><span class="sxs-lookup"><span data-stu-id="33ba1-107">In addition, administrators will likely run cmdlets such as [Test-CsTopology](https://technet.microsoft.com/library/Gg398127(v=OCS.15)) and [Test-CsComputer](https://technet.microsoft.com/library/Gg398162(v=OCS.15)) to help ensure that Lync Server 2013 has been correctly installed and is working as expected.</span></span>

<div>

## <a name="topology-cmdlets"></a><span data-ttu-id="33ba1-108">拓扑 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="33ba1-108">Topology Cmdlets</span></span>

<span data-ttu-id="33ba1-109">以下是与您直接管理 Lync Server 拓扑相关的 cmdlet 的列表：</span><span class="sxs-lookup"><span data-stu-id="33ba1-109">The following is a list of cmdlets that relate directly managing your Lync Server topology:</span></span>

<span data-ttu-id="33ba1-110">**拓扑**</span><span class="sxs-lookup"><span data-stu-id="33ba1-110">**Topology**</span></span>

  - <span></span>  
    <span data-ttu-id="33ba1-111">[Start-cspool](https://technet.microsoft.com/library/Gg398992(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="33ba1-111">[Get-CsPool](https://technet.microsoft.com/library/Gg398992(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="33ba1-112">[Get-cssite](https://technet.microsoft.com/library/Gg398185(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="33ba1-112">[Get-CsSite](https://technet.microsoft.com/library/Gg398185(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="33ba1-113">[Get-cssite](https://technet.microsoft.com/library/Gg413023(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="33ba1-113">[Set-CsSite](https://technet.microsoft.com/library/Gg413023(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="33ba1-114">[Enable-Enable-cstopology](https://technet.microsoft.com/library/Gg398398(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="33ba1-114">[Enable-CsTopology](https://technet.microsoft.com/library/Gg398398(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="33ba1-115">[Enable-cstopology](https://technet.microsoft.com/library/Gg412824(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="33ba1-115">[Get-CsTopology](https://technet.microsoft.com/library/Gg412824(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="33ba1-116">[发布-Enable-cstopology](https://technet.microsoft.com/library/Gg398953(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="33ba1-116">[Publish-CsTopology](https://technet.microsoft.com/library/Gg398953(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="33ba1-117">[Test-Enable-cstopology](https://technet.microsoft.com/library/Gg398127(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="33ba1-117">[Test-CsTopology](https://technet.microsoft.com/library/Gg398127(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="33ba1-118">[Export-CsConfiguration](https://technet.microsoft.com/library/Gg398627(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="33ba1-118">[Export-CsConfiguration](https://technet.microsoft.com/library/Gg398627(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="33ba1-119">[Import-CsConfiguration](https://technet.microsoft.com/library/Gg398800(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="33ba1-119">[Import-CsConfiguration](https://technet.microsoft.com/library/Gg398800(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="33ba1-120">[CsServerVersion](https://technet.microsoft.com/library/Gg398470(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="33ba1-120">[Get-CsServerVersion](https://technet.microsoft.com/library/Gg398470(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="33ba1-121">[Disable-CsComputer](https://technet.microsoft.com/library/Gg399023(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="33ba1-121">[Disable-CsComputer](https://technet.microsoft.com/library/Gg399023(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="33ba1-122">[Enable-CsComputer](https://technet.microsoft.com/library/Gg412815(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="33ba1-122">[Enable-CsComputer](https://technet.microsoft.com/library/Gg412815(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="33ba1-123">[CsComputer](https://technet.microsoft.com/library/Gg425959(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="33ba1-123">[Get-CsComputer](https://technet.microsoft.com/library/Gg425959(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="33ba1-124">[Test-CsComputer](https://technet.microsoft.com/library/Gg398162(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="33ba1-124">[Test-CsComputer](https://technet.microsoft.com/library/Gg398162(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="33ba1-125">[CsNetworkInterface](https://technet.microsoft.com/library/Gg398121(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="33ba1-125">[Get-CsNetworkInterface](https://technet.microsoft.com/library/Gg398121(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="33ba1-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="33ba1-126">See Also</span></span>


[<span data-ttu-id="33ba1-127">Lync Server PowerShell 博客</span><span class="sxs-lookup"><span data-stu-id="33ba1-127">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

