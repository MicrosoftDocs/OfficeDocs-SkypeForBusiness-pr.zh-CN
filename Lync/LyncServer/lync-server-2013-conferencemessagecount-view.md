---
title: Lync Server 2013： ConferenceMessageCount 视图
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceMessageCount view
ms:assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688129(v=OCS.15)
ms:contentKeyID: 49733727
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a35b1f223c16c1a490197a11206ea972816c94e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140595"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferencemessagecount-view-in-lync-server-2013"></a><span data-ttu-id="faeec-102">Lync Server 2013 中的 ConferenceMessageCount 视图</span><span class="sxs-lookup"><span data-stu-id="faeec-102">ConferenceMessageCount view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="faeec-103">_**上次修改的主题：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="faeec-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="faeec-104">ConferenceMessageCount 视图存储有关用户已向会议中发送的消息数的信息。</span><span class="sxs-lookup"><span data-stu-id="faeec-104">The ConferenceMessageCount view stores information about how many messages were sent by a user to a conference.</span></span> <span data-ttu-id="faeec-105">此视图是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="faeec-105">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="faeec-106">ConferenceMessageCount 视图包含在<A href="lync-server-2013-conferencesessiondetails-view.md">Lync Server 2013 的 ConferenceSessionDetails 视图</A>中的所有列，此外还列出了下面列出的列。</span><span class="sxs-lookup"><span data-stu-id="faeec-106">The ConferenceMessageCount view contains all of the columns in the <A href="lync-server-2013-conferencesessiondetails-view.md">ConferenceSessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="faeec-107">列</span><span class="sxs-lookup"><span data-stu-id="faeec-107">Column</span></span></th>
<th><span data-ttu-id="faeec-108">数据类型</span><span class="sxs-lookup"><span data-stu-id="faeec-108">Data Type</span></span></th>
<th><span data-ttu-id="faeec-109">详细信息</span><span class="sxs-lookup"><span data-stu-id="faeec-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="faeec-110"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="faeec-110"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="faeec-111">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="faeec-111">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="faeec-112">发送消息的用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="faeec-112">URI of the user who sent the message.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="faeec-113"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="faeec-113"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="faeec-114">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="faeec-114">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="faeec-115">发送消息的用户的 URI 类型。</span><span class="sxs-lookup"><span data-stu-id="faeec-115">Type of URI of the user who sent the messages.</span></span> <span data-ttu-id="faeec-116">有关详细信息，请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</span><span class="sxs-lookup"><span data-stu-id="faeec-116">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="faeec-117"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="faeec-117"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="faeec-118">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="faeec-118">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="faeec-119">发送消息的用户的租户。</span><span class="sxs-lookup"><span data-stu-id="faeec-119">Tenant of user who sent the messages.</span></span> <span data-ttu-id="faeec-120">有关详细信息，请参阅<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a>。</span><span class="sxs-lookup"><span data-stu-id="faeec-120">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="faeec-121"><strong>UserMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="faeec-121"><strong>UserMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="faeec-122">smallint</span><span class="sxs-lookup"><span data-stu-id="faeec-122">smallint</span></span></p></td>
<td><p><span data-ttu-id="faeec-123">用户在会议会话期间发送的消息数。</span><span class="sxs-lookup"><span data-stu-id="faeec-123">Number of messages sent by the user during the conference session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

