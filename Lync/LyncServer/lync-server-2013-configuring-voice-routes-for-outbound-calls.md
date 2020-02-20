---
title: Lync Server 2013：配置出站呼叫的语音路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring voice routes for outbound calls
ms:assetid: 3c182cdd-7a4a-4a9d-bdac-4199f0abd947
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425890(v=OCS.15)
ms:contentKeyID: 48183875
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c53a8358345130aa95fff4e29b5facf901cbea79
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154094"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-voice-routes-for-outbound-calls-in-lync-server-2013"></a><span data-ttu-id="76987-102">在 Lync Server 2013 中配置出站呼叫的语音路由</span><span class="sxs-lookup"><span data-stu-id="76987-102">Configuring voice routes for outbound calls in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="76987-103">_**上次修改的主题：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="76987-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="76987-104">Lync Server 2013 语音路由将目标电话号码与一个或多个公用电话交换网（PSTN）网关或 SIP 中继以及一个或多个 PSTN 用法记录相关联。</span><span class="sxs-lookup"><span data-stu-id="76987-104">A Lync Server 2013 voice route associates destination phone numbers with one or more public switched telephone network (PSTN) gateways or SIP trunks and one or more PSTN usage records.</span></span>

<span data-ttu-id="76987-105">**使用 Lync Server 控制面板查看语音路由**</span><span class="sxs-lookup"><span data-stu-id="76987-105">**To view voice routes by using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="76987-106">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="76987-106">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="76987-107">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="76987-107">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="76987-108">单击“语音路由”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="76987-108">Click **Voice Routing**.</span></span>

3.  <span data-ttu-id="76987-109">单击“路由”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="76987-109">Click **Route**.</span></span>

4.  <span data-ttu-id="76987-p102">双击语音路由以查看语音路由列表中的其他属性，或选择路由并单击“编辑”\*\*\*\*。然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="76987-p102">Double-click a voice route to view additional properties from the list of voice routes, or select the route and click **Edit**. Then click **Show details**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="76987-112">一次只能查看一个路由的详细信息。</span><span class="sxs-lookup"><span data-stu-id="76987-112">You can only view detailed information for a single route at a time.</span></span>

    
    </div>

<span data-ttu-id="76987-113">**使用 Windows PowerShell 查看语音路由**</span><span class="sxs-lookup"><span data-stu-id="76987-113">**To view voice routes by using Windows PowerShell**</span></span>

  - <span data-ttu-id="76987-114">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="76987-114">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span> <span data-ttu-id="76987-115">可以使用 Windows PowerShell 和**CsVoiceRoute** cmdlet 查看语音路由。</span><span class="sxs-lookup"><span data-stu-id="76987-115">Voice routes can be viewed by using Windows PowerShell and the **Get-CsVoiceRoute** cmdlet.</span></span> <span data-ttu-id="76987-116">此 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。</span><span class="sxs-lookup"><span data-stu-id="76987-116">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="76987-117">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。</span><span class="sxs-lookup"><span data-stu-id="76987-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="76987-118">若要查看有关所有语音路由的信息，请在 Lync Server 命令行管理程序中键入以下命令，然后按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="76987-118">To view information about all of your voice routes, type the following command in the Lync Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsVoiceRoute
    
    <span data-ttu-id="76987-119">这将返回与以下类似的信息：</span><span class="sxs-lookup"><span data-stu-id="76987-119">That will return information similar to this:</span></span>
    
        Identity          : global
        Priority          : -1
        Description       :
        NumberPattern     : ^(\+1[0-9]{10})$
        PstnUsages        : {}
        PstnGatewayList   : {}
        Name              : global
        SuppressCallerId  :
        AlternateCallerId :

<div>


> [!NOTE]  
> <span data-ttu-id="76987-120">有关详细信息，请参阅规划文档中的<A href="lync-server-2013-voice-routes.md">Lync Server 2013 中的语音路由</A>。</span><span class="sxs-lookup"><span data-stu-id="76987-120">For details, see <A href="lync-server-2013-voice-routes.md">Voice routes in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="76987-121">本部分内容</span><span class="sxs-lookup"><span data-stu-id="76987-121">In This Section</span></span>

  - [<span data-ttu-id="76987-122">在 Lync Server 2013 中创建语音路由</span><span class="sxs-lookup"><span data-stu-id="76987-122">Create a voice route in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-route.md)

  - [<span data-ttu-id="76987-123">在 Lync Server 2013 中修改语音路由</span><span class="sxs-lookup"><span data-stu-id="76987-123">Modify a voice route in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-route.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="76987-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="76987-124">See Also</span></span>


[<span data-ttu-id="76987-125">在 Lync Server 2013 中管理语音路由</span><span class="sxs-lookup"><span data-stu-id="76987-125">Managing voice routing in Lync Server 2013</span></span>](lync-server-2013-managing-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

