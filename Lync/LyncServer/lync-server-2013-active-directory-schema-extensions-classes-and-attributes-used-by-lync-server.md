---
title: Lync Server 2013： Lync Server 使用的 Active Directory 架构扩展、类和属性
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory schema extensions, classes, and attributes used by Lync Server 2013
ms:assetid: 579bfa5a-9443-46dd-9a8e-07d00ba2824d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398379(v=OCS.15)
ms:contentKeyID: 48184188
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e393c5c65e77f22763380563e61c30bcdb69b23a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145050"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="active-directory-schema-extensions-classes-and-attributes-used-by-lync-server-2013"></a><span data-ttu-id="d5472-102">Lync Server 2013 使用的 Active Directory 架构扩展、类和属性</span><span class="sxs-lookup"><span data-stu-id="d5472-102">Active Directory schema extensions, classes, and attributes used by Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5472-103">_**上次修改的主题：** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="d5472-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="d5472-104">本参考部分包括以下信息：</span><span class="sxs-lookup"><span data-stu-id="d5472-104">This reference section includes the following information:</span></span>

  - <span data-ttu-id="d5472-105">Lync Server 2013 的新的或更改的 Active Directory 架构扩展</span><span class="sxs-lookup"><span data-stu-id="d5472-105">Active Directory schema extensions that are new or changed for Lync Server 2013</span></span>
    
    <span data-ttu-id="d5472-106">Active Directory 架构包含可在 Active Directory 林中创建的每个对象类的正式定义。</span><span class="sxs-lookup"><span data-stu-id="d5472-106">The Active Directory schema contains formal definitions of every object class that can be created in an Active Directory forest.</span></span> <span data-ttu-id="d5472-107">该架构还包含可存在于 Active Directory 对象上的每个属性的正式定义。</span><span class="sxs-lookup"><span data-stu-id="d5472-107">The schema also contains formal definitions of every attribute that can exist on an Active Directory object.</span></span> <span data-ttu-id="d5472-108">Active Directory 全局编录包含林中所有对象的副本，以及每个对象的属性子集。</span><span class="sxs-lookup"><span data-stu-id="d5472-108">The Active Directory global catalog contains replicas of all the objects for the forest, along with a subset of the attributes for each object.</span></span> <span data-ttu-id="d5472-109">本节介绍了在 Lync Server 2013 中新增或更改的类和属性。</span><span class="sxs-lookup"><span data-stu-id="d5472-109">This section describes the classes and attributes that are new or changed in Lync Server 2013.</span></span>

  - <span data-ttu-id="d5472-110">Lync Server 使用的所有类，以及每个类的说明</span><span class="sxs-lookup"><span data-stu-id="d5472-110">All the classes used by Lync Server, with a description of each</span></span>

  - <span data-ttu-id="d5472-111">Lync Server 使用的所有属性，以及每个属性的说明</span><span class="sxs-lookup"><span data-stu-id="d5472-111">All the attributes used by Lync Server, with a description of each</span></span>

  - <span data-ttu-id="d5472-112">Lync Server 使用的类的列表，每个类的属性可能包含</span><span class="sxs-lookup"><span data-stu-id="d5472-112">A list of the classes used by Lync Server, with the attributes each may contain</span></span>

  - <span data-ttu-id="d5472-113">全局设置和对象，以及在林准备过程中创建的通用服务组和管理组</span><span class="sxs-lookup"><span data-stu-id="d5472-113">Global settings and objects, in addition to the universal service and administration groups that are created during forest preparation</span></span>

  - <span data-ttu-id="d5472-114">域准备过程中在域根和内置容器中创建的访问控制项 (ACE)</span><span class="sxs-lookup"><span data-stu-id="d5472-114">Access control entries (ACEs) that are created on the domain root and built-in containers during domain preparation</span></span>

  - <span data-ttu-id="d5472-115">通过 Grant\_CsSetupPermission Cmdlet 在 Active Directory 组织单位（OU）上进行的更改。</span><span class="sxs-lookup"><span data-stu-id="d5472-115">Changes that are made on an Active Directory organizational unit (OU) by the Grant\_CsSetupPermission cmdlet.</span></span>

  - <span data-ttu-id="d5472-116">通过 Grant\_CsOUPermission Cmdlet 在 ACTIVE Directory OU 中进行的更改。</span><span class="sxs-lookup"><span data-stu-id="d5472-116">Changes that are made on an Active Directory OU by the Grant\_CsOUPermission cmdlet.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d5472-117">本部分内容</span><span class="sxs-lookup"><span data-stu-id="d5472-117">In This Section</span></span>

  - [<span data-ttu-id="d5472-118">Lync Server 2013 中的架构更改</span><span class="sxs-lookup"><span data-stu-id="d5472-118">Schema changes in Lync Server 2013</span></span>](lync-server-2013-schema-changes-in-lync-server-2013.md)

  - [<span data-ttu-id="d5472-119">Lync Server 2013 中的架构类和说明</span><span class="sxs-lookup"><span data-stu-id="d5472-119">Schema classes and descriptions in Lync Server 2013</span></span>](lync-server-2013-schema-classes-and-descriptions.md)

  - [<span data-ttu-id="d5472-120">Lync Server 2013 中的架构属性和说明</span><span class="sxs-lookup"><span data-stu-id="d5472-120">Schema attributes and descriptions in Lync Server 2013</span></span>](lync-server-2013-schema-attributes-and-descriptions.md)

  - [<span data-ttu-id="d5472-121">Lync Server 2013 中按类分类的架构属性</span><span class="sxs-lookup"><span data-stu-id="d5472-121">Schema attributes by class in Lync Server 2013</span></span>](lync-server-2013-schema-attributes-by-class.md)

  - [<span data-ttu-id="d5472-122">Lync Server 2013 中的林准备所做的更改</span><span class="sxs-lookup"><span data-stu-id="d5472-122">Changes made by forest preparation in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-forest-preparation.md)

  - [<span data-ttu-id="d5472-123">Lync Server 2013 中的域准备所做的更改</span><span class="sxs-lookup"><span data-stu-id="d5472-123">Changes made by domain preparation in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-domain-preparation.md)

  - [<span data-ttu-id="d5472-124">Lync Server 2013 中的 CsSetupPermission 所做的更改</span><span class="sxs-lookup"><span data-stu-id="d5472-124">Changes made by Grant-CsSetupPermission in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission)

  - [<span data-ttu-id="d5472-125">Lync Server 2013 中的 CsOUPermission 所做的更改</span><span class="sxs-lookup"><span data-stu-id="d5472-125">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission)

</div>

</div>

<span> </span>

</div>

</div>

</div>

