---
title: Lync Server 2013：规划分支站点语音恢复能力
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for branch-site voice resiliency
ms:assetid: 67713f57-3ded-4127-ac37-57d8099bf384
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398477(v=OCS.15)
ms:contentKeyID: 48184351
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fb6b586a1d98e5ec557a3f459bafe870f1f24467
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202178"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-branch-site-voice-resiliency-in-lync-server-2013"></a><span data-ttu-id="cc15a-102">在 Lync Server 2013 中规划分支站点语音恢复</span><span class="sxs-lookup"><span data-stu-id="cc15a-102">Planning for branch-site voice resiliency in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cc15a-103">_**上次修改的主题：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="cc15a-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="cc15a-104">如果要提供分支站点恢复能力（即高可用性企业语音服务），可以使用三种方法执行此操作：</span><span class="sxs-lookup"><span data-stu-id="cc15a-104">If you want to provide branch-site resiliency, that is, high-availability Enterprise Voice service, you have three options for doing so:</span></span>

  - <span data-ttu-id="cc15a-105">Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="cc15a-105">Survivable Branch Appliance</span></span>

  - <span data-ttu-id="cc15a-106">自动恢复分支服务器</span><span class="sxs-lookup"><span data-stu-id="cc15a-106">Survivable Branch Server</span></span>

  - <span data-ttu-id="cc15a-107">分支站点上的完整 Lync Server 部署</span><span class="sxs-lookup"><span data-stu-id="cc15a-107">A full Lync Server deployment at the branch site</span></span>

<span data-ttu-id="cc15a-p101">本指南将帮助您评估最适合组织的恢复能力解决方案，并基于您的恢复能力解决方案选择要使用的 PSTN 连接解决方案。还将通过介绍先决条件和其他规划注意事项来帮助您准备部署所选择的解决方案。</span><span class="sxs-lookup"><span data-stu-id="cc15a-p101">This guide will help you evaluate which resiliency solution is best for your organization and, based on your resiliency solution, which PSTN-connectivity solution to use. It will also help you prepare to deploy the solution that you choose by describing prerequisites and other planning considerations.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="cc15a-110">本部分内容</span><span class="sxs-lookup"><span data-stu-id="cc15a-110">In This Section</span></span>

  - [<span data-ttu-id="cc15a-111">Lync Server 2013 中的分支站点恢复功能</span><span class="sxs-lookup"><span data-stu-id="cc15a-111">Branch-site resiliency features in Lync Server 2013</span></span>](lync-server-2013-branch-site-resiliency-features.md)

  - [<span data-ttu-id="cc15a-112">Lync Server 2013 中的分支站点恢复解决方案</span><span class="sxs-lookup"><span data-stu-id="cc15a-112">Branch-site resiliency solutions in Lync Server 2013</span></span>](lync-server-2013-branch-site-resiliency-solutions.md)

  - [<span data-ttu-id="cc15a-113">Lync Server 2013 的分支站点恢复要求</span><span class="sxs-lookup"><span data-stu-id="cc15a-113">Branch-site resiliency requirements for Lync Server 2013</span></span>](lync-server-2013-branch-site-resiliency-requirements.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

