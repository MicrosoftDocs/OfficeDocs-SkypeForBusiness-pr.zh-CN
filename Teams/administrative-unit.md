---
title: 使用管理单元管理设备
author: mahoffman
ms.author: serdars
ms.reviewer: prasad.ghlove
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何使用管理单元Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 63579e7e9b6b2f7a7456349c489d4f544eb67cc1
ms.sourcegitcommit: 9e868a155bcd20dd5dafdedcff091ff77ca7398b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/31/2022
ms.locfileid: "64584307"
---
# <a name="manage-devices-in-the-teams-admin-center-with-administrative-units"></a>使用管理单元Teams管理中心中的设备

管理中心Teams单元提供详细的基于角色的访问权限，用于管理Teams设备。 管理单元Teams特定资源的管理员访问权限，但限制该管理员对其他资源的访问权限。 如果你拥有位于不同国家/Teams本地管理员，这尤其有用。

例如，Contoso 在全球拥有运营。 Alice 是位于伦敦的全球 IT 管理员，Prashant 是位于印度班加罗尔的本地 IT 管理员。 现在，当 Prashant 以设备管理员Teams登录管理中心时，他可以看到Teams的设备。 Alice 希望限制 Prashant 仅Teams班加罗尔的设备的访问权限。 管理单位允许她这样做。 有关详细信息，请参阅管理[单元Azure Active Directory](/azure/active-directory/roles/administrative-units)。

> [!NOTE]
> 管理单元目前仅在 Teams 管理中心中提供，Teams设备管理员角色。

## <a name="add-administrative-units"></a>添加管理单元

需要成为全局管理员才能添加管理单元。 若要了解如何，请参阅 [添加管理单元](/azure/active-directory/roles/admin-units-manage#add-an-administrative-unit)。

## <a name="assign-admins-to-administrative-units"></a>将管理员分配到管理单元

你还需要是全局管理员才能分配管理单元。 可以使用 Azure 门户 PowerShell 或 Microsoft 图形 API 分配管理单元。 有关详细信息，请参阅使用[管理Azure AD分配角色](/azure/active-directory/roles/admin-units-assign-roles)。

## <a name="select-administrative-units"></a>选择管理单元

如果你是设备管理员Teams，在全局管理员将你分配到管理单元后，你可以登录到 Teams 管理中心来管理设备。 如果只分配到一个管理单元，则只能看到分配给该管理单元的设备。 如果分配到多个管理单元，可以在这些管理单元之间切换，而无需从管理中心Teams。 

1. 登录到 Teams [管理中心](https://go.microsoft.com/fwlink/p/?linkid=2024339)。

2. 在" **管理单元"** 对话框中，执行以下步骤之一：
    - 选择要管理的管理单元，或 
    - 如果 **有权管理** 组织的所有设备，请选择"所有设备"。

3. 选择“**保存**”。

## <a name="switch-administrative-units"></a>切换管理单元

如果你是设备管理员Teams，如果登录到管理中心，可以在管理单元Teams切换。 切换到其他管理单元：

1. 登录到 Teams [管理中心](https://go.microsoft.com/fwlink/p/?linkid=2024339)。

2. 在左侧导航栏中，选择 **Teams设备"**。

3. 在右窗格的左上角，选择显示的管理单元。

4. 在" **管理单元"** 对话框中，执行以下步骤之一：
    - 选择要管理的管理单元，或 
    - 如果 **有权管理** 组织的所有设备，请选择"所有设备"。

5. 选择“**保存**”。

## <a name="related-topics"></a>相关主题

- [将用户或组添加到管理单元](/azure/active-directory/roles/admin-units-members-add)
