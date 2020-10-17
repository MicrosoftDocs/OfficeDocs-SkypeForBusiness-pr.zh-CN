---
title: Lync Server 2013： ContentTypes 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ContentTypes table
ms:assetid: e3e38035-457c-4173-bdb9-d53a7420eba2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399007(v=OCS.15)
ms:contentKeyID: 48185723
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5aa26746e8c970fe2685aea63ef3ff43a672846f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501989"
---
# <a name="contenttypes-table-in-lync-server-2013"></a><span data-ttu-id="ca848-102">Lync Server 2013 中的 ContentTypes 表</span><span class="sxs-lookup"><span data-stu-id="ca848-102">ContentTypes table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca848-103">_**上次修改的主题：** 2010-11-07_</span><span class="sxs-lookup"><span data-stu-id="ca848-103">_**Topic Last Modified:** 2010-11-07_</span></span>

<span data-ttu-id="ca848-104">ContentTypes 表是一个支持表，它存储对等会话和会议会话中使用的内容类型的列表。</span><span class="sxs-lookup"><span data-stu-id="ca848-104">The ContentTypes table is a supporting table that stores a list of the content types used in both peer-to-peer sessions and conference sessions.</span></span> <span data-ttu-id="ca848-105">表中的每条记录都代表一种内容类型。</span><span class="sxs-lookup"><span data-stu-id="ca848-105">Each record in the table represents one content type.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ca848-106">列</span><span class="sxs-lookup"><span data-stu-id="ca848-106">Column</span></span></th>
<th><span data-ttu-id="ca848-107">数据类型</span><span class="sxs-lookup"><span data-stu-id="ca848-107">Data Type</span></span></th>
<th><span data-ttu-id="ca848-108">键/索引</span><span class="sxs-lookup"><span data-stu-id="ca848-108">Key/Index</span></span></th>
<th><span data-ttu-id="ca848-109">详细信息</span><span class="sxs-lookup"><span data-stu-id="ca848-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ca848-110"><strong>ContentTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="ca848-110"><strong>ContentTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="ca848-111">int</span><span class="sxs-lookup"><span data-stu-id="ca848-111">int</span></span></p></td>
<td><p><span data-ttu-id="ca848-112">主</span><span class="sxs-lookup"><span data-stu-id="ca848-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="ca848-113">标识内容类型的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="ca848-113">Unique number identifying the content type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca848-114"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="ca848-114"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="ca848-115">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="ca848-115">nvarchar(256)</span></span></p></td>
<td> </td>
<td><p><span data-ttu-id="ca848-116">内容类型名称。</span><span class="sxs-lookup"><span data-stu-id="ca848-116">Content type name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

