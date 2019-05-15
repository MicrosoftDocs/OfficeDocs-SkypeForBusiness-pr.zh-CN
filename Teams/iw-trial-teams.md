---
title: 管理 Microsoft Teams Commercial Cloud Trial 产品
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 04/23/2019
ms.topic: reference
audience: Admin
ms.reviewer: annikaelias
ms.service: msteams
search.appverid: MET150
localization_priority: Priority
description: 未获得 Microsoft Teams 许可的 Office 365 用户可以启动 Teams 的 1 年期试用版。
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 654db34de9160c0e858fd8972d00487291fd1653
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33921249"
---
<a name="manage-the-microsoft-teams-commercial-cloud-trial-offer"></a>管理 Microsoft Teams Commercial Cloud Trial 产品
=======================================================

Microsoft Teams 是组织的一个很好的协作工具。 它使人们和团队能够使用 Office 365 的强大功能进行讨论、创新和共享创意。 Microsoft Teams Commercial Cloud Trial 为组织中未获得 Microsoft Teams 许可的现有 Office 365 用户提供该产品的 1 年期试用版。 管理员可以为组织中的用户打开或关闭此功能。

> [!IMPORTANT]
> Microsoft Teams 商业云试用版已更新，现有额外的服务计划针对增加的 Teams 功能，并且现由你组织的账单管理员拥有和控制。这使得试用版更易管理并与所有其他 Microsoft 365 产品/服务相一致。 现有的 Teams 商业云试用版用户将迁移到新的计划。

## <a name="whats-in-the-offer"></a>此优惠的内容

此优惠中包含的服务计划有：

- Exchange Foundation
- Flow for Office 365 计划 1
- Forms
- Microsoft Planner
- Microsoft Teams（Teams1、Teams IW）
- Office Online
- PowerApps for Office 365 计划 1
- SharePoint Online Kiosk
- Stream
- Sway
- Whiteboard
- Yammer Enterprise 

该试用版为你的整个组织提供为期一年的试用版订阅。 该试用版使 500,000 个许可证可用于分配。 对于分配的每个许可，该试用版将分配 2 GB 的 SharePoint Online 存储容量。 

## <a name="who-is-eligible"></a>哪些人符合条件

必须允许用户注册应用和试用版（在 Microsoft 365 管理中心中）。 有关详细信息，请参阅本文后面的[管理试用版](#manage-the-trial)。 

没有 Office 365 许可证（包含 Teams）的用户可以启动 Microsoft Teams Commercial Cloud Trial 优惠。 例如，如果用户拥有 Office 365 商业版（不包括 Teams），则他们符合该试用版的条件。

## <a name="who-is-not-eligible"></a>哪些人不符合条件

如果你是联合合作伙伴客户，或者是 GCC、GCC High、DoD 或 EDU 客户，则你的组织没有资格使用该试用版。

如果你的组织不符合 Microsoft Teams Commercial Cloud Trial 优惠的条件，你将无法看到**让用户安装试用版应用和服务**的开关。

## <a name="how-users-sign-up-for-the-trial"></a>用户如何注册试用版

符合条件的用户可通过登录到 Teams ([teams.microsoft.com](https://teams.microsoft.com)) 注册。 他们将看到以下屏幕来开始试用版。 

![Teams IW 试用版开始页面的屏幕截图。](media/iw-trial-start-screen.png)

组织中的所有试用版共享相同的开始和结束日期，即第一个用户注册试用版的日期。 例如，如果用户 A 在 2019 年 1 月 25 日开始第一次试用，用户 B 在 2019 年 6 月 3 日开始试用，则两个用户的试用版都将于 2020 年 1 月 25 日到期。

## <a name="manage-the-trial"></a>管理试用版

按分配管理员所获取的任何其他订阅的方式分配试用版许可证。 有关详细信息，请参阅[在 Office 365 商业版中向用户分配许可证](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide)。 

此外，管理员可以禁用最终用户在其组织中申请试用版应用和服务的功能。 目前，本文中描述的试用版是此类别中唯一的试用版，但它将来可能适用于其他类似的程序。 

### <a name="prevent-users-from-installing-trial-apps-and-services"></a>阻止用户安装试用版应用和服务

你可以关闭用户安装试用版应用和服务的功能。

1. 从“[Microsoft 365 管理中心](https://portal.office.com/adminportal/home)”，转到“**设置**” > “**服务和外接程序**” > “**用户拥有的应用和服务**”。

    ![Office 365 管理中心中“服务和外接程序”页面的屏幕截图。](media/iw-trial-enable-1.png)

2. 关闭**让用户安装试用版应用和服务**。

    ![Office 365 管理中心中“用户拥有的应用和服务”页面的屏幕截图。](media/iw-trial-enable-2.png)


### <a name="manage-trial-availability-for-a-user-with-a-license-that-includes-teams"></a>为拥有包含 Teams 的许可证的用户管理试用版可用性

分配了包含 Teams 的许可证的用户不符合试用版的条件。 启用 Teams 服务计划时，用户可登录并使用 Teams。 如果禁用该服务计划，则用户无法登录，也不会为其显示试用版选项。

关闭对 Teams 的访问：

1. 在 Microsoft 365 管理中心中，选择“**用户**” > “**活动用户**”。

2. 选择用户姓名旁的框。

3. 在右侧的“**产品许可证**”行中，选择“**编辑**”。

4. 在“**产品许可证**”窗格中，将开关切换为“**关闭**”。

    ![Office 365 管理中心中的“产品许可证”页面的屏幕截图。](media/iw-trial-enable-3.png)

### <a name="manage-teams-availability-for-users-who-already-claimed-the-trial"></a>为已经申请试用版的用户管理 Teams 可用性

如果用户申请了 Teams 试用版许可证，则可以通过删除许可证或服务计划来删除它。

关闭试用版许可证：

1. 在 Microsoft 365 管理中心中，选择“**用户**” > “**活动用户**”。

2. 选择用户姓名旁的框。

3. 在右侧的“**产品许可证**”行中，选择“**编辑**”。

4. 在“**产品许可证**”窗格中，将开关切换为“**关闭**”。

    ![“产品许可证”窗格上的“Teams 试用版许可证”设置的屏幕截图](media/iW-trial-enable-4.png)
    
>[!Note]
>在组织中的首位用户注册试用版后，就会出现 Microsoft Teams 试用版切换开关。

### <a name="manage-teams-for-users-who-have-the-trial-license"></a>为拥有试用版许可证的用户管理 Teams

你可以管理拥有试用版许可证的用户，就像管理具有常规付费许可证的用户一样。 有关详细信息，请参阅[为你的组织管理 Microsoft Teams 设置](enable-features-office-365.md)。

### <a name="upgrade-users-from-the-trial-license"></a>从试用版许可证升级用户

要从试用版许可证升级用户，请执行以下操作：

1. 购买包含 Teams 的订阅。

2. 删除用户的 Teams 试用版订阅。

3. 分配新购买的许可证。

有关详细信息，请参阅[适用于 Microsoft Teams 的 Office 365 许可](Office-365-licensing.md)。

> [!NOTE]
> 如果试用版结束，而用户未立即升级到包含 Teams 的订阅，则不删除该用户数据。 该用户仍保留在 Azure Active Directory 中，且 Teams 中的所有数据都将保留。 一旦向该用户分配新的许可证来重新启用 Teams 功能，则所有内容仍将存在。 
