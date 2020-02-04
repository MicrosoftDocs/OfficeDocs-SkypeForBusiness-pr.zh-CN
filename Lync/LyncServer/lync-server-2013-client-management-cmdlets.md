---
title: Lync Server 2013：客户端管理 cmdlet
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Client management cmdlets
ms:assetid: 0384f8ab-453d-49d6-aaa7-52439e27b7e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398087(v=OCS.15)
ms:contentKeyID: 48183261
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 023b7c165d1366d42303f4b609401fcc7bbe6a1c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742922"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="client-management-cmdlets-in-lync-server-2013"></a><span data-ttu-id="9b020-102">Lync Server 2013 中的客户端管理 cmdlet</span><span class="sxs-lookup"><span data-stu-id="9b020-102">Client management cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9b020-103">_**主题上次修改时间：** 2012-09-27_</span><span class="sxs-lookup"><span data-stu-id="9b020-103">_**Topic Last Modified:** 2012-09-27_</span></span>

<span data-ttu-id="9b020-104">客户端管理主要包括确定允许哪些客户端应用程序（如 Microsoft Lync 2013）登录 Lync Server 2013 并确定这些客户端应用程序在登录后可使用的功能。</span><span class="sxs-lookup"><span data-stu-id="9b020-104">Client management consists primarily of determining which client applications (such as Microsoft Lync 2013) will be allowed to log on to Lync Server 2013 and determining the capabilities available to those client applications after they have logged on.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="9b020-105">有关 cmdlet 的其他信息，请参阅 Lync Server&nbsp;Windows PowerShell 博客<A href="http://go.microsoft.com/fwlink/p/?linkid=263432">http://go.microsoft.com/fwlink/p/?linkId=263432</A>。</span><span class="sxs-lookup"><span data-stu-id="9b020-105">For additional information about cmdlets, see the Lync Server&nbsp;Windows PowerShell Blog at <A href="http://go.microsoft.com/fwlink/p/?linkid=263432">http://go.microsoft.com/fwlink/p/?linkId=263432</A>.</span></span> <span data-ttu-id="9b020-106">每个博客的内容及其 URL 如有更改，恕不另行通知。</span><span class="sxs-lookup"><span data-stu-id="9b020-106">The content of each blog and its URL are subject to change without notice.</span></span>



</div>

<div>

## <a name="client-management-cmdlets"></a><span data-ttu-id="9b020-107">客户端管理 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="9b020-107">Client Management Cmdlets</span></span>

<span data-ttu-id="9b020-108">大多数适用于客户端管理的管理任务都可以从 Lync Server 2013 控制面板执行。</span><span class="sxs-lookup"><span data-stu-id="9b020-108">Most management tasks that apply to client management can be performed from the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="9b020-109">可以使用 Lync Server 命令行管理程序或脚本中的 cmdlet 执行这些相同的任务。</span><span class="sxs-lookup"><span data-stu-id="9b020-109">These same tasks can be performed using cmdlets from the Lync Server Management Shell or from within a script.</span></span> <span data-ttu-id="9b020-110">通过使用脚本，您可以自动执行某些任务。</span><span class="sxs-lookup"><span data-stu-id="9b020-110">By using a script, you can automate certain tasks.</span></span> <span data-ttu-id="9b020-111">以下是与客户端管理直接相关的 cmdlet 的列表：</span><span class="sxs-lookup"><span data-stu-id="9b020-111">The following is a list of cmdlets that relate directly to client management:</span></span>

  - <span></span>  
    <span data-ttu-id="9b020-112">[Set-csclientpolicy](https://technet.microsoft.com/en-us/library/Gg398830(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="9b020-112">[Get-CsClientPolicy](https://technet.microsoft.com/en-us/library/Gg398830(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="9b020-113">[授权-Set-csclientpolicy](https://technet.microsoft.com/en-us/library/Gg412942(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="9b020-113">[Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/Gg412942(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="9b020-114">[新-Set-csclientpolicy](https://technet.microsoft.com/en-us/library/Gg425949(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="9b020-114">[New-CsClientPolicy](https://technet.microsoft.com/en-us/library/Gg425949(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="9b020-115">[Remove-Set-csclientpolicy](https://technet.microsoft.com/en-us/library/Gg425772(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="9b020-115">[Remove-CsClientPolicy](https://technet.microsoft.com/en-us/library/Gg425772(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="9b020-116">[Set-Set-csclientpolicy](https://technet.microsoft.com/en-us/library/Gg398300(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="9b020-116">[Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/Gg398300(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="9b020-117">[新-CsClientPolicyEntry](https://technet.microsoft.com/en-us/library/Gg399046(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="9b020-117">[New-CsClientPolicyEntry](https://technet.microsoft.com/en-us/library/Gg399046(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="9b020-118">[CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg399072(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="9b020-118">[Get-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg399072(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="9b020-119">[新-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg399029(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="9b020-119">[New-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg399029(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="9b020-120">[Remove-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg425925(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="9b020-120">[Remove-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg425925(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="9b020-121">[Set-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg398623(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="9b020-121">[Set-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg398623(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="9b020-122">[CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg398957(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="9b020-122">[Get-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg398957(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="9b020-123">[授权-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg412903(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="9b020-123">[Grant-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg412903(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="9b020-124">[新-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg398709(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="9b020-124">[New-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg398709(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="9b020-125">[Remove-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg425801(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="9b020-125">[Remove-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg425801(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="9b020-126">[Set-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg398876(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="9b020-126">[Set-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg398876(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="9b020-127">[CsClientVersionPolicyRule](https://technet.microsoft.com/en-us/library/Gg413048(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="9b020-127">[Get-CsClientVersionPolicyRule](https://technet.microsoft.com/en-us/library/Gg413048(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="9b020-128">[新-CsClientVersionPolicyRule](https://technet.microsoft.com/en-us/library/Gg398905(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="9b020-128">[New-CsClientVersionPolicyRule](https://technet.microsoft.com/en-us/library/Gg398905(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="9b020-129">[Remove-CsClientVersionPolicyRule](https://technet.microsoft.com/en-us/library/Gg398541(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="9b020-129">[Remove-CsClientVersionPolicyRule](https://technet.microsoft.com/en-us/library/Gg398541(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="9b020-130">[Set-CsClientVersionPolicyRule](https://technet.microsoft.com/en-us/library/Gg425790(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="9b020-130">[Set-CsClientVersionPolicyRule](https://technet.microsoft.com/en-us/library/Gg425790(v=OCS.15))</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

