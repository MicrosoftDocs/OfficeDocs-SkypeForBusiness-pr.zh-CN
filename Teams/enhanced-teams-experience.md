---
title: Microsoft Teams 高级版 - 管理员概述
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: ''
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-meetings
- highpri
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.custom:
- Licensing
description: 了解面向管理员和 IT 专业人员的Microsoft Teams 高级版。
ms.openlocfilehash: 2abcdd1c9f9df0101bbf7d0e22720c71375728d0
ms.sourcegitcommit: ca4d1011f3d62af203145431f0b19065ad81601b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2023
ms.locfileid: "69800286"
---
# <a name="microsoft-teams-premium---overview-for-administrators"></a>Microsoft Teams 高级版 - 管理员概述

![信息图标](media/info.png) **本文中所述的大多数功能都需要Teams 高级版，这是预览版。** 一些功能（例如，某些网络研讨会功能）也可用于其他许可证。 有关功能可用性和许可的详细信息，请参阅[Teams 高级版许可](teams-add-on-licensing/licensing-enhance-teams.md)。

本文面向将部署和配置Teams 高级版功能的 IT 专业人员和管理员。 本文简要介绍了这些功能，并提供了指向更详细文档的链接。

Teams 高级版是一个附加许可证，可为 Teams 提供以下增强功能：  

-   为最终用户提供增强的会议体验
-   增强会议安全性和保护 
-   增强的管理和遥测支持


> [!IMPORTANT]
> 由于 Teams 高级版 是公共预览版，因此在正式版中，Teams 当前提供的某些功能只能通过Teams 高级版许可证提供。 

以下部分介绍以下Teams 高级版增强功能：

- [受保护的会议](#protected-meetings)
- [自定义会议](#custom-meetings)
- [高级事件](#premium-events)
- [虚拟约会](#advanced-virtual-appointments)

> [!Note]
>我们将继续更新本文。 请经常回来查看指向新内容的链接。

## <a name="protected-meetings"></a>受保护的会议

Teams 高级版提供了保护会议的其他方法，具有以下关键功能： 

- **敏感度标签** - 敏感度标签的扩展功能，用于控制通常由会议组织者控制的会议设置。 这些功能包括用于控制大厅、聊天、聊天复制、演示和录制功能的新设置。

- **水印** - 通过敏感度标签强制实施。 水印显示会议参与者的电子邮件地址，这对于保护会议中共享的机密信息非常有用。 

- **端到端加密** - 通过敏感度标签强制实施。 端到端加密为需要更高级别保护的会议提供了更高的安全性。


| 功能/任务  | 面向管理员的文档 | 面向最终用户的文档
| -------------------- | ----------- | ------------ |
| 敏感度标签 | [使用三层保护配置 Teams 会议](configure-meetings-three-tiers-protection.md) | |
| 水印 | [会议需要水印](watermark-meeting-content-video.md) | [会议水印](https://support.microsoft.com/office/watermark-for-teams-meetings-a9166432-f429-4a19-9a72-c9e8fdf4f589)|
| 端到端加密 (E2EE)  | [敏感会议的加密](end-to-end-encrypted-meetings.md) | [使用加密](https://support.microsoft.com/office/use-end-to-end-encryption-for-teams-meetings-a8326d15-d187-49c4-ac99-14c17dbd617c)  |
| 模板、标签和策略 | [模板、敏感度标签和策略](meeting-templates-sensitivity-labels-policies.md)  | [使用自定义模板](https://support.microsoft.com/office/use-custom-templates-for-teams-meetings-78279be9-3283-4999-b24e-96fb0da2fb4f) |
| 限制可以录制的人员 | [管理敏感会议的录制内容](manage-meeting-recording-options.md) | [录制会议](https://support.microsoft.com/office/record-a-meeting-in-teams-34dfbe7f-b07d-4a27-b4c6-de62f1348c24?storagetype=stage#bkmk_whocanstartorstoparecording) |


## <a name="custom-meetings"></a>自定义会议

Teams 高级版提供了以下用于自定义会议的其他功能：

- **会议模板** - 用于控制会议组织者通常控制的会议设置。 使用模板，可以在组织中创建一致的会议体验，并帮助强制实施合规性要求和业务规则。

- **会议主题** - 允许组织在整个会议体验中扩展其视觉标识。 可以为单个租户中的各种业务部门和部门设置和创建会议主题。

- **组织的自定义会议背景** - 可以创建和定义自定义会议背景，然后可以使用Teams 高级版许可证提供给最终用户。

- **为组织自定义一起模式场景** - 你可以为会议创建、自定义或接受自定义的一起模式场景，然后可以使用Teams 高级版许可证提供给最终用户。


| 功能/任务 | 面向管理员的文档 | 面向最终用户的文档
| -------------------- | ----------- | ------------ |
| 会议模板 | - [概述](custom-meeting-templates-overview.md)<br>- [创建自定义会议模板](create-custom-meeting-template.md)| [使用自定义模板](https://support.microsoft.com/office/use-custom-templates-for-teams-meetings-78279be9-3283-4999-b24e-96fb0da2fb4f)
| 会议主题 | [Teams 会议的主题](meeting-themes.md) | [使用会议主题](https://support.microsoft.com/office/use-meeting-themes-for-teams-meetings-fbfd826d-1112-4790-918a-5a82cac8250e) |
| 组织的自定义会议背景 | [会议背景](custom-meeting-backgrounds.md)| |
| 组织的自定义联合模式场景 | [面向你和开发人员的内容](/microsoftteams/platform/apps-in-teams-meetings/teams-together-mode)| |





## <a name="premium-events"></a>高级事件

Teams 高级版使用新的 Teams 事件策略为用户提供高级网络研讨会体验。 新策略在继续支持注册和跟踪的同时，还将为会议主持人和组织者提供功能，例如：

- **条款和条件自定义问题** - 向与会者演示。
- **演示者简介** - 包含有关演示者的信息。
- **横幅、徽标和预定义颜色** - 提供自定义的可视化网络研讨会体验。
- **高级注册功能** - 包括手动审批、等待列表、注册日期和时间限制。
- **注册概述和管理** - 对于每个事件，都会提供注册状态摘要，其中包含处于不同注册状态的与会者列表，具体取决于已启用哪些注册功能。


| 功能/任务 | 面向管理员的文档 | 面向最终用户的文档
| -------------------- | ----------- | ----------- |
| 了解会议、网络研讨会和实时事件 | [快速启动](quick-start-meetings-live-events.md) | |
| 设置网络研讨会 | [设置网络研讨会](set-up-webinars.md) | - [管理网络研讨会注册](https://support.microsoft.com/office/manage-webinar-registration-923f382a-0cca-433a-b38d-7461971192d1) <br> - [管理与会者看到的内容](https://support.microsoft.com/office/manage-what-attendees-see-in-teams-meetings-19bfd690-8122-49f4-bc04-c2c5f69b4e16)|
| 网络研讨会的会议策略 | [会议策略](meeting-policies-in-teams-general.md) | |




## <a name="advanced-virtual-appointments"></a>高级虚拟约会

借助任何 Microsoft 365 许可证，最终用户可以使用基本虚拟约会功能来安排和加入企业到客户的会议。 例如，用户可以在 Bookings 日历中安排约会，外部与会者可以通过浏览器加入，而无需下载 Teams。 

Teams 高级版提供高级虚拟约会功能，例如：

- 短信通知
- 自定义候诊室
- 计划约会和按需约会的队列
- 分析

| 功能/任务  | 面向管理员的文档 | 
| -------------------- | ----------- | 
| 短信通知  | [短信通知](bookings-app-admin.md#sms-text-notifications) | 
| 报告 | [虚拟约会使用情况报告](/microsoft-365/frontline/virtual-appointments-usage-report?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json)<br>[高级虚拟约会活动报告](/microsoft-365/frontline/advanced-virtual-appointments-activity-report?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json) | 



## <a name="additional-resources"></a>其他资源

可在此处找到其他资源：

- [Microsoft Teams 高级版产品网站](https://www.microsoft.com/microsoft-teams/premium)
- [Microsoft Teams 高级版博客](https://www.microsoft.com/microsoft-365/blog/2022/10/12/introducing-microsoft-teams-premium-the-better-way-to-meet/)



