---
title: Lync Server 2013：配置出站呼叫的语音路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring voice routes for outbound calls
ms:assetid: 3c182cdd-7a4a-4a9d-bdac-4199f0abd947
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425890(v=OCS.15)
ms:contentKeyID: 48183875
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e91525f5d35110560b28059f774be8d2cb5df6d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837148"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-voice-routes-for-outbound-calls-in-lync-server-2013"></a><span data-ttu-id="dbe9e-102">在 Lync Server 2013 中配置出站呼叫的语音路由</span><span class="sxs-lookup"><span data-stu-id="dbe9e-102">Configuring voice routes for outbound calls in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dbe9e-103">_**主题上次修改时间:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="dbe9e-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="dbe9e-104">Lync Server 2013 语音路由将目标电话号码与一个或多个公共交换电话网络 (PSTN) 网关或 SIP 中继以及一个或多个 PSTN 使用记录相关联。</span><span class="sxs-lookup"><span data-stu-id="dbe9e-104">A Lync Server 2013 voice route associates destination phone numbers with one or more public switched telephone network (PSTN) gateways or SIP trunks and one or more PSTN usage records.</span></span>

<span data-ttu-id="dbe9e-105">**使用 Lync Server "控制面板" 查看语音路由**</span><span class="sxs-lookup"><span data-stu-id="dbe9e-105">**To view voice routes by using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="dbe9e-106">打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="dbe9e-106">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="dbe9e-107">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="dbe9e-107">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="dbe9e-108">单击 "**语音路由**"。</span><span class="sxs-lookup"><span data-stu-id="dbe9e-108">Click **Voice Routing**.</span></span>

3.  <span data-ttu-id="dbe9e-109">单击“路由”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dbe9e-109">Click **Route**.</span></span>

4.  <span data-ttu-id="dbe9e-110">双击语音路线以从语音路由列表中查看其他属性, 或选择路线, 然后单击 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="dbe9e-110">Double-click a voice route to view additional properties from the list of voice routes, or select the route and click **Edit**.</span></span> <span data-ttu-id="dbe9e-111">然后单击 "**显示详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="dbe9e-111">Then click **Show details**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="dbe9e-112">一次只能查看一个路线的详细信息。</span><span class="sxs-lookup"><span data-stu-id="dbe9e-112">You can only view detailed information for a single route at a time.</span></span>

    
    </div>

<span data-ttu-id="dbe9e-113">**使用 Windows PowerShell 查看语音路由**</span><span class="sxs-lookup"><span data-stu-id="dbe9e-113">**To view voice routes by using Windows PowerShell**</span></span>

  - <span data-ttu-id="dbe9e-114">启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="dbe9e-114">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span> <span data-ttu-id="dbe9e-115">可以使用 Windows PowerShell 和**CsVoiceRoute** cmdlet 查看语音路线。</span><span class="sxs-lookup"><span data-stu-id="dbe9e-115">Voice routes can be viewed by using Windows PowerShell and the **Get-CsVoiceRoute** cmdlet.</span></span> <span data-ttu-id="dbe9e-116">此 cmdlet 既可以从 Lync Server 2013 管理外壳运行, 也可以从 Windows PowerShell 的远程会话运行。</span><span class="sxs-lookup"><span data-stu-id="dbe9e-116">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="dbe9e-117">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息, 请参阅 Lync Server Windows PowerShell 博客文章 "快速入门: 使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="dbe9e-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="dbe9e-118">若要查看有关所有语音路由的信息, 请在 Lync Server 命令行管理程序中键入以下命令, 然后按 ENTER:</span><span class="sxs-lookup"><span data-stu-id="dbe9e-118">To view information about all of your voice routes, type the following command in the Lync Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsVoiceRoute
    
    <span data-ttu-id="dbe9e-119">这将返回与以下类似的信息：</span><span class="sxs-lookup"><span data-stu-id="dbe9e-119">That will return information similar to this:</span></span>
    
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
> <span data-ttu-id="dbe9e-120">有关详细信息, 请参阅规划文档中<A href="lync-server-2013-voice-routes.md">Lync Server 2013 中的语音路由</A>。</span><span class="sxs-lookup"><span data-stu-id="dbe9e-120">For details, see <A href="lync-server-2013-voice-routes.md">Voice routes in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="dbe9e-121">本节内容</span><span class="sxs-lookup"><span data-stu-id="dbe9e-121">In This Section</span></span>

  - [<span data-ttu-id="dbe9e-122">在 Lync Server 2013 中创建语音路由</span><span class="sxs-lookup"><span data-stu-id="dbe9e-122">Create a voice route in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-route.md)

  - [<span data-ttu-id="dbe9e-123">在 Lync Server 2013 中修改语音路由</span><span class="sxs-lookup"><span data-stu-id="dbe9e-123">Modify a voice route in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-route.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="dbe9e-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dbe9e-124">See Also</span></span>


[<span data-ttu-id="dbe9e-125">在 Lync Server 2013 中管理语音路由</span><span class="sxs-lookup"><span data-stu-id="dbe9e-125">Managing voice routing in Lync Server 2013</span></span>](lync-server-2013-managing-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

