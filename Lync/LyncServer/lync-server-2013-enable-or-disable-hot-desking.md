---
title: Lync Server 2013：启用或禁用热 desking
description: Lync Server 2013：启用或禁用热 desking。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable hot desking
ms:assetid: 93a7fed6-f61a-4b41-9336-a8320afa87cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994057(v=OCS.15)
ms:contentKeyID: 51803968
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3fd22c9bf51078324cfe5e215bd154503c2d9b57
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552428"
---
# <a name="enable-or-disable-hot-desking-in-lync-server-2013"></a><span data-ttu-id="02049-103">在 Lync Server 2013 中启用或禁用热 desking</span><span class="sxs-lookup"><span data-stu-id="02049-103">Enable or disable hot desking in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="02049-104">_**上次修改的主题：** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="02049-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="02049-105">你可以将公用区域电话设置为 *热电话*。</span><span class="sxs-lookup"><span data-stu-id="02049-105">You can set up common area phones as *hot-desk phones*.</span></span> <span data-ttu-id="02049-106">使用热电话，用户可以登录到自己的用户帐户，并在登录后使用 Lync Server 功能及其自己的用户配置文件设置。</span><span class="sxs-lookup"><span data-stu-id="02049-106">With hot-desk phones, users can log on to their own user account, and, after they are logged on, use Lync Server features and their own user profile settings.</span></span> <span data-ttu-id="02049-107">热 desking 通过使用客户端策略进行管理：若要启用或禁用热 desking，需要修改公共区域电话所使用的客户端策略。</span><span class="sxs-lookup"><span data-stu-id="02049-107">Hot desking is managed by using client policies: to enable or disable hot desking, you need to modify the client policies that are used by your common area phones.</span></span> <span data-ttu-id="02049-108">有关如何确定已分配给您的公共区域电话的会议策略的详细信息，请参阅 [在 Lync Server 2013 中查看常见区域电话信息](lync-server-2013-view-common-area-phone-information.md)。</span><span class="sxs-lookup"><span data-stu-id="02049-108">For details about how to determine the conferencing policies that have been assigned to your common area phones, see [View common area phone information in Lync Server 2013](lync-server-2013-view-common-area-phone-information.md).</span></span>

<span data-ttu-id="02049-109">您可以使用 **set-csclientpolicy** Cmdlet 或 **Set-csclientpolicy** cmdlet 的 EnableHotdesking 参数在手机上启用或禁用热 desking，如下所示。</span><span class="sxs-lookup"><span data-stu-id="02049-109">You use the EnableHotdesking parameter of the **New-CSClientPolicy** cmdlet or the **Set-CSClientPolicy** cmdlet to enable or disable hot desking on a phone, as follows.</span></span> <span data-ttu-id="02049-110">从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行这些 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="02049-110">Run these cmdlets from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="02049-111">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上的 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="02049-111">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="enabling-hot-desking"></a><span data-ttu-id="02049-112">启用热 desking</span><span class="sxs-lookup"><span data-stu-id="02049-112">Enabling hot desking</span></span>

  - <span data-ttu-id="02049-113">若要为公用区域电话启用热 desking，您必须修改已分配给该电话 (或电话集合) 的客户端策略。</span><span class="sxs-lookup"><span data-stu-id="02049-113">To enable hot desking for a common area phone, you must modify the client policy that has been assigned to that phone (or collection of phones).</span></span>
    
    <span data-ttu-id="02049-114">在确定了需要修改的策略后，下一步是使用 **set-csclientpolicy** Cmdlet 将 EnableHotdesking 参数设置为 True。</span><span class="sxs-lookup"><span data-stu-id="02049-114">After you have identified the policy that needs to be modified, the next step is to use the **Set-CsClientPolicy** cmdlet to set the EnableHotdesking parameter to True.</span></span> <span data-ttu-id="02049-115">例如：</span><span class="sxs-lookup"><span data-stu-id="02049-115">For example:</span></span>
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $True

  - <span data-ttu-id="02049-116">或者，也可以使用 **set-csclientpolicy** cmdlet 创建启用热 desking 的新客户端策略。</span><span class="sxs-lookup"><span data-stu-id="02049-116">Alternatively, you can use the **New-CsClientPolicy** cmdlet to create a new client policy that enables hot desking.</span></span> <span data-ttu-id="02049-117">例如：</span><span class="sxs-lookup"><span data-stu-id="02049-117">For example:</span></span>
    
        New-CsClientPolicy -Identity "NewCommonAreaPhonePolicy" - EnableHotdesking $True

</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="02049-118">创建此策略后，必须将其分配给适当的公共区域电话。</span><span class="sxs-lookup"><span data-stu-id="02049-118">After this policy has been created, you must assign it to the appropriate common area phones.</span></span> <span data-ttu-id="02049-119">有关详细信息，请参阅 <A href="lync-server-2013-assign-policies-to-a-common-area-phone.md">在 Lync Server 2013 中将策略分配给公用区域电话</A>。</span><span class="sxs-lookup"><span data-stu-id="02049-119">For details, see <A href="lync-server-2013-assign-policies-to-a-common-area-phone.md">Assign policies in Lync Server 2013 to a common area phone</A>.</span></span>



</div>

<div>

## <a name="disabling-hot-desking"></a><span data-ttu-id="02049-120">禁用热 desking</span><span class="sxs-lookup"><span data-stu-id="02049-120">Disabling hot desking</span></span>

  - <span data-ttu-id="02049-121">若要为公用区域电话禁用热 desking，请将 **set-csclientpolicy** Cmdlet 的 EnableHotdesking 参数重置为默认值 False。</span><span class="sxs-lookup"><span data-stu-id="02049-121">To disable hot desking for a common area phone, reset the EnableHotdesking parameter of the **Set-CsClientPolicy** cmdlet to the default value of False.</span></span> <span data-ttu-id="02049-122">例如：</span><span class="sxs-lookup"><span data-stu-id="02049-122">For example:</span></span>
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $False

</div>

<span data-ttu-id="02049-123">有关详细信息，请参阅 [set-csclientpolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) Cmdlet 和 [Set-csclientpolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="02049-123">For details, see the Help topics for the [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) cmdlet and the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

