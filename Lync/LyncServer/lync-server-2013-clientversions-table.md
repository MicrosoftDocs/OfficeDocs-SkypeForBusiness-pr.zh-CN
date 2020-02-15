---
title: Lync Server 2013： ClientVersions 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ClientVersions table
ms:assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398356(v=OCS.15)
ms:contentKeyID: 48184176
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e05344d7b97d4bcb0c093058b7642ca8d9b8676
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046675"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="clientversions-table-in-lync-server-2013"></a><span data-ttu-id="cae37-102">Lync Server 2013 中的 ClientVersions 表</span><span class="sxs-lookup"><span data-stu-id="cae37-102">ClientVersions table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cae37-103">_**上次修改的主题：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="cae37-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="cae37-p101">ClientVersions 表是一个支持表，用于存储已参与数据库中记录的会话的各种客户端类型和版本的列表。表中的每条记录都代表一个客户端版本。</span><span class="sxs-lookup"><span data-stu-id="cae37-p101">The ClientVersions table is a supporting table that stores a list of the various client types and versions that have participated in sessions recorded in the database. Each record in the table represents one client version.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cae37-106">列</span><span class="sxs-lookup"><span data-stu-id="cae37-106">Column</span></span></th>
<th><span data-ttu-id="cae37-107">数据类型</span><span class="sxs-lookup"><span data-stu-id="cae37-107">Data Type</span></span></th>
<th><span data-ttu-id="cae37-108">键/索引</span><span class="sxs-lookup"><span data-stu-id="cae37-108">Key/Index</span></span></th>
<th><span data-ttu-id="cae37-109">详细信息</span><span class="sxs-lookup"><span data-stu-id="cae37-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cae37-110"><strong>VersionId</strong></span><span class="sxs-lookup"><span data-stu-id="cae37-110"><strong>VersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="cae37-111"><strong>int</strong></span><span class="sxs-lookup"><span data-stu-id="cae37-111"><strong>int</strong></span></span></p></td>
<td><p><span data-ttu-id="cae37-112">主</span><span class="sxs-lookup"><span data-stu-id="cae37-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="cae37-113">标识此客户端类型和版本的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="cae37-113">Unique number identifying this client type and version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cae37-114"><strong>版本</strong></span><span class="sxs-lookup"><span data-stu-id="cae37-114"><strong>Version</strong></span></span></p></td>
<td><p><span data-ttu-id="cae37-115"><strong>nvarchar （256）</strong></span><span class="sxs-lookup"><span data-stu-id="cae37-115"><strong>nvarchar(256)</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cae37-116">版本名称。</span><span class="sxs-lookup"><span data-stu-id="cae37-116">Version name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cae37-117"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="cae37-117"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="cae37-118">int</span><span class="sxs-lookup"><span data-stu-id="cae37-118">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cae37-119">指定会话中使用的客户端的类型。</span><span class="sxs-lookup"><span data-stu-id="cae37-119">Specifies the type of client used in the session.</span></span> <span data-ttu-id="cae37-120">有关详细信息，请参阅<a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表</a>。</span><span class="sxs-lookup"><span data-stu-id="cae37-120">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="cae37-121">此字段是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="cae37-121">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

