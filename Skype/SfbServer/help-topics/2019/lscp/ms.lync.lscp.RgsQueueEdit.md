---
title: 响应组队列创建新的或编辑现有的
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.RgsQueueEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: cbdde536-8668-4a08-9862-8615e8691fd7
ROBOTS: NOINDEX, NOFOLLOW
description: 响应组队列保留对响应组的呼叫，直到代理应答呼叫。
ms.openlocfilehash: ee99ac8cb4f3ea9c2f0e1804914eaf30c909a2b0
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118801"
---
# <a name="response-groups-queue-create-new-or-edit-existing"></a>响应组队列：创建新的或编辑现有的

响应组队列保留对响应组的呼叫，直到代理应答呼叫。

## <a name="ui-reference"></a>用户界面参考

下表介绍了该页上的各个字段。

- **名称** 每个队列都必须有一个名称。 键入队列的描述性名称。

- **说明** 此字段是可选的。 使用它提供有关队列的其他详细信息。

- **组** 选择要分配给队列的代理组。 单击 **"选择** "将代理组添加到列表中。 单击 **"** 删除"从列表中删除所选代理组。

    向上和向下箭头可在列表中向上和向下移动所选代理组。 代理组的顺序会影响 Skype for Business Server 搜索可用代理的顺序。 即，首先搜索列表中的第一个组以查找可用代理，随后是第二个组，依此类推。

- **启用队列退出** 选中此复选框可指定呼叫者在代理应答呼叫之前等待等待的最大时间。 如果选择此选项，则还需要指定以下内容：

  - **时间段的 (秒)** 选择或键入呼叫者在代理应答呼叫之前可以等待的最大秒数。

  - **呼叫操作** 选择在呼叫退出时发生的操作。你的选择是：

  - **Disconnect**

  - **转发到语音邮件** 如果选择此选项，请在 **"SIP** 地址"中，键入格式为 sip： 的语音邮件 (<username> @ <domainname> 例如，sip:bob@contoso.com) 。

  - **转发到电话号码** 如果选择此选项，请在 **"SIP** 地址"中，键入格式为 sip： <number> @ <domainname> (例如，sip:+14255550121@contoso.com) 。

  - **转发到 SIP 地址** 选择此选项以将呼叫转发给其他用户。 在 **"SIP 地址**"中，键入用户的 URI，格式为 <username> @ <domainname> sip：。

  - **转发到另一个队列** 如果选择此选项，请浏览到呼叫退出时要接收呼叫的队列。

- **启用队列溢出** 选中此复选框可指定队列可以保留的最大呼叫数。 如果选择此选项，则还需要指定以下内容：

  - **最大呼叫数** 选择或键入队列可以保留的最大呼叫数。

  - **转发呼叫** 选择在达到队列溢出阈值时要采取措施的呼叫。

  - **呼叫操作** 选择在达到队列溢出阈值时发生的操作。 选项包括：

  - **Disconnect**

  - **转发到语音邮件** 如果选择此选项，请在 **"SIP** 地址"中，键入格式为 sip： 的语音邮件 (<username> @ <domainname> 例如，sip:bob@contoso.com) 。

  - **转发到电话号码** 如果选择此选项，请在 **"SIP** 地址"中，键入格式为 sip： <number> @ <domainname> (例如，sip:+14255550121@contoso.com) 。

  - **转发到 SIP 地址** 选择此选项以将呼叫转发给其他用户。 在 **"SIP 地址**"中，键入用户的 URI，格式为 <username> @ <domainname> sip：。

  - **转发到另一个队列** 如果选择此选项，请浏览到在达到队列溢出阈值时接收呼叫的队列。

有关响应组特性和功能的详细信息，请参阅规划文档中的 Plan [for the Response Group application in Skype for Business Server。](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) 有关使用队列的详细信息，请参阅操作文档中的[Managing Response Group Queues](/previous-versions/office/lync-server-2013/lync-server-2013-managing-response-group-queues)。