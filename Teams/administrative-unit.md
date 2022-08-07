---
title: 使用管理单元管理设备
author: CarolynRowe
ms.author: crowe
ms.reviewer: prasad.ghlove
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何在 Microsoft Teams 中使用管理单元
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Devices
appliesto:
- Microsoft Teams
ms.openlocfilehash: b1ccc079617a1ae58b3881da8ae48c8a993d5863
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2022
ms.locfileid: "67269467"
---
# <a name="manage-devices-in-the-teams-admin-center-with-administrative-units"></a>使用管理单元管理 Teams 管理中心中的设备

Teams 管理中心的管理单元提供详细的基于角色的访问权限来管理 Teams 设备。 管理单位授予 Teams 管理员对特定资源的访问权限，但限制该管理员对其他资源的访问权限。 如果你在不同国家或地区拥有本地 Teams 管理员，这尤其有用。

例如，Contoso 在全球开展操作。 Alice 是总部设在伦敦的全球 IT 管理员，而 Prashant 是位于印度班加罗尔的本地 IT 管理员。 今天，当 Prashant 以设备管理员身份登录 Teams 管理中心时，他可以看到全球各地的 Teams 设备。 Alice 希望限制 Prashant 仅在班加罗尔访问 Teams 设备。 管理单位允许她执行此操作。 若要了解详细信息，请参阅 [Azure Active Directory 中的管理单元](/azure/active-directory/roles/administrative-units)。

> [!NOTE]
> 管理单元目前仅适用于 Teams 设备管理员角色的 Teams 管理中心。

## <a name="add-administrative-units"></a>添加管理单元

需要全局管理员才能添加管理单元。 若要了解如何操作，请参阅 [“添加管理单元](/azure/active-directory/roles/admin-units-manage#add-an-administrative-unit)”。

## <a name="assign-admins-to-administrative-units"></a>将管理员分配到管理单元

还需要全局管理员才能分配管理单元。 可以使用 Azure 门户、PowerShell 或 Microsoft 图形 API 分配管理单元。 若要了解详细信息，请参阅 [分配具有管理单元范围的 Azure AD 角色](/azure/active-directory/roles/admin-units-assign-roles)。

## <a name="select-administrative-units"></a>选择管理单元

如果你是 Teams 设备管理员，则全局管理员将你分配到管理单元后，可以登录 Teams 管理中心来管理设备。 如果只分配给一个管理单元，则只会看到分配给该管理单元的设备。 如果分配到多个管理单元，则可以在这些管理单元之间切换，而无需从 Teams 管理中心注销。 

1. 登录到 [Teams 管理中心](https://go.microsoft.com/fwlink/p/?linkid=2024339)。

2. 在“ **管理单元** ”对话框中，执行以下步骤之一：
    - 选择要管理的管理单元，或 
    - 如果你有权管理组织的所有设备，请选择 **所有设备** 。

3. 选择“**保存**”。

## <a name="switch-administrative-units"></a>切换管理单元

如果你是 Teams 设备管理员，如果登录到 Teams 管理中心，则可以在管理单元之间切换。 若要切换到其他管理单元，请执行以下操作：

1. 登录到 [Teams 管理中心](https://go.microsoft.com/fwlink/p/?linkid=2024339)。

2. 在左侧导航栏中，选择 **Teams 设备**。

3. 在右窗格的左上角，选择显示的管理单元。

4. 在“ **管理单元** ”对话框中，执行以下步骤之一：
    - 选择要管理的管理单元，或 
    - 如果你有权管理组织的所有设备，请选择 **所有设备** 。

5. 选择“**保存**”。

## <a name="related-topics"></a>相关主题

- [将用户或组添加到管理单元](/azure/active-directory/roles/admin-units-members-add)
