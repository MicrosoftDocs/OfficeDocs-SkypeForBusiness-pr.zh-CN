---
title: Lync Server 2013：通用区域电话
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Common area phones
ms:assetid: d63bb3de-154e-4347-9251-9fa94e7d593a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994076(v=OCS.15)
ms:contentKeyID: 51803987
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 736aa12c9de027aa485cfc89a6f5cd820a460833
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045814"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="common-area-phones-in-lync-server-2013"></a><span data-ttu-id="ba607-102">Lync Server 2013 中的常见区域电话</span><span class="sxs-lookup"><span data-stu-id="ba607-102">Common area phones in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ba607-103">_**上次修改的主题：** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="ba607-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="ba607-104">公用区域电话是不与单个用户相关联的 IP 电话。</span><span class="sxs-lookup"><span data-stu-id="ba607-104">Common area phones are IP phones that are not associated with an individual user.</span></span> <span data-ttu-id="ba607-105">公共区域电话通常位于建筑物会议厅、cafeterias、员工 lounges、会议室和其他许多人可能收集的地方，而不是位于某人的办公室中。</span><span class="sxs-lookup"><span data-stu-id="ba607-105">Instead of being located in someone’s office, common area phones are typically located in building lobbies, cafeterias, employee lounges, meeting rooms, and other locations where a large number of people are likely to gather.</span></span> <span data-ttu-id="ba607-106">与 Lync Server 中的其他电话（通常是通过使用语音策略和分配给单个用户的拨号计划进行维护）不同，公用区域电话不会向其分配单个用户。</span><span class="sxs-lookup"><span data-stu-id="ba607-106">Unlike other phones in Lync Server, which are typically maintained by using voice policies and dial plans that are assigned to individual users, common area phones do not have individual users assigned to them.</span></span> <span data-ttu-id="ba607-107">这意味着它们的管理方式必须不同于其他电话。</span><span class="sxs-lookup"><span data-stu-id="ba607-107">This means that they must be managed differently than your other phones.</span></span>

<span data-ttu-id="ba607-108">若要管理公用区域电话，可以为您的所有公用区域电话创建 Active Directory 域服务联系人对象（如用户帐户），可以为其分配策略和语音计划。</span><span class="sxs-lookup"><span data-stu-id="ba607-108">To manage common area phones, you create Active Directory Domain Services contact objects for all your common area phones that, like user accounts, can be assigned policies and voice plans.</span></span> <span data-ttu-id="ba607-109">此方法使您能够保持对公用区域电话的控制，即使这些电话并不与单个用户相关联。</span><span class="sxs-lookup"><span data-stu-id="ba607-109">This approach enables you to maintain control over common area phones, even though those phones are not associated with an individual user.</span></span>

<span data-ttu-id="ba607-110">使用本节中的主题可了解如何为公用区域电话创建联系人对象、修改和删除它们，以及配置和查看有关部署中的公共区域电话的配置信息。</span><span class="sxs-lookup"><span data-stu-id="ba607-110">Use the topics in this section to learn how to create contact objects for common area phones, modify and delete them, and configure and view configuration information about the common area phones in your deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ba607-111">共有三个选项用于常见区域电话： Aastra 6721ip 公共区域电话、HP 4110 IP 电话和 Polycom CX500 IP 公共区域电话。</span><span class="sxs-lookup"><span data-stu-id="ba607-111">You have three options for common area phones: the Aastra 6721ip common area phone, the HP 4110 IP Phone, and the Polycom CX500 IP common area phone.</span></span> <span data-ttu-id="ba607-112">Polycom CX3000 IP 会议电话是另一个变种公用区域电话。</span><span class="sxs-lookup"><span data-stu-id="ba607-112">The Polycom CX3000 IP conferencing phone is another variant common area phone.</span></span> <span data-ttu-id="ba607-113">但是，它适用于会议室。</span><span class="sxs-lookup"><span data-stu-id="ba607-113">However, it is intended for use in conference rooms.</span></span> <span data-ttu-id="ba607-114">有关常见区域电话的详细信息，请参阅<A href="http://technet.microsoft.com/library/gg398958(v=ocs.14).aspx">选择新设备</A>的公共区域电话部分。</span><span class="sxs-lookup"><span data-stu-id="ba607-114">For details about common area phones, see the Common Area Phones section of <A href="http://technet.microsoft.com/library/gg398958(v=ocs.14).aspx">Choosing New Devices</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ba607-115">本部分内容</span><span class="sxs-lookup"><span data-stu-id="ba607-115">In This Section</span></span>

  - [<span data-ttu-id="ba607-116">在 Lync Server 2013 中查看常见区域电话信息</span><span class="sxs-lookup"><span data-stu-id="ba607-116">View common area phone information in Lync Server 2013</span></span>](lync-server-2013-view-common-area-phone-information.md)

  - [<span data-ttu-id="ba607-117">在 Lync Server 2013 中创建或修改公用区域电话联系人对象</span><span class="sxs-lookup"><span data-stu-id="ba607-117">Create or modify a common area phone Contact object in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-common-area-phone-contact-object.md)

  - [<span data-ttu-id="ba607-118">在 Lync Server 2013 中启用或禁用热 desking</span><span class="sxs-lookup"><span data-stu-id="ba607-118">Enable or disable hot desking in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-hot-desking.md)

  - [<span data-ttu-id="ba607-119">在 Lync Server 2013 中删除公用区域电话联系人对象</span><span class="sxs-lookup"><span data-stu-id="ba607-119">Delete a common area phone Contact object in Lync Server 2013</span></span>](lync-server-2013-delete-a-common-area-phone-contact-object.md)

  - [<span data-ttu-id="ba607-120">在 Lync Server 2013 中将策略分配给公用区域电话</span><span class="sxs-lookup"><span data-stu-id="ba607-120">Assign policies in Lync Server 2013 to a common area phone</span></span>](lync-server-2013-assign-policies-to-a-common-area-phone.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

