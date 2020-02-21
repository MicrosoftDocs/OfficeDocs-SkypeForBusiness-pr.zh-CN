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
ms.openlocfilehash: 084a02c9add6b383d6099073992f27d8955a66d1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195445"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="contenttypes-table-in-lync-server-2013"></a><span data-ttu-id="7ec1e-102">Lync Server 2013 中的 ContentTypes 表</span><span class="sxs-lookup"><span data-stu-id="7ec1e-102">ContentTypes table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7ec1e-103">_**上次修改的主题：** 2010-11-07_</span><span class="sxs-lookup"><span data-stu-id="7ec1e-103">_**Topic Last Modified:** 2010-11-07_</span></span>

<span data-ttu-id="7ec1e-104">ContentTypes 表是一个支持表，它存储对等会话和会议会话中使用的内容类型的列表。</span><span class="sxs-lookup"><span data-stu-id="7ec1e-104">The ContentTypes table is a supporting table that stores a list of the content types used in both peer-to-peer sessions and conference sessions.</span></span> <span data-ttu-id="7ec1e-105">表中的每条记录都代表一种内容类型。</span><span class="sxs-lookup"><span data-stu-id="7ec1e-105">Each record in the table represents one content type.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7ec1e-106">列</span><span class="sxs-lookup"><span data-stu-id="7ec1e-106">Column</span></span></th>
<th><span data-ttu-id="7ec1e-107">数据类型</span><span class="sxs-lookup"><span data-stu-id="7ec1e-107">Data Type</span></span></th>
<th><span data-ttu-id="7ec1e-108">键/索引</span><span class="sxs-lookup"><span data-stu-id="7ec1e-108">Key/Index</span></span></th>
<th><span data-ttu-id="7ec1e-109">详细信息</span><span class="sxs-lookup"><span data-stu-id="7ec1e-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7ec1e-110"><strong>ContentTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="7ec1e-110"><strong>ContentTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="7ec1e-111">int</span><span class="sxs-lookup"><span data-stu-id="7ec1e-111">int</span></span></p></td>
<td><p><span data-ttu-id="7ec1e-112">主</span><span class="sxs-lookup"><span data-stu-id="7ec1e-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="7ec1e-113">标识内容类型的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="7ec1e-113">Unique number identifying the content type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ec1e-114"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="7ec1e-114"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="7ec1e-115">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="7ec1e-115">nvarchar(256)</span></span></p></td>
<td> </td>
<td><p><span data-ttu-id="7ec1e-116">内容类型名称。</span><span class="sxs-lookup"><span data-stu-id="7ec1e-116">Content type name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

