---
title: 部署 Survivable Branch Appliance 或 Survivable Branch Server - 中央站点任务
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying a Survivable Branch Appliance or Server - central site tasks
ms:assetid: 0f631a36-fc2e-41cd-8a0d-f27e84f4a89e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398189(v=OCS.15)
ms:contentKeyID: 48183422
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a9aa6d38ec873652feae6ef6a374ee5b771520b1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729622"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-a-survivable-branch-appliance-or-server-with-lync-server-2013---central-site-tasks"></a><span data-ttu-id="da890-102">使用 Lync Server 2013 部署 Survivable Branch Appliance 或 Survivable Branch Server  - 中央站点任务</span><span class="sxs-lookup"><span data-stu-id="da890-102">Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="da890-103">_**主题上次修改时间：** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="da890-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="da890-104">在中心网站完成本部分中的任务。</span><span class="sxs-lookup"><span data-stu-id="da890-104">Complete the tasks in this section at the central site.</span></span> <span data-ttu-id="da890-105">如果要部署 Survivable 分支服务器，请跳过第一个任务。</span><span class="sxs-lookup"><span data-stu-id="da890-105">If you’re deploying a Survivable Branch Server, skip the first task.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="da890-106">在执行本部分中的任务之前，必须具备以下条件：</span><span class="sxs-lookup"><span data-stu-id="da890-106">Before you perform the tasks in this section, the following conditions must be in place:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="da890-107">必须在中心网站上设置 Lync 服务器。</span><span class="sxs-lookup"><span data-stu-id="da890-107">Lync Server must be set up at the central site.</span></span></P>
> <LI>
> <P><span data-ttu-id="da890-108">分支站点上的安装技术人员必须添加到 RTCUniversalSBATechnicians 组。</span><span class="sxs-lookup"><span data-stu-id="da890-108">An installation technician at the branch site must be added to the RTCUniversalSBATechnicians group.</span></span></P></LI></UL><span data-ttu-id="da890-109">此外，我们建议你执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="da890-109">In addition, we recommend that you do the following:</span></span>
> <UL>
> <LI>
> <P><span data-ttu-id="da890-110">在每个分支站点上部署 DHCP 服务器，以使客户能够获取 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="da890-110">Deploy a DHCP server at each branch site to enable clients to obtain IP addresses.</span></span></P>
> <LI>
> <P><span data-ttu-id="da890-111">除了在每个分支站点上部署 DHCP 服务器之外，在 Survivable 分支机构或 Survivable 分支服务器上启用 Lync Server DHCP，方法是使用 Lync Server Management Shell cmdlet <STRONG>Set-CsRegistrarConfiguration-EnableDHCPServer $true</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="da890-111">As an alternative to deploying a DHCP server at each branch site, enable Lync Server DHCP on the Survivable Branch Appliance or Survivable Branch Server by using the Lync Server Management Shell cmdlet <STRONG>Set-CsRegistrarConfiguration –EnableDHCPServer $true</STRONG>.</span></span> <span data-ttu-id="da890-112">有关详细信息，请参阅规划文档中<A href="lync-server-2013-branch-site-resiliency-requirements.md">Lync Server 2013 的分支站点恢复要求</A>的 "硬件和软件要求" 部分。</span><span class="sxs-lookup"><span data-stu-id="da890-112">For details, see the “Hardware and Software Requirements” section of <A href="lync-server-2013-branch-site-resiliency-requirements.md">Branch-site resiliency requirements for Lync Server 2013</A> in the Planning documentation.</span></span></P></LI></UL>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="da890-113">本节内容</span><span class="sxs-lookup"><span data-stu-id="da890-113">In This Section</span></span>

  - [<span data-ttu-id="da890-114">在 Lync Server 2013 中向 Active Directory 中添加 Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="da890-114">Add a Survivable Branch Appliance to Active Directory in Lync Server 2013</span></span>](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md)

  - [<span data-ttu-id="da890-115">在 Lync Server 2013 中向拓扑添加分支站点</span><span class="sxs-lookup"><span data-stu-id="da890-115">Add branch sites to your topology in Lync Server 2013</span></span>](lync-server-2013-add-branch-sites-to-your-topology.md)

  - [<span data-ttu-id="da890-116">在 Lync Server 2013 中定义 Survivable Branch Appliance 或 Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="da890-116">Define a Survivable Branch Appliance or Server in Lync Server 2013</span></span>](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

