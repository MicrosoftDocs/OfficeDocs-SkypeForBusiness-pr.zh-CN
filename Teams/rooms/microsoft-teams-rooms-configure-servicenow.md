---
title: 为Teams 会议室配置 ServiceNow
author: altsou
ms.author: altsou
manager: serdars
ms.reviewer: altsou
ms.topic: article
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: 了解如何在Teams 会议室专业版管理门户中配置 ServiceNow
f1keywords: ''
ms.collection:
- M365-collaboration
- Teams_ITAdmin_MTRP
ms.openlocfilehash: 2166332df2c4ea388256d32a9dbc35a709042041
ms.sourcegitcommit: baf29d244b428712052553f9e4484e72e727247e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/17/2022
ms.locfileid: "69046851"
---
# <a name="configure-servicenow-for-teams-rooms"></a>为Teams 会议室配置 ServiceNow

本文介绍在 Teams 会议室专业版 管理门户中配置 ServiceNow 环境的先决条件和步骤。

## <a name="watch-microsoft-teams-rooms-pro-management--service-now-integration"></a>观看：Microsoft Teams 会议室专业版管理 — 立即服务集成

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4ZK4B]


### <a name="teams-rooms-prerequisites"></a>Teams 会议室先决条件

- 必须具有分配的服务管理员角色。 有关详细信息，请参阅[使用 Microsoft Teams 会议室专业版 Management 进行基于角色的访问控制](rooms-pro-rbac.md)。

### <a name="servicenow-prerequisites"></a>ServiceNow 先决条件

- 基本授权登录或 [OAuth](https://docs.servicenow.com/bundle/rome-platform-administration/page/administer/security/concept/c_OAuthApplications.html) 登录。 有关详细信息，请参阅在 ServiceNow [中创建凭据](https://developer.servicenow.com/dev.do#!/learn/learning-plans/rome/servicenow_application_developer/app_store_learnv2_rest_rome_creating_credentials) 。
- ServiceNow 实例及其实例主机名和 API URI
- incident_manager 或更高版本的角色
- 支持表 API 的 ServiceNow 软件版本

## <a name="configure-your-environment"></a>配置环境

如何配置环境是高度可自定义的，将取决于组织的需求。 以下步骤逐步讲解如何将 ServiceNow 中的现有配置复制到 Teams 会议室专业版 管理门户。

1. 打开要复制的 ServiceNow 实例。 在Teams 会议室专业版管理门户中完成配置表单时，需要引用此项。
2. 在新的浏览器选项卡中，转到 [Teams 会议室专业版管理门户](https://portal.rooms.microsoft.com/)，然后转到 **“设置”。** 然后，在左侧导航菜单中选择“ **ServiceNow** ”，打开配置窗体。
3. 选择要登录的身份验证方法，并输入 ServiceNow 实例主机和 API URI。
4. “字段映射”部分的“ServiceNow 字段”列中的所有必需项都应预先填充。 下表包含每个 ServiceNow 字段及其相应的Microsoft Teams 会议室字段。 完成“字段映射”部分的每一行的操作。 有关每个 ServiceNow 字段的定义，请参阅 [ServiceNow 字段定义](#servicenow-field-definitions)。

| ServiceNow 字段 | Microsoft Teams 会议室字段 | 操作 |
| --- | --- | --- |
| short_description | 事件说明 | 无需执行任何操作。 自动填充Teams 会议室字段。 |
| 描述 | 第一条消息 | 无需执行任何操作。 自动填充Teams 会议室字段。 |
| assignment_group | 会议室组 | 复制 ServiceNow 实例中的assignment_group值，并将其粘贴到配置窗体中的 ServiceNow 值字段中。 如果有多个assignment_group，请为每个附加的自定义值选择 **“添加会议室组** ”。 |
| 严重性 | 环 | 严重性是 ServiceNow 中的自定义值。 它是 ServiceNow 实例的第二列中的第四项。 复制值并将其粘贴到配置窗体中的 ServiceNow 值字段中。 如果有多个严重性值，请为每个附加的自定义值选择 **“添加 Ring** ”。 |
| 注释 (可选)  | 自定义值* | 若要向配置窗体添加注释字段，请选择字段映射部分顶部的“ **添加** ”。 复制 ServiceNow 实例中的注释值，并将其粘贴到配置窗体中的 ServiceNow 字段。 从下拉菜单中为其分配 Microsoft Teams 会议室字段，然后复制并粘贴 ServiceNow 值。 |
| 已解决) 状态 ( | 自定义值* | 从 ServiceNow 实例复制解析状态，并将其粘贴到配置窗体中的 ServiceNow 值字段中。 |
| close_code | 自定义值* | 在 ServiceNow 实例的“ **解决方案信息** ”选项卡中，复制关闭代码并将其粘贴到配置窗体的 ServiceNow 值字段中。 |

*从下拉菜单中选择自定义值

>[!NOTE]
>如果找不到自定义值，请与 ServiceNow 管理员联系。

若要向“解决事件”部分添加其他必填字段，请选择“ **添加**”。

## <a name="test-and-enable"></a>测试和启用

完成配置表单后，选择页面底部的“ **测试** ”。 需要测试才能提交配置。

测试成功通过后，选择“ **提交** ”以保存更改。 准备好为组织启用 ServiceNow 后，请将“ **是否启用 ServiceNow？”** 切换为“ **打开**”。

## <a name="servicenow-field-definitions"></a>ServiceNow 字段定义

- **short_description**：ServiceNow 中的简短说明字段是一个简短的 160 个字符的字母数字值，用于提供事件摘要。 简短说明等效于Teams 会议室专业版管理门户中的事件说明。

- **description**：ServiceNow 中的说明字段是 ServiceNow 事件的会话历史记录中的第一个值。 说明等效于Teams 会议室专业版管理门户中的第一条消息。

- **assignment_group**：ServiceNow 中的“分配组”字段用于组织事件。 分配组等效于Teams 会议室专业版管理门户中的会议室组。 默认情况下，有一个会议室组，可以添加更多会议室组。 由你决定有多少组以及如何对事件进行分组。 例如，可以选择按位置组织事件。

- **严重性**：ServiceNow 中的严重性字段用于按优先级组织事件。 指定优先级的值可自定义。 严重性等效于Teams 会议室专业版管理门户中的 Ring 字段。 若要在Teams 会议室专业版管理门户中自定义环，请转到左侧导航菜单中的 **汇报**。 然后转到“ **Ring** ”选项卡，然后选择“ **添加戒指**”。

- **注释**：注释是 ServiceNow 中的可选字段，用于在 Teams 会议室专业版 管理门户配置中包含 ServiceNow 实例中的自定义必填字段。 注释的等效项是Teams 会议室专业版管理门户中的自定义值。

- **状态 (解决)**：ServiceNow 中已解决 (状态) 字段用于指定如何解决事件，并且是关闭事件所必需的。 可自定义) 值 (解析的状态。 解析 (状态的等效) 是Teams 会议室专业版管理门户中的自定义值。

- **close_code**：完全解决后，必须将关闭代码分配给事件。 此值可在 ServiceNow 中自定义。 关闭代码的等效项是Teams 会议室专业版管理门户中的自定义值。
