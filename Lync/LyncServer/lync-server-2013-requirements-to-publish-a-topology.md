---
title: Lync Server 2013：发布拓扑的要求
description: Lync Server 2013：发布拓扑的要求。
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
ms.openlocfilehash: 5699657e680b78587b8ba354e9dc538f2e280c56
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577858"
---
# <a name="requirements-to-publish-a-topology-in-lync-server-2013"></a><span data-ttu-id="0f8c4-103">在 Lync Server 2013 中发布拓扑的要求</span><span class="sxs-lookup"><span data-stu-id="0f8c4-103">Requirements to publish a topology in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0f8c4-104">_**上次修改的主题：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="0f8c4-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="0f8c4-105">本主题介绍了特定于发布拓扑的基础结构和软件要求，无论是使用拓扑生成器还是 Lync Server 2013 管理命令行接口。</span><span class="sxs-lookup"><span data-stu-id="0f8c4-105">This topic describes the infrastructure and software requirements that are specific to publishing a topology, whether by using Topology Builder or the Lync Server 2013 Management Shell command-line interface.</span></span> <span data-ttu-id="0f8c4-106">这些要求是对适用于所有 Lync Server 2013 管理工具的常规操作系统、软件和权限要求的补充。</span><span class="sxs-lookup"><span data-stu-id="0f8c4-106">These requirements are in addition to the general operating system, software, and permissions requirements applicable to all Lync Server 2013 administrative tools.</span></span> <span data-ttu-id="0f8c4-107">在发布拓扑之前，请确保满足所有管理工具的要求。</span><span class="sxs-lookup"><span data-stu-id="0f8c4-107">Make sure that you satisfy all administrative tools requirements before you publish a topology.</span></span>

  - <span data-ttu-id="0f8c4-108">您必须在已加入到您正在创建的 Lync Server 2013 部署的相同域或林的计算机上运行拓扑生成器，以便 Active Directory 域服务准备步骤已完成，从而使您能够使用该计算机上的管理工具成功发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="0f8c4-108">You must run Topology Builder on a computer that is joined to the same domain or forest of the Lync Server 2013 deployment you are creating so that Active Directory Domain Services preparation steps are already completed, enabling you to use the administrative tools on that computer to successfully publish your topology.</span></span>

  - <span data-ttu-id="0f8c4-p102">拓扑中定义的计算机必须加入域（边缘服务器除外）并且位于 AD DS 中。但在发布拓扑时，计算机不需要处于联机状态。</span><span class="sxs-lookup"><span data-stu-id="0f8c4-p102">The computers defined in the topology must be joined to the domain, except for Edge Servers, and in AD DS. However, the computers do not need to be online when you publish the topology.</span></span>

  - <span data-ttu-id="0f8c4-111">必须创建池的文件共享，且该文件共享必须对远程用户可用。</span><span class="sxs-lookup"><span data-stu-id="0f8c4-111">The file share for the pool must be created and available to remote users.</span></span>

  - <span data-ttu-id="0f8c4-112">为了发布 Enterprise Edition 前端池，基于 SQL Server 的后端服务器必须加入到您在其中部署服务器的域，并使用适当的防火墙规则进行配置，以使其可供远程用户使用。</span><span class="sxs-lookup"><span data-stu-id="0f8c4-112">In order to publish an Enterprise Edition Front End pool, the SQL Server-based Back End Server must be joined to the domain in which you are deploying the servers, online, and configured with the appropriate firewall rules to make it available to remote users.</span></span> <span data-ttu-id="0f8c4-113">有关指定防火墙例外的详细信息，请参阅 [了解使用 Lync server 2013 的 SQL Server 的防火墙要求](lync-server-2013-understanding-firewall-requirements-for-sql-server.md)。</span><span class="sxs-lookup"><span data-stu-id="0f8c4-113">For details about specifying firewall exceptions, see [Understanding firewall requirements for SQL Server with Lync Server 2013](lync-server-2013-understanding-firewall-requirements-for-sql-server.md).</span></span> <span data-ttu-id="0f8c4-114">有关配置 SQL Server 的其他详细信息，请参阅 [CONFIGURE SQL server For Lync Server 2013](lync-server-2013-configure-sql-server-for-lync-server.md)。</span><span class="sxs-lookup"><span data-stu-id="0f8c4-114">For other details about configuring SQL Server, see [Configure SQL Server for Lync Server 2013](lync-server-2013-configure-sql-server-for-lync-server.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0f8c4-115">Standard Edition server 具有一个并置数据库，该数据库将接受已发布的配置。</span><span class="sxs-lookup"><span data-stu-id="0f8c4-115">Standard Edition server has a collocated database that will accept the published configuration.</span></span> <span data-ttu-id="0f8c4-116">必须先在 Lync Server 部署向导中运行 " <STRONG>准备第一个 Standard Edition server</STRONG> 安装程序" 任务。</span><span class="sxs-lookup"><span data-stu-id="0f8c4-116">You must first run the <STRONG>Prepare first Standard Edition server</STRONG> setup task in the Lync Server Deployment Wizard.</span></span>

    
    </div>

<div>

## <a name="see-also"></a><span data-ttu-id="0f8c4-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0f8c4-117">See Also</span></span>


[<span data-ttu-id="0f8c4-118">在 Lync Server 2013 中发布拓扑</span><span class="sxs-lookup"><span data-stu-id="0f8c4-118">Publish the topology in Lync Server 2013</span></span>](lync-server-2013-publish-the-topology.md)  
[<span data-ttu-id="0f8c4-119">在 Lync Server 2013 中委派安装程序权限</span><span class="sxs-lookup"><span data-stu-id="0f8c4-119">Delegate setup permissions in Lync Server 2013</span></span>](lync-server-2013-delegate-setup-permissions.md)  


[<span data-ttu-id="0f8c4-120">Lync Server 2013 中的管理工具软件要求</span><span class="sxs-lookup"><span data-stu-id="0f8c4-120">Administrative tools software requirements in Lync Server 2013</span></span>](lync-server-2013-administrative-tools-software-requirements.md)  
[<span data-ttu-id="0f8c4-121">Lync Server 2013 中的服务器和工具操作系统支持</span><span class="sxs-lookup"><span data-stu-id="0f8c4-121">Server and tools operating system support in Lync Server 2013</span></span>](lync-server-2013-server-and-tools-operating-system-support.md)  


[<span data-ttu-id="0f8c4-122">安装和管理 Lync Server 2013 所需的管理员权利和权限</span><span class="sxs-lookup"><span data-stu-id="0f8c4-122">Administrator rights and permissions required for setup and administration of Lync Server 2013</span></span>](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

