---
title: Lync Server 2013：IPv6 的迁移和共存注意事项
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration and coexistence considerations for IPv6
ms:assetid: 8c769c4f-c8a9-4cbf-9080-beee3be9848a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205068(v=OCS.15)
ms:contentKeyID: 48184751
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d5785b270aa3070c2b1592112ab4d5ae582e52bc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766023"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-and-coexistence-considerations-for-ipv6-in-lync-server-2013"></a><span data-ttu-id="0a882-102">Lync Server 2013 中 IPv6 的迁移和共存注意事项</span><span class="sxs-lookup"><span data-stu-id="0a882-102">Migration and coexistence considerations for IPv6 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0a882-103">_**主题上次修改时间：** 2012-06-14_</span><span class="sxs-lookup"><span data-stu-id="0a882-103">_**Topic Last Modified:** 2012-06-14_</span></span>

<span data-ttu-id="0a882-104">Lync Server 2010 或 Office 通信服务器不支持 IP 版本6（IPv6）。</span><span class="sxs-lookup"><span data-stu-id="0a882-104">IP version 6 (IPv6) is not supported on Lync Server 2010 or Office Communications Server.</span></span> <span data-ttu-id="0a882-105">出于试验目的，你可以测试 Lync Server 2010 和 Lync Server 2013 双重堆栈共存。</span><span class="sxs-lookup"><span data-stu-id="0a882-105">For piloting purposes, you can test Lync Server 2010 and Lync Server 2013 dual-stack coexistence.</span></span> <span data-ttu-id="0a882-106">我们建议在对任何池启用 IPv6 （双栈网络）之前，将给定中心站点的所有池升级到 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="0a882-106">We recommend that all pools for a given central site are upgraded to Lync Server 2013 before you enable IPv6 (dual-stack network) for any of the pools.</span></span> <span data-ttu-id="0a882-107">如果您需要为池配置仅 IPv6，则建议您在实验室环境中设置仅 IPv6 以进行测试。</span><span class="sxs-lookup"><span data-stu-id="0a882-107">If you need to configure a pool for IPv6 only, we recommend that you set up an IPv6-only pool in your lab environment for testing.</span></span>

<span data-ttu-id="0a882-108">迁移和共存期间支持下列方案：</span><span class="sxs-lookup"><span data-stu-id="0a882-108">The following scenarios are supported during migration and coexistence:</span></span>

  - <span data-ttu-id="0a882-109">Lync Server 2013、Lync Server 2010 和 Office 通信服务器2007在 IPv4 模式下与 Lync Server 2013 在双堆栈模式下共存的 R2 池。</span><span class="sxs-lookup"><span data-stu-id="0a882-109">Lync Server 2013, Lync Server 2010, and Office Communications Server 2007 R2 pools in IPv4 mode, coexisting with Lync Server 2013 in dual-stack mode.</span></span>

  - <span data-ttu-id="0a882-110">仅限 IPv6 模式下的 Lync Server 2013 池（如果仅限 IPv6 的池是孤立的池）。</span><span class="sxs-lookup"><span data-stu-id="0a882-110">Lync Server 2013 pool in IPv6-only mode, if the IPv6-only pool is siloed.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

