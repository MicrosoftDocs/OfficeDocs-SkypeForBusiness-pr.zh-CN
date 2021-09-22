---
title: 使用 Microsoft Teams Room 高级版 服务的基于角色的访问控制
author: dstrome
ms.author: dstrome
manager: serdars
ms.reviewer: altsou
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 了解使用托管服务进行基于角色Microsoft Teams 会议室控制。
f1keywords: ''
ms.openlocfilehash: 9b1a3a770c8b56c9d9ed3b589fa13163d955c294
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2021
ms.locfileid: "58728071"
---
# <a name="role-based-access-control-with-the-microsoft-teams-rooms-managed-service"></a>使用托管服务进行基于Microsoft Teams 会议室访问控制

使用托管服务 (RBAC) 基于角色Microsoft Teams 会议室可帮助管理用户对组织中会议室资源数据的访问权限。 通过向服务门户用户分配角色，可以限制他们可以看到和更改的内容。 每个角色都有一组权限，用于确定哪些具有该角色的用户可以在组织中访问和更改。

若要创建、编辑或分配角色，帐户必须具有以下权限之一：

- 通过 Azure AD Azure Active Directory (全局) 
- 通过托管服务门户Microsoft Teams 会议室托管服务管理员

## <a name="what-is-a-role"></a>什么是角色？

角色定义授予分配给该角色的用户的权限集。 目前，Microsoft Teams 会议室托管服务具有三个内置角色：托管服务管理员、**站点主管** 和 **站点技术**。  它们涵盖了组织中可能参与管理聊天室的用户的一些常见方案。

若要查看角色，请在 Microsoft Teams 会议室 服务门户的左侧导航栏中，转到"角色"，然后选择任一角色以查看角色的属性、权限和分配。  

- **属性**：名称、角色类型和说明
- **权限**：列出角色有权访问的功能和权限级别。
- **分配**：角色分配列表，定义哪些用户具有针对会议室资源帐户范围的已配置权限。 一个角色可以有多个分配，一个用户可以有多个分配。

## <a name="built-in-roles"></a>内置角色

无需进一步配置，即可将内置角色分配给组或用户。 请记住，不能删除或编辑内置角色的名称、说明、类型或权限。

- **托管服务管理员**：具有对 Microsoft Teams 高级版 服务门户的完全访问权限。
- **网站主管**：组织会议室、有权访问报表并可以管理票证。 无法重置注册密钥或更改服务的配置。  
- **网站技术**：管理特定房间的票证。 无权修改服务或组织服务中的聊天室。

下表汇总了每个角色可以执行哪些操作。

|功能 |权限 |托管服务管理员  |网站潜在顾客  |网站技术  |
|---------|---------|---------|---------|---------|
|会议室     |查看        |&#10004;           |&#10004;           |&#10004;  |
|    |修改         |&#10004;           |&#10004;           |&#10004; |
|    |重置密钥         |&#10004;           |         ||
|    |下载密钥         |&#10004;           |&#10004;          |&#10004; |
|    |取消注册         |&#10004;           |&#10004;           |&#10004; |
|组管理   |创建         |&#10004;           |           ||
|    |查看       |&#10004;          |&#10004;           ||
|    |修改         |&#10004;           |           ||
|更新环管理    |创建         |&#10004;           |           ||
|    |查看         |&#10004;           |           ||
|    |修改         |&#10004;           |           ||
|报表   |查看        |&#10004;           |&#10004;           ||
|票证管理   |创建客户事件         |&#10004;           |&#10004;           |&#10004;  |
|    |查看         |&#10004;           |&#10004;           |&#10004;  |
|    |更新         |&#10004;           |&#10004;           |&#10004;  |
|Microsoft Teams 会议室托管服务设置    |查看         |&#10004;           |         ||
|    |修改        |&#10004;           |         ||
|角色管理    |查看         |&#10004;           |         ||
|    |修改         |&#10004;           |         ||

## <a name="assign-a-role"></a>分配角色

若要分配角色，必须是全局管理员或托管服务管理员。

1. 在托管服务门户的Microsoft Teams 会议室导航中 **，转到"设置**  >  **角色"。**

    :::image type="content" source="../media/microsoft-teams-rooms-premium-roles.png" alt-text="显示角色的访问控制页面的屏幕截图。":::

2. 选择要分配的角色。
3. 在角色窗格中，选择"分配 **添加**  >  **"。**

    :::image type="content" source="../media/microsoft-teams-rooms-premium-role-assignments.png" alt-text="用于添加角色的添加选项的屏幕截图。":::

4. 在" **常规设置"** 页上的" **工作分配属性**"下，输入此作业的名称。 说明是可选的。 选择"下 **一步"。**
5. 在 **"成员**"页面上的"搜索用户或安全组"框中，输入要授予权限的租户中用户或安全组的名称，然后完成选择。 选择"下 **一步"。** 
6. 在 **"范围**"页面上的"搜索聊天室或会议室组"框中，键入允许用户管理的聊天室或聊天室组的名称。 选择"下 **一步"。**
7. 在" **完成** "页上，查看作业的详细信息。 如果对配置感到满意，请选择"添加 **分配"。** 如果要编辑分区，请使用"上一步" **按钮或** 选择左侧导航中的步骤。  

## <a name="related-topics"></a>相关主题

- [Microsoft Teams 会议室托管服务](microsoft-teams-rooms-premium.md)
