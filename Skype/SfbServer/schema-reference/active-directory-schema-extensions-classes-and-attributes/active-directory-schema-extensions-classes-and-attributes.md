---
title: Active Directory 架构扩展名、类和属性
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 579bfa5a-9443-46dd-9a8e-07d00ba2824d
description: 本参考部分包括以下信息：
ms.openlocfilehash: dc2d147791317134ee9abd3de723f1c53f8f625b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33907099"
---
# <a name="active-directory-schema-extensions-classes-and-attributes"></a><span data-ttu-id="cf27e-103">Active Directory 架构扩展名、类和属性</span><span class="sxs-lookup"><span data-stu-id="cf27e-103">Active Directory schema extensions, classes, and attributes</span></span>
 
<span data-ttu-id="cf27e-104">本参考部分包括以下信息：</span><span class="sxs-lookup"><span data-stu-id="cf27e-104">This reference section includes the following information:</span></span> 
  
- <span data-ttu-id="cf27e-105">新增或更改的 Skype 业务服务器的 active Directory 架构扩展</span><span class="sxs-lookup"><span data-stu-id="cf27e-105">Active Directory schema extensions that are new or changed for Skype for Business Server</span></span>
    
    <span data-ttu-id="cf27e-106">Active Directory 架构包含可在 Active Directory 林中创建每个对象类的正式定义。</span><span class="sxs-lookup"><span data-stu-id="cf27e-106">The Active Directory schema contains formal definitions of every object class that can be created in an Active Directory forest.</span></span> <span data-ttu-id="cf27e-107">该架构还包含每个属性的 Active Directory 对象上可能存在的正式定义。</span><span class="sxs-lookup"><span data-stu-id="cf27e-107">The schema also contains formal definitions of every attribute that can exist on an Active Directory object.</span></span> <span data-ttu-id="cf27e-108">Active Directory 全局编录包含林，以及每个对象的属性的子集的所有对象的副本。</span><span class="sxs-lookup"><span data-stu-id="cf27e-108">The Active Directory global catalog contains replicas of all the objects for the forest, along with a subset of the attributes for each object.</span></span> <span data-ttu-id="cf27e-109">本节介绍的类和属性的新的或更改 Skype 业务服务器中。</span><span class="sxs-lookup"><span data-stu-id="cf27e-109">This section describes the classes and attributes that are new or changed in Skype for Business Server.</span></span>
    
- <span data-ttu-id="cf27e-110">每个说明中使用 Business Server Skype 的所有类</span><span class="sxs-lookup"><span data-stu-id="cf27e-110">All the classes used by Skype for Business Server, with a description of each</span></span>
    
- <span data-ttu-id="cf27e-111">每个说明中使用 Business Server Skype 的所有属性</span><span class="sxs-lookup"><span data-stu-id="cf27e-111">All the attributes used by Skype for Business Server, with a description of each</span></span>
    
- <span data-ttu-id="cf27e-112">与每个属性中使用 Business Server Skype 的类列表以及可能包含</span><span class="sxs-lookup"><span data-stu-id="cf27e-112">A list of the classes used by Skype for Business Server, with the attributes each may contain</span></span>
    
- <span data-ttu-id="cf27e-113">全局设置和对象，以及在林准备期间创建的通用服务和管理组</span><span class="sxs-lookup"><span data-stu-id="cf27e-113">Global settings and objects, in addition to the universal service and administration groups that are created during forest preparation</span></span>
    
- <span data-ttu-id="cf27e-114">域准备过程中在域根和内置容器中创建的访问控制项 (Ace)</span><span class="sxs-lookup"><span data-stu-id="cf27e-114">Access control entries (ACEs) that are created on the domain root and built-in containers during domain preparation</span></span>
    
- <span data-ttu-id="cf27e-115">通过 Grant_CsSetupPermission cmdlet 对 Active Directory 组织单位 (OU) 进行的更改。</span><span class="sxs-lookup"><span data-stu-id="cf27e-115">Changes that are made on an Active Directory organizational unit (OU) by the Grant_CsSetupPermission cmdlet.</span></span>
    
- <span data-ttu-id="cf27e-116">通过 Grant_CsOUPermission cmdlet Active Directory OU 所做的更改。</span><span class="sxs-lookup"><span data-stu-id="cf27e-116">Changes that are made on an Active Directory OU by the Grant_CsOUPermission cmdlet.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="cf27e-117">本节内容</span><span class="sxs-lookup"><span data-stu-id="cf27e-117">In This Section</span></span>

- [<span data-ttu-id="cf27e-118">Skype 业务服务器中的架构更改</span><span class="sxs-lookup"><span data-stu-id="cf27e-118">Schema changes in Skype for Business Server</span></span>](schema-changes.md)
    
- [<span data-ttu-id="cf27e-119">架构类和 Skype 中的业务服务器的说明</span><span class="sxs-lookup"><span data-stu-id="cf27e-119">Schema classes and descriptions in Skype for Business Server</span></span>](schema-classes-and-descriptions.md)
    
- [<span data-ttu-id="cf27e-120">架构属性和 Skype 中的业务服务器的说明</span><span class="sxs-lookup"><span data-stu-id="cf27e-120">Schema attributes and descriptions in Skype for Business Server</span></span>](schema-attributes-and-descriptions.md)
    
- [<span data-ttu-id="cf27e-121">Skype 业务服务器中的类的架构属性</span><span class="sxs-lookup"><span data-stu-id="cf27e-121">Schema attributes by class in Skype for Business Server</span></span>](schema-attributes-by-class.md)
    
- [<span data-ttu-id="cf27e-122">Skype 中为 Business Server 的林准备所做的更改</span><span class="sxs-lookup"><span data-stu-id="cf27e-122">Changes made by forest preparation in Skype for Business Server</span></span>](changes-made-by-forest-preparation.md)
    
- [<span data-ttu-id="cf27e-123">Skype 中的业务服务器的域准备所做的更改</span><span class="sxs-lookup"><span data-stu-id="cf27e-123">Changes made by domain preparation in Skype for Business Server</span></span>](changes-made-by-domain-preparation.md)
    
- [<span data-ttu-id="cf27e-124">业务服务器通过在 Skype Grant-cssetuppermission 所做的更改</span><span class="sxs-lookup"><span data-stu-id="cf27e-124">Changes made by Grant-CsSetupPermission in Skype for Business Server</span></span>](changes-made-by-grant-cssetuppermission.md)
    
- [<span data-ttu-id="cf27e-125">Grant-csoupermission Skype 中通过 Business 服务器所做的更改</span><span class="sxs-lookup"><span data-stu-id="cf27e-125">Changes made by Grant-CsOUPermission in Skype for Business Server</span></span>](changes-made-by-grant-csoupermission.md)
    

