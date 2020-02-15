---
title: Lync Server 2013：启动服务器上的服务
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Start services on servers
ms:assetid: fa26eaed-0529-4f32-9f3f-f32c4bd4b1c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413059(v=OCS.15)
ms:contentKeyID: 48185912
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee5e58f316acde9e1aadeee80cfccb6ee1b189be
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007701"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="start-services-on-servers-for-lync-server-2013"></a><span data-ttu-id="e0f90-102">为 Lync Server 2013 启动服务器上的服务</span><span class="sxs-lookup"><span data-stu-id="e0f90-102">Start services on servers for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e0f90-103">_**上次修改的主题：** 2014-09-03_</span><span class="sxs-lookup"><span data-stu-id="e0f90-103">_**Topic Last Modified:** 2014-09-03_</span></span>

<span data-ttu-id="e0f90-104">要成功完成此过程，应以 RTCUniversalServerAdmins 组成员或委派了相应权限的用户身份登录。</span><span class="sxs-lookup"><span data-stu-id="e0f90-104">To successfully complete this procedure you should be logged in as a user who is a member of the RTCUniversalServerAdmins group or have the correct permissions delegated.</span></span> <span data-ttu-id="e0f90-105">有关委派权限的详细信息，请参阅[在 Lync Server 2013 中委派安装权限](lync-server-2013-delegate-setup-permissions.md)主题。</span><span class="sxs-lookup"><span data-stu-id="e0f90-105">For details about delegating permissions, see the topic [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

<span data-ttu-id="e0f90-106">在服务器上安装本地配置存储后，安装 Lync Server 2013 组件，并在前端服务器或前端服务器上配置证书，必须在服务器上启动 Lync Server 2013 服务。</span><span class="sxs-lookup"><span data-stu-id="e0f90-106">After you install the Local Configuration store on your servers, install the Lync Server 2013 components, and configure certificates on a Front End Server or Front End Server, you must start the Lync Server 2013 services on the server.</span></span> <span data-ttu-id="e0f90-107">使用以下过程可在部署中的每台前端服务器上启动服务。</span><span class="sxs-lookup"><span data-stu-id="e0f90-107">Use the following procedure to start services on each Front End Server in your deployment.</span></span>

<div>

## <a name="to-start-services-on-a-standard-edition-or-front-end-server"></a><span data-ttu-id="e0f90-108">启动 Standard Edition Server 或前端服务器上的服务</span><span class="sxs-lookup"><span data-stu-id="e0f90-108">To start services on a Standard Edition or Front End Server</span></span>

1.  <span data-ttu-id="e0f90-109">在 Lync Server 部署向导中，在 " **Lync server 2013** " 页上，单击 "**步骤4：启动服务**" 旁边的 "**运行**"。</span><span class="sxs-lookup"><span data-stu-id="e0f90-109">In the Lync Server Deployment Wizard, on the **Lync Server 2013** page, click **Run** next to **Step 4: Start Services**.</span></span>

2.  <span data-ttu-id="e0f90-110">在 "**启动服务**" 页上，单击 "**下一步**" 以启动服务器上的 Lync Server 服务。</span><span class="sxs-lookup"><span data-stu-id="e0f90-110">On the **Start Services** page, click **Next** to start the Lync Server services on the server.</span></span>

3.  <span data-ttu-id="e0f90-111">在“正在执行命令”\*\*\*\* 页上，成功启动所有服务后，单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e0f90-111">On the **Executing Commands** page, after all services have started successfully, click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e0f90-112">用于启动服务器上的服务的命令是报告实际上已启动服务的最佳方法。</span><span class="sxs-lookup"><span data-stu-id="e0f90-112">The command to start the services on the server is a best effort method to report that the services have in fact started.</span></span> <span data-ttu-id="e0f90-113">该命令可能无法反映服务的实际状态。</span><span class="sxs-lookup"><span data-stu-id="e0f90-113">It might not reflect the actual state of the service.</span></span> <span data-ttu-id="e0f90-114">建议使用紧随“启动服务”<STRONG></STRONG>之后的步骤“服务状态(可选)”<STRONG></STRONG>来打开 Microsoft 管理控制台 (MMC) 并确认服务已成功启动。</span><span class="sxs-lookup"><span data-stu-id="e0f90-114">We recommend that you use the step <STRONG>Service Status (Optional)</STRONG> immediately following <STRONG>Start Services</STRONG> to open the Microsoft Management Console (MMC) and confirm that the services have started successfully.</span></span> <span data-ttu-id="e0f90-115">如果任何 Lync Server 服务尚未启动，则可以在 MMC 中右键单击该服务，然后单击 "<STRONG>启动</STRONG>"。</span><span class="sxs-lookup"><span data-stu-id="e0f90-115">If any Lync Server service has not started, you can right-click that service in the MMC, and then click <STRONG>Start</STRONG>.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

