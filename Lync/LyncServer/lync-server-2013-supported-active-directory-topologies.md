---
title: Lync Server 2013：支持的 Active Directory 拓扑
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Supported Active Directory topologies
ms:assetid: 0c76b778-7652-4eb0-b161-86f2d4a94ccf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398173(v=OCS.15)
ms:contentKeyID: 48183391
ms.date: 10/02/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3dc15cea3d07dc4e00f1d2a5527c862d90a078c6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845784"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-active-directory-topologies-in-lync-server-2013"></a><span data-ttu-id="aa7c9-102">Lync Server 2013 中支持的 Active Directory 拓扑</span><span class="sxs-lookup"><span data-stu-id="aa7c9-102">Supported Active Directory topologies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aa7c9-103">_**主题上次修改时间:** 2014-10-02_</span><span class="sxs-lookup"><span data-stu-id="aa7c9-103">_**Topic Last Modified:** 2014-10-02_</span></span>

<span data-ttu-id="aa7c9-104">Lync Server 2013 支持与 Microsoft Lync Server 2010 和 Microsoft Office 通信服务器 2007 R2 相同的 Active Directory 域服务拓扑。</span><span class="sxs-lookup"><span data-stu-id="aa7c9-104">Lync Server 2013 supports the same Active Directory Domain Services topologies as Microsoft Lync Server 2010 and Microsoft Office Communications Server 2007 R2.</span></span> <span data-ttu-id="aa7c9-105">支持下列拓扑:</span><span class="sxs-lookup"><span data-stu-id="aa7c9-105">The following topologies are supported:</span></span>

  - <span data-ttu-id="aa7c9-106">具有单个域的单林</span><span class="sxs-lookup"><span data-stu-id="aa7c9-106">Single forest with single domain</span></span>

  - <span data-ttu-id="aa7c9-107">具有单个树和多个域的单林</span><span class="sxs-lookup"><span data-stu-id="aa7c9-107">Single forest with a single tree and multiple domains</span></span>

  - <span data-ttu-id="aa7c9-108">具有多个树和互不连接的命名空间的单林</span><span class="sxs-lookup"><span data-stu-id="aa7c9-108">Single forest with multiple trees and disjoint namespaces</span></span>

  - <span data-ttu-id="aa7c9-109">中央林拓扑中的多林</span><span class="sxs-lookup"><span data-stu-id="aa7c9-109">Multiple forests in a central forest topology</span></span>

  - <span data-ttu-id="aa7c9-110">资源林拓扑中的多林</span><span class="sxs-lookup"><span data-stu-id="aa7c9-110">Multiple forests in a resource forest topology</span></span>

  - <span data-ttu-id="aa7c9-111">使用 Exchange Online 的 Lync 资源林拓扑中的多个林</span><span class="sxs-lookup"><span data-stu-id="aa7c9-111">Multiple forests in a Lync resource forest topology with Exchange Online</span></span>

<span data-ttu-id="aa7c9-112">下图标识了本部分中的插图中使用的图标。</span><span class="sxs-lookup"><span data-stu-id="aa7c9-112">The following figure identifies the icons used in the illustrations in this section.</span></span>

<span data-ttu-id="aa7c9-113">**拓扑图的关键**</span><span class="sxs-lookup"><span data-stu-id="aa7c9-113">**Key to topology illustrations**</span></span>

<span data-ttu-id="aa7c9-114">![拓扑图的关键](images/Gg398173.0c3cc89f-6c43-4bc8-b2ec-61d89e391ee9(OCS.15).jpg "拓扑图的关键")</span><span class="sxs-lookup"><span data-stu-id="aa7c9-114">![Key to topology illustrations](images/Gg398173.0c3cc89f-6c43-4bc8-b2ec-61d89e391ee9(OCS.15).jpg "Key to topology illustrations")</span></span>

<div>

## <a name="single-forest-single-domain"></a><span data-ttu-id="aa7c9-115">单林、单个域</span><span class="sxs-lookup"><span data-stu-id="aa7c9-115">Single Forest, Single Domain</span></span>

<span data-ttu-id="aa7c9-116">Lync Server (单个域林) 支持的最简单的活动目录拓扑是常见拓扑。</span><span class="sxs-lookup"><span data-stu-id="aa7c9-116">The simplest Active Directory topology supported by Lync Server, a single domain forest, is a common topology.</span></span>

<span data-ttu-id="aa7c9-117">下图显示了单个域 Active Directory 拓扑中的 Lync Server 部署。</span><span class="sxs-lookup"><span data-stu-id="aa7c9-117">The following figure illustrates a Lync Server deployment in a single domain Active Directory topology.</span></span>

<span data-ttu-id="aa7c9-118">**支持的 MA 与 SFB，启用了 MA 的 SFBO，加 EXCH 和 SFB。**</span><span class="sxs-lookup"><span data-stu-id="aa7c9-118">**Single domain topology**</span></span>

<span data-ttu-id="aa7c9-119">![单域拓扑](images/Gg398173.258b3b3f-0558-4a36-a4c2-031be7299668(OCS.15).jpg "单域拓扑")</span><span class="sxs-lookup"><span data-stu-id="aa7c9-119">![Single domain topology](images/Gg398173.258b3b3f-0558-4a36-a4c2-031be7299668(OCS.15).jpg "Single domain topology")</span></span>

</div>

<div>

## <a name="single-forest-multiple-domains"></a><span data-ttu-id="aa7c9-120">单个林、多个域</span><span class="sxs-lookup"><span data-stu-id="aa7c9-120">Single Forest, Multiple Domains</span></span>

<span data-ttu-id="aa7c9-121">Lync Server 支持的其他 Active Directory 拓扑是一个由根域和一个或多个子域组成的单个林。</span><span class="sxs-lookup"><span data-stu-id="aa7c9-121">Another Active Directory topology supported by Lync Server is a single forest that consists of a root domain and one or more child domains.</span></span> <span data-ttu-id="aa7c9-122">在此类型的 Active Directory 拓扑中, 你创建用户的域可能不同于你在其中部署 Lync Server 的域。</span><span class="sxs-lookup"><span data-stu-id="aa7c9-122">In this type of Active Directory topology, the domain where you create users can be different from the domain where you deploy Lync Server.</span></span> <span data-ttu-id="aa7c9-123">但是, 如果你部署前端池, 则必须在单个域内部署池中的所有前端服务器。</span><span class="sxs-lookup"><span data-stu-id="aa7c9-123">However, if you deploy a Front End pool, you must deploy all the Front End Servers in the pool within a single domain.</span></span> <span data-ttu-id="aa7c9-124">Lync Server 支持 Windows 通用管理员组支持跨域管理。</span><span class="sxs-lookup"><span data-stu-id="aa7c9-124">Lync Server support for Windows universal administrator groups enables cross-domain administration.</span></span>

<span data-ttu-id="aa7c9-125">下图显示了具有多个域的单个林中的部署。</span><span class="sxs-lookup"><span data-stu-id="aa7c9-125">The following figure illustrates a deployment in a single forest with multiple domains.</span></span> <span data-ttu-id="aa7c9-126">在此图中, 用户图标显示用户帐户所驻留的域, 箭头指向 Lync 服务器池所在的域。</span><span class="sxs-lookup"><span data-stu-id="aa7c9-126">In this figure, a user icon shows the domain where the user account is homed, and the arrow points to the domain where the Lync Server pool resides.</span></span> <span data-ttu-id="aa7c9-127">用户帐户包括以下内容:</span><span class="sxs-lookup"><span data-stu-id="aa7c9-127">User accounts include the following:</span></span>

  - <span data-ttu-id="aa7c9-128">与 Lync Server 池位于同一域中的用户帐户</span><span class="sxs-lookup"><span data-stu-id="aa7c9-128">User accounts within the same domain as the Lync Server pool</span></span>

  - <span data-ttu-id="aa7c9-129">Lync Server 池中的其他域中的用户帐户</span><span class="sxs-lookup"><span data-stu-id="aa7c9-129">User accounts in a different domain from the Lync Server pool</span></span>

  - <span data-ttu-id="aa7c9-130">使用 Lync Server 池的域的子域中的用户帐户</span><span class="sxs-lookup"><span data-stu-id="aa7c9-130">User accounts in a child domain of the domain with the Lync Server pool</span></span>

<span data-ttu-id="aa7c9-131">**具有多个域的单个林**</span><span class="sxs-lookup"><span data-stu-id="aa7c9-131">**Single forest with multiple domains**</span></span>

<span data-ttu-id="aa7c9-132">![具有多个域的单个林](images/Gg398173.2b809c72-c3cd-4fad-afe6-8c2dae779750(OCS.15).jpg "具有多个域的单个林")</span><span class="sxs-lookup"><span data-stu-id="aa7c9-132">![Single forest with multiple domains](images/Gg398173.2b809c72-c3cd-4fad-afe6-8c2dae779750(OCS.15).jpg "Single forest with multiple domains")</span></span>

</div>

<div>

## <a name="single-forest-multiple-trees"></a><span data-ttu-id="aa7c9-133">单林、多个树</span><span class="sxs-lookup"><span data-stu-id="aa7c9-133">Single Forest, Multiple Trees</span></span>

<span data-ttu-id="aa7c9-134">多树林拓扑由两个或多个域组成, 这些域定义独立的树结构和单独的 Active Directory 命名空间。</span><span class="sxs-lookup"><span data-stu-id="aa7c9-134">A multiple-tree forest topology consists of two or more domains that define independent tree structures and separate Active Directory namespaces.</span></span>

<span data-ttu-id="aa7c9-135">下图显示了具有多个树的单个目录林。</span><span class="sxs-lookup"><span data-stu-id="aa7c9-135">The following figure illustrates a single forest with multiple trees.</span></span> <span data-ttu-id="aa7c9-136">在此图中, 用户图标显示用户帐户所在的域、实线指向位于同一域或不同域的 Lync Server 池, 并且虚线指向位于不同树中的 Lync Server 池。</span><span class="sxs-lookup"><span data-stu-id="aa7c9-136">In this figure, a user icon shows the domain where the user account is homed, a solid line points to a Lync Server pool that resides in the same or a different domain, and a dashed line points to Lync Server pool that resides in a different tree.</span></span> <span data-ttu-id="aa7c9-137">用户帐户包括以下内容:</span><span class="sxs-lookup"><span data-stu-id="aa7c9-137">User accounts include the following:</span></span>

  - <span data-ttu-id="aa7c9-138">与 Lync Server 池位于同一域中的用户帐户</span><span class="sxs-lookup"><span data-stu-id="aa7c9-138">User accounts within the same domain as the Lync Server pool</span></span>

  - <span data-ttu-id="aa7c9-139">不同域中的用户帐户 (但同一个树与 Lync 服务器池相同)</span><span class="sxs-lookup"><span data-stu-id="aa7c9-139">User accounts in a different domain from (but the same tree as) the Lync Server pool</span></span>

  - <span data-ttu-id="aa7c9-140">Lync Server 池中的不同树中的用户帐户</span><span class="sxs-lookup"><span data-stu-id="aa7c9-140">User accounts in a different tree from the Lync Server pool</span></span>

<span data-ttu-id="aa7c9-141">**具有多个树的单林**</span><span class="sxs-lookup"><span data-stu-id="aa7c9-141">**Single forest with multiple trees**</span></span>

<span data-ttu-id="aa7c9-142">![具有多个树的单林](images/Gg398173.db30fa49-174a-4974-8695-41dd78e39432(OCS.15).jpg "具有多个树的单林")</span><span class="sxs-lookup"><span data-stu-id="aa7c9-142">![Single forest with multiple trees](images/Gg398173.db30fa49-174a-4974-8695-41dd78e39432(OCS.15).jpg "Single forest with multiple trees")</span></span>

</div>

<div>

## <a name="multiple-forests-central-forest"></a><span data-ttu-id="aa7c9-143">多个林, 中央林</span><span class="sxs-lookup"><span data-stu-id="aa7c9-143">Multiple Forests, Central Forest</span></span>

<span data-ttu-id="aa7c9-144">Lync Server 支持在中央林拓扑中配置的多个林。</span><span class="sxs-lookup"><span data-stu-id="aa7c9-144">Lync Server supports multiple forests that are configured in a central forest topology.</span></span> <span data-ttu-id="aa7c9-145">中央林拓扑使用中央林中的联系人对象来表示其他林中的用户。</span><span class="sxs-lookup"><span data-stu-id="aa7c9-145">Central forest topologies use contact objects in the central forest to represent users in the other forests.</span></span> <span data-ttu-id="aa7c9-146">中央林还为此林中的任何用户托管用户帐户。</span><span class="sxs-lookup"><span data-stu-id="aa7c9-146">The central forest also hosts user accounts for any users in this forest.</span></span> <span data-ttu-id="aa7c9-147">目录同步产品 (如 Microsoft 身份集成服务器 (MIIS)、Microsoft Forefront Identity Manager (FIM) 2010 或 Microsoft Identity 生命周期管理器 (ILM) 2007 功能包 1 (FP1) 在中管理用户帐户的生命周期组织: 当在其中一个目录林中创建新用户帐户或从目录林中删除用户帐户时, 目录同步产品将同步中央林中的相应联系人。</span><span class="sxs-lookup"><span data-stu-id="aa7c9-147">A directory synchronization product, such as Microsoft Identity Integration Server (MIIS), Microsoft Forefront Identity Manager (FIM) 2010, or Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), manages the life cycle of user accounts within the organization: When a new user account is created in one of the forests or a user account is deleted from a forest, the directory synchronization product synchronizes the corresponding contact in the central forest.</span></span>

<span data-ttu-id="aa7c9-148">中央林具有以下优点:</span><span class="sxs-lookup"><span data-stu-id="aa7c9-148">A central forest has the following advantages:</span></span>

  - <span data-ttu-id="aa7c9-149">运行 Lync Server 的服务器集中在单个林中。</span><span class="sxs-lookup"><span data-stu-id="aa7c9-149">Servers running Lync Server are centralized within a single forest.</span></span>

  - <span data-ttu-id="aa7c9-150">用户可以搜索任何林中的其他用户并与之通信。</span><span class="sxs-lookup"><span data-stu-id="aa7c9-150">Users can search for and communicate with other users in any forest.</span></span>

  - <span data-ttu-id="aa7c9-151">用户可以查看任何林中的其他用户的状态。</span><span class="sxs-lookup"><span data-stu-id="aa7c9-151">Users can view presence of other users in any forest.</span></span>

  - <span data-ttu-id="aa7c9-152">目录同步产品可在创建或删除用户帐户时自动添加和删除中央林中的联系人对象。</span><span class="sxs-lookup"><span data-stu-id="aa7c9-152">The directory synchronization product automates the addition and deletion of contact objects in the central forest as user accounts are created or removed.</span></span>

<span data-ttu-id="aa7c9-153">下图显示了中央林拓扑。</span><span class="sxs-lookup"><span data-stu-id="aa7c9-153">The following figure illustrates a central forest topology.</span></span> <span data-ttu-id="aa7c9-154">在此图中, 托管 Lync Server 的域之间有双向信任关系 (位于中央林) 和每个仅用户域 (位于单独的林中) 之间。</span><span class="sxs-lookup"><span data-stu-id="aa7c9-154">In this figure, there are two-way trust relationships between the domain that hosts Lync Server, which is in the central forest, and each user-only domain, which is in a separate forest.</span></span> <span data-ttu-id="aa7c9-155">单独用户目录林中的架构无需扩展。</span><span class="sxs-lookup"><span data-stu-id="aa7c9-155">The schema in the separate user forests does not need to be extended.</span></span>

<span data-ttu-id="aa7c9-156">**中央林拓扑**</span><span class="sxs-lookup"><span data-stu-id="aa7c9-156">**Central forest topology**</span></span>

<span data-ttu-id="aa7c9-157">![中央林拓扑](images/Gg398173.7feb049a-453b-4134-9128-873b83ee1755(OCS.15).jpg "中央林拓扑")</span><span class="sxs-lookup"><span data-stu-id="aa7c9-157">![Central forest topology](images/Gg398173.7feb049a-453b-4134-9128-873b83ee1755(OCS.15).jpg "Central forest topology")</span></span>

</div>

<div>

## <a name="multiple-forests-resource-forest"></a><span data-ttu-id="aa7c9-158">多个林, 资源林</span><span class="sxs-lookup"><span data-stu-id="aa7c9-158">Multiple Forests, Resource Forest</span></span>

<span data-ttu-id="aa7c9-159">在资源林拓扑中, 一个林专用于运行服务器应用程序, 例如 Microsoft Exchange Server 和 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="aa7c9-159">In a resource forest topology, one forest is dedicated to running server applications, such as Microsoft Exchange Server and Lync Server.</span></span> <span data-ttu-id="aa7c9-160">资源林托管服务器应用程序和活动用户对象的同步表示形式, 但不包含启用登录的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="aa7c9-160">The resource forest hosts the server applications and a synchronized representation of the active user object, but it does not contain logon-enabled user accounts.</span></span> <span data-ttu-id="aa7c9-161">资源林充当用户对象所在的其他林的共享服务环境。</span><span class="sxs-lookup"><span data-stu-id="aa7c9-161">The resource forest acts as a shared services environment for the other forests where user objects reside.</span></span> <span data-ttu-id="aa7c9-162">用户林与资源林具有林级别的信任关系。</span><span class="sxs-lookup"><span data-stu-id="aa7c9-162">The user forests have a forest-level trust relationship with the resource forest.</span></span> <span data-ttu-id="aa7c9-163">在此类型的拓扑中部署 Lync Server 时, 在资源目录林中为用户目录林中的每个用户帐户创建一个已禁用的用户对象。</span><span class="sxs-lookup"><span data-stu-id="aa7c9-163">When you deploy Lync Server in this type of topology, you create one disabled user object in the resource forest for every user account in the user forests.</span></span> <span data-ttu-id="aa7c9-164">如果 Microsoft Exchange 已部署在资源目录林中, 则已禁用的用户帐户可能已存在。</span><span class="sxs-lookup"><span data-stu-id="aa7c9-164">If Microsoft Exchange is already deployed in the resource forest, the disabled user accounts might already exist.</span></span> <span data-ttu-id="aa7c9-165">目录同步产品 (如 MIIS、Microsoft Forefront Identity Manager (FIM) 2010 或 Microsoft Identity 生命周期管理器 (ILM) 2007 功能包 1 (FP1)) 管理用户帐户的生命周期。</span><span class="sxs-lookup"><span data-stu-id="aa7c9-165">A directory synchronization product, such as MIIS, Microsoft Forefront Identity Manager (FIM) 2010, or Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), manages the life cycle of user accounts.</span></span> <span data-ttu-id="aa7c9-166">当在其中一个用户林中创建新的用户帐户, 或者从目录林中删除用户帐户时, 目录同步产品将同步资源林中对应的用户表示形式。</span><span class="sxs-lookup"><span data-stu-id="aa7c9-166">When a new user account is created in one of the user forests or a user account is deleted from a forest, the directory synchronization product synchronizes the corresponding user representation in the resource forest.</span></span>

<span data-ttu-id="aa7c9-167">此拓扑可用于为组织中管理多个林的服务提供共享基础结构, 或将 Active Directory 对象的管理与其他管理分开。</span><span class="sxs-lookup"><span data-stu-id="aa7c9-167">This topology can be used to provide a shared infrastructure for services in organizations that manage multiple forests or to separate the administration of Active Directory objects from other administration.</span></span> <span data-ttu-id="aa7c9-168">出于安全原因需要隔离 Active Directory 管理的公司通常会选择此拓扑。</span><span class="sxs-lookup"><span data-stu-id="aa7c9-168">Companies that need to isolate Active Directory administration for security reasons often choose this topology.</span></span>

<span data-ttu-id="aa7c9-169">此拓扑提供了限制将 Active Directory 架构扩展到单个林 (即资源林) 的需要的好处。</span><span class="sxs-lookup"><span data-stu-id="aa7c9-169">This topology provides the benefit of limiting the need to extend the Active Directory schema to a single forest (that is, the resource forest).</span></span>

<span data-ttu-id="aa7c9-170">下图显示了一个资源林拓扑。</span><span class="sxs-lookup"><span data-stu-id="aa7c9-170">The following diagram illustrates a resource forest topology.</span></span>

<span data-ttu-id="aa7c9-171">**资源林拓扑**</span><span class="sxs-lookup"><span data-stu-id="aa7c9-171">**Resource forest topology**</span></span>

<span data-ttu-id="aa7c9-172">![Active Directory 资源林拓扑](images/Gg398173.54ab82f1-e9e5-40f0-a54e-86e340b65c2a(OCS.15).jpg "Active Directory 资源林拓扑")</span><span class="sxs-lookup"><span data-stu-id="aa7c9-172">![Active Directory Resource Forest Topology](images/Gg398173.54ab82f1-e9e5-40f0-a54e-86e340b65c2a(OCS.15).jpg "Active Directory Resource Forest Topology")</span></span>

</div>

<div>

## <a name="multiple-forests-in-a-lync-resource-forest-topology-with-exchange-online"></a><span data-ttu-id="aa7c9-173">使用 Exchange Online 的 Lync 资源林拓扑中的多个林</span><span class="sxs-lookup"><span data-stu-id="aa7c9-173">Multiple forests in a Lync resource forest topology with Exchange Online</span></span>

<span data-ttu-id="aa7c9-174">在此拓扑中, 一个或多个林位于本地, 并且专用于托管 Active Directory 用户帐户。</span><span class="sxs-lookup"><span data-stu-id="aa7c9-174">In this topology, one or more forests are located on-premises and are dedicated to hosting Active Directory user accounts.</span></span> <span data-ttu-id="aa7c9-175">资源林位于本地, 由第三方托管提供商维护。</span><span class="sxs-lookup"><span data-stu-id="aa7c9-175">The resource forest is located off-premises and is maintained by a third-party hosting provider.</span></span> <span data-ttu-id="aa7c9-176">资源林仅包含本地用户帐户林中的 Lync Server 部署和用户帐户的同步复制。</span><span class="sxs-lookup"><span data-stu-id="aa7c9-176">The resource forest contains only the Lync Server deployment and a synchronized replication of the user accounts from the on-premises user accounts forest(s).</span></span> <span data-ttu-id="aa7c9-177">它不包含启用登录的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="aa7c9-177">It does not contain logon-enabled user accounts.</span></span> <span data-ttu-id="aa7c9-178">Exchange 是在集成的本地用户帐户目录林中 (与 Exchange Online (混合) 一起部署的) 中部署的, 或者本地用户帐户的电子邮件服务专门由 Exchange Online 提供。</span><span class="sxs-lookup"><span data-stu-id="aa7c9-178">Exchange is deployed either in the on-premises user account forest(s) integrated along with Exchange Online (Hybrid), or email services for the on-premises user accounts are provided exclusively by Exchange Online.</span></span>

<span data-ttu-id="aa7c9-179">资源林充当用户对象所在的本地 Active Directory 林的共享服务环境。</span><span class="sxs-lookup"><span data-stu-id="aa7c9-179">The resource forest acts as a shared services environment for the on-premises Active Directory forest(s) where user objects reside.</span></span> <span data-ttu-id="aa7c9-180">用户帐户林与资源林有一种方式的林级信任关系。</span><span class="sxs-lookup"><span data-stu-id="aa7c9-180">The user account forest(s) have a one way forest-level trust relationship with the resource forest.</span></span> <span data-ttu-id="aa7c9-181">在此类型的拓扑中部署 Lync Server 时, 在资源目录林中为用户目录林中的每个用户帐户创建一个已禁用的用户对象。</span><span class="sxs-lookup"><span data-stu-id="aa7c9-181">When you deploy Lync Server in this type of topology, you create one disabled user object in the resource forest for every user account in the user forests.</span></span> <span data-ttu-id="aa7c9-182">目录同步产品 (如 MIIS、Microsoft Forefront Identity Manager (FIM) 2010 或 Microsoft Identity 生命周期管理器 (ILM) 2007 功能包 1 (FP1)) 管理用户帐户的生命周期。</span><span class="sxs-lookup"><span data-stu-id="aa7c9-182">A directory synchronization product, such as MIIS, Microsoft Forefront Identity Manager (FIM) 2010, or Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), manages the life cycle of user accounts.</span></span> <span data-ttu-id="aa7c9-183">当在其中一个用户林中创建新的用户帐户, 或者从目录林中删除用户帐户时, 目录同步产品将同步资源林中对应的用户表示形式。</span><span class="sxs-lookup"><span data-stu-id="aa7c9-183">When a new user account is created in one of the user forests or a user account is deleted from a forest, the directory synchronization product synchronizes the corresponding user representation in the resource forest.</span></span> <span data-ttu-id="aa7c9-184">有关配置多目录林部署的详细信息, 请参阅[在多林结构 (具有 Exchange 混合的合作伙伴托管 lync) 中部署 Lync](http://go.microsoft.com/fwlink/p/?linkid=513216)。</span><span class="sxs-lookup"><span data-stu-id="aa7c9-184">For more information about configuring a multi-forest deployment, see [Deploying Lync in a Multi-Forest Architecture (Partner Hosted Lync with Exchange Hybrid)](http://go.microsoft.com/fwlink/p/?linkid=513216).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

