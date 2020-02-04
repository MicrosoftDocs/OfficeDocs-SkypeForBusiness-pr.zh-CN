---
title: Lync Server 2013：持久聊天服务器合规性表的列表
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
ms.openlocfilehash: 3c4f6e9622e839e2f1fd719b8e2d7ba95286247e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765410"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-persistent-chat-server-compliance-tables-in-lync-server-2013"></a><span data-ttu-id="0c2b7-102">Lync Server 2013 中持久聊天服务器合规性表的列表</span><span class="sxs-lookup"><span data-stu-id="0c2b7-102">List of Persistent Chat Server compliance tables in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0c2b7-103">_**主题上次修改时间：** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="0c2b7-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="0c2b7-104">持久聊天合规性数据库架构由下表组成。</span><span class="sxs-lookup"><span data-stu-id="0c2b7-104">The Persistent Chat compliance database schema consists of the following tables.</span></span>

<div>

## <a name="list-of-persistent-chat-server-compliance-tables"></a><span data-ttu-id="0c2b7-105">持久聊天服务器合规性表列表</span><span class="sxs-lookup"><span data-stu-id="0c2b7-105">List of Persistent Chat Server Compliance Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0c2b7-106">表格</span><span class="sxs-lookup"><span data-stu-id="0c2b7-106">Table</span></span></th>
<th><span data-ttu-id="0c2b7-107">说明</span><span class="sxs-lookup"><span data-stu-id="0c2b7-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0c2b7-108"><a href="lync-server-2013-tblcompliancedata.md">Lync Server 2013 中的 tblComplianceData</a></span><span class="sxs-lookup"><span data-stu-id="0c2b7-108"><a href="lync-server-2013-tblcompliancedata.md">tblComplianceData in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0c2b7-109">包含已配置的适配器尚未处理的合规性事件。</span><span class="sxs-lookup"><span data-stu-id="0c2b7-109">Contains the compliance events that have not yet been processed by the configured adapter.</span></span></p>
<p><span data-ttu-id="0c2b7-110">此表包括与聊天相关的持久事件，例如聊天消息和文件下载。</span><span class="sxs-lookup"><span data-stu-id="0c2b7-110">This table includes Persistent Chat-related events, such as chat messages and file downloads.</span></span> <span data-ttu-id="0c2b7-111">（参与者事件由 tblComplianceParticipant 表跟踪。）</span><span class="sxs-lookup"><span data-stu-id="0c2b7-111">(Participant events are tracked by the tblComplianceParticipant table.)</span></span></p>
<p><span data-ttu-id="0c2b7-112">（处理此表中的事件的服务器在 tblComplianceFanout 表中列出。）</span><span class="sxs-lookup"><span data-stu-id="0c2b7-112">(The servers that processed the events in this table are listed in the tblComplianceFanout table.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c2b7-113"><a href="lync-server-2013-tblcompliancefanout.md">Lync Server 2013 中的 tblComplianceFanout</a></span><span class="sxs-lookup"><span data-stu-id="0c2b7-113"><a href="lync-server-2013-tblcompliancefanout.md">tblComplianceFanout in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0c2b7-114">包含处理合规性事件的服务器。</span><span class="sxs-lookup"><span data-stu-id="0c2b7-114">Contains the servers that processed a compliance event.</span></span> <span data-ttu-id="0c2b7-115">此表与 tblComplianceData 表紧密耦合。</span><span class="sxs-lookup"><span data-stu-id="0c2b7-115">This table is tightly coupled with the tblComplianceData table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c2b7-116"><a href="lync-server-2013-tblcomplianceparticipant.md">Lync Server 2013 中的 tblComplianceParticipant</a></span><span class="sxs-lookup"><span data-stu-id="0c2b7-116"><a href="lync-server-2013-tblcomplianceparticipant.md">tblComplianceParticipant in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0c2b7-117">包含每个聊天服务和每台服务器的当前参与者。</span><span class="sxs-lookup"><span data-stu-id="0c2b7-117">Contains current participants per chat service and per server.</span></span> <span data-ttu-id="0c2b7-118">它根据从持久聊天服务接收的联接和部件合规性事件进行维护。</span><span class="sxs-lookup"><span data-stu-id="0c2b7-118">It is maintained based on join and part compliance events received from the Persistent Chat service.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c2b7-119"><a href="lync-server-2013-tblcompliancestate.md">Lync Server 2013 中的 tblComplianceState</a></span><span class="sxs-lookup"><span data-stu-id="0c2b7-119"><a href="lync-server-2013-tblcompliancestate.md">tblComplianceState in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0c2b7-120">包含池范围的合规性状态信息。</span><span class="sxs-lookup"><span data-stu-id="0c2b7-120">Contains pool-wide compliance state information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

