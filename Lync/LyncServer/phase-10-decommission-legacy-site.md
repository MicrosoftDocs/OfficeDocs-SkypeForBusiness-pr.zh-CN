---
title: 阶段10：停止旧版网站
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: 'Phase 10: Decommission legacy site'
ms:assetid: d591a310-3b5c-4092-b19e-0349616e40df
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205300(v=OCS.15)
ms:contentKeyID: 48185540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d40c988822a27a34f148e4e1e7893a077965fcd
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751154"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="phase-10-decommission-legacy-site"></a><span data-ttu-id="4059b-102">阶段10：停止旧版网站</span><span class="sxs-lookup"><span data-stu-id="4059b-102">Phase 10: Decommission legacy site</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4059b-103">_**上次修改的主题：** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="4059b-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="4059b-104">以下主题提供了有关如何使池退役以及从 Office 通信服务器 2007 R2 的旧部署中停用和删除服务器和池的指南。</span><span class="sxs-lookup"><span data-stu-id="4059b-104">The following topics provide guidance in decommissioning pools, and deactivating and removing servers and pools from a legacy deployment of Office Communications Server 2007 R2.</span></span> <span data-ttu-id="4059b-105">并非本节中列出的所有过程都是必需的。</span><span class="sxs-lookup"><span data-stu-id="4059b-105">Not all of the procedures listed in this section are required.</span></span> <span data-ttu-id="4059b-106">请阅读下面每个主题中的信息，以确定要使用的停用过程。</span><span class="sxs-lookup"><span data-stu-id="4059b-106">Read the information in each of these topics to determine which decommissioning procedure to use.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="4059b-107">如果您导入会议目录以将电话拨入式会议加入 Lync Server 2013，那么在开始解除池的准备之前，必须将会议目录所有权转移到 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="4059b-107">If you imported conference directories for dial-in conferencing to Lync Server 2013, it is important to transition conference directory ownership to Lync Server 2013 before you begin to decommission your pools.</span></span> <span data-ttu-id="4059b-108">如果停用池时没有先转移会议目录所有权，则所有迁移会议的拨入功能将不再起作用。</span><span class="sxs-lookup"><span data-stu-id="4059b-108">If you decommission a pool without first transitioning conference directory ownership, the dial-in feature for all migrated meetings will no longer work.</span></span> <span data-ttu-id="4059b-109">必须为旧池中的每个会议目录执行一次转移所有权的步骤。</span><span class="sxs-lookup"><span data-stu-id="4059b-109">You must perform the step to transition ownership once for each conference directory in your legacy pool.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4059b-110">若要了解如何迁移和升级 Microsoft 统一通信托管 API （UCMA）应用程序，在取消旧环境之前，请参阅<A href="https://go.microsoft.com/fwlink/p/?linkid=269555">https://go.microsoft.com/fwlink/p/?LinkId=269555</A></span><span class="sxs-lookup"><span data-stu-id="4059b-110">For information on migrating and upgrading Microsoft Unified Communications Managed API (UCMA) applications, prior to decommissioning your legacy environment, see <A href="https://go.microsoft.com/fwlink/p/?linkid=269555">https://go.microsoft.com/fwlink/p/?LinkId=269555</A></span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4059b-111">本部分内容</span><span class="sxs-lookup"><span data-stu-id="4059b-111">In This Section</span></span>

  - [<span data-ttu-id="4059b-112">移动会议目录</span><span class="sxs-lookup"><span data-stu-id="4059b-112">Move conference directories</span></span>](move-conference-directories.md)

  - [<span data-ttu-id="4059b-113">更新 DNS SRV 记录</span><span class="sxs-lookup"><span data-stu-id="4059b-113">Update DNS SRV records</span></span>](update-dns-srv-records_1.md)

  - [<span data-ttu-id="4059b-114">退役服务器和池</span><span class="sxs-lookup"><span data-stu-id="4059b-114">Decommissioning servers and pools</span></span>](decommissioning-servers-and-pools.md)

  - [<span data-ttu-id="4059b-115">删除 BackCompatSite</span><span class="sxs-lookup"><span data-stu-id="4059b-115">Remove BackCompatSite</span></span>](remove-backcompatsite.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

