---
title: Lync Server 2013：Lync Server 使用的 Active Directory 架构扩展、类和属性
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
ms.openlocfilehash: 2ec6b3eff05ba27b41488aea49bb0347d058b6f0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735192"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-schema-extensions-classes-and-attributes-used-by-lync-server-2013"></a><span data-ttu-id="a738b-102">Lync Server 2013 使用的 Active Directory 架构扩展、类和属性</span><span class="sxs-lookup"><span data-stu-id="a738b-102">Active Directory schema extensions, classes, and attributes used by Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a738b-103">_**主题上次修改时间：** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="a738b-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="a738b-104">本参考部分包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="a738b-104">This reference section includes the following information:</span></span>

  - <span data-ttu-id="a738b-105">Lync Server 2013 的新的或已更改的 Active Directory 架构扩展</span><span class="sxs-lookup"><span data-stu-id="a738b-105">Active Directory schema extensions that are new or changed for Lync Server 2013</span></span>
    
    <span data-ttu-id="a738b-106">Active Directory 架构包含可在 Active Directory 林中创建的每个对象类的正式定义。</span><span class="sxs-lookup"><span data-stu-id="a738b-106">The Active Directory schema contains formal definitions of every object class that can be created in an Active Directory forest.</span></span> <span data-ttu-id="a738b-107">该架构还包含可存在于 Active Directory 对象上的每个属性的正式定义。</span><span class="sxs-lookup"><span data-stu-id="a738b-107">The schema also contains formal definitions of every attribute that can exist on an Active Directory object.</span></span> <span data-ttu-id="a738b-108">Active Directory 全局编录包含林的所有对象的副本，以及每个对象的属性子集。</span><span class="sxs-lookup"><span data-stu-id="a738b-108">The Active Directory global catalog contains replicas of all the objects for the forest, along with a subset of the attributes for each object.</span></span> <span data-ttu-id="a738b-109">本部分介绍 Lync Server 2013 中新增或更改的类和属性。</span><span class="sxs-lookup"><span data-stu-id="a738b-109">This section describes the classes and attributes that are new or changed in Lync Server 2013.</span></span>

  - <span data-ttu-id="a738b-110">Lync Server 使用的所有类，以及每个类的说明</span><span class="sxs-lookup"><span data-stu-id="a738b-110">All the classes used by Lync Server, with a description of each</span></span>

  - <span data-ttu-id="a738b-111">Lync Server 使用的所有属性，以及每个属性的说明</span><span class="sxs-lookup"><span data-stu-id="a738b-111">All the attributes used by Lync Server, with a description of each</span></span>

  - <span data-ttu-id="a738b-112">Lync Server 使用的类列表，每个类都可能包含的属性</span><span class="sxs-lookup"><span data-stu-id="a738b-112">A list of the classes used by Lync Server, with the attributes each may contain</span></span>

  - <span data-ttu-id="a738b-113">全局设置和对象，以及林准备期间创建的通用服务和管理组</span><span class="sxs-lookup"><span data-stu-id="a738b-113">Global settings and objects, in addition to the universal service and administration groups that are created during forest preparation</span></span>

  - <span data-ttu-id="a738b-114">在域准备期间在域根和内置容器上创建的访问控制条目（Ace）</span><span class="sxs-lookup"><span data-stu-id="a738b-114">Access control entries (ACEs) that are created on the domain root and built-in containers during domain preparation</span></span>

  - <span data-ttu-id="a738b-115">通过授予\_CsSetupPermission Cmdlet 对 Active Directory 组织单位（OU）所做的更改。</span><span class="sxs-lookup"><span data-stu-id="a738b-115">Changes that are made on an Active Directory organizational unit (OU) by the Grant\_CsSetupPermission cmdlet.</span></span>

  - <span data-ttu-id="a738b-116">通过授予\_CsOUPermission Cmdlet 在 ACTIVE Directory OU 上进行的更改。</span><span class="sxs-lookup"><span data-stu-id="a738b-116">Changes that are made on an Active Directory OU by the Grant\_CsOUPermission cmdlet.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a738b-117">本节内容</span><span class="sxs-lookup"><span data-stu-id="a738b-117">In This Section</span></span>

  - [<span data-ttu-id="a738b-118">Lync Server 2013 中的架构更改</span><span class="sxs-lookup"><span data-stu-id="a738b-118">Schema changes in Lync Server 2013</span></span>](lync-server-2013-schema-changes-in-lync-server-2013.md)

  - [<span data-ttu-id="a738b-119">Lync Server 2013 中的架构类和说明</span><span class="sxs-lookup"><span data-stu-id="a738b-119">Schema classes and descriptions in Lync Server 2013</span></span>](lync-server-2013-schema-classes-and-descriptions.md)

  - [<span data-ttu-id="a738b-120">Lync Server 2013 中的架构属性和说明</span><span class="sxs-lookup"><span data-stu-id="a738b-120">Schema attributes and descriptions in Lync Server 2013</span></span>](lync-server-2013-schema-attributes-and-descriptions.md)

  - [<span data-ttu-id="a738b-121">Lync Server 2013 中按类分类的架构属性</span><span class="sxs-lookup"><span data-stu-id="a738b-121">Schema attributes by class in Lync Server 2013</span></span>](lync-server-2013-schema-attributes-by-class.md)

  - [<span data-ttu-id="a738b-122">Lync Server 2013 中的林准备所做的更改</span><span class="sxs-lookup"><span data-stu-id="a738b-122">Changes made by forest preparation in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-forest-preparation.md)

  - [<span data-ttu-id="a738b-123">Lync Server 2013 中的域准备进行的更改</span><span class="sxs-lookup"><span data-stu-id="a738b-123">Changes made by domain preparation in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-domain-preparation.md)

  - [<span data-ttu-id="a738b-124">Lync Server 2013 中的 "授权-CsSetupPermission" 所做的更改</span><span class="sxs-lookup"><span data-stu-id="a738b-124">Changes made by Grant-CsSetupPermission in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission)

  - [<span data-ttu-id="a738b-125">Lync Server 2013 中的 "授权-CsOUPermission" 所做的更改</span><span class="sxs-lookup"><span data-stu-id="a738b-125">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission)

</div>

</div>

<span> </span>

</div>

</div>

</div>

