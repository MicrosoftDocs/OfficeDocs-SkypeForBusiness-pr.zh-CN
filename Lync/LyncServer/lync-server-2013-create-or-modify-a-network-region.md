---
title: Lync Server 2013：创建或修改网络区域
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a network region
ms:assetid: bf7a3dc4-71a2-4559-a547-d90305d4f904
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412933(v=OCS.15)
ms:contentKeyID: 48185281
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3579286f0cf4b77c84baa013aead13b3b671549c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137571"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-network-region-in-lync-server-2013"></a><span data-ttu-id="8590a-102">在 Lync Server 2013 中创建或修改网络区域</span><span class="sxs-lookup"><span data-stu-id="8590a-102">Create or modify a network region in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8590a-103">_**上次修改的主题：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="8590a-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="8590a-104">*网络区域* 是在呼叫允许控制、E9-1-1 和媒体旁路的配置中使用的网络中心或网络中枢。</span><span class="sxs-lookup"><span data-stu-id="8590a-104">*Network regions* are the network hubs or backbones used in the configuration of call admission control, E9-1-1, and media bypass.</span></span> <span data-ttu-id="8590a-105">使用以下过程创建或修改网络区域。</span><span class="sxs-lookup"><span data-stu-id="8590a-105">Use the following procedures to create or modify network regions.</span></span> <span data-ttu-id="8590a-106">例如，如果已为一个语音功能创建网络区域，则不需要创建新的网络区域；其他高级企业语音功能也将使用这些网络区域。</span><span class="sxs-lookup"><span data-stu-id="8590a-106">For example, if you have already created network regions for one Voice feature, you do not need to create new network regions; other advanced Enterprise Voice features will use those same network regions.</span></span> <span data-ttu-id="8590a-107">但是，可能需要修改现有的网络区域定义，以应用特定于功能的设置。</span><span class="sxs-lookup"><span data-stu-id="8590a-107">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="8590a-108">例如，如果已为 E9-1-1（它不要求有关联的中央站点）创建网络区域，然后部署呼叫允许控制，则需要修改网络区域定义，以指定中央站点。</span><span class="sxs-lookup"><span data-stu-id="8590a-108">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and you then deploy call admission control, you need to modify the network region definitions to specify a central site.</span></span> <span data-ttu-id="8590a-109">有关详细信息，请参阅[在 Lync Server 2013 中配置 CAC 的网络区域](lync-server-2013-configure-network-regions-for-cac.md)。</span><span class="sxs-lookup"><span data-stu-id="8590a-109">For details, see [Configure network regions for CAC in Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8590a-110">有关网络区域定义的任何特定于功能的要求均编档在相应功能的部署主题中。</span><span class="sxs-lookup"><span data-stu-id="8590a-110">Any feature-specific requirements for network region definitions are documented in the Deployment topics for the feature.</span></span>



</div>

<span data-ttu-id="8590a-111">有关使用网络区域的详细信息，请参阅 Lync Server 命令行管理程序文档中的以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="8590a-111">For details about working with network regions, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="8590a-112">新 CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="8590a-112">New-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)

  - [<span data-ttu-id="8590a-113">CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="8590a-113">Get-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)

  - [<span data-ttu-id="8590a-114">CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="8590a-114">Set-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)

  - [<span data-ttu-id="8590a-115">CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="8590a-115">Remove-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)

<div>

## <a name="create-a-network-region"></a><span data-ttu-id="8590a-116">创建网络区域</span><span class="sxs-lookup"><span data-stu-id="8590a-116">Create a Network Region</span></span>

<span data-ttu-id="8590a-117">创建可由呼叫允许控制、E9-1-1 或媒体旁路使用的网络区域。</span><span class="sxs-lookup"><span data-stu-id="8590a-117">Create a network region that can be used by call admission control, E9-1-1, or media bypass.</span></span>

<div>

## <a name="to-create-a-network-region-using-lync-server-management-shell"></a><span data-ttu-id="8590a-118">使用 Lync Server 命令行管理程序创建网络区域</span><span class="sxs-lookup"><span data-stu-id="8590a-118">To create a network region using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="8590a-119">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8590a-119">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="8590a-120">运行 New-CsNetworkRegion cmdlet 创建网络区域：</span><span class="sxs-lookup"><span data-stu-id="8590a-120">Run the New-CsNetworkRegion cmdlet to create network regions:</span></span>
    
        New-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    <span data-ttu-id="8590a-121">例如：</span><span class="sxs-lookup"><span data-stu-id="8590a-121">For example:</span></span>
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"
    
    <span data-ttu-id="8590a-122">在此示例中，您创建了一个称为“NorthAmerica”的网络区域，此区域与站点 ID 为 CHICAGO 的中央站点相关联。</span><span class="sxs-lookup"><span data-stu-id="8590a-122">In this example, you created a network region called “NorthAmerica” that is associated with a central site with site ID CHICAGO.</span></span>

3.  <span data-ttu-id="8590a-123">要为拓扑完成网络区域的创建，请使用每个网络区域的设置重复步骤 2。</span><span class="sxs-lookup"><span data-stu-id="8590a-123">To finish creating network regions for your topology, repeat step 2 with settings for each network region.</span></span>

</div>

<div>

## <a name="to-create-a-network-region-using-lync-server-control-panel"></a><span data-ttu-id="8590a-124">使用 Lync Server 控制面板创建网络区域</span><span class="sxs-lookup"><span data-stu-id="8590a-124">To create a network region using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="8590a-125">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="8590a-125">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8590a-126">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="8590a-126">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="8590a-127">在左侧导航栏中，单击“网络配置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8590a-127">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="8590a-128">单击“区域”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8590a-128">Click **Region**.</span></span>

4.  <span data-ttu-id="8590a-129">单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8590a-129">Click **New**.</span></span>

5.  <span data-ttu-id="8590a-130">在“新建区域”\*\*\*\* 页上，单击“名称”\*\*\*\*，然后键入网络区域的名称。</span><span class="sxs-lookup"><span data-stu-id="8590a-130">On the **New Region** page, click **Name** and then type a name for the network region.</span></span>

6.  <span data-ttu-id="8590a-131">单击“中央站点”\*\*\*\*，然后单击列表中的某个中央站点。</span><span class="sxs-lookup"><span data-stu-id="8590a-131">Click **Central site**, and then click a central site in the list.</span></span>

7.  <span data-ttu-id="8590a-132">或者，单击“说明”\*\*\*\*，然后键入其他信息以描述此网络站点。</span><span class="sxs-lookup"><span data-stu-id="8590a-132">Optionally, click **Description**, and then type additional information to describe this network site.</span></span>

8.  <span data-ttu-id="8590a-133">单击“提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8590a-133">Click **Commit**.</span></span>

9.  <span data-ttu-id="8590a-134">要为拓扑完成网络区域的创建，请使用其他区域的设置重复步骤 4 至 8。</span><span class="sxs-lookup"><span data-stu-id="8590a-134">To finish creating network regions for your topology, repeat steps 4 through 8 with settings for other regions.</span></span>

</div>

</div>

<div>

## <a name="modify-a-network-region"></a><span data-ttu-id="8590a-135">修改网络区域</span><span class="sxs-lookup"><span data-stu-id="8590a-135">Modify a Network Region</span></span>

<span data-ttu-id="8590a-136">修改现有网络区域的设置，以实现对基本区域信息的更改或者新功能所需的更改。</span><span class="sxs-lookup"><span data-stu-id="8590a-136">Modify settings for an existing network region to accommodate changes to the basic region information or changes required by a new feature.</span></span>

<div>

## <a name="to-modify-a-network-region-using-lync-server-management-shell"></a><span data-ttu-id="8590a-137">使用 Lync Server 命令行管理程序修改网络区域</span><span class="sxs-lookup"><span data-stu-id="8590a-137">To modify a network region using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="8590a-138">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8590a-138">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="8590a-139">运行 Set-CsNetworkRegion cmdlet 修改现有网络区域：</span><span class="sxs-lookup"><span data-stu-id="8590a-139">Run the Set-CsNetworkRegion cmdlet to modify an existing network region:</span></span>
    
        Set-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    <span data-ttu-id="8590a-140">例如：</span><span class="sxs-lookup"><span data-stu-id="8590a-140">For example:</span></span>
    
        Set-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "North American Region"
    
    <span data-ttu-id="8590a-p103">在此示例中，您通过更改说明修改了称为“NorthAmerica”的现有网络区域（在本主题前面的过程中创建）。如果“NorthAmerica”区域已存在说明，此命令将使用该值覆盖它；如果尚未设置说明，此命令会进行设置。</span><span class="sxs-lookup"><span data-stu-id="8590a-p103">In this example, you modified an existing network region called “NorthAmerica” (created using the procedures earlier in this topic) by changing the description. If a description existed for the “NorthAmerica” region, this command overwrites it with this value; if no description had been set, then this command sets it.</span></span>

3.  <span data-ttu-id="8590a-143">要修改其他网络区域，请使用其他区域的设置重复步骤 2。</span><span class="sxs-lookup"><span data-stu-id="8590a-143">To modify other network regions, repeat step 2 with settings for other regions.</span></span>

</div>

<div>

## <a name="to-modify-a-network-region-using-lync-server-control-panel"></a><span data-ttu-id="8590a-144">使用 Lync Server 控制面板修改网络区域</span><span class="sxs-lookup"><span data-stu-id="8590a-144">To modify a network region using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="8590a-145">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="8590a-145">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8590a-146">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="8590a-146">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="8590a-147">在左侧导航栏中，单击“网络配置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8590a-147">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="8590a-148">单击“区域”\*\*\*\* 导航按钮。</span><span class="sxs-lookup"><span data-stu-id="8590a-148">Click the **Region** navigation button.</span></span>

4.  <span data-ttu-id="8590a-149">在表中，单击要修改的网络区域。</span><span class="sxs-lookup"><span data-stu-id="8590a-149">In the table, click the network region that you want to modify.</span></span>

5.  <span data-ttu-id="8590a-150">单击“编辑”\*\*\*\*，然后单击“显示详细信息...”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8590a-150">Click **Edit**, and then click **Show details…**.</span></span>

6.  <span data-ttu-id="8590a-151">在“编辑区域”\*\*\*\* 页上，根据需要更改此网络区域的设置的值。</span><span class="sxs-lookup"><span data-stu-id="8590a-151">On the **Edit Region** page, change the values for this network region’s settings as appropriate.</span></span>

7.  <span data-ttu-id="8590a-152">单击“提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8590a-152">Click **Commit**.</span></span>

8.  <span data-ttu-id="8590a-153">要完成网络区域的修改，请使用其他区域的设置重复步骤 4 至 7。</span><span class="sxs-lookup"><span data-stu-id="8590a-153">To finish modify network regions, repeat steps 4 through 7 with settings for other regions.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

