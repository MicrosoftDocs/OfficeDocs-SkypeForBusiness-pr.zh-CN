---
title: 配置 ServiceNow Teams 会议室
author: cazawideh
ms.author: czawideh
manager: serdars
ms.reviewer: ''
ms.topic: article
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: 了解如何在门户中Teams 会议室 高级版 ServiceNow
f1keywords: ''
ms.openlocfilehash: a8f1e43ca52ee9fa155115fb911f88221cb6fdd0
ms.sourcegitcommit: 9364f4fdf3dcd5ab6805360ff913d4e2e7ca9cfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2021
ms.locfileid: "59432704"
---
# <a name="configure-servicenow-for-teams-rooms"></a>配置 ServiceNow Teams 会议室

本文介绍在门户中配置 ServiceNow 环境的先决条件Teams 会议室 高级版步骤。

## <a name="before-you-begin"></a>开始之前

### <a name="teams-rooms-prerequisites"></a>Teams 会议室先决条件

- 必须分配有服务管理员角色。 有关详细信息，请参阅使用托管服务 进行基于角色[Microsoft Teams 会议室访问控制](microsoft-teams-rooms-premium-rbac.md)。

### <a name="servicenow-prerequisites"></a>ServiceNow 先决条件

- 基本授权登录或 OAuth 登录。 有关详细信息，请参阅 [在](https://developer.servicenow.com/dev.do#!/learn/learning-plans/rome/servicenow_application_developer/app_store_learnv2_rest_rome_creating_credentials) ServiceNow 中创建凭据。
- ServiceNow 实例及其实例主机名和 API URI
- 角色incident_manager或更高
- 支持表 API 的 ServiceNow 软件版本

## <a name="configure-your-environment"></a>配置环境

环境的配置方式可高度自定义，并且取决于组织的需求。 以下步骤将演练如何将 ServiceNow 中的现有配置复制到 Teams 会议室 高级版 门户。

1. 打开要复制的 ServiceNow 实例。 在门户中完成配置窗体时，需要引用Teams 会议室 高级版窗体。
2. 在新的浏览器选项卡中，转到 Teams 会议室 高级版 [门户](https://portal.rooms.microsoft.com/)**并转到** 设置。 然后，在 **左侧导航菜单中选择"ServiceNow"** 打开配置窗体。
3. 选择要登录的身份验证方法，并输入 ServiceNow 实例主机和 API URI。
4. 应预先填充"字段映射"部分"ServiceNow 字段"列中的所有必需项。 下表包含每个 ServiceNow 字段及其对应的Microsoft Teams 会议室字段。 为"字段映射"部分的每一行完成操作。 有关每个 ServiceNow 字段的定义，请参阅 [ServiceNow 字段定义](#servicenow-field-definitions)。

| ServiceNow 字段 | Microsoft Teams 会议室 字段 | Action |
| --- | --- | --- |
| short_description | 事件说明 | 无需任何操作。 "Teams 会议室字段是自动填充的。 |
| description | 第一条消息 | 无需任何操作。 "Teams 会议室字段是自动填充的。 |
| assignment_group | 会议室组 | 复制 serviceNow assignment_group中的值，并将其粘贴到配置窗体中的 ServiceNow 值字段中。 如果具有多个自定义assignment_group，请 **针对** 每个附加的自定义值选择"添加会议室组"。 |
| severity | 圆环 | 严重性是 ServiceNow 中的自定义值。 它是 ServiceNow 实例的第二列中的第四个项。 复制该值并将其粘贴到配置窗体中的 ServiceNow 值字段中。 如果具有多个严重性值，请针对每个附加的自定义 **值** 选择"添加环"。 |
| 批注 (可选)  | 自定义值* | 若要向配置窗体添加注释字段，请选择字段映射部分顶部的"添加"。 复制 ServiceNow 实例中的注释值，并将其粘贴到配置窗体中的 ServiceNow 字段。 从下拉菜单中Microsoft Teams"会议室"字段，然后复制并粘贴 ServiceNow 值。 |
| state (已)  | 自定义值* | 从 ServiceNow 实例复制解析状态，并将其粘贴到配置窗体中的 ServiceNow 值字段中。 |
| close_code | 自定义值* | 在ServiceNow 实例的"解析信息"选项卡中，复制关闭代码并将其粘贴到配置窗体的"ServiceNow 值"字段中。 |

*从下拉菜单中选择自定义值

>[!NOTE]
>如果找不到自定义值，请联系 ServiceNow 管理员。

若要将其他必填字段添加到"解决事件"部分，请选择"**添加"。**

## <a name="test-and-enable"></a>测试和启用

完成配置表单后，选择 **页面** 底部的"测试"。 需要测试才能提交配置。

测试成功通过后，选择 **"提交** "以保存更改。 准备好为组织启用 ServiceNow 后，将"是否要启用 **ServiceNow？"** 切换为"打开 **"。**

## <a name="servicenow-field-definitions"></a>ServiceNow 字段定义

- short_description：ServiceNow 中的简短说明字段是一个简短的 160 个字符的字母数字值，提供事件的摘要。 简短说明相当于门户中的事件Teams 会议室 高级版说明。

- **说明**：ServiceNow 中的 description 字段是 ServiceNow 事件的聊天历史记录中的第一个值。 说明相当于门户中第一Teams 会议室 高级版消息。

- assignment_group：ServiceNow 中的"分配组"域用于组织事件。 工作分配组等效于门户中的Teams 会议室 高级版组。 默认情况下，有一个聊天室组，可以添加更多组。 由你决定有多少个组以及如何对事件进行分组。 例如，可以选择按位置组织事件。

- **严重性**：ServiceNow 中的严重性字段用于按优先级组织事件。 指定优先级的值可自定义。 严重性相当于门户中"环"Teams 会议室 高级版字段。 若要在门户中Teams 会议室 高级版环，请转到 **左侧导航菜单中** 的"更新"。 然后转到"圈 **"** 选项卡并选择"**添加圈"。**

- **注释**：注释是 ServiceNow 中的可选字段，用于将 ServiceNow 实例中的自定义必填字段Teams 会议室 高级版门户配置中。 注释的等效项是门户门户中的Teams 会议室 高级版值。

- **state (已**) ：ServiceNow () 字段的状态，用于指定事件的解决方式，关闭事件需要此状态。 解析 (的状态) 可自定义。 解析后的状态 (是) 门户中的自定义Teams 会议室 高级版值。

- **close_code：** 完全解决事件后，必须为事件分配关闭代码。 此值在 ServiceNow 中可自定义。 关闭代码的等效项是门户门户中的Teams 会议室 高级版值。
