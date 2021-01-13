---
title: 基于角色的访问控制 (RBAC) For Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d01fba36-eb7e-4de9-9bba-5102ae157820
description: Skype for Business Server 包括Role-Based访问控制 (RBAC) 组，使你可以委派管理任务，同时维护高安全标准。 这些组是在林准备期间创建的。 有关林准备的详细信息，请参阅 Active Directory Domain Services for Skype for Business Server。 有关林准备创建的特定组的详细信息，请参阅部署文档中的 Skype for Business Server 中的林准备所做的更改。
ms.openlocfilehash: 9d3c453d4e7c3057c03f99cf2ff31b5fe17ae0bb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832102"
---
# <a name="role-based-access-control-rbac-for-skype-for-business-server"></a><span data-ttu-id="d37f2-106">基于角色的访问控制 (RBAC) For Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="d37f2-106">Role-based access control (RBAC) for Skype for Business Server</span></span>
 
<span data-ttu-id="d37f2-107">Skype for Business Server 包括Role-Based访问控制 (RBAC) 组，使你可以委派管理任务，同时维护高安全标准。</span><span class="sxs-lookup"><span data-stu-id="d37f2-107">Skype for Business Server includes Role-Based Access Control (RBAC) groups to enable you to delegate administrative tasks while maintaining high standards for security.</span></span> <span data-ttu-id="d37f2-108">这些组是在林准备期间创建的。</span><span class="sxs-lookup"><span data-stu-id="d37f2-108">These groups are created during forest preparation.</span></span> <span data-ttu-id="d37f2-109">有关林准备的详细信息，请参阅[Active Directory 域服务 for Skype for Business Server。](active-directory-domain-services.md)</span><span class="sxs-lookup"><span data-stu-id="d37f2-109">For details about forest preparation, see [Active Directory Domain Services for Skype for Business Server](active-directory-domain-services.md).</span></span> <span data-ttu-id="d37f2-110">有关林准备创建的特定组的详细信息，请参阅部署文档中 [的 Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) 中的林准备所做的更改。</span><span class="sxs-lookup"><span data-stu-id="d37f2-110">For details about the specific groups created by forest preparation, see [Changes made by forest preparation in Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span>
  
<span data-ttu-id="d37f2-111">使用 RBAC，可以通过将用户分配至预定义的管理角色（包括 11 个可以执行多种常见管理任务的预定义角色）来授予管理权限。</span><span class="sxs-lookup"><span data-stu-id="d37f2-111">With RBAC, administrative privilege is granted by assigning users to pre-defined administrative roles, including the 11 predefined roles that cover many common administrative tasks.</span></span> <span data-ttu-id="d37f2-112">每个角色都与允许该角色中的用户运行的 Skype for Business Server 命令行管理程序 cmdlet 的特定列表相关联。</span><span class="sxs-lookup"><span data-stu-id="d37f2-112">Each role is associated with a specific list of Skype for Business Server Management Shell cmdlets that users in that role are allowed to run.</span></span> <span data-ttu-id="d37f2-113">可以使用 RBAC 来遵守“最小特权”原则，按照该原则，用户只能获得工作所需的管理能力。</span><span class="sxs-lookup"><span data-stu-id="d37f2-113">You can use RBAC to follow the principle of "least privilege," in which users are given only the administrative abilities that their jobs require.</span></span> 
  
<span data-ttu-id="d37f2-114">有关 RBAC 角色的更多详细信息，请参阅 [规划基于角色的访问控制](https://docs.microsoft.com/lyncserver/lync-server-2013-planning-for-role-based-access-control)。</span><span class="sxs-lookup"><span data-stu-id="d37f2-114">More details on RBAC roles can be found at [Planning for role-based access control](https://docs.microsoft.com/lyncserver/lync-server-2013-planning-for-role-based-access-control).</span></span>
