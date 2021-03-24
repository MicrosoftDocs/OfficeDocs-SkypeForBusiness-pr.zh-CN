---
title: 客户端版本配置
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientCVSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cb17314e-b89e-4821-8855-12f8fd2edc9b
description: 除了指定希望在环境中支持的客户端版本之外，还可以指定尚未定义版本策略的客户端的默认操作。这样可以限制在环境中使用的客户端版本，从而帮助您控制与支持多个客户端版本相关的成本。
ms.openlocfilehash: 31facafd00a25993aa16f5d89b1fad5a97e566a9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095616"
---
# <a name="client-version-configuration"></a>客户端版本配置

除了指定希望在环境中支持的客户端版本之外，还可以指定尚未定义版本策略的客户端的默认操作。这样可以限制在环境中使用的客户端版本，从而帮助您控制与支持多个客户端版本相关的成本。

## <a name="tasks-you-can-perform"></a>可执行的任务

您可以在“客户端版本配置”页上执行以下任务：

- 编辑默认的全局 **()** 客户端版本配置。

- 为特定站点创建客户端版本配置。

- 启用和禁用现有客户端版本配置。

> [!NOTE]
> 由于匿名用户未与站点关联，因此匿名用户仅受全局级别策略的影响。

## <a name="ui-reference"></a>用户界面参考

下表介绍了该页上的菜单、命令、字段和属性。

- **新建** 您可以为特定站点创建客户端版本配置。

- **编辑** 可以更改任何客户端版本策略的选项。 使用此选项，可以执行以下操作：

  - **显示详细信息** 此选项将打开一个对话框，您可以在其中更改客户端版本配置的选项。

  - **全选** 此选项选择列表中的所有客户端版本配置。

  - **删除** 此选项将删除所有选定的客户端版本配置。

- **刷新** 可以刷新客户端版本配置列表以验证所有客户端版本配置的选项状态。

有关客户端和客户端版本之间的交互性的详细信息，请参阅规划文档中的 [Client Interoperability in Lync 2013 Preview](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013)。 有关使用客户端版本配置的详细信息，请参阅操作文档中的[Modify the Default Action for Clients Not Explicitly Supported or Restricted](/previous-versions/office/lync-server-2013/lync-server-2013-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted)。