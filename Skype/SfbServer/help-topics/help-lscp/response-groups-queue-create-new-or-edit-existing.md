---
title: 响应组队列新建或编辑现有
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.RgsQueueEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cbdde536-8668-4a08-9862-8615e8691fd7
description: 响应组队列将呼叫保留到响应组, 直到工程师应答呼叫。
ms.openlocfilehash: 3eba4fbba662ecc1497b5c8d0aac14ce5083c1ea
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286346"
---
# <a name="response-groups-queue-create-new-or-edit-existing"></a>响应组队列：创建新的或编辑现有的

响应组队列将呼叫保留到响应组, 直到工程师应答呼叫。

## <a name="ui-reference"></a>用户界面参考

下表介绍了该页上的各个字段。

- **名称**每个队列必须有一个名称。 键入队列的描述性名称。

- **说明**此字段是可选的。 使用它提供有关队列的其他详细信息。

- **组**选择要分配给队列的代理组。 单击 "**选择**" 将代理组添加到列表。 单击 "**删除**", 从列表中删除所选的代理组。

    向上和向下箭头可在列表中向上和向下移动所选代理组。 代理组的顺序影响 Skype for Business 服务器搜索可用代理的顺序。 即，首先搜索列表中的第一个组以查找可用代理，随后是第二个组，依此类推。

- **启用队列超时**选中此复选框以指定呼叫者在代理应答呼叫之前等待保持的最长时间。 如果选择此选项, 还需要指定以下内容:

  - **超时时间 (秒)** 选择或键入呼叫者在工程师应答呼叫之前可以等待的最大秒数。

  - **通话操作**选择通话超时后出现的操作。您的选择是:

  - **断开连接**

  - **转发到语音邮件**如果选择此选项, 请在 " **sip 地址**" 中以 sip<username> @ <domainname>格式键入语音邮件地址 (例如, sip:bob@contoso.com)。

  - **转发到电话号码**如果选择此选项, 则在 " **sip 地址**" 中, 键入 sip 的格式的<number> @ <domainname>电话号码: (例如, sip:+14255550121@contoso.com)。

  - **转发到 SIP 地址**选择此选项可将呼叫转移到其他用户。 在 " **sip 地址**" 中, 在 "设置 SIP 格式" 中键入<username>@<domainname>用户的 URI:。

  - **转发到另一个队列**如果选择此选项, 请通过浏览找到通话超时时接收呼叫的队列。

- **启用队列溢出**选中此复选框以指定队列可以保留的最大通话数。 如果选择此选项, 还需要指定以下内容:

  - **最大通话次数**选择或键入队列可以保留的最大通话数。

  - **转接呼叫**选择达到队列溢出阈值时要采取的措施。

  - **通话操作**选择满足队列溢出阈值时发生的操作。 您的选择是:

  - **断开连接**

  - **转发到语音邮件**如果选择此选项, 请在 " **sip 地址**" 中以 sip<username> @ <domainname>格式键入语音邮件地址 (例如, sip:bob@contoso.com)。

  - **转发到电话号码**如果选择此选项, 则在 " **sip 地址**" 中, 键入 sip 的格式的<number> @ <domainname>电话号码: (例如, sip:+14255550121@contoso.com)。

  - **转发到 SIP 地址**选择此选项可将呼叫转移到其他用户。 在 " **sip 地址**" 中, 在 "设置 SIP 格式" 中键入<username>@<domainname>用户的 URI:。

  - **转发到另一个队列**如果选择此选项, 请浏览到满足队列溢出阈值时要接收呼叫的队列。

有关响应组功能和功能的详细信息, 请参阅规划文档中的[Skype For Business Server 2015 中的 "响应组" 应用计划](../../plan-your-deployment/enterprise-voice-solution/response-group.md)。 有关使用队列的详细信息，请参阅操作文档中的[Managing Response Group Queues](https://technet.microsoft.com/library/1e91720c-ab67-4dfb-b30c-0ef2a8012310.aspx)。


