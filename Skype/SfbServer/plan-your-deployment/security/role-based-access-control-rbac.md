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
# <a name="role-based-access-control-rbac-for-skype-for-business-server"></a>基于角色的访问控制 (RBAC) For Skype for Business Server
 
Skype for Business Server 包括Role-Based访问控制 (RBAC) 组，使你可以委派管理任务，同时维护高安全标准。 这些组是在林准备期间创建的。 有关林准备的详细信息，请参阅[Active Directory 域服务 for Skype for Business Server。](active-directory-domain-services.md) 有关林准备创建的特定组的详细信息，请参阅部署文档中 [的 Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) 中的林准备所做的更改。
  
使用 RBAC，可以通过将用户分配至预定义的管理角色（包括 11 个可以执行多种常见管理任务的预定义角色）来授予管理权限。 每个角色都与允许该角色中的用户运行的 Skype for Business Server 命令行管理程序 cmdlet 的特定列表相关联。 可以使用 RBAC 来遵守“最小特权”原则，按照该原则，用户只能获得工作所需的管理能力。 
  
有关 RBAC 角色的更多详细信息，请参阅 [规划基于角色的访问控制](https://docs.microsoft.com/lyncserver/lync-server-2013-planning-for-role-based-access-control)。
