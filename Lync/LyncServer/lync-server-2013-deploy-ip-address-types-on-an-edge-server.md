---
title: Lync Server 2013：在边缘服务器上部署 IP 地址类型
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploy IP address types on an Edge Server
ms:assetid: 6e2fe7e8-6e90-4d1a-8fc5-e3be92c46571
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204984(v=OCS.15)
ms:contentKeyID: 48184435
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a094a39fd74ab30ee1dd3a5a3da4e777bcf7e338
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830573"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-ip-address-types-on-an-edge-server-for-lync-server-2013"></a><span data-ttu-id="2a660-102">在 Lync Server 2013 边缘服务器上部署 IP 地址类型</span><span class="sxs-lookup"><span data-stu-id="2a660-102">Deploy IP address types on an Edge Server for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2a660-103">_**主题上次修改时间:** 2012-06-14_</span><span class="sxs-lookup"><span data-stu-id="2a660-103">_**Topic Last Modified:** 2012-06-14_</span></span>

<span data-ttu-id="2a660-104">使用拓扑生成器, 执行以下过程中的步骤以在 Edge 服务器上部署 IP 地址类型。</span><span class="sxs-lookup"><span data-stu-id="2a660-104">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on an Edge Server.</span></span>

<div>

## <a name="to-deploy-ip-address-types-on-an-edge-server"></a><span data-ttu-id="2a660-105">在边缘服务器上部署 IP 地址类型</span><span class="sxs-lookup"><span data-stu-id="2a660-105">To deploy IP address types on an Edge Server</span></span>

1.  <span data-ttu-id="2a660-106">在拓扑生成器中, 在 "**边缘池**" 下, 右键单击池中的服务器, 然后选择 "**编辑属性**"。</span><span class="sxs-lookup"><span data-stu-id="2a660-106">In Topology Builder, under **Edge pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="2a660-107">(或者, 选择服务器, 然后从 "**操作**" 菜单中单击 "**编辑属性**"。)</span><span class="sxs-lookup"><span data-stu-id="2a660-107">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

2.  <span data-ttu-id="2a660-p102">在“**编辑属性**”窗口中，选择要支持的 IP 地址配置。下图显示用于内部接口和外部接口的双协议栈配置。</span><span class="sxs-lookup"><span data-stu-id="2a660-p102">In the **Edit Properties** window, select the IP address configuration that you want to support. The following figures show a dual stack configuration for the internal interface and the external interface.</span></span>
    
    <span data-ttu-id="2a660-110">**双协议栈边缘服务器内部接口**</span><span class="sxs-lookup"><span data-stu-id="2a660-110">**Dual stacked Edge Server internal interface**</span></span>
    
    <span data-ttu-id="2a660-111">![Lync Server 常规属性页面](images/JJ204984.5b0883ee-b9f2-4a21-91a9-3286d0beb63b(OCS.15).png "Lync Server 常规属性页面")</span><span class="sxs-lookup"><span data-stu-id="2a660-111">![Lync Server general properties page](images/JJ204984.5b0883ee-b9f2-4a21-91a9-3286d0beb63b(OCS.15).png "Lync Server general properties page")</span></span>
    
    <span data-ttu-id="2a660-112">**双协议栈边缘服务器外部接口**</span><span class="sxs-lookup"><span data-stu-id="2a660-112">**Dual stacked Edge Server external interface**</span></span>
    
    <span data-ttu-id="2a660-113">![Lync Server 下一跃点/外部配置页面](images/JJ204984.2aa00ce2-ba50-40aa-bbf1-78636016daf9(OCS.15).png "Lync Server 下一跃点/外部配置页面")</span><span class="sxs-lookup"><span data-stu-id="2a660-113">![Lync Server next hop/external configuration page](images/JJ204984.2aa00ce2-ba50-40aa-bbf1-78636016daf9(OCS.15).png "Lync Server next hop/external configuration page")</span></span>

3.  <span data-ttu-id="2a660-114">对于您选择的每个地址类型，必须提供适当的内部和外部地址。</span><span class="sxs-lookup"><span data-stu-id="2a660-114">For each address type that you select, you must supply appropriate internal and external addresses.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

