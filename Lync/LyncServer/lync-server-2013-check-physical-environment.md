---
title: Lync Server 2013：检查物理环境
description: Lync Server 2013：检查物理环境。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Performing physical environmental checks
ms:assetid: 153aee5e-3adf-4dbf-bf41-53e4fba51fb0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720558(v=OCS.15)
ms:contentKeyID: 63969582
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d963485b109e0afdf21b3a9085fa28884dfc3100
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543548"
---
# <a name="performing-physical-environmental-checks"></a><span data-ttu-id="343a8-103">执行物理环境检查</span><span class="sxs-lookup"><span data-stu-id="343a8-103">Performing physical environmental checks</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="343a8-104">_**上次修改的主题：** 2014-04-30_</span><span class="sxs-lookup"><span data-stu-id="343a8-104">_**Topic Last Modified:** 2014-04-30_</span></span>

<span data-ttu-id="343a8-105">在检查 Lync Server 2013 部署的性能、可用性和功能之前，应检查物理环境。</span><span class="sxs-lookup"><span data-stu-id="343a8-105">Before checking the performance, availability, and functionality of the Lync Server 2013 deployment, you should check the physical environment.</span></span> <span data-ttu-id="343a8-106">例如，服务器的室内温度可能必须降低，或者可能需要更换网络电缆。</span><span class="sxs-lookup"><span data-stu-id="343a8-106">For example, the server room temperature might have to be lowered, or a network cable might have to be replaced.</span></span> <span data-ttu-id="343a8-107">为获得最佳结果，请执行以下物理环境检查：</span><span class="sxs-lookup"><span data-stu-id="343a8-107">For best results, perform the following physical environmental inspections:</span></span>

  - <span data-ttu-id="343a8-108">**物理安全措施**    物理安全保护（如锁、门和受限制访问的聊天室）必须受到保护。</span><span class="sxs-lookup"><span data-stu-id="343a8-108">**Physical security measures**   Physical security protection such as locks, doors, and restricted-access rooms must be secured.</span></span> <span data-ttu-id="343a8-109">检查是否有未授权和强制的设备损坏迹象。</span><span class="sxs-lookup"><span data-stu-id="343a8-109">Check for any unauthorized and forced entries and signs of equipment damage.</span></span>

  - <span data-ttu-id="343a8-110">**温度和湿度**    高温、空气流量差和湿度可能导致硬件组件过热。</span><span class="sxs-lookup"><span data-stu-id="343a8-110">**Temperature and humidity**   High temperature, poor air flow, and humidity can cause hardware components to overheat.</span></span> <span data-ttu-id="343a8-111">检查温度和湿度，以确保环境系统（如加热和空调）可以在硬件制造商的规范中维护可接受的条件和功能。</span><span class="sxs-lookup"><span data-stu-id="343a8-111">Check temperature and humidity to help to make sure that the environmental systems such as heating and air conditioning can maintain acceptable conditions and function within the hardware manufacturer's specifications.</span></span> <span data-ttu-id="343a8-112">最近安装新设备时，还应检查服务器的通风流是否不受支持，并符合制造商的规范。</span><span class="sxs-lookup"><span data-stu-id="343a8-112">When new equipment has recently been installed, also check that air flow both to and from the servers is unimpeded and meets manufacturer spec.</span></span>

  - <span data-ttu-id="343a8-113">**设备和组件**    Lync Server 2013 组织依赖于正常运行的物理网络和相关硬件。</span><span class="sxs-lookup"><span data-stu-id="343a8-113">**Devices and components**   The Lync Server 2013 organization relies on a functioning physical network and related hardware.</span></span> <span data-ttu-id="343a8-114">请确保路由器、交换机、集线器、物理电缆和连接器正常运行。</span><span class="sxs-lookup"><span data-stu-id="343a8-114">Make sure that routers, switches, hubs, physical cables, and connectors are operational.</span></span>

<span data-ttu-id="343a8-115">有关如何执行这些检查的具体说明将很大程度上取决于您的安装网站和所选的服务器硬件。</span><span class="sxs-lookup"><span data-stu-id="343a8-115">The specifics on how to perform these checks will depend greatly on your installation site and the server hardware that was chosen.</span></span> <span data-ttu-id="343a8-116">第一次执行此检查时，请参阅硬件文档，并记下所需的参数以供将来参考。</span><span class="sxs-lookup"><span data-stu-id="343a8-116">The first time that you perform this check, refer to the hardware documentation and note the desired parameters for future reference.</span></span>

### <a name="desired-server-space-environment"></a><span data-ttu-id="343a8-117">所需的服务器空间环境</span><span class="sxs-lookup"><span data-stu-id="343a8-117">Desired server space environment</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="343a8-118">参数</span><span class="sxs-lookup"><span data-stu-id="343a8-118">Parameter</span></span></th>
<th><span data-ttu-id="343a8-119">所需的值或范围</span><span class="sxs-lookup"><span data-stu-id="343a8-119">Desired value or range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="343a8-120">量</span><span class="sxs-lookup"><span data-stu-id="343a8-120">Temperature</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="343a8-121">湿度</span><span class="sxs-lookup"><span data-stu-id="343a8-121">Humidity</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="343a8-122">服务器正面</span><span class="sxs-lookup"><span data-stu-id="343a8-122">Front of server faces</span></span></p></td>
<td><p><span data-ttu-id="343a8-123">热通道/cold 通道</span><span class="sxs-lookup"><span data-stu-id="343a8-123">Hot aisle / cold aisle</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="343a8-124">不流通的耗尽净空</span><span class="sxs-lookup"><span data-stu-id="343a8-124">Unimpeded exhaust clearance</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

