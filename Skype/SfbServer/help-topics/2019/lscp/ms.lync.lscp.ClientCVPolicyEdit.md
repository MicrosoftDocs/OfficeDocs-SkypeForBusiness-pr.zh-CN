---
title: 客户端版本策略新建或编辑现有
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e32c6712-6dc9-4de9-8d74-9fdccf3de1ba
ROBOTS: NOINDEX, NOFOLLOW
description: 可以指定环境中支持的客户端版本。 当两个不同版本的客户端交互时，其中一个客户端的可用功能会受到另一个客户端的功能的限制。
ms.openlocfilehash: 6a0f8db06f3e4e4283cd5c574f5e5f1dd566633c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34300544"
---
# <a name="client-version-policy-create-new-or-edit-existing"></a>客户端版本策略：创建新的或编辑现有的

可以指定环境中支持的客户端版本。 当两个不同版本的客户端交互时，其中一个客户端的可用功能会受到另一个客户端的功能的限制。 为了最大程度地利用 Skype for Business 服务器中包含的功能并提高总体用户体验, 你可以使用客户端版本筛选器来限制你的环境中使用的客户端版本。 使用客户端版本筛选器还有助于降低支持多个客户端版本的相关成本。

> [!IMPORTANT]
> 按优先顺序列出筛选器。例如，如果您具有一个筛选器可允许运行版本 1.5 的客户端进行连接，还有另一个筛选器可阻止运行低于 2.0 版本的客户端，则第一个筛选器优先，允许运行版本 1.5 的客户端进行连接。

## <a name="tasks-you-can-perform"></a>可执行的任务

您可以在“**新建客户端版本策略**”或“**编辑客户端版本策略**”页上执行以下任务：

- 添加或修改客户端版本策略的名称或描述。

- 添加或修改客户端版本策略的客户端版本规则。

## <a name="ui-reference"></a>用户界面参考

下表介绍了该页上的菜单、命令、字段和属性。

- **范围**标识客户端版本策略的范围 (网站、池或用户)。

- **名称**你可以添加或修改客户端版本策略的名称。

- **说明**你可以在 "客户端版本策略" 页上的列表中添加说明来帮助标识策略。

- **新**你可以将新的客户端版本规则添加到策略。

- **显示详细信息**此选项将打开一个对话框, 您可以在其中更改客户端版本规则的选项。

- **删除**此选项将从策略中删除所选的客户端版本规则。

- **向上键和向下键**此选项将按优先级向上或向下移动选定的客户端版本规则。 按列出的顺序处理规则。

有关客户端和客户端版本之间的互操作性的详细信息, 请参阅[客户端互操作](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) 有关使用客户端版本策略的详细信息，请参阅操作文档中的[Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx)。

