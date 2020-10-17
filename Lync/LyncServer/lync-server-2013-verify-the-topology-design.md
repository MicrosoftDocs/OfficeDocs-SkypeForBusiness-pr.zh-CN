---
title: Lync Server 2013：验证拓扑设计
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify the topology design
ms:assetid: c1b61814-239e-4101-aab0-de3db1d8793c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412951(v=OCS.15)
ms:contentKeyID: 48185311
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8e8dae20a945194fb4fda2bcc84eab232d9b34e1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518589"
---
# <a name="verify-the-topology-design-in-lync-server-2013"></a><span data-ttu-id="7f08d-102">验证 Lync Server 2013 中的拓扑设计</span><span class="sxs-lookup"><span data-stu-id="7f08d-102">Verify the topology design in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7f08d-103">_**上次修改的主题：** 2012-01-02_</span><span class="sxs-lookup"><span data-stu-id="7f08d-103">_**Topic Last Modified:** 2012-01-02_</span></span>

<span data-ttu-id="7f08d-104">拓扑生成器将自动验证拓扑。</span><span class="sxs-lookup"><span data-stu-id="7f08d-104">Topology Builder automatically verifies the topology.</span></span> <span data-ttu-id="7f08d-105">任何拓扑错误均被标识为验证错误，由服务器角色旁边的验证错误图标指示。</span><span class="sxs-lookup"><span data-stu-id="7f08d-105">Any topology error is identified as a validation error, indicated by the validation error icon next to the server role.</span></span> <span data-ttu-id="7f08d-106">验证拓扑是否正确代表部署的拓扑也很重要。</span><span class="sxs-lookup"><span data-stu-id="7f08d-106">It is important to also verify that the topology correctly represents the topology for your deployment.</span></span>

<div>

## <a name="to-verify-the-topology-prior-to-publication"></a><span data-ttu-id="7f08d-107">发布前验证拓扑</span><span class="sxs-lookup"><span data-stu-id="7f08d-107">To verify the topology prior to publication</span></span>

1.  <span data-ttu-id="7f08d-108">检查所有简单 URL 是否配置正确。</span><span class="sxs-lookup"><span data-stu-id="7f08d-108">Check that all simple URLs are configured correctly.</span></span>

2.  <span data-ttu-id="7f08d-109">确认基于 SQL Server 的服务器处于联机状态，并且可用于安装了拓扑生成器的计算机，包括任何必要的防火墙规则。</span><span class="sxs-lookup"><span data-stu-id="7f08d-109">Confirm that the SQL Server-based server is online and available to the computer where Topology Builder is installed, including any necessary firewall rules.</span></span>

3.  <span data-ttu-id="7f08d-110">确认文件共享可用，并已定义适当的权限。</span><span class="sxs-lookup"><span data-stu-id="7f08d-110">Confirm that the file share is available and has the proper permissions defined.</span></span>

4.  <span data-ttu-id="7f08d-111">确认拓扑中定义了满足部署要求的正确服务器角色。</span><span class="sxs-lookup"><span data-stu-id="7f08d-111">Confirm that the correct server roles that meet the deployment requirements are defined in the topology.</span></span>

5.  <span data-ttu-id="7f08d-112">验证服务器是否存在于 Active Directory 域服务中。</span><span class="sxs-lookup"><span data-stu-id="7f08d-112">Verify that the servers exist in Active Directory Domain Services.</span></span> <span data-ttu-id="7f08d-113">如果已将服务器加入域，将自动验证。</span><span class="sxs-lookup"><span data-stu-id="7f08d-113">This will happen automatically if you have joined the servers to the domain.</span></span>

<span data-ttu-id="7f08d-114">如果已验证拓扑并且未出现验证错误，则发布拓扑的准备工作应该已经就绪。</span><span class="sxs-lookup"><span data-stu-id="7f08d-114">When you have verified the topology and there are no validation errors, you should be ready to publish the topology.</span></span> <span data-ttu-id="7f08d-115">如果出现验证错误，则必须先更正错误，然后才能发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="7f08d-115">If there are validation errors, you must correct these before you can publish the topology.</span></span> <span data-ttu-id="7f08d-116">有关发布拓扑的详细信息，请参阅 [在 Lync Server 2013 中发布拓扑](lync-server-2013-publish-the-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="7f08d-116">For details about publishing your topology, see [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

