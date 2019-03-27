---
title: 基于角色的访问控制 (RBAC) 的 Skype 业务服务器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d01fba36-eb7e-4de9-9bba-5102ae157820
description: Skype 业务服务器包括基于角色的访问控制 (RBAC) 组，以使您能够保持高标准安全性的同时委派管理任务。 这些组是在林准备期间创建的。 有关林准备的详细信息，请参阅业务服务器的 Skype 的 Active Directory 域服务。 有关林准备所创建的特定组的详细信息，请参阅林准备 Skype 中为 Business Server 部署文档中所做的更改。
ms.openlocfilehash: 461fa82809b16ccf6db1ac02e7c8d0e6698e2b61
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30894271"
---
# <a name="role-based-access-control-rbac-for-skype-for-business-server"></a><span data-ttu-id="c945d-106">基于角色的访问控制 (RBAC) 的 Skype 业务服务器</span><span class="sxs-lookup"><span data-stu-id="c945d-106">Role-based access control (RBAC) for Skype for Business Server</span></span>
 
<span data-ttu-id="c945d-107">Skype 业务服务器包括基于角色的访问控制 (RBAC) 组，以使您能够保持高标准安全性的同时委派管理任务。</span><span class="sxs-lookup"><span data-stu-id="c945d-107">Skype for Business Server includes Role-Based Access Control (RBAC) groups to enable you to delegate administrative tasks while maintaining high standards for security.</span></span> <span data-ttu-id="c945d-108">这些组是在林准备期间创建的。</span><span class="sxs-lookup"><span data-stu-id="c945d-108">These groups are created during forest preparation.</span></span> <span data-ttu-id="c945d-109">有关林准备的详细信息，请参阅[为 Skype 业务服务器的 Active Directory 域服务](active-directory-domain-services.md)。</span><span class="sxs-lookup"><span data-stu-id="c945d-109">For details about forest preparation, see [Active Directory Domain Services for Skype for Business Server](active-directory-domain-services.md).</span></span> <span data-ttu-id="c945d-110">有关林准备所创建的特定组的详细信息，请参阅部署文档中的[Skype 业务服务器中的林准备所做的更改](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md)。</span><span class="sxs-lookup"><span data-stu-id="c945d-110">For details about the specific groups created by forest preparation, see [Changes made by forest preparation in Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span>
  
<span data-ttu-id="c945d-111">使用 RBAC，可以通过将用户分配至预定义的管理角色（包括 11 个可以执行多种常见管理任务的预定义角色）来授予管理权限。</span><span class="sxs-lookup"><span data-stu-id="c945d-111">With RBAC, administrative privilege is granted by assigning users to pre-defined administrative roles, including the 11 predefined roles that cover many common administrative tasks.</span></span> <span data-ttu-id="c945d-112">每个角色相关联的用户的角色中允许运行 Lync Server Management Shell cmdlet 特定列表。</span><span class="sxs-lookup"><span data-stu-id="c945d-112">Each role is associated with a specific list of Lync Server Management Shell cmdlets that users in that role are allowed to run.</span></span> <span data-ttu-id="c945d-113">可以使用 RBAC 来遵守“最小特权”原则，按照该原则，用户只能获得工作所需的管理能力。</span><span class="sxs-lookup"><span data-stu-id="c945d-113">You can use RBAC to follow the principle of "least privilege," in which users are given only the administrative abilities that their jobs require.</span></span> 
  
<span data-ttu-id="c945d-114">RBAC 角色的更多详细信息，请访问：https://technet.microsoft.com/en-us/library/gg425917(v=ocs.15).aspx</span><span class="sxs-lookup"><span data-stu-id="c945d-114">More details on RBAC roles can be found at: https://technet.microsoft.com/en-us/library/gg425917(v=ocs.15).aspx</span></span>
