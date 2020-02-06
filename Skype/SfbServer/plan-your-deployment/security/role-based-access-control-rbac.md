---
title: Skype for business Server 的基于角色的访问控制（RBAC）
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d01fba36-eb7e-4de9-9bba-5102ae157820
description: Skype for Business 服务器包含基于角色的访问控制（RBAC）组，使你能够委派管理任务，同时保持高标准的安全。 这些组是在林准备期间创建的。 有关林准备的详细信息，请参阅适用于 Skype for Business 服务器的 Active Directory 域服务。 有关由林准备创建的特定组的详细信息，请参阅部署文档中 Skype for Business 服务器的林准备所做的更改。
ms.openlocfilehash: 41efad45b442d9c7fca82d090afa0d1aa23e7d63
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815620"
---
# <a name="role-based-access-control-rbac-for-skype-for-business-server"></a><span data-ttu-id="943e5-106">Skype for business Server 的基于角色的访问控制（RBAC）</span><span class="sxs-lookup"><span data-stu-id="943e5-106">Role-based access control (RBAC) for Skype for Business Server</span></span>
 
<span data-ttu-id="943e5-107">Skype for Business 服务器包含基于角色的访问控制（RBAC）组，使你能够委派管理任务，同时保持高标准的安全。</span><span class="sxs-lookup"><span data-stu-id="943e5-107">Skype for Business Server includes Role-Based Access Control (RBAC) groups to enable you to delegate administrative tasks while maintaining high standards for security.</span></span> <span data-ttu-id="943e5-108">这些组是在林准备期间创建的。</span><span class="sxs-lookup"><span data-stu-id="943e5-108">These groups are created during forest preparation.</span></span> <span data-ttu-id="943e5-109">有关林准备的详细信息，请参阅[适用于 Skype For Business 服务器的 Active Directory 域服务](active-directory-domain-services.md)。</span><span class="sxs-lookup"><span data-stu-id="943e5-109">For details about forest preparation, see [Active Directory Domain Services for Skype for Business Server](active-directory-domain-services.md).</span></span> <span data-ttu-id="943e5-110">有关由林准备创建的特定组的详细信息，请参阅部署文档中[Skype For Business 服务器的林准备所做的更改](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md)。</span><span class="sxs-lookup"><span data-stu-id="943e5-110">For details about the specific groups created by forest preparation, see [Changes made by forest preparation in Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span>
  
<span data-ttu-id="943e5-111">使用 RBAC，可以通过将用户分配至预定义的管理角色（包括 11 个可以执行多种常见管理任务的预定义角色）来授予管理权限。</span><span class="sxs-lookup"><span data-stu-id="943e5-111">With RBAC, administrative privilege is granted by assigning users to pre-defined administrative roles, including the 11 predefined roles that cover many common administrative tasks.</span></span> <span data-ttu-id="943e5-112">每个角色都与该角色中的用户允许运行的 Skype for business Server Management Shell cmdlet 的特定列表相关联。</span><span class="sxs-lookup"><span data-stu-id="943e5-112">Each role is associated with a specific list of Skype for Business Server Management Shell cmdlets that users in that role are allowed to run.</span></span> <span data-ttu-id="943e5-113">可以使用 RBAC 来遵守“最小特权”原则，按照该原则，用户只能获得工作所需的管理能力。</span><span class="sxs-lookup"><span data-stu-id="943e5-113">You can use RBAC to follow the principle of "least privilege," in which users are given only the administrative abilities that their jobs require.</span></span> 
  
<span data-ttu-id="943e5-114">[规划基于角色的访问控制](https://docs.microsoft.com/lyncserver/lync-server-2013-planning-for-role-based-access-control)时，可以找到有关 RBAC 角色的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="943e5-114">More details on RBAC roles can be found at [Planning for role-based access control](https://docs.microsoft.com/lyncserver/lync-server-2013-planning-for-role-based-access-control).</span></span>
