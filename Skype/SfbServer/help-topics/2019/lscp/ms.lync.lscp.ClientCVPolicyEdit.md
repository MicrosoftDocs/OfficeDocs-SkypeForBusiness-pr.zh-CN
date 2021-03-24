---
title: 客户端版本策略 创建新的或编辑现有的
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientCVPolicyEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: e32c6712-6dc9-4de9-8d74-9fdccf3de1ba
ROBOTS: NOINDEX, NOFOLLOW
description: 可以指定环境中支持的客户端版本。 当两个不同版本的客户端交互时，其中一个客户端的可用功能会受到另一个客户端的功能的限制。
ms.openlocfilehash: 57c273198a9c88ae26540518c9f892b218b96118
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100688"
---
# <a name="client-version-policy-create-new-or-edit-existing"></a>客户端版本策略：创建新的或编辑现有的

可以指定环境中支持的客户端版本。 当两个不同版本的客户端交互时，其中一个客户端的可用功能会受到另一个客户端的功能的限制。 为了充分利用 Skype for Business Server 中包含的功能并改进整体用户体验，可以使用客户端版本筛选器来限制环境中使用的客户端版本。 使用客户端版本筛选器还有助于降低支持多个客户端版本的相关成本。

> [!IMPORTANT]
> 按优先顺序列出筛选器。例如，如果您具有一个筛选器可允许运行版本 1.5 的客户端进行连接，还有另一个筛选器可阻止运行低于 2.0 版本的客户端，则第一个筛选器优先，允许运行版本 1.5 的客户端进行连接。

## <a name="tasks-you-can-perform"></a>可执行的任务

您可以在"新建客户端版本策略"或"编辑客户端版本策略"页上执行 **以下** 任务：

- 添加或修改客户端版本策略的名称或说明。

- 添加或修改客户端版本策略的客户端版本规则。

## <a name="ui-reference"></a>用户界面参考

下表介绍了该页上的菜单、命令、字段和属性。

- **范围** 标识客户端 (站点、池或) 作用域。

- **名称** 可以添加或修改客户端版本策略的名称。

- **说明** 可以添加说明以帮助在"客户端版本策略"页上的列表中标识策略。

- **新建** 可以将新的客户端版本规则添加到策略。

- **显示详细信息** 此选项将打开一个对话框，您可以在其中更改客户端版本规则的选项。

- **删除** 此选项从策略中删除所选的客户端版本规则。

- **向上和向下箭头** 此选项将所选客户端版本规则优先级上移或下移。 将按列出的顺序处理规则。

有关客户端和客户端版本之间的互操作性的详细信息，请参阅客户端 [互操作性](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013)。 有关使用客户端版本策略的详细信息，请参阅操作文档中的[Specify the Client Versions Supported in Your Organization](/previous-versions/office/lync-server-2013/lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013)。