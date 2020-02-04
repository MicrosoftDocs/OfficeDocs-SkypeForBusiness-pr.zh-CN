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
ms.openlocfilehash: 85266477df342c16ed69c0507813b905c608745c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742142"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-the-topology-design-in-lync-server-2013"></a><span data-ttu-id="b3ac3-102">在 Lync Server 2013 中验证拓扑设计</span><span class="sxs-lookup"><span data-stu-id="b3ac3-102">Verify the topology design in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3ac3-103">_**主题上次修改时间：** 2012-01-02_</span><span class="sxs-lookup"><span data-stu-id="b3ac3-103">_**Topic Last Modified:** 2012-01-02_</span></span>

<span data-ttu-id="b3ac3-104">拓扑生成器会自动验证拓扑。</span><span class="sxs-lookup"><span data-stu-id="b3ac3-104">Topology Builder automatically verifies the topology.</span></span> <span data-ttu-id="b3ac3-105">任何拓扑错误均标识为验证错误，该错误由服务器角色旁边的验证错误图标指示。</span><span class="sxs-lookup"><span data-stu-id="b3ac3-105">Any topology error is identified as a validation error, indicated by the validation error icon next to the server role.</span></span> <span data-ttu-id="b3ac3-106">还必须验证拓扑是否正确表示你的部署的拓扑。</span><span class="sxs-lookup"><span data-stu-id="b3ac3-106">It is important to also verify that the topology correctly represents the topology for your deployment.</span></span>

<div>

## <a name="to-verify-the-topology-prior-to-publication"></a><span data-ttu-id="b3ac3-107">在发布之前验证拓扑</span><span class="sxs-lookup"><span data-stu-id="b3ac3-107">To verify the topology prior to publication</span></span>

1.  <span data-ttu-id="b3ac3-108">检查所有简单 URL 是否配置正确。</span><span class="sxs-lookup"><span data-stu-id="b3ac3-108">Check that all simple URLs are configured correctly.</span></span>

2.  <span data-ttu-id="b3ac3-109">确认基于 SQL Server 的服务器处于联机状态，并可供安装拓扑生成器（包括所有必要防火墙规则）的计算机使用。</span><span class="sxs-lookup"><span data-stu-id="b3ac3-109">Confirm that the SQL Server-based server is online and available to the computer where Topology Builder is installed, including any necessary firewall rules.</span></span>

3.  <span data-ttu-id="b3ac3-110">确认文件共享可用且已定义适当的权限。</span><span class="sxs-lookup"><span data-stu-id="b3ac3-110">Confirm that the file share is available and has the proper permissions defined.</span></span>

4.  <span data-ttu-id="b3ac3-111">确认拓扑中定义了满足部署要求的正确服务器角色。</span><span class="sxs-lookup"><span data-stu-id="b3ac3-111">Confirm that the correct server roles that meet the deployment requirements are defined in the topology.</span></span>

5.  <span data-ttu-id="b3ac3-112">验证服务器是否存在于 Active Directory 域服务中。</span><span class="sxs-lookup"><span data-stu-id="b3ac3-112">Verify that the servers exist in Active Directory Domain Services.</span></span> <span data-ttu-id="b3ac3-113">如果已将服务器加入域，则会自动发生此情况。</span><span class="sxs-lookup"><span data-stu-id="b3ac3-113">This will happen automatically if you have joined the servers to the domain.</span></span>

<span data-ttu-id="b3ac3-114">如果已验证拓扑并且未出现验证错误，则发布拓扑的准备工作应该已经就绪。</span><span class="sxs-lookup"><span data-stu-id="b3ac3-114">When you have verified the topology and there are no validation errors, you should be ready to publish the topology.</span></span> <span data-ttu-id="b3ac3-115">如果存在验证错误，则必须先更正这些错误，然后才能发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="b3ac3-115">If there are validation errors, you must correct these before you can publish the topology.</span></span> <span data-ttu-id="b3ac3-116">有关发布拓扑的详细信息，请参阅[在 Lync Server 2013 中发布拓扑](lync-server-2013-publish-the-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="b3ac3-116">For details about publishing your topology, see [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

