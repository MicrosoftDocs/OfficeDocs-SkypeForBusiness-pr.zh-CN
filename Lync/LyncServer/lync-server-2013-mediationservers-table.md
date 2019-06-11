---
title: Lync Server 2013：MediationServers 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: MediationServers table
ms:assetid: 9f757377-ab79-4795-aaa9-1163cb9c8a59
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412743(v=OCS.15)
ms:contentKeyID: 48184929
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e211bf9339df49faef7fa83bffa7c65b732b2684
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827198"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mediationservers-table-in-lync-server-2013"></a><span data-ttu-id="cf12a-102">Lync Server 2013 中的 MediationServers 表</span><span class="sxs-lookup"><span data-stu-id="cf12a-102">MediationServers table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cf12a-103">_**主题上次修改时间:** 2010-11-06_</span><span class="sxs-lookup"><span data-stu-id="cf12a-103">_**Topic Last Modified:** 2010-11-06_</span></span>

<span data-ttu-id="cf12a-104">MediationServers 表是支持表。</span><span class="sxs-lookup"><span data-stu-id="cf12a-104">The MediationServers table is a supporting table.</span></span> <span data-ttu-id="cf12a-105">每个记录存储有关在数据库中具有记录的通话中涉及的一个中介服务器的信息。</span><span class="sxs-lookup"><span data-stu-id="cf12a-105">Each record stores information about one Mediation Server that is involved in calls that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cf12a-106">列</span><span class="sxs-lookup"><span data-stu-id="cf12a-106">Column</span></span></th>
<th><span data-ttu-id="cf12a-107">数据类型</span><span class="sxs-lookup"><span data-stu-id="cf12a-107">Data Type</span></span></th>
<th><span data-ttu-id="cf12a-108">键/索引</span><span class="sxs-lookup"><span data-stu-id="cf12a-108">Key/Index</span></span></th>
<th><span data-ttu-id="cf12a-109">详细信息</span><span class="sxs-lookup"><span data-stu-id="cf12a-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cf12a-110"><strong>MediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="cf12a-110"><strong>MediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="cf12a-111">int</span><span class="sxs-lookup"><span data-stu-id="cf12a-111">int</span></span></p></td>
<td><p><span data-ttu-id="cf12a-112">Primary</span><span class="sxs-lookup"><span data-stu-id="cf12a-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="cf12a-113">标识此中介服务器的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="cf12a-113">Unique number identifying this Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf12a-114"><strong>MediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="cf12a-114"><strong>MediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="cf12a-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="cf12a-115">nvarchar(256)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cf12a-116">中介服务器名称。</span><span class="sxs-lookup"><span data-stu-id="cf12a-116">Mediation Server name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

