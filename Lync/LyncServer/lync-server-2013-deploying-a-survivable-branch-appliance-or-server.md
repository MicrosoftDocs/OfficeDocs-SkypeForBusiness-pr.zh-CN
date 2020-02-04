---
title: Lync Server 2013：部署 Survivable Branch Appliance 或 Survivable Branch Server
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
ms.openlocfilehash: ca6fae79854356951701eaf6040fb436e787acd2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729577"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-a-survivable-branch-appliance-or-server-with-lync-server-2013"></a><span data-ttu-id="78000-102">使用 Lync Server 2013 部署 Survivable Branch Appliance 或 Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="78000-102">Deploying a Survivable Branch Appliance or Server with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="78000-103">_**主题上次修改时间：** 2014-12-10_</span><span class="sxs-lookup"><span data-stu-id="78000-103">_**Topic Last Modified:** 2014-12-10_</span></span>

<span data-ttu-id="78000-104">复原的企业语音是指分支站点复原功能，即，当中心网站的链接不可用时，可以向分支网站用户提供连续的企业语音服务。</span><span class="sxs-lookup"><span data-stu-id="78000-104">Resilient Enterprise Voice refers to branch-site resiliency, that is, the ability to provide continuous Enterprise Voice service to branch site users in the event that the link to the central site becomes unavailable.</span></span>

<span data-ttu-id="78000-105">对于小型和中型分支网站（有25到1000个用户的分支网站），我们建议部署 Survivable 分支设备，这将通过使用其内置 PSTN 网关或向电话 SIP 主干来终止公共交换电话网络（PSTN）呼叫。服务提供商。</span><span class="sxs-lookup"><span data-stu-id="78000-105">For small and medium-sized branch sites (branch sites with 25 to 1,000 users), we recommend deploying a Survivable Branch Appliance, which will terminate public switched telephone network (PSTN) calls by using its built-in PSTN gateway or a SIP trunk to a telephone service provider.</span></span> <span data-ttu-id="78000-106">Survivable 分支设备是一种第三方设备，包括运行 Windows Server 2008 R2 操作系统、Lync Server 2013 注册机构、中介服务器软件和 PSTN 网关的刀片式服务器，所有这些设备均位于单个装置机箱中。</span><span class="sxs-lookup"><span data-stu-id="78000-106">A Survivable Branch Appliance is a third-party device that includes a blade server running the Windows Server 2008 R2 operating system, Lync Server 2013 Registrar, Mediation Server software, and a PSTN gateway, all in a single appliance chassis.</span></span>

<span data-ttu-id="78000-107">对于1000到5000用户且没有弹性 WAN 的分支站点，我们建议将 Survivable 分支服务器连接到电话服务提供商的 PSTN 网关或 SIP 主干。</span><span class="sxs-lookup"><span data-stu-id="78000-107">For branch sites with 1,000 to 5,000 users and no resilient WAN, we recommend a Survivable Branch Server connected to either a PSTN gateway or a SIP trunk to a telephone service provider.</span></span> <span data-ttu-id="78000-108">Survivable 分支服务器是安装了注册机构和中介服务器软件的基于 Windows 服务器的计算机。</span><span class="sxs-lookup"><span data-stu-id="78000-108">A Survivable Branch Server is a Windows Server-based computer that has Registrar and Mediation Server software installed on it.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="78000-109">对于具有超过5000个用户和专用 Lync Server 管理员的分支站点，我们建议使用完整的 Lync Server 2013 部署，与中心网站的部署不同。</span><span class="sxs-lookup"><span data-stu-id="78000-109">For branch sites with more than 5,000 users and dedicated Lync Server administrators, we recommend a full Lync Server 2013 deployment, separate from that of the central site.</span></span><BR><span data-ttu-id="78000-110">有关为组织中的分支网站选择最佳复原解决方案的详细信息（包括先决条件和规划注意事项），请参阅规划文档中<A href="lync-server-2013-branch-site-resiliency-requirements.md">Lync Server 2013 的分支站点恢复要求</A>。</span><span class="sxs-lookup"><span data-stu-id="78000-110">For details about choosing the best resiliency solution for the branch sites in your organization, including prerequisites and planning considerations, see <A href="lync-server-2013-branch-site-resiliency-requirements.md">Branch-site resiliency requirements for Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="78000-111">在 Lync Server Survivable 分支设备上托管的用户无法创建新的聊天室或查看现有聊天室的聊天室卡片。</span><span class="sxs-lookup"><span data-stu-id="78000-111">Users who are homed on a Lync Server Survivable Branch Appliance are unable to create new chat rooms or view the room card for existing rooms.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="78000-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="78000-112">In This Section</span></span>

  - [<span data-ttu-id="78000-113">使用 Lync Server 2013 部署 Survivable Branch Appliance 或 Survivable Branch Server  - 中央站点任务</span><span class="sxs-lookup"><span data-stu-id="78000-113">Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks</span></span>](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md)

  - [<span data-ttu-id="78000-114">使用 Lync Server 2013 部署 Survivable Branch Appliance 或 Survivable Branch Server  - 分支站点任务</span><span class="sxs-lookup"><span data-stu-id="78000-114">Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task</span></span>](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)

  - [<span data-ttu-id="78000-115">在 Lync Server 2013 中为用户配置分支站点恢复能力</span><span class="sxs-lookup"><span data-stu-id="78000-115">Configuring users for branch site resiliency in Lync Server 2013</span></span>](lync-server-2013-configuring-users-for-branch-site-resiliency.md)

  - [<span data-ttu-id="78000-116">在 Lync Server 2013 中在 Survivable Branch Appliance 或 Survivable Branch Server 上承载用户</span><span class="sxs-lookup"><span data-stu-id="78000-116">Home users on a Survivable Branch Appliance or Server in Lync Server 2013</span></span>](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md)

  - [<span data-ttu-id="78000-117">附录：Lync Server 2013 中的 Survivable Branch Appliance 和 Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="78000-117">Appendices: Survivable Branch Appliances and Servers in Lync Server 2013</span></span>](lync-server-2013-appendices-survivable-branch-appliances-and-servers.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="78000-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="78000-118">See Also</span></span>


[<span data-ttu-id="78000-119">部署 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="78000-119">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

