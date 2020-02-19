---
title: Lync Server 2013：部署 Survivable 分支设备或服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying a Survivable Branch Appliance or Server
ms:assetid: cb780c14-dc5f-41ba-8092-f20ae905bd16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398849(v=OCS.15)
ms:contentKeyID: 48185643
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 835a12cb49c8474389b8ae3cc26773fcea2e4157
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140135"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-a-survivable-branch-appliance-or-server-with-lync-server-2013"></a><span data-ttu-id="ee4eb-102">使用 Lync Server 2013 部署 Survivable 分支设备或服务器</span><span class="sxs-lookup"><span data-stu-id="ee4eb-102">Deploying a Survivable Branch Appliance or Server with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ee4eb-103">_**上次修改的主题：** 2014-12-10_</span><span class="sxs-lookup"><span data-stu-id="ee4eb-103">_**Topic Last Modified:** 2014-12-10_</span></span>

<span data-ttu-id="ee4eb-104">复原企业语音是指分支站点恢复能力，即，在指向中央站点的链接不可用的情况下，能够向分支站点用户提供连续的企业语音服务。</span><span class="sxs-lookup"><span data-stu-id="ee4eb-104">Resilient Enterprise Voice refers to branch-site resiliency, that is, the ability to provide continuous Enterprise Voice service to branch site users in the event that the link to the central site becomes unavailable.</span></span>

<span data-ttu-id="ee4eb-105">对于小型和中型分支站点（25到1000个用户的分支站点），我们建议部署 Survivable 分支设备，这将通过使用其内置 PSTN 网关或到电话的 SIP 中继来终止公共交换电话网络（PSTN）呼叫服务提供商。</span><span class="sxs-lookup"><span data-stu-id="ee4eb-105">For small and medium-sized branch sites (branch sites with 25 to 1,000 users), we recommend deploying a Survivable Branch Appliance, which will terminate public switched telephone network (PSTN) calls by using its built-in PSTN gateway or a SIP trunk to a telephone service provider.</span></span> <span data-ttu-id="ee4eb-106">Survivable 分支设备是一种第三方设备，其中包括运行 Windows Server 2008 R2 操作系统的刀片服务器、Lync Server 2013 注册器、中介服务器软件和 PSTN 网关（全部位于单个设备机箱中）。</span><span class="sxs-lookup"><span data-stu-id="ee4eb-106">A Survivable Branch Appliance is a third-party device that includes a blade server running the Windows Server 2008 R2 operating system, Lync Server 2013 Registrar, Mediation Server software, and a PSTN gateway, all in a single appliance chassis.</span></span>

<span data-ttu-id="ee4eb-107">对于1000到5000用户且无弹性 WAN 的分支站点，我们建议将 Survivable 分支服务器连接到与电话服务提供商的 PSTN 网关或 SIP 中继。</span><span class="sxs-lookup"><span data-stu-id="ee4eb-107">For branch sites with 1,000 to 5,000 users and no resilient WAN, we recommend a Survivable Branch Server connected to either a PSTN gateway or a SIP trunk to a telephone service provider.</span></span> <span data-ttu-id="ee4eb-108">Survivable 分支服务器是一台基于 Windows Server 的计算机，其中安装了注册器和中介服务器软件。</span><span class="sxs-lookup"><span data-stu-id="ee4eb-108">A Survivable Branch Server is a Windows Server-based computer that has Registrar and Mediation Server software installed on it.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ee4eb-109">对于具有超过5000个用户和专用 Lync Server 管理员的分支站点，我们建议使用完整的 Lync Server 2013 部署，并将其与中心站点的部署分开。</span><span class="sxs-lookup"><span data-stu-id="ee4eb-109">For branch sites with more than 5,000 users and dedicated Lync Server administrators, we recommend a full Lync Server 2013 deployment, separate from that of the central site.</span></span><BR><span data-ttu-id="ee4eb-110">有关为组织中的分支站点选择最佳恢复解决方案的详细信息（包括先决条件和规划注意事项），请参阅规划文档中的<A href="lync-server-2013-branch-site-resiliency-requirements.md">Lync Server 2013 的分支站点恢复要求</A>。</span><span class="sxs-lookup"><span data-stu-id="ee4eb-110">For details about choosing the best resiliency solution for the branch sites in your organization, including prerequisites and planning considerations, see <A href="lync-server-2013-branch-site-resiliency-requirements.md">Branch-site resiliency requirements for Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="ee4eb-111">驻留在 Lync Server Survivable 分支设备上的用户无法创建新的聊天室或查看现有聊天室的会议室卡片。</span><span class="sxs-lookup"><span data-stu-id="ee4eb-111">Users who are homed on a Lync Server Survivable Branch Appliance are unable to create new chat rooms or view the room card for existing rooms.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ee4eb-112">本部分内容</span><span class="sxs-lookup"><span data-stu-id="ee4eb-112">In This Section</span></span>

  - [<span data-ttu-id="ee4eb-113">使用 Lync Server 2013 部署 Survivable 分支设备或服务器-中心站点任务</span><span class="sxs-lookup"><span data-stu-id="ee4eb-113">Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks</span></span>](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md)

  - [<span data-ttu-id="ee4eb-114">使用 Lync Server 2013 部署 Survivable 分支设备或服务器-分支站点任务</span><span class="sxs-lookup"><span data-stu-id="ee4eb-114">Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task</span></span>](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)

  - [<span data-ttu-id="ee4eb-115">在 Lync Server 2013 中为用户配置分支站点恢复能力</span><span class="sxs-lookup"><span data-stu-id="ee4eb-115">Configuring users for branch site resiliency in Lync Server 2013</span></span>](lync-server-2013-configuring-users-for-branch-site-resiliency.md)

  - [<span data-ttu-id="ee4eb-116">Lync Server 2013 中的 Survivable 分支装置或服务器上的家庭用户</span><span class="sxs-lookup"><span data-stu-id="ee4eb-116">Home users on a Survivable Branch Appliance or Server in Lync Server 2013</span></span>](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md)

  - [<span data-ttu-id="ee4eb-117">附录： Lync Server 2013 中的 Survivable 分支装置和服务器</span><span class="sxs-lookup"><span data-stu-id="ee4eb-117">Appendices: Survivable Branch Appliances and Servers in Lync Server 2013</span></span>](lync-server-2013-appendices-survivable-branch-appliances-and-servers.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ee4eb-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ee4eb-118">See Also</span></span>


[<span data-ttu-id="ee4eb-119">部署 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ee4eb-119">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

