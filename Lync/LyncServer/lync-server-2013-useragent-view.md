---
title: Lync Server 2013： UserAgent 视图
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UserAgent view
ms:assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721862(v=OCS.15)
ms:contentKeyID: 49733795
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cb9e70635fc4c54448f6fe3f549d3d6853612070
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530119"
---
# <a name="useragent-view-in-lync-server-2013"></a><span data-ttu-id="a0a70-102">Lync Server 2013 中的 UserAgent 视图</span><span class="sxs-lookup"><span data-stu-id="a0a70-102">UserAgent view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a0a70-103">_**上次修改的主题：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="a0a70-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="a0a70-104">UserAgent 视图会存储有关在数据库中含有记录的会话中所涉及的用户代理的信息。</span><span class="sxs-lookup"><span data-stu-id="a0a70-104">The UserAgent View stores information about the user agents that have been involved in sessions that have records in the database.</span></span> <span data-ttu-id="a0a70-105">此视图是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="a0a70-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a0a70-106">列</span><span class="sxs-lookup"><span data-stu-id="a0a70-106">Column</span></span></th>
<th><span data-ttu-id="a0a70-107">数据类型</span><span class="sxs-lookup"><span data-stu-id="a0a70-107">Data Type</span></span></th>
<th><span data-ttu-id="a0a70-108">详细信息</span><span class="sxs-lookup"><span data-stu-id="a0a70-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a0a70-109">UserAgentKey</span><span class="sxs-lookup"><span data-stu-id="a0a70-109">UserAgentKey</span></span></p></td>
<td><p><span data-ttu-id="a0a70-110">int</span><span class="sxs-lookup"><span data-stu-id="a0a70-110">int</span></span></p></td>
<td><p><span data-ttu-id="a0a70-111">标识此用户代理的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="a0a70-111">Unique number identifying this user agent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0a70-112">UserAgent</span><span class="sxs-lookup"><span data-stu-id="a0a70-112">UserAgent</span></span></p></td>
<td><p><span data-ttu-id="a0a70-113">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="a0a70-113">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a0a70-114">用户代理字符串。</span><span class="sxs-lookup"><span data-stu-id="a0a70-114">User agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0a70-115">UAType</span><span class="sxs-lookup"><span data-stu-id="a0a70-115">UAType</span></span></p></td>
<td><p><span data-ttu-id="a0a70-116">smallint</span><span class="sxs-lookup"><span data-stu-id="a0a70-116">smallint</span></span></p></td>
<td><p><span data-ttu-id="a0a70-117">用户代理的类型。</span><span class="sxs-lookup"><span data-stu-id="a0a70-117">Type of user agent.</span></span> <span data-ttu-id="a0a70-118">有关更多详细信息，请参阅 <a href="lync-server-2013-useragent-table.md">Lync Server 2013 中的 UserAgent 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="a0a70-118">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0a70-119">UACategory</span><span class="sxs-lookup"><span data-stu-id="a0a70-119">UACategory</span></span></p></td>
<td><p><span data-ttu-id="a0a70-120">nvarchar (64) </span><span class="sxs-lookup"><span data-stu-id="a0a70-120">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="a0a70-p103">用户代理所属的类别。例如，用户代理 Conferencing_Attendant_1.0 属于 UACategory CAA。</span><span class="sxs-lookup"><span data-stu-id="a0a70-p103">Category that the user agent belongs to. For example, the user agent Conferencing_Attendant_1.0 belongs to the UACategory CAA.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

