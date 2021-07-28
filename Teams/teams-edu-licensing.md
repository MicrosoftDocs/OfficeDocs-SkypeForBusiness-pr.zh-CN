---
title: 教育版管理员的 Microsoft Teams 资源：为 EDU 分配 Teams 许可证
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: Microsoft Teams 教育版许可演练。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
appliesto:
- Microsoft Teams
ms.openlocfilehash: e51d472bbf3310b03fea6344b354fc307c8ce08a
ms.sourcegitcommit: b387296c043fcf10fba7b9ef416328383e54a565
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/26/2021
ms.locfileid: "53587371"
---
# <a name="assign-microsoft-teams-licenses-for-edu"></a>为教育版分配 Microsoft Teams 许可证

Microsoft Teams 是一个数字中心，其中汇聚了对话、内容及应用。 由于它是基于 Office 365 构建的，因此学校可以从与他们熟悉的 Office 应用和服务的集成中受益。 你的机构可以使用 Microsoft Teams 创建协作式教室、连接专业学校社区并与学校教职员工进行沟通 - 一切皆可通过 Office 365 教育版中的单一体验来实现。

首先，IT 管理员需要使用 Microsoft 365 管理中心[为你的学校启用 Microsoft Teams](/microsoft-365/education/intune-edu-trial/enable-microsoft-teams)。
完成后，你必须为用户帐户分配许可证，以便你的教职员工和学生可以访问 Office 365 服务，例如 Microsoft Teams。

可通过组成员身份单独或自动向用户帐户分配许可证。 本文将向你介绍如何通过 Microsoft 365 管理中心将 Office 365 许可证分配给单个或一小组用户帐户。 要通过组成员身份自动分配许可证，请参阅我们的以下支持文章之一：

- [Office 365 Powershell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)
- [Active Directory 中基于组的许可](/azure/active-directory/users-groups-roles/licensing-groups-assign)

可在“**许可证**”页面或“**活动用户**”页面上向用户分配许可证。 使用哪种方法取决于是要向特定用户分配产品许可证还是向特定产品分配用户许可证。

> [!NOTE]
> 如果未使用新的 Microsoft 365 管理中心，可通过选择“**试用新的管理中心**”切换按钮（位于主页顶部）将其打开。

## <a name="assign-licenses-to-users-on-the-licenses-page"></a>在“许可证”页面上向用户分配许可证

> [!NOTE]
> 你必须是全局管理员、账单管理员、许可证管理员或用户管理管理员。有关详细信息，请参阅[关于 Office 365 管理员角色](/microsoft-365/admin/add-users/about-admin-roles)。

使用“**许可证**”页面分配许可证时，最多可向 20 名用户分配特定产品的许可证。 在“**许可证**”页面上，你会看到你已订阅的所有产品的列表，还有每个产品的许可证总数、已分配的许可证数以及可用的许可证数。

1. 在管理中心，转到“**账单**” > “[许可证](https://go.microsoft.com/fwlink/p/?linkid=842264)”页面。

   ![账单窗口和菜单选项的屏幕截图。](media/EDU-Lic-Billing-License.png)
2. 选择要为其分配许可证的产品。 Microsoft Teams 是免费的 Office 365 A1 学生版 SKU 的一部分。

   ![“许可证”页面屏幕截图，其中包含可用于为其分配许可证的产品。](media/EDU-Lic-Licenses-Products.png)
3. 选择“**分配许可证**”。

   ![页面的“用户”部分以及前面带有加号的“分配许可证”选项的屏幕截图。](media/EDU-Lic-Assign-Licenses.png)
4. 在“**向用户分配许可证**”窗格中，开始键入名称，该名称应生成一个名称列表。 从结果中选择要查找的名称，以将其添加到列表中。 一次最多可添加 20 名用户。

   ![“向用户分配许可证”页面的屏幕截图，其中键入了部分名称，显示了该部分名称的搜索结果。](media/EDU-Lic-Assign-Licenses-Users.png)
5. 选择“**打开或关闭应用和服务**”，向特定项目（例如 Microsoft Teams）分配访问权限或删除其访问权限。 请确保已选中 **Microsoft Teams** 和 **Office 网页版（教育版）**。
6. 完成后，选择“**分配**”，然后选择“**关闭**”。

要更改应用和服务，用户需有权限：

1. 选择包含该用户的行。
1. 在右侧窗格中，选择或取消选择要授予或取消访问权限的应用和服务。
1. 完成后，选择“**保存**”，然后选择“**关闭**”。

## <a name="assign-licenses-to-an-individual-or-multiple-users-on-the-active-users-page"></a>在“活动用户”页面上向单个或多个用户分配许可证

1. 在管理中心，转到“**用户**” > “[活动用户](https://go.microsoft.com/fwlink/p/?linkid=834822)”页面。

   ![Microsoft O365 管理中心中“活动用户”菜单选项的屏幕截图。](media/EDU-Lic-Active-Users.png)
2. 选中要向其分配许可证的用户姓名旁边的圆圈。

   ![“活动用户”页面以及该页面上活动用户列表（其中一些用户被选中，因为其姓名旁边的圆圈被填充）的屏幕截图。](media/EDU-Lic-Active-Users-List.png)
3. 在顶部，选择“**管理产品许可证**”。

   ![“管理产品许可证”选项卡以及一个以未经许可列出的用户的屏幕截图。](media/EDU-Lic-Manage-Product-Licenses.png)
4. 在“**管理产品许可证**”窗格中，选择“**添加到现有产品许可证分配**” > “**下一步**”。

   ![“管理产品许可证”窗口的屏幕截图，其中选中了“添加到现有产品许可证分配”单选按钮。](media/EDU-Lic-Add-Existing-Product.png)
5. 在“**添加到现有产品**”窗格中，将希望所选用户具备的许可证的开关切换到“**开**”位置。 请确保已选中 **Microsoft Teams** 和 **Office 网页版（教育版）**。

   ![在“添加到现有产品”选项卡上选中 Microsoft Teams 和 Office 网页版（教育版）的屏幕截图。](media/EDU-Lic-Add-Existing-Products.png)

   默认情况下，与这些许可证关联的所有服务都将自动分配给该用户。 可限制能提供给用户的具体服务。 将不希望所选用户具备的服务的开关切换到“**关**”。
6. 在窗格底部，选择“添加”>“关闭”。