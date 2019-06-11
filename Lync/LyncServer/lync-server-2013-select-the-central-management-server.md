---
title: Lync Server 2013：选择中央管理服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Select the Central Management Server
ms:assetid: 1ca6b7d0-125c-4727-aac4-2d683d23394d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204726(v=OCS.15)
ms:contentKeyID: 48183561
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: daa99142b1e0814335ea1ca1de8ecf5452029943
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822067"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="select-the-central-management-server-in-lync-server-2013"></a><span data-ttu-id="d303e-102">在 Lync Server 2013 中选择中央管理服务器</span><span class="sxs-lookup"><span data-stu-id="d303e-102">Select the Central Management Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d303e-103">_**主题上次修改时间:** 2012-01-02_</span><span class="sxs-lookup"><span data-stu-id="d303e-103">_**Topic Last Modified:** 2012-01-02_</span></span>

<span data-ttu-id="d303e-104">在定义和配置拓扑之前, 必须首先定义安装中央管理服务器的位置。</span><span class="sxs-lookup"><span data-stu-id="d303e-104">Before you can define and configure your topology, you must first define the location to install the Central Management Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d303e-105">只有在拓扑生成器中发布拓扑后, 此操作才会生效。</span><span class="sxs-lookup"><span data-stu-id="d303e-105">This will not take effect until you have published a topology in Topology Builder.</span></span> <span data-ttu-id="d303e-106">若要在创建和发布拓扑之前设置中央管理服务器, 请运行<STRONG>CSConfigurationStoreLocation</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="d303e-106">To set the Central Management Server before the topology is created and published, run <STRONG>Set-CSConfigurationStoreLocation</STRONG>.</span></span>



</div>

<div>

## <a name="to-select-the-central-management-server"></a><span data-ttu-id="d303e-107">选择中央管理服务器</span><span class="sxs-lookup"><span data-stu-id="d303e-107">To select the Central Management Server</span></span>

1.  <span data-ttu-id="d303e-108">启动拓扑生成器: 单击 "**开始**", 单击 "**所有程序**", 单击 " **Microsoft Lync server 2013**", 然后单击 " **Lync server 拓扑生成器**"。</span><span class="sxs-lookup"><span data-stu-id="d303e-108">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="d303e-109">右键单击 "Lync Server 2013" 节点, 然后单击 "**编辑属性**"。</span><span class="sxs-lookup"><span data-stu-id="d303e-109">Right-click the Lync Server 2013 node, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="d303e-110">在 "中央管理服务器" 窗格中, 选择要在其中安装中央管理服务器的前端服务器, 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="d303e-110">In the Central Management Server pane, select the Front End Server to install the Central Management Server on and then click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

