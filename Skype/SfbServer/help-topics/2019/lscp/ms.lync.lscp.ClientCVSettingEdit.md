---
title: 客户端版本配置 创建新的或编辑现有的
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientCVSettingEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 07fec57c-5cd3-422a-829a-0b62cb0092c4
ROBOTS: NOINDEX, NOFOLLOW
description: 客户端版本配置设置用于打开或关闭客户端版本控制。 全局客户端版本配置随 Skype for Business Server 一起安装，用于启用或禁用整个服务器部署的客户端版本控制。 当全局配置处于启用状态时，用户尝试登录后您所拥有的任何客户端版本策略都将生效。 如果不希望发生任何客户端版本控制，则可以禁用全局客户端版本配置。
ms.openlocfilehash: 67d151a4aaa6ca1e80382977140cbebee2c302ec
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120281"
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

  - **允许** 允许客户端在客户端版本策略列表中不匹配任何筛选器时登录。

  - **阻止** 如果客户端版本不匹配客户端版本策略列表中的任何筛选器，则阻止客户端登录。

  - **使用 URL 阻止** 如果客户端版本不匹配客户端版本策略列表中的任何筛选器，则阻止客户端登录，并包括一条错误消息，其中包含可下载较新客户端的 URL。

  - **允许使用 URL** 如果客户端版本不匹配客户端版本策略列表中的任何筛选器，则允许客户端登录，并包含一条错误消息，其中包含可下载较新客户端的 URL。

  - **URL** 如果选择" **使用 URL 阻止** "或"允许使用 **URL"，** 可以指定要包括在错误消息中的客户端下载 URL。

有关客户端和客户端版本之间的互操作性的详细信息，请参阅规划文档中的 Client [Interoperability。](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013) 有关使用客户端版本配置的详细信息，请参阅操作文档中的[Modify the Default Action for Clients Not Explicitly Supported or Restricted](/previous-versions/office/lync-server-2013/lync-server-2013-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted)。