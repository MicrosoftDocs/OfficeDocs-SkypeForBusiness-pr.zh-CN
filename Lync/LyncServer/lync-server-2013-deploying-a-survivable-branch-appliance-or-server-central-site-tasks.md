---
title: 部署 Survivable 分支设备或服务器中心网站任务
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
ms.openlocfilehash: 4756da7db87504e8b8c700cea1abb171b594543e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42047546"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-a-survivable-branch-appliance-or-server-with-lync-server-2013---central-site-tasks"></a><span data-ttu-id="1bc35-102">使用 Lync Server 2013 部署 Survivable 分支设备或服务器-中心站点任务</span><span class="sxs-lookup"><span data-stu-id="1bc35-102">Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1bc35-103">_**上次修改的主题：** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="1bc35-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="1bc35-104">在中央站点完成本节中的任务。</span><span class="sxs-lookup"><span data-stu-id="1bc35-104">Complete the tasks in this section at the central site.</span></span> <span data-ttu-id="1bc35-105">如果要部署 Survivable 分支服务器，请跳过第一个任务。</span><span class="sxs-lookup"><span data-stu-id="1bc35-105">If you’re deploying a Survivable Branch Server, skip the first task.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="1bc35-106">执行本节中的任务之前，必须满足以下条件：</span><span class="sxs-lookup"><span data-stu-id="1bc35-106">Before you perform the tasks in this section, the following conditions must be in place:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="1bc35-107">必须在中央站点上设置 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="1bc35-107">Lync Server must be set up at the central site.</span></span></P>
> <LI>
> <P><span data-ttu-id="1bc35-108">必须将分支站点的安装技术人员添加到 RTCUniversalSBATechnicians 组。</span><span class="sxs-lookup"><span data-stu-id="1bc35-108">An installation technician at the branch site must be added to the RTCUniversalSBATechnicians group.</span></span></P></LI></UL><span data-ttu-id="1bc35-109">此外，建议执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="1bc35-109">In addition, we recommend that you do the following:</span></span>
> <UL>
> <LI>
> <P><span data-ttu-id="1bc35-110">在每个分支站点部署 DHCP 服务器，以便客户端能够获取 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="1bc35-110">Deploy a DHCP server at each branch site to enable clients to obtain IP addresses.</span></span></P>
> <LI>
> <P><span data-ttu-id="1bc35-111">在每个分支站点上部署 DHCP 服务器的另一种方法是，使用 Lync Server Management Shell cmdlet <STRONG>CsRegistrarConfiguration – EnableDHCPServer $true</STRONG>在 Survivable 分支设备或 Survivable 分支服务器上启用 LYNC server DHCP。</span><span class="sxs-lookup"><span data-stu-id="1bc35-111">As an alternative to deploying a DHCP server at each branch site, enable Lync Server DHCP on the Survivable Branch Appliance or Survivable Branch Server by using the Lync Server Management Shell cmdlet <STRONG>Set-CsRegistrarConfiguration –EnableDHCPServer $true</STRONG>.</span></span> <span data-ttu-id="1bc35-112">有关详细信息，请参阅规划文档中的<A href="lync-server-2013-branch-site-resiliency-requirements.md">Lync Server 2013 分支站点恢复要求</A>的 "硬件和软件要求" 一节。</span><span class="sxs-lookup"><span data-stu-id="1bc35-112">For details, see the “Hardware and Software Requirements” section of <A href="lync-server-2013-branch-site-resiliency-requirements.md">Branch-site resiliency requirements for Lync Server 2013</A> in the Planning documentation.</span></span></P></LI></UL>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="1bc35-113">本部分内容</span><span class="sxs-lookup"><span data-stu-id="1bc35-113">In This Section</span></span>

  - [<span data-ttu-id="1bc35-114">在 Lync Server 2013 中将 Survivable 分支设备添加到 Active Directory</span><span class="sxs-lookup"><span data-stu-id="1bc35-114">Add a Survivable Branch Appliance to Active Directory in Lync Server 2013</span></span>](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md)

  - [<span data-ttu-id="1bc35-115">在 Lync Server 2013 中向拓扑添加分支站点</span><span class="sxs-lookup"><span data-stu-id="1bc35-115">Add branch sites to your topology in Lync Server 2013</span></span>](lync-server-2013-add-branch-sites-to-your-topology.md)

  - [<span data-ttu-id="1bc35-116">在 Lync Server 2013 中定义 Survivable 分支设备或服务器</span><span class="sxs-lookup"><span data-stu-id="1bc35-116">Define a Survivable Branch Appliance or Server in Lync Server 2013</span></span>](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

