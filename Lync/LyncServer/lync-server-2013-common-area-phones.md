---
title: 'Lync Server 2013: 常见的区域电话'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Common area phones
ms:assetid: d63bb3de-154e-4347-9251-9fa94e7d593a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994076(v=OCS.15)
ms:contentKeyID: 51803987
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 179d6a0102e62a081846a14981ed70294432ed44
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837535"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="common-area-phones-in-lync-server-2013"></a><span data-ttu-id="e0603-102">Lync Server 2013 中的常见区域电话</span><span class="sxs-lookup"><span data-stu-id="e0603-102">Common area phones in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e0603-103">_**主题上次修改时间:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="e0603-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="e0603-104">常见的区域电话是不与单个用户关联的 IP 电话。</span><span class="sxs-lookup"><span data-stu-id="e0603-104">Common area phones are IP phones that are not associated with an individual user.</span></span> <span data-ttu-id="e0603-105">通常, 常用的区域电话通常位于建筑物大厅、cafeterias、员工 lounges、会议室和其他大量人员可能收集的地方, 而不是位于其他人的 office 中。</span><span class="sxs-lookup"><span data-stu-id="e0603-105">Instead of being located in someone’s office, common area phones are typically located in building lobbies, cafeterias, employee lounges, meeting rooms, and other locations where a large number of people are likely to gather.</span></span> <span data-ttu-id="e0603-106">与 Lync Server 中的其他电话不同, 通常使用分配给单个用户的语音策略和拨号计划来维护这些电话, 常用的区域电话没有分配给他们的单个用户。</span><span class="sxs-lookup"><span data-stu-id="e0603-106">Unlike other phones in Lync Server, which are typically maintained by using voice policies and dial plans that are assigned to individual users, common area phones do not have individual users assigned to them.</span></span> <span data-ttu-id="e0603-107">这意味着它们的管理方式必须不同于您的其他电话。</span><span class="sxs-lookup"><span data-stu-id="e0603-107">This means that they must be managed differently than your other phones.</span></span>

<span data-ttu-id="e0603-108">若要管理常用的区域电话, 请为您的所有公共区域电话创建 Active Directory 域服务联系人对象 (如用户帐户), 这些对象可以分配有策略和语音计划。</span><span class="sxs-lookup"><span data-stu-id="e0603-108">To manage common area phones, you create Active Directory Domain Services contact objects for all your common area phones that, like user accounts, can be assigned policies and voice plans.</span></span> <span data-ttu-id="e0603-109">通过此方法, 您可以保持对常用区域电话的控制, 即使这些电话不与单个用户关联。</span><span class="sxs-lookup"><span data-stu-id="e0603-109">This approach enables you to maintain control over common area phones, even though those phones are not associated with an individual user.</span></span>

<span data-ttu-id="e0603-110">使用本部分中的主题, 了解如何为常见的区域电话创建联系人对象、修改和删除它们以及配置和查看有关部署中的公共区域电话的配置信息。</span><span class="sxs-lookup"><span data-stu-id="e0603-110">Use the topics in this section to learn how to create contact objects for common area phones, modify and delete them, and configure and view configuration information about the common area phones in your deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e0603-111">您有三个适用于常见区域电话的选项: Aastra 6721ip 通用区域电话、HP 4110 IP 电话和 Polycom CX500 IP 公共区域电话。</span><span class="sxs-lookup"><span data-stu-id="e0603-111">You have three options for common area phones: the Aastra 6721ip common area phone, the HP 4110 IP Phone, and the Polycom CX500 IP common area phone.</span></span> <span data-ttu-id="e0603-112">Polycom CX3000 IP 会议电话是另一个变种通用的区域电话。</span><span class="sxs-lookup"><span data-stu-id="e0603-112">The Polycom CX3000 IP conferencing phone is another variant common area phone.</span></span> <span data-ttu-id="e0603-113">但是, 它旨在在会议室中使用。</span><span class="sxs-lookup"><span data-stu-id="e0603-113">However, it is intended for use in conference rooms.</span></span> <span data-ttu-id="e0603-114">有关常见的区域电话的详细信息, 请参阅<A href="http://technet.microsoft.com/en-us/library/gg398958(v=ocs.14).aspx">选择新设备</A>的通用区域电话部分。</span><span class="sxs-lookup"><span data-stu-id="e0603-114">For details about common area phones, see the Common Area Phones section of <A href="http://technet.microsoft.com/en-us/library/gg398958(v=ocs.14).aspx">Choosing New Devices</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e0603-115">本节内容</span><span class="sxs-lookup"><span data-stu-id="e0603-115">In This Section</span></span>

  - [<span data-ttu-id="e0603-116">在 Lync Server 2013 中查看常见的区域电话信息</span><span class="sxs-lookup"><span data-stu-id="e0603-116">View common area phone information in Lync Server 2013</span></span>](lync-server-2013-view-common-area-phone-information.md)

  - [<span data-ttu-id="e0603-117">在 Lync Server 2013 中创建或修改公用的 "区域电话联系人" 对象</span><span class="sxs-lookup"><span data-stu-id="e0603-117">Create or modify a common area phone Contact object in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-common-area-phone-contact-object.md)

  - [<span data-ttu-id="e0603-118">在 Lync Server 2013 中启用或禁用热 desking</span><span class="sxs-lookup"><span data-stu-id="e0603-118">Enable or disable hot desking in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-hot-desking.md)

  - [<span data-ttu-id="e0603-119">在 Lync Server 2013 中删除公用的 "区域电话联系人" 对象</span><span class="sxs-lookup"><span data-stu-id="e0603-119">Delete a common area phone Contact object in Lync Server 2013</span></span>](lync-server-2013-delete-a-common-area-phone-contact-object.md)

  - [<span data-ttu-id="e0603-120">在 Lync Server 2013 中将策略分配到常见的区域电话</span><span class="sxs-lookup"><span data-stu-id="e0603-120">Assign policies in Lync Server 2013 to a common area phone</span></span>](lync-server-2013-assign-policies-to-a-common-area-phone.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

