---
title: Lync Server 2013：发布拓扑的要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Requirements to publish a topology
ms:assetid: 841cdf5d-d884-414d-ab50-3bb681b622ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195733(v=OCS.15)
ms:contentKeyID: 48184688
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f1422df35ebbe9f368dc8aa3d121caf740e7033
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723782"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="requirements-to-publish-a-topology-in-lync-server-2013"></a><span data-ttu-id="cf30b-102">在 Lync Server 2013 中发布拓扑的要求</span><span class="sxs-lookup"><span data-stu-id="cf30b-102">Requirements to publish a topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cf30b-103">_**主题上次修改时间：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="cf30b-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="cf30b-104">本主题介绍了特定于发布拓扑的基础结构和软件要求，无论是使用拓扑生成器还是 Lync Server 2013 管理外壳程序命令行界面。</span><span class="sxs-lookup"><span data-stu-id="cf30b-104">This topic describes the infrastructure and software requirements that are specific to publishing a topology, whether by using Topology Builder or the Lync Server 2013 Management Shell command-line interface.</span></span> <span data-ttu-id="cf30b-105">除了适用于所有 Lync Server 2013 管理工具的常规操作系统、软件和权限要求外，还提供了这些要求。</span><span class="sxs-lookup"><span data-stu-id="cf30b-105">These requirements are in addition to the general operating system, software, and permissions requirements applicable to all Lync Server 2013 administrative tools.</span></span> <span data-ttu-id="cf30b-106">在发布拓扑之前，请确保满足所有管理工具要求。</span><span class="sxs-lookup"><span data-stu-id="cf30b-106">Make sure that you satisfy all administrative tools requirements before you publish a topology.</span></span>

  - <span data-ttu-id="cf30b-107">必须在已加入到你正在创建的 Lync Server 2013 部署的相同域或林的计算机上运行拓扑生成器，以便已完成 Active Directory 域服务准备步骤，从而使你能够使用中的管理工具该计算机成功发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="cf30b-107">You must run Topology Builder on a computer that is joined to the same domain or forest of the Lync Server 2013 deployment you are creating so that Active Directory Domain Services preparation steps are already completed, enabling you to use the administrative tools on that computer to successfully publish your topology.</span></span>

  - <span data-ttu-id="cf30b-108">拓扑中定义的计算机必须加入域（边缘服务器除外）和 AD DS 中。</span><span class="sxs-lookup"><span data-stu-id="cf30b-108">The computers defined in the topology must be joined to the domain, except for Edge Servers, and in AD DS.</span></span> <span data-ttu-id="cf30b-109">但是，当你发布拓扑时，计算机无需联机。</span><span class="sxs-lookup"><span data-stu-id="cf30b-109">However, the computers do not need to be online when you publish the topology.</span></span>

  - <span data-ttu-id="cf30b-110">必须创建池的文件共享，并将其提供给远程用户。</span><span class="sxs-lookup"><span data-stu-id="cf30b-110">The file share for the pool must be created and available to remote users.</span></span>

  - <span data-ttu-id="cf30b-111">为了发布企业版前端池，基于 SQL Server 的后端服务器必须联接到您在其中部署服务器的域，并使用相应的防火墙规则进行配置，以使其可供远程用户使用。</span><span class="sxs-lookup"><span data-stu-id="cf30b-111">In order to publish an Enterprise Edition Front End pool, the SQL Server-based Back End Server must be joined to the domain in which you are deploying the servers, online, and configured with the appropriate firewall rules to make it available to remote users.</span></span> <span data-ttu-id="cf30b-112">有关指定防火墙例外的详细信息，请参阅[了解适用于 Lync server 2013 的 SQL Server 的防火墙要求](lync-server-2013-understanding-firewall-requirements-for-sql-server.md)。</span><span class="sxs-lookup"><span data-stu-id="cf30b-112">For details about specifying firewall exceptions, see [Understanding firewall requirements for SQL Server with Lync Server 2013](lync-server-2013-understanding-firewall-requirements-for-sql-server.md).</span></span> <span data-ttu-id="cf30b-113">有关配置 SQL Server 的其他详细信息，请参阅[配置 Lync server 2013 的 SQL Server](lync-server-2013-configure-sql-server-for-lync-server.md)。</span><span class="sxs-lookup"><span data-stu-id="cf30b-113">For other details about configuring SQL Server, see [Configure SQL Server for Lync Server 2013](lync-server-2013-configure-sql-server-for-lync-server.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cf30b-114">标准版服务器具有一个 collocated 数据库，该数据库将接受已发布的配置。</span><span class="sxs-lookup"><span data-stu-id="cf30b-114">Standard Edition server has a collocated database that will accept the published configuration.</span></span> <span data-ttu-id="cf30b-115">必须首先运行 Lync Server 部署向导中的 "<STRONG>准备第一个标准版服务器</STRONG>设置" 任务。</span><span class="sxs-lookup"><span data-stu-id="cf30b-115">You must first run the <STRONG>Prepare first Standard Edition server</STRONG> setup task in the Lync Server Deployment Wizard.</span></span>

    
    </div>

<div>

## <a name="see-also"></a><span data-ttu-id="cf30b-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cf30b-116">See Also</span></span>


[<span data-ttu-id="cf30b-117">在 Lync Server 2013 中发布拓扑</span><span class="sxs-lookup"><span data-stu-id="cf30b-117">Publish the topology in Lync Server 2013</span></span>](lync-server-2013-publish-the-topology.md)  
[<span data-ttu-id="cf30b-118">Lync Server 2013 中的委派安装权限</span><span class="sxs-lookup"><span data-stu-id="cf30b-118">Delegate setup permissions in Lync Server 2013</span></span>](lync-server-2013-delegate-setup-permissions.md)  


[<span data-ttu-id="cf30b-119">Lync Server 2013 中的管理工具软件要求</span><span class="sxs-lookup"><span data-stu-id="cf30b-119">Administrative tools software requirements in Lync Server 2013</span></span>](lync-server-2013-administrative-tools-software-requirements.md)  
[<span data-ttu-id="cf30b-120">Lync Server 2013 中的服务器和工具操作系统支持</span><span class="sxs-lookup"><span data-stu-id="cf30b-120">Server and tools operating system support in Lync Server 2013</span></span>](lync-server-2013-server-and-tools-operating-system-support.md)  


[<span data-ttu-id="cf30b-121">Lync Server 2013 的安装和管理所需的管理员权限</span><span class="sxs-lookup"><span data-stu-id="cf30b-121">Administrator rights and permissions required for setup and administration of Lync Server 2013</span></span>](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

