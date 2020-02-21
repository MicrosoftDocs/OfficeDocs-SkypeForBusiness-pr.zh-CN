---
title: Lync Server 2013：启动控制器上的服务
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Start services on the Director
ms:assetid: 095b13e1-e788-4b80-93fa-5c5e7498678b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398146(v=OCS.15)
ms:contentKeyID: 48183351
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da0b18e6c5c64d7aee14eb955c9a3d3757f06835
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181705"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="start-services-on-the-director-in-lync-server-2013"></a><span data-ttu-id="85f45-102">在 Lync Server 2013 中的控制器上启动服务</span><span class="sxs-lookup"><span data-stu-id="85f45-102">Start services on the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="85f45-103">_**上次修改的主题：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="85f45-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="85f45-104">在安装本地配置存储后，安装 Lync Server 组件，并在 Director 上配置证书后，必须在服务器上启动 Lync Server 服务。</span><span class="sxs-lookup"><span data-stu-id="85f45-104">After you install the Local Configuration Store, install the Lync Server Components, and configure certificates on a Director, you must start the Lync Server services on the server.</span></span> <span data-ttu-id="85f45-105">可以使用以下过程来启动部署中每个控制器上的服务。</span><span class="sxs-lookup"><span data-stu-id="85f45-105">You can use the following procedure to start services on each Director in your deployment.</span></span>

<div>

## <a name="to-start-services-on-a-director"></a><span data-ttu-id="85f45-106">启动控制器上的服务</span><span class="sxs-lookup"><span data-stu-id="85f45-106">To start services on a Director</span></span>

1.  <span data-ttu-id="85f45-107">在 Lync Server 部署向导中，在 " **Lync server 2013** " 页上，单击 "**步骤4：启动服务**" 旁边的 "**运行**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="85f45-107">In the Lync Server Deployment Wizard, on the **Lync Server 2013** page, click the **Run** button next to **Step 4: Start Services**.</span></span>

2.  <span data-ttu-id="85f45-108">在 "**启动服务**" 页上，单击 "**下一步**" 以启动服务器上的 Lync Server 服务。</span><span class="sxs-lookup"><span data-stu-id="85f45-108">On the **Start Services** page, click **Next** to start the Lync Server services on the server.</span></span>

3.  <span data-ttu-id="85f45-109">在“正在执行命令”\*\*\*\* 页上，成功启动所有服务后，单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="85f45-109">On the **Executing Commands** page, after all services have started successfully, click **Finish**.</span></span>

4.  <span data-ttu-id="85f45-110">在“步骤 4: 启动服务”\*\*\*\* 下，单击“服务状态(可选)”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="85f45-110">Below **Step 4: Start Services**, click **Services Status (Optional)**.</span></span>

5.  <span data-ttu-id="85f45-111">在服务器上的 "**服务**" Microsoft 管理控制台（MMC）中，验证所有 Lync server 2013 服务是否正在运行。</span><span class="sxs-lookup"><span data-stu-id="85f45-111">In the **Services** Microsoft Management Console (MMC) on the server, verify that all of the Lync Server 2013 services are running.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

