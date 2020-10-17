---
title: 部署 Survivable 分支设备或服务器分支站点任务
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
ms.openlocfilehash: 835de118f46dba61fe86ee3f412c55d945dfb2a9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521649"
---
# <a name="deploy-a-survivable-branch-appliance-or-server-with-lync-server-2013---branch-site-task"></a><span data-ttu-id="699c5-102">使用 Lync Server 2013 部署 Survivable 分支设备或服务器-分支站点任务</span><span class="sxs-lookup"><span data-stu-id="699c5-102">Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="699c5-103">_**上次修改的主题：** 2014-10-28_</span><span class="sxs-lookup"><span data-stu-id="699c5-103">_**Topic Last Modified:** 2014-10-28_</span></span>

<span data-ttu-id="699c5-104">执行 [部署 Survivable 分支机构或包含 Lync server 2013 的服务器](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md)中的任务后，请在分支站点执行本主题中介绍的两个过程之一-中心站点任务。</span><span class="sxs-lookup"><span data-stu-id="699c5-104">Perform one of the two procedures described in this topic at the branch site, after successfully completing the tasks in [Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md).</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="699c5-105">要执行此过程，您必须是 RTCUniversalSBATechnicians 组的成员。</span><span class="sxs-lookup"><span data-stu-id="699c5-105">To perform this procedure, you must be a member of the RTCUniversalSBATechnicians group.</span></span>



</div>

<div>

## <a name="to-deploy-the-survivable-branch-appliance"></a><span data-ttu-id="699c5-106">部署 Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="699c5-106">To deploy the Survivable Branch Appliance</span></span>

  - <span data-ttu-id="699c5-107">Survivable 分支装置部署由 Survivable 分支机构供应商通过 web 用户界面 (UI) 启用。</span><span class="sxs-lookup"><span data-stu-id="699c5-107">Survivable Branch Appliance deployment is enabled by the Survivable Branch Appliance vendor through a web user interface (UI).</span></span> <span data-ttu-id="699c5-108">有关部署 Survivable 分支设备的信息，请参阅您的 Survivable 分支设备供应商文档。</span><span class="sxs-lookup"><span data-stu-id="699c5-108">For information about deploying the Survivable Branch Appliance, see your Survivable Branch Appliance vendor documentation.</span></span>

</div>

<div>

## <a name="to-deploy-the-survivable-branch-server"></a><span data-ttu-id="699c5-109">部署 Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="699c5-109">To deploy the Survivable Branch Server</span></span>

  - <span data-ttu-id="699c5-110">像安装任何其他 Lync Server 2013 Server 角色一样，在运行 Windows Server 2008 R2、Windows Server 2012 或 Windows Server 2012 R2 的计算机上安装 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="699c5-110">Install Lync Server 2013 on a computer running Windows Server 2008 R2, Windows Server 2012, or Windows Server 2012 R2, just as you would install any other Lync Server 2013 server role.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="699c5-111">有关安装 Lync Server 的信息，请参阅部署文档中的 <A href="lync-server-2013-deploying-lync-server.md">部署 Lync server 2013</A> 。</span><span class="sxs-lookup"><span data-stu-id="699c5-111">For information about installing Lync Server, see <A href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

<span data-ttu-id="699c5-112">**下一步**： [在 Lync Server 2013 中为分支站点恢复配置用户](lync-server-2013-configuring-users-for-branch-site-resiliency.md)</span><span class="sxs-lookup"><span data-stu-id="699c5-112">**Next step**: [Configuring users for branch site resiliency in Lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="699c5-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="699c5-113">See Also</span></span>


[<span data-ttu-id="699c5-114">附录 A：使用 cmdlet 在 Lync Server 2013 中部署 Survivable 分支设备</span><span class="sxs-lookup"><span data-stu-id="699c5-114">Appendix A: Using cmdlets to deploy a Survivable Branch Appliance in Lync Server 2013</span></span>](lync-server-2013-appendix-a-using-cmdlets-to-deploy-a-survivable-branch-appliance.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

