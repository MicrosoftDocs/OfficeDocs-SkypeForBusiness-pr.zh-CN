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
# <a name="role-based-access-control-rbac-for-skype-for-business-server"></a>Skype for business Server 的基于角色的访问控制（RBAC）
 
Skype for Business 服务器包含基于角色的访问控制（RBAC）组，使你能够委派管理任务，同时保持高标准的安全。 这些组是在林准备期间创建的。 有关林准备的详细信息，请参阅[适用于 Skype For Business 服务器的 Active Directory 域服务](active-directory-domain-services.md)。 有关由林准备创建的特定组的详细信息，请参阅部署文档中[Skype For Business 服务器的林准备所做的更改](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md)。
  
使用 RBAC，可以通过将用户分配至预定义的管理角色（包括 11 个可以执行多种常见管理任务的预定义角色）来授予管理权限。 每个角色都与该角色中的用户允许运行的 Skype for business Server Management Shell cmdlet 的特定列表相关联。 可以使用 RBAC 来遵守“最小特权”原则，按照该原则，用户只能获得工作所需的管理能力。 
  
[规划基于角色的访问控制](https://docs.microsoft.com/lyncserver/lync-server-2013-planning-for-role-based-access-control)时，可以找到有关 RBAC 角色的更多详细信息。
