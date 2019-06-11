---
title: Lync Server 2013：发布拓扑
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Publish your topology
ms:assetid: bfed3829-7a54-4b5c-a7cb-28871acd35e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412935(v=OCS.15)
ms:contentKeyID: 48185287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3bd542db6acedbec75e475045ae2ace6d63d5469
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823663"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-your-topology-in-lync-server-2013"></a><span data-ttu-id="356b1-102">在 Lync Server 2013 中发布拓扑</span><span class="sxs-lookup"><span data-stu-id="356b1-102">Publish your topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="356b1-103">_**主题上次修改时间:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="356b1-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="356b1-104">每次使用拓扑生成器构建拓扑时, 必须将拓扑发布到中央管理存储中的数据库, 以便可以使用这些数据部署 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="356b1-104">Each time you use Topology Builder to build your topology, you must publish the topology to a database in the Central Management store so that the data can be used to deploy Lync Server 2013.</span></span> <span data-ttu-id="356b1-105">使用以下过程发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="356b1-105">Use the following procedure to publish your topology.</span></span>

<div>

## <a name="to-publish-the-topology"></a><span data-ttu-id="356b1-106">发布拓扑</span><span class="sxs-lookup"><span data-stu-id="356b1-106">To publish the topology</span></span>

1.  <span data-ttu-id="356b1-107">启动拓扑生成器: 单击 "**开始**", 单击 "**所有程序**", 单击 " **Microsoft Lync server 2013**", 然后单击 " **Lync server 拓扑生成器**"。</span><span class="sxs-lookup"><span data-stu-id="356b1-107">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="356b1-108">在拓扑生成器的控制台树中, 右键单击 " **Lync 2013**", 然后单击 "**发布拓扑**"。</span><span class="sxs-lookup"><span data-stu-id="356b1-108">In Topology Builder, in the console tree, right-click **Lync 2013**, and then click **Publish Topology**.</span></span>

3.  <span data-ttu-id="356b1-109">在向导的“**欢迎**”页上，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="356b1-109">On the **Welcome** page of the wizard, click **Next**.</span></span>

4.  <span data-ttu-id="356b1-110">在**拓扑生成器 "发现 CMS 存储**" 页面上, 单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="356b1-110">On the **Topology Builder found a CMS store** page, click **Next**.</span></span>

5.  <span data-ttu-id="356b1-111">在“**创建其他数据库**”页上，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="356b1-111">On the **Create other databases** page, click **Next**.</span></span>

6.  <span data-ttu-id="356b1-112">当状态指示 "已成功创建数据库" 时, 请执行下列操作:</span><span class="sxs-lookup"><span data-stu-id="356b1-112">When the status indicates that database creation succeeded, do the following:</span></span>
    
      - <span data-ttu-id="356b1-113">若要查看日志，请单击“**查看日志**”。</span><span class="sxs-lookup"><span data-stu-id="356b1-113">To view the log, click **View log**.</span></span>
    
      - <span data-ttu-id="356b1-114">若要关闭向导，请单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="356b1-114">To close the wizard, click **Finish**.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="356b1-115">如果这是边缘服务器或边缘池的全新安装, 则必须从现有前端服务器、前端池或标准版服务器导出 Edge 服务器配置。</span><span class="sxs-lookup"><span data-stu-id="356b1-115">If this is a new installation of an Edge Server or Edge pool, you must export the Edge Server configuration from an existing Front End Server, Front End pool, or Standard Edition server.</span></span> <span data-ttu-id="356b1-116">若要导出配置, 请参阅<A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">导出 Lync Server 2013 拓扑并将其复制到外部媒体以进行边缘安装</A>。</span><span class="sxs-lookup"><span data-stu-id="356b1-116">To export the configuration, see <A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">Export your Lync Server 2013 topology and copy it to external media for edge installation</A>.</span></span> <span data-ttu-id="356b1-117">您将在边缘服务器的设置和部署阶段通过 Lync Server 部署向导导入来自外部媒体或网络共享的配置文件。</span><span class="sxs-lookup"><span data-stu-id="356b1-117">You will import the configuration file from the external media or network share during the setup and deployment phase of the Edge Servers through the Lync Server Deployment Wizard.</span></span><BR><span data-ttu-id="356b1-118">当边缘服务器运行且本地配置管理存储数据库与内部部署复制后, 将发布对 Lync Server 2013 配置的后续更新并将其复制到边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="356b1-118">Once the Edge Servers are operational and the local configuration management store database is replicating with the internal deployment, subsequent updates to the Lync Server 2013 configuration will be published and replicated to the Edge Servers.</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

