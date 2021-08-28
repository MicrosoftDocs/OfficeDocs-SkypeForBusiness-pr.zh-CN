---
title: 客户端版本策略
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
- ms.lync.lscp.ClientCVPolicyMain
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 4f84bc0f-e1df-4acb-b8ef-57f165b0153b
description: 可以指定环境中支持的客户端版本。 当两个不同版本的客户端交互时，其中一个客户端的可用功能会受到另一个客户端的功能的限制。 为了充分利用 Skype for Business Server 2015 中包含的功能并改进整体用户体验，您可以使用客户端版本筛选器来限制环境中使用的客户端版本。 使用客户端版本筛选器还有助于降低支持多个客户端版本的相关成本。
ms.openlocfilehash: 9bd78d82f182fe8c34ec3271313584502a0f63ce
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58615898"
---
# <a name="client-version-policy"></a>客户端版本策略

可以指定环境中支持的客户端版本。 当两个不同版本的客户端交互时，其中一个客户端的可用功能会受到另一个客户端的功能的限制。 为了充分利用 Skype for Business Server 2015 中包含的功能并改进整体用户体验，您可以使用客户端版本筛选器来限制环境中使用的客户端版本。 使用客户端版本筛选器还有助于降低与支持多个客户端版本关联的成本。

## <a name="tasks-you-can-perform"></a>可执行的任务

您可以在“客户端版本策略”页上执行以下任务：

- 编辑默认策略 ( **全局**) 客户端版本策略。

- 为特定站点或池创建客户端版本策略。

- 创建可分配给各个用户的客户端版本策略。

> [!NOTE]
> 由于匿名用户未与用户、站点或服务关联，因此匿名用户仅受全局级别策略的影响。

## <a name="ui-reference"></a>用户界面参考

下表介绍了该页上的菜单、命令、字段和属性。

- **新建** 可以创建以下一个或多个客户端版本策略：

  - 站点策略

  - 池策略

  - 用户策略

- **编辑** 可以更改任何客户端版本策略的选项。 使用此选项，可以执行以下操作：

  - **显示详细信息** 此选项将打开一个对话框，您可以在其中更改客户端版本策略的选项。

  - **全选** 此选项选择列表中的所有客户端版本策略。

  - **删除** 此选项将删除所有选定的客户端版本策略。

- **刷新** 可以刷新客户端版本策略列表以验证所有客户端版本策略的选项状态。

有关客户端与客户端版本之间的互操作性的详细信息，请参阅规划文档中的 [Client Interoperability in Lync 2013 Preview](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013)。有关使用客户端版本策略的详细信息，请参阅操作文档中的[Specify the Client Versions Supported in Your Organization](/previous-versions/office/lync-server-2013/lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013)。