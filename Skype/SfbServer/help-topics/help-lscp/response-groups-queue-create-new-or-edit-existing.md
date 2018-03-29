---
title: 响应组队列创建新模板或编辑现有的
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.RgsQueueEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cbdde536-8668-4a08-9862-8615e8691fd7
description: 直到代理应答呼叫，响应组队列包含响应组对的调用。
ms.openlocfilehash: f5223aaca700c10a25631131db69a55de1362ddc
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="response-groups-queue-create-new-or-edit-existing"></a>响应组队列：创建新的或编辑现有的
 
直到代理应答呼叫，响应组队列包含响应组对的调用。
  
## <a name="ui-reference"></a>用户界面参考

下表介绍了该页上的各个字段。
  
- **名称**每个队列都必须具有名称。 键入该队列的一个描述性名称。
    
- **说明**此字段是可选的。 使用它来提供有关队列的其他详细信息。
    
- **组**选择您想要分配到该队列的代理组。 单击**选择**要将代理组添加到列表。 单击**删除**以从列表中删除选定的代理组。
    
    向上和向下箭头可在列表中向上和向下移动所选代理组。 代理组的顺序会影响可用的代理搜索 Skype 业务服务器的顺序。 即，首先搜索列表中的第一个组以查找可用代理，随后是第二个组，依此类推。
    
- **启用队列超时**选中此复选框可以指定调用方暂停代理应答呼叫等待的时间最长。 如果您选择此选项，您还需要指定以下：
    
  - **超时时间 （秒）**选择或键入的最大调用方可以等待代理应答呼叫之前的秒数。
    
  - **调用操作**选择调用超时时发生的动作。可用的选项有：
    
  - **断开连接**
    
  - **转发到语音邮件**如果您选择此选项，在**SIP 地址**，键入格式 sip 中的语音邮件地址：<username> @ <domainname> (例如，sip:bob@contoso.com)。
    
  - **转发到电话号码**如果您选择此选项，在**SIP 地址**键入格式 sip 中的电话号码：<number> @ <domainname> (例如，sip:+14255550121@contoso.com)。
    
  - **转发到的 SIP 地址**选择此选项可将呼叫转接至另一个用户。 在**SIP 地址**，键入用户在格式 sip URI:<username>@<domainname>。
    
  - **转发到另一个队列**如果您选择此选项，浏览到队列接收调用时，调用的超时时间。
    
- **启用队列溢出**选中此复选框可以指定调用队列可以容纳的最大数量。 如果您选择此选项，您还需要指定以下：
    
  - **调用的最大数目**选择或键入的调用队列所能容纳的最大数目。
    
  - **将呼叫转接**选择呼叫的满足队列溢出阈值时采取行动。
    
  - **调用操作**选择满足队列溢出阈值时发生的操作。 可用的选项有：
    
  - **断开连接**
    
  - **转发到语音邮件**如果您选择此选项，在**SIP 地址**，键入格式 sip 中的语音邮件地址：<username> @ <domainname> (例如，sip:bob@contoso.com)。
    
  - **转发到电话号码**如果您选择此选项，在**SIP 地址**键入格式 sip 中的电话号码：<number> @ <domainname> (例如，sip:+14255550121@contoso.com)。
    
  - **转发到的 SIP 地址**选择此选项可将呼叫转接至另一个用户。 在**SIP 地址**，键入用户在格式 sip URI:<username>@<domainname>。
    
  - **转发到另一个队列**如果您选择此选项，浏览到要满足队列溢出阈值时接收调用队列。
    
有关响应组的特性和功能的详细信息，请参阅规划文档中[规划业务服务器 2015年的 Skype 的响应组应用程序](../../plan-your-deployment/enterprise-voice-solution/response-group.md)。 有关如何使用队列的详细信息，请参阅[管理响应组队列](http://technet.microsoft.com/library/1e91720c-ab67-4dfb-b30c-0ef2a8012310.aspx)操作文档中。
  

