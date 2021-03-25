---
title: 选择代理
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.RgsSelAgent
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: b5cf912b-8273-4c2c-a1e5-f25530b264d0
ROBOTS: NOINDEX, NOFOLLOW
description: 代理是指定应答响应组呼叫的用户。 响应组必须具有一个分配的代理组来识别可接收针对响应组的呼叫的代理。 创建代理组的一种方法就是通过选择合格用户来定义自定义组。 符合条件的用户已启用 Skype for Business Server 和 企业语音。
ms.openlocfilehash: 399ad65a2fe232d217ce4891061aeed8284277b9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118781"
---
# <a name="select-agents"></a>选择代理

代理是指定应答响应组呼叫的用户。 响应组必须具有一个分配的代理组来识别可接收针对响应组的呼叫的代理。 创建代理组的一种方法就是通过选择合格用户来定义自定义组。 符合条件的用户已启用 Skype for Business Server 和 企业语音。

使用“选择代理”对话框可选择要添加到代理组的用户。

## <a name="ui-reference"></a>用户界面参考

下表介绍了“选择代理”对话框中的各个控件。

- **查找** 搜索用户的 SIP 地址显示名称地址。 输入地址或名称的一部分或全部。 将搜索框留空，以显示已启用 Skype for Business Server 的所有用户企业语音。

- **要显示的最大用户数** 更改显示的返回结果数。 如果您希望获得许多结果，请使用此计数器来限制搜索。

下表介绍了“选择代理”对话框中的各个字段。

- **代理** 显示搜索返回的用户名。

- **SIP 地址** 显示搜索返回的用户 SIP 地址。

- **电话** 显示为用户 **定义的"电话"** 字段的值。

- **已启用** 显示为用户定义的 **Enabled for Lync Server** 字段的值。

有关使用代理组的详细信息，请参阅操作文档中的[Managing Agent Groups](/previous-versions/office/lync-server-2013/lync-server-2013-managing-response-group-agent-groups)。