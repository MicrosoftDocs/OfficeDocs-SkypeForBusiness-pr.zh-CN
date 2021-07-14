---
title: 将用户移至云
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
description: 在停用本地环境Skype for Business移动用户。
ms.openlocfilehash: 992f2dd479e0b8ca8a3f11f069e8ef049259ad9c
ms.sourcegitcommit: f39484688800a3d22f361e660d0eeba974a44fb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420807"
---
# <a name="move-required-users-before-decommissioning-your-on-premises-environment"></a>在停用本地环境之前移动所需用户

本文介绍如何在停用本地部署环境之前，将所需用户Skype for Business Microsoft 云。 这是停止使用本地环境的以下步骤的第 1 步：

- **步骤 1.将所有所需的用户从本地移动到联机。**  (本文) 

- 步骤 2. [禁用混合配置](cloud-consolidation-disabling-hybrid.md)。

- 步骤 3. [将混合应用程序终结点从本地迁移到联机](decommission-move-on-prem-endpoints.md)。 请注意，完成此步骤之前，在执行上述步骤 2 这两者之间，将不能发现任何现有的混合应用程序终结点。 您应计划在同一维护窗口中执行步骤 2 和步骤 3。

- 步骤 4. [删除本地部署Skype for Business部署](decommission-remove-on-prem.md)。


## <a name="move-all-required-users-from-on-premises-to-the-cloud"></a>将所有所需的用户从本地移动到云

完成迁移后将继续使用的任何用户必须先从本地迁移到云。 使用本地管理工具移动用户。 有关详细信息，请参阅在内部 [部署和云之间移动用户](move-users-between-on-premises-and-cloud.md)。

虽然具有本地用户帐户的用户可以使用Skype for Business Server帐户Teams，但是这些用户没有 Teams。 这些用户无法与仍在联机或本地部署Skype for Business (用户进行互操作或) 。 这些用户也无法在客户端客户端中接收 PSTN Teams呼叫。 因此，必须将这些用户移至联机。 此步骤还可确保在迁移时创建的任何Skype for Business Server或会议迁移到Teams。

若要检查本地部署中是否有剩余用户，请在 PowerShell 窗口中Skype for Business Server cmdlet。

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"}
```

如果返回了任何用户，请查看输出以确定是否必须将任何帐户移动到云，对于此类用户，请按照此处 [的步骤操作](move-users-between-on-premises-and-cloud.md)。 对于不再需要的用户帐户，请运行以下 Skype for Business Server PowerShell cmdlet：

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Disable-CsUser
```

> [!NOTE]
> 运行Disable-CsUser将删除Skype for Business筛选条件的所有用户的所有属性。 在继续之前，请确认今后不再需要这些帐户。


现在，你已准备好 [禁用混合配置](cloud-consolidation-disabling-hybrid.md)。

## <a name="see-also"></a>另请参阅

- [停用本地 Skype for Business 环境](decommission-on-prem-overview.md)

- [禁用混合配置](cloud-consolidation-disabling-hybrid.md)

- [将混合应用程序终结点从本地移动到联机](decommission-move-on-prem-endpoints.md)

- [删除本地 Skype for Business 环境](decommission-remove-on-prem.md)




