---
title: Lync Server 2013：设置前端服务器和前端池
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Front End Servers and Front End pools
ms:assetid: c88526f9-69e2-47dd-b3d7-056139d74fb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398827(v=OCS.15)
ms:contentKeyID: 48185381
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b912eca536960bccc09c5e7a14c9adc245fe69e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732192"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-front-end-servers-and-front-end-pools-for-lync-server-2013"></a><span data-ttu-id="a4647-102">为 Lync Server 2013 设置前端服务器和前端池</span><span class="sxs-lookup"><span data-stu-id="a4647-102">Setting up Front End Servers and Front End pools for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a4647-103">_**主题上次修改时间：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="a4647-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="a4647-104">本部分将指导你安装 Lync Server 2013 并为标准版服务器和前端池设置服务器角色，包括前端服务器和与前端服务器 collocated 的任何服务器角色。</span><span class="sxs-lookup"><span data-stu-id="a4647-104">This section guides you through installing Lync Server 2013 and setting up the server roles for the Standard Edition server and the Front End pool, including the Front End Servers and any server roles that are collocated with the Front End Servers.</span></span> <span data-ttu-id="a4647-105">若要安装和设置服务器角色，请在要安装服务器角色的每台计算机上运行 Lync Server 部署向导。</span><span class="sxs-lookup"><span data-stu-id="a4647-105">To install and set up server roles, you run the Lync Server Deployment Wizard on each computer on which you are installing a server role.</span></span> <span data-ttu-id="a4647-106">使用部署向导完成所有四个部署步骤，包括安装本地配置存储、安装前端服务器、配置证书和启动服务。</span><span class="sxs-lookup"><span data-stu-id="a4647-106">You use the Deployment Wizard to complete all four deployment steps, including installing the Local Configuration store, installing the Front End Servers, configuring certificates, and starting services.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a4647-107">必须已成功发布拓扑，您才能设置服务器角色。</span><span class="sxs-lookup"><span data-stu-id="a4647-107">Before you can set up server roles, you must have successfully published a topology.</span></span> <span data-ttu-id="a4647-108">有关发布拓扑的详细信息，请参阅<A href="lync-server-2013-finalizing-and-implementing-the-topology-design.md">在 Lync Server 2013 中完成和实施拓扑设计</A>。</span><span class="sxs-lookup"><span data-stu-id="a4647-108">For details about publishing a topology, see <A href="lync-server-2013-finalizing-and-implementing-the-topology-design.md">Finalizing and implementing the topology design in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a4647-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="a4647-109">In This Section</span></span>

  - [<span data-ttu-id="a4647-110">在 Lync Server 2013 中安装本地配置存储</span><span class="sxs-lookup"><span data-stu-id="a4647-110">Install the Local Configuration store in Lync Server 2013</span></span>](lync-server-2013-install-the-local-configuration-store.md)

  - [<span data-ttu-id="a4647-111">安装适用于 Lync Server 2013 的服务器组件</span><span class="sxs-lookup"><span data-stu-id="a4647-111">Install server components for Lync Server 2013</span></span>](lync-server-2013-install-lync-server-server-components.md)

  - [<span data-ttu-id="a4647-112">在 Lync Server 2013 中为服务器配置证书</span><span class="sxs-lookup"><span data-stu-id="a4647-112">Configure certificates for servers in Lync Server 2013</span></span>](lync-server-2013-configure-certificates-for-servers.md)

  - [<span data-ttu-id="a4647-113">为 Lync Server 2013 启动服务器上的服务</span><span class="sxs-lookup"><span data-stu-id="a4647-113">Start services on servers for Lync Server 2013</span></span>](lync-server-2013-start-services-on-servers.md)

  - [<span data-ttu-id="a4647-114">在 Lync Server 2013 中测试池部署</span><span class="sxs-lookup"><span data-stu-id="a4647-114">Test the pool deployment in Lync Server 2013</span></span>](lync-server-2013-test-the-pool-deployment.md)

  - [<span data-ttu-id="a4647-115">在 Lync Server 2013 中测试 Standard Edition 服务器</span><span class="sxs-lookup"><span data-stu-id="a4647-115">Test the Standard Edition server in Lync Server 2013</span></span>](lync-server-2013-test-the-standard-edition-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

