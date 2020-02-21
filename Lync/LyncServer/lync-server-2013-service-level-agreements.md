---
title: Lync Server 2013：服务级别协议
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Service level agreements
ms:assetid: 10899bad-e8b0-422d-83c9-1599fb3a7d17
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720321(v=OCS.15)
ms:contentKeyID: 63969580
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f902a946d272ce3a16db5f032b74ec031c7e3a7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200788"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="service-level-agreements-in-lync-server-2013"></a><span data-ttu-id="d636f-102">Lync Server 2013 中的服务级别协议</span><span class="sxs-lookup"><span data-stu-id="d636f-102">Service level agreements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d636f-103">_**上次修改的主题：** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="d636f-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="d636f-104">SLA 是一个文档，用于定义客户期望您的服务。</span><span class="sxs-lookup"><span data-stu-id="d636f-104">The SLA is a document that defines the services that your customer expects from you.</span></span> <span data-ttu-id="d636f-105">此文档的复杂性和内容很大程度上取决于客户是内部的客户（在您的环境中）还是外部的。</span><span class="sxs-lookup"><span data-stu-id="d636f-105">The complexity and content of this document depends largely on whether customers are internal (within your environment) or external.</span></span>

<div>

## <a name="external-customers"></a><span data-ttu-id="d636f-106">外部客户</span><span class="sxs-lookup"><span data-stu-id="d636f-106">External Customers</span></span>

<span data-ttu-id="d636f-107">如果您的客户是外部客户，则 SLA 可能是法律激励合同的一部分，以及在定义的服务级别范围之内或之外的绩效受影响的财务奖励和惩罚。</span><span class="sxs-lookup"><span data-stu-id="d636f-107">If your customer is external, the SLA may be part of a legal contract with financial incentives and penalties for performance that falls inside or outside defined levels of service.</span></span> <span data-ttu-id="d636f-108">若要定义这些级别的服务，应属于整体合同协商。</span><span class="sxs-lookup"><span data-stu-id="d636f-108">Defining these levels of service should be part of the overall contract negotiation.</span></span>

<span data-ttu-id="d636f-109">与所有合同一样，双方都了解期望，这一点非常重要。</span><span class="sxs-lookup"><span data-stu-id="d636f-109">As with all contracts, it’s important that both parties understand expectations.</span></span> <span data-ttu-id="d636f-110">SLA 定义了这些预期。</span><span class="sxs-lookup"><span data-stu-id="d636f-110">The SLA defines these expectations.</span></span> <span data-ttu-id="d636f-111">文档的内容应经常更改，且仅由于与客户协商而进行。</span><span class="sxs-lookup"><span data-stu-id="d636f-111">The contents of the document should change infrequently and only because of negotiations with the customer.</span></span>

</div>

<div>

## <a name="internal-customers"></a><span data-ttu-id="d636f-112">内部客户</span><span class="sxs-lookup"><span data-stu-id="d636f-112">Internal Customers</span></span>

<span data-ttu-id="d636f-113">如果您的客户是内部客户，您可能仍需要定义运营团队和 IT 系统所需的服务。</span><span class="sxs-lookup"><span data-stu-id="d636f-113">If your customer is internal, you may still want to define the services that are expected of operations teams and of IT systems.</span></span> <span data-ttu-id="d636f-114">SLA 可由操作人员创建，并可用作组织内 IT 服务可用性的一系列目标。</span><span class="sxs-lookup"><span data-stu-id="d636f-114">The SLA may be created by the operations staff and intended as a set of goals for the availability of IT services within your organization.</span></span> <span data-ttu-id="d636f-115">或者，性能级别可以在评估员工绩效时由管理部门进行管理，并将其用作基准。</span><span class="sxs-lookup"><span data-stu-id="d636f-115">Or, performance levels may be set by management and used as benchmarks when assessing staff performance.</span></span>

</div>

<div>

## <a name="typical-criteria"></a><span data-ttu-id="d636f-116">典型条件</span><span class="sxs-lookup"><span data-stu-id="d636f-116">Typical Criteria</span></span>

<span data-ttu-id="d636f-117">Sla 包括定义最低级别可用性、支持和容量的条件的各个部分。</span><span class="sxs-lookup"><span data-stu-id="d636f-117">SLAs include sections that define criteria of minimum levels of availability, support, and capacity.</span></span>

  - <span data-ttu-id="d636f-118">**可用性**   定义网站和其他 Lync services 将在其上可用的时间和操作系统。</span><span class="sxs-lookup"><span data-stu-id="d636f-118">**Availability**   Define the hours and the operating systems on which sites and other Lync services will be available.</span></span> <span data-ttu-id="d636f-119">应定义任何影响服务可用性的定期维护。</span><span class="sxs-lookup"><span data-stu-id="d636f-119">Any routine maintenance that affects service availability should be defined.</span></span> <span data-ttu-id="d636f-120">定义影响服务的外部因素，例如，Internet 连接丢失。</span><span class="sxs-lookup"><span data-stu-id="d636f-120">Define external factors that affect service, for example, the loss of Internet connectivity.</span></span>

  - <span data-ttu-id="d636f-121">**支持**   定义对系统提供支持时的小时数。</span><span class="sxs-lookup"><span data-stu-id="d636f-121">**Support**   Define the hours when support for a system will be available.</span></span> <span data-ttu-id="d636f-122">指定客户联系支持人员的方法、事件的分组方式以及目标时间以响应和解决事件。</span><span class="sxs-lookup"><span data-stu-id="d636f-122">Specify methods for customers to contact support staff, how incidents are grouped, and target time to respond and to resolve the incident.</span></span> <span data-ttu-id="d636f-123">定义反馈给客户的频率和内容。</span><span class="sxs-lookup"><span data-stu-id="d636f-123">Define frequency and content of feedback to the customer.</span></span>

  - <span data-ttu-id="d636f-124">**容量**   定义了 Lync 网站的最大启用大小以及超出限制时要采取的步骤。</span><span class="sxs-lookup"><span data-stu-id="d636f-124">**Capacity**   Define the maximum enabled size of Lync sites and the steps to take if the limit is exceeded.</span></span> <span data-ttu-id="d636f-125">定义要执行标准任务的最大启用时间，如从文档库中检索文档的时间。</span><span class="sxs-lookup"><span data-stu-id="d636f-125">Define the maximum enabled time to do standard tasks, such as the time to retrieve a document from a document library.</span></span> <span data-ttu-id="d636f-126">定义每个 Lync 池的最大用户数，并同意在添加更多用户时增加容量的过程。</span><span class="sxs-lookup"><span data-stu-id="d636f-126">Define the maximum number of users per Lync pool and agree to a process to increase capacity if more users are added.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

