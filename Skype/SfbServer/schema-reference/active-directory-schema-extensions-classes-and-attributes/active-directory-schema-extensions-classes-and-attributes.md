---
title: Active Directory 架构扩展名、类和属性
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 579bfa5a-9443-46dd-9a8e-07d00ba2824d
description: '本参考部分包含以下信息:'
ms.openlocfilehash: 5934c9ffab8055de86cdaf3bcf507fa9c806f245
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296740"
---
# <a name="active-directory-schema-extensions-classes-and-attributes"></a><span data-ttu-id="155d5-103">Active Directory 架构扩展名、类和属性</span><span class="sxs-lookup"><span data-stu-id="155d5-103">Active Directory schema extensions, classes, and attributes</span></span>
 
<span data-ttu-id="155d5-104">本参考部分包含以下信息:</span><span class="sxs-lookup"><span data-stu-id="155d5-104">This reference section includes the following information:</span></span> 
  
- <span data-ttu-id="155d5-105">Skype for business 服务器的新的或已更改的 Active Directory 架构扩展</span><span class="sxs-lookup"><span data-stu-id="155d5-105">Active Directory schema extensions that are new or changed for Skype for Business Server</span></span>
    
    <span data-ttu-id="155d5-106">Active Directory 架构包含可在 Active Directory 林中创建的每个对象类的正式定义。</span><span class="sxs-lookup"><span data-stu-id="155d5-106">The Active Directory schema contains formal definitions of every object class that can be created in an Active Directory forest.</span></span> <span data-ttu-id="155d5-107">该架构还包含可存在于 Active Directory 对象上的每个属性的正式定义。</span><span class="sxs-lookup"><span data-stu-id="155d5-107">The schema also contains formal definitions of every attribute that can exist on an Active Directory object.</span></span> <span data-ttu-id="155d5-108">Active Directory 全局编录包含林的所有对象的副本, 以及每个对象的属性子集。</span><span class="sxs-lookup"><span data-stu-id="155d5-108">The Active Directory global catalog contains replicas of all the objects for the forest, along with a subset of the attributes for each object.</span></span> <span data-ttu-id="155d5-109">本部分介绍 Skype for Business 服务器中新增或更改的类和属性。</span><span class="sxs-lookup"><span data-stu-id="155d5-109">This section describes the classes and attributes that are new or changed in Skype for Business Server.</span></span>
    
- <span data-ttu-id="155d5-110">Skype for Business Server 使用的所有课堂, 以及每个课堂的描述</span><span class="sxs-lookup"><span data-stu-id="155d5-110">All the classes used by Skype for Business Server, with a description of each</span></span>
    
- <span data-ttu-id="155d5-111">Skype for Business Server 使用的所有属性, 以及每个属性的说明</span><span class="sxs-lookup"><span data-stu-id="155d5-111">All the attributes used by Skype for Business Server, with a description of each</span></span>
    
- <span data-ttu-id="155d5-112">Skype for Business 服务器使用的类的列表, 每个类可能包含的属性</span><span class="sxs-lookup"><span data-stu-id="155d5-112">A list of the classes used by Skype for Business Server, with the attributes each may contain</span></span>
    
- <span data-ttu-id="155d5-113">全局设置和对象, 以及林准备期间创建的通用服务和管理组</span><span class="sxs-lookup"><span data-stu-id="155d5-113">Global settings and objects, in addition to the universal service and administration groups that are created during forest preparation</span></span>
    
- <span data-ttu-id="155d5-114">在域准备期间在域根和内置容器上创建的访问控制条目 (Ace)</span><span class="sxs-lookup"><span data-stu-id="155d5-114">Access control entries (ACEs) that are created on the domain root and built-in containers during domain preparation</span></span>
    
- <span data-ttu-id="155d5-115">通过 Grant_CsSetupPermission cmdlet 在 Active Directory 组织单元 (OU) 上进行的更改。</span><span class="sxs-lookup"><span data-stu-id="155d5-115">Changes that are made on an Active Directory organizational unit (OU) by the Grant_CsSetupPermission cmdlet.</span></span>
    
- <span data-ttu-id="155d5-116">通过 Grant_CsOUPermission cmdlet 在 Active Directory OU 上进行的更改。</span><span class="sxs-lookup"><span data-stu-id="155d5-116">Changes that are made on an Active Directory OU by the Grant_CsOUPermission cmdlet.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="155d5-117">本节内容</span><span class="sxs-lookup"><span data-stu-id="155d5-117">In This Section</span></span>

- [<span data-ttu-id="155d5-118">Skype for Business 服务器中的架构更改</span><span class="sxs-lookup"><span data-stu-id="155d5-118">Schema changes in Skype for Business Server</span></span>](schema-changes.md)
    
- [<span data-ttu-id="155d5-119">Skype for Business 服务器中的架构类和说明</span><span class="sxs-lookup"><span data-stu-id="155d5-119">Schema classes and descriptions in Skype for Business Server</span></span>](schema-classes-and-descriptions.md)
    
- [<span data-ttu-id="155d5-120">Skype for Business Server 中的架构属性和说明</span><span class="sxs-lookup"><span data-stu-id="155d5-120">Schema attributes and descriptions in Skype for Business Server</span></span>](schema-attributes-and-descriptions.md)
    
- [<span data-ttu-id="155d5-121">Skype for Business Server 中按类分类的架构属性</span><span class="sxs-lookup"><span data-stu-id="155d5-121">Schema attributes by class in Skype for Business Server</span></span>](schema-attributes-by-class.md)
    
- [<span data-ttu-id="155d5-122">Skype for Business Server 中的林准备所做的更改</span><span class="sxs-lookup"><span data-stu-id="155d5-122">Changes made by forest preparation in Skype for Business Server</span></span>](changes-made-by-forest-preparation.md)
    
- [<span data-ttu-id="155d5-123">Skype for Business Server 中的域准备所做的更改</span><span class="sxs-lookup"><span data-stu-id="155d5-123">Changes made by domain preparation in Skype for Business Server</span></span>](changes-made-by-domain-preparation.md)
    
- [<span data-ttu-id="155d5-124">由 Skype for Business Server 中的 "授权 CsSetupPermission" 所做的更改</span><span class="sxs-lookup"><span data-stu-id="155d5-124">Changes made by Grant-CsSetupPermission in Skype for Business Server</span></span>](changes-made-by-grant-cssetuppermission.md)
    
- [<span data-ttu-id="155d5-125">由 Skype for Business Server 中的 "授权 CsOUPermission" 所做的更改</span><span class="sxs-lookup"><span data-stu-id="155d5-125">Changes made by Grant-CsOUPermission in Skype for Business Server</span></span>](changes-made-by-grant-csoupermission.md)
    

