---
title: Lync Server 2013：持久聊天服务器合规性表的列表
description: Lync Server 2013：持久聊天服务器合规性表的列表。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of Persistent Chat Server compliance tables
ms:assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215878(v=OCS.15)
ms:contentKeyID: 48706007
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47cb28a0ca4180327c2adc48d80e9e41171a7bfc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550068"
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-lync-server-2013"></a><span data-ttu-id="e208e-103">Lync Server 2013 中持久聊天服务器合规性表的列表</span><span class="sxs-lookup"><span data-stu-id="e208e-103">List of Persistent Chat Server compliance tables in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e208e-104">_**上次修改的主题：** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="e208e-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="e208e-105">持久聊天合规性数据库架构由下表组成。</span><span class="sxs-lookup"><span data-stu-id="e208e-105">The Persistent Chat compliance database schema consists of the following tables.</span></span>

<div>

## <a name="list-of-persistent-chat-server-compliance-tables"></a><span data-ttu-id="e208e-106">持久聊天服务器合规性表的列表</span><span class="sxs-lookup"><span data-stu-id="e208e-106">List of Persistent Chat Server Compliance Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e208e-107">Table</span><span class="sxs-lookup"><span data-stu-id="e208e-107">Table</span></span></th>
<th><span data-ttu-id="e208e-108">说明</span><span class="sxs-lookup"><span data-stu-id="e208e-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e208e-109"><a href="lync-server-2013-tblcompliancedata.md">Lync Server 2013 中的 tblComplianceData</a></span><span class="sxs-lookup"><span data-stu-id="e208e-109"><a href="lync-server-2013-tblcompliancedata.md">tblComplianceData in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e208e-110">包含已配置的适配器尚未处理的合规性事件。</span><span class="sxs-lookup"><span data-stu-id="e208e-110">Contains the compliance events that have not yet been processed by the configured adapter.</span></span></p>
<p><span data-ttu-id="e208e-111">此表包括与持久聊天相关的事件，如聊天消息和文件下载。</span><span class="sxs-lookup"><span data-stu-id="e208e-111">This table includes Persistent Chat-related events, such as chat messages and file downloads.</span></span> <span data-ttu-id="e208e-112"> (参与者事件由 tblComplianceParticipant 表跟踪。 ) </span><span class="sxs-lookup"><span data-stu-id="e208e-112">(Participant events are tracked by the tblComplianceParticipant table.)</span></span></p>
<p><span data-ttu-id="e208e-113">（处理该表中的事件的服务器列在 tblComplianceFanout 表中。）</span><span class="sxs-lookup"><span data-stu-id="e208e-113">(The servers that processed the events in this table are listed in the tblComplianceFanout table.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e208e-114"><a href="lync-server-2013-tblcompliancefanout.md">Lync Server 2013 中的 tblComplianceFanout</a></span><span class="sxs-lookup"><span data-stu-id="e208e-114"><a href="lync-server-2013-tblcompliancefanout.md">tblComplianceFanout in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e208e-115">包含处理合规性事件的服务器。</span><span class="sxs-lookup"><span data-stu-id="e208e-115">Contains the servers that processed a compliance event.</span></span> <span data-ttu-id="e208e-116">该表与 tblComplianceData 表联系紧密。</span><span class="sxs-lookup"><span data-stu-id="e208e-116">This table is tightly coupled with the tblComplianceData table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e208e-117"><a href="lync-server-2013-tblcomplianceparticipant.md">Lync Server 2013 中的 tblComplianceParticipant</a></span><span class="sxs-lookup"><span data-stu-id="e208e-117"><a href="lync-server-2013-tblcomplianceparticipant.md">tblComplianceParticipant in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e208e-118">包含每个聊天服务和每台服务器的当前参与者。</span><span class="sxs-lookup"><span data-stu-id="e208e-118">Contains current participants per chat service and per server.</span></span> <span data-ttu-id="e208e-119">它将根据从持久聊天服务接收到的联接和部件合规性事件进行维护。</span><span class="sxs-lookup"><span data-stu-id="e208e-119">It is maintained based on join and part compliance events received from the Persistent Chat service.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e208e-120"><a href="lync-server-2013-tblcompliancestate.md">Lync Server 2013 中的 tblComplianceState</a></span><span class="sxs-lookup"><span data-stu-id="e208e-120"><a href="lync-server-2013-tblcompliancestate.md">tblComplianceState in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e208e-121">包含池范围的合规性状态信息。</span><span class="sxs-lookup"><span data-stu-id="e208e-121">Contains pool-wide compliance state information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

