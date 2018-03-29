---
title: 活动目录架构扩展、 类和属性
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 579bfa5a-9443-46dd-9a8e-07d00ba2824d
description: 此引用部分包括以下信息：
ms.openlocfilehash: f185a11bdc5d3700839be2f1306e266d9ab6af26
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="active-directory-schema-extensions-classes-and-attributes"></a><span data-ttu-id="4075b-103">活动目录架构扩展、 类和属性</span><span class="sxs-lookup"><span data-stu-id="4075b-103">Active Directory schema extensions, classes, and attributes</span></span>
 
<span data-ttu-id="4075b-104">此引用部分包括以下信息：</span><span class="sxs-lookup"><span data-stu-id="4075b-104">This reference section includes the following information:</span></span> 
  
- <span data-ttu-id="4075b-105">将新的或更改的业务服务器的 Skype 的活动目录架构扩展</span><span class="sxs-lookup"><span data-stu-id="4075b-105">Active Directory schema extensions that are new or changed for Skype for Business Server</span></span>
    
    <span data-ttu-id="4075b-106">Active Directory 架构中包含可以在 Active Directory 目录林中创建的每个对象类的正式定义。</span><span class="sxs-lookup"><span data-stu-id="4075b-106">The Active Directory schema contains formal definitions of every object class that can be created in an Active Directory forest.</span></span> <span data-ttu-id="4075b-107">该架构还包含可存在于 Active Directory 对象的每个属性的正式定义。</span><span class="sxs-lookup"><span data-stu-id="4075b-107">The schema also contains formal definitions of every attribute that can exist on an Active Directory object.</span></span> <span data-ttu-id="4075b-108">Active Directory 全局编录包含的目录林的每个对象属性的子集以及所有对象的副本。</span><span class="sxs-lookup"><span data-stu-id="4075b-108">The Active Directory global catalog contains replicas of all the objects for the forest, along with a subset of the attributes for each object.</span></span> <span data-ttu-id="4075b-109">本部分介绍的类和新的或更改在 Skype 业务服务器的属性。</span><span class="sxs-lookup"><span data-stu-id="4075b-109">This section describes the classes and attributes that are new or changed in Skype for Business Server.</span></span>
    
- <span data-ttu-id="4075b-110">用于通过 Skype 业务服务器，每个说明的所有类</span><span class="sxs-lookup"><span data-stu-id="4075b-110">All the classes used by Skype for Business Server, with a description of each</span></span>
    
- <span data-ttu-id="4075b-111">用于通过 Skype 业务服务器，每个说明的所有属性</span><span class="sxs-lookup"><span data-stu-id="4075b-111">All the attributes used by Skype for Business Server, with a description of each</span></span>
    
- <span data-ttu-id="4075b-112">可能包含用于通过 Skype 业务服务器与每个属性的类的列表</span><span class="sxs-lookup"><span data-stu-id="4075b-112">A list of the classes used by Skype for Business Server, with the attributes each may contain</span></span>
    
- <span data-ttu-id="4075b-113">全局设置和对象，除在林准备过程中创建的通用服务和管理组</span><span class="sxs-lookup"><span data-stu-id="4075b-113">Global settings and objects, in addition to the universal service and administration groups that are created during forest preparation</span></span>
    
- <span data-ttu-id="4075b-114">在域准备过程创建域根目录和内置容器的访问控制项 (Ace)</span><span class="sxs-lookup"><span data-stu-id="4075b-114">Access control entries (ACEs) that are created on the domain root and built-in containers during domain preparation</span></span>
    
- <span data-ttu-id="4075b-115">由 Grant_CsSetupPermission cmdlet 的 Active Directory 组织单位 (OU) 进行的更改。</span><span class="sxs-lookup"><span data-stu-id="4075b-115">Changes that are made on an Active Directory organizational unit (OU) by the Grant_CsSetupPermission cmdlet.</span></span>
    
- <span data-ttu-id="4075b-116">活动目录 OU 上通过 Grant_CsOUPermission cmdlet 所做的更改。</span><span class="sxs-lookup"><span data-stu-id="4075b-116">Changes that are made on an Active Directory OU by the Grant_CsOUPermission cmdlet.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="4075b-117">本节内容</span><span class="sxs-lookup"><span data-stu-id="4075b-117">In This Section</span></span>

- [<span data-ttu-id="4075b-118">在 Skype 业务服务器的架构更改</span><span class="sxs-lookup"><span data-stu-id="4075b-118">Schema changes in Skype for Business Server</span></span>](schema-changes.md)
    
- [<span data-ttu-id="4075b-119">架构类和在 Skype 业务服务器的描述</span><span class="sxs-lookup"><span data-stu-id="4075b-119">Schema classes and descriptions in Skype for Business Server</span></span>](schema-classes-and-descriptions.md)
    
- [<span data-ttu-id="4075b-120">架构属性，并在 Skype 业务服务器的描述</span><span class="sxs-lookup"><span data-stu-id="4075b-120">Schema attributes and descriptions in Skype for Business Server</span></span>](schema-attributes-and-descriptions.md)
    
- [<span data-ttu-id="4075b-121">在 Skype 业务服务器类的架构属性</span><span class="sxs-lookup"><span data-stu-id="4075b-121">Schema attributes by class in Skype for Business Server</span></span>](schema-attributes-by-class.md)
    
- [<span data-ttu-id="4075b-122">由林准备在 Skype 业务服务器所做的更改</span><span class="sxs-lookup"><span data-stu-id="4075b-122">Changes made by forest preparation in Skype for Business Server</span></span>](changes-made-by-forest-preparation.md)
    
- [<span data-ttu-id="4075b-123">通过在 Skype 业务服务器的域准备工作所做的更改</span><span class="sxs-lookup"><span data-stu-id="4075b-123">Changes made by domain preparation in Skype for Business Server</span></span>](changes-made-by-domain-preparation.md)
    
- [<span data-ttu-id="4075b-124">在 Skype 的授予 CsSetupPermission 业务服务器所做更改</span><span class="sxs-lookup"><span data-stu-id="4075b-124">Changes made by Grant-CsSetupPermission in Skype for Business Server</span></span>](changes-made-by-grant-cssetuppermission.md)
    
- [<span data-ttu-id="4075b-125">在 Skype 的授予 CsOUPermission 业务服务器所做更改</span><span class="sxs-lookup"><span data-stu-id="4075b-125">Changes made by Grant-CsOUPermission in Skype for Business Server</span></span>](changes-made-by-grant-csoupermission.md)
    

