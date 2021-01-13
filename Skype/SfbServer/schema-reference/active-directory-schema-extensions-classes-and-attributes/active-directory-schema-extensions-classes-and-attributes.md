---
title: Active Directory 架构扩展名、类和属性
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 579bfa5a-9443-46dd-9a8e-07d00ba2824d
description: 本参考部分包括以下信息：
ms.openlocfilehash: 5c8a1ceb6b623466219cbd3df46ff2b39ccceb2c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831932"
---
# <a name="active-directory-schema-extensions-classes-and-attributes"></a><span data-ttu-id="6b27b-103">Active Directory 架构扩展名、类和属性</span><span class="sxs-lookup"><span data-stu-id="6b27b-103">Active Directory schema extensions, classes, and attributes</span></span>
 
<span data-ttu-id="6b27b-104">本参考部分包括以下信息：</span><span class="sxs-lookup"><span data-stu-id="6b27b-104">This reference section includes the following information:</span></span> 
  
- <span data-ttu-id="6b27b-105">Skype for Business Server 新增或已更改的 Active Directory 架构扩展</span><span class="sxs-lookup"><span data-stu-id="6b27b-105">Active Directory schema extensions that are new or changed for Skype for Business Server</span></span>
    
    <span data-ttu-id="6b27b-106">Active Directory 架构包含可在 Active Directory 林中创建的每个对象类的正式定义。</span><span class="sxs-lookup"><span data-stu-id="6b27b-106">The Active Directory schema contains formal definitions of every object class that can be created in an Active Directory forest.</span></span> <span data-ttu-id="6b27b-107">该架构还包含可存在于 Active Directory 对象上的每个属性的正式定义。</span><span class="sxs-lookup"><span data-stu-id="6b27b-107">The schema also contains formal definitions of every attribute that can exist on an Active Directory object.</span></span> <span data-ttu-id="6b27b-108">Active Directory 全局编录包含林中所有对象的副本，以及每个对象的属性子集。</span><span class="sxs-lookup"><span data-stu-id="6b27b-108">The Active Directory global catalog contains replicas of all the objects for the forest, along with a subset of the attributes for each object.</span></span> <span data-ttu-id="6b27b-109">本部分介绍 Skype for Business Server 中新增或已更改的类和属性。</span><span class="sxs-lookup"><span data-stu-id="6b27b-109">This section describes the classes and attributes that are new or changed in Skype for Business Server.</span></span>
    
- <span data-ttu-id="6b27b-110">Skype for Business Server 使用的所有类，每个类的描述</span><span class="sxs-lookup"><span data-stu-id="6b27b-110">All the classes used by Skype for Business Server, with a description of each</span></span>
    
- <span data-ttu-id="6b27b-111">Skype for Business Server 使用的所有属性，每个属性的描述</span><span class="sxs-lookup"><span data-stu-id="6b27b-111">All the attributes used by Skype for Business Server, with a description of each</span></span>
    
- <span data-ttu-id="6b27b-112">Skype for Business Server 使用的类列表，其中每个类可能包含的属性</span><span class="sxs-lookup"><span data-stu-id="6b27b-112">A list of the classes used by Skype for Business Server, with the attributes each may contain</span></span>
    
- <span data-ttu-id="6b27b-113">全局设置和对象，以及在林准备过程中创建的通用服务组和管理组</span><span class="sxs-lookup"><span data-stu-id="6b27b-113">Global settings and objects, in addition to the universal service and administration groups that are created during forest preparation</span></span>
    
- <span data-ttu-id="6b27b-114">域准备过程中在域根和内置容器中创建的访问控制项 (ACE)</span><span class="sxs-lookup"><span data-stu-id="6b27b-114">Access control entries (ACEs) that are created on the domain root and built-in containers during domain preparation</span></span>
    
- <span data-ttu-id="6b27b-115">通过 Grant_CsSetupPermission cmdlet 对 Active Directory 组织单位 (OU) 所做的更改。</span><span class="sxs-lookup"><span data-stu-id="6b27b-115">Changes that are made on an Active Directory organizational unit (OU) by the Grant_CsSetupPermission cmdlet.</span></span>
    
- <span data-ttu-id="6b27b-116">通过 Grant_CsOUPermission cmdlet 对 Active Directory OU 所做的更改。</span><span class="sxs-lookup"><span data-stu-id="6b27b-116">Changes that are made on an Active Directory OU by the Grant_CsOUPermission cmdlet.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="6b27b-117">本节内容</span><span class="sxs-lookup"><span data-stu-id="6b27b-117">In This Section</span></span>

- [<span data-ttu-id="6b27b-118">Skype for Business Server 中的架构更改</span><span class="sxs-lookup"><span data-stu-id="6b27b-118">Schema changes in Skype for Business Server</span></span>](schema-changes.md)
    
- [<span data-ttu-id="6b27b-119">Skype for Business Server 中的架构类和说明</span><span class="sxs-lookup"><span data-stu-id="6b27b-119">Schema classes and descriptions in Skype for Business Server</span></span>](schema-classes-and-descriptions.md)
    
- [<span data-ttu-id="6b27b-120">Skype for Business Server 中的架构属性和说明</span><span class="sxs-lookup"><span data-stu-id="6b27b-120">Schema attributes and descriptions in Skype for Business Server</span></span>](schema-attributes-and-descriptions.md)
    
- [<span data-ttu-id="6b27b-121">Skype for Business Server 中按类分类的架构属性</span><span class="sxs-lookup"><span data-stu-id="6b27b-121">Schema attributes by class in Skype for Business Server</span></span>](schema-attributes-by-class.md)
    
- [<span data-ttu-id="6b27b-122">通过林准备在 Skype for Business Server 中所做的更改</span><span class="sxs-lookup"><span data-stu-id="6b27b-122">Changes made by forest preparation in Skype for Business Server</span></span>](changes-made-by-forest-preparation.md)
    
- [<span data-ttu-id="6b27b-123">由 Skype for Business Server 中的域准备所做的更改</span><span class="sxs-lookup"><span data-stu-id="6b27b-123">Changes made by domain preparation in Skype for Business Server</span></span>](changes-made-by-domain-preparation.md)
    
- [<span data-ttu-id="6b27b-124">Skype for Business Server Grant-CsSetupPermission所做的更改</span><span class="sxs-lookup"><span data-stu-id="6b27b-124">Changes made by Grant-CsSetupPermission in Skype for Business Server</span></span>](changes-made-by-grant-cssetuppermission.md)
    
- [<span data-ttu-id="6b27b-125">Skype for Business Server Grant-CsOUPermission所做的更改</span><span class="sxs-lookup"><span data-stu-id="6b27b-125">Changes made by Grant-CsOUPermission in Skype for Business Server</span></span>](changes-made-by-grant-csoupermission.md)
    

