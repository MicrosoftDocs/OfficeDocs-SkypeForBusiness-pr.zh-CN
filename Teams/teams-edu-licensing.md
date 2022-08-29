---
title: 为教育分配 Microsoft Teams 许可证
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: 了解如何为Microsoft Teams 教育版分配许可证。
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom:
- admindeeplinkMAC
ms.openlocfilehash: e57780436167e3a872e78a717d12cd3acc35a6e9
ms.sourcegitcommit: c19ac3be42cc4b8409c8d512bbe3156736af0309
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/24/2022
ms.locfileid: "67426799"
---
# <a name="assign-microsoft-teams-licenses-for-education"></a>为教育分配 Microsoft Teams 许可证

本文面向需要向教职员工和学生分配团队许可证的教育版 IT 管理员。

若要让用户为 Teams 做好准备，需要：

1. [在Microsoft 365 管理中心中为学校启用 Microsoft Teams](/microsoft-365/education/intune-edu-trial/enable-microsoft-teams)。
2. 将许可证分配给用户帐户以访问 Microsoft 365 服务，包括 Teams。

## <a name="ways-to-assign-teams-licenses"></a>分配 Teams 许可证的方法

可以向用户帐户分配许可证：

- 单独或向Microsoft 365 管理中心中的一小组用户。
- 使用 [基于 PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell) 或 [Active Directory 组的许可](/azure/active-directory/users-groups-roles/licensing-groups-assign)自动通过组成员身份。

本文介绍如何在Microsoft 365 管理中心中分配许可证。

在Microsoft 365 管理中心中，可以向用户分配以下任一许可证：

- 要将产品许可证分配给特定用户的 **“许可证** ”页。
- 用于向特定产品分配用户许可证的 **“活动用户** ”页面。

> [!NOTE]
> 你必须是全局管理员、账单管理员、许可证管理员或用户管理管理员。有关详细信息，请参阅[关于 Office 365 管理员角色](/microsoft-365/admin/add-users/about-admin-roles)。

## <a name="assign-licenses-to-users-on-the-licenses-page"></a>在“许可证”页面上向用户分配许可证

在 **“许可证”** 页上，你将看到订阅的所有产品的列表、每个产品的许可证总数、分配的许可证数以及可用的许可证数。

1. 在 [管理中心](https://go.microsoft.com/fwlink/p/?linkid=2024339)，转到“**计** > 费 [许可证”](https://go.microsoft.com/fwlink/p/?linkid=842264)页。

2. 选择要为其分配许可证的产品。 Microsoft Teams 是学生 SKU 免费Microsoft 365 A1的一部分。

3. 选择“**分配许可证**”。

4. 在“**向用户分配许可证**”窗格中，开始键入名称，该名称应生成一个名称列表。

5. 从结果中选择要查找的名称，以将其添加到列表中。 一次最多可添加 20 名用户。

6. 选择“**打开或关闭应用和服务**”，向特定项目（例如 Microsoft Teams）分配访问权限或删除其访问权限。 请确保已选中 **Microsoft Teams** 和 **Office 网页版（教育版）**。

7. 完成后，选择“**分配**”，然后选择“**关闭**”。

### <a name="change-the-apps-and-services-a-user-has-access-to"></a>更改用户有权访问的应用和服务

1. 选择包含该用户的行。

2. 在右侧窗格中，选择或取消选择要授予或取消访问权限的应用和服务。

3. 完成后，选择“**保存**”，然后选择“**关闭**”。

## <a name="assign-licenses-to-users-on-the-active-users-page"></a>在“活动用户”页上向用户分配许可证

1. 在 [管理中心](https://go.microsoft.com/fwlink/p/?linkid=2024339)，转到 **“用户** > [活动用户](https://go.microsoft.com/fwlink/p/?linkid=834822) ”页面。

2. 选中要向其分配许可证的用户姓名旁边的圆圈。

3. 在顶部，选择 **“管理产品许可证**”。

4. 在“**管理产品许可证**”窗格中，选择“**添加到现有产品许可证分配**” > “**下一步**”。

5. 在“**添加到现有产品**”窗格中，将希望所选用户具备的许可证的开关切换到“**开**”位置。 请确保已选中 **Microsoft Teams** 和 **Office 网页版（教育版）**。

   默认情况下，与这些许可证关联的所有服务都将自动分配给该用户。 可限制能提供给用户的具体服务。 将不希望所选用户具备的服务的开关切换到“**关**”。

6. 在窗格底部，选择 **“添加** > **关闭**”。
