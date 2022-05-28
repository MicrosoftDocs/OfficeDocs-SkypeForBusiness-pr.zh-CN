---
title: 为 Teams 会议室 配置 ServiceNow
author: dstrome
ms.author: dstrome
manager: serdars
ms.reviewer: ''
ms.topic: article
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: 了解如何在 Teams 会议室 高级版 门户中配置 ServiceNow
f1keywords: ''
ms.openlocfilehash: c11a4e3cf4f128c8043ad2451f7d0a7a2ffe1c2e
ms.sourcegitcommit: 726df9ecac561bda18e349a5adab9bc85e52844d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2022
ms.locfileid: "65761494"
---
# <a name="configure-servicenow-for-teams-rooms"></a>为 Teams 会议室 配置 ServiceNow

本文介绍在Teams 会议室 高级版门户中配置 ServiceNow 环境的先决条件和步骤。

## <a name="before-you-begin"></a>开始之前

### <a name="teams-rooms-prerequisites"></a>Teams 会议室先决条件

- 必须具有分配的服务管理员角色。 有关详细信息，请参阅[Microsoft Teams 会议室托管服务的基于角色的访问控制](microsoft-teams-rooms-premium-rbac.md)。

### <a name="servicenow-prerequisites"></a>ServiceNow 先决条件

- 基本授权登录或 [OAuth](https://docs.servicenow.com/bundle/rome-platform-administration/page/administer/security/concept/c_OAuthApplications.html) 登录。 有关详细信息，请参阅在 ServiceNow 中 [创建凭据](https://developer.servicenow.com/dev.do#!/learn/learning-plans/rome/servicenow_application_developer/app_store_learnv2_rest_rome_creating_credentials) 。
- ServiceNow 实例及其实例主机名和 API URI
- incident_manager或更高版本的角色
- 支持表 API的 ServiceNow 软件版本

## <a name="configure-your-environment"></a>配置环境

如何配置环境是高度可自定义的，将取决于组织的需求。 以下步骤介绍如何将 ServiceNow 中的现有配置复制到Teams 会议室 高级版门户。

1. 打开要复制的 ServiceNow 实例。 在Teams 会议室 高级版门户中完成配置表单时，需要引用此信息。
2. 在新的浏览器选项卡中，转到 [Teams 会议室 高级版门户](https://portal.rooms.microsoft.com/)并转到 **设置**。 然后，在左侧导航菜单中选择 **ServiceNow** 以打开配置窗体。
3. 选择要登录的身份验证方法并输入 ServiceNow 实例主机和 API URI。
4. 应预先填充字段映射部分的 ServiceNow 字段列中的所有必需项。 下表包含每个 ServiceNow 字段及其相应的Microsoft Teams 会议室字段。 完成字段映射部分的每一行的操作。 有关每个 ServiceNow 字段的定义，请参阅 [ServiceNow 字段定义](#servicenow-field-definitions)。

| ServiceNow 字段 | Microsoft Teams 会议室字段 | 操作 |
| --- | --- | --- |
| short_description | 事件说明 | 无需执行任何操作。 Teams 会议室字段自动填充。 |
| 描述 | 第一条消息 | 无需执行任何操作。 Teams 会议室字段自动填充。 |
| assignment_group | 会议室组 | 复制 ServiceNow 实例中的assignment_group值并将其粘贴到配置窗体中的 ServiceNow 值字段中。 如果有多个assignment_group，请为每个附加的自定义值选择 **“添加会议室组** ”。 |
| 严重性 | 环 | 严重性是 ServiceNow 中的自定义值。 这是 ServiceNow 实例第二列中的第四项。 复制该值并将其粘贴到配置窗体中的 ServiceNow 值字段中。 如果有多个严重性值，请为每个附加的自定义值选择 **“添加环** ”。 |
| 注释 (可选)  | 自定义值* | 若要将注释字段添加到配置窗体，请选择“在字段映射部分顶部 **添加** ”。 复制 ServiceNow 实例中的注释值，并将其粘贴到配置窗体中的 ServiceNow 字段。 从下拉菜单中为它分配一个Microsoft Teams会议室字段，然后复制并粘贴 ServiceNow 值。 |
| 状态 (解析)  | 自定义值* | 从 ServiceNow 实例复制解析状态，并将其粘贴到配置窗体中的 ServiceNow 值字段中。 |
| close_code | 自定义值* | 在 ServiceNow 实例的“ **解决信息”** 选项卡中，复制关闭代码并将其粘贴到 ServiceNow 值字段中，并将其粘贴到配置窗体中。 |

*从下拉菜单中选择自定义值

>[!NOTE]
>如果找不到自定义值，请联系 ServiceNow 管理员。

若要添加其他必需字段以解决事件部分，请选择 **“添加**”。

## <a name="test-and-enable"></a>测试并启用

完成配置表单后，选择页面底部的 **“测试** ”。 提交配置需要测试。

测试成功通过后，选择 **“提交** ”以保存所做的更改。 准备好为组织启用 ServiceNow 后，请切换 **“是否启用 ServiceNow？** ”切换到 **“打开**”。

## <a name="servicenow-field-definitions"></a>ServiceNow 字段定义

- **short_description**：ServiceNow 中的简短说明字段是一个 160 个字符的简短字母数字值，提供事件摘要。 简短说明等效于Teams 会议室 高级版门户中的事件说明。

- **说明**：ServiceNow 中的说明字段是 ServiceNow 事件的会话历史记录中的第一个值。 说明等效于Teams 会议室 高级版门户中的第一条消息。

- **assignment_group**：ServiceNow 中的分配组字段用于组织事件。 分配组等效于Teams 会议室 高级版门户中的会议室组。 默认情况下，有一个会议室组，可以添加更多。 你决定有多少组以及如何对事件进行分组。 例如，可以选择按位置组织事件。

- **严重性**：ServiceNow 中的严重性字段用于按优先级组织事件。 指定优先级的值是可自定义的。 严重性等效于Teams 会议室 高级版门户中的 Ring 字段。 若要在Teams 会议室 高级版门户中自定义环，请转到左侧导航菜单中的 **“更新**”。 然后转到 **“指环”** 选项卡，然后选择 **“添加戒指**”。

- **注释**：注释是 ServiceNow 中的可选字段，用于在Teams 会议室 高级版门户配置中包含 ServiceNow 实例中的自定义必需字段。 等效的注释是Teams 会议室 高级版门户中的自定义值。

- **状态 (解决)**：ServiceNow 中) 字段 (解决的状态用于指定事件的解决方式，需要关闭事件。  (解析的状态) 值是可自定义的。 状态 (解析) 等效于Teams 会议室 高级版门户中的自定义值。

- **close_code**：完全解析后，必须为事件分配关闭代码。 此值可在 ServiceNow 中自定义。 关闭代码的等效值是Teams 会议室 高级版门户中的自定义值。
