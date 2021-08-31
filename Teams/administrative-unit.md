---
title: 使用管理单元功能Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: prasad.ghlove
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何在云中使用管理单元Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9f1424149a3f585b30cb7a31d7742370c06cae3d
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2021
ms.locfileid: "58736121"
---
# <a name="administrative-unit-functionality-for-device-management-in-teams"></a>设备管理中的管理单元功能Teams

使用管理中心进行更精细的基于角色的访问，Microsoft Teams管理。 我们已通过管理中心实现了设备管理Teams概念。

使用管理单元概念，可确保专用管理员能够访问一组特定的资源。 管理单元限制访问所有资源。 你可以为设备管理扩展Teams功能。

> [!NOTE]
> 管理单元概念目前仅适用于Teams管理员角色。

例如，Contoso 跨不同的地理区域运营。 Alice 是伦敦的全球 IT 管理员，Prashant 是印度 IT 管理员。 现在，当 Prashant 使用Teams管理员角色登录管理中心时，他们可以看到世界各地的设备。 Alice 想要将 Prashant 的访问权限限制为仅允许印度存在的设备。 管理单元概念有助于解决此问题。 详细了解 [管理单元概念](/azure/active-directory/roles/administrative-units)。

![显示方案的图表。](media/au-diagram.png)

## <a name="creation-of-administrative-units"></a>创建管理单元

在 Azure 门户中创建管理单元，并为每个管理单元分配管理员。 在管理管理单元 中详细了解如何 [分配管理单元](/azure/active-directory/roles/admin-units-manage)。

![示例公司管理单元。](media/au-example.png)

创建后，全局 IT 管理员可以添加对应于该管理单元的设备用户。

![用户预览版的示例公司。](media/au-example2.png)

可以使用 [Add-AzureADMSScopedRoleMembership](/powershell/module/azuread/add-azureadmsscopedrolemembership?view=azureadps-2.0) cmdlet 通过 PowerShell 完成角色分配。

将角色分配给管理单元的用户后，用户需要登录到管理Teams中心，以开始管理具有作用域的设备。

## <a name="experience-for-administrative-unit-admin"></a>管理单元管理员的经验

如果为同一管理员分配了多个管理单元的责任，他们可以在管理单元之间切换，而无需从门户中退出。 在更改的管理单元视图中，他们只能看到与新的管理单元关联的一组设备。
