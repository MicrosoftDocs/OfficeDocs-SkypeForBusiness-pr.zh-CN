---
title: 'Lync Server 2013: 为 Lync Online 客户配置联合身份验证支持'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring federation support for a Lync Online customer
ms:assetid: e5f7f38d-ede5-4af3-88c2-026e8a78df12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202193(v=OCS.15)
ms:contentKeyID: 48185669
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f5e3b1e7a325a078d4769116697f957815f02487
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837252"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-federation-support-for-a-lync-online-customer-in-lync-server-2013"></a><span data-ttu-id="40688-102">在 Lync Server 2013 中为 Lync Online 客户配置联合身份验证支持</span><span class="sxs-lookup"><span data-stu-id="40688-102">Configuring federation support for a Lync Online customer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="40688-103">_**主题上次修改时间:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="40688-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="40688-104">你可以通过以下任一方式向组织中的用户提供通信服务:</span><span class="sxs-lookup"><span data-stu-id="40688-104">You can provide communications services to users in your organization in any of the following ways:</span></span>

  - <span data-ttu-id="40688-105">在你的组织 (称为*本地服务*) 中部署 lync Server 2013 并在你的组织中设置 lync 2013 用户帐户。</span><span class="sxs-lookup"><span data-stu-id="40688-105">Deploying Lync Server 2013 in your organization (known as *on-premises services*) and setting up Lync 2013 user accounts in your organization.</span></span>

  - <span data-ttu-id="40688-106">使用托管提供商设置 Microsoft Lync Online 2010 客户帐户, 并使用托管提供商 (称为*联机服务*) 设置用户帐户。</span><span class="sxs-lookup"><span data-stu-id="40688-106">Setting up a Microsoft Lync Online 2010 customer account with a Hosting Provider and setting up user accounts with the Hosting Provider (known as *online services*).</span></span>

<span data-ttu-id="40688-107">如果您在组织中部署 Lync 2013, 则可以与一个或多个 Microsoft Lync Online 2010 客户的域联盟。</span><span class="sxs-lookup"><span data-stu-id="40688-107">If you deploy Lync 2013 in your organization, you can federate with the domains of one or more Microsoft Lync Online 2010 customers.</span></span> <span data-ttu-id="40688-108">若要在本地 Lync 2013 部署的用户与 Lync Online 2010 客户的用户之间启用联盟, 必须为 Lync Online 客户的域和用户配置支持。</span><span class="sxs-lookup"><span data-stu-id="40688-108">To enable federation between users of your on-premises Lync 2013 deployment and users of a Lync Online 2010 customer, you must configure support for the domain and users of the Lync Online customer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="40688-109">本文档仅介绍配置组织以支持与 Lync Online 2010 客户联合的过程。</span><span class="sxs-lookup"><span data-stu-id="40688-109">This documentation describes only the procedures for configuring your organization to support federation with an Lync Online 2010 customer.</span></span> <span data-ttu-id="40688-110">本文档不介绍将 Lync Online 2010 客户配置为支持联盟的过程。</span><span class="sxs-lookup"><span data-stu-id="40688-110">This documentation does not describe the procedures for configuring the Lync Online 2010 customer to support federation.</span></span> <span data-ttu-id="40688-111">有关 Lync Online 服务的详细信息, 请参阅 Lync <A href="http://go.microsoft.com/fwlink/p/?linkid=218941">http://go.microsoft.com/fwlink/p/?linkId=218941</A>online。</span><span class="sxs-lookup"><span data-stu-id="40688-111">For details about Lync Online services, see Lync Online at <A href="http://go.microsoft.com/fwlink/p/?linkid=218941">http://go.microsoft.com/fwlink/p/?linkId=218941</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="40688-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="40688-112">In This Section</span></span>

  - [<span data-ttu-id="40688-113">在 Lync Server 2013 中与 Lync Online 客户进行联盟的先决条件</span><span class="sxs-lookup"><span data-stu-id="40688-113">Prerequisites for federating with a Lync Online customer in Lync Server 2013</span></span>](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md)

  - [<span data-ttu-id="40688-114">在 Lync Server 2013 中配置 Lync Online 域的联合身份验证支持</span><span class="sxs-lookup"><span data-stu-id="40688-114">Configure federation support for a Lync Online domain in Lync Server 2013</span></span>](lync-server-2013-configure-federation-support-for-a-lync-online-domain.md)

  - [<span data-ttu-id="40688-115">在 Lync Server 2013 中配置与 Lync Online 客户的联盟的用户访问权限</span><span class="sxs-lookup"><span data-stu-id="40688-115">Configure user access for federation with a Lync Online customer in Lync Server 2013</span></span>](lync-server-2013-configure-user-access-for-federation-with-a-lync-online-customer.md)

  - [<span data-ttu-id="40688-116">在 Lync Server 2013 中验证与 Lync Online 客户的通信</span><span class="sxs-lookup"><span data-stu-id="40688-116">Verify communications with a Lync Online customer in Lync Server 2013</span></span>](lync-server-2013-verify-communications-with-a-lync-online-customer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

