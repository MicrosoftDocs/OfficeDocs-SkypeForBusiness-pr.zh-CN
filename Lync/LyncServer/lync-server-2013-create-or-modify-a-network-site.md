---
title: Lync Server 2013：创建或修改网络站点
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a network site
ms:assetid: 14e24856-9996-4da4-9f31-300940bdf5aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398218(v=OCS.15)
ms:contentKeyID: 48183488
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ed721a48b12a497b25d58e7ebb65ff3a91980904
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722559"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-network-site-in-lync-server-2013"></a><span data-ttu-id="7f104-102">在 Lync Server 2013 中创建或修改网络站点</span><span class="sxs-lookup"><span data-stu-id="7f104-102">Create or modify a network site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7f104-103">_**主题上次修改时间：** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="7f104-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="7f104-104">呼叫许可控制（CAC）、E9-1 和媒体旁路部署依赖于定义的*网络站点*的配置，并且与网络区域之间始终关联。</span><span class="sxs-lookup"><span data-stu-id="7f104-104">Call admission control (CAC), E9-1-1, and media bypass deployments rely on the configuration of *network sites* which are defined within and always associated with a network region.</span></span> <span data-ttu-id="7f104-105">网络站点表示分支机构位置、一组建筑物或校园。</span><span class="sxs-lookup"><span data-stu-id="7f104-105">A network site represents a branch office location, a set of buildings, or a campus.</span></span> <span data-ttu-id="7f104-106">网络站点表示具有相似带宽的子网的集合。</span><span class="sxs-lookup"><span data-stu-id="7f104-106">Network sites represent collections of subnets with similar bandwidth.</span></span>

<span data-ttu-id="7f104-107">使用以下过程创建或修改网络站点。</span><span class="sxs-lookup"><span data-stu-id="7f104-107">Use the following procedures to create or modify network sites.</span></span> <span data-ttu-id="7f104-108">例如，如果已为一个语音功能创建了网络网站，则不需要创建新的网络网站;其他语音功能将使用这些相同的网站。</span><span class="sxs-lookup"><span data-stu-id="7f104-108">For example, if you have already created network sites for one Voice feature, you do not need to create new network sites; other Voice features will use those same sites.</span></span> <span data-ttu-id="7f104-109">但是，可能需要修改现有的网络站点定义来应用特定于功能的设置。</span><span class="sxs-lookup"><span data-stu-id="7f104-109">You may, however, need to modify an existing network site definition to apply feature-specific settings.</span></span> <span data-ttu-id="7f104-110">例如，如果已为 E9-1-1 创建了网络站点，则需要在部署呼叫允许控制的过程中修改该网络站点，以便应用带宽策略配置文件。</span><span class="sxs-lookup"><span data-stu-id="7f104-110">For example, if you created a network site for E9-1-1, you need to modify the network site during deployment of call admission control to apply a bandwidth policy profile.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7f104-111">无论它们位于何处，您都可以在适用于每个功能的部署文档中找到与高级语音功能相关的网络站点的特定示例和要求：</span><span class="sxs-lookup"><span data-stu-id="7f104-111">Where they exist, you can find specific examples and requirements for network sites as they pertain to an advanced Voice feature in the Deployment documentation for each feature:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="7f104-112"><A href="lync-server-2013-configure-network-sites-for-cac.md">在 Lync Server 2013 中配置 CAC 的网络站点</A></span><span class="sxs-lookup"><span data-stu-id="7f104-112"><A href="lync-server-2013-configure-network-sites-for-cac.md">Configure network sites for CAC in Lync Server 2013</A></span></span></P></LI></UL>



</div>

<span data-ttu-id="7f104-113">有关使用网络站点的详细信息，请参阅以下 cmdlet 的 Lync Server Management Shell 文档：</span><span class="sxs-lookup"><span data-stu-id="7f104-113">For details about working with network sites, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="7f104-114">New-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="7f104-114">New-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)

  - [<span data-ttu-id="7f104-115">Get-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="7f104-115">Get-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)

  - [<span data-ttu-id="7f104-116">Set-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="7f104-116">Set-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)

  - [<span data-ttu-id="7f104-117">Remove-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="7f104-117">Remove-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)

<div>

## <a name="create-a-network-site"></a><span data-ttu-id="7f104-118">创建网络网站</span><span class="sxs-lookup"><span data-stu-id="7f104-118">Create a Network Site</span></span>

<span data-ttu-id="7f104-119">创建可由呼叫许可控制、E9-1 或媒体旁路使用的网络区域。</span><span class="sxs-lookup"><span data-stu-id="7f104-119">Create a network region that can be used by call admission control, E9-1-1, or media bypass.</span></span>

<div>

## <a name="to-create-a-network-site-by-using-management-shell"></a><span data-ttu-id="7f104-120">使用命令行管理程序创建网络站点</span><span class="sxs-lookup"><span data-stu-id="7f104-120">To create a network site by using Management Shell</span></span>

1.  <span data-ttu-id="7f104-121">启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="7f104-121">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="7f104-122">运行 New-CsNetworkSite cmdlet 创建网络站点：</span><span class="sxs-lookup"><span data-stu-id="7f104-122">Run the New-CsNetworkSite cmdlet to create network sites:</span></span>
    
        New-CsNetworkSite -NetworkSiteID <string>
    
    <span data-ttu-id="7f104-123">例如：</span><span class="sxs-lookup"><span data-stu-id="7f104-123">For example:</span></span>
    
        New-CsNetworkSite -NetworkSiteID Chicago -Description "Corporate headquarters"-NetworkRegionID NorthAmerica
    
    <span data-ttu-id="7f104-124">在此示例中，您创建了一个称为“Chicago”的网络站点，该站点位于“NorthAmerica”网络区域。</span><span class="sxs-lookup"><span data-stu-id="7f104-124">In this example, you created a network site called “Chicago” that is in the “NorthAmerica” network region.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7f104-125">为了成功运行此命令，NorthAmerica 网络区域必须已经存在。</span><span class="sxs-lookup"><span data-stu-id="7f104-125">The NorthAmerica network region must already exist for this command to run successfully.</span></span>

    
    </div>

3.  <span data-ttu-id="7f104-126">要为拓扑完成网络站点的创建，请使用其他站点的设置重复步骤 2。</span><span class="sxs-lookup"><span data-stu-id="7f104-126">To finish creating network sites for your topology, repeat step 2 with settings for other sites.</span></span>

</div>

<div>

## <a name="to-create-a-network-site-by-using-lync-server-control-panel"></a><span data-ttu-id="7f104-127">使用 Lync Server "控制面板" 创建网络网站</span><span class="sxs-lookup"><span data-stu-id="7f104-127">To create a network site by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="7f104-128">打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="7f104-128">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="7f104-129">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="7f104-129">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="7f104-130">在左侧导航栏中，单击“网络配置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7f104-130">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="7f104-131">单击“站点”\*\*\*\* 导航按钮。</span><span class="sxs-lookup"><span data-stu-id="7f104-131">Click the **Site** navigation button.</span></span>

4.  <span data-ttu-id="7f104-132">单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7f104-132">Click **New**.</span></span>

5.  <span data-ttu-id="7f104-133">在“新建站点”\*\*\*\* 页上，单击“名称”\*\*\*\*，然后键入网络站点的名称。</span><span class="sxs-lookup"><span data-stu-id="7f104-133">On the **New Site** page, click **Name** and then type a name for the network site.</span></span>

6.  <span data-ttu-id="7f104-134">单击“区域”\*\*\*\*，然后单击列表中的某个区域。</span><span class="sxs-lookup"><span data-stu-id="7f104-134">Click **Region**, and then click a region in the list.</span></span>

7.  <span data-ttu-id="7f104-135">或者，单击“带宽策略”\*\*\*\*，然后单击列表中的某个带宽策略。</span><span class="sxs-lookup"><span data-stu-id="7f104-135">Optionally, click **Bandwidth policy**, and then click a bandwidth policy in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7f104-136">只有在站点上部署呼叫允许控制时才需要带宽策略。</span><span class="sxs-lookup"><span data-stu-id="7f104-136">Bandwidth policy is required only if you deploy call admission control at the site.</span></span>

    
    </div>

8.  <span data-ttu-id="7f104-137">或者，单击“位置策略”\*\*\*\*，然后单击列表中的某个位置策略。</span><span class="sxs-lookup"><span data-stu-id="7f104-137">Optionally, click **Location policy**, and then click a location policy in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7f104-138">只有在站点上部署 E9-1-1 时才需要位置策略。</span><span class="sxs-lookup"><span data-stu-id="7f104-138">Location policy is required only if you deploy E9-1-1 at the site.</span></span>

    
    </div>

9.  <span data-ttu-id="7f104-139">或者，单击“说明”\*\*\*\*，然后键入其他信息以描述此网络站点。</span><span class="sxs-lookup"><span data-stu-id="7f104-139">Optionally, click **Description**, and then type additional information to describe this network site.</span></span>

10. <span data-ttu-id="7f104-140">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="7f104-140">Click **Commit**.</span></span>

11. <span data-ttu-id="7f104-141">要为拓扑完成网络站点的创建，请使用其他站点的设置重复步骤 4 至 10。</span><span class="sxs-lookup"><span data-stu-id="7f104-141">To finish creating network sites for your topology, repeat steps 4 through 10 with settings for other sites.</span></span>

</div>

</div>

<div>

## <a name="modify-a-network-site"></a><span data-ttu-id="7f104-142">修改网络网站</span><span class="sxs-lookup"><span data-stu-id="7f104-142">Modify a Network Site</span></span>

<span data-ttu-id="7f104-143">修改可由呼叫许可控制、E9-1 或媒体绕过使用的网络区域。</span><span class="sxs-lookup"><span data-stu-id="7f104-143">Modify a network region that can be used by call admission control, E9-1-1, or media bypass.</span></span>

<div>

## <a name="to-modify-a-network-site"></a><span data-ttu-id="7f104-144">修改网络网站</span><span class="sxs-lookup"><span data-stu-id="7f104-144">To modify a network site</span></span>

1.  <span data-ttu-id="7f104-145">启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="7f104-145">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="7f104-146">运行 Set-CsNetworkSite cmdlet 修改网络站点：</span><span class="sxs-lookup"><span data-stu-id="7f104-146">Run the Set-CsNetworkSite cmdlet to modify network sites:</span></span>
    
        Set-CsNetworkSite -Identity <string>
    
    <span data-ttu-id="7f104-147">例如：</span><span class="sxs-lookup"><span data-stu-id="7f104-147">For example:</span></span>
    
        Set-CsNetworkSite -Identity Albuquerque -NetworkRegionID NorthAmerica
    
    <span data-ttu-id="7f104-p104">在此示例中，称为“Albuquerque”的站点将移动到“NorthAmerica”网络区域。要修改网络站点配置以部署呼叫允许控制、E9-1-1 或媒体旁路，请分别运行带有 BWPolicyProfileID 参数或 LocationPolicy 参数的 Set-CsNetworkSite cmdlet 来修改网络站点设置。</span><span class="sxs-lookup"><span data-stu-id="7f104-p104">In this example, the site called “Albuquerque” is moved to the “NorthAmerica” network region. To modify the network site configuration to deploy call admission control, E9-1-1, or media bypass, modify the network site settings by running the Set-CsNetworkSite cmdlet with the BWPolicyProfileID or LocationPolicy parameter, respectively.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7f104-p105">尽管存在用于媒体旁路的 BypassID 参数，但强烈建议您不要覆盖自动生成的旁路 ID。您无需指定其他参数来为媒体旁路配置网络站点。</span><span class="sxs-lookup"><span data-stu-id="7f104-p105">Although the BypassID parameter exists for media bypass, we strongly recommend that you do not override automatically generated bypass IDs. You do not need to specify additional parameters to configure a network site for media bypass.</span></span>

    
    </div>

3.  <span data-ttu-id="7f104-152">要为拓扑完成网络站点的修改，请使用其他站点的设置重复步骤 2。</span><span class="sxs-lookup"><span data-stu-id="7f104-152">To finish modifying network sites for your topology, repeat step 2 with settings for other sites.</span></span>

</div>

<div>

## <a name="to-modify-a-network-site-by-using-lync-server-control-panel"></a><span data-ttu-id="7f104-153">使用 Lync Server "控制面板" 修改网络站点</span><span class="sxs-lookup"><span data-stu-id="7f104-153">To modify a network site by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="7f104-154">打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="7f104-154">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="7f104-155">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="7f104-155">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="7f104-156">在左侧导航栏中，单击“网络配置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7f104-156">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="7f104-157">单击“站点”\*\*\*\* 导航按钮。</span><span class="sxs-lookup"><span data-stu-id="7f104-157">Click the **Site** navigation button.</span></span>

4.  <span data-ttu-id="7f104-158">在表中，单击要修改的网络站点。</span><span class="sxs-lookup"><span data-stu-id="7f104-158">In the table, click the network site that you want to modify.</span></span>

5.  <span data-ttu-id="7f104-159">单击“编辑”\*\*\*\*，然后单击“显示详细信息...”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7f104-159">Click **Edit**, and then click **Show details…**.</span></span>

6.  <span data-ttu-id="7f104-160">在“编辑站点”\*\*\*\* 页上，根据需要更改此网络站点的设置的值。</span><span class="sxs-lookup"><span data-stu-id="7f104-160">On the **Edit Site** page, change the values for this network site’s settings as appropriate.</span></span>

7.  <span data-ttu-id="7f104-161">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="7f104-161">Click **Commit**.</span></span>

8.  <span data-ttu-id="7f104-162">要完成网络站点的修改，请使用其他站点的设置重复步骤 4 至 7。</span><span class="sxs-lookup"><span data-stu-id="7f104-162">To finish modify network sites, repeat steps 4 through 7 with settings for other sites.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

