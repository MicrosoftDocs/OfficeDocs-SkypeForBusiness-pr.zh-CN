---
title: 管理 Microsoft Teams Commercial Cloud Trial 产品
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 12/10/2018
ms.topic: article
audience: Admin
ms.reviewer: annikaelias
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
description: Office 365 用户未授权的 Microsoft 团队可以发起 1 年试用版的团队。
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: dc0b62ce0be0606ad4c31d3cee04347729fbbe32
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "27214578"
---
<a name="manage-the-microsoft-teams-commercial-cloud-trial-offer"></a>管理 Microsoft Teams Commercial Cloud Trial 产品
=======================================================

Microsoft 团队是为您的组织的绝佳协作工具。 它使人和团队讨论、 创新和共享想法使用 Office 365 的能力。 Microsoft 团队商业云试用版提供了您的组织中未授权的 Microsoft 团队启动 1 年试用版的产品的现有 Office 365 用户。 管理员可以在组织中切换用户打开或关闭此功能。

## <a name="whats-in-the-offer"></a>什么是在优惠中

包含此服务的服务计划是：

- Exchange Foundation
- Flow for Office 365 计划 1
- Microsoft 计划程序
- Microsoft 团队 （Teams1、 团队 IW）
- Office Online
- Office 365 的 PowerApps 计划 1
- SharePoint Online Kiosk
- Sway
- Yammer Enterprise

试用授予对您的整个组织的一年试用订阅。 试用使 500000 许可证可用于工作分配。 对于每个分配的许可证，试用分配 2 GB 的 SharePoint Online 的存储空间。 

## <a name="who-is-eligible"></a>谁有资格参与

用户必须能够注册应用程序和试用 （英文） (Office 365 管理中心中）。 有关详细信息，请参阅本文后面的[管理试用版](#manage-the-trial)。 

没有包括团队的 Office 365 许可证的用户可以启动 Microsoft 团队商业云试用版。 例如，如果用户具有 Office 365 企业版 （其中不包括团队），它们是合格的试用版。

## <a name="who-is-not-eligible"></a>谁是不符合条件的

您的组织不符合试用 if 条件： 

- 您是联合合作伙伴客户
- 您是经销商合作伙伴客户
- 您是政府或 EDU 客户

如果您的组织的 Microsoft 团队商业云试用版不符合要求，您将不会看到**让用户安装试用版应用程序和服务**的开关。

## <a name="how-users-sign-up-for-the-trial"></a>如何用户注册试用版

合格的用户可以注册试用版通过登录到团队 ([teams.microsoft.com](https://teams.microsoft.com))。 他们将看到以下屏幕启动试用版。 

![团队 IW 试用版的起始页的屏幕截图。](media/iw-trial-start-screen.png)

组织内的所有 trials 都共享相同的开始和结束日期，即第一个用户已注册试用版的日期。 例如，如果用户 A 启动 2019 年 1 月 25，在第一个试用版，用户 B 启动试用版上 2019，年 6 月 3，这两个用户的试用版将上于 2020 年 1 月 25 日过期。

## <a name="manage-the-trial"></a>管理试用版

管理员可以管理的已注册的用户的许可证。 

此外，管理员可以禁用让最终用户声明试用版应用程序和服务其组织内的功能。 目前，本文中所述试用版是仅试用在此类别中，但它可能将来应用于其他类似的程序。 

### <a name="prevent-users-from-installing-trial-apps-and-services"></a>阻止用户安装试用版应用程序和服务

您可以关闭用户能够安装试用版应用程序和服务。

1. 从[Microsoft 365 管理中心](https://portal.office.com/adminportal/home)，转到**设置** > **服务和外接程序** > **用户拥有的应用程序和服务**。

    ![在 Office 365 管理中心中的服务和外接程序页的屏幕截图。](media/iw-trial-enable-1.png)

2. 关闭**让用户安装试用版应用程序和服务**。

    ![用户的屏幕截图拥有 Office 365 管理中心中的应用程序和服务页。](media/iw-trial-enable-2.png)


### <a name="manage-trial-availability-for-a-user-with-a-license-that-includes-teams"></a>试用的用户具有许可证，其中包括团队可用性进行管理

用户分配许可证，其中包括团队不适用于试用版。 启用团队服务计划后，用户可以登录，然后使用小组。 如果禁用服务计划，则用户无法登录，并将不显示试用选项也。

若要关闭向工作组的访问：

1. 在 Microsoft 365 管理中心中，选择**用户** > **活动用户**。

2. 选择用户名称旁边的框。

3. 在右侧，在**产品许可证**行中，选择**编辑**。

4. 在**产品许可证**窗格中，切换到**关闭**的切换。

    ![在 Office 365 管理中心中的产品许可证页的屏幕截图。](media/iw-trial-enable-3.png)

### <a name="manage-teams-availability-for-users-who-already-claimed-the-trial"></a>管理团队的已经占用了试用的用户的可用性

如果用户已声明团队试用许可证，您可以通过删除许可证或服务计划将其删除。

若要关闭试用许可证：

1. 在 Microsoft 365 管理中心中，选择**用户** > **活动用户**。

2. 选择用户名称旁边的框。

3. 在右侧，在**产品许可证**行中，选择**编辑**。

4. 在**产品许可证**窗格中，切换到**关闭**的切换。

    ![产品许可证窗格上的团队试用许可证设置的屏幕截图](media/iW-trial-enable-4.png)

### <a name="manage-teams-for-users-who-have-the-trial-license"></a>管理团队拥有试用许可证的用户 （英文）

您可以管理像管理拥有常规付费的许可证的用户具有使用试用许可证的用户。 有关详细信息，请参阅[Office 365 组织中的管理 Microsoft 团队 features](enable-features-office-365.md)。

### <a name="upgrade-users-from-the-trial-license"></a>用户从试用许可证升级

若要从试用版许可证升级用户，执行以下操作：

1. 购买订阅包含团队。

2. 删除用户团队试用订阅。

3. 分配新购买的许可证。

有关详细信息，请参阅[适用于 Microsoft Teams 的 Office 365 许可](Office-365-licensing.md)。