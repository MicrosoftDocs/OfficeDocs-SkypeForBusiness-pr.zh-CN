---
title: 停用本地 Skype for Business 环境
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: 有关如何停用本地 Skype for Business 环境的说明。
ms.openlocfilehash: 7f5109661fc7d29d83172489dd987b96cb7e87fd
ms.sourcegitcommit: f223b5f3735f165d46bb611a52fcdfb0f4b88f66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2021
ms.locfileid: "51593875"
---
# <a name="decommission-your-on-premises-skype-for-business-environment"></a>停用本地 Skype for Business 环境

如果你的组织将 Teams 或 Skype for Business Online 与 Skype for Business Server 本地部署一同使用，你可以将这些环境完全迁移到云，然后停用 Skype for Business Server 本地部署。 

> [!NOTE]
> 在停用本地环境之前 [，必须在本地](configure-hybrid-connectivity.md) 部署和 Microsoft 365 之间配置混合连接。 配置混合连接后，你可以将用户迁移到云，同时从本地迁移他们的会议，以及将任何联系人从 Skype for Business Server 迁移到 Teams。 配置混合连接是将用户从本地迁移到云并确保 Teams 完整功能所需的步骤。

若要完成从本地到云的迁移并停止使用本地 Skype for Business Server 环境，必须按以下顺序完成以下步骤：

- **步骤 1.** [将所有必需的用户和应用程序终结点从本地移动到联机](decommission-move-on-prem-users.md)。

- **步骤 2.** [禁用混合配置](cloud-consolidation-disabling-hybrid.md)。

- **步骤 3.** [删除本地 Skype for Business 部署](decommission-remove-on-prem.md)。

