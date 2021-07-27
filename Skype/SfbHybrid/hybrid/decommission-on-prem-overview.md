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
description: 有关如何停用本地部署环境Skype for Business说明。
ms.openlocfilehash: 820a5b55fe7bf2b5e2351fff253990fd794c562d
ms.sourcegitcommit: 3f1635d1915561798ea764c3e33d7db55f7e49da
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/23/2021
ms.locfileid: "53574217"
---
# <a name="decommission-your-on-premises-skype-for-business-environment"></a>停用本地 Skype for Business 环境

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

如果你的组织Teams本地部署 Skype for Business Server，你可以完全将这些环境迁移到云，然后停用本地部署 Skype for Business Server。 

> [!NOTE]
> 在停用本地环境之前，必须在本地部署和部署[](configure-hybrid-connectivity.md)环境之间配置混合Microsoft 365。 配置混合连接后，你可以将用户迁移到云，同时从本地迁移他们的会议，以及将任何联系人从 Skype for Business Server 迁移到 Teams。 配置混合连接是将用户从本地迁移到云并确保实现完整的混合Teams一步。

若要完成从本地到云的迁移并停止使用本地 Skype for Business Server 环境，必须按以下顺序完成以下步骤：

- **步骤 1.** [将所有所需的用户从本地移动到联机](decommission-move-on-prem-users.md)。

- **步骤 2.** [禁用混合配置](cloud-consolidation-disabling-hybrid.md)。

- **步骤 3.** [将混合应用程序终结点从本地移动到联机](decommission-move-on-prem-endpoints.md)。

- **步骤 4.** [删除本地部署Skype for Business部署](decommission-remove-on-prem.md)。

