---
title: 部署 Survivable 分支设备或服务器分支站点任务
description: 部署 Survivable 分支设备或服务器分支站点任务。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy a Survivable Branch Appliance or Server - branch site task
ms:assetid: 7989ba29-0419-46dd-892c-4ad3238afd56
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398599(v=OCS.15)
ms:contentKeyID: 48184586
ms.date: 10/29/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b84f603f185bd507111d4767a22e9009fc0e8b3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545298"
---
# <a name="deploy-a-survivable-branch-appliance-or-server-with-lync-server-2013---branch-site-task"></a><span data-ttu-id="9366b-103">使用 Lync Server 2013 部署 Survivable 分支设备或服务器-分支站点任务</span><span class="sxs-lookup"><span data-stu-id="9366b-103">Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9366b-104">_**上次修改的主题：** 2014-10-28_</span><span class="sxs-lookup"><span data-stu-id="9366b-104">_**Topic Last Modified:** 2014-10-28_</span></span>

<span data-ttu-id="9366b-105">执行 [部署 Survivable 分支机构或包含 Lync server 2013 的服务器](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md)中的任务后，请在分支站点执行本主题中介绍的两个过程之一-中心站点任务。</span><span class="sxs-lookup"><span data-stu-id="9366b-105">Perform one of the two procedures described in this topic at the branch site, after successfully completing the tasks in [Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md).</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="9366b-106">要执行此过程，您必须是 RTCUniversalSBATechnicians 组的成员。</span><span class="sxs-lookup"><span data-stu-id="9366b-106">To perform this procedure, you must be a member of the RTCUniversalSBATechnicians group.</span></span>



</div>

<div>

## <a name="to-deploy-the-survivable-branch-appliance"></a><span data-ttu-id="9366b-107">部署 Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="9366b-107">To deploy the Survivable Branch Appliance</span></span>

  - <span data-ttu-id="9366b-108">Survivable 分支装置部署由 Survivable 分支机构供应商通过 web 用户界面 (UI) 启用。</span><span class="sxs-lookup"><span data-stu-id="9366b-108">Survivable Branch Appliance deployment is enabled by the Survivable Branch Appliance vendor through a web user interface (UI).</span></span> <span data-ttu-id="9366b-109">有关部署 Survivable 分支设备的信息，请参阅您的 Survivable 分支设备供应商文档。</span><span class="sxs-lookup"><span data-stu-id="9366b-109">For information about deploying the Survivable Branch Appliance, see your Survivable Branch Appliance vendor documentation.</span></span>

</div>

<div>

## <a name="to-deploy-the-survivable-branch-server"></a><span data-ttu-id="9366b-110">部署 Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="9366b-110">To deploy the Survivable Branch Server</span></span>

  - <span data-ttu-id="9366b-111">像安装任何其他 Lync Server 2013 Server 角色一样，在运行 Windows Server 2008 R2、Windows Server 2012 或 Windows Server 2012 R2 的计算机上安装 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="9366b-111">Install Lync Server 2013 on a computer running Windows Server 2008 R2, Windows Server 2012, or Windows Server 2012 R2, just as you would install any other Lync Server 2013 server role.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="9366b-112">有关安装 Lync Server 的信息，请参阅部署文档中的 <A href="lync-server-2013-deploying-lync-server.md">部署 Lync server 2013</A> 。</span><span class="sxs-lookup"><span data-stu-id="9366b-112">For information about installing Lync Server, see <A href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

<span data-ttu-id="9366b-113">**下一步**： [在 Lync Server 2013 中为分支站点恢复配置用户](lync-server-2013-configuring-users-for-branch-site-resiliency.md)</span><span class="sxs-lookup"><span data-stu-id="9366b-113">**Next step**: [Configuring users for branch site resiliency in Lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9366b-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9366b-114">See Also</span></span>


[<span data-ttu-id="9366b-115">附录 A：使用 cmdlet 在 Lync Server 2013 中部署 Survivable 分支设备</span><span class="sxs-lookup"><span data-stu-id="9366b-115">Appendix A: Using cmdlets to deploy a Survivable Branch Appliance in Lync Server 2013</span></span>](lync-server-2013-appendix-a-using-cmdlets-to-deploy-a-survivable-branch-appliance.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

