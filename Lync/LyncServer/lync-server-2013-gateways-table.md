---
title: Lync Server 2013：网关表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Gateways table
ms:assetid: a909daad-d137-45e0-b149-1de9f8e1e029
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412795(v=OCS.15)
ms:contentKeyID: 48185034
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a03222cd628466e7d88e8f36adafbf5207f0ef0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037994"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="gateways-table-in-lync-server-2013"></a><span data-ttu-id="4da04-102">Lync Server 2013 中的网关表</span><span class="sxs-lookup"><span data-stu-id="4da04-102">Gateways table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4da04-103">_**上次修改的主题：** 2010-11-05_</span><span class="sxs-lookup"><span data-stu-id="4da04-103">_**Topic Last Modified:** 2010-11-05_</span></span>

<span data-ttu-id="4da04-104">网关表是支持表。</span><span class="sxs-lookup"><span data-stu-id="4da04-104">The Gateways table is a supporting table.</span></span> <span data-ttu-id="4da04-105">每个记录存储在数据库中具有记录的公用电话交换网（PSTN）呼叫中涉及的一个网关的相关信息。</span><span class="sxs-lookup"><span data-stu-id="4da04-105">Each record stores information about one gateway that is involved in public switched telephone network (PSTN) calls that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4da04-106">列</span><span class="sxs-lookup"><span data-stu-id="4da04-106">Column</span></span></th>
<th><span data-ttu-id="4da04-107">数据类型</span><span class="sxs-lookup"><span data-stu-id="4da04-107">Data Type</span></span></th>
<th><span data-ttu-id="4da04-108">键/索引</span><span class="sxs-lookup"><span data-stu-id="4da04-108">Key/Index</span></span></th>
<th><span data-ttu-id="4da04-109">详细信息</span><span class="sxs-lookup"><span data-stu-id="4da04-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4da04-110"><strong>GatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="4da04-110"><strong>GatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="4da04-111">int</span><span class="sxs-lookup"><span data-stu-id="4da04-111">int</span></span></p></td>
<td><p><span data-ttu-id="4da04-112">主</span><span class="sxs-lookup"><span data-stu-id="4da04-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="4da04-113">标识此网关的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="4da04-113">Unique number identifying this gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4da04-114"><strong>网关</strong></span><span class="sxs-lookup"><span data-stu-id="4da04-114"><strong>Gateway</strong></span></span></p></td>
<td><p><span data-ttu-id="4da04-115">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="4da04-115">nvarchar(256)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4da04-116">网关名称。</span><span class="sxs-lookup"><span data-stu-id="4da04-116">Gateway name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

