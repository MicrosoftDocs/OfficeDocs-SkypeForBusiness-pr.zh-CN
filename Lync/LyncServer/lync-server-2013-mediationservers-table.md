---
title: Lync Server 2013：MediationServers 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: MediationServers table
ms:assetid: 9f757377-ab79-4795-aaa9-1163cb9c8a59
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412743(v=OCS.15)
ms:contentKeyID: 48184929
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7854306eefb1bed16753e8f6408a8c06f95bd04f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766063"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mediationservers-table-in-lync-server-2013"></a><span data-ttu-id="e0cc0-102">Lync Server 2013 中的 MediationServers 表</span><span class="sxs-lookup"><span data-stu-id="e0cc0-102">MediationServers table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e0cc0-103">_**主题上次修改时间：** 2010-11-06_</span><span class="sxs-lookup"><span data-stu-id="e0cc0-103">_**Topic Last Modified:** 2010-11-06_</span></span>

<span data-ttu-id="e0cc0-104">MediationServers 表是支持表。</span><span class="sxs-lookup"><span data-stu-id="e0cc0-104">The MediationServers table is a supporting table.</span></span> <span data-ttu-id="e0cc0-105">每个记录存储有关在数据库中具有记录的通话中涉及的一个中介服务器的信息。</span><span class="sxs-lookup"><span data-stu-id="e0cc0-105">Each record stores information about one Mediation Server that is involved in calls that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e0cc0-106">列</span><span class="sxs-lookup"><span data-stu-id="e0cc0-106">Column</span></span></th>
<th><span data-ttu-id="e0cc0-107">数据类型</span><span class="sxs-lookup"><span data-stu-id="e0cc0-107">Data Type</span></span></th>
<th><span data-ttu-id="e0cc0-108">键/索引</span><span class="sxs-lookup"><span data-stu-id="e0cc0-108">Key/Index</span></span></th>
<th><span data-ttu-id="e0cc0-109">详细信息</span><span class="sxs-lookup"><span data-stu-id="e0cc0-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e0cc0-110"><strong>MediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="e0cc0-110"><strong>MediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="e0cc0-111">int</span><span class="sxs-lookup"><span data-stu-id="e0cc0-111">int</span></span></p></td>
<td><p><span data-ttu-id="e0cc0-112">Primary</span><span class="sxs-lookup"><span data-stu-id="e0cc0-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="e0cc0-113">标识此中介服务器的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="e0cc0-113">Unique number identifying this Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0cc0-114"><strong>MediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="e0cc0-114"><strong>MediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="e0cc0-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e0cc0-115">nvarchar(256)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e0cc0-116">中介服务器名称。</span><span class="sxs-lookup"><span data-stu-id="e0cc0-116">Mediation Server name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

