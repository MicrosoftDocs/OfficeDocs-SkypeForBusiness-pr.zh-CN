---
title: '第10阶段: 停止旧版网站'
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: 'Phase 10: Decommission legacy site'
ms:assetid: d591a310-3b5c-4092-b19e-0349616e40df
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205300(v=OCS.15)
ms:contentKeyID: 48185540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a04054c158f1c97f5090328e1277dcdb63b1d823
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845172"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="phase-10-decommission-legacy-site"></a><span data-ttu-id="6abcc-102">第10阶段: 停止旧版网站</span><span class="sxs-lookup"><span data-stu-id="6abcc-102">Phase 10: Decommission legacy site</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6abcc-103">_**主题上次修改时间:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="6abcc-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="6abcc-104">以下主题提供了解除池的指导, 以及从 Office 通信服务器 2007 R2 的传统部署中停用和删除服务器和池的指南。</span><span class="sxs-lookup"><span data-stu-id="6abcc-104">The following topics provide guidance in decommissioning pools, and deactivating and removing servers and pools from a legacy deployment of Office Communications Server 2007 R2.</span></span> <span data-ttu-id="6abcc-105">不需要本部分中列出的所有过程。</span><span class="sxs-lookup"><span data-stu-id="6abcc-105">Not all of the procedures listed in this section are required.</span></span> <span data-ttu-id="6abcc-106">阅读其中每个主题中的信息, 确定要使用的解除授权过程。</span><span class="sxs-lookup"><span data-stu-id="6abcc-106">Read the information in each of these topics to determine which decommissioning procedure to use.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="6abcc-107">如果您已将电话拨入式会议的会议目录导入到 Lync Server 2013, 则在开始取消池之前将会议目录所有权转移到 Lync Server 2013 非常重要。</span><span class="sxs-lookup"><span data-stu-id="6abcc-107">If you imported conference directories for dial-in conferencing to Lync Server 2013, it is important to transition conference directory ownership to Lync Server 2013 before you begin to decommission your pools.</span></span> <span data-ttu-id="6abcc-108">如果您在没有首先转换会议目录所有权的情况下取消池, 则所有已迁移会议的拨入功能将不再有效。</span><span class="sxs-lookup"><span data-stu-id="6abcc-108">If you decommission a pool without first transitioning conference directory ownership, the dial-in feature for all migrated meetings will no longer work.</span></span> <span data-ttu-id="6abcc-109">必须针对旧版池中的每个会议目录执行一次过渡所有权的步骤。</span><span class="sxs-lookup"><span data-stu-id="6abcc-109">You must perform the step to transition ownership once for each conference directory in your legacy pool.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6abcc-110">有关迁移和升级 Microsoft 统一通信托管 API (UCMA) 应用程序的信息, 在取消旧环境之前, 请参阅<A href="http://go.microsoft.com/fwlink/p/?linkid=269555">http://go.microsoft.com/fwlink/p/?LinkId=269555</A></span><span class="sxs-lookup"><span data-stu-id="6abcc-110">For information on migrating and upgrading Microsoft Unified Communications Managed API (UCMA) applications, prior to decommissioning your legacy environment, see <A href="http://go.microsoft.com/fwlink/p/?linkid=269555">http://go.microsoft.com/fwlink/p/?LinkId=269555</A></span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6abcc-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="6abcc-111">In This Section</span></span>

  - [<span data-ttu-id="6abcc-112">移动会议目录</span><span class="sxs-lookup"><span data-stu-id="6abcc-112">Move conference directories</span></span>](move-conference-directories.md)

  - [<span data-ttu-id="6abcc-113">更新 DNS SRV 记录</span><span class="sxs-lookup"><span data-stu-id="6abcc-113">Update DNS SRV records</span></span>](update-dns-srv-records_1.md)

  - [<span data-ttu-id="6abcc-114">服务器和池退役</span><span class="sxs-lookup"><span data-stu-id="6abcc-114">Decommissioning servers and pools</span></span>](decommissioning-servers-and-pools.md)

  - [<span data-ttu-id="6abcc-115">删除 BackCompatSite</span><span class="sxs-lookup"><span data-stu-id="6abcc-115">Remove BackCompatSite</span></span>](remove-backcompatsite.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

