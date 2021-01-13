---
title: 客户端版本配置创建新的或编辑现有的
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientCVSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 07fec57c-5cd3-422a-829a-0b62cb0092c4
description: 客户端版本配置设置用于打开或关闭客户端版本控制。 全局客户端版本配置随 Skype for Business Server 一起安装，用于启用或禁用整个服务器部署的客户端版本控制。 当全局配置处于启用状态时，用户尝试登录后您所拥有的任何客户端版本策略都将生效。 如果不希望发生任何客户端版本控制，则可以禁用全局客户端版本配置。
ms.openlocfilehash: 5567a4de26d29413c049126b90c907383916d71c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800502"
---
# <a name="client-version-configuration-create-new-or-edit-existing"></a>客户端版本配置：创建新的或编辑现有的

客户端版本配置设置用于打开或关闭客户端版本控制。 全局客户端版本配置随 Skype for Business Server 一起安装，用于启用或禁用整个服务器部署的客户端版本控制。 当全局配置处于启用状态时，用户尝试登录后您所拥有的任何客户端版本策略都将生效。 如果不希望发生任何客户端版本控制，则可以禁用全局客户端版本配置。

也可以创建站点特定的客户端版本配置，这样您可以按网站来启用或禁用客户端版本控制。站点特定的配置优先于全局配置。

## <a name="tasks-you-can-perform"></a>可执行的任务

您可以在“新建客户端版本配置”或“编辑客户端版本配置”页上执行以下任务：

- 添加或修改客户端版本配置的名称。

- 启用或禁用全局或某特定站点的客户端版本控制。

- 添加或修改客户端版本配置的默认操作。

## <a name="ui-reference"></a>用户界面参考

下表介绍了该页上的菜单、命令、字段和属性。

- **范围** 标识客户端 (全局) 站点范围。

- **名称** 可以添加或修改客户端版本配置的名称。

- **启用版本控制** 您可以全局或为站点启用或禁用客户端版本控制，具体取决于配置的范围。

- **默认操作** 可以选择当用户尝试使用没有特定客户端版本策略的客户端应用程序登录时应用的默认操作。 可以选择下列选项：

  - **允许** 如果客户端版本与客户端版本策略列表中的任何筛选器不匹配，则允许客户端登录。

  - **阻止** 如果客户端版本与客户端版本策略列表中的任何筛选器不匹配，则阻止客户端登录。

  - **使用 URL 阻止** 如果客户端版本与客户端版本策略列表中的任何筛选器不匹配，则阻止客户端登录，并包含一条错误消息，其中包含可下载较新客户端的 URL。

  - **允许使用 URL** 如果客户端版本与客户端版本策略列表中的任何筛选器不匹配，则允许客户端登录，并包含一条错误消息，其中包含可下载较新客户端的 URL。

  - **URL** 如果选择" **使用 URL 阻止** "或"允许使用 **URL"，** 可以指定要包括在错误消息中的客户端下载 URL。

有关客户端和客户端版本之间的交互性的详细信息，请参阅规划文档中的 [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx)。 有关使用客户端版本配置的详细信息，请参阅操作文档中的[Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx)。

