---
title: Lync Server 2013：规划安全性
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for security
ms:assetid: 17eeba87-cafa-4e9b-852d-c017a7d10d59
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn342827(v=OCS.15)
ms:contentKeyID: 56107267
ms.date: 06/22/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd4fb61648e5d2adb8b49ceb56cc550fd0d2960e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152700"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-security-in-lync-server-2013"></a><span data-ttu-id="aaa29-102">在 Lync Server 2013 中规划安全性</span><span class="sxs-lookup"><span data-stu-id="aaa29-102">Planning for security in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aaa29-103">_**上次修改的主题：** 2016-06-22_</span><span class="sxs-lookup"><span data-stu-id="aaa29-103">_**Topic Last Modified:** 2016-06-22_</span></span>

<span data-ttu-id="aaa29-104">使用此安全部分可评估和管理 Lync Server 2013 部署的安全风险。</span><span class="sxs-lookup"><span data-stu-id="aaa29-104">Use this security section to assess and manage security risks to your deployment of Lync Server 2013.</span></span>

<span data-ttu-id="aaa29-105">即使你的 Lync Server 2013 部署适中，你的网络中的组件也可能拥有自己的安全文档。</span><span class="sxs-lookup"><span data-stu-id="aaa29-105">Even if your Lync Server 2013 deployment is modest, you probably have components in your network that have their own security documentation.</span></span> <span data-ttu-id="aaa29-106">因此，此部分不太可能涵盖与您的部署相关的所有组件和区域的安全性的所有方面。</span><span class="sxs-lookup"><span data-stu-id="aaa29-106">Therefore, it is unlikely that this section covers all aspects of security for all components and areas that are pertinent to your deployment.</span></span>

<span data-ttu-id="aaa29-107">将此部分用作解决 Lync Server 2013 部署安全的起点。</span><span class="sxs-lookup"><span data-stu-id="aaa29-107">Use this section as a starting point to address the security of your Lync Server 2013 deployment.</span></span> <span data-ttu-id="aaa29-108">它提供了用于评估和管理最常见的安全风险的一般准则和最佳做法。</span><span class="sxs-lookup"><span data-stu-id="aaa29-108">It provides general guidelines and best practices for assessing and managing the most common security risks.</span></span> <span data-ttu-id="aaa29-109">在每个主题的末尾列出了其他产品和安全资源。</span><span class="sxs-lookup"><span data-stu-id="aaa29-109">Additional product and security resources are listed at the end of each topic.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="aaa29-110">安全性是一个不断发展的主题。</span><span class="sxs-lookup"><span data-stu-id="aaa29-110">Security is a constantly evolving topic.</span></span> <span data-ttu-id="aaa29-111">随着新威胁和解决方案的出现，应使用最新的资料替换过期的文档、解决方案、方法和过程。</span><span class="sxs-lookup"><span data-stu-id="aaa29-111">As new threats and solutions arise, outdated documents, solutions, methods, and procedures should be replaced with up-to-date material.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="aaa29-112">本部分内容</span><span class="sxs-lookup"><span data-stu-id="aaa29-112">In This Section</span></span>

  - [<span data-ttu-id="aaa29-113">Lync Server 2013 中的关键安全功能</span><span class="sxs-lookup"><span data-stu-id="aaa29-113">Key security features in Lync Server 2013</span></span>](lync-server-2013-key-security-features.md)

  - [<span data-ttu-id="aaa29-114">现代的日期计算中的常见安全威胁</span><span class="sxs-lookup"><span data-stu-id="aaa29-114">Common security threats in modern day computing</span></span>](lync-server-2013-common-security-threats-in-modern-day-computing.md)

  - [<span data-ttu-id="aaa29-115">Lync Server 2013 的防病毒扫描排除</span><span class="sxs-lookup"><span data-stu-id="aaa29-115">Antivirus scanning exclusions for Lync Server 2013</span></span>](lync-server-2013-antivirus-scanning-exclusions.md)

  - [<span data-ttu-id="aaa29-116">Lync Server 2013 的安全框架</span><span class="sxs-lookup"><span data-stu-id="aaa29-116">Security framework for Lync Server 2013</span></span>](lync-server-2013-security-framework-for-lync-server.md)

  - [<span data-ttu-id="aaa29-117">解决 Lync Server 2013 对核心基础结构的威胁</span><span class="sxs-lookup"><span data-stu-id="aaa29-117">Addressing threats to your core infrastructure for Lync Server 2013</span></span>](lync-server-2013-addressing-threats-to-your-core-infrastructure.md)

  - [<span data-ttu-id="aaa29-118">在 Lync Server 2013 中部署 SQL Server 非标准端口和别名</span><span class="sxs-lookup"><span data-stu-id="aaa29-118">Deploying a SQL Server nonstandard port and alias in Lync Server 2013</span></span>](deploying-a-sql-server-nonstandard-port-and-alias-in-lync-server-2013.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

