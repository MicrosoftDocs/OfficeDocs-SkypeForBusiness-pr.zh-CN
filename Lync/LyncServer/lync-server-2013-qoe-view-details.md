---
title: Lync Server 2013： QoE 查看详细信息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: QoE view details
ms:assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688081(v=OCS.15)
ms:contentKeyID: 49733677
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d47fb90b7ffb9eb0cb7fcd1631a0f00ca249276a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724602"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="qoe-view-details-in-lync-server-2013"></a><span data-ttu-id="25bc8-102">QoE 在 Lync Server 2013 中查看详细信息</span><span class="sxs-lookup"><span data-stu-id="25bc8-102">QoE view details in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="25bc8-103">_**主题上次修改时间：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="25bc8-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="25bc8-104">视图涵盖从 QoE SQL 数据库返回数据的最常见方案。</span><span class="sxs-lookup"><span data-stu-id="25bc8-104">Views cover the most common scenarios for returning data from the QoE SQL database.</span></span> <span data-ttu-id="25bc8-105">推荐用于构建自定义报表的视图，而不是直接访问数据库表;这是因为视图更有可能保持与未来版本的向后兼容性。</span><span class="sxs-lookup"><span data-stu-id="25bc8-105">It is recommended views used for building custom reports instead of directly accessing the database tables; that’s because views are more likely to maintain backwards compatibility with future releases.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="25bc8-106">视图名称</span><span class="sxs-lookup"><span data-stu-id="25bc8-106">View Name</span></span></th>
<th><span data-ttu-id="25bc8-107">说明</span><span class="sxs-lookup"><span data-stu-id="25bc8-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="25bc8-108"><a href="lync-server-2013-audiostreamdetail-view.md">Lync Server 2013 中的 AudioStreamDetail 视图</a></span><span class="sxs-lookup"><span data-stu-id="25bc8-108"><a href="lync-server-2013-audiostreamdetail-view.md">AudioStreamDetail view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="25bc8-109">存储有关数据库中每个音频流的信息。</span><span class="sxs-lookup"><span data-stu-id="25bc8-109">Stores information about each audio stream in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25bc8-110"><a href="lync-server-2013-medialine-view.md">Lync Server 2013 中的 MediaLine 视图</a></span><span class="sxs-lookup"><span data-stu-id="25bc8-110"><a href="lync-server-2013-medialine-view.md">MediaLine view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="25bc8-111">存储有关数据库中每个媒体行的信息。</span><span class="sxs-lookup"><span data-stu-id="25bc8-111">Stores information about each media line in the database.</span></span> <span data-ttu-id="25bc8-112">一个音频会话通常包含一个音频媒体行。</span><span class="sxs-lookup"><span data-stu-id="25bc8-112">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="25bc8-113">一个音频和视频（A/V）会话通常包含一个音频媒体线和一个视频媒体行;但是，如果使用了会议设备或使用了库视图，则会话可能包含两个视频媒体线。</span><span class="sxs-lookup"><span data-stu-id="25bc8-113">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25bc8-114"><a href="lync-server-2013-networkconfigurationsettings-view.md">Lync Server 2013 中的 NetworkConfigurationSettings 视图</a></span><span class="sxs-lookup"><span data-stu-id="25bc8-114"><a href="lync-server-2013-networkconfigurationsettings-view.md">NetworkConfigurationSettings view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="25bc8-115">存储有关网络配置的信息。</span><span class="sxs-lookup"><span data-stu-id="25bc8-115">Stores information about the network configuration.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25bc8-116"><a href="lync-server-2013-session-view.md">Lync Server 2013 中的 "会话" 视图</a></span><span class="sxs-lookup"><span data-stu-id="25bc8-116"><a href="lync-server-2013-session-view.md">Session view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="25bc8-117">存储有关在数据库中具有记录的会话的信息。</span><span class="sxs-lookup"><span data-stu-id="25bc8-117">Stores information about sessions that have records in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25bc8-118"><a href="lync-server-2013-useragent-view.md">Lync Server 2013 中的 UserAgent 视图</a></span><span class="sxs-lookup"><span data-stu-id="25bc8-118"><a href="lync-server-2013-useragent-view.md">UserAgent view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="25bc8-119">存储有关在数据库中具有记录的会话中涉及的用户代理的信息。</span><span class="sxs-lookup"><span data-stu-id="25bc8-119">Stores information about the user agents that have been involved in sessions that have records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25bc8-120"><a href="lync-server-2013-videostreamdetail-view.md">Lync Server 2013 中的 VideoStreamDetail 视图</a></span><span class="sxs-lookup"><span data-stu-id="25bc8-120"><a href="lync-server-2013-videostreamdetail-view.md">VideoStreamDetail view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="25bc8-121">存储有关数据库中的每个视频流的信息。</span><span class="sxs-lookup"><span data-stu-id="25bc8-121">Stores information about each video stream in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

