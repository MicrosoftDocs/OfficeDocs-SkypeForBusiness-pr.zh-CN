---
title: Lync Server 2013：Application 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Application table
ms:assetid: 30938426-e2f9-4735-a7f4-59baf7a7d7e6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425808(v=OCS.15)
ms:contentKeyID: 48183757
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 649463f3fe543e17172ecf69daa5a380c2b5e774
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737612"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="application-table-in-lync-server-2013"></a><span data-ttu-id="762e0-102">Lync Server 2013 中的 Application 表</span><span class="sxs-lookup"><span data-stu-id="762e0-102">Application table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="762e0-103">_**主题上次修改时间：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="762e0-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="762e0-104">此表存储有关路由和连接的 Lync Server 2013 中的各种进程的信息。</span><span class="sxs-lookup"><span data-stu-id="762e0-104">This table stores information about the various processes within Lync Server 2013 involved in routing and connections.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="762e0-105">列</span><span class="sxs-lookup"><span data-stu-id="762e0-105">Column</span></span></th>
<th><span data-ttu-id="762e0-106">数据类型</span><span class="sxs-lookup"><span data-stu-id="762e0-106">Data Type</span></span></th>
<th><span data-ttu-id="762e0-107">键/索引</span><span class="sxs-lookup"><span data-stu-id="762e0-107">Key/Index</span></span></th>
<th><span data-ttu-id="762e0-108">详细信息</span><span class="sxs-lookup"><span data-stu-id="762e0-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="762e0-109"><strong>ApplicationId</strong></span><span class="sxs-lookup"><span data-stu-id="762e0-109"><strong>ApplicationId</strong></span></span></p></td>
<td><p><span data-ttu-id="762e0-110">int</span><span class="sxs-lookup"><span data-stu-id="762e0-110">int</span></span></p></td>
<td><p><span data-ttu-id="762e0-111">Primary</span><span class="sxs-lookup"><span data-stu-id="762e0-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="762e0-112">标识此应用程序的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="762e0-112">Unique number identifying this application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="762e0-113"><strong>名称</strong> - 按 WAN 链路进行筛选（筛选器位于图形右侧）。</span><span class="sxs-lookup"><span data-stu-id="762e0-113"><strong>Name</strong></span></span></p></td>
<td><p><span data-ttu-id="762e0-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="762e0-114">nvarchar(256)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="762e0-115">服务器组件的名称。</span><span class="sxs-lookup"><span data-stu-id="762e0-115">Name of the server component.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

