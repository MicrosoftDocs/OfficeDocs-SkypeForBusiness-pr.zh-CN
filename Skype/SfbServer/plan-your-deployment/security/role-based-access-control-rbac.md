---
title: Skype for business Server 的基于角色的访问控制 (RBAC)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d01fba36-eb7e-4de9-9bba-5102ae157820
description: Skype for Business 服务器包含基于角色的访问控制 (RBAC) 组, 使你能够委派管理任务, 同时保持高标准的安全。 这些组是在林准备期间创建的。 有关林准备的详细信息, 请参阅适用于 Skype for Business 服务器的 Active Directory 域服务。 有关由林准备创建的特定组的详细信息, 请参阅部署文档中 Skype for Business 服务器的林准备所做的更改。
ms.openlocfilehash: d5f31d7c53c743e4b2d001b00abec7ec93ef8d91
ms.sourcegitcommit: c554b09527817dc3e06b10509f6668b42ccc5cb9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/17/2019
ms.locfileid: "35759013"
---
# <a name="role-based-access-control-rbac-for-skype-for-business-server"></a>Skype for business Server 的基于角色的访问控制 (RBAC)
 
Skype for Business 服务器包含基于角色的访问控制 (RBAC) 组, 使你能够委派管理任务, 同时保持高标准的安全。 这些组是在林准备期间创建的。 有关林准备的详细信息, 请参阅[适用于 Skype For Business 服务器的 Active Directory 域服务](active-directory-domain-services.md)。 有关由林准备创建的特定组的详细信息, 请参阅部署文档中[Skype For Business 服务器的林准备所做的更改](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md)。
  
使用 RBAC，可以通过将用户分配至预定义的管理角色（包括 11 个可以执行多种常见管理任务的预定义角色）来授予管理权限。 每个角色都与该角色中的用户允许运行的 Skype for business Server Management Shell cmdlet 的特定列表相关联。 可以使用 RBAC 来遵守“最小特权”原则，按照该原则，用户只能获得工作所需的管理能力。 
  
[规划基于角色的访问控制](https://docs.microsoft.com/lyncserver/lync-server-2013-planning-for-role-based-access-control)时, 可以找到有关 RBAC 角色的更多详细信息。
