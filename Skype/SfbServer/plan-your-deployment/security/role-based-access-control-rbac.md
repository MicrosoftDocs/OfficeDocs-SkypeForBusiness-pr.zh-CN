---
title: 基于角色的访问控制 (RBAC) 的 Skype 业务服务器
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
ms.openlocfilehash: b0029ec683bec29da187ecd23dd0c3230fc603a5
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20967689"
---
# <a name="role-based-access-control-rbac-for-skype-for-business-server"></a>基于角色的访问控制 (RBAC) 的 Skype 业务服务器
 
Skype 业务服务器包括基于角色的访问控制 (RBAC) 组，以使您能够保持高标准安全性的同时委派管理任务。 这些组是在林准备期间创建的。 有关林准备的详细信息，请参阅[为 Skype 业务服务器的 Active Directory 域服务](active-directory-domain-services.md)。 有关林准备所创建的特定组的详细信息，请参阅部署文档中的[Skype 业务服务器中的林准备所做的更改](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md)。
  
使用 RBAC，可以通过将用户分配至预定义的管理角色（包括 11 个可以执行多种常见管理任务的预定义角色）来授予管理权限。 每个角色相关联的用户的角色中允许运行 Lync Server Management Shell cmdlet 特定列表。 可以使用 RBAC 来遵守“最小特权”原则，按照该原则，用户只能获得工作所需的管理能力。 
  
RBAC 角色的更多详细信息，请访问：https://technet.microsoft.com/en-us/library/gg425917(v=ocs.15).aspx
