---
title: 管理组织的汇报应用
author: daisyfell
ms.author: daisyfeller
ms.reviewer: samanro
manager: pamgreen
ms.topic: how-to
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
description: 了解如何在 Teams 中为组织中的用户管理汇报应用。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- m365-frontline
- highpri
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: 214ae4f925f3a33e82fb4eac8186f02e0a65cbc2
ms.sourcegitcommit: e6182aa3b15346dc955333a2bc571565ef463a57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/28/2022
ms.locfileid: "68784417"
---
# <a name="manage-the-updates-app-for-your-organization-in-microsoft-teams"></a>在 Microsoft Teams 中管理组织的汇报应用

## <a name="what-is-the-updates-app"></a>什么是汇报应用

Microsoft Teams 应用中的汇报提供了一个集中位置，供组织成员创建、查看和提交更新。 通过创建模板，可以使用 汇报 应用跟踪组织所需的任何内容。 汇报适用于桌面和移动设备。

在 Teams 中，用户可以从 Teams 应用商店获取汇报。 他们将在“ **提交** ”页上看到需要提交的所有更新。 可以与用户共享[汇报入门一文](https://support.microsoft.com/office/get-started-in-updates-c03a079e-e660-42dc-817b-ca4cfd602e5a)，帮助他们熟悉使用汇报。

[![Teams 桌面版中的“提交”页面的图像。](media/updates-submit-small.png)](media/updates-submit.png#lightbox)

用户可以在 **“审阅** ”页中查看他们分配的更新。

[![Teams 桌面版中的“审阅”页的图像。](media/updates-home-small.png)](media/updates-home.png#lightbox)

向用户分配更新后，更新将显示在其 Teams 活动源中。 用户还可以在 汇报 应用中查看所有当前更新请求和以前的提交。 此外，任何人都可以创建模板并发送更新请求。

汇报附带适用于常见业务方案的现用模板和创建自己的模板的选项。 任何人都可以为新类型的更新创建模板。

## <a name="example-scenario"></a>应用场景示例

服装店的员工每天负责开店和关门。 每天早上，值班主管都会填写 Microsoft Store 开业更新，这是 汇报 应用中的现用模板。 在此更新中，他们描述了前一晚关闭的任何问题，回答有关商店清洁度的问题，并报告需要补充的任何用品。 提交更新可让他们快速高效地传达对应用商店的需求和任何问题。 每日更新也为商店员工提供了一个机会，以突出进展顺利。

在商店的制造工厂，员工使用移动设备对汇报进行安全检查。

![移动设备上每周安全演练模板的图像。](media/updates-mobile.png)

与此同时，一个远程工人团队正在更新商店的网站。 它们分布在多个时区，因此每天的站立会议不方便。 相反，每个团队成员每天向团队领导提交汇报进度报告。

[下载汇报 lookbook](https://go.microsoft.com/fwlink/?linkid=2197649)，查看有关汇报可以执行的操作的更多示例。

## <a name="required-permissions-and-licenses"></a>所需权限和许可证

需要以下项的权限才能部署汇报：

- 创建 Microsoft Dataverse 数据库的权限。

- [powerautomate.microsoft.com](https://powerautomate.microsoft.com/) 上的帐户。

- 目标环境中的管理员角色。

- Power Automate、Office 365或 Dynamics 365 许可证。

- 用户设置新模板需要Microsoft Forms许可证。

## <a name="storage-with-microsoft-dataverse"></a>使用 Microsoft Dataverse 存储

通用数据模型 (CDM) 是 Microsoft Dataverse 中的业务和分析应用程序使用的共享数据语言。 它由 Microsoft 和我们的合作伙伴发布的一组标准化、可扩展的数据架构组成，这些架构可实现跨应用程序和业务流程的数据及其含义的一致性。 详细了解 [通用数据模型](/common-data-model/)。

从模板创建的汇报仍将数据存储在 Microsoft Dataverse 中，例如标题、详细信息、模板 ID 等。 详细了解 [用于Microsoft Forms的数据存储](https://support.microsoft.com/office/data-storage-for-microsoft-forms-97a34e2e-98e1-4dc2-b6b4-7a8444cb1dc3#:~:text=Where%20data%20is%20stored%20for%20Microsoft%20Forms.%20Microsoft,European-based%20tenants%20is%20stored%20on%20servers%20in%20Europe)。

>[!Note]
>如果在 Microsoft Forms 网站上删除表单模板，则会中断汇报模板，并且用户无法提交更新。 用户在尝试打开已在 Microsoft Forms 上删除的模板时收到错误“CDB TableNotFound”。

## <a name="updates-teams-app-permissions"></a>汇报 Teams 应用权限

使用 汇报 Teams 应用可以访问以下功能：

- 接收你向其提供的消息和数据。

- 向你发送消息和通知。

- 呈现个人应用和对话框，但不显示 Teams 提供的标题。

- 访问你的个人资料信息，如姓名、电子邮件地址、公司名称和首选语言。

- 在频道中接收团队成员向其提供的消息和数据。

- 在频道中发送消息和通知。

- 访问团队的信息：
  - 团队名称
  - 频道列表
  - 花名册 (团队成员的姓名和电子邮件地址) 

- 使用团队的信息联系他们。

## <a name="disable-the-updates-app"></a>禁用汇报应用

默认情况下，汇报应用可用。 可在 Teams 管理中心中禁用该应用。

  1. 登录到 Teams 管理中心。

  2. 转到 “**Teams 应用**” > “**管理应用**”。

  3. 搜索汇报应用。

     [![管理员中心导航的屏幕截图，其中突出显示了 Teams 应用>管理应用。](media/manage-updates-small.png)](media/manage-updates.png#lightbox)

  4. 选择 **“汇报**”。

  5. 选择切换开关以为你的组织禁用该应用。
    ![用于启用或禁用汇报的切换的图像。](media/toggle-updates.png)

## <a name="pin-updates-to-teams"></a>将汇报固定到 Teams

应用设置策略允许自定义 Teams，以固定用户中最重要的应用。 应用固定到应用栏（Teams 桌面客户端一侧和 Teams 移动客户端底部的栏），用户可以快速轻松地访问应用栏。

若要为用户固定汇报应用，可以编辑全局 (组织范围的默认) 策略，或在应用设置策略中创建和分配自定义策略。 要了解详细信息，请参阅[在 Teams 中管理应用设置策略](teams-app-setup-policies.md)。

## <a name="retention-policy"></a>保留策略

从 汇报 应用创建的汇报存储在默认的 Microsoft Dataverse 环境中，目前不支持备份。 详细了解如何[备份和还原环境 - Power Platform\| Microsoft Docs](/power-platform/admin/backup-restore-environments)。

在模板创建者从Microsoft Forms Web 应用中的 **已删除表单** 选项卡中清理数据之前，不会删除存储在窗体中的数据。

## <a name="conditional-access-and-permission-policies"></a>条件访问和权限策略

Teams 中的汇报应用当前不支持为 Microsoft Teams 设置的条件访问策略。

可以使用 [Teams 应用权限策略](teams-app-permission-policies.md)来管理汇报。

## <a name="data-limitations"></a>数据限制

每个用户最多可以创建 400 个汇报模板，并且每个模板最多可以基于Microsoft Forms中的当前功能收集 50，000 个请求。

## <a name="security"></a>安全性

在 Teams 汇报 应用中，用户有权创建新更新并查看已发送和接收的更新。 用户无权访问其他人创建的汇报，除非他们是请求的查看者。

>[!Note]
> 如果用户是创建更新报告的聊天或频道的一部分，或者模板创建者手动将他们添加为查看者，则用户将获得请求的查看者角色。 如果在创建报表时未赋予该角色，则他们无法对请求执行操作。
