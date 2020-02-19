---
title: Lync Server 2013：在拓扑生成器中定义中介服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a Mediation Server in Topology Builder
ms:assetid: 59d8f5ba-5064-4ea5-b4bf-2b9736e0fedd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398391(v=OCS.15)
ms:contentKeyID: 48184217
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b0109a7091870b7409fd9bc20b9de3abd3b2f3a4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138263"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="define-a-mediation-server-in-topology-builder-in-lync-server-2013"></a><span data-ttu-id="4f3ea-102">在 Lync Server 2013 的拓扑生成器中定义中介服务器</span><span class="sxs-lookup"><span data-stu-id="4f3ea-102">Define a Mediation Server in Topology Builder in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f3ea-103">_**上次修改的主题：** 2013-03-25_</span><span class="sxs-lookup"><span data-stu-id="4f3ea-103">_**Topic Last Modified:** 2013-03-25_</span></span>

<span data-ttu-id="4f3ea-104">按照本主题中的步骤使用拓扑生成器定义独立中介服务器或在尚未部署企业语音的站点上具有前端池的池并置。</span><span class="sxs-lookup"><span data-stu-id="4f3ea-104">Follow the steps in this topic to use Topology Builder to define a stand-alone Mediation Server or a pool collocated with a Front End pool at a site for which you did not previously deploy Enterprise Voice.</span></span>

<span data-ttu-id="4f3ea-105">可以使用 Administrators 组成员的帐户定义拓扑。</span><span class="sxs-lookup"><span data-stu-id="4f3ea-105">You can define a topology using an account that is a member of the Administrators group.</span></span>

<div>

## <a name="define-mediation-server-collocated-to-a-front-end-pool"></a><span data-ttu-id="4f3ea-106">定义中介服务器并置到前端池</span><span class="sxs-lookup"><span data-stu-id="4f3ea-106">Define Mediation Server collocated to a Front End pool</span></span>

<span data-ttu-id="4f3ea-107">按照本主题中的步骤使用拓扑生成器将中介服务器并置定义到尚未部署企业语音的站点中的前端池。</span><span class="sxs-lookup"><span data-stu-id="4f3ea-107">Follow the steps in this topic to use Topology Builder to define a Mediation Server collocated to a Front End pool in a site where Enterprise Voice has not been previously deployed.</span></span>

<div>

## <a name="to-add-a-mediation-server-to-a-front-end-pool"></a><span data-ttu-id="4f3ea-108">将中介服务器添加到前端池</span><span class="sxs-lookup"><span data-stu-id="4f3ea-108">To Add a Mediation Server to a Front End pool</span></span>

1.  <span data-ttu-id="4f3ea-109">启动拓扑生成器：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server 拓扑生成器**"。</span><span class="sxs-lookup"><span data-stu-id="4f3ea-109">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="4f3ea-110">在拓扑生成器中的控制台树中，展开要为其定义前端池的网站的名称。</span><span class="sxs-lookup"><span data-stu-id="4f3ea-110">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Front End pool.</span></span>

3.  <span data-ttu-id="4f3ea-111">在控制台树中，右键单击所需的前端池类型，然后单击 "**新建前端池"。**</span><span class="sxs-lookup"><span data-stu-id="4f3ea-111">In the console tree, right-click the type of Front End pool you want, and then click **New Front End pool..**.</span></span>

4.  <span data-ttu-id="4f3ea-112">在“定义新的前端池”\*\*\*\* 向导中导航，直到到达“选择并置服务器角色”\*\*\*\* 页。</span><span class="sxs-lookup"><span data-stu-id="4f3ea-112">Navigate through the **Define New Front End Pool** wizard until you reach the **Select collocated server roles** page.</span></span>

5.  <span data-ttu-id="4f3ea-113">在 "**选择并置服务器角色**" 中，选中 "**并置中介服务器**" 选项。</span><span class="sxs-lookup"><span data-stu-id="4f3ea-113">In **Select collocated server roles**, check the option **Collocate Mediation Server**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="4f3ea-114">如果所选的前端池的类型为 Enterprise Edition，则中介服务器组件将安装在该前端池的所有前端服务器上。</span><span class="sxs-lookup"><span data-stu-id="4f3ea-114">If the type of Front End pool you selected is the Enterprise Edition, then the Mediation Server component will be installed on all the Front End Servers of that Front End pool.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="4f3ea-115">中介服务器使用的<STRONG>下一个跃点池</STRONG>将是中介服务器在其中并置的前端池。</span><span class="sxs-lookup"><span data-stu-id="4f3ea-115">The <STRONG>Next hop pool</STRONG> used by the Mediation Server will be the Front End pool where the Mediation Server is collocated on.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="4f3ea-116">中介服务器使用的<STRONG>边缘池</STRONG>将是与在其中并置中介服务器的前端池关联的同一个边缘池。</span><span class="sxs-lookup"><span data-stu-id="4f3ea-116">The <STRONG>Edge pool</STRONG> used by the Mediation Server will be the same Edge pool associated with the Front End pool where the Mediation Server is collocated on.</span></span></P></LI></UL>

    
    </div>

6.  <span data-ttu-id="4f3ea-117">单击 "**设为默认值**" 以使用此前端池将来自 Microsoft Office 通信服务器 2007 R2 的呼叫路由到 PSTN。</span><span class="sxs-lookup"><span data-stu-id="4f3ea-117">Click **Make Default** to use this Front End pool to route calls from Microsoft Office Communications Server 2007 R2 to the PSTN.</span></span>

7.  <span data-ttu-id="4f3ea-118">完成将一个或多个对等方关联到前端池时，请单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="4f3ea-118">Click **Finish** when you are finished associating one or more peers to the Front End pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4f3ea-119">在继续执行企业语音部署过程中的下一步之前，请确保中介服务器池（即具有中介服务器组件并置的前端池）使用您指定的 Fqdn。</span><span class="sxs-lookup"><span data-stu-id="4f3ea-119">Before you proceed to the next step in the Enterprise Voice deployment process, make sure that the Mediation Server pool (i.e. Front End pool with the Mediation Server component collocated) is using the FQDNs that you specified.</span></span>

    
    </div>

8.  <span data-ttu-id="4f3ea-120">接下来，按照部署指南文档中的 "[发布 Lync server 2013](lync-server-2013-publish-the-topology.md)中的拓扑" 中的过程操作，将中介服务器添加到拓扑中，然后再转到修改中介服务器侦听端口的下一步（如果需要）。</span><span class="sxs-lookup"><span data-stu-id="4f3ea-120">Next, follow the procedures in [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md) in the Deployment Guide documentation to add the Mediation Server to your topology before proceeding to the next step of modifying the listening ports of the Mediation Server if needed.</span></span> <span data-ttu-id="4f3ea-121">每次使用拓扑生成器定义或修改拓扑时，都必须发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="4f3ea-121">You must publish your topology each time you use Topology Builder to define or modify your topology.</span></span>

</div>

</div>

<div>

## <a name="define-stand-alone-mediation-server"></a><span data-ttu-id="4f3ea-122">定义独立中介服务器</span><span class="sxs-lookup"><span data-stu-id="4f3ea-122">Define stand-alone Mediation Server</span></span>

<span data-ttu-id="4f3ea-123">按照本主题中的步骤使用拓扑生成器在尚未部署企业语音的站点上定义独立中介服务器或池。</span><span class="sxs-lookup"><span data-stu-id="4f3ea-123">Follow the steps in this topic to use Topology Builder to define a stand-alone Mediation Server or pool at a site where Enterprise Voice has not been previously deployed.</span></span>

<span data-ttu-id="4f3ea-124">如果您已经在此站点上部署了并置到前端池的中介服务器，则可以跳过此部分并[在 lync server 2013 中安装中介服务器的文件](lync-server-2013-install-the-files-for-mediation-server.md)，然后再继续在[lync Server 2013 中配置中继](lync-server-2013-configuring-trunks.md)。</span><span class="sxs-lookup"><span data-stu-id="4f3ea-124">If you already deployed Mediation Servers collocated to Front End pools at this site, you can skip this section and [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) before proceeding to [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4f3ea-125">本节假定您已经至少设置了一个前端池，如在<A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Lync server 2013 中定义和配置前端池或 Standard Edition server</A>以及部署指南文档中的在<A href="lync-server-2013-publish-the-topology.md">lync Server 2013 中发布拓扑</A>中所述。</span><span class="sxs-lookup"><span data-stu-id="4f3ea-125">This section assumes that you have already setup at least one Front End pool, as described in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</A> and <A href="lync-server-2013-publish-the-topology.md">Publish the topology in Lync Server 2013</A> in the Deployment Guide documentation.</span></span>



</div>

<div>

## <a name="to-add-a-mediation-server"></a><span data-ttu-id="4f3ea-126">添加中介服务器</span><span class="sxs-lookup"><span data-stu-id="4f3ea-126">To Add a Mediation Server</span></span>

1.  <span data-ttu-id="4f3ea-127">启动拓扑生成器：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server 拓扑生成器**"。</span><span class="sxs-lookup"><span data-stu-id="4f3ea-127">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="4f3ea-128">在拓扑生成器中的控制台树中，展开要为其定义中介服务器的站点的名称。</span><span class="sxs-lookup"><span data-stu-id="4f3ea-128">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Mediation Server.</span></span>

3.  <span data-ttu-id="4f3ea-129">在控制台树中，右键单击 "**中介池**" 节点，然后单击 "**中介服务器池**"。</span><span class="sxs-lookup"><span data-stu-id="4f3ea-129">In the console tree, right-click the **Mediation pools** node, and then click **Mediation Server pool**.</span></span>

4.  <span data-ttu-id="4f3ea-130">在 "**定义新的中介池**" 中，键入中介服务器池完全限定的域名（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="4f3ea-130">In **Define New Mediation Pool**, type the Mediation Server pool fully qualified domain name (FQDN).</span></span>

5.  <span data-ttu-id="4f3ea-131">接下来，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="4f3ea-131">Next, do one of the following:</span></span>
    
      - <span data-ttu-id="4f3ea-132">如果要在池中部署多个中介服务器以提供高可用性，请选择 "**多计算机池**"。</span><span class="sxs-lookup"><span data-stu-id="4f3ea-132">If you want to deploy multiple Mediation Servers in the pool to provide high availability, then select **Multiple computer pool**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="4f3ea-133">您必须部署 DNS 负载平衡，以支持具有多个中介服务器的中介服务器池。</span><span class="sxs-lookup"><span data-stu-id="4f3ea-133">You must deploy DNS load balancing to support Mediation Server pools that have multiple Mediation Servers.</span></span> <span data-ttu-id="4f3ea-134">有关详细信息，请参阅规划文档中的在<A href="lync-server-2013-dns-load-balancing.md">Lync server 2013 中的 dns 负载平衡</A>的 "在中介服务器池上使用 Dns 负载平衡" 部分。</span><span class="sxs-lookup"><span data-stu-id="4f3ea-134">For details, see the Using DNS Load Balancing on Mediation Server Pools section of <A href="lync-server-2013-dns-load-balancing.md">DNS load balancing in Lync Server 2013</A> in the Planning documentation.</span></span>

        
        </div>
    
      - <span data-ttu-id="4f3ea-135">如果您只希望在池中部署一个中介服务器，因为您不需要高可用性，则选择 "**单计算机池**"。</span><span class="sxs-lookup"><span data-stu-id="4f3ea-135">If you want to deploy only one Mediation Server in the pool because you do not require high availability, then select **Single computer pool**.</span></span> <span data-ttu-id="4f3ea-136">跳过以下步骤。</span><span class="sxs-lookup"><span data-stu-id="4f3ea-136">Skip the following step.</span></span>

6.  <span data-ttu-id="4f3ea-137">如果在前一步骤中选择了“多计算机池”\*\*\*\*，那么在“定义此池中的计算机”\*\*\*\* 项上单击“计算机 FQDN”\*\*\*\*，键入此池中每个服务器的 FQDN，然后单击“添加”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4f3ea-137">If you selected **Multiple computer pool** in the previous step, on the **Define the computers in this pool** item, click **Computer FQDN**, type the FQDN of each server in the pool, and then click **Add**.</span></span> <span data-ttu-id="4f3ea-138">对要添加到池中的所有其他中介服务器重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="4f3ea-138">Repeat this step for all other Mediation Servers that you want to add to the pool.</span></span> <span data-ttu-id="4f3ea-139">定义该池中的所有计算机后，单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4f3ea-139">When you have defined all the computers in the pool, click **Next**.</span></span>

7.  <span data-ttu-id="4f3ea-140">在 "**选择下一个跃点**" 页上，单击 "**下一跃点池**"，单击将使用此中介服务器池的前端池的 FQDN，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="4f3ea-140">On the **Select the next hop** page, click **Next hop pool**, click the FQDN of the Front End pool that will use this Mediation Server pool, and then click **Next**.</span></span>

8.  <span data-ttu-id="4f3ea-141">在“选择边缘服务器”\*\*\*\* 页上执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="4f3ea-141">On the **Select an Edge Server** page, do one of the following:</span></span>
    
      - <span data-ttu-id="4f3ea-142">如果要为启用企业语音的外部用户提供 PSTN 连接，请在 "**选择此中介服务器使用的边缘池**" 下，单击将使用此中介服务器池的边缘服务器池的 FQDN，以提供与这些外部用户的 PSTN 连接，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="4f3ea-142">If you want to provide PSTN connectivity to external users enabled for Enterprise Voice, under **Select Edge Pool used by this Mediation Server**, click the FQDN of the Edge Server pool that will use this Mediation Server pool to provide PSTN connectivity to those external users, and then click **Next**.</span></span>
    
      - <span data-ttu-id="4f3ea-143">如果您不打算为外部用户启用企业语音，或者如果您不想在内部网络外部向用户提供 PSTN 连接，请单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="4f3ea-143">If you do not plan to enable external users for Enterprise Voice, or if you do not want to provide PSTN connectivity to users when they are outside the internal network, click **Next**.</span></span>

9.  <span data-ttu-id="4f3ea-144">接下来，按照部署文档中的 "[发布 Lync server 2013](lync-server-2013-publish-the-topology.md)中的拓扑" 中的过程操作，将中介服务器添加到拓扑中。</span><span class="sxs-lookup"><span data-stu-id="4f3ea-144">Next, follow the procedures in [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md) in the Deployment documentation to add the Mediation Server to the topology.</span></span> <span data-ttu-id="4f3ea-145">您必须在每次使用拓扑生成器生成或修改拓扑时发布拓扑，以便可以使用数据来安装运行 Lync Server 的服务器的文件。</span><span class="sxs-lookup"><span data-stu-id="4f3ea-145">You must publish your topology each time you use Topology Builder to build or modify your topology so that the data can be used to install the files for servers that are running Lync Server.</span></span> <span data-ttu-id="4f3ea-146">如有必要，请继续执行下列步骤来修改中介服务器上的侦听端口。</span><span class="sxs-lookup"><span data-stu-id="4f3ea-146">Then continue to the next steps to modify the listening ports on the Mediation Server, if necessary.</span></span>

</div>

</div>

<div>

## <a name="define-the-mediation-server-listening-ports"></a><span data-ttu-id="4f3ea-147">定义中介服务器侦听端口</span><span class="sxs-lookup"><span data-stu-id="4f3ea-147">Define the Mediation Server Listening Ports</span></span>

<span data-ttu-id="4f3ea-148">按照本主题中的步骤使用拓扑生成器定义中介服务器或池将接受来自网关对等的传入连接的侦听端口。</span><span class="sxs-lookup"><span data-stu-id="4f3ea-148">Follow the steps in this topic to use Topology Builder to define the listening ports a Mediation Server or pool will accept incoming connections from a gateway peer.</span></span>

<div>

## <a name="to-modify-the-mediation-server-listening-ports"></a><span data-ttu-id="4f3ea-149">修改中介服务器侦听端口</span><span class="sxs-lookup"><span data-stu-id="4f3ea-149">To Modify the Mediation Server Listening Ports</span></span>

1.  <span data-ttu-id="4f3ea-150">启动拓扑生成器：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server 拓扑生成器**"。</span><span class="sxs-lookup"><span data-stu-id="4f3ea-150">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="4f3ea-151">在拓扑生成器中的控制台树中，展开 "**中介池**" 节点，然后右键单击之前创建的中介服务器。</span><span class="sxs-lookup"><span data-stu-id="4f3ea-151">In Topology Builder, in the console tree, expand the **Mediation pools** node, and right-click the Mediation Server previously created.</span></span>

3.  <span data-ttu-id="4f3ea-152">默认情况下，中介服务器上的 SIP 侦听端口为来自 Lync Server 的 TLS 流量为5070，5067表示来自对等方（网关、PBXes 或 SBCs）的 TLS 流量。</span><span class="sxs-lookup"><span data-stu-id="4f3ea-152">By default, the SIP listening ports on the Mediation Server are 5070 for TLS traffic from Lync Server, 5067 for TLS traffic from peers (gateways, PBXes, or SBCs).</span></span> <span data-ttu-id="4f3ea-153">默认情况下，TCP 处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="4f3ea-153">TCP port is disabled by default.</span></span> <span data-ttu-id="4f3ea-154">如果有不支持 TLS 的网关，则必须启用 TCP 端口。</span><span class="sxs-lookup"><span data-stu-id="4f3ea-154">You must enable TCP port if you have gateways that do not support TLS.</span></span>

4.  <span data-ttu-id="4f3ea-155">指定所需的 TLS 或 TCP 侦听端口范围中介服务器将接受来自 PSTN 网关的传入连接。</span><span class="sxs-lookup"><span data-stu-id="4f3ea-155">Specify the desired TLS or TCP listening port range the Mediation Server will accept incoming connections from PSTN gateways.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4f3ea-156">如果未选中“启用 TCP 端口”<STRONG></STRONG>，则不需要输入 TCP 端口范围。</span><span class="sxs-lookup"><span data-stu-id="4f3ea-156">Entering a TCP port range is not required if <STRONG>Enable TCP port</STRONG> is not checked.</span></span> <span data-ttu-id="4f3ea-157">此设置是可选的。</span><span class="sxs-lookup"><span data-stu-id="4f3ea-157">This setting is optional.</span></span>

    
    </div>

<span data-ttu-id="4f3ea-158">接下来，在[lync server 2013 拓扑生成器中定义网关](lync-server-2013-define-a-gateway-in-topology-builder.md)，并按照在[Lync Server 2013 中安装中介服务器](lync-server-2013-install-the-files-for-mediation-server.md)中的文件中的步骤在池中的每台中介服务器上安装文件。</span><span class="sxs-lookup"><span data-stu-id="4f3ea-158">Next, [Define a gateway in Topology Builder in Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md) and install the files on each Mediation Server in the pool by following the procedures in [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md).</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

