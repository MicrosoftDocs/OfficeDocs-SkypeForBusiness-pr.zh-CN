---
title: Lync Server 2013： CodecDescription 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: CodecDescription table
ms:assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204797(v=OCS.15)
ms:contentKeyID: 48183802
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4be7b878d3d9b6457fbda7a081db9b6b6cb80314
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045834"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="codecdescription-table-in-lync-server-2013"></a><span data-ttu-id="51437-102">Lync Server 2013 中的 CodecDescription 表</span><span class="sxs-lookup"><span data-stu-id="51437-102">CodecDescription table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="51437-103">_**上次修改的主题：** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="51437-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="51437-104">CodecDescription 表可将唯一编解码器标识符映射到其相应的编解码器。</span><span class="sxs-lookup"><span data-stu-id="51437-104">The CodecDescription table maps unique codec identifiers to their corresponding codec.</span></span> <span data-ttu-id="51437-105">编解码器用于对传输和广播的数字信号进行编码，然后解码这些信号以进行播放。</span><span class="sxs-lookup"><span data-stu-id="51437-105">Codecs are used to encode digital signals for transmission and broadcast, and then to decode those signals for playback.</span></span> <span data-ttu-id="51437-106">此表是在 Microsoft Lync Server 2013 中引入的</span><span class="sxs-lookup"><span data-stu-id="51437-106">This table was introduced in Microsoft Lync Server 2013</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="51437-107"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="51437-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="51437-108"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="51437-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="51437-109"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="51437-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="51437-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="51437-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="51437-111"><strong>CodecDescriptionKey</strong></span><span class="sxs-lookup"><span data-stu-id="51437-111"><strong>CodecDescriptionKey</strong></span></span></p></td>
<td><p><span data-ttu-id="51437-112">smallint</span><span class="sxs-lookup"><span data-stu-id="51437-112">smallint</span></span></p></td>
<td><p><span data-ttu-id="51437-113">主</span><span class="sxs-lookup"><span data-stu-id="51437-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="51437-114">分配给编解码器的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="51437-114">Unique identifier assigned to the codec.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51437-115"><strong>CodecDescription</strong></span><span class="sxs-lookup"><span data-stu-id="51437-115"><strong>CodecDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="51437-116">varchar （256）</span><span class="sxs-lookup"><span data-stu-id="51437-116">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="51437-117">独特</span><span class="sxs-lookup"><span data-stu-id="51437-117">Unique</span></span></p></td>
<td><p><span data-ttu-id="51437-118">与 CodecDescriptionKey 对应的编解码器的唯一说明。</span><span class="sxs-lookup"><span data-stu-id="51437-118">Unique description of the codec corresponding to the CodecDescriptionKey.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

