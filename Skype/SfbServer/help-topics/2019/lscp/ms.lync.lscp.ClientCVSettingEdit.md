---
title: 客户端版本配置创建新的或编辑现有的
ms.reviewer: ''
ms.author: SerdarS
author: SerdarSoysal
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 07fec57c-5cd3-422a-829a-0b62cb0092c4
ROBOTS: NOINDEX, NOFOLLOW
description: 客户端版本配置设置用于打开或关闭客户端版本控制。 全局客户端版本配置与 Skype 的业务服务器安装，并用于启用或禁用整个服务器部署的客户端版本控制。 当全局配置处于启用状态时，用户尝试登录后您所拥有的任何客户端版本策略都将生效。 如果不希望发生任何客户端版本控制，则可以禁用全局客户端版本配置。
ms.openlocfilehash: 3b91ca6b9c3d3f801a8a247eef5641673dc86556
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30883205"
---
# <a name="client-version-configuration-create-new-or-edit-existing"></a>客户端版本配置：创建新的或编辑现有的

客户端版本配置设置用于打开或关闭客户端版本控制。 全局客户端版本配置与 Skype 的业务服务器安装，并用于启用或禁用整个服务器部署的客户端版本控制。 当全局配置处于启用状态时，用户尝试登录后您所拥有的任何客户端版本策略都将生效。 如果不希望发生任何客户端版本控制，则可以禁用全局客户端版本配置。

也可以创建站点特定的客户端版本配置，这样您可以按网站来启用或禁用客户端版本控制。站点特定的配置优先于全局配置。

## <a name="tasks-you-can-perform"></a>可执行的任务

您可以在“**新建客户端版本配置**”或“**编辑客户端版本配置**”页上执行以下任务：

- 添加或修改客户端版本配置的名称。

- 启用或禁用全局或某特定站点的客户端版本控制。

- 添加或修改客户端版本配置的默认操作。

## <a name="ui-reference"></a>用户界面参考

下表介绍了该页上的菜单、命令、字段和属性。

- **范围**标识客户端版本配置的范围 （全局或站点）。

- **名称**您可以添加或修改客户端版本配置的名称。

- **启用版本控制**您可以启用或禁用全局或站点，具体取决于配置的范围的客户端版本控制。

- **默认操作**您可以选择当用户尝试登录使用客户端应用程序没有任何特定客户端版本策略将应用默认操作。 您具有以下选项：

  - **允许**允许客户端登录，如果客户端版本不匹配客户端版本策略列表中的任何筛选器。

  - **阻止**阻止客户端登录，如果客户端版本不匹配客户端版本策略列表中的任何筛选器。

  - **使用 URL 阻止**阻止客户端登录，如果客户端版本不匹配客户端版本策略列表中的任何筛选器，并包括包含的 URL，可以下载更新的客户端一条错误消息。

  - **使用 URL 允许**允许客户端登录，如果客户端版本不匹配客户端版本策略列表中的任何筛选器，并包括包含 URL 的错误消息，可以下载更新的客户端。

  - **URL**如果选择了**使用 URL 阻止**或**使用 URL 允许**，则可以指定要包含在错误消息的客户端下载 URL。

有关客户端和客户端版本之间的互操作性的详细信息，请参阅规划文档中的[客户端互操作性](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx)。 有关使用客户端版本配置的详细信息，请参阅操作文档中的[Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx)。

