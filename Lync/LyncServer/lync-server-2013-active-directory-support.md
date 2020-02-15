---
title: Lync Server 2013 Active Directory 支持
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory support
ms:assetid: 28ed9ac4-586d-4803-ad45-99c4fa793f54
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425756(v=OCS.15)
ms:contentKeyID: 48183679
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b3ded5de5500778559efe632c5272db50b0eadbd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034112"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-support-in-lync-server-2013"></a><span data-ttu-id="203a2-102">Lync Server 2013 中的 Active Directory 支持</span><span class="sxs-lookup"><span data-stu-id="203a2-102">Active Directory support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="203a2-103">_**上次修改的主题：** 2012-12-04_</span><span class="sxs-lookup"><span data-stu-id="203a2-103">_**Topic Last Modified:** 2012-12-04_</span></span>

<span data-ttu-id="203a2-104">Lync Server 2013 支持的 Active Directory 域服务本地拓扑如下所示：</span><span class="sxs-lookup"><span data-stu-id="203a2-104">The Active Directory Domain Services on-premises topologies that are supported by Lync Server 2013 are as follows:</span></span>

  - <span data-ttu-id="203a2-105">具有单个域的单林</span><span class="sxs-lookup"><span data-stu-id="203a2-105">Single forest with single domain</span></span>

  - <span data-ttu-id="203a2-106">具有单个树和多个域的单林</span><span class="sxs-lookup"><span data-stu-id="203a2-106">Single forest with a single tree and multiple domains</span></span>

  - <span data-ttu-id="203a2-107">具有多个树和互不连接的命名空间的单林</span><span class="sxs-lookup"><span data-stu-id="203a2-107">Single forest with multiple trees and disjoint namespaces</span></span>

  - <span data-ttu-id="203a2-108">中央林拓扑中的多林</span><span class="sxs-lookup"><span data-stu-id="203a2-108">Multiple forests in a central forest topology</span></span>

  - <span data-ttu-id="203a2-109">资源林拓扑中的多林</span><span class="sxs-lookup"><span data-stu-id="203a2-109">Multiple forests in a resource forest topology</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="203a2-110">Lync Server 2013 不支持单标签域。</span><span class="sxs-lookup"><span data-stu-id="203a2-110">Lync Server 2013 does not support single-label domains.</span></span> <span data-ttu-id="203a2-111">例如，支持具有名为<STRONG>contoso. local</STRONG>的根域的林，但不支持名为<STRONG>local</STRONG>的单标签根域。</span><span class="sxs-lookup"><span data-stu-id="203a2-111">For example, a forest with a root domain named <STRONG>contoso.local</STRONG> is supported, but a single-label root domain named <STRONG>local</STRONG> is not supported.</span></span> <span data-ttu-id="203a2-112">有关详细信息，请参阅 Microsoft 知识库文章 300684 "有关为带有单标签 DNS 名称的域配置 Windows 的信息" <A href="http://go.microsoft.com/fwlink/p/?linkid=143752">http://go.microsoft.com/fwlink/p/?linkId=143752</A>。</span><span class="sxs-lookup"><span data-stu-id="203a2-112">For details, see Microsoft Knowledge Base article 300684, "Information about configuring Windows for domains with single-label DNS names," at <A href="http://go.microsoft.com/fwlink/p/?linkid=143752">http://go.microsoft.com/fwlink/p/?linkId=143752</A>.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="203a2-113">Lync Server 2013 不支持对域进行重命名。</span><span class="sxs-lookup"><span data-stu-id="203a2-113">Lync Server 2013 does not support renaming domains.</span></span> <span data-ttu-id="203a2-114">如果需要重命名已在其中部署 Lync Server 的域，则需要先卸载 Lync Server，再重命名域，然后重新安装 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="203a2-114">If you need to rename a domain where Lync Server is deployed, you need to first uninstall Lync Server, then rename the domain, and then reinstall Lync Server.</span></span>



</div>

<span data-ttu-id="203a2-115">有关支持的拓扑和本地部署要求的详细信息，请参阅规划文档中的[Lync Server 2013 中的 Active Directory 域服务要求、支持和拓扑](lync-server-2013-active-directory-domain-services-requirements-support-and-topologies.md)。</span><span class="sxs-lookup"><span data-stu-id="203a2-115">For details about supported topologies and requirements for on-premises deployments, see [Active Directory Domain Services requirements, support, and topologies in Lync Server 2013](lync-server-2013-active-directory-domain-services-requirements-support-and-topologies.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

