---
title: Skype for Business Server 2015 的基于角色的访问控制 (RBAC)
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 4/6/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d01fba36-eb7e-4de9-9bba-5102ae157820
description: Skype 的业务服务器 2015年包括基于角色的访问控制 (RBAC) 组，以便您能够同时保持高标准的安全委派管理任务。 这些组是在林准备期间创建的。 林准备过程的详细信息，请参阅有关业务服务器 2015年的 Skype 的 Active Directory 域服务。 林准备过程所创建的特定组的详细信息，请参阅由林准备在 Skype 业务服务器部署文档中所做的更改。
ms.openlocfilehash: f637ef752bb122cb73220d66fd8aa19c16fb358e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="role-based-access-control-rbac-for-skype-for-business-server-2015"></a>Skype for Business Server 2015 的基于角色的访问控制 (RBAC)
 
Skype 的业务服务器 2015年包括基于角色的访问控制 (RBAC) 组，以便您能够同时保持高标准的安全委派管理任务。 这些组是在林准备期间创建的。 林准备过程的详细信息，请参阅[有关业务服务器 2015年的 Skype 的 Active Directory 域服务](active-directory-domain-services.md)。 林准备过程所创建的特定组的详细信息，请参阅部署文档中[林准备在 Skype 业务服务器中进行更改](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md)。
  
使用 RBAC，可以通过将用户分配至预定义的管理角色（包括 11 个可以执行多种常见管理任务的预定义角色）来授予管理权限。 每个角色都与特定列表中的该角色中的用户都可以运行的 Lync 服务器管理外壳 cmdlet 相关联。 可以使用 RBAC 来遵守“最小特权”原则，按照该原则，用户只能获得工作所需的管理能力。 
  

