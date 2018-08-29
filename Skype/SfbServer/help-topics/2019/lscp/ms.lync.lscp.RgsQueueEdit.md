---
title: 响应组队列创建新的或编辑现有的
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.RgsQueueEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cbdde536-8668-4a08-9862-8615e8691fd7
ROBOTS: NOINDEX, NOFOLLOW
description: 响应组队列保留对响应组呼叫，直到代理应答呼叫。
ms.openlocfilehash: b55f1ad12369824a60282294dacfc63177675e02
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/29/2018
ms.locfileid: "23263835"
---
# <a name="response-groups-queue-create-new-or-edit-existing"></a>响应组队列：创建新的或编辑现有的

响应组队列保留对响应组呼叫，直到代理应答呼叫。

## <a name="ui-reference"></a>用户界面参考

下表介绍了该页上的各个字段。

- **名称**每个队列必须有一个名称。 键入队列的描述性名称。

- **说明**此字段是可选的。 使用它来提供有关队列的其他详细信息。

- **组**选择您想要分配给队列的代理组。 单击**选择**要添加到列表的代理组。 单击**删除**以从列表中删除选定的代理组。

    向上和向下箭头可在列表中向上和向下移动所选代理组。 代理组的顺序影响业务服务器 Skype 搜索可用代理的顺序。 即，首先搜索列表中的第一个组以查找可用代理，随后是第二个组，依此类推。

- **启用队列超时**选中此复选框，以指定的呼叫者处于保持状态状态之前要等待代理应答呼叫的时间最长时段。 如果选择此选项，您还需要指定以下：

  - **超时时段 （秒）** 选择或键入最大呼叫者等待代理应答呼叫的秒数。

  - **呼叫操作**选择呼叫超时时时发生的操作。您选择的是：

  - **断开连接**

  - **转接到语音邮件**如果选择此选项，请在**SIP 地址**中，键入语音邮件地址格式 sip:<username> @ <domainname> (例如，sip:bob@contoso.com)。

  - **转接到电话号码**如果选择此选项，在**SIP 地址**中键入该电话号码格式 sip:<number> @ <domainname> (例如，sip:+14255550121@contoso.com)。

  - **转接到 SIP 地址**选择此选项可将呼叫转接至另一个用户。 在**SIP 地址**，键入格式 sip 用户的 URI:<username>@<domainname>。

  - **转接至其他队列**如果选择此选项，浏览到队列接收呼叫的呼叫超时。

- **启用队列溢出**选中此复选框，若要指定队列可以容纳的呼叫的最大次数。 如果选择此选项，您还需要指定以下：

  - **最大呼叫数**选择或键入的呼叫队列可以容纳的最大数。

  - **将呼叫转接**选择达到队列溢出阈值时执行操作的呼叫。

  - **呼叫操作**选择达到队列溢出阈值时，发生此事件的操作。 您选择的是：

  - **断开连接**

  - **转接到语音邮件**如果选择此选项，请在**SIP 地址**中，键入语音邮件地址格式 sip:<username> @ <domainname> (例如，sip:bob@contoso.com)。

  - **转接到电话号码**如果选择此选项，在**SIP 地址**中键入该电话号码格式 sip:<number> @ <domainname> (例如，sip:+14255550121@contoso.com)。

  - **转接到 SIP 地址**选择此选项可将呼叫转接至另一个用户。 在**SIP 地址**，键入格式 sip 用户的 URI:<username>@<domainname>。

  - **转接至其他队列**如果选择此选项，浏览到在达到队列溢出阈值时接收呼叫的队列。

有关响应组特性和功能的详细信息，请参阅规划文档中的[计划中的业务服务器 Skype 的响应组应用程序](../../../plan-your-deployment/enterprise-voice-solution/response-group.md)。 有关使用队列的详细信息，请参阅操作文档中的[Managing Response Group Queues](https://technet.microsoft.com/library/1e91720c-ab67-4dfb-b30c-0ef2a8012310.aspx) 。


